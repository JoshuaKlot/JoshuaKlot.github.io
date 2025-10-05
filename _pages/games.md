---
title: "Joshua Klotzkin - Games"
layout: gridlay
excerpt: "Joshua Klotzkin: Games"
sitemap: false
permalink: /games/
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Games</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0 auto;
        }

        h1 {
            text-align: center;
            color: #333;
            margin-bottom: 10px;
        }

        .intro {
            text-align: center;
            color: #666;
            margin-bottom: 40px;
            font-size: 16px;
        }

        h2 {
            color: #444;
            border-bottom: 3px solid #333;
            padding-bottom: 10px;
            margin-bottom: 30px;
        }

        .games-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(500px, 2fr));
            gap: 30px;
            margin-bottom: 40px;
        }

        .game-card {
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .game-card:hover {
            transform: translateY(-5px);
            }

        .game-card iframe {
            width: 100%;
            margin-bottom: 15px;
        }

        .game-card p {
            font-size: 16px;
            line-height: 1.6;
            color: #555;
            margin: 0;
        }

        @media (max-width: 600px) {
            .games-grid {
                grid-template-columns: 1fr;
            }
            
            .game-card iframe {
                height: 150px;
            }
        }
    </style>
</head>
<body>
    <h1>My Game Portfolio</h1>
    <p class="intro">These are video games I have made in my free time and published on itch.io. They were made with a variety of Game Engines and coding languages.</p>
    
    <h2>Games</h2>
    
    <div class="games-grid">
        <div class="game-card">
            <iframe frameborder="0" src="https://itch.io/embed/2161439?bg_color=803b3b&amp;fg_color=ffffff&amp;link_color=030303&amp;border_color=000000" width="552" height="167">
                <a href="https://juklok.itch.io/the-lava-is-floor">The Lava is Floor by Juklok</a>
            </iframe>
            <p>The floor is lava was a game made for GMTK's 2023 game jam. The theme was role reversal so my idea was a platformer where lava was walkable and rocks were dangerous. I added in some game mechanics that could only be done if the player was walking on liquid so it would feel like a standard platformer.</p>
        </div>
        
        <div class="game-card">
            <iframe frameborder="0" src="https://itch.io/embed/2901981?bg_color=8382ff&amp;fg_color=ffffff&amp;link_color=98ff22&amp;border_color=91ff94" width="552" height="167">
                <a href="https://juklok.itch.io/magical-magnifier">Magical Magnifier by Juklok</a>
            </iframe>
            <p>Magical Magnifier was a game made for GMTK's 2024 game jam. The theme was Built to Scale so my idea was a platformer where you can grow and shrink blocks to platform and push them across water.</p>
        </div>
    </div>
</body>
</html>
