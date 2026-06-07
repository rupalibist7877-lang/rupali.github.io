<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Chatri Automobiles — Premier Car Service Centre</title>
  <link href="https://fonts.googleapis.com/css2?family=DM+Sans:ital,wght@0,300;0,400;0,500;0,600;0,700;1,400&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    /* ── MONOCHROMATIC RED PALETTE ── */
    :root {
      --r900: #5c0412;   /* deepest */
      --r800: #8b0820;
      --r700: #b00d28;
      --r600: #c8102e;   /* primary brand red */
      --r500: #d63350;
      --r400: #e06a80;
      --r300: #eca8b5;
      --r200: #f5d3d9;
      --r100: #faf0f2;
      --r050: #fff7f8;

      --text-dark:  #1a0508;
      --text-mid:   #5c1525;
      --text-soft:  #8b3a4a;
      --border:     rgba(180, 30, 60, 0.14);
      --white:      #ffffff;
    }

    html { scroll-behavior: smooth; }

    body {
      background: var(--white);
      color: var(--text-dark);
      font-family: 'DM Sans', sans-serif;
      font-weight: 400;
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* ── TOP BAR ── */
    .topbar {
      background: var(--r900);
      text-align: center;
      padding: 9px 20px;
      font-size: 0.76rem;
      letter-spacing: 0.14em;
      font-weight: 600;
      text-transform: uppercase;
      color: var(--r300);
    }

    /* ── HEADER / HERO ── */
    header {
      position: relative;
      background: var(--white);
      overflow: hidden;
      padding: 0;
    }

    .header-inner {
      display: grid;
      grid-template-columns: 1fr 1fr;
      min-height: 86vh;
    }

    .header-left {
      display: flex;
      flex-direction: column;
      justify-content: center;
      padding: 70px 60px 70px 70px;
      position: relative;
      z-index: 2;
    }

    .badge {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      border: 1.5px solid var(--r400);
      color: var(--r700);
      background: var(--r100);
      padding: 6px 16px;
      border-radius: 2px;
      font-size: 0.71rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      font-weight: 700;
      margin-bottom: 28px;
      width: fit-content;
      animation: fadeUp 0.8s ease both;
    }
    .badge::before {
      content: '';
      display: inline-block;
      width: 6px; height: 6px;
      background: var(--r600);
      border-radius: 50%;
    }

    .brand-name {
      font-family: 'DM Sans', sans-serif;
      font-weight: 700;
      font-size: clamp(3.4rem, 5.8vw, 6rem);
      line-height: 0.95;
      color: var(--text-dark);
      letter-spacing: -0.02em;
      animation: fadeUp 0.8s 0.1s ease both;
    }
    .brand-name span {
      color: var(--r600);
      display: block;
    }

    .brand-tagline {
      font-family: 'DM Sans', sans-serif;
      font-style: italic;
      font-weight: 300;
      font-size: 1.1rem;
      color: var(--text-soft);
      margin-top: 18px;
      animation: fadeUp 0.8s 0.2s ease both;
    }

    .divider {
      width: 50px; height: 3px;
      background: linear-gradient(90deg, var(--r600), var(--r300));
      margin: 28px 0;
      border-radius: 2px;
      animation: fadeUp 0.8s 0.3s ease both;
    }

    .header-stats {
      display: flex;
      gap: 36px;
      margin-bottom: 42px;
      animation: fadeUp 0.8s 0.35s ease both;
    }
    .stat-num {
      font-family: 'DM Sans', sans-serif;
      font-weight: 700;
      font-size: 2.4rem;
      color: var(--r600);
      line-height: 1;
      letter-spacing: -0.02em;
    }
    .stat-label {
      font-size: 0.71rem;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--text-soft);
      font-weight: 500;
    }

    .hero-cta {
      display: flex;
      gap: 14px;
      flex-wrap: wrap;
      animation: fadeUp 0.8s 0.45s ease both;
    }

    .btn-primary {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      background: var(--r600);
      color: var(--white);
      padding: 14px 30px;
      border-radius: 3px;
      text-decoration: none;
      font-weight: 600;
      font-size: 0.88rem;
      letter-spacing: 0.07em;
      text-transform: uppercase;
      transition: background 0.25s, transform 0.2s;
    }
    .btn-primary:hover { background: var(--r800); transform: translateY(-2px); }
    .btn-primary svg { width: 17px; height: 17px; }

    .btn-outline {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      border: 1.5px solid var(--r300);
      color: var(--r700);
      background: transparent;
      padding: 14px 26px;
      border-radius: 3px;
      text-decoration: none;
      font-weight: 600;
      font-size: 0.88rem;
      letter-spacing: 0.05em;
      transition: border-color 0.25s, background 0.25s, color 0.25s;
    }
    .btn-outline:hover { border-color: var(--r600); background: var(--r100); color: var(--r800); }

    /* Right panel */
    .header-right {
      position: relative;
      overflow: hidden;
    }
    .header-right::before {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(100deg, var(--white) 0%, transparent 28%);
      z-index: 2;
    }
    .header-right img {
      width: 100%; height: 100%;
      object-fit: cover;
      object-position: center;
      filter: brightness(0.6) saturate(0.5) sepia(0.4) hue-rotate(-10deg);
      animation: zoomIn 1.2s ease both;
    }

    .float-card {
      position: absolute;
      bottom: 40px; right: 40px;
      background: rgba(255,255,255,0.96);
      border: 1px solid var(--r200);
      backdrop-filter: blur(12px);
      padding: 20px 26px;
      border-radius: 6px;
      z-index: 3;
      animation: fadeUp 1s 0.6s ease both;
      color: var(--text-dark);
    }
    .float-card-title {
      font-size: 0.68rem;
      text-transform: uppercase;
      letter-spacing: 0.16em;
      color: var(--r600);
      margin-bottom: 6px;
      font-weight: 700;
    }
    .float-card-body { font-size: 0.92rem; font-weight: 600; color: var(--text-dark); }
    .float-card-sub { font-size: 0.74rem; color: var(--text-soft); margin-top: 3px; font-weight: 400; }

    /* ── ABOUT / TRUST SECTION ── */
    .about-section {
      background: var(--r050);
      position: relative;
      overflow: hidden;
      border-top: 1px solid var(--r200);
      border-bottom: 1px solid var(--r200);
    }
    .about-section::before {
      content: 'CHATRI';
      position: absolute;
      top: -20px; left: -10px;
      font-family: 'DM Sans', sans-serif;
      font-weight: 900;
      font-size: 18vw;
      color: rgba(200,16,46,0.04);
      pointer-events: none;
      white-space: nowrap;
      letter-spacing: -0.04em;
    }

    .about-inner {
      max-width: 1200px;
      margin: 0 auto;
      padding: 90px 60px;
      display: grid;
      grid-template-columns: 1fr 1.4fr;
      gap: 80px;
      align-items: center;
      position: relative;
      z-index: 1;
    }

    .section-label {
      font-size: 0.71rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--r600);
      font-weight: 700;
      margin-bottom: 14px;
    }

    .section-heading {
      font-family: 'DM Sans', sans-serif;
      font-weight: 700;
      font-size: clamp(1.7rem, 2.8vw, 2.5rem);
      line-height: 1.15;
      color: var(--text-dark);
      margin-bottom: 20px;
      letter-spacing: -0.02em;
    }
    .section-heading em {
      color: var(--r600);
      font-style: italic;
      font-weight: 700;
    }

    .about-desc {
      font-size: 0.97rem;
      color: var(--text-mid);
      line-height: 1.8;
      margin-bottom: 32px;
      font-weight: 400;
    }

    .trust-pills {
      display: flex;
      flex-wrap: wrap;
      gap: 9px;
    }
    .pill {
      background: var(--r100);
      border: 1px solid var(--r300);
      color: var(--r700);
      padding: 7px 15px;
      border-radius: 100px;
      font-size: 0.77rem;
      font-weight: 600;
      letter-spacing: 0.04em;
    }

    .about-right {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 14px;
    }

    .trust-card {
      background: var(--white);
      border: 1px solid var(--r200);
      border-radius: 8px;
      padding: 26px 22px;
      transition: border-color 0.3s, transform 0.3s, box-shadow 0.3s;
      position: relative;
      overflow: hidden;
    }
    .trust-card::after {
      content: '';
      position: absolute;
      bottom: 0; left: 0;
      width: 100%; height: 3px;
      background: linear-gradient(90deg, var(--r600), var(--r300));
      transform: scaleX(0);
      transition: transform 0.3s;
      transform-origin: left;
    }
    .trust-card:hover {
      border-color: var(--r300);
      transform: translateY(-4px);
      box-shadow: 0 8px 30px rgba(200,16,46,0.1);
    }
    .trust-card:hover::after { transform: scaleX(1); }

    .trust-icon { font-size: 1.8rem; margin-bottom: 12px; display: block; }
    .trust-card h4 {
      font-size: 0.9rem;
      font-weight: 700;
      color: var(--text-dark);
      margin-bottom: 7px;
      letter-spacing: 0.01em;
    }
    .trust-card p {
      font-size: 0.81rem;
      color: var(--text-soft);
      line-height: 1.65;
    }

    /* ── SCHEDULE SERVICE SECTION ── */
    .schedule-section {
      background: var(--white);
      padding: 90px 60px;
      position: relative;
      overflow: hidden;
      border-top: 1px solid var(--r200);
    }

    .schedule-inner {
      max-width: 1100px;
      margin: 0 auto;
    }

    .schedule-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 56px;
      align-items: center;
    }

    .schedule-section-header {
      text-align: center;
      margin-bottom: 52px;
    }
    .schedule-section-header .section-heading {
      font-size: clamp(1.9rem, 3vw, 2.8rem);
    }
    .schedule-section-header p {
      font-size: 0.95rem;
      color: var(--text-soft);
      margin-top: 10px;
    }

    .schedule-img-wrap {
      position: relative;
      border-radius: 10px;
      overflow: hidden;
      aspect-ratio: 4/3;
      box-shadow: 0 24px 70px rgba(200,16,46,0.14);
    }
    .schedule-img-wrap img {
      width: 100%; height: 100%;
      object-fit: cover;
      filter: brightness(0.65) saturate(0.5) sepia(0.5) hue-rotate(-10deg);
    }
    .img-overlay {
      position: absolute;
      inset: 0;
      background: linear-gradient(180deg, transparent 38%, rgba(92,4,18,0.8));
    }
    .img-badge {
      position: absolute;
      top: 18px; left: 18px;
      background: var(--r600);
      color: var(--white);
      font-size: 0.7rem;
      font-weight: 700;
      letter-spacing: 0.13em;
      text-transform: uppercase;
      padding: 5px 13px;
      border-radius: 2px;
    }
    .img-caption {
      position: absolute;
      bottom: 20px; left: 20px; right: 20px;
      font-size: 0.83rem;
      color: var(--r300);
    }
    .img-caption strong { display: block; font-size: 1rem; color: var(--white); margin-bottom: 2px; }

    .schedule-right {}
    .schedule-right .section-heading { font-size: clamp(1.5rem, 2.4vw, 2rem); margin-bottom: 14px; }

    .schedule-desc {
      font-size: 0.95rem;
      color: var(--text-mid);
      line-height: 1.78;
      margin-bottom: 30px;
    }

    .service-list {
      list-style: none;
      display: flex;
      flex-direction: column;
      gap: 11px;
    }
    .service-list li {
      display: flex;
      align-items: center;
      gap: 12px;
      font-size: 0.88rem;
      color: var(--text-mid);
      font-weight: 500;
    }
    .service-list li::before {
      content: '';
      display: block;
      width: 7px; height: 7px;
      background: var(--r500);
      border-radius: 50%;
      flex-shrink: 0;
    }

    /* ── FOOTER ── */
    footer {
      background: var(--r900);
      border-top: 1px solid var(--r800);
      padding: 60px;
    }
    .footer-inner {
      max-width: 1200px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: 2fr 1fr 1fr;
      gap: 60px;
    }
    .footer-brand-name {
      font-family: 'DM Sans', sans-serif;
      font-weight: 700;
      font-size: 2rem;
      color: var(--white);
      letter-spacing: -0.02em;
      margin-bottom: 12px;
    }
    .footer-brand-name span { color: var(--r400); }
    .footer-desc {
      font-size: 0.85rem;
      color: var(--r300);
      line-height: 1.72;
      max-width: 300px;
    }
    .footer-heading {
      font-size: 0.7rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--r400);
      font-weight: 700;
      margin-bottom: 18px;
    }
    .footer-links { list-style: none; display: flex; flex-direction: column; gap: 10px; }
    .footer-links a {
      color: var(--r300);
      text-decoration: none;
      font-size: 0.86rem;
      font-weight: 400;
      transition: color 0.2s;
    }
    .footer-links a:hover { color: var(--white); }
    .footer-bottom {
      max-width: 1200px;
      margin: 40px auto 0;
      padding-top: 26px;
      border-top: 1px solid var(--r800);
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 0.77rem;
      color: var(--r400);
    }

    /* ── ANIMATIONS ── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(22px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    @keyframes zoomIn {
      from { transform: scale(1.07); }
      to   { transform: scale(1); }
    }

    /* ── RESPONSIVE ── */
    @media (max-width: 900px) {
      .header-inner { grid-template-columns: 1fr; }
      .header-right { display: none; }
      .header-left { padding: 55px 28px; }
      .about-inner { grid-template-columns: 1fr; padding: 60px 28px; gap: 36px; }
      .about-right { grid-template-columns: 1fr; }
      .schedule-grid { grid-template-columns: 1fr; }
      .schedule-section { padding: 60px 28px; }
      .footer-inner { grid-template-columns: 1fr; gap: 32px; }
      footer { padding: 48px 28px; }
      .footer-bottom { flex-direction: column; gap: 10px; text-align: center; }
    }
  </style>
