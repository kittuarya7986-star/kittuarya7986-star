[index.html](https://github.com/user-attachments/files/28606876/index.html)
[script.js](https://github.com/user-attachments/files/28606877/script.js)[style.css](https://github.com/user-attachments/files/28606879/style.css):root {
  --bg: #050505;
  --cyan: #00f5ff;
  --purple: #8a2be2;
  --pink: #ff1493;
  --white: #ffffff;
  --gray: #b0b0b0;
  --panel: rgba(255, 255, 255, 0.075);
  --panel-strong: rgba(255, 255, 255, 0.13);
  --line: rgba(255, 255, 255, 0.15);
  --shadow: 0 22px 70px rgba(0, 0, 0, 0.5);
  --glow-cyan: 0 0 28px rgba(0, 245, 255, 0.36);
  --glow-pink: 0 0 30px rgba(255, 20, 147, 0.34);
}

* { box-sizing: border-box; margin: 0; padding: 0; }

html { scroll-behavior: smooth; }

body {
  min-height: 100vh;
  background:
    linear-gradient(rgba(255, 255, 255, 0.028) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255, 255, 255, 0.028) 1px, transparent 1px),
    radial-gradient(circle at 16% 15%, rgba(0, 245, 255, 0.16), transparent 29%),
    radial-gradient(circle at 84% 12%, rgba(255, 20, 147, 0.12), transparent 27%),
    var(--bg);
  background-size: 44px 44px, 44px 44px, auto, auto, auto;
  color: var(--white);
  font-family: Inter, system-ui, sans-serif;
  overflow-x: hidden;
}

body.menu-open, body.modal-open { overflow: hidden; }

a { color: inherit; text-decoration: none; }
button, input, textarea { font: inherit; }
button { border: 0; color: inherit; cursor: pointer; }

.loader {
  position: fixed;
  inset: 0;
  z-index: 10000;
  display: grid;
  place-items: center;
  gap: 18px;
  background: #030303;
  transition: opacity 500ms ease, visibility 500ms ease;
}

.loader.hidden { opacity: 0; visibility: hidden; }

.loader-mark {
  font-family: "Space Grotesk", sans-serif;
  font-size: 2.2rem;
  font-weight: 700;
  color: var(--cyan);
  text-shadow: 0 0 24px var(--cyan);
}

.loader-line {
  width: min(260px, 70vw);
  height: 4px;
  border-radius: 999px;
  background: rgba(255, 255, 255, 0.1);
  overflow: hidden;
}

.loader-line span {
  display: block;
  height: 100%;
  width: 45%;
  border-radius: inherit;
  background: linear-gradient(90deg, var(--cyan), var(--purple), var(--pink));
  animation: loading 1.2s ease-in-out infinite;
}

.cursor-dot, .cursor-ring, .mouse-glow, #trail-canvas {
  position: fixed;
  pointer-events: none;
  z-index: 9999;
}

.cursor-dot {
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: var(--cyan);
  box-shadow: 0 0 18px var(--cyan);
  transform: translate(-50%, -50%);
}

.cursor-ring {
  width: 42px;
  height: 42px;
  border: 1px solid rgba(0, 245, 255, 0.7);
  border-radius: 50%;
  transform: translate(-50%, -50%);
  transition: width 160ms ease, height 160ms ease, border-color 160ms ease;
}

.cursor-ring.active { width: 66px; height: 66px; border-color: rgba(255, 20, 147, 0.85); }

.mouse-glow {
  width: 340px;
  height: 340px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(0, 245, 255, 0.14), transparent 68%);
  transform: translate(-50%, -50%);
  mix-blend-mode: screen;
  z-index: 1;
}

#trail-canvas { inset: 0; width: 100%; height: 100%; z-index: 2; }

.site-header {
  position: fixed;
  top: 16px;
  left: 0;
  width: 100%;
  z-index: 1000;
  padding: 0 20px;
}

