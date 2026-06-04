<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="CodeWithKanishka is a premium animated student developer portfolio for frontend development, UI design, and creative coding.">
  <meta name="theme-color" content="#050505">
  <title>CodeWithKanishka |  Kanishka Portfolio</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=Space+Grotesk:wght@500;600;700&display=swap" 
  rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/aos/2.3.4/aos.css">
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="loader" id="loader" aria-label="Loading portfolio">
    <div class="loader-mark">KANISHKA</div>
    <div class="loader-line"><span></span></div>
  </div>

  <div class="cursor-dot" aria-hidden="true"></div>
  <div class="cursor-ring" aria-hidden="true"></div>
  <div class="mouse-glow" aria-hidden="true"></div>
  <canvas id="trail-canvas" aria-hidden="true"></canvas>

  <header class="site-header" id="site-header">
    <nav class="navbar" aria-label="Primary navigation">
      <a class="logo magnetic" href="#home" aria-label="CodeWithKanishka home">CodeWith<span>Kanishka</span></a>
      <button class="nav-toggle magnetic" type="button" aria-label="Toggle menu" aria-expanded="false">
        <span></span><span></span><span></span>
      </button>
      <ul class="nav-links">
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#services">Services</a></li>
        <li><a href="#testimonials">Learning</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>

  <main>
    <section class="hero section-panel" id="home">
      <canvas id="particle-canvas" aria-hidden="true"></canvas>
      <div class="animated-grid" aria-hidden="true"></div>
      <div class="neon-shape shape-one" aria-hidden="true"></div>
      <div class="neon-shape shape-two" aria-hidden="true"></div>
      <div class="neon-shape shape-three" aria-hidden="true"></div>

      <div class="hero-content" data-aos="fade-up">
        <p class="eyebrow split-text">Creative Developer Portfolio</p>
        <h1 class="split-text">Hi, I'm <span>Kanishka</span></h1>
        <h2><span id="typed-text"></span><span class="caret">|</span></h2>
        <p class="hero-copy">
          BCA second-year student learning frontend development, UI design, and creative coding through animated websites and practical mini projects.
        </p>
        <div class="hero-actions">
          <a class="btn primary magnetic" href="#projects">View Projects</a>
          <a class="btn ghost magnetic" href="#contact">Contact Me</a>
        </div>
      </div>

      <div class="profile-stage" data-aos="zoom-in" data-aos-delay="150">
        <div class="profile-card tilt-card">
          <div class="profile-halo" aria-hidden="true"></div>
          <div class="profile-image" role="img" aria-label="Animated neon profile portrait">
            <div class="avatar-face"></div>
            <div class="avatar-code code-a">&lt;/&gt;</div>
            
          </div>
          <div class="profile-chip">Frontend Developer</div>
        </div>
      </div>
    </section>

    <section class="section about" id="about">
      <div class="section-heading" data-aos="fade-up">
        <p class="eyebrow">About</p>
        <h2>A beginner developer building skills through creative practice.</h2>
      </div>
      <div class="about-layout">
        <article class="glass-card about-card" data-aos="fade-right">
          <h3>CodeWithKanishka</h3>
          <p>
            I am Kanishka, 
            a BCA second-year student exploring frontend development,
             UI design, and creative coding by building responsive 
             and animated practice projects.
          </p>
          <div class="counter-grid">
            <div><strong class="counter" data-target="8" data-suffix="+">0</strong><span>Practice Projects</span></div>
            <div><strong class="counter" data-target="2" data-suffix="nd">0</strong><span>BCA Year</span></div>
            <div><strong class="counter" data-target="7" data-suffix="+">0</strong><span>Skills Learning</span></div>
          </div>
        </article>
        <div class="timeline glass-card" data-aos="fade-left">
          <div class="timeline-item">
            <span>2024</span>
            <h3>Started Web Development</h3>
            <p>Learned HTML, CSS, basic JavaScript, and responsive page structure.</p>
          </div>
          <div class="timeline-item">
            <span>2025</span>
            <h3>BCA Learning Projects</h3>
            <p>Created animated websites, landing pages, and small frontend experiments.</p>
          </div>
          <div class="timeline-item">
            <span>2026</span>
            <h3>Second-Year Growth</h3>
            <p>Practicing JavaScript, React basics, GitHub, and better UI design habits.</p>
          </div>
        </div>
      </div>
    </section>

    <section class="section skills" id="skills">
      <div class="section-heading" data-aos="fade-up">
        <p class="eyebrow">Skills</p>
        <h2>Modern tools, animated with precision.</h2>
      </div>
      <div class="floating-icons" aria-hidden="true">
        <span>HTML</span><span>CSS</span><span>JS</span><span>React</span><span>Node</span><span>Git</span>
      </div>
      <div class="skills-grid">
        <article class="skill-card glass-card tilt-card" data-skill="94" data-aos="fade-up"><div class="skill-icon">H</div><h3>HTML</h3><p>Semantic, SEO-friendly structure.</p><div class="progress"><span></span></div></article>
        <article class="skill-card glass-card tilt-card" data-skill="92" data-aos="fade-up" data-aos-delay="60"><div class="skill-icon">C</div><h3>CSS</h3><p>Responsive glass and neon systems.</p><div class="progress"><span></span></div></article>
        <article class="skill-card glass-card tilt-card" data-skill="88" data-aos="fade-up" data-aos-delay="120"><div class="skill-icon">J</div><h3>JavaScript</h3><p>Interactive UI and browser logic.</p><div class="progress"><span></span></div></article>
        <article class="skill-card glass-card tilt-card" data-skill="84" data-aos="fade-up" data-aos-delay="120"><div class="skill-icon">G</div><h3>Git & GitHub</h3><p>Version control and collaboration.</p><div class="progress"><span></span></div></article>
      </div>
    </section>

    <section class="section projects" id="projects">
      <div class="section-heading" data-aos="fade-up">
        <p class="eyebrow">Projects</p>
        <h2>Practice projects with animation, layout, and responsive design.</h2>
      </div>
      <div class="filter-bar" data-aos="fade-up">
        <button class="filter-btn active magnetic" data-filter="all">All</button>
        <button class="filter-btn magnetic" data-filter="web">Web Design</button>
        <button class="filter-btn magnetic" data-filter="frontend">Frontend</button>
        <button class="filter-btn magnetic" data-filter="fullstack">Full Stack</button>
      </div>
      <div class="project-grid">
        <article class="project-card glass-card tilt-card" data-category="frontend" data-title="Animated Website" data-description="A beginner-friendly animated website with a dark neon theme, smooth scrolling, glowing buttons, and responsive sections." data-aos="fade-up">
          <div class="project-preview preview-one"><span>Animation UI</span></div><h3>Animated Website</h3><p>A creative animated webpage made to practice motion, layout, and hover effects.</p><div class="project-actions"><button class="open-project">Preview</button><a href="#">Live Demo</a><a href="#">GitHub</a></div>
        </article>
        <article class="project-card glass-card tilt-card" data-category="web" data-title="Paws Website" data-description="A cute pet website concept for pet adoption and care, designed with friendly cards, pet sections, and mobile responsive layout." data-aos="fade-up" data-aos-delay="80">
          <div class="project-preview preview-two"><span>Paws Pets</span></div><h3>Paws Website</h3><p>A pet-themed website concept for animals, adoption, and pet care information.</p><div class="project-actions"><button class="open-project">Preview</button><a href="#">Live Demo</a><a href="#">GitHub</a></div>
        </article>
        <article class="project-card glass-card tilt-card" data-category="frontend" data-title="Student Portfolio" data-description="A personal student portfolio project with about, skills, projects, and contact sections made using HTML, CSS, and JavaScript." data-aos="fade-up" data-aos-delay="160">
          <div class="project-preview preview-three"><span>Student Site</span></div><h3>Student Portfolio</h3><p>A personal portfolio built while learning frontend development in BCA.</p><div class="project-actions"><button class="open-project">Preview</button><a href="#">Live Demo</a><a href="#">GitHub</a></div>
        </article>
        <article class="project-card glass-card tilt-card" data-category="fullstack" data-title="College Notes UI" data-description="A simple college notes interface idea with subject cards, search-style layout, and clean beginner-friendly UI sections." data-aos="fade-up">
          <div class="project-preview preview-four"><span>Notes UI</span></div><h3>College Notes UI</h3><p>A study-focused interface concept for organizing BCA notes and subjects.</p><div class="project-actions"><button class="open-project">Preview</button><a href="#">Live Demo</a><a href="#">GitHub</a></div>
        </article>
      </div>
    </section>

    <section class="section services" id="services">
      <div class="section-heading" data-aos="fade-up">
        <p class="eyebrow">Services</p>
        <h2>What I am currently learning and practicing.</h2>
      </div>
      <div class="services-grid">
        <article class="service-card glass-card tilt-card" data-aos="zoom-in"><span>01</span><h3>Web Development</h3><p>Practicing HTML, CSS, JavaScript, and responsive website structure.</p></article>
        <article class="service-card glass-card tilt-card" data-aos="zoom-in" data-aos-delay="80"><span>02</span><h3>UI/UX Design</h3><p>Learning clean layouts, colors, spacing, and user-friendly screen design.</p></article>
        <article class="service-card glass-card tilt-card" data-aos="zoom-in" data-aos-delay="160"><span>03</span><h3>Responsive Design</h3><p>Making projects work nicely on mobile, tablet, and desktop screens.</p></article>
        <article class="service-card glass-card tilt-card" data-aos="zoom-in" data-aos-delay="240"><span>04</span><h3>Mini Projects</h3><p>Building small practice projects to improve logic, design, and confidence.</p></article>
      </div>
    </section>

    <section class="section testimonials" id="testimonials">
      <div class="section-heading" data-aos="fade-up">
        <p class="eyebrow">Learning Notes</p>
        <h2>Growing step by step through practice.</h2>
      </div>
      <div class="testimonial-shell glass-card" data-aos="fade-up">
        <div class="testimonial-track" id="testimonial-track">
          <article class="testimonial active"><p>"I am focusing on strong basics first: HTML structure, CSS layouts, JavaScript logic, and clean responsive design."</p><h3>Current Focus</h3><span>BCA Second Year</span></article>
          <article class="testimonial"><p>"My goal is to build creative beginner projects like animated websites, pet websites, portfolios, and useful student tools."</p><h3>Project Practice</h3><span>Frontend Learning</span></article>
          <article class="testimonial"><p>"Every project helps me improve small details like spacing, colors, hover effects, animations, and mobile design."</p><h3>Design Growth</h3><span>Creative Coding</span></article>
        </div>
        <div class="testimonial-dots" id="testimonial-dots" aria-label="Testimonial controls"></div>
      </div>
    </section>

    <section class="section contact" id="contact">
      <div class="section-heading" data-aos="fade-up">
        <p class="eyebrow">Contact</p>
        <h2>Let's build something cool together </h2>
      </div>
      <div class="contact-layout">
        <aside class="contact-panel glass-card" data-aos="fade-right">
          <h3>Start a Project</h3>
          <p>Share a project idea, college collaboration, frontend doubt, or feedback for my learning journey.</p>
          <a href="mailto:kittuarya7986@gmail.com">kittuarya7986@gmail.com</a>
          <div class="socials">
            <a class="magnetic" href="#" aria-label="GitHub">GH</a>
            <a class="magnetic" href="#" aria-label="LinkedIn">IN</a>
            <a class="magnetic" href="#" aria-label="Instagram">IG</a>
          </div>
        </aside>
        <form class="contact-form glass-card" id="contact-form" novalidate data-aos="fade-left">
          <div class="field"><input id="name" name="name" type="text" autocomplete="name" required><label for="name">Your Name</label><small></small></div>
          <div class="field"><input id="email" name="email" type="email" autocomplete="email" required><label for="email">Email Address</label><small></small></div>
          <div class="field"><textarea id="message" name="message" rows="5" required></textarea><label for="message">Project Message</label><small></small></div>
          <button class="btn primary magnetic" type="submit">Send Message</button>
          <p class="form-status" role="status" aria-live="polite"></p>
        </form>
      </div>
    </section>
  </main>

  <footer class="footer">
    <div class="footer-socials">
      <a href="#">GitHub</a><a href="#">LinkedIn</a><a href="#">Instagram</a>
    </div>
    <p>Copyright 2026 CodeWithKanishka. All rights reserved.</p>
  </footer>

  <button class="back-to-top magnetic" id="back-to-top" type="button" aria-label="Back to top">↑</button>

  <div class="project-modal" id="project-modal" aria-hidden="true" role="dialog" aria-modal="true" aria-labelledby="modal-title">
    <div class="modal-card glass-card">
      <button class="modal-close" type="button" aria-label="Close project modal">×</button>
      <div class="modal-preview"></div>
      <h3 id="modal-title">Project Title</h3>
      <p id="modal-description"></p>
      <div class="modal-actions"><a class="btn primary" href="#">Live Demo</a><a class="btn ghost" href="#">GitHub</a></div>
    </div>
  </div>

  <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/ScrollTrigger.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/aos/2.3.4/aos.js"></script>
  <script src="script.js"></script>
</body>
</html>
