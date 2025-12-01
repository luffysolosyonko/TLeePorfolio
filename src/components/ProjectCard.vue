<script setup>
import { ref } from 'vue'
const { project } = defineProps({ project: Object })

const showVideo = ref(false)
const embedUrl = ref('')

function toEmbedUrl(url) {
  if (!url) return ''
  try {
    const u = new URL(url)
    if (u.hostname.includes('youtu.be')) {
      const id = u.pathname.replace('/', '')
      return `https://www.youtube.com/embed/${id}?rel=0&autoplay=1`
    }
    if (u.hostname.includes('youtube.com')) {
      const v = u.searchParams.get('v')
      if (v) return `https://www.youtube.com/embed/${v}?rel=0&autoplay=1`
      if (u.pathname.startsWith('/embed/')) return url + '?rel=0&autoplay=1'
    }
  } catch (e) {
    return url
  }
  return url
}

function openVideo(url) {
  embedUrl.value = toEmbedUrl(url)
  showVideo.value = true
  document.documentElement.style.overflow = 'hidden'
}

function closeVideo() {
  showVideo.value = false
  embedUrl.value = ''
  document.documentElement.style.overflow = ''
}
</script>

<template>
  <article class="card">
    <div class="thumb" :style="project.image ? { backgroundImage: `url(${project.image})` } : {}">
      <span v-if="!project.image" class="thumb-placeholder">{{ project.title.charAt(0) }}</span>
    </div>

    <div class="card-body">
      <h3 class="card-title">{{ project.title }}</h3>
      <p class="card-desc">{{ project.description }}</p>
      <p class="card-links">
        <button v-if="project.video" @click="openVideo(project.video)" type="button" class="video-btn" aria-label="Play demo">
          <svg viewBox="0 0 24 24" width="16" height="16" fill="currentColor" aria-hidden="true"><path d="M10 8.64L15.27 12 10 15.36V8.64z"/></svg>
          <span class="sr-only">Demo</span>
        </button>

        <a v-if="project.repo && project.repo !== '#'" :href="project.repo" target="_blank" rel="noopener" class="code-link" aria-label="View source on GitHub">
          <svg viewBox="0 0 24 24" width="16" height="16" fill="currentColor" aria-hidden="true"><path d="M12 .5C5.65.5.5 5.65.5 12c0 5.08 3.29 9.39 7.86 10.91.58.11.79-.25.79-.56 0-.28-.01-1.02-.02-2-3.2.7-3.88-1.54-3.88-1.54-.53-1.36-1.3-1.72-1.3-1.72-1.06-.72.08-.71.08-.71 1.17.08 1.78 1.2 1.78 1.2 1.04 1.78 2.73 1.27 3.4.97.11-.76.41-1.27.74-1.56-2.55-.29-5.24-1.28-5.24-5.7 0-1.26.45-2.29 1.19-3.1-.12-.29-.52-1.47.11-3.06 0 0 .97-.31 3.18 1.18a11.06 11.06 0 012.9-.39c.98 0 1.97.13 2.9.39 2.2-1.49 3.17-1.18 3.17-1.18.64 1.59.24 2.77.12 3.06.74.81 1.19 1.84 1.19 3.1 0 4.43-2.69 5.4-5.25 5.69.42.36.8 1.08.8 2.18 0 1.58-.01 2.86-.01 3.25 0 .31.21.68.8.56C20.71 21.39 24 17.08 24 12c0-6.35-5.15-11.5-11.5-11.5z"/></svg>
          <span class="sr-only">Code</span>
        </a>

        <span v-else class="disabled" aria-hidden="true">
          <svg viewBox="0 0 24 24" width="16" height="16" fill="currentColor" aria-hidden="true"><path d="M12 .5C5.65.5.5 5.65.5 12c0 5.08 3.29 9.39 7.86 10.91.58.11.79-.25.79-.56 0-.28-.01-1.02-.02-2-3.2.7-3.88-1.54-3.88-1.54-.53-1.36-1.3-1.72-1.3-1.72-1.06-.72.08-.71.08-.71 1.17.08 1.78 1.2 1.78 1.2 1.04 1.78 2.73 1.27 3.4.97.11-.76.41-1.27.74-1.56-2.55-.29-5.24-1.28-5.24-5.7 0-1.26.45-2.29 1.19-3.1-.12-.29-.52-1.47.11-3.06 0 0 .97-.31 3.18 1.18a11.06 11.06 0 012.9-.39c.98 0 1.97.13 2.9.39 2.2-1.49 3.17-1.18 3.17-1.18.64 1.59.24 2.77.12 3.06.74.81 1.19 1.84 1.19 3.1 0 4.43-2.69 5.4-5.25 5.69.42.36.8 1.08.8 2.18 0 1.58-.01 2.86-.01 3.25 0 .31.21.68.8.56C20.71 21.39 24 17.08 24 12c0-6.35-5.15-11.5-11.5-11.5z"/></svg>
          <span class="sr-only">Code</span>
        </span>
      </p>
    </div>
  </article>
  <div v-if="showVideo" class="video-modal" @click.self="closeVideo">
    <div class="video-wrap">
      <button class="modal-close" @click="closeVideo" aria-label="Close video">✕</button>
      <iframe class="video-frame" :src="embedUrl" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen title="Project demo"></iframe>
    </div>
  </div>