.navbar {
  width: min(1180px, 100%);
  margin: 0 auto;
  min-height: 68px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 22px;
  padding: 12px 16px;
  border: 1px solid var(--line);
  border-radius: 8px;
  background: rgba(5, 5, 5, 0.62);
  backdrop-filter: blur(18px);
  box-shadow: var(--shadow);
  transition: border-color 220ms ease, box-shadow 220ms ease;
}

.site-header.scrolled .navbar { border-color: rgba(0, 245, 255, 0.35); box-shadow: var(--glow-cyan), var(--shadow); }

.logo, h1, h2, h3 { font-family: "Space Grotesk", sans-serif; letter-spacing: 0; }

.logo {
  font-size: clamp(1rem, 2vw, 1.3rem);
  font-weight: 700;
  white-space: nowrap;
}

.logo span { color: var(--cyan); text-shadow: 0 0 16px var(--cyan); }

.nav-links { display: flex; align-items: center; gap: 22px; list-style: none; }
.nav-links a {
  position: relative;
  color: var(--gray);
  font-size: 0.92rem;
  font-weight: 600;
  transition: color 180ms ease;
}
.nav-links a::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: -9px;
  width: 0;
  height: 2px;
  background: linear-gradient(90deg, var(--cyan), var(--pink));
  box-shadow: 0 0 12px var(--cyan);
  transition: width 180ms ease;
}
.nav-links a:hover, .nav-links a.active { color: var(--white); }
.nav-links a:hover::after, .nav-links a.active::after { width: 100%; }

.nav-toggle {
  display: none;
  width: 44px;
  height: 44px;
  border: 1px solid var(--line);
  border-radius: 8px;
  background: rgba(255, 255, 255, 0.08);
}
.nav-toggle span {
  display: block;
  width: 19px;
  height: 2px;
  margin: 5px auto;
  background: var(--white);
  transition: transform 180ms ease, opacity 180ms ease;
}
.nav-toggle.open span:nth-child(1) { transform: translateY(7px) rotate(45deg); }
.nav-toggle.open span:nth-child(2) { opacity: 0; }
.nav-toggle.open span:nth-child(3) { transform: translateY(-7px) rotate(-45deg); }

.section, .section-panel {
  position: relative;
  width: min(1180px, calc(100% - 36px));
  margin: 0 auto;
  padding: 112px 0;
  z-index: 3;
}

.hero {
  width: 100%;
  min-height: 100vh;
  display: grid;
  grid-template-columns: minmax(0, 1.08fr) minmax(300px, 0.78fr);
  align-items: center;
  gap: clamp(30px, 7vw, 86px);
  padding: 145px max(18px, calc((100vw - 1180px) / 2)) 86px;
  overflow: hidden;
  background:
    radial-gradient(circle at 20% 28%, rgba(0, 245, 255, 0.18), transparent 34%),
    radial-gradient(circle at 82% 24%, rgba(255, 20, 147, 0.14), transparent 32%),
    radial-gradient(circle at 55% 84%, rgba(138, 43, 226, 0.12), transparent 34%),
    linear-gradient(180deg, rgba(5, 5, 5, 0.1), rgba(5, 5, 5, 0.82));
}

.hero::before {
  content: "";
  position: absolute;
  inset: 0;
  z-index: 0;
  background:
    linear-gradient(120deg, transparent 18%, rgba(0, 245, 255, 0.08), transparent 44%),
    linear-gradient(250deg, transparent 12%, rgba(255, 20, 147, 0.075), transparent 42%);
  opacity: 0.58;
  animation: heroAtmosphere 16s ease-in-out infinite alternate;
}

.hero::after {
  content: "";
  position: absolute;
  inset: 0;
  z-index: 1;
  background:
    radial-gradient(circle at 50% 40%, transparent 0 28%, rgba(5, 5, 5, 0.22) 72%),
    linear-gradient(90deg, transparent, rgba(0, 245, 255, 0.035), transparent);
  mix-blend-mode: screen;
  opacity: 0.52;
  mask-image: linear-gradient(to bottom, transparent, black 18%, black 76%, transparent);
  animation: scanSweep 11s ease-in-out infinite alternate;
}

