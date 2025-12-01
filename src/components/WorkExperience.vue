<template>
  <section id="work" class="work-experience nv-card">
    <h2>Work Experience</h2>

    <div class="work-intro">
      <p class="muted">A short summary of my recent roles. For the full resume, see the Resume section below.</p>
    </div>

    <div class="roles">
      <div class="role nv-card">
        <strong>Systems Analyst</strong>
        <div class="muted">LSU, Baton Rouge, Louisiana — Sept. 2025 - Present</div>
        <ul class="muted">
          <li>Managed and optimized Linux-based systems, performing monitoring, log analysis, and troubleshooting to ensure reliable operations.</li>
          <li>Developed shell scripts and automation tools to streamline workflows, enhance database performance, and reduce manual tasks.</li>
          <li>Diagnosed and resolved hardware and software issues, improving system efficiency and supporting university IT infrastructure.</li>
        </ul>
      </div>

      <div class="role nv-card">
        <strong>Undergraduate Robotics Researcher</strong>
        <div class="muted">LSU, Baton Rouge, Louisiana — Sept. 2025 - Present</div>
        <ul class="muted">
          <li>Exploring integration of LLMs with ABB RobotStudio using C# and .NET to simplify robot programming through natural language.</li>
          <li>Designing simulation tools to improve usability of robotics platforms for education, research, and industry.</li>
          <li>Collaborating with faculty on advancing robotics, AI integration, and multipurpose automation applications.</li>
        </ul>
      </div>

      <div class="role nv-card">
        <strong>LSU Tutor</strong>
        <div class="muted">LSU, Baton Rouge, Louisiana — Sept. 2023 - Dec. 2024</div>
        <ul class="muted">
          <li>Delivered personalized instruction in mathematics and computer science, strengthening students' comprehension of foundational concepts.</li>
          <li>Simplified complex problems through clear, step-by-step explanations, improving student engagement and understanding.</li>
          <li>Mentored college freshmen to build strong academic foundations, enhancing their confidence and performance in entry-level courses.</li>
        </ul>
      </div>
    </div>
  </section>
</template>

<style scoped>
.work-experience { padding: 1rem; border-radius: 8px; text-align: center }
.work-experience h2 { color: var(--nv-green-2); margin-top: 0 }
.work-intro { margin-bottom: 1rem }
.roles { display: flex; flex-direction: column; gap: .75rem; align-items: center }
.roles .role { padding: .75rem; text-align: center; width: 100%; max-width: 680px; margin: 0 auto }
.roles .role strong { display: block; color: #e9f9d9; margin-bottom: .25rem }
.roles .role .muted { font-size: .95rem }
</style>
