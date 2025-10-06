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


        .games-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(500px, 1fr));
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
            <iframe frameborder="0" src="https://itch.io/embed/1999028?bg_color=000000&amp;fg_color=ffffff&amp;link_color=75fa5b" width="552" height="167"><a href="https://juklok.itch.io/dance-of-the-planets">Dance Of The Planets by Juklok</a></iframe>
            <p>Dance of the Planets was made for Suny Polytechnics game jam in 2023. The theme was Parallel Worlds so my idea was a pseudo-rhythm game where the goal is to press the arrow keys to keep in time with the other planets to keep them parallel.</p>
            <p> Programs used: Unity, C#, beepbox, Aseprite</p>
        </div>
        <div class="game-card">
            <iframe frameborder="0" src="https://itch.io/embed/2161439?border_width=5&amp;bg_color=904b00&amp;fg_color=e10029&amp;link_color=9a0000" width="216" height="175"><a href="https://juklok.itch.io/the-lava-is-floor">The Lava is Floor by Juklok</a></iframe>                <a href="https://juklok.itch.io/the-lava-is-floor">The Lava is Floor by Juklok</a>
            <p>The floor is lava was a game made for GMTK's 2023 game jam. The theme was role reversal so my idea was a platformer where lava was walkable and rocks were dangerous. I added in some game mechanics that could only be done if the player was walking on liquid so it wouldn't feel like just a standard platformer.</p>
            <p> Programs used: Unity, C#, beepbox, Aseprite</p>
        </div>
        <div class="game-card">
            <iframe frameborder="0" src="https://itch.io/embed/2419235?bg_color=7e7e7e&amp;fg_color=feffff&amp;link_color=3c3838&amp;border_color=000000" width="552" height="167"><a href="https://juklok.itch.io/robo-beat-em-up">Robo Beat em Up by Juklok</a></iframe>
            <p>The floor is lava was a game made for Big Mode's 2023 game jam. The theme was mode so my idea was a tower defense game with a single tower with multiple modes that could be upgraded as it killed enemies. I had 2 weeks to make this so it is by far my most indepth game.</p> 
            <p> Programs used: Unity, C#, beepbox, Aseprite</p>
        </div>
        
        <div class="game-card">
            <iframe frameborder="0" src="https://itch.io/embed/2901981?border_width=5&amp;bg_color=44ff24&amp;link_color=00b1c3" width="216" height="175"><a href="https://juklok.itch.io/magical-magnifier">Magical Magnifier by Juklok</a></iframe>The Lava is Floor by Juklok</     <a href="https://juklok.itch.io/magical-magnifier">Magical Magnifier by Juklok</a>
            <p>Magical Magnifier was a game made for GMTK's 2024 game jam. The theme was Built to Scale so my idea was a platformer where you can grow and shrink blocks to platform and push them across water. The game has a bit of a physics system as the smaller the box is the further it will be pushed.</p>
            <p> Programs used: Unity, C#, beepbox, Aseprite</p>
        </div>

    </div>
</body>
</html>