#particle-canvas, .animated-grid { position: absolute; inset: 0; width: 100%; height: 100%; }
#particle-canvas { z-index: 0; }

.animated-grid {
  z-index: 0;
  background-image:
    linear-gradient(rgba(0, 245, 255, 0.055) 1px, transparent 1px),
    linear-gradient(90deg, rgba(138, 43, 226, 0.05) 1px, transparent 1px);
  background-size: 92px 92px;
  mask-image: linear-gradient(to bottom, black, transparent 82%);
  animation: gridMove 18s linear infinite;
}

.neon-shape {
  position: absolute;
  z-index: 1;
  border: 1px solid rgba(0, 245, 255, 0.38);
  border-radius: 8px;
  box-shadow: var(--glow-cyan);
  transform: rotate(18deg);
  animation: floatShape 7s ease-in-out infinite;
}
.shape-one { width: 74px; height: 74px; right: 12%; top: 20%; }
.shape-two { width: 54px; height: 54px; left: 7%; bottom: 18%; border-color: rgba(255, 20, 147, 0.5); box-shadow: var(--glow-pink); animation-delay: -2s; }
.shape-three { width: 88px; height: 44px; right: 42%; bottom: 14%; border-color: rgba(138, 43, 226, 0.55); animation-delay: -4s; }

.hero-content, .profile-stage { position: relative; z-index: 4; }

.eyebrow {
  margin-bottom: 14px;
  color: var(--cyan);
  font-size: 0.78rem;
  font-weight: 800;
  text-transform: uppercase;
  letter-spacing: 2px;
}

.hero h1 {
  max-width: 760px;
  font-size: clamp(3rem, 7vw, 6.6rem);
  line-height: 0.96;
}

.hero h1 span {
  display: block;
  color: transparent;
  background: linear-gradient(90deg, var(--cyan), var(--purple), var(--pink));
  background-clip: text;
  -webkit-background-clip: text;
  text-shadow: none;
}

.hero h2 {
  min-height: 42px;
  margin-top: 22px;
  color: #eafcff;
  font-size: clamp(1.18rem, 2.8vw, 2rem);
}

#typed-text { color: var(--cyan); }
.caret { color: var(--pink); animation: blink 700ms steps(2, start) infinite; }

.hero-copy {
  max-width: 690px;
  margin: 22px 0 32px;
  color: var(--gray);
  font-size: clamp(1rem, 2vw, 1.12rem);
  line-height: 1.8;
}

.hero-actions, .modal-actions { display: flex; flex-wrap: wrap; gap: 14px; }

.btn, .filter-btn, .project-actions a, .project-actions button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-height: 48px;
  padding: 0 20px;
  border-radius: 8px;
  border: 1px solid transparent;
  font-weight: 800;
  transition: transform 180ms ease, box-shadow 180ms ease, border-color 180ms ease;
}

