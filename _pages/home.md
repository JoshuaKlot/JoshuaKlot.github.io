---
title: "Joshua Klotzkin Home Page"
layout: textlay
excerpt: "Joshua Klotzkin's Website homepage"
sitemap: false
permalink: /
---

<body>
  <div class="fade-in">
<h1 style="text-align:center;margin-bottom:60px">This Weeks Featured Game</h1>
<p style="font-size:20px">
  <img src="images/titleScreen.png" alt="titleScreen" style="display:block;margin:0 auto;width:50%;height:50%;">
Robo Beat em Up was a game I created for Big mode's 2023 game jam, and even today I would still say its one of my more impressive projects to date. The theme of the game was Mode so my idea was a tower defense game with a single tower that could switch through multiple modes of defense
</p>
  </div>
<div style="background-color:light-blue;margin-top:60px">
<div class="fade-in">
<p style="font-size:20px"> 
<img src="images/worldbuilding.png" alt="worldbuilding" style="float:left;width:20%;height:20%;margin-right:10px;"><img src="images/action.png" alt="action" style="float:right;width:20%;height:20%;margin-left:10px;">
This game was greatly inspired by Plants vs Zombies, with again the idea being the player has access to a single plant the can change its weapons at will. I was really inspired by that games humor with its enemy descriptions and attempted to do that with my own how to screen. The game also has a Vampire Survivor-esque progession system  where defeating enemies allows you to level up one of your equipped weapons.
  

</p>
<div style="text-align:center;margin-top:120px">
  <h1 style="text-align:center;margin-bottom:60px">Play It Now!!!</h1>
  <div class="center">
<iframe frameborder="0" src="https://itch.io/embed/2466230?bg_color=949494&amp;fg_color=640000&amp;link_color=c90000&amp;border_color=000000" width="750" height="167"><a href="https://juklok.itch.io/robo-beatemup-20">Play It Now!!</a></iframe>
  </div>
</div>
</div>
</div>
</body> 
<style>
  .fade-in {
    transform: translateX(200px);
    transition: opacity 1s ease, transform 1s ease;
  }
  .center {
  display: flex;
  justify-content: center;
  align-items: center;
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
