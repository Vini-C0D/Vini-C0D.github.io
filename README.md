# Vini-C0D.github.io
Barbearia 
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Navalha & Arte — Barbearia</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&family=Barlow:wght@300;400;500;600&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --cream: #F5EFE0;
      --cream-dark: #E8DFC8;
      --brown: #2C1A0E;
      --brown-mid: #5C3A1E;
      --gold: #C89B3C;
      --gold-light: #E8C46A;
      --warm-gray: #8C7B6B;
      --white: #FDFAF5;
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Barlow', sans-serif;
      background: var(--brown);
      color: var(--cream);
      overflow-x: hidden;
    }

    /* ── NAV ── */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      display: flex; align-items: center; justify-content: space-between;
      padding: 1.25rem 4rem;
      background: rgba(44, 26, 14, 0.95);
      backdrop-filter: blur(8px);
      border-bottom: 1px solid rgba(200, 155, 60, 0.25);
    }

    .nav-logo {
      font-family: 'Playfair Display', serif;
      font-size: 1.4rem;
      font-weight: 900;
      color: var(--gold);
      letter-spacing: 0.05em;
      text-decoration: none;
    }

    .nav-logo span { color: var(--cream); font-weight: 400; }

    nav ul { list-style: none; display: flex; gap: 2.5rem; }
    nav ul a {
      color: var(--cream);
      text-decoration: none;
      font-size: 0.85rem;
      font-weight: 500;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      opacity: 0.75;
      transition: opacity 0.2s, color 0.2s;
    }
    nav ul a:hover { opacity: 1; color: var(--gold); }

    .nav-cta {
      background: var(--gold);
      color: var(--brown) !important;
      padding: 0.6rem 1.5rem;
      border-radius: 2px;
      opacity: 1 !important;
      font-weight: 600 !important;
      transition: background 0.2s !important;
    }
    .nav-cta:hover { background: var(--gold-light) !important; }

    /* ── HERO ── */
    #hero {
      min-height: 100vh;
      display: grid;
      grid-template-columns: 1fr 1fr;
      padding-top: 80px;
      position: relative;
      overflow: hidden;
    }

    .hero-left {
      display: flex;
      flex-direction: column;
      justify-content: center;
      padding: 5rem 3rem 5rem 4rem;
    }

    .hero-badge {
      display: inline-flex;
      align-items: center;
      gap: 0.6rem;
      font-size: 0.75rem;
      font-weight: 600;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 1.5rem;
    }
    .hero-badge::before {
      content: '';
      display: block;
      width: 32px;
      height: 1px;
      background: var(--gold);
    }

    .hero-title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(3rem, 5vw, 5.5rem);
      font-weight: 900;
      line-height: 1.05;
      color: var(--white);
      margin-bottom: 1.5rem;
    }

    .hero-title em {
      font-style: italic;
      color: var(--gold);
    }

    .hero-subtitle {
      font-size: 1.05rem;
      font-weight: 300;
      color: rgba(245, 239, 224, 0.65);
      line-height: 1.75;
      max-width: 400px;
      margin-bottom: 3rem;
    }

    .hero-actions { display: flex; gap: 1rem; align-items: center; }

    .btn-primary {
      background: var(--gold);
      color: var(--brown);
      padding: 1rem 2.5rem;
      font-family: 'Barlow', sans-serif;
      font-size: 0.85rem;
      font-weight: 700;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      text-decoration: none;
      border: none;
      cursor: pointer;
      border-radius: 2px;
      transition: background 0.2s, transform 0.15s;
    }
    .btn-primary:hover { background: var(--gold-light); transform: translateY(-1px); }

    .btn-ghost {
      color: var(--cream);
      font-size: 0.85rem;
      font-weight: 500;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      text-decoration: none;
      opacity: 0.6;
      transition: opacity 0.2s;
      display: flex; align-items: center; gap: 0.5rem;
    }
    .btn-ghost:hover { opacity: 1; }
    .btn-ghost::after { content: '→'; font-size: 1rem; }

    .hero-stats {
      display: flex; gap: 3rem;
      margin-top: 4rem;
      padding-top: 2.5rem;
      border-top: 1px solid rgba(200, 155, 60, 0.2);
    }
    .stat-num {
      font-family: 'Playfair Display', serif;
      font-size: 2.2rem;
      font-weight: 700;
      color: var(--gold);
    }
    .stat-label {
      font-size: 0.75rem;
      font-weight: 500;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--warm-gray);
      margin-top: 0.2rem;
    }

    .hero-right {
      position: relative;
      display: flex;
      align-items: stretch;
      overflow: hidden;
    }

    .hero-img-wrapper {
      position: relative;
      width: 100%;
      overflow: hidden;
    }

    .hero-img-wrapper::before {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(to right, var(--brown) 0%, transparent 20%),
                  linear-gradient(to bottom, rgba(44,26,14,0.3) 0%, transparent 30%);
      z-index: 1;
    }

    .hero-img-placeholder {
      width: 100%;
      height: 100%;
      min-height: 600px;
      background:
        repeating-linear-gradient(
          45deg,
          rgba(200,155,60,0.04) 0px,
          rgba(200,155,60,0.04) 1px,
          transparent 1px,
          transparent 20px
        ),
        linear-gradient(135deg, #3d2513 0%, #1a0d05 100%);
      display: flex;
      align-items: center;
      justify-content: center;
    }

    /* Decorative barber pole illustration */
    .barber-pole-deco {
      position: absolute;
      right: 3rem;
      top: 50%;
      transform: translateY(-50%);
      z-index: 2;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 0.5rem;
    }

    .pole-wrap {
      width: 56px;
      height: 260px;
      border-radius: 28px;
      background: #e8dfc8;
      overflow: hidden;
      position: relative;
      box-shadow: inset -6px 0 12px rgba(0,0,0,0.25), 0 0 0 3px #c89b3c;
    }

    .pole-stripe {
      position: absolute;
      left: -100%;
      width: 300%;
      height: 100%;
      background: repeating-linear-gradient(
        60deg,
        #e8dfc8 0px,
        #e8dfc8 14px,
        #c0272b 14px,
        #c0272b 28px,
        #e8dfc8 28px,
        #e8dfc8 42px,
        #0a2e6e 42px,
        #0a2e6e 56px
      );
      animation: spin-stripe 4s linear infinite;
    }

    @keyframes spin-stripe {
      0%   { transform: translateY(0); }
      100% { transform: translateY(56px); }
    }

    .pole-cap {
      width: 64px; height: 18px;
      background: var(--gold);
      border-radius: 4px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.4);
    }

    /* ── DECORATIVE LINE ── */
    .section-line {
      width: 48px; height: 2px;
      background: var(--gold);
      margin-bottom: 1rem;
    }

    /* ── ABOUT ── */
    #sobre {
      padding: 7rem 4rem;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 5rem;
      align-items: center;
      background: var(--cream);
      color: var(--brown);
    }

    .about-label {
      font-size: 0.75rem;
      font-weight: 700;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 0.75rem;
    }

    .section-title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2rem, 3vw, 3rem);
      font-weight: 900;
      line-height: 1.2;
      color: var(--brown);
      margin-bottom: 1.5rem;
    }

    .section-title em { color: var(--gold); font-style: italic; }

    .about-text {
      font-size: 1rem;
      font-weight: 300;
      line-height: 1.85;
      color: var(--brown-mid);
      margin-bottom: 2rem;
    }

    .about-features {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1.25rem;
    }

    .feat-item {
      display: flex;
      align-items: flex-start;
      gap: 0.75rem;
    }

    .feat-icon {
      width: 36px; height: 36px; flex-shrink: 0;
      background: var(--brown);
      border-radius: 2px;
      display: flex; align-items: center; justify-content: center;
      font-size: 1.1rem;
    }

    .feat-text strong {
      display: block;
      font-size: 0.85rem;
      font-weight: 600;
      letter-spacing: 0.05em;
      color: var(--brown);
    }
    .feat-text span {
      font-size: 0.8rem;
      color: var(--warm-gray);
    }

    .about-image-side {
      position: relative;
    }

    .img-frame {
      width: 100%;
      aspect-ratio: 4/5;
      background:
        repeating-linear-gradient(
          -45deg,
          rgba(44,26,14,0.06) 0px,
          rgba(44,26,14,0.06) 1px,
          transparent 1px,
          transparent 18px
        ),
        linear-gradient(135deg, #e8dfc8 0%, #d4c5a9 100%);
      border-radius: 2px;
      position: relative;
      overflow: hidden;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .img-frame-inner {
      font-family: 'Playfair Display', serif;
      font-size: 5rem;
      color: rgba(44,26,14,0.12);
      font-weight: 900;
      user-select: none;
    }

    .img-frame-deco {
      position: absolute;
      bottom: -1rem; right: -1rem;
      width: 60%;
      aspect-ratio: 1;
      border: 3px solid var(--gold);
      border-radius: 2px;
      z-index: -1;
    }

    /* ── SERVIÇOS ── */
    #servicos {
      padding: 7rem 4rem;
      background: var(--brown);
    }

    .section-header {
      text-align: center;
      margin-bottom: 4rem;
    }

    .section-header .section-title { color: var(--white); }

    .section-line-center {
      width: 48px; height: 2px;
      background: var(--gold);
      margin: 0 auto 1rem;
    }

    .section-label {
      font-size: 0.75rem;
      font-weight: 700;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 0.75rem;
    }

    .services-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1.5px;
      background: rgba(200,155,60,0.1);
      border: 1px solid rgba(200,155,60,0.1);
    }

    .service-card {
      background: var(--brown);
      padding: 2.5rem 2rem;
      position: relative;
      overflow: hidden;
      transition: background 0.3s;
      cursor: default;
    }

    .service-card::before {
      content: '';
      position: absolute;
      top: 0; left: 0;
      width: 3px; height: 0;
      background: var(--gold);
      transition: height 0.3s;
    }
    .service-card:hover { background: rgba(92,58,30,0.5); }
    .service-card:hover::before { height: 100%; }

    .service-icon {
      font-size: 2rem;
      margin-bottom: 1.25rem;
      display: block;
    }

    .service-name {
      font-family: 'Playfair Display', serif;
      font-size: 1.2rem;
      font-weight: 700;
      color: var(--white);
      margin-bottom: 0.75rem;
    }

    .service-desc {
      font-size: 0.88rem;
      font-weight: 300;
      color: var(--warm-gray);
      line-height: 1.7;
      margin-bottom: 1.5rem;
    }

    .service-price {
      font-family: 'Playfair Display', serif;
      font-size: 1.6rem;
      font-weight: 700;
      color: var(--gold);
    }

    .service-price span {
      font-family: 'Barlow', sans-serif;
      font-size: 0.8rem;
      font-weight: 400;
      color: var(--warm-gray);
      margin-left: 0.25rem;
    }

    /* ── BARBEIROS ── */
    #barbeiros {
      padding: 7rem 4rem;
      background: #1e0f06;
    }

    .barbers-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 2rem;
      margin-top: 1rem;
    }

    .barber-card {
      position: relative;
      overflow: hidden;
    }

    .barber-photo {
      width: 100%;
      aspect-ratio: 3/4;
      background:
        repeating-linear-gradient(
          60deg,
          rgba(200,155,60,0.05) 0px,
          rgba(200,155,60,0.05) 1px,
          transparent 1px,
          transparent 22px
        ),
        linear-gradient(160deg, #3d2513 30%, #1a0d05 100%);
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: 'Playfair Display', serif;
      font-size: 4rem;
      color: rgba(245,239,224,0.08);
      font-weight: 900;
      border-bottom: 3px solid var(--gold);
    }

    .barber-info {
      padding: 1.25rem 1.5rem;
      background: rgba(92,58,30,0.2);
      border: 1px solid rgba(200,155,60,0.1);
      border-top: none;
    }

    .barber-name {
      font-family: 'Playfair Display', serif;
      font-size: 1.2rem;
      font-weight: 700;
      color: var(--white);
      margin-bottom: 0.25rem;
    }

    .barber-role {
      font-size: 0.78rem;
      font-weight: 600;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 0.75rem;
    }

    .barber-bio {
      font-size: 0.85rem;
      font-weight: 300;
      color: var(--warm-gray);
      line-height: 1.65;
    }

    /* ── AGENDAMENTO ── */
    #agendamento {
      padding: 7rem 4rem;
      background: var(--gold);
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 5rem;
      align-items: center;
    }

    #agendamento .section-title {
      color: var(--brown);
    }

    .booking-label {
      font-size: 0.75rem;
      font-weight: 700;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--brown-mid);
      margin-bottom: 0.75rem;
    }

    .booking-text {
      font-size: 1rem;
      font-weight: 300;
      line-height: 1.85;
      color: var(--brown-mid);
      margin-bottom: 2.5rem;
    }

    .booking-form {
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }

    .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }

    .form-group {
      display: flex;
      flex-direction: column;
      gap: 0.4rem;
    }

    .form-group label {
      font-size: 0.75rem;
      font-weight: 700;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--brown);
    }

    .form-group input,
    .form-group select {
      width: 100%;
      padding: 0.85rem 1rem;
      background: rgba(44,26,14,0.1);
      border: 1.5px solid rgba(44,26,14,0.2);
      border-radius: 2px;
      font-family: 'Barlow', sans-serif;
      font-size: 0.9rem;
      color: var(--brown);
      outline: none;
      transition: border-color 0.2s;
      -webkit-appearance: none;
    }
    .form-group input::placeholder { color: rgba(44,26,14,0.4); }
    .form-group input:focus,
    .form-group select:focus { border-color: var(--brown); }

    .btn-book {
      margin-top: 0.5rem;
      padding: 1rem 2rem;
      background: var(--brown);
      color: var(--gold);
      font-family: 'Barlow', sans-serif;
      font-size: 0.85rem;
      font-weight: 700;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      border: none;
      border-radius: 2px;
      cursor: pointer;
      transition: background 0.2s, transform 0.15s;
      align-self: flex-start;
      min-width: 220px;
    }
    .btn-book:hover { background: var(--brown-mid); transform: translateY(-1px); }

    .booking-aside {
      display: flex;
      flex-direction: column;
      gap: 2rem;
    }

    .info-block {
      display: flex;
      gap: 1.25rem;
      align-items: flex-start;
    }

    .info-icon {
      width: 44px; height: 44px; flex-shrink: 0;
      background: rgba(44,26,14,0.1);
      border-radius: 2px;
      display: flex; align-items: center; justify-content: center;
      font-size: 1.25rem;
    }

    .info-title {
      font-size: 0.8rem;
      font-weight: 700;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--brown);
      margin-bottom: 0.3rem;
    }

    .info-detail {
      font-size: 0.92rem;
      font-weight: 400;
      color: var(--brown-mid);
      line-height: 1.6;
    }

    /* ── DEPOIMENTOS ── */
    #depoimentos {
      padding: 7rem 4rem;
      background: var(--cream);
    }

    .testimonials-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1.5rem;
      margin-top: 1rem;
    }

    .testimonial-card {
      background: var(--white);
      border: 1px solid var(--cream-dark);
      border-radius: 2px;
      padding: 2rem;
      position: relative;
    }

    .testimonial-card::before {
      content: '"';
      position: absolute;
      top: 1rem; right: 1.5rem;
      font-family: 'Playfair Display', serif;
      font-size: 4rem;
      color: var(--gold);
      line-height: 1;
      opacity: 0.4;
    }

    .stars {
      color: var(--gold);
      font-size: 0.85rem;
      margin-bottom: 1rem;
      letter-spacing: 0.1em;
    }

    .testimonial-text {
      font-size: 0.92rem;
      font-weight: 300;
      line-height: 1.8;
      color: var(--brown-mid);
      margin-bottom: 1.5rem;
    }

    .testimonial-author {
      display: flex;
      align-items: center;
      gap: 0.75rem;
    }

    .author-avatar {
      width: 40px; height: 40px;
      border-radius: 50%;
      background: var(--brown);
      display: flex; align-items: center; justify-content: center;
      font-family: 'Playfair Display', serif;
      font-weight: 700;
      font-size: 0.9rem;
      color: var(--gold);
    }

    .author-name {
      font-size: 0.88rem;
      font-weight: 600;
      color: var(--brown);
    }

    .author-since {
      font-size: 0.75rem;
      color: var(--warm-gray);
    }

    /* ── FOOTER ── */
    footer {
      background: #0f0700;
      padding: 4rem;
      display: grid;
      grid-template-columns: 2fr 1fr 1fr 1fr;
      gap: 3rem;
      border-top: 1px solid rgba(200,155,60,0.15);
    }

    .footer-brand {
      font-family: 'Playfair Display', serif;
      font-size: 1.6rem;
      font-weight: 900;
      color: var(--gold);
      margin-bottom: 1rem;
    }

    .footer-brand span { color: var(--cream); font-weight: 400; }

    .footer-tagline {
      font-size: 0.85rem;
      font-weight: 300;
      color: var(--warm-gray);
      line-height: 1.7;
      max-width: 260px;
      margin-bottom: 1.5rem;
    }

    .social-links { display: flex; gap: 0.75rem; }

    .social-btn {
      width: 38px; height: 38px;
      border: 1px solid rgba(200,155,60,0.3);
      border-radius: 2px;
      display: flex; align-items: center; justify-content: center;
      font-size: 0.85rem;
      color: var(--warm-gray);
      text-decoration: none;
      transition: border-color 0.2s, color 0.2s;
    }
    .social-btn:hover { border-color: var(--gold); color: var(--gold); }

    .footer-col h4 {
      font-family: 'Playfair Display', serif;
      font-size: 0.95rem;
      font-weight: 700;
      color: var(--white);
      margin-bottom: 1.25rem;
      padding-bottom: 0.75rem;
      border-bottom: 1px solid rgba(200,155,60,0.2);
    }

    .footer-col ul { list-style: none; display: flex; flex-direction: column; gap: 0.6rem; }

    .footer-col ul a {
      font-size: 0.85rem;
      font-weight: 300;
      color: var(--warm-gray);
      text-decoration: none;
      transition: color 0.2s;
    }
    .footer-col ul a:hover { color: var(--gold); }

    .footer-bottom {
      background: #0f0700;
      padding: 1.5rem 4rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-top: 1px solid rgba(200,155,60,0.1);
    }

    .footer-bottom p {
      font-size: 0.78rem;
      color: rgba(140,123,107,0.6);
    }

    .footer-bottom a {
      color: var(--gold);
      text-decoration: none;
      opacity: 0.7;
    }

    /* ── DIVIDER ── */
    .ornament {
      text-align: center;
      color: var(--gold);
      font-size: 1rem;
      letter-spacing: 0.5em;
      opacity: 0.4;
      padding: 2rem 0;
      background: var(--brown);
    }

    /* ── RESPONSIVE ── */
    @media (max-width: 900px) {
      nav { padding: 1rem 1.5rem; }
      nav ul { display: none; }
      #hero { grid-template-columns: 1fr; }
      .hero-right { display: none; }
      #sobre { grid-template-columns: 1fr; padding: 4rem 1.5rem; }
      #servicos { padding: 4rem 1.5rem; }
      .services-grid { grid-template-columns: 1fr; }
      #barbeiros { padding: 4rem 1.5rem; }
      .barbers-grid { grid-template-columns: 1fr; }
      #agendamento { grid-template-columns: 1fr; padding: 4rem 1.5rem; }
      #depoimentos { padding: 4rem 1.5rem; }
      .testimonials-grid { grid-template-columns: 1fr; }
      footer { grid-template-columns: 1fr 1fr; padding: 3rem 1.5rem; }
      .footer-bottom { padding: 1.5rem; flex-direction: column; gap: 0.5rem; text-align: center; }
      .hero-left { padding: 4rem 1.5rem 3rem; }
      #barbeiros .section-header, #servicos .section-header, #depoimentos .section-header { text-align: left; }
      .section-line-center { margin: 0 0 1rem; }
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#" class="nav-logo">Navalha<span> & Arte</span></a>
  <ul>
    <li><a href="#sobre">Sobre</a></li>
    <li><a href="#servicos">Serviços</a></li>
    <li><a href="#barbeiros">Barbeiros</a></li>
    <li><a href="#depoimentos">Depoimentos</a></li>
    <li><a href="#agendamento" class="nav-cta">Agendar</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-left">
    <div class="hero-badge">Desde 2008 — Curitiba, PR</div>
    <h1 class="hero-title">
      Arte que<br>
      <em>transforma</em><br>
      sua imagem
    </h1>
    <p class="hero-subtitle">
      Onde cada corte é uma obra de precisão. Tradição, técnica e o melhor da barbearia clássica reunidos em um só lugar.
    </p>
    <div class="hero-actions">
      <a href="#agendamento" class="btn-primary">Agendar Horário</a>
      <a href="#servicos" class="btn-ghost">Ver Serviços</a>
    </div>
    <div class="hero-stats">
      <div>
        <div class="stat-num">16+</div>
        <div class="stat-label">Anos de experiência</div>
      </div>
      <div>
        <div class="stat-num">4.9★</div>
        <div class="stat-label">Avaliação média</div>
      </div>
      <div>
        <div class="stat-num">8K+</div>
        <div class="stat-label">Clientes satisfeitos</div>
      </div>
    </div>
  </div>
  <div class="hero-right">
    <div class="hero-img-wrapper">
      <div class="hero-img-placeholder">
        <div class="barber-pole-deco">
          <div class="pole-cap"></div>
          <div class="pole-wrap"><div class="pole-stripe"></div></div>
          <div class="pole-cap"></div>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="ornament">✦ &nbsp;&nbsp; ✦ &nbsp;&nbsp; ✦</div>

<!-- SOBRE -->
<section id="sobre">
  <div class="about-text-side">
    <div class="about-label">Nossa História</div>
    <div class="section-line"></div>
    <h2 class="section-title">Mais que uma barbearia,<br>um <em>ritual</em></h2>
    <p class="about-text">
      Fundada em 2008 no coração de Curitiba, a Navalha & Arte nasceu da paixão pelos ofícios clássicos da barbearia. Ao longo de mais de uma década, combinamos técnicas tradicionais com as tendências contemporâneas para oferecer uma experiência única de cuidado masculino.
    </p>
    <p class="about-text">
      Cada visita é pensada nos mínimos detalhes — do atendimento personalizado ao ambiente acolhedor, para que você saia não apenas bem aparado, mas renovado.
    </p>
    <div class="about-features">
      <div class="feat-item">
        <div class="feat-icon">✂</div>
        <div class="feat-text">
          <strong>Cortes Precisos</strong>
          <span>Técnica e detalhe em cada fio</span>
        </div>
      </div>
      <div class="feat-item">
        <div class="feat-icon">🪒</div>
        <div class="feat-text">
          <strong>Barba Clássica</strong>
          <span>Navalha quente com toalha</span>
        </div>
      </div>
      <div class="feat-item">
        <div class="feat-icon">🏆</div>
        <div class="feat-text">
          <strong>Premiados</strong>
          <span>Melhor barbearia do Paraná</span>
        </div>
      </div>
      <div class="feat-item">
        <div class="feat-icon">🌿</div>
        <div class="feat-text">
          <strong>Produtos Premium</strong>
          <span>Linha exclusiva de grooming</span>
        </div>
      </div>
    </div>
  </div>
  <div class="about-image-side">
    <div class="img-frame">
      <div class="img-frame-inner">N&A</div>
      <div class="img-frame-deco"></div>
    </div>
  </div>
</section>

<!-- SERVIÇOS -->
<section id="servicos">
  <div class="section-header">
    <div class="section-label">O que oferecemos</div>
    <div class="section-line-center"></div>
    <h2 class="section-title" style="color:var(--white)">Nossos <em>Serviços</em></h2>
  </div>
  <div class="services-grid">
    <div class="service-card">
      <span class="service-icon">✂</span>
      <div class="service-name">Corte Clássico</div>
      <p class="service-desc">Tesoura ou máquina, com acabamento impecável e styling incluídos. O clássico que nunca sai de moda.</p>
      <div class="service-price">R$ 65 <span>/ 45 min</span></div>
    </div>
    <div class="service-card">
      <span class="service-icon">🪒</span>
      <div class="service-name">Barba Completa</div>
      <p class="service-desc">Modelagem, navalha quente, toalha aromática e finalização com bálsamo artesanal.</p>
      <div class="service-price">R$ 55 <span>/ 40 min</span></div>
    </div>
    <div class="service-card">
      <span class="service-icon">👑</span>
      <div class="service-name">Corte + Barba</div>
      <p class="service-desc">A experiência completa: corte preciso e barba clássica em uma única visita.</p>
      <div class="service-price">R$ 110 <span>/ 75 min</span></div>
    </div>
    <div class="service-card">
      <span class="service-icon">💆</span>
      <div class="service-name">Ritual Premium</div>
      <p class="service-desc">Inclui corte, barba, hidratação capilar, massagem craniana e brace de ombros.</p>
      <div class="service-price">R$ 170 <span>/ 120 min</span></div>
    </div>
    <div class="service-card">
      <span class="service-icon">🎨</span>
      <div class="service-name">Coloração</div>
      <p class="service-desc">Tingimento de cabelo ou barba com produtos sem amônia e resultado natural.</p>
      <div class="service-price">R$ 90 <span>/ 60 min</span></div>
    </div>
    <div class="service-card">
      <span class="service-icon">✨</span>
      <div class="service-name">Progressiva Capilar</div>
      <p class="service-desc">Redução de volume e disciplina dos fios com tratamento nutritivo profissional.</p>
      <div class="service-price">R$ 150 <span>/ 90 min</span></div>
    </div>
  </div>
</section>

<!-- BARBEIROS -->
<section id="barbeiros">
  <div class="section-header" style="text-align:center;margin-bottom:3.5rem;">
    <div class="section-label">Conheça a equipe</div>
    <div class="section-line-center"></div>
    <h2 class="section-title" style="color:var(--white)">Nossos <em>Barbeiros</em></h2>
  </div>
  <div class="barbers-grid">
    <div class="barber-card">
      <div class="barber-photo">✂</div>
      <div class="barber-info">
        <div class="barber-name">Ricardo Alves</div>
        <div class="barber-role">Mestre Barbeiro — Fundador</div>
        <p class="barber-bio">Com 20 anos de profissão, Ricardo é especialista em cortes clássicos e barba com navalha. Formado em Barcelona e São Paulo.</p>
      </div>
    </div>
    <div class="barber-card">
      <div class="barber-photo">🪒</div>
      <div class="barber-info">
        <div class="barber-name">Bruno Martins</div>
        <div class="barber-role">Senior Barber</div>
        <p class="barber-bio">Referência em degradês e cortes modernos. Vencedor do campeonato estadual de barbearia 2022 e 2023.</p>
      </div>
    </div>
    <div class="barber-card">
      <div class="barber-photo">💈</div>
      <div class="barber-info">
        <div class="barber-name">Thiago Souza</div>
        <div class="barber-role">Barber & Colorista</div>
        <p class="barber-bio">Especialista em coloração masculina e tratamentos capilares. Atualização constante nas principais tendências internacionais.</p>
      </div>
    </div>
  </div>
</section>

<!-- DEPOIMENTOS -->
<section id="depoimentos">
  <div class="section-header">
    <div class="section-label" style="color:var(--gold)">O que dizem nossos clientes</div>
    <div class="section-line-center" style="margin-left:0; text-align:left;"></div>
    <h2 class="section-title">Satisfação que <em>fala</em></h2>
  </div>
  <div class="testimonials-grid">
    <div class="testimonial-card">
      <div class="stars">★★★★★</div>
      <p class="testimonial-text">Melhor barbearia que já fui em toda minha vida. O Ricardo tem uma precisão de corte que eu nunca vi antes. Atendimento impecável do início ao fim.</p>
      <div class="testimonial-author">
        <div class="author-avatar">MF</div>
        <div>
          <div class="author-name">Marcos Ferreira</div>
          <div class="author-since">Cliente desde 2015</div>
        </div>
      </div>
    </div>
    <div class="testimonial-card">
      <div class="stars">★★★★★</div>
      <p class="testimonial-text">O ritual premium é simplesmente transformador. Massagem, toalha quente, o cheiro dos produtos... você se sente em outro mundo. Vale cada centavo.</p>
      <div class="testimonial-author">
        <div class="author-avatar">DP</div>
        <div>
          <div class="author-name">Diego Pereira</div>
          <div class="author-since">Cliente desde 2019</div>
        </div>
      </div>
    </div>
    <div class="testimonial-card">
      <div class="stars">★★★★★</div>
      <p class="testimonial-text">Fui indicado por um amigo e não me arrependo. O Bruno acertou em cheio no degradê que pedi. Ambiente incrível, preços justos. Já sou fiel!</p>
      <div class="testimonial-author">
        <div class="author-avatar">LC</div>
        <div>
          <div class="author-name">Lucas Carvalho</div>
          <div class="author-since">Cliente desde 2023</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- AGENDAMENTO -->
<section id="agendamento">
  <div>
    <div class="booking-label">Reservar agora</div>
    <div class="section-line" style="background:var(--brown);opacity:0.4;"></div>
    <h2 class="section-title">Agende seu <em style="color:var(--brown-mid);">horário</em></h2>
    <p class="booking-text">Escolha o serviço, o barbeiro e o melhor horário para você. Confirmação instantânea por WhatsApp.</p>
    <form class="booking-form" onsubmit="handleBooking(event)">
      <div class="form-row">
        <div class="form-group">
          <label>Nome Completo</label>
          <input type="text" placeholder="Seu nome" required />
        </div>
        <div class="form-group">
          <label>WhatsApp</label>
          <input type="tel" placeholder="(41) 9xxxx-xxxx" required />
        </div>
      </div>
      <div class="form-row">
        <div class="form-group">
          <label>Serviço</label>
          <select required>
            <option value="">Selecione...</option>
            <option>Corte Clássico — R$ 65</option>
            <option>Barba Completa — R$ 55</option>
            <option>Corte + Barba — R$ 110</option>
            <option>Ritual Premium — R$ 170</option>
            <option>Coloração — R$ 90</option>
          </select>
        </div>
        <div class="form-group">
          <label>Barbeiro</label>
          <select required>
            <option value="">Selecione...</option>
            <option>Ricardo Alves</option>
            <option>Bruno Martins</option>
            <option>Thiago Souza</option>
            <option>Sem preferência</option>
          </select>
        </div>
      </div>
      <div class="form-row">
        <div class="form-group">
          <label>Data</label>
          <input type="date" required />
        </div>
        <div class="form-group">
          <label>Horário</label>
          <select required>
            <option value="">Selecione...</option>
            <option>09:00</option><option>09:45</option>
            <option>10:30</option><option>11:15</option>
            <option>13:00</option><option>13:45</option>
            <option>14:30</option><option>15:15</option>
            <option>16:00</option><option>16:45</option>
            <option>17:30</option><option>18:15</option>
          </select>
        </div>
      </div>
      <button type="submit" class="btn-book">Confirmar Agendamento</button>
    </form>
  </div>
  <div class="booking-aside">
    <div class="info-block">
      <div class="info-icon">📍</div>
      <div>
        <div class="info-title">Endereço</div>
        <div class="info-detail">Rua XV de Novembro, 823<br>Centro — Curitiba / PR</div>
      </div>
    </div>
    <div class="info-block">
      <div class="info-icon">🕐</div>
      <div>
        <div class="info-title">Horário de Funcionamento</div>
        <div class="info-detail">
          Segunda a Sexta: 09h às 19h<br>
          Sábado: 09h às 17h<br>
          Domingo: Fechado
        </div>
      </div>
    </div>
    <div class="info-block">
      <div class="info-icon">📱</div>
      <div>
        <div class="info-title">Contato</div>
        <div class="info-detail">
          (41) 3322-0808<br>
          contato@navalhaearte.com.br
        </div>
      </div>
    </div>
    <div class="info-block">
      <div class="info-icon">🅿</div>
      <div>
        <div class="info-title">Estacionamento</div>
        <div class="info-detail">Convênio com o estacionamento<br>Garagem XV — 2h gratuitas</div>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div>
    <div class="footer-brand">Navalha<span> & Arte</span></div>
    <p class="footer-tagline">Tradição, precisão e cuidado em cada visita. Sua melhor versão começa aqui.</p>
    <div class="social-links">
      <a href="#" class="social-btn" title="Instagram">in</a>
      <a href="#" class="social-btn" title="Facebook">fb</a>
      <a href="#" class="social-btn" title="WhatsApp">wp</a>
      <a href="#" class="social-btn" title="YouTube">yt</a>
    </div>
  </div>
  <div class="footer-col">
    <h4>Serviços</h4>
    <ul>
      <li><a href="#">Corte Clássico</a></li>
      <li><a href="#">Barba Completa</a></li>
      <li><a href="#">Corte + Barba</a></li>
      <li><a href="#">Ritual Premium</a></li>
      <li><a href="#">Coloração</a></li>
    </ul>
  </div>
  <div class="footer-col">
    <h4>A Barbearia</h4>
    <ul>
      <li><a href="#">Nossa História</a></li>
      <li><a href="#">A Equipe</a></li>
      <li><a href="#">Depoimentos</a></li>
      <li><a href="#">Premiações</a></li>
      <li><a href="#">Loja Online</a></li>
    </ul>
  </div>
  <div class="footer-col">
    <h4>Atendimento</h4>
    <ul>
      <li><a href="#">Agendamento</a></li>
      <li><a href="#">Planos Mensais</a></li>
      <li><a href="#">Vale-Presente</a></li>
      <li><a href="#">Política de Cancelamento</a></li>
      <li><a href="#">Contato</a></li>
    </ul>
  </div>
</footer>
<div class="footer-bottom">
  <p>© 2024 Navalha & Arte. Todos os direitos reservados.</p>
  <p>Desenvolvido com ✦ em Curitiba</p>
</div>

<script>
  function handleBooking(e) {
    e.preventDefault();
    alert('Agendamento recebido! Em breve você receberá a confirmação via WhatsApp. Obrigado!');
    e.target.reset();
  }
</script>

</body>
</html>