.btn:hover, .filter-btn:hover, .project-actions a:hover, .project-actions button:hover { transform: translateY(-3px); }
.btn.primary { color: #021114; background: linear-gradient(135deg, var(--cyan), var(--purple)); box-shadow: var(--glow-cyan); }
.btn.ghost { border-color: rgba(0, 245, 255, 0.4); background: rgba(255, 255, 255, 0.055); }

.profile-card {
  position: relative;
  min-height: 490px;
  border: 1px solid rgba(0, 245, 255, 0.24);
  border-radius: 8px;
  background: linear-gradient(145deg, rgba(255, 255, 255, 0.14), rgba(255, 255, 255, 0.04));
  backdrop-filter: blur(20px);
  box-shadow: var(--glow-pink), var(--shadow);
  overflow: hidden;
  animation: profileFloat 5s ease-in-out infinite;
}

.profile-halo {
  position: absolute;
  inset: 38px;
  border: 1px dashed rgba(0, 245, 255, 0.42);
  border-radius: 50%;
  animation: spin 16s linear infinite;
}

.profile-image {
  position: absolute;
  inset: 58px 34px 92px;
  display: grid;
  place-items: center;
  border: 1px solid rgba(255, 255, 255, 0.13);
  border-radius: 8px;
  background:
    linear-gradient(135deg, rgba(0, 245, 255, 0.2), transparent),
    linear-gradient(225deg, rgba(255, 20, 147, 0.16), transparent),
    rgba(0, 0, 0, 0.36);
  overflow: hidden;
}

.avatar-face {
  width: min(210px, 58vw);
  aspect-ratio: 1;
  border-radius: 50%;
  background:
    linear-gradient(#0b0b12, #0b0b12) padding-box,
    linear-gradient(135deg, var(--cyan), var(--purple), var(--pink)) border-box;
  border: 5px solid transparent;
  box-shadow: 0 0 44px rgba(0, 245, 255, 0.34);
}
.avatar-face::before, .avatar-face::after {
  content: "";
  position: absolute;
  width: 45px;
  height: 14px;
  top: 44%;
  border-radius: 999px;
  background: var(--cyan);
  box-shadow: 0 0 22px var(--cyan);
}
.avatar-face::before { left: calc(50% - 72px); }
.avatar-face::after { right: calc(50% - 72px); }

.avatar-code {
  position: absolute;
  padding: 9px 12px;
  border: 1px solid var(--line);
  border-radius: 8px;
  color: var(--cyan);
  background: rgba(0, 0, 0, 0.46);
  box-shadow: var(--glow-cyan);
  font-weight: 800;
}
.code-a { left: 22px; top: 28px; animation: miniFloat 4s ease-in-out infinite; }
.code-b { right: 22px; bottom: 34px; animation: miniFloat 4.4s ease-in-out infinite reverse; }

.profile-chip {
  position: absolute;
  left: 24px;
  right: 24px;
  bottom: 24px;
  padding: 14px 16px;
  border: 1px solid rgba(0, 245, 255, 0.32);
  border-radius: 8px;
  color: #dffcff;
  background: rgba(0, 0, 0, 0.45);
  text-align: center;
  font-weight: 800;
}

.section-heading { max-width: 760px; margin-bottom: 38px; }
.section-heading h2 { font-size: clamp(1.9rem, 4vw, 3.3rem); line-height: 1.14; }

.glass-card {
  position: relative;
  border: 1px solid var(--line);
  border-radius: 8px;
  background: linear-gradient(145deg, rgba(255, 255, 255, 0.105), rgba(255, 255, 255, 0.045));
  backdrop-filter: blur(18px);
  box-shadow: var(--shadow);
  overflow: hidden;
}
.glass-card::before {
  content: "";
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, rgba(0, 245, 255, 0.14), transparent 40%, rgba(255, 20, 147, 0.13));
  opacity: 0;
  transition: opacity 220ms ease;
  pointer-events: none;
}
.glass-card:hover::before { opacity: 1; }

.about-layout, .contact-layout { display: grid; grid-template-columns: 1fr 1fr; gap: 24px; align-items: start; }
.about-card, .timeline, .contact-panel, .contact-form, .testimonial-shell { padding: 28px; }
.about-card p, .timeline p, .skill-card p, .project-card p, .service-card p, .contact-panel p, .testimonial p {
  color: var(--gray);
  line-height: 1.72;
}

.counter-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 14px; margin-top: 26px; }
.counter-grid div {
  padding: 16px;
  border: 1px solid rgba(255, 255, 255, 0.12);
  border-radius: 8px;
  background: rgba(255, 255, 255, 0.055);
}
.counter-grid strong { display: block; color: var(--cyan); font-size: 2rem; text-shadow: 0 0 18px var(--cyan); }
.counter-grid span { color: var(--gray); font-size: 0.85rem; }