</head>
<body>

<!-- TOP BAR -->
<div class="topbar">📍 Pune, Maharashtra &nbsp;|&nbsp; Mon – Fri: 10:00 AM – 6:00 PM &nbsp;|&nbsp; ☎ +91 90213 94405</div>

<!-- ══════════════ HEADER / HERO ══════════════ -->
<header>
  <div class="header-inner">

    <div class="header-left">
      <div class="badge">Authorised Multi-Brand Service Centre</div>

      <h1 class="brand-name">
        Chatri<br>
        <span>Automobiles</span>
      </h1>

      <p class="brand-tagline">Where precision meets passion — every kilometre counts.</p>

      <div class="divider"></div>

      <div class="header-stats">
        <div class="stat">
          <div class="stat-num">22+</div>
          <div class="stat-label">Years of Trust</div>
        </div>
        <div class="stat">
          <div class="stat-num">15K+</div>
          <div class="stat-label">Cars Serviced</div>
        </div>
      </div>

      <div class="hero-cta">
        <a href="https://www.youtube.com/" class="btn-primary">
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"/></svg>
          Book a Service
        </a>
        <a href="tel:+919021394405" class="btn-outline">Call Us Now</a>
      </div>
    </div>

    <div class="header-right">
      <img src="https://images.unsplash.com/photo-1619642751034-765dfdf7c58e?w=1200&q=80" alt="Car being serviced at Chatri Automobiles"/>
      <div class="float-card">
        <div class="float-card-title">Next Available Slot</div>
        <div class="float-card-body">Tomorrow — 10:00 AM</div>
        <div class="float-card-sub">Free Vehicle Health Check Included</div>
      </div>
    </div>

  </div>
