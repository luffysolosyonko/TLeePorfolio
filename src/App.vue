<script setup>
import Profile from './components/Profile.vue'
import Projects from './components/Projects.vue'
import WorkExperience from './components/WorkExperience.vue'
import Resume from './components/Resume.vue'
import About from './components/About.vue'
import Contact from './components/Contact.vue'
import Awards from './components/Awards.vue'
</script>

<template>
  <div id="portfolio">
    <header class="site-header">
      <Profile />
    </header>

    <main class="site-main">
      <Projects />
      <WorkExperience />
      <div class="section-divider" aria-hidden="true"></div>
      <Resume />
      <About />
      <Awards />
      <Contact />
      
    </main>
  </div>
</template>

<style scoped>
:root {
  --container-max: 1100px;
}

#portfolio {
  max-width: var(--container-max);
  margin: 0 auto;
  padding: 2rem 1rem;
}

.site-header {
  margin-bottom: 2rem;
}

.site-main {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2.75rem;
}

.site-main > * {
  width: 100%;
  max-width: 900px;
  margin: 0 auto;
}
</style>
