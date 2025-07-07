<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Adi Sontakke | Portfolio</title>
  <style>
    :root {
      --primary-color: #4b6cb7;
      --background-color: #f5f5f5;
      --dark-bg: #222;
      --text-color: #333;
      --light-text: #fff;
      --box-shadow: rgba(0, 0, 0, 0.08);
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      background-color: var(--background-color);
      color: var(--text-color);
      line-height: 1.6;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }

    header {
      background-color: var(--dark-bg);
      color: var(--light-text);
      padding: 20px 40px;
      box-shadow: 0 2px 5px var(--box-shadow);
      position: sticky;
      top: 0;
      z-index: 1000;

      /* Animation */
      animation: slideDownFadeIn 1s ease forwards;
    }

    header h1 {
      font-size: 28px;
      font-weight: 700;
      letter-spacing: 1.2px;
      margin-right: 40px;
      opacity: 0;
      transform: translateY(20px);
      animation: fadeSlideUp 1s ease forwards;
      animation-delay: 0.3s;
      color: var(--light-text);
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    nav ul {
      list-style: none;
      display: flex;
      gap: 25px;
    }

    nav ul li a {
      color: var(--light-text);
      text-decoration: none;
      font-weight: 600;
      font-size: 16px;
      padding: 8px 12px;
      border-radius: 4px;
      transition: background-color 0.3s ease, color 0.3s ease;
    }

    nav ul li a:hover,
    nav ul li a:focus {
      background-color: var(--primary-color);
      color: var(--light-text);
      outline: none;
    }

    /* Hero Section */
    .hero {
      background-image: url('https://images.unsplash.com/photo-1519389950473-47ba0277781c?auto=format&fit=crop&w=1600&q=80');
      background-size: cover;
      background-position: center;
      color: var(--light-text);
      text-align: center;
      padding: 140px 20px 120px;
      position: relative;
      animation: fadeSlideUp 1.5s ease-out forwards;
      opacity: 0;
      transform: translateY(20px);
      display: flex;
      flex-direction: column;
      justify-content: center;
      min-height: 60vh;
    }

    .hero::before {
      content: "";
      position: absolute;
      inset: 0;
      background-color: rgba(0, 0, 0, 0.55);
      z-index: 1;
    }

    .hero h2,
    .hero p {
      position: relative;
      z-index: 2;
      margin-bottom: 0.5rem;
    }

    .hero h2 {
      font-size: 3rem;
      font-weight: 700;
      letter-spacing: 2px;
      text-transform: capitalize;
    }

    .hero p {
      font-size: 1.25rem;
      font-weight: 500;
      letter-spacing: 1px;
    }

    @keyframes fadeSlideUp {
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    @keyframes slideDownFadeIn {
      from {
        opacity: 0;
        transform: translateY(-20px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
    
    /* Section Styling */
    .section {
      max-width: 900px;
      margin: 60px auto;
      padding: 0 20px;
    }

    .section h2 {
      font-size: 2.2rem;
      margin-bottom: 20px;
      color: var(--primary-color);
      border-left: 5px solid var(--primary-color);
      padding-left: 15px;
      font-weight: 700;
    }

    .section p {
      font-size: 1.1rem;
      color: #555;
      line-height: 1.7;
    }

    /* Skills Grid */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 25px;
      margin-top: 25px;
    }

    .skill-box {
      background-color: #fff;
      border-left: 5px solid var(--primary-color);
      padding: 25px 20px;
      border-radius: 10px;
      box-shadow: 0 4px 12px var(--box-shadow);
      transition: transform 0.3s ease, box-shadow 0.3s ease;
      cursor: default;
    }

    .skill-box:hover {
      transform: translateY(-6px);
      box-shadow: 0 10px 20px rgba(75, 108, 183, 0.3);
    }

    .skill-box h3 {
      color: var(--primary-color);
      margin-bottom: 12px;
      font-weight: 700;
      font-size: 1.4rem;
    }

    .skill-box p {
      font-size: 0.95rem;
      color: #444;
      line-height: 1.5;
    }

    /* Projects */
    .project {
      background: #fff;
      padding: 20px 25px;
      margin-bottom: 25px;
      border-left: 5px solid var(--primary-color);
      box-shadow: 0 4px 10px var(--box-shadow);
      border-radius: 8px;
      transition: box-shadow 0.3s ease;
    }

    .project:hover {
      box-shadow: 0 8px 20px rgba(75, 108, 183, 0.3);
    }

    .project h3 {
      color: var(--primary-color);
      margin-bottom: 12px;
      font-weight: 700;
      font-size: 1.3rem;
    }

    .project p {
      font-size: 1rem;
      color: #555;
      line-height: 1.5;
    }

    /* Contact Form */
    form {
      max-width: 600px;
      margin: 0 auto;
      display: flex;
      flex-direction: column;
      gap: 15px;
    }

    form input,
    form textarea {
      padding: 15px;
      border: 1.5px solid #ccc;
      border-radius: 7px;
      font-size: 1rem;
      resize: vertical;
      transition: border-color 0.3s ease;
    }

    form input:focus,
    form textarea:focus {
      border-color: var(--primary-color);
      outline: none;
      box-shadow: 0 0 8px rgba(75, 108, 183, 0.4);
    }

    form button {
      background-color: var(--primary-color);
      color: var(--light-text);
      border: none;
      padding: 15px;
      font-size: 1.1rem;
      border-radius: 7px;
      cursor: pointer;
      font-weight: 700;
      transition: background-color 0.3s ease;
    }

    form button:hover,
    form button:focus {
      background-color: #3a54a1;
      outline: none;
    }

    /* Footer */
    footer {
      background-color: var(--dark-bg);
      color: var(--light-text);
      text-align: center;
      padding: 25px 20px;
      margin-top: 60px;
      font-size: 0.95rem;
    }

    footer a {
      color: #79a6ff;
      text-decoration: none;
      font-weight: 600;
      transition: color 0.3s ease;
    }

    footer a:hover,
    footer a:focus {
      color: #a8c6ff;
      outline: none;
    }

    /* Responsive tweaks */
    @media (max-width: 600px) {
      header h1 {
        font-size: 20px;
      }
      nav ul {
        gap: 12px;
      }
      .hero h2 {
        font-size: 2.2rem;
      }
      .hero p {
        font-size: 1rem;
      }
      .section {
        margin: 40px 15px;
      }
      form {
        max-width: 100%;
      }
    }
    .hero h2, .hero p {
  opacity: 0;
  transform: translateY(30px);
  animation: fadeSlideUp 1s ease forwards;
}

.hero h2 {
  animation-delay: 0.3s;
}

.hero p {
  animation-delay: 0.7s;
}

@keyframes fadeSlideUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

  </style>
</head>
<body>

  <header role="banner">
    <div class="container">
      <h1 tabindex="0">Adi Sontakke</h1>
      <nav role="navigation" aria-label="Main navigation">
        <ul>
          <li><a href="#about" tabindex="0">About</a></li>
          <li><a href="#skills" tabindex="0">Skills</a></li>
          <li><a href="#projects" tabindex="0">Projects</a></li>
          <li><a href="#contact" tabindex="0">Contact</a></li>
          <li><a href="https://www.instagram.com/yourusername" target="_blank" rel="noopener" tabindex="0" aria-label="Instagram profile">Instagram</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <main>
    <section class="hero" aria-label="Introduction">
      <h2>Hi, I'm Adinath Sontakke</h2>
      <p>A passionate front-end developer creating engaging user experiences.</p>
    </section>

    <section class="section" id="about" tabindex="0" aria-labelledby="about-title">
      <h2 id="about-title">About Me</h2>
      <p>
        Hello! I'm Adinath Sontakke, a skilled front-end developer specializing in HTML, CSS, JavaScript, and React.js.
        I create modern and responsive websites with smooth animations and clean code.
      </p>
    </section>

    <section class="section" id="skills" tabindex="0" aria-labelledby="skills-title">
      <h2 id="skills-title">Skills</h2>
      <div class="skills-grid">
        <div class="skill-box" tabindex="0" aria-label="HTML skill">
          <h3>HTML</h3>
          <p>Proficient in semantic HTML5, accessible markup, and SEO best practices.</p>
        </div>
        <div class="skill-box" tabindex="0" aria-label="CSS skill">
          <h3>CSS</h3>
          <p>Experienced with Flexbox, Grid, animations, and responsive design techniques.</p>
        </div>
        <div class="skill-box" tabindex="0" aria-label="JavaScript skill">
          <h3>JavaScript</h3>
          <p>Skilled in vanilla JS, ES6+, DOM manipulation, and event handling.</p>
        </div>
      
      </div>
    </section>

    <section class="section" id="projects" tabindex="0" aria-labelledby="projects-title">
      <h2 id="projects-title">Projects</h2>
      <div class="project" tabindex="0">
        <h3>Portfolio Website</h3>
        <p>A personal portfolio built with React and styled-components showcasing my work.</p>
      </div>
     
      
    </section>

    <section class="section" id="contact" tabindex="0" aria-labelledby="contact-title">
      <h2 id="contact-title">Contact Me</h2>
      <form action="#" method="post" aria-label="Contact form">
        <input type="text" name="name" placeholder="Your Name" aria-label="Your Name" required />
        <input type="email" name="email" placeholder="Your Email" aria-label="Your Email" required />
        <textarea name="message" rows="6" placeholder="Your Message" aria-label="Your Message" required></textarea>
        <button type="submit">Send Message</button>
      </form>
    </section>
  </main>

  <footer role="contentinfo">
    <p>Follow me on <a href="https://www.instagram.com/yourusername" target="_blank" rel="noopener" aria-label="Instagram profile">Instagram</a></p>
    <p>&copy; 2025 Adi Sontakke</p>
  </footer>

</body>
</html>