</header>

<!-- ══════════════ ABOUT / TRUST ══════════════ -->
<section class="about-section">
  <div class="about-inner">

    <div class="about-left">
      <div class="section-label">Why Choose Us</div>
      <h2 class="section-heading">Built on expertise,<br>driven by trust.</h2>
      <p class="about-desc">
        At Chatri Automobiles, every mechanic on our floor has completed rigorous OEM-certified training and carries a minimum of 8 years of hands-on experience across Indian and international vehicle platforms. We don't cut corners — we use only genuine, manufacturer-approved parts sourced directly from authorised distributors, so your warranty stays intact and your vehicle performs exactly as it was engineered to.
        <br><br>
        From a routine oil change to a complex engine overhaul, our state-of-the-art diagnostics bay and specialised tooling ensure your car receives the care it deserves — every single visit.
      </p>
      <div class="trust-pills">
        <span class="pill">OEM Certified Parts</span>
        <span class="pill">Digital Diagnostics</span>
        <span class="pill">Warranty Safe</span>
        <span class="pill">Transparent Pricing</span>
        <span class="pill">Express Bay Available</span>
      </div>
    </div>

    <div class="about-right">
      <div class="trust-card">
        <span class="trust-icon">🛠️</span>
        <h4>Factory-Trained Mechanics</h4>
        <p>Each technician undergoes 200+ hours of brand-specific training annually to stay current with the latest platforms.</p>
      </div>
      <div class="trust-card">
        <span class="trust-icon">🔩</span>
        <h4>100% Genuine Parts</h4>
        <p>We stock and fit only OEM-approved components — no cheaper substitutes that could compromise performance or safety.</p>
      </div>
      <div class="trust-card">
        <span class="trust-icon">📊</span>
        <h4>Advanced Diagnostics</h4>
        <p>Our multi-brand scanner reads live ECU data, pinpointing issues fast and accurately before they become costly problems.</p>
      </div>
      <div class="trust-card">
        <span class="trust-icon">🏆</span>
        <h4>Quality Guaranteed</h4>
        <p>Every service comes with a 90-day / 5,000 km quality assurance — drive away with complete peace of mind.</p>
      </div>
    </div>

  </div>
