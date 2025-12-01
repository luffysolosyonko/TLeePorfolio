<template>
  <section id="resume" class="resume-section nv-card">
    <h2>Resume</h2>

    <div class="resume-actions">
      <a class="button" :href="pdfPath" target="_blank" rel="noopener">Open Resume</a>
      <a class="button muted" :href="pdfPath" download>Download</a>
    </div>

    <div class="resume-embed">
      <iframe :src="pdfPath" frameborder="0" aria-label="Resume PDF"></iframe>
    </div>
  </section>
</template>

<script setup>
import { computed } from 'vue'

const pdfPath = computed(() => {
  const base = import.meta.env.BASE_URL || '/'
  return `${base}resumenovember2025.pdf`
})
</script>

<style scoped>
.resume-section { padding: 1rem; border-radius: 8px; text-align: center }
.resume-section h2 { color: var(--nv-green-2); margin-top: 0 }
.resume-actions { margin-bottom: 1rem }
.resume-embed { width: 100%; max-width: 900px; margin: 0 auto; overflow: hidden }
.resume-embed iframe { width: 100%; height: 720px; border: none; display: block }

@media (max-width: 700px) {
  .resume-embed iframe { height: 420px }
}
</style>
