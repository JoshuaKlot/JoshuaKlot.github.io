---
title: "Joshua Klotzkin Home Page"
layout: textlay
excerpt: "Allan Lab at Leiden University &rarr; LMU."
sitemap: false
permalink: /
---


<body>
  <div class="fade-in">
<h1>My Portfolio</h1>
<p style="font-size:20px">
  <img src="images/JoshImage.png" alt="A picture of me" style="float:right;width:50%;height:50%;">
I've been interested in video games for almost my entire life, basically since playing Putt Putt Saves the Zoo on Windows XP. Especially after getting the Nintendo Wii and playing Super Mario Galaxy, I was really interested in making my own video games. I went to a lot of game design clubs that introduced me to Scratch and other logic based programing languages, before taking Unity classes and classes on other game engines in high school and college.
</p>
  </div>
<div class="fade-in">
<p style="font-size:20px"> 
I went to Vestal High School and started to improve my programming skills after going to SUNY Oneonta and taking some classes there. I left for SUNY Polytechnic to pursue more game design opportunities. I was able to get a game design minor, join a game design club featuring like minded students, and even go to GDC which was a very cool experience for someone my age. Right now I'm currently working towards a masters at Binghamton University while looking for a more permanent job.
</p>
</div>
<div style="background-color:powderblue; padding: 200px;" class="fade-in">

    <h2>Games</h2>
    <p style="font-size:20px"> 
      In my free time i enjoy making my own video games using Unity, Godot, Unreal Engine, C#, C++ , Java and so on, and publishing them on itch.io to compete in game jams or grow my own skills. Im always experimenting with new genres and technology, in order to best set myself up with anything I may need in the future. I was even able to working in a group with some of them which was really great. You can see a "best of" on my website here or click the link at the bottom to go straight to my itch page.
    </p>
</div>

<div class="fade-in">
<h2>Projects</h2>
<p>I've also worked on my fair share of non gaming, programming related projects</p> 

</div>
</body>
<style>
  .fade-in {
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 1s ease, transform 1s ease;
  }
  
  .fade-in.visible {
    opacity: 1;
    transform: translateY(0);
  }
    
    p {
      margin-bottom: 20px;
    }
    
    h2 {
      margin-top: 200px;
      margin-bottom: 10px;
    }
    
    h1:first-of-type {
      margin-top: 0;
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