</section>

<!-- ══════════════ SCHEDULE SERVICE ══════════════ -->
<section class="schedule-section" id="schedule">
  <div class="schedule-inner">

    <div class="schedule-grid">

      <!-- Image side -->
      <div class="schedule-img-wrap">
        <img src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=900&q=80" alt="Indian cars being serviced — Tata Safari, Kia Seltos at Chatri Automobiles"/>
        <div class="img-overlay"></div>
        <div class="img-badge">Live Service Bay</div>
        <div class="img-caption">
          <strong>Expert hands. Genuine parts.</strong>
          Servicing Tata, Kia, Hyundai &amp; more — right here in Pune.
        </div>
      </div>

      <!-- Text side -->
      <div class="schedule-right">
        <div class="section-label">Schedule Your Service</div>
        <h3 class="section-heading">Your car deserves<br>the very best.</h3>
        <p class="schedule-desc">
          Whether you're due for a routine check-up, facing a warning light, or planning a long drive — our team is ready. Free pick-up &amp; drop available within 10 km of Pune city.
        </p>

        <ul class="service-list">
          <li>Periodic Maintenance &amp; Oil Change</li>
          <li>Multi-Point Health Inspection (free with any service)</li>
          <li>AC Servicing &amp; Gas Refill</li>
          <li>Brake Pad, Tyre &amp; Alignment Check</li>
          <li>Engine &amp; Transmission Diagnostics</li>
          <li>Battery Check &amp; Electrical Repairs</li>
          <li>Denting, Painting &amp; Detailing</li>
        </ul>
      </div>

    </div>
  </div>
