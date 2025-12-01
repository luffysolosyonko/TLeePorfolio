<template>
  <aside id="contact" class="contact">
    <h2>Contact</h2>

    <p>If you'd like to chat about a project or opportunity, email me at <a :href="mailto">mathheejoo@gmail.com</a>.</p>

    <p>
      <strong>Links:</strong>
      <br />
      <a :href="linkedin" target="_blank" rel="noopener"> 
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" aria-hidden="true" style="vertical-align:middle; margin-right:6px"><path d="M4.98 3.5C4.98 4.88 3.86 6 2.48 6S0 4.88 0 3.5 1.12 1 2.5 1 4.98 2.12 4.98 3.5zM0 8.99h4.97V24H0V8.99zM8.34 8.99h4.77v2.04h.07c.66-1.25 2.28-2.57 4.7-2.57 5.03 0 5.96 3.31 5.96 7.61V24h-4.97v-7.42c0-1.77-.03-4.05-2.47-4.05-2.47 0-2.85 1.93-2.85 3.92V24H8.34V8.99z" fill="currentColor"/></svg>
        LinkedIn
      </a>
      <span style="margin:0 .5rem">•</span>
      <a :href="github" target="_blank" rel="noopener">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" aria-hidden="true" style="vertical-align:middle; margin-right:6px"><path d="M12 .5C5.65.5.5 5.65.5 12c0 5.08 3.29 9.39 7.86 10.91.58.11.79-.25.79-.56 0-.28-.01-1.02-.02-2-3.2.7-3.88-1.54-3.88-1.54-.53-1.36-1.3-1.72-1.3-1.72-1.06-.72.08-.71.08-.71 1.17.08 1.78 1.2 1.78 1.2 1.04 1.78 2.73 1.27 3.4.97.11-.76.41-1.27.74-1.56-2.55-.29-5.24-1.28-5.24-5.7 0-1.26.45-2.29 1.19-3.1-.12-.29-.52-1.47.11-3.06 0 0 .97-.31 3.18 1.18a11.06 11.06 0 012.9-.39c.98 0 1.97.13 2.9.39 2.2-1.49 3.17-1.18 3.17-1.18.64 1.59.24 2.77.12 3.06.74.81 1.19 1.84 1.19 3.1 0 4.43-2.69 5.4-5.25 5.69.42.36.8 1.08.8 2.18 0 1.58-.01 2.86-.01 3.25 0 .31.21.68.8.56C20.71 21.39 24 17.08 24 12c0-6.35-5.15-11.5-11.5-11.5z" fill="currentColor"/></svg>
        GitHub
      </a>
    </p>
  </aside>
</template>

<script setup>
const mailto = 'mailto:mathheejoo@gmail.com'
const github = 'https://github.com/luffysolosyonko'
const linkedin = 'https://www.linkedin.com/in/thomas-lee-842a95265/'
</script>

<style scoped>
.contact {
  padding: 1rem;
  border-radius: 8px;
  background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(0,0,0,0.04));
  border: 1px solid rgba(118,185,0,0.06);
  box-shadow: 0 10px 30px rgba(2,6,23,0.6);
}
.contact h2 { color: var(--nv-green-2) }
.contact a { color: var(--nv-green); text-decoration: none }
</style>