.timeline { display: grid; gap: 22px; }
.timeline-item { position: relative; padding-left: 28px; }
.timeline-item::before {
  content: "";
  position: absolute;
  left: 0;
  top: 6px;
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: var(--pink);
  box-shadow: 0 0 18px var(--pink);
}
.timeline-item::after {
  content: "";
  position: absolute;
  left: 5px;
  top: 25px;
  bottom: -20px;
  width: 1px;
  background: rgba(0, 245, 255, 0.28);
}
.timeline-item:last-child::after { display: none; }
.timeline-item span { color: var(--cyan); font-weight: 800; }

.skills { overflow: hidden; }
.floating-icons {
  position: absolute;
  inset: 90px 0 auto;
  display: flex;
  justify-content: space-between;
  color: rgba(255, 255, 255, 0.12);
  font-weight: 800;
  pointer-events: none;
}
.floating-icons span { animation: miniFloat 5s ease-in-out infinite; }
.floating-icons span:nth-child(2n) { animation-delay: -2s; color: rgba(0, 245, 255, 0.18); }

.skills-grid, .project-grid, .services-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

.skill-card, .service-card, .project-card { padding: 20px; min-height: 245px; transform-style: preserve-3d; transition: transform 180ms ease, opacity 220ms ease, box-shadow 180ms ease; }
.skill-card:hover, .project-card:hover, .service-card:hover { box-shadow: var(--glow-cyan), var(--shadow); }
.skill-icon {
  width: 54px;
  height: 54px;
  display: grid;
  place-items: center;
  margin-bottom: 18px;
  border: 1px solid rgba(0, 245, 255, 0.35);
  border-radius: 8px;
  color: var(--cyan);
  background: rgba(0, 245, 255, 0.08);
  box-shadow: var(--glow-cyan);
  font-weight: 900;
}
.progress {
  height: 9px;
  margin-top: 22px;
  border-radius: 999px;
  background: rgba(255, 255, 255, 0.11);
  overflow: hidden;
}
.progress span {
  display: block;
  width: 0;
  height: 100%;
  border-radius: inherit;
  background: linear-gradient(90deg, var(--cyan), var(--purple), var(--pink));
  box-shadow: 0 0 18px var(--cyan);
  transition: width 1.2s cubic-bezier(0.22, 1, 0.36, 1);
}

