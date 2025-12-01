<template>
  <section class="profile">
    <img class="profile-pic" :src="profilePic" alt="Profile picture" />

    <div class="profile-content">
      <h1 class="name">Thomas Lee</h1>
      <p class="role">Computer Science (Software Engineer) Student at Louisiana State University</p>
      <p class="lead">I build accessible, responsive web applications and clean user interfaces. I focus on performance, maintainability, and delivering delightful user experiences.</p>
      <p>
        <a class="button" href="#projects">View projects</a>
        <a class="button muted" href="#contact">Contact me</a>
      </p>
    </div>
  </section>
</template>

<script setup>
import { computed } from 'vue'

const profilePic = computed(() => {
  const base = import.meta.env.BASE_URL || '/'
  return `${base}profilepicture.jpg`
})
</script>

<style scoped>
.profile {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  align-items: center;
  text-align: center;
}

.profile-pic {
  width: 112px;
  height: 112px;
  object-fit: cover;
  border-radius: 999px;
  box-shadow: 0 8px 40px rgba(118,185,0,0.08), inset 0 0 18px rgba(118,185,0,0.02);
  border: 2px solid rgba(118,185,0,0.12);
  flex-shrink: 0;
}

.profile-content { max-width: 820px }

.name { margin: 0 0 0.25rem 0; font-size: 1.6rem }

.role { margin: 0 0 0.5rem 0; color: var(--nv-green-2); font-weight: 600 }

.lead { margin: 0 0 0.75rem 0; color: var(--muted) }

.button {
  display: inline-block;
  margin: 0 .4rem;
  padding: .5rem .9rem;
  border-radius: 6px;
  background: linear-gradient(180deg, var(--nv-green), var(--nv-green-2));
  color: #07120a;
  text-decoration: none;
  font-weight: 600;
}

.button.muted {
  background: transparent;
  color: var(--muted);
  border: 1px solid rgba(255,255,255,0.03);
}

@media (min-width: 700px) {
  .profile { flex-direction: column }
}
</style>