</section>

<!-- ══════════════ FOOTER ══════════════ -->
<footer>
  <div class="footer-inner">
    <div>
      <div class="footer-brand-name">Chatri <span>Automobiles</span></div>
      <p class="footer-desc">Pune's most trusted multi-brand car service centre. Expert mechanics, genuine parts, transparent pricing — since 2002.</p>
    </div>
    <div>
      <div class="footer-heading">Services</div>
      <ul class="footer-links">
        <li><a href="#">Periodic Service</a></li>
        <li><a href="#">Engine Repair</a></li>
        <li><a href="#">AC Servicing</a></li>
        <li><a href="#">Denting &amp; Painting</a></li>
        <li><a href="#">Tyre &amp; Alignment</a></li>
        <li><a href="#">Car Detailing</a></li>
      </ul>
    </div>
    <div>
      <div class="footer-heading">Contact</div>
      <ul class="footer-links">
        <li><a href="#">📍 Pune, Maharashtra</a></li>
        <li><a href="tel:+919021394405">☎ +91 90213 94405</a></li>
        <li><a href="mailto:service@chatriautomobiles.in">✉ service@chatriautomobiles.in</a></li>
        <li><a href="#">⏰ Mon–Fri: 10:00 AM – 6:00 PM</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <span>© 2026 Chatri Automobiles. All rights reserved.</span>
    <span>Designed for excellence &nbsp;|&nbsp; Pune, MH</span>
  </div>
</footer>

</body>
</html>