.filter-bar { display: flex; flex-wrap: wrap; gap: 12px; margin-bottom: 26px; }
.filter-btn {
  min-height: 42px;
  border: 1px solid rgba(255, 255, 255, 0.14);
  background: rgba(255, 255, 255, 0.06);
}
.filter-btn.active { color: #031014; background: linear-gradient(135deg, var(--cyan), var(--purple)); box-shadow: var(--glow-cyan); }

.project-card.hidden { opacity: 0; transform: scale(0.92); pointer-events: none; display: none; }
.project-preview {
  height: 170px;
  display: grid;
  place-items: end start;
  margin-bottom: 18px;
  padding: 18px;
  border-radius: 8px;
  border: 1px solid rgba(255, 255, 255, 0.14);
  overflow: hidden;
}
.project-preview span {
  padding: 8px 10px;
  border-radius: 8px;
  color: #f7feff;
  background: rgba(0, 0, 0, 0.42);
  font-weight: 800;
}
.preview-one { background: linear-gradient(135deg, rgba(0, 245, 255, 0.88), rgba(5, 5, 5, 0.18)), repeating-linear-gradient(90deg, transparent, transparent 22px, rgba(255, 255, 255, 0.18) 23px); }
.preview-two { background: linear-gradient(135deg, rgba(138, 43, 226, 0.9), rgba(5, 5, 5, 0.2)), radial-gradient(circle at 75% 25%, rgba(0, 245, 255, 0.75), transparent 28%); }
.preview-three { background: linear-gradient(135deg, rgba(255, 20, 147, 0.86), rgba(5, 5, 5, 0.2)), linear-gradient(90deg, rgba(255, 255, 255, 0.18) 18%, transparent 18%); }
.preview-four { background: linear-gradient(135deg, rgba(0, 245, 255, 0.7), rgba(138, 43, 226, 0.78)), repeating-linear-gradient(0deg, transparent, transparent 18px, rgba(255, 255, 255, 0.15) 19px); }

.project-actions { display: flex; flex-wrap: wrap; gap: 9px; margin-top: 18px; }
.project-actions a, .project-actions button {
  min-height: 38px;
  padding: 0 12px;
  border: 1px solid rgba(0, 245, 255, 0.28);
  background: rgba(0, 245, 255, 0.07);
}

.service-card span { display: block; margin-bottom: 28px; color: var(--pink); font-size: 2.1rem; font-weight: 900; text-shadow: 0 0 18px var(--pink); }

.testimonial-shell { max-width: 860px; }
.testimonial { display: none; }
.testimonial.active { display: block; animation: fadeSlide 520ms ease both; }
.testimonial p { font-size: clamp(1.1rem, 2.3vw, 1.55rem); }
.testimonial h3 { margin-top: 22px; }
.testimonial span { color: var(--cyan); font-weight: 700; }
.testimonial-dots { display: flex; gap: 10px; margin-top: 22px; }
.testimonial-dots button {
  width: 34px;
  height: 4px;
  border-radius: 999px;
  background: rgba(255, 255, 255, 0.22);
}
.testimonial-dots button.active { background: var(--cyan); box-shadow: 0 0 12px var(--cyan); }

.contact-panel a { display: inline-block; margin-top: 18px; color: var(--cyan); font-weight: 800; word-break: break-word; }
.socials, .footer-socials { display: flex; flex-wrap: wrap; gap: 12px; margin-top: 24px; }
.socials a {
  width: 46px;
  height: 46px;
  display: grid;
  place-items: center;
  border: 1px solid rgba(0, 245, 255, 0.35);
  border-radius: 8px;
  background: rgba(255, 255, 255, 0.06);
  color: var(--cyan);
  font-weight: 900;
}

.contact-form { display: grid; gap: 18px; }
.field { position: relative; }
.field input, .field textarea {
  width: 100%;
  border: 1px solid rgba(255, 255, 255, 0.16);
  border-radius: 8px;
  padding: 18px 14px 12px;
  color: var(--white);
  background: rgba(0, 0, 0, 0.34);
  outline: none;
  resize: vertical;
}
.field label {
  position: absolute;
  left: 14px;
  top: 15px;
  color: var(--gray);
  pointer-events: none;
  transition: transform 160ms ease, color 160ms ease, font-size 160ms ease;
}
.field input:focus, .field textarea:focus { border-color: rgba(0, 245, 255, 0.72); box-shadow: 0 0 0 4px rgba(0, 245, 255, 0.1); }
.field.filled label, .field input:focus + label, .field textarea:focus + label {
  transform: translateY(-12px);
  color: var(--cyan);
  font-size: 0.72rem;
}
.field.error input, .field.error textarea { border-color: rgba(255, 20, 147, 0.82); }
.field small { display: block; min-height: 18px; margin-top: 6px; color: #ff8bd0; font-size: 0.78rem; }
.form-status { min-height: 24px; color: var(--cyan); font-weight: 800; }

.footer {
  position: relative;
  z-index: 3;
  padding: 34px 18px;
  border-top: 1px solid var(--line);
  text-align: center;
  color: var(--gray);
  background: rgba(0, 0, 0, 0.38);
}
.footer-socials { justify-content: center; margin: 0 0 14px; }
.footer-socials a { color: var(--cyan); font-weight: 800; }

.back-to-top {
  position: fixed;
  right: 20px;
  bottom: 20px;
  width: 48px;
  height: 48px;
  z-index: 900;
  border: 1px solid rgba(0, 245, 255, 0.4);
  border-radius: 8px;
  background: linear-gradient(135deg, rgba(0, 245, 255, 0.9), rgba(138, 43, 226, 0.9));
  color: #020b0e;
  font-size: 1.4rem;
  font-weight: 900;
  box-shadow: var(--glow-cyan);
  opacity: 0;
  visibility: hidden;
  transition: opacity 180ms ease, visibility 180ms ease, transform 180ms ease;
}
.back-to-top.visible { opacity: 1; visibility: visible; }

.project-modal {
  position: fixed;
  inset: 0;
  z-index: 5000;
  display: grid;
  place-items: center;
  padding: 20px;
  background: rgba(0, 0, 0, 0.72);
  opacity: 0;
  visibility: hidden;
  transition: opacity 200ms ease, visibility 200ms ease;
}
.project-modal.open { opacity: 1; visibility: visible; }
.modal-card { width: min(620px, 100%); padding: 24px; transform: translateY(18px) scale(0.96); transition: transform 200ms ease; }
.project-modal.open .modal-card { transform: translateY(0) scale(1); }
.modal-close {
  position: absolute;
  right: 12px;
  top: 10px;
  width: 38px;
  height: 38px;
  border-radius: 8px;
  background: rgba(255, 255, 255, 0.08);
  font-size: 1.5rem;
}
.modal-preview { height: 220px; margin-bottom: 18px; border-radius: 8px; background: linear-gradient(135deg, var(--cyan), var(--purple), var(--pink)); }
.modal-card p { color: var(--gray); line-height: 1.72; margin: 10px 0 18px; }

@keyframes loading { 0% { transform: translateX(-105%); } 100% { transform: translateX(235%); } }
@keyframes blink { 50% { opacity: 0; } }
@keyframes spin { to { transform: rotate(360deg); } }
@keyframes gridMove { to { background-position: 92px 92px; } }
@keyframes heroAtmosphere {
  0% { filter: hue-rotate(0deg); transform: translateX(-1%); }
  100% { filter: hue-rotate(10deg); transform: translateX(1%); }
}
@keyframes scanSweep {
  0% { background-position: 45% 40%, -30vw 0; }
  100% { background-position: 55% 44%, 30vw 0; }
}
@keyframes profileFloat { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-18px); } }
@keyframes miniFloat { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-13px); } }
@keyframes floatShape { 0%, 100% { transform: translateY(0) rotate(18deg); } 50% { transform: translateY(-24px) rotate(30deg); } }
@keyframes fadeSlide { from { opacity: 0; transform: translateY(14px); } to { opacity: 1; transform: translateY(0); } }

