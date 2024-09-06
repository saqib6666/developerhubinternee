<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <link rel="stylesheet" href="style.css">
    <title>Personal Portfolio</title>
</head>
<body>
    <nav>
        <div class="nav-container">
            <div class="logo">
                <span>Personal</span> Portfolio
            </div>
            <div class="links">
                <div class="link"><a href="#home">Home</a></div>
                <div class="link"><a href="#about">About</a></div>
                <div class="link"><a href="#projects">Projects</a></div>
                <div class="link"><a href="#contact" onclick="showContactForm()">Contact</a></div>
            </div>
            <i class="fa-solid fa-bars hamburg" onclick="hamburg()"></i>
        </div>
        <div class="dropdown">
            <div class="links">
                <a href="#home">Home</a>
                <a href="#about">About</a>
                <a href="#projects">Projects</a>
                <a href="#contact" onclick="showContactForm()">Contact</a>
                <i class="fa-solid fa-xmark cancel" onclick="cancel()"></i>
            </div>
        </div>
    </nav>
    
    <section id="home">
        <div class="main-container">
            <div class="content">
                <h1>Hello, I'm <span>Your Name</span></h1>
                <div class="typewriter">
                    I'm a <span class="typewriter-text"></span><label for="">|</label>
                </div>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
                <div class="social-links">
                    <a href="#" target="_blank" title="GitHub"><i class="fa-brands fa-github"></i></a>
                    <a href="#" target="_blank" title="Facebook"><i class="fa-brands fa-facebook"></i></a>
                    <a href="#" target="_blank" title="LinkedIn"><i class="fa-brands fa-linkedin"></i></a>
                    <a href="#" target="_blank" title="Twitter"><i class="fa-brands fa-twitter"></i></a>
                </div>
                <div class="btn">
                    <button>Hire Me</button>
                </div>
            </div>
        </div>
    </section>

    <section id="about">
        <h2>About Me</h2>
        <p>Provide some details about yourself here. Highlight your skills, experience, and background.</p>
    </section>

    <section id="projects">
        <h2>Projects</h2>
        <div class="project">
            <h3>Project Title 1</h3>
            <p>Description of the project. Highlight the technology used and the impact of the project.</p>
        </div>
        <div class="project">
            <h3>Project Title 2</h3>
            <p>Description of the project. Highlight the technology used and the impact of the project.</p>
        </div>
    </section>

    <section id="contact" class="contact-section">
        <h2>Contact Me</h2>
        <button onclick="showContactForm()">Contact Form</button>
        <div id="contactFormContainer" class="form-container">
            <form id="contactForm" onsubmit="return validateForm()">
                <label for="name">Name:</label>
                <input type="text" id="name" name="name" placeholder="Your Name" required>
                
                <label for="email">Email:</label>
                <input type="email" id="email" name="email" placeholder="Your Email" required>
                
                <label for="message">Message:</label>
                <textarea id="message" name="message" rows="4" placeholder="Your Message" required></textarea>
                
                <button type="submit">Submit</button>
            </form>
            <div id="formResponse"></div>
        </div>
    </section>

    <script src="script.js"></script>
</body>
</html>
