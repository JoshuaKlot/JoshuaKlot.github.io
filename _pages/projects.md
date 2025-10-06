---
title: "Joshua Klotzkin - Projects"
layout: textlay
excerpt: "Projects"
sitemap: false
permalink: /projects
---


<h1>My previous employment/internship experience and projects</h1>
<div class="fade-in">
<div class="project-title">Security System with Raspberry PI, Research Project at Vestal, NY from December 2024-Present
</div>
<p class="project-detail">-Worked with a professor at Binghamton University on a project with group of networked Raspberry Pi</p>
<p class="project-detail">-Project goal is to create a security system with facial recognition</p>
<p class="project-detail">-Connected a motion sensor and a camera that would activate on detection</p>
<p class="project-detail">-Use machine learning to develop robust facial recognition system</p>
</div>

<div class="fade-in">
<div class="project-title">Binghamton ITS, Software Engineer Intern at Binghamton, NY from June 2024 - August 2024
</div>
<p class="project-detail">-Developed and maintained a SQL database that mapped students' majors to their corresponding courses</p>
<p class="project-detail">-Implemented web pages on the Binghamton University website using integrated custom APIs written in C and C++ to fetch and display data from the SQL database</p>
<p class="project-detail">-Converted the Bash scripts into Python using Visual Studio to modernize and future-proof database refresh processes, increasing efficiency</p>
</div>

<div class="fade-in">
<div class="project-title">AMAG Nanometro, Software Engineer Consultant at Albany, NY from Dec 2022 - August 2024
</div>
<p class="project-detail">-Created Java GUI to add feature identification in SEM (scanning electron microscope) images</p>
<p class="project-detail">-Automated pattern generation by writing scripts that iterated through image data, utilized Blender's Python API to create custom panels, and optimized visualization through efficient looping techniques</p>
<p class="project-detail">-Integrated features into SimuSEM software package and used GitHub for collaboration and version control</p>
</div>

<div class="fade-in">
<div class="project-title">Griffiss Air Force Base, RI Intern at Rome, NY from June 2022 - August 2022
</div>
<p class="project-detail">-Programmed user interface in Unity for video game adaptation of Persian Incursion board game</p>
<p class="project-detail">-Created menus using Unity and C# for the game to save selections between scenes, including target weapon, plane, and unmanned aerial vehicle selections</p>
<p class="project-detail">-Transferred a board game algorithm to Unity by implementing a series of optimized switch statements to match planes with bombs and assign bombs to appropriate targets</p>
<p class="project-detail">-Version controlled using GitHub in order to easily access older versions and enable easier collaboration</p>
</div>

<div class="fade-in">
<div class="project-title">Door Motion Sensor, Research Project
</div>
<p class="project-detail">-Uses a raspberry Pi as a security system</p>
<p class="project-detail">-When the door opens the Pi will put the exact time on the AWS blockchain</p>
</div>

<style>
  .fade-in {
    transform: translateX(-600px);
    transition: transform 1s ease;
    margin-bottom: 50px;
  }
  
  .fade-in.visible {
    transform: translateY(0);
  }
    
    
      .project-title {
        font-weight: bold;
        font-size: 20px;
        margin-top: 75px;
        color: #2c3e50;
    }
    
    .project-detail {
        font-size: 18px;
        padding-left: 20px;
    }
    
  </style>

  <script>
  // Create an Intersection Observer
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
      }
      else{
        entry.target.classList.remove('visible');
      }
    });
  }, {
    threshold: 0.1, // Trigger when 10% of element is visible
    rootMargin: '0px' // Adjust this to trigger earlier/later
  });
  
  // Observe all elements with fade-in class
  document.addEventListener('DOMContentLoaded', () => {
    document.querySelectorAll('.fade-in').forEach(el => {
      observer.observe(el);
    });
  });
</script>