</template>

<style scoped>
.card {
  display: flex;
  gap: .9rem;
  padding: .9rem;
  border-radius: 10px;
  background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(0,0,0,0.06));
  border: 1px solid rgba(118,185,0,0.06);
  box-shadow: 0 10px 30px rgba(2,6,23,0.6);
  align-items: center;
}

.thumb {
  width: 84px;
  height: 84px;
  background-color: rgba(118,185,0,0.06);
  background-size: cover;
  background-position: center;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--nv-green-2);
  border: 1px solid rgba(118,185,0,0.06);
}

.thumb-placeholder { font-weight: 700; font-size: 1.6rem }

.card-body { flex: 1 }
.card-title { margin: 0 0 .25rem 0; color: #e9f9d9 }
.card-desc { margin: 0 0 .65rem 0; color: var(--muted) }
.card-links a { margin-right: .6rem; color: var(--nv-green); text-decoration: none }
.card-links .disabled { margin-right: .6rem; color: rgba(255,255,255,0.25); }

/* accessibility helper */
.sr-only { position: absolute; width: 1px; height: 1px; padding: 0; margin: -1px; overflow: hidden; clip: rect(0,0,0,0); white-space: nowrap; border: 0 }

.code-link svg { color: var(--nv-green); vertical-align: middle }
.card-links .disabled svg { color: rgba(255,255,255,0.25) }

.card:hover { transform: translateY(-4px); transition: transform .18s ease-in-out; box-shadow: 0 20px 50px rgba(118,185,0,0.06) }

.video-btn { background: transparent; border: 1px solid rgba(118,185,0,0.12); color: var(--nv-green); padding: .5rem .7rem; border-radius: 8px; margin-right: .6rem; cursor: pointer; display: inline-flex; align-items: center; gap: .4rem; font-size: 0.95rem }
.video-btn:hover { background: rgba(118,185,0,0.06) }
.video-btn svg { width: 20px; height: 20px }

.video-modal { position: fixed; inset: 0; display: flex; align-items: center; justify-content: center; background: rgba(0,0,0,0.7); z-index: 1200 }
.video-wrap { position: relative; width: min(920px, 95%); aspect-ratio: 16/9; background: #000; border-radius: 8px; overflow: hidden }
.video-frame { width: 100%; height: 100%; display: block; }
.modal-close { position: absolute; right: 8px; top: 8px; background: rgba(0,0,0,0.4); color: #fff; border: none; padding: .25rem .5rem; border-radius: 6px; cursor: pointer }
</style>
