# -Brightday-Essien-.github.io
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Brightday Essien — Pastor · Brand Strategist · Creative Director · Communication Expert</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Tenor+Sans&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --gold: #C9A84C;
    --gold-light: #E8C96B;
    --gold-pale: #F5E8C0;
    --obsidian: #0A0A0A;
    --deep: #111111;
    --charcoal: #1A1A1A;
    --ash: #2A2828;
    --smoke: #888480;
    --cream: #F0EBE0;
    --white: #FAF8F4;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--obsidian);
    color: var(--cream);
    font-family: 'DM Sans', sans-serif;
    font-weight: 300;
    overflow-x: hidden;
    cursor: none;
  }

  /* CUSTOM CURSOR */
  .cursor {
    width: 10px; height: 10px;
    background: var(--gold);
    border-radius: 50%;
    position: fixed; top: 0; left: 0;
    pointer-events: none; z-index: 9999;
    transform: translate(-50%, -50%);
    transition: transform 0.1s ease;
    mix-blend-mode: difference;
  }
  .cursor-ring {
    width: 36px; height: 36px;
    border: 1px solid rgba(201,168,76,0.5);
    border-radius: 50%;
    position: fixed; top: 0; left: 0;
    pointer-events: none; z-index: 9998;
    transform: translate(-50%, -50%);
    transition: all 0.25s ease;
  }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0;
    z-index: 100;
    padding: 24px 60px;
    display: flex; justify-content: space-between; align-items: center;
    background: linear-gradient(to bottom, rgba(10,10,10,0.95) 0%, transparent 100%);
    backdrop-filter: blur(2px);
  }
  .nav-logo {
    font-family: 'Cormorant Garamond', serif;
    font-size: 20px; font-weight: 300;
    letter-spacing: 0.15em; color: var(--gold-light);
    text-transform: uppercase;
  }
  .nav-links { display: flex; gap: 40px; list-style: none; }
  .nav-links a {
    font-family: 'Tenor Sans', sans-serif;
    font-size: 11px; letter-spacing: 0.2em;
    color: var(--smoke); text-decoration: none;
    text-transform: uppercase;
    transition: color 0.3s ease;
  }
  .nav-links a:hover { color: var(--gold); }

  /* GRAIN OVERLAY */
  body::before {
    content: '';
    position: fixed; inset: 0; z-index: 1;
    pointer-events: none;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.03'/%3E%3C/svg%3E");
    opacity: 0.4;
  }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    position: relative; overflow: hidden;
  }

  .hero-left {
    display: flex; flex-direction: column;
    justify-content: center;
    padding: 140px 60px 80px;
    position: relative; z-index: 2;
  }

  .hero-tagline {
    font-family: 'Tenor Sans', sans-serif;
    font-size: 10px; letter-spacing: 0.35em;
    color: var(--gold); text-transform: uppercase;
    margin-bottom: 28px;
    display: flex; align-items: center; gap: 12px;
  }
  .hero-tagline::before {
    content: ''; display: block;
    width: 30px; height: 1px;
    background: var(--gold);
  }

  .hero-name {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(52px, 7vw, 88px);
    font-weight: 300; line-height: 0.95;
    color: var(--white);
    margin-bottom: 10px;
  }
  .hero-name em {
    font-style: italic; color: var(--gold-light);
    display: block;
  }

  .hero-roles {
    margin: 32px 0;
    display: flex; flex-direction: column; gap: 6px;
  }
  .role-item {
    font-family: 'Tenor Sans', sans-serif;
    font-size: 12px; letter-spacing: 0.25em;
    color: var(--smoke); text-transform: uppercase;
    display: flex; align-items: center; gap: 10px;
    opacity: 0;
    animation: fadeUp 0.7s ease forwards;
  }
  .role-item:nth-child(1) { animation-delay: 0.4s; }
  .role-item:nth-child(2) { animation-delay: 0.55s; }
  .role-item:nth-child(3) { animation-delay: 0.7s; }
  .role-item:nth-child(4) { animation-delay: 0.85s; }
  .role-dot {
    width: 4px; height: 4px;
    background: var(--gold); border-radius: 50%;
    flex-shrink: 0;
  }

  .hero-cta {
    margin-top: 48px; display: flex; gap: 20px; align-items: center;
    opacity: 0; animation: fadeUp 0.7s ease 1s forwards;
  }
  .btn-primary {
    font-family: 'Tenor Sans', sans-serif;
    font-size: 11px; letter-spacing: 0.2em; text-transform: uppercase;
    padding: 14px 32px;
    background: var(--gold);
    color: var(--obsidian);
    border: none; cursor: none;
    text-decoration: none;
    transition: background 0.3s ease, transform 0.2s ease;
    display: inline-block;
  }
  .btn-primary:hover {
    background: var(--gold-light);
    transform: translateY(-1px);
  }
  .btn-ghost {
    font-family: 'Tenor Sans', sans-serif;
    font-size: 11px; letter-spacing: 0.2em; text-transform: uppercase;
    padding: 14px 32px;
    background: transparent;
    color: var(--cream);
    border: 1px solid rgba(201,168,76,0.3);
    cursor: none; text-decoration: none;
    transition: border-color 0.3s ease, color 0.3s ease;
    display: inline-block;
  }
  .btn-ghost:hover { border-color: var(--gold); color: var(--gold); }

  /* HERO PHOTO */
  .hero-right {
    position: relative; overflow: hidden;
    background: var(--charcoal);
  }
  .hero-photo-container {
    width: 100%; height: 100%;
    position: relative; overflow: hidden;
  }
  .hero-photo-container img {
    width: 100%; height: 100%;
    object-fit: cover; object-position: top center;
    filter: grayscale(20%) contrast(1.05);
    opacity: 0.85;
    transition: opacity 0.4s ease;
  }
  .photo-placeholder {
    width: 100%; height: 100%;
    display: flex; flex-direction: column;
    align-items: center; justify-content: center;
    gap: 16px;
    background: linear-gradient(135deg, var(--charcoal), var(--deep));
    cursor: pointer;
    border: 1px dashed rgba(201,168,76,0.2);
    transition: border-color 0.3s ease;
  }
  .photo-placeholder:hover { border-color: rgba(201,168,76,0.5); }
  .photo-placeholder input[type="file"] {
    position: absolute; inset: 0; opacity: 0; cursor: pointer;
    width: 100%; height: 100%;
  }
  .upload-icon {
    width: 56px; height: 56px;
    border: 1px solid rgba(201,168,76,0.4);
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    color: var(--gold);
    font-size: 22px;
  }
  .upload-label {
    font-family: 'Tenor Sans', sans-serif;
    font-size: 11px; letter-spacing: 0.2em;
    color: var(--smoke); text-transform: uppercase;
    text-align: center; line-height: 1.7;
  }
  .hero-photo-overlay {
    position: absolute; inset: 0;
    background: linear-gradient(90deg, var(--obsidian) 0%, transparent 40%),
                linear-gradient(to top, var(--obsidian) 0%, transparent 35%);
    pointer-events: none;
  }

  /* GOLD DIVIDER */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--gold), transparent);
    opacity: 0.3;
    margin: 0 60px;
  }

  /* SECTION BASE */
  section { position: relative; z-index: 2; }
  .section-label {
    font-family: 'Tenor Sans', sans-serif;
    font-size: 10px; letter-spacing: 0.35em;
    color: var(--gold); text-transform: uppercase;
    display: flex; align-items: center; gap: 14px;
    margin-bottom: 20px;
  }
  .section-label::after {
    content: ''; flex: 1; height: 1px;
    background: linear-gradient(90deg, rgba(201,168,76,0.4), transparent);
  }
  .section-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(36px, 5vw, 60px);
    font-weight: 300; line-height: 1.1;
    color: var(--white);
  }
  .section-title em { font-style: italic; color: var(--gold-light); }

  /* ABOUT */
  .about {
    padding: 120px 60px;
    display: grid; grid-template-columns: 1fr 1.4fr;
    gap: 100px; align-items: center;
  }
  .about-quote {
    font-family: 'Cormorant Garamond', serif;
    font-size: 28px; font-weight: 300; font-style: italic;
    line-height: 1.5; color: var(--gold-pale);
    border-left: 1px solid var(--gold);
    padding-left: 28px;
  }
  .about-text {
    font-size: 15px; line-height: 1.9; color: var(--smoke);
    font-weight: 300;
  }
  .about-text p + p { margin-top: 16px; }
  .about-stats {
    display: grid; grid-template-columns: repeat(3, 1fr);
    gap: 24px; margin-top: 40px;
  }
  .stat {
    padding: 20px;
    border: 1px solid rgba(201,168,76,0.15);
    background: rgba(201,168,76,0.03);
    text-align: center;
  }
  .stat-number {
    font-family: 'Cormorant Garamond', serif;
    font-size: 40px; font-weight: 300;
    color: var(--gold-light); display: block;
  }
  .stat-label {
    font-family: 'Tenor Sans', sans-serif;
    font-size: 10px; letter-spacing: 0.15em;
    color: var(--smoke); text-transform: uppercase;
    margin-top: 4px;
  }

  /* ROLES */
  .roles-section {
    padding: 100px 60px;
    background: var(--deep);
  }
  .roles-grid {
    display: grid; grid-template-columns: repeat(4, 1fr);
    gap: 2px; margin-top: 60px;
  }
  .role-card {
    padding: 48px 32px;
    background: var(--charcoal);
    position: relative; overflow: hidden;
    transition: background 0.4s ease;
    cursor: default;
  }
  .role-card::before {
    content: '';
    position: absolute; bottom: 0; left: 0; right: 0;
    height: 2px;
    background: var(--gold);
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.4s ease;
  }
  .role-card:hover { background: var(--ash); }
  .role-card:hover::before { transform: scaleX(1); }
  .role-number {
    font-family: 'Cormorant Garamond', serif;
    font-size: 60px; font-weight: 300;
    color: rgba(201,168,76,0.1);
    line-height: 1; margin-bottom: 20px;
    display: block;
  }
  .role-icon {
    font-size: 28px; margin-bottom: 20px; display: block;
  }
  .role-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: 22px; font-weight: 400;
    color: var(--white); margin-bottom: 12px; line-height: 1.2;
  }
  .role-desc {
    font-size: 13px; line-height: 1.8;
    color: var(--smoke);
  }

  /* PORTFOLIO */
  .portfolio-section {
    padding: 120px 60px;
  }
  .portfolio-header {
    display: flex; justify-content: space-between; align-items: flex-end;
    margin-bottom: 60px;
  }
  .portfolio-filter {
    display: flex; gap: 4px;
  }
  .filter-btn {
    font-family: 'Tenor Sans', sans-serif;
    font-size: 10px; letter-spacing: 0.2em;
    text-transform: uppercase;
    padding: 10px 20px;
    background: transparent;
    color: var(--smoke);
    border: 1px solid rgba(255,255,255,0.08);
    cursor: pointer;
    transition: all 0.3s ease;
  }
  .filter-btn.active, .filter-btn:hover {
    background: rgba(201,168,76,0.1);
    color: var(--gold); border-color: rgba(201,168,76,0.3);
  }

  .portfolio-grid {
    display: grid;
    grid-template-columns: repeat(12, 1fr);
    grid-template-rows: auto;
    gap: 3px;
  }
  .portfolio-item {
    position: relative; overflow: hidden;
    background: var(--charcoal);
    cursor: pointer;
  }
  .portfolio-item:nth-child(1) { grid-column: span 7; grid-row: span 2; }
  .portfolio-item:nth-child(2) { grid-column: span 5; }
  .portfolio-item:nth-child(3) { grid-column: span 5; }
  .portfolio-item:nth-child(4) { grid-column: span 4; }
  .portfolio-item:nth-child(7) { grid-column: span 6; }
  .portfolio-item:nth-child(8) { grid-column: span 6; }
  .portfolio-item:nth-child(5) { grid-column: span 4; }
  .portfolio-item:nth-child(6) { grid-column: span 4; }

  .portfolio-upload-zone {
    width: 100%; padding-top: 75%;
    position: relative;
    background: linear-gradient(135deg, var(--charcoal), var(--ash));
    border: 1px dashed rgba(201,168,76,0.15);
    transition: border-color 0.3s ease;
  }
  .portfolio-item:nth-child(1) .portfolio-upload-zone { padding-top: 60%; }
  .portfolio-upload-zone:hover { border-color: rgba(201,168,76,0.4); }

  .portfolio-upload-inner {
    position: absolute; inset: 0;
    display: flex; flex-direction: column;
    align-items: center; justify-content: center;
    gap: 10px;
  }
  .portfolio-upload-inner input[type="file"] {
    position: absolute; inset: 0; opacity: 0;
    cursor: pointer; width: 100%; height: 100%;
  }
  .upload-plus {
    font-size: 28px; color: rgba(201,168,76,0.3);
    line-height: 1;
  }
  .upload-hint {
    font-family: 'Tenor Sans', sans-serif;
    font-size: 10px; letter-spacing: 0.2em;
    color: rgba(201,168,76,0.3); text-transform: uppercase;
    text-align: center;
  }

  .portfolio-item img {
    position: absolute; inset: 0;
    width: 100%; height: 100%;
    object-fit: cover;
    transition: transform 0.6s ease, filter 0.4s ease;
    filter: grayscale(15%);
  }
  .portfolio-item:hover img {
    transform: scale(1.04);
    filter: grayscale(0%);
  }
  .portfolio-overlay {
    position: absolute; inset: 0;
    background: linear-gradient(to top, rgba(10,10,10,0.85) 0%, transparent 60%);
    opacity: 0;
    transition: opacity 0.4s ease;
    display: flex; align-items: flex-end;
    padding: 24px;
    pointer-events: none;
  }
  .portfolio-item:hover .portfolio-overlay { opacity: 1; }
  .portfolio-meta {}
  .portfolio-cat {
    font-family: 'Tenor Sans', sans-serif;
    font-size: 9px; letter-spacing: 0.25em;
    color: var(--gold); text-transform: uppercase;
    display: block; margin-bottom: 4px;
  }
  .portfolio-title-small {
    font-family: 'Cormorant Garamond', serif;
    font-size: 18px; font-weight: 400; color: var(--white);
  }

  /* EXPERIENCE TIMELINE */
  .experience-section {
    padding: 100px 60px;
    background: var(--deep);
  }
  .timeline {
    margin-top: 60px; position: relative;
    padding-left: 40px;
  }
  .timeline::before {
    content: '';
    position: absolute; left: 0; top: 0; bottom: 0;
    width: 1px;
    background: linear-gradient(to bottom, var(--gold), rgba(201,168,76,0.1));
  }
  .timeline-item {
    position: relative; margin-bottom: 48px;
    padding-bottom: 48px;
    border-bottom: 1px solid rgba(255,255,255,0.04);
  }
  .timeline-item:last-child { border-bottom: none; margin-bottom: 0; }
  .timeline-dot {
    position: absolute; left: -44px; top: 6px;
    width: 8px; height: 8px;
    background: var(--gold); border-radius: 50%;
  }
  .timeline-year {
    font-family: 'Tenor Sans', sans-serif;
    font-size: 10px; letter-spacing: 0.2em;
    color: var(--gold); text-transform: uppercase;
    margin-bottom: 8px;
  }
  .timeline-role {
    font-family: 'Cormorant Garamond', serif;
    font-size: 24px; font-weight: 400; color: var(--white);
    margin-bottom: 4px;
  }
  .timeline-org {
    font-size: 13px; color: var(--smoke); margin-bottom: 12px;
    letter-spacing: 0.05em;
  }
  .timeline-desc {
    font-size: 13px; line-height: 1.8; color: rgba(136,132,128,0.7);
    max-width: 600px;
  }

  /* TESTIMONIALS */
  .testimonials-section {
    padding: 120px 60px;
    overflow: hidden;
  }
  .testimonials-track {
    display: grid; grid-template-columns: repeat(3, 1fr);
    gap: 24px; margin-top: 60px;
  }
  .testimonial-card {
    padding: 40px;
    border: 1px solid rgba(201,168,76,0.12);
    background: rgba(201,168,76,0.02);
    position: relative;
    transition: border-color 0.4s ease, background 0.4s ease;
  }
  .testimonial-card:hover {
    border-color: rgba(201,168,76,0.3);
    background: rgba(201,168,76,0.05);
  }
  .quote-mark {
    font-family: 'Cormorant Garamond', serif;
    font-size: 80px; line-height: 0.5;
    color: rgba(201,168,76,0.15); display: block;
    margin-bottom: 20px;
  }
  .testimonial-text {
    font-family: 'Cormorant Garamond', serif;
    font-size: 17px; font-weight: 300; font-style: italic;
    line-height: 1.7; color: var(--cream);
    margin-bottom: 28px;
  }
  .testimonial-author { display: flex; align-items: center; gap: 14px; }
  .author-avatar {
    width: 44px; height: 44px; border-radius: 50%;
    background: linear-gradient(135deg, var(--charcoal), var(--ash));
    border: 1px solid rgba(201,168,76,0.3);
    display: flex; align-items: center; justify-content: center;
    font-family: 'Cormorant Garamond', serif;
    font-size: 16px; color: var(--gold);
    flex-shrink: 0;
  }
  .author-name {
    font-family: 'Tenor Sans', sans-serif;
    font-size: 12px; letter-spacing: 0.1em;
    color: var(--white); text-transform: uppercase;
  }
  .author-role {
    font-size: 12px; color: var(--smoke); margin-top: 2px;
  }
  .star-row { display: flex; gap: 3px; margin-bottom: 16px; }
  .star { color: var(--gold); font-size: 12px; }

  /* SKILLS */
  .skills-section {
    padding: 100px 60px;
    background: var(--deep);
  }
  .skills-grid {
    display: grid; grid-template-columns: repeat(2, 1fr);
    gap: 60px; margin-top: 60px;
  }
  .skill-group-title {
    font-family: 'Tenor Sans', sans-serif;
    font-size: 10px; letter-spacing: 0.25em;
    color: var(--gold); text-transform: uppercase;
    margin-bottom: 28px;
    padding-bottom: 12px;
    border-bottom: 1px solid rgba(201,168,76,0.2);
  }
  .skill-bar-item { margin-bottom: 20px; }
  .skill-bar-label {
    display: flex; justify-content: space-between;
    font-size: 13px; color: var(--cream);
    margin-bottom: 8px;
  }
  .skill-bar-label span { color: var(--smoke); font-size: 12px; }
  .skill-bar-track {
    height: 2px; background: rgba(255,255,255,0.06);
    position: relative; overflow: hidden;
  }
  .skill-bar-fill {
    height: 100%;
    background: linear-gradient(90deg, var(--gold), var(--gold-light));
    transform-origin: left;
    animation: barFill 1.2s ease forwards;
    transform: scaleX(0);
  }
  @keyframes barFill {
    to { transform: scaleX(1); }
  }

  /* CONTACT */
  .contact-section {
    padding: 120px 60px;
    text-align: center; position: relative;
    overflow: hidden;
  }
  .contact-section::before {
    content: 'CONNECT';
    position: absolute; top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    font-family: 'Cormorant Garamond', serif;
    font-size: 200px; font-weight: 300;
    color: rgba(201,168,76,0.03);
    white-space: nowrap; pointer-events: none;
    z-index: 0;
  }
  .contact-inner { position: relative; z-index: 1; max-width: 600px; margin: 0 auto; }
  .contact-subtitle {
    font-family: 'Cormorant Garamond', serif;
    font-size: 20px; font-style: italic;
    color: var(--smoke); margin-top: 16px; margin-bottom: 48px;
  }
  .contact-links {
    display: flex; gap: 16px; justify-content: center; flex-wrap: wrap;
  }
  .contact-link {
    font-family: 'Tenor Sans', sans-serif;
    font-size: 11px; letter-spacing: 0.2em;
    text-transform: uppercase;
    padding: 14px 28px;
    border: 1px solid rgba(201,168,76,0.25);
    color: var(--cream); text-decoration: none;
    transition: all 0.3s ease; display: flex; align-items: center; gap: 8px;
  }
  .contact-link:hover {
    border-color: var(--gold); color: var(--gold);
    background: rgba(201,168,76,0.05);
  }

  /* FOOTER */
  footer {
    padding: 32px 60px;
    display: flex; justify-content: space-between; align-items: center;
    border-top: 1px solid rgba(255,255,255,0.04);
    background: var(--obsidian);
    position: relative; z-index: 2;
  }
  .footer-copy {
    font-size: 12px; color: rgba(136,132,128,0.5);
    letter-spacing: 0.05em;
  }
  .footer-brand {
    font-family: 'Cormorant Garamond', serif;
    font-size: 14px; color: var(--gold);
    letter-spacing: 0.1em;
  }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .fade-in {
    opacity: 0; transform: translateY(30px);
    transition: opacity 0.8s ease, transform 0.8s ease;
  }
  .fade-in.visible { o
