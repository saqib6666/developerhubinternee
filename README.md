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





body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

nav {
    background-color: #333;
    color: #fff;
    position: fixed;
    width: 100%;
    top: 0;
    left: 0;
    z-index: 1000;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
}

.nav-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 15px 30px;
}

.logo {
    font-size: 28px;
    font-weight: bold;
}

.logo span {
    color: #ff0;
}

.links {
    display: flex;
}

.link {
    margin: 0 20px;
}

.link a {
    color: #fff;
    text-decoration: none;
    font-size: 16px;
    transition: color 0.3s;
}

.link a:hover,
.link a.active {
    color: #ff0;
}

.hamburg {
    display: none;
    font-size: 24px;
    cursor: pointer;
}

.dropdown {
    display: none;
    position: fixed;
    top: 0;
    right: 0;
    width: 250px;
    background-color: #333;
    color: #fff;
    height: 100%;
    transform: translateY(-100%);
    transition: transform 0.3s ease-in-out;
    padding: 20px;
}

.dropdown .links {
    display: flex;
    flex-direction: column;
}

.dropdown .links a {
    color: #fff;
    text-decoration: none;
    margin: 10px 0;
    font-size: 18px;
    transition: color 0.3s;
}

.dropdown .links a:hover {
    color: #ff0;
}

.cancel {
    font-size: 24px;
    cursor: pointer;
    margin-top: 20px;
}

section {
    padding: 80px 20px;
    text-align: center;
}

section h2 {
    margin-bottom: 30px;
    font-size: 36px;
    font-weight: bold;
    color: #333;
}

.project {
    margin-bottom: 30px;
}

form {
    display: flex;
    flex-direction: column;
    max-width: 600px;
    margin: 0 auto;
    background-color: #f9f9f9;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

form label {
    margin: 10px 0 5px;
    font-weight: bold;
}

form input,
form textarea {
    padding: 12px;
    margin-bottom: 10px;
    border: 1px solid #ddd;
    border-radius: 4px;
    font-size: 16px;
    width: 100%;
}

form button {
    padding: 12px;
    background-color: #333;
    color: #fff;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 16px;
    transition: background-color 0.3s;
}

form button:hover {
    background-color: #555;
}

#formResponse {
    margin-top: 20px;
    text-align: center;
    font-weight: bold;
    color: #333;
}

/* Responsive Design */
@media (max-width: 768px) {
    .hamburg {
        display: block;
    }

    .links {
        display: none;
    }

    .dropdown {
        display: block;
    }

    .dropdown.show {
        transform: translateY(0);
    }
    /* Add to your existing style.css */

/* Hide the contact form initially */
.form-container {
    display: none;
}

/* Show the contact form when it's toggled */
.form-container.show {
    display: block;
}

}



// Typewriter Effect
const typewriterText = document.querySelector(".typewriter-text");
const words = ["a Web Developer", "a Programmer", "a Designer"];
let wordIndex = 0;
let letterIndex = 0;
let currentWord = "";
let isDeleting = false;

function type() {
    currentWord = words[wordIndex];
    if (isDeleting) {
        typewriterText.textContent = currentWord.substring(0, letterIndex--);
    } else {
        typewriterText.textContent = currentWord.substring(0, letterIndex++);
    }

    if (!isDeleting && letterIndex === currentWord.length) {
        isDeleting = true;
        setTimeout(type, 2000);
    } else if (isDeleting && letterIndex === 0) {
        isDeleting = false;
        wordIndex = (wordIndex + 1) % words.length;
        setTimeout(type, 500);
    } else {
        setTimeout(type, isDeleting ? 100 : 200);
    }
}

document.addEventListener("DOMContentLoaded", () => type());

// Navigation Toggle Functions
function hamburg() {
    document.querySelector(".dropdown").classList.add('show');
}

function cancel() {
    document.querySelector(".dropdown").classList.remove('show');
}

// Contact Form Validation
function validateForm() {
    const name = document.getElementById('name').value.trim();
    const email = document.getElementById('email').value.trim();
    const message = document.getElementById('message').value.trim();

    if (name === "" || email === "" || message === "") {
        alert("All fields are required!");
        return false;
    }

    if (!validateEmail(email)) {
        alert("Please enter a valid email address!");
        return false;
    }

    document.getElementById('formResponse').innerText = "Message sent successfully!";
    return true;
}

function validateEmail(email) {
    const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    return re.test(email);
}

// Smooth Scrolling
document.querySelectorAll('nav .links a').forEach(anchor => {
    anchor.addEventListener('click', function(e) {
        e.preventDefault();
        document.querySelector(this.getAttribute('href')).scrollIntoView({
            behavior: 'smooth'
        });
        document.querySelectorAll('nav .links a').forEach(link => link.classList.remove('active'));
        this.classList.add('active');
    });
    
});


