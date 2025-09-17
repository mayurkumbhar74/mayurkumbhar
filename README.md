<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Landing Page</title>
  <style>
    /* Reset */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: Arial, sans-serif;
      line-height: 1.6;
    }

    /* Navigation Bar */
    nav {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      background: transparent;
      padding: 15px 20px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      transition: background 0.3s;
      z-index: 1000;
    }

    nav.scrolled {
      background: #333;
    }

    nav .logo {
      font-size: 20px;
      font-weight: bold;
      color: white;
    }

    nav ul {
      list-style: none;
      display: flex;
    }

    nav ul li {
      margin: 0 15px;
    }

    nav ul li a {
      color: white;
      text-decoration: none;
      font-weight: bold;
      transition: color 0.3s;
    }

    nav ul li a:hover {
      color: yellow;
    }

    /* Hero Section */
    .hero {
      height: 100vh;
      background: url('https://picsum.photos/1200/800') no-repeat center center/cover;
      display: flex;
      justify-content: center;
      align-items: center;
      color: white;
      text-align: center;
    }

    .hero h1 {
      font-size: 50px;
      background: rgba(0,0,0,0.5);
      padding: 20px;
      border-radius: 10px;
    }

    /* Content Sections */
    section {
      padding: 80px 20px;
      text-align: center;
    }

    /* Responsive */
    @media (max-width: 768px) {
      nav ul {
        display: none;
        flex-direction: column;
        background: #333;
        position: absolute;
        top: 60px;
        right: 20px;
        width: 200px;
        border-radius: 8px;
      }

      nav ul.active {
        display: flex;
      }

      .menu-toggle {
        display: block;
        font-size: 22px;
        color: white;
        cursor: pointer;
      }
    }

    @media (min-width: 769px) {
      .menu-toggle {
        display: none;
      }
    }
  </style>
</head>
<body>

  <nav id="navbar">
    <div class="logo">MyLogo</div>
    <span class="menu-toggle" onclick="toggleMenu()">☰</span>
    <ul id="menu">
      <li><a href="#home">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#services">Services</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <div class="hero" id="home">
    <h1>Welcome to My Landing Page</h1>
  </div>

  <section id="about">
    <h2>About Us</h2>
    <p>This is the about section of the landing page.</p>
  </section>

  <section id="services">
    <h2>Services</h2>
    <p>Here we describe our awesome services.</p>
  </section>

  <section id="contact">
    <h2>Contact Us</h2>
    <p>Get in touch with us through this section.</p>
  </section>

  <script>
    // Navbar scroll effect
    window.addEventListener("scroll", function() {
      let navbar = document.getElementById("navbar");
      if (window.scrollY > 50) {
        navbar.classList.add("scrolled");
      } else {
        navbar.classList.remove("scrolled");
      }
    });

    // Mobile menu toggle
    function toggleMenu() {
      let menu = document.getElementById("menu");
      menu.classList.toggle("active");
    }
  </script>
</body>
</html>
