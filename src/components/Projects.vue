<script setup>
import ProjectCard from './ProjectCard.vue'

const projects = [
  {
    id: 1,
    title: 'Poetry Garden',
    description:
      'React, TypeScript, Firebase — Built a full-stack poetry sharing app with Firebase authentication and a real-time database. Designed an interactive flower-association feature to visually represent each poem and optimized a responsive front-end for cross-device publishing and browsing. (Feb 2024–Jun 2024)',
    link: '#',
    repo: 'https://github.com/CSC-3380-Spring-2025/Team-29',
    image: '/React-icon.svg.png'
  },
  {
    id: 2,
    title: 'Discord Workout Tracker',
    description:
      'Node.js, Firebase, Python — Built a Discord bot that logs structured workouts, tracks progress, and estimates calories burned. Integrated Firebase for persistent data storage and generated progress graphs; deployed to Railway with environment variable handling for reliable uptime.',
    link: '#',
    repo: 'https://github.com/luffysolosyonko/discord-workout-tracker',
    image: '/png-clipart-node-js-logo-node-js-javascript-web-application-express-js-computer-software-others-miscellaneous-text-thumbnail.png'
  },
  {
    id: 3,
    title: 'Personality Country Quiz',
    description:
      'HTML, CSS, JavaScript — Web-based personality quiz that recommends ideal travel destinations based on user responses. Implemented a recommendation algorithm and improved load performance by 25% through responsive CSS and layout optimizations.',
    link: '#',
    repo: 'https://github.com/luffysolosyonko/Personalitytravelguide',
    image: '/javascript-logo-javascript-icon-transparent-free-png.webp'
  }
  ,
  {
    id: 4,
    title: 'Heartfusion ',
    description:
      'GameMaker - A game built in GameMaker for Chillenium 2023 at Texas A&M. A top-down shooter where you play as a half human, half dog mix trying to survive against waves of enemies. Features combat system, with health tracker.',
    video: 'https://youtu.be/kD6jbGcpZWM',
    repo: 'https://github.com/luffysolosyonko/Heartfusion',
    image: '/gamemaker-os7p0j98mgnwmrd3pzgoof.webp'
  }
]
</script>

<template>
  <section id="projects" class="projects">
    <h2>Selected Projects</h2>

    <div class="projects-grid">
      <ProjectCard v-for="p in projects" :key="p.id" :project="p" />
    </div>
  </section>
</template>

<style scoped>
.projects { text-align: center }
.projects h2 { margin: 0 0 1rem 0; color: var(--nv-green-2) }
.projects-grid { display: grid; gap: 1rem; grid-template-columns: 1fr }

</style>