@media (max-width: 980px) {
  .nav-toggle { display: block; }
  .nav-links {
    position: fixed;
    left: 20px;
    right: 20px;
    top: 88px;
    display: grid;
    gap: 4px;
    padding: 14px;
    border: 1px solid var(--line);
    border-radius: 8px;
    background: rgba(5, 5, 5, 0.94);
    backdrop-filter: blur(18px);
    opacity: 0;
    pointer-events: none;
    transform: translateY(-12px);
    transition: opacity 180ms ease, transform 180ms ease;
  }
  .nav-links.open { opacity: 1; pointer-events: auto; transform: translateY(0); }
  .nav-links a { display: block; padding: 12px; }
  .hero, .about-layout, .contact-layout { grid-template-columns: 1fr; }
  .profile-stage { max-width: 520px; }
  .skills-grid, .project-grid, .services-grid { grid-template-columns: repeat(2, 1fr); }
}

@media (max-width: 660px) {
  .cursor-dot, .cursor-ring, .mouse-glow, #trail-canvas { display: none; }
  .site-header { top: 10px; padding: 0 12px; }
  .section, .section-panel { width: min(100% - 28px, 1180px); padding: 82px 0; }
  .hero { padding: 128px 14px 70px; }
  .hero h1 { font-size: clamp(2.55rem, 17vw, 4rem); }
  .hero-actions, .btn, .filter-btn { width: 100%; }
  .skills-grid, .project-grid, .services-grid, .counter-grid { grid-template-columns: 1fr; }
  .profile-card { min-height: 390px; }
  .profile-image { inset: 46px 22px 82px; }
  .floating-icons { display: none; }
  .about-card, .timeline, .contact-panel, .contact-form, .testimonial-shell { padding: 22px; }
}

@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    scroll-behavior: auto !important;
    transition-duration: 0.01ms !important;
  }
}
