---
title: "Joshua Klotzkin Home Page"
layout: textlay
excerpt: "Joshua Klotzkin's Website homepage"
sitemap: false
permalink: /
---


<body>
  <div class="fade-in">
<h1>My Portfolio</h1>
<p style="font-size:20px">
  <img src="images/JoshImage.png" alt="A picture of me" style="float:right;width:50%;height:50%;">
I have a Bacholer's degree in computer science and minor in Game Design from Suny Polytechic. I have taught myself a lot of skills in high school and those skills were only imporved upon when I went into college. I have lots of expirence in lots of different aspects of computer science and programming such as object oriented programming, embedded systems, artifical intelligence and machine learning thanks to my education.
</p>
  </div>
<div class="fade-in">
<p style="font-size:20px"> 
I started to improve my programming skills after going to SUNY Oneonta and taking some classes there, such as Data Structure, Algebra III, and Object Oriented Programming. I left for SUNY Polytechnic to pursue more game design opportunities. I was able to get a game design minor, join a game design club featuring like minded students, and even go to GDC which was a very cool experience for someone my age. Right now I'm currently working towards a masters at Binghamton University while looking for a more permanent job.
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
