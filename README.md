<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hacker 97 | Portfolio</title>
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #00d2ff;
            --accent-color: #0072ff;
            --bg-overlay: rgba(10, 15, 29, 0.88);
            --card-bg: rgba(255, 255, 255, 0.07);
            --text-color: #ffffff;
            --text-secondary: #cccccc;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
            scroll-behavior: smooth;
        }

        body {
            color: var(--text-color);
            background: url('background.jpg') no-repeat center center fixed;
            background-size: cover;
            position: relative;
            min-height: 100vh;
        }

        /* Dark overlay over background image */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--bg-overlay);
            z-index: -1;
        }

        /* Navigation Header */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 8%;
            background: rgba(10, 15, 29, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            border-bottom: 1px solid rgba(0, 210, 255, 0.2);
        }

        .logo {
            font-size: 24px;
            font-weight: 700;
            color: var(--primary-color);
            letter-spacing: 1px;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 25px;
        }

        .nav-links a {
            color: var(--text-color);
            text-decoration: none;
            font-weight: 500;
            transition: 0.3s;
        }

        .nav-links a:hover {
            color: var(--primary-color);
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 120px 8% 60px;
            gap: 40px;
        }

        .hero-content {
            max-width: 600px;
        }

        .hero-content h3 {
            font-size: 24px;
            color: var(--primary-color);
        }

        .hero-content h1 {
            font-size: 48px;
            margin: 10px 0;
            line-height: 1.2;
        }

        .typing-text {
            font-size: 22px;
            font-weight: 600;
            color: #00d2ff;
            margin-bottom: 15px;
            min-height: 32px;
        }

        .hero-content p {
            color: var(--text-secondary);
            margin-bottom: 25px;
            line-height: 1.6;
        }

        .btn-container {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
            margin-bottom: 25px;
        }

        .btn {
            padding: 12px 28px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: 0.3s;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .btn-primary {
            background: linear-gradient(45deg, var(--primary-color), var(--accent-color));
            color: #fff;
            box-shadow: 0 4px 15px rgba(0, 210, 255, 0.3);
        }

        .btn-whatsapp {
            background: #25D366;
            color: #fff;
            box-shadow: 0 4px 15px rgba(37, 211, 102, 0.3);
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(0, 210, 255, 0.5);
        }

        .profile-img-container {
            position: relative;
            width: 320px;
            height: 320px;
            border-radius: 50%;
            padding: 8px;
            background: linear-gradient(45deg, var(--primary-color), transparent);
        }

        .profile-img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 50%;
            border: 4px solid #0a0f1d;
        }

        /* Social Icons */
        .social-icons {
            display: flex;
            gap: 15px;
        }

        .social-icons a {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.1);
            color: var(--text-color);
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            transition: 0.3s;
            border: 1px solid rgba(0, 210, 255, 0.3);
        }

        .social-icons a:hover {
            background: var(--primary-color);
            color: #000;
            transform: translateY(-3px);
        }

        /* Sections General */
        section {
            padding: 80px 8%;
        }

        .section-title {
            text-align: center;
            font-size: 32px;
            margin-bottom: 50px;
            color: var(--primary-color);
            position: relative;
        }

        /* Skills Section */
        .skills-container {
            max-width: 800px;
            margin: 0 auto;
            background: var(--card-bg);
            padding: 30px;
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .skill-box {
            margin-bottom: 20px;
        }

        .skill-info {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
            font-weight: 500;
        }

        .progress-bar {
            width: 100%;
            height: 10px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            overflow: hidden;
        }

        .progress {
            height: 100%;
            background: linear-gradient(90deg, var(--primary-color), var(--accent-color));
            border-radius: 10px;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
        }

        .project-card {
            background: var(--card-bg);
            border-radius: 15px;
            padding: 25px;
            border: 1px solid rgba(0, 210, 255, 0.2);
            transition: 0.3s;
        }

        .project-card:hover {
            transform: translateY(-5px);
            border-color: var(--primary-color);
        }

        .project-card h3 {
            color: var(--primary-color);
            margin-bottom: 10px;
        }

        /* Contact Section */
        .contact-details {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 30px;
            max-width: 900px;
            margin: 0 auto;
        }

        .contact-item {
            background: var(--card-bg);
            padding: 20px 30px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            gap: 15px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            min-width: 250px;
        }

        .contact-item i {
            font-size: 24px;
            color: var(--primary-color);
        }

        footer {
            text-align: center;
            padding: 20px;
            background: #050811;
            color: var(--text-secondary);
            font-size: 14px;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .hero {
                flex-direction: column-reverse;
                text-align: center;
                padding-top: 140px;
            }

            .btn-container, .social-icons {
                justify-content: center;
            }

            .profile-img-container {
                width: 240px;
                height: 240px;
            }

            .nav-links {
                display: none; /* Hide for simplicity on mobile */
            }
        }
    </style>
</head>
<body>

    <!-- Header Navigation -->
    <header>
        <div class="logo">HACKER 97</div>
        <ul class="nav-links">
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#skills">Skills</a></li>
            <li><a href="#projects">Projects</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </header>

    <!-- Hero / Animated Homepage -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h3>Hello, I'm</h3>
            <h1>Shahwaiz Bhai</h1>
            <div class="typing-text"><span id="type-writer"></span></div>
            <p>Based in Badin, Pakistan. Passionate about Web Development, Cyber Security, Design, and Video Editing.</p>
            
            <div class="btn-container">
                <a href="#contact" class="btn btn-primary"><i class="fas fa-envelope"></i> Contact Me</a>
                <a href="https://wa.me/923153064231" target="_blank" class="btn btn-whatsapp"><i class="fab fa-whatsapp"></i> WhatsApp</a>
                <a href="#" class="btn btn-primary" style="background: transparent; border: 2px solid var(--primary-color);" onclick="alert('CV Download Link Ready!')"><i class="fas fa-download"></i> Download CV</a>
            </div>

            <!-- Social Media Buttons -->
            <div class="social-icons">
                <a href="https://facebook.com" target="_blank" title="Facebook"><i class="fab fa-facebook-f"></i></a>
                <a href="https://instagram.com/Muskanjaan8866" target="_blank" title="Instagram"><i class="fab fa-instagram"></i></a>
                <a href="https://github.com" target="_blank" title="GitHub"><i class="fab fa-github"></i></a>
                <a href="mailto:shahwaizmagsi5@gmail.com" title="Email"><i class="fas fa-envelope"></i></a>
            </div>
        </div>

        <div class="profile-img-container">
            <img src="profile.jpg" alt="Shahwaiz Bhai - Hacker 97" class="profile-img">
        </div>
    </section>

    <!-- About Me Section -->
    <section id="about">
        <h2 class="section-title">About Me</h2>
        <div style="max-width: 800px; margin: 0 auto; text-align: center; background: var(--card-bg); padding: 30px; border-radius: 15px; border: 1px solid rgba(255, 255, 255, 0.1);">
            <p style="font-size: 18px; line-height: 1.8; color: var(--text-secondary);">
                I am a passionate <strong style="color: var(--primary-color);">Web Developer</strong> and tech enthusiast from Badin, Pakistan. With strong experience in frontend development, graphic design, video editing, and cyber security exploration, I build modern web applications and secure digital environments.
            </p>
        </div>
    </section>

    <!-- Skills Section with Progress Bars -->
    <section id="skills">
        <h2 class="section-title">My Skills</h2>
        <div class="skills-container">
            
            <div class="skill-box">
                <div class="skill-info">
                    <span>HTML / CSS / JavaScript</span>
                    <span>85%</span>
                </div>
                <div class="progress-bar"><div class="progress" style="width: 85%;"></div></div>
            </div>

            <div class="skill-box">
                <div class="skill-info">
                    <span>Graphic Designing</span>
                    <span>80%</span>
                </div>
                <div class="progress-bar"><div class="progress" style="width: 80%;"></div></div>
            </div>

            <div class="skill-box">
                <div class="skill-info">
                    <span>Video Editing</span>
                    <span>75%</span>
                </div>
                <div class="progress-bar"><div class="progress" style="width: 75%;"></div></div>
            </div>

            <div class="skill-box">
                <div class="skill-info">
                    <span>MS Word & Online Work</span>
                    <span>90%</span>
                </div>
                <div class="progress-bar"><div class="progress" style="width: 90%;"></div></div>
            </div>

            <div class="skill-box">
                <div class="skill-info">
                    <span>Ethical Hacking & Cyber Security</span>
                    <span>70%</span>
                </div>
                <div class="progress-bar"><div class="progress" style="width: 70%;"></div></div>
            </div>

        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects">
        <h2 class="section-title">Featured Project</h2>
        <div class="projects-grid">
            <div class="project-card">
                <i class="fas fa-user-secret" style="font-size: 40px; color: var(--primary-color); margin-bottom: 15px;"></i>
                <h3>Hacker 97</h3>
                <p style="color: var(--text-secondary); margin-bottom: 15px;">An interactive web platform focused on coding, design, editing showcase, and security concepts.</p>
                <span style="font-size: 12px; background: rgba(0, 210, 255, 0.2); padding: 5px 10px; border-radius: 5px; color: var(--primary-color);">Web / Cyber Security</span>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <h2 class="section-title">Contact Me</h2>
        <div class="contact-details">
            <div class="contact-item">
                <i class="fas fa-phone"></i>
                <div>
                    <h4>Phone / WhatsApp</h4>
                    <p style="color: var(--text-secondary);">03153064231</p>
                </div>
            </div>
            <div class="contact-item">
                <i class="fas fa-envelope"></i>
                <div>
                    <h4>Email</h4>
                    <p style="color: var(--text-secondary);">shahwaizmagsi5@gmail.com</p>
                </div>
            </div>
            <div class="contact-item">
                <i class="fas fa-map-marker-alt"></i>
                <div>
                    <h4>Location</h4>
                    <p style="color: var(--text-secondary);">Badin, Pakistan</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2026 Hacker 97 (Shahwaiz Bhai). All Rights Reserved.</p>
    </footer>

    <!-- Typing Effect Script -->
    <script>
        const words = ["Web Developer", "Graphic Designer", "Video Editor", "Ethical Hacker", "MS Word Expert"];
        let i = 0;
        let timer;

        function typingEffect() {
            let word = words[i].split("");
            var loopTyping = function() {
                if (word.length > 0) {
                    document.getElementById('type-writer').innerHTML += word.shift();
                } else {
                    setTimeout(deletingEffect, 2000);
                    return false;
                }
                timer = setTimeout(loopTyping, 100);
            };
            loopTyping();
        }

        function deletingEffect() {
            let word = words[i].split("");
            var loopDeleting = function() {
                if (word.length > 0) {
                    word.pop();
                    document.getElementById('type-writer').innerHTML = word.join("");
                } else {
                    if (words.length > (i + 1)) {
                        i++;
                    } else {
                        i = 0;
                    }
                    setTimeout(typingEffect, 500);
                    return false;
                }
                timer = setTimeout(loopDeleting, 50);
            };
            loopDeleting();
        }

        typingEffect();
    </script>
</body>
</html>
