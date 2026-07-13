<img width="1917" height="1066" alt="image" src="https://github.com/user-attachments/assets/26d63ad4-c4d5-4c3d-9566-16444ebe8fb3" />---
title: "Joshua Klotzkin Home Page"
layout: textlay
excerpt: "Joshua Klotzkin's Website homepage"
sitemap: false
permalink: /
---


<body>
  <div class="fade-in">
<h1>Featured Game</h1>
<p style="font-size:20px">
  <img src="images/titleScreen.png" alt="titleScreen" style="float:right;width:50%;height:50%;">
Robo Beat em Up was a game I created for Big mode's 2023 game jam, and even today I would still say its one of my more impressive projects to date. The theme of the game was Mode so my idea was a tower defense game with a single tower that could switch through multiple modes of defense
</p>
  </div>
<div style="background-color:light-blue">
<div class="fade-in">

<h2>Games</h2>
<p style="font-size:20px"> 

In my free time i enjoy making my own video games using Unity, Godot, Unreal Engine, C#, C++ , Java, Python and so on, and publishing them on itch.io to compete in game jams or grow my own skills. I'm always experimenting with new genres and technology, in order to best set myself up with anything I may need in the future. I was even able to work in a group with some of them which was really great. You can see a "best of" on my website <a href="https://joshuaklot.github.io/games/">here</a> or click the link at the bottom to go straight to my itch.io page.
</p>
</div>
</div>

<div class="fade-in">
<h2>Projects</h2>
<p style="font-size:20px">I've also worked on my fair share of non gaming, programming related projects, such as making these websites for other people (and myself), using machine learning to detect faces on a raspberry pi, and making an edge detection GUI. Those projects can also be viewed <a href="https://joshuaklot.github.io/projects">here.</a></p> 
</div>
</body>
<style>
  .fade-in {
    transform: translateX(200px);
    transition: opacity 1s ease, transform 1s ease;
  }
  
  .fade-in.visible {
    transform: translateY(0);
  }
    
    p {
      margin-bottom: 20px;
    }
    
    h2 {
      margin-top: 50px;
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
