<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Joshua Klotzkin - Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #fff;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        h1 {
            font-size: 3.5em;
            margin: 80px 0 40px 0;
            text-align: center;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            letter-spacing: 2px;
        }

        .section {
            margin: 120px 0;
            opacity: 0;
            transform: translateX(-100px);
            transition: all 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
        }

        .section.from-right {
            transform: translateX(100px);
        }

        .section.visible {
            opacity: 1;
            transform: translateX(0);
        }

        .content-box {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
            border: 1px solid rgba(255, 255, 255, 0.18);
        }

        .intro-section {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items: center;
        }

        .intro-text {
            font-size: 1.3em;
            line-height: 1.8;
        }

        .profile-image {
            width: 100%;
            border-radius: 20px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.3);
            transition: transform 0.3s ease;
        }

        .profile-image:hover {
            transform: scale(1.05) rotate(2deg);
        }

        .text-content {
            font-size: 1.3em;
            line-height: 1.8;
        }

        .highlight {
            background: linear-gradient(120deg, #84fab0 0%, #8fd3f4 100%);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: bold;
        }

        @media (max-width: 768px) {
            .intro-section {
                grid-template-columns: 1fr;
            }

            h1 {
                font-size: 2.5em;
            }

            .text-content, .intro-text {
                font-size: 1.1em;
            }
        }

        .fade-in {
            animation: fadeIn 1s ease-in;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(-20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1 class="fade-in">Joshua Klotzkin</h1>

        <div class="section from-left" data-direction="left">
            <div class="content-box">
                <h1>My Portfolio</h1>
                <div class="intro-section">
                    <div class="intro-text">
                        I've been interested in video games for almost my entire life, basically since playing <span class="highlight">Putt Putt Saves the Zoo</span> on Windows XP. Especially after getting the Nintendo Wii and playing Super Mario Galaxy, I was really interested in making my own video games. I went to a lot of game design clubs that introduced me to Scratch and other logic based programming languages, before taking Unity classes and classes on other game engines in high school and college.
                    </div>
                    <img src="images/JoshImage.png" alt="A picture of me" class="profile-image">
                </div>
            </div>
        </div>

        <div class="section from-right" data-direction="right">
            <div class="content-box">
                <div class="text-content">
                    I went to <span class="highlight">Vestal High School</span> and started to improve my programming skills after going to SUNY Oneonta and taking some classes there. I left for <span class="highlight">SUNY Polytechnic</span> to pursue more game design opportunities. I was able to get a game design minor, join a game design club featuring like minded students, and even go to <span class="highlight">GDC</span> which was a very cool experience for someone my age. Right now I'm currently working towards a masters at <span class="highlight">Binghamton University</span> while looking for a more permanent job.
                </div>
            </div>
        </div>

        <div class="section from-left" data-direction="left">
            <div class="content-box">
                <h1>Games</h1>
                <div class="text-content">
                    In my free time I enjoy making my own video games using <span class="highlight">Unity, Godot, Unreal Engine, C#, C++, Java</span> and so on, and publishing them on itch.io to compete in game jams or grow my own skills. I'm always experimenting with new genres and technology, in order to best set myself up with anything I may need in the future. I was even able to work in a group with some of them which was really great. You can see a "best of" on my website here or click the link at the bottom to go straight to my itch page.
                </div>
            </div>
        </div>

        <div class="section from-right" data-direction="right">
            <div class="content-box">
                <h1>Projects</h1>
                <div class="text-content">
                    I've also worked on my fair share of non gaming, programming related projects that showcase my versatility as a developer and problem solver.
                </div>
            </div>
        </div>
    </div>

    <script>
        const observerOptions = {
            threshold: 0.2,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.section').forEach(section => {
            observer.observe(section);
        });
    </script>
</body>
</html>
