<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <title>SaaS — Build. Scale. Simplify.</title>
  <meta
    name="description"
    content="SaaS is a modern platform helping teams build, manage and scale better."
  />

  <style>
    :root {
      --bg: #ffffff;
      --surface: #f7f8fa;
      --surface-2: #eef1f5;
      --text: #101828;
      --muted: #667085;
      --border: #e4e7ec;
      --primary: #111827;
      --primary-hover: #273244;
      --white: #ffffff;
      --success: #12b76a;
      --radius: 18px;
      --shadow: 0 20px 60px rgba(16, 24, 40, 0.10);
      --max-width: 1180px;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family:
        Inter, ui-sans-serif, system-ui, -apple-system,
        BlinkMacSystemFont, "Segoe UI", sans-serif;
      background: var(--bg);
      color: var(--text);
      line-height: 1.6;
      overflow-x: hidden;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    button {
      font: inherit;
    }

    .container {
      width: min(100% - 40px, var(--max-width));
      margin-inline: auto;
    }

    /* ---------------- NAVBAR ---------------- */

    .navbar {
      position: sticky;
      top: 0;
      z-index: 1000;
      background: rgba(255, 255, 255, 0.88);
      backdrop-filter: blur(18px);
      border-bottom: 1px solid rgba(228, 231, 236, 0.75);
    }

    .nav-inner {
      height: 76px;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .logo {
      display: flex;
      align-items: center;
      gap: 10px;
      font-size: 22px;
      font-weight: 800;
      letter-spacing: -0.04em;
    }

    .logo-mark {
      width: 34px;
      height: 34px;
      display: grid;
      place-items: center;
      border-radius: 10px;
      color: white;
      background: #111827;
      font-size: 15px;
      font-weight: 800;
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 34px;
      color: #475467;
      font-size: 14px;
      font-weight: 600;
    }

    .nav-links a {
      transition: color 0.2s ease;
    }

    .nav-links a:hover {
      color: var(--text);
    }

    .nav-actions {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .login {
      color: #475467;
      font-size: 14px;
      font-weight: 600;
    }

    .btn {
      border: 0;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 9px;
      min-height: 44px;
      padding: 0 19px;
      border-radius: 11px;
      font-size: 14px;
      font-weight: 700;
      transition:
        transform 0.2s ease,
        background 0.2s ease,
        box-shadow 0.2s ease;
    }

    .btn:hover {
      transform: translateY(-2px);
    }

    .btn-primary {
      background: var(--primary);
      color: var(--white);
      box-shadow: 0 5px 15px rgba(16, 24, 40, 0.12);
    }

    .btn-primary:hover {
      background: var(--primary-hover);
    }

    .btn-secondary {
      background: white;
      border: 1px solid var(--border);
      color: var(--text);
    }

    .mobile-menu-btn {
      display: none;
      width: 42px;
      height: 42px;
      border: 1px solid var(--border);
      border-radius: 10px;
      background: white;
      cursor: pointer;
      font-size: 20px;
    }

    /* ---------------- HERO ---------------- */

    .hero {
      position: relative;
      padding: 100px 0 80px;
      overflow: hidden;
    }

    .hero::before {
      content: "";
      position: absolute;
      width: 600px;
      height: 600px;
      border-radius: 50%;
      background: #eef2ff;
      filter: blur(80px);
      opacity: 0.7;
      top: -300px;
      left: 50%;
      transform: translateX(-50%);
      pointer-events: none;
    }

    .hero-content {
      position: relative;
      max-width: 900px;
      margin: auto;
      text-align: center;
    }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 7px 12px;
      border: 1px solid var(--border);
      background: rgba(255, 255, 255, 0.8);
      border-radius: 999px;
      color: #475467;
      font-size: 12px;
      font-weight: 700;
      margin-bottom: 25px;
    }

    .eyebrow-dot {
      width: 7px;
      height: 7px;
      border-radius: 50%;
      background: var(--success);
    }

    .hero h1 {
      font-size: clamp(48px, 7vw, 78px);
      line-height: 0.98;
      letter-spacing: -0.065em;
      font-weight: 800;
      max-width: 850px;
      margin: auto;
    }

    .hero h1 span {
      color: #667085;
    }

    .hero-description {
      max-width: 650px;
      margin: 28px auto 0;
      color: var(--muted);
      font-size: 18px;
      line-height: 1.7;
    }

    .hero-buttons {
      display: flex;
      justify-content: center;
      gap: 12px;
      margin-top: 34px;
    }

    .hero-note {
      margin-top: 17px;
      color: #98a2b3;
      font-size: 12px;
    }

    /* ---------------- DASHBOARD ---------------- */

    .dashboard-wrap {
      margin-top: 70px;
      perspective: 1000px;
    }

    .dashboard {
      position: relative;
      overflow: hidden;
      background: #101828;
      border-radius: 24px;
      border: 7px solid #f0f2f5;
      box-shadow: 0 30px 90px rgba(16, 24, 40, 0.20);
      transform: rotateX(2deg);
    }

    .dashboard-top {
      height: 52px;
      display: flex;
      align-items: center;
      gap: 7px;
      padding: 0 18px;
      background: #182230;
      border-bottom: 1px solid #344054;
    }

    .window-dot {
      width: 9px;
      height: 9px;
      border-radius: 50%;
      background: #667085;
    }

    .dashboard-body {
      display: grid;
      grid-template-columns: 190px 1fr;
      min-height: 460px;
      background: #f8fafc;
    }

    .sidebar {
      background: #ffffff;
      border-right: 1px solid var(--border);
      padding: 22px 15px;
    }

    .sidebar-brand {
      font-weight: 800;
      margin-bottom: 28px;
      padding: 0 10px;
    }

    .side-item {
      padding: 10px;
      border-radius: 8px;
      color: #667085;
      font-size: 13px;
      margin-bottom: 5px;
    }

    .side-item.active {
      color: #101828;
      background: #f2f4f7;
      font-weight: 700;
    }

    .main-panel {
      padding: 30px;
    }

    .panel-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 25px;
    }

    .panel-header h3 {
      font-size: 21px;
      letter-spacing: -0.03em;
    }

    .mini-date {
      color: #667085;
      font-size: 12px;
    }

    .metric-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 15px;
    }

    .metric {
      background: white;
      border: 1px solid var(--border);
      border-radius: 13px;
      padding: 18px;
    }

    .metric-label {
      color: #667085;
      font-size: 12px;
    }

    .metric-value {
      margin-top: 7px;
      font-size: 25px;
      font-weight: 800;
      letter-spacing: -0.04em;
    }

    .metric-growth {
      margin-top: 7px;
      color: var(--success);
      font-size: 11px;
      font-weight: 700;
    }

    .chart-card {
      margin-top: 15px;
      background: white;
      border: 1px solid var(--border);
      border-radius: 13px;
      padding: 20px;
    }

    .chart-title {
      font-size: 13px;
      font-weight: 700;
    }

    .chart {
      height: 190px;
      margin-top: 20px;
      display: flex;
      align-items: end;
      gap: 9px;
    }

    .bar {
      flex: 1;
      border-radius: 6px 6px 2px 2px;
      background: #d0d5dd;
      min-height: 25px;
      transition: height 0.6s ease;
    }

    .bar.highlight {
      background: #101828;
    }

    /* ---------------- TRUST ---------------- */

    .trust {
      padding: 55px 0;
      border-top: 1px solid var(--border);
      border-bottom: 1px solid var(--border);
    }

    .trust p {
      text-align: center;
      color: #98a2b3;
      font-size: 12px;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 0.12em;
    }

    .logos {
      margin-top: 25px;
      display: flex;
      align-items: center;
      justify-content: space-around;
      gap: 30px;
      color: #667085;
      font-weight: 800;
      font-size: 17px;
    }

    /* ---------------- SECTIONS ---------------- */

    section {
      scroll-margin-top: 90px;
    }

    .section {
      padding: 110px 0;
    }

    .section-header {
      max-width: 650px;
      margin-bottom: 55px;
    }

    .section-label {
      color: #667085;
      font-size: 12px;
      font-weight: 800;
      text-transform: uppercase;
      letter-spacing: 0.12em;
      margin-bottom: 15px;
    }

    .section h2 {
      font-size: clamp(36px, 5vw, 54px);
      line-height: 1.05;
      letter-spacing: -0.055em;
    }

    .section-header p {
      color: var(--muted);
      margin-top: 20px;
      font-size: 17px;
    }

    /* ---------------- FEATURES ---------------- */

    .features {
      background: var(--surface);
    }

    .feature-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 18px;
    }

    .feature-card {
      background: white;
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 30px;
      transition:
        transform 0.25s ease,
        box-shadow 0.25s ease;
    }

    .feature-card:hover {
      transform: translateY(-5px);
      box-shadow: var(--shadow);
    }

    .feature-icon {
      width: 45px;
      height: 45px;
      display: grid;
      place-items: center;
      border-radius: 12px;
      background: #f2f4f7;
      margin-bottom: 25px;
      font-size: 20px;
    }

    .feature-card h3 {
      font-size: 18px;
      letter-spacing: -0.02em;
    }

    .feature-card p {
      color: var(--muted);
      font-size: 14px;
      margin-top: 10px;
      line-height: 1.7;
    }

    /* ---------------- SHOWCASE ---------------- */

    .showcase {
      display: grid;
      grid-template-columns: 0.9fr 1.1fr;
      align-items: center;
      gap: 80px;
    }

    .showcase-text h2 {
      font-size: clamp(36px, 5vw, 55px);
      line-height: 1.05;
      letter-spacing: -0.055em;
    }

    .showcase-text p {
      color: var(--muted);
      margin-top: 20px;
      font-size: 16px;
    }

    .check-list {
      margin-top: 28px;
      display: grid;
      gap: 14px;
    }

    .check {
      display: flex;
      align-items: center;
      gap: 12px;
      color: #344054;
      font-size: 14px;
      font-weight: 600;
    }

    .check span {
      width: 21px;
      height: 21px;
      display: grid;
      place-items: center;
      background: #ecfdf3;
      color: #039855;
      border-radius: 50%;
      font-size: 12px;
    }

    .product-card {
      background: #101828;
      border-radius: 25px;
      padding: 24px;
      box-shadow: var(--shadow);
    }

    .product-window {
      background: white;
      border-radius: 15px;
      overflow: hidden;
    }

    .product-window-top {
      padding: 16px;
      border-bottom: 1px solid var(--border);
      display: flex;
      justify-content: space-between;
      font-size: 12px;
      font-weight: 700;
    }

    .product-content {
      padding: 25px;
    }

    .product-row {
      display: grid;
      grid-template-columns: 1fr 100px 100px;
      gap: 15px;
      align-items: center;
      padding: 15px 0;
      border-bottom: 1px solid #f2f4f7;
      font-size: 12px;
    }

    .product-user {
      display: flex;
      align-items: center;
      gap: 10px;
      font-weight: 700;
    }

    .avatar {
      width: 30px;
      height: 30px;
      display: grid;
      place-items: center;
      border-radius: 50%;
      background: #eaecf0;
      font-size: 11px;
    }

    .status {
      width: fit-content;
      padding: 5px 9px;
      border-radius: 999px;
      background: #ecfdf3;
      color: #027a48;
      font-weight: 700;
    }

    /* ---------------- TESTIMONIAL ---------------- */

    .testimonial {
      background: var(--surface);
      text-align: center;
    }

    .quote {
      max-width: 850px;
      margin: auto;
      font-size: clamp(25px, 4vw, 39px);
      line-height: 1.25;
      letter-spacing: -0.04em;
      font-weight: 700;
    }

    .quote-author {
      margin-top: 28px;
      color: #667085;
      font-size: 13px;
    }

    /* ---------------- CTA ---------------- */

    .cta {
      padding: 110px 0;
    }

    .cta-box {
      position: relative;
      overflow: hidden;
      background: #101828;
      color: white;
      border-radius: 26px;
      padding: 80px 30px;
      text-align: center;
    }

    .cta-box::before {
      content: "";
      position: absolute;
      width: 350px;
      height: 350px;
      border-radius: 50%;
      border: 1px solid #344054;
      top: -170px;
      left: 50%;
      transform: translateX(-50%);
    }

    .cta-box h2 {
      position: relative;
      font-size: clamp(35px, 5vw, 55px);
      letter-spacing: -0.055em;
      line-height: 1;
    }

    .cta-box p {
      position: relative;
      max-width: 560px;
      margin: 20px auto 30px;
      color: #98a2b3;
    }

    .cta-box .btn {
      position: relative;
      background: white;
      color: #101828;
    }

    /* ---------------- FOOTER ---------------- */

    footer {
      border-top: 1px solid var(--border);
      padding: 65px 0 30px;
    }

    .footer-grid {
      display: grid;
      grid-template-columns: 1.5fr repeat(3, 1fr);
      gap: 50px;
    }

    .footer-brand p {
      max-width: 300px;
      margin-top: 15px;
      color: var(--muted);
      font-size: 13px;
    }

    .footer-column h4 {
      font-size: 13px;
      margin-bottom: 18px;
    }

    .footer-column a {
      display: block;
      color: #667085;
      font-size: 13px;
      margin-bottom: 11px;
    }

    .footer-column a:hover {
      color: var(--text);
    }

    .copyright {
      border-top: 1px solid var(--border);
      margin-top: 50px;
      padding-top: 25px;
      color: #98a2b3;
      font-size: 12px;
      display: flex;
      justify-content: space-between;
    }

    /* ---------------- ANIMATION ---------------- */

    .reveal {
      opacity: 0;
      transform: translateY(20px);
      transition:
        opacity 0.7s ease,
        transform 0.7s ease;
    }

    .reveal.visible {
      opacity: 1;
      transform: translateY(0);
    }

    /* ---------------- MOBILE ---------------- */

    @media (max-width: 850px) {
      .nav-links,
      .nav-actions {
        display: none;
      }

      .mobile-menu-btn {
        display: block;
      }

      .nav-inner.menu-open .nav-links {
        display: flex;
        position: absolute;
        top: 76px;
        left: 20px;
        right: 20px;
        padding: 20px;
        flex-direction: column;
        align-items: flex-start;
        gap: 0;
        background: white;
        border: 1px solid var(--border);
        border-radius: 14px;
        box-shadow: var(--shadow);
      }

      .nav-inner.menu-open .nav-links a {
        width: 100%;
        padding: 13px 5px;
      }

      .hero {
        padding-top: 75px;
      }

      .hero-description {
        font-size: 16px;
      }

      .dashboard-body {
        grid-template-columns: 1fr;
      }

      .sidebar {
        display: none;
      }

      .feature-grid {
        grid-template-columns: 1fr;
      }

      .showcase {
        grid-template-columns: 1fr;
        gap: 45px;
      }

      .footer-grid {
        grid-template-columns: 1fr 1fr;
      }
    }

    @media (max-width: 600px) {
      .container {
        width: min(100% - 28px, var(--max-width));
      }

      .hero {
        padding: 60px 0;
      }

      .hero h1 {
        font-size: 47px;
      }

      .hero-buttons {
        flex-direction: column;
      }

      .hero-buttons .btn {
        width: 100%;
      }

      .dashboard-wrap {
        margin-top: 45px;
      }

      .dashboard {
        border-width: 4px;
        border-radius: 17px;
      }

      .main-panel {
        padding: 17px;
      }

      .metric-grid {
        grid-template-columns: 1fr;
      }

      .metric {
        padding: 14px;
      }

      .chart {
        height: 140px;
      }

      .logos {
        flex-wrap: wrap;
        justify-content: center;
        gap: 20px 30px;
        font-size: 14px;
      }

      .section {
        padding: 75px 0;
      }

      .section-header {
        margin-bottom: 35px;
      }

      .feature-card {
        padding: 23px;
      }

      .product-card {
        padding: 12px;
      }

      .product-content {
        padding: 15px;
      }

      .product-row {
        grid-template-columns: 1fr 70px;
      }

      .product-row > :last-child {
        display: none;
      }

      .cta {
        padding: 75px 0;
      }

      .cta-box {
        padding: 60px 22px;
        border-radius: 20px;
      }

      .footer-grid {
        grid-template-columns: 1fr 1fr;
        gap: 35px 20px;
      }

      .footer-brand {
        grid-column: 1 / -1;
      }

      .copyright {
        flex-direction: column;
        gap: 7px;
      }
    }
  </style>
</head>

<body>

  <!-- NAVBAR -->
  <header class="navbar">
    <div class="container nav-inner" id="navInner">

      <a href="#" class="logo">
        <span class="logo-mark">S</span>
        SaaS
      </a>

      <nav class="nav-links">
        <a href="#product">Product</a>
        <a href="#solutions">Solutions</a>
        <a href="#security">Security</a>
        <a href="#customers">Customers</a>
        <a href="#pricing">Pricing</a>
      </nav>

      <div class="nav-actions">
        <a href="#" class="login">Log in</a>
        <a href="#contact" class="btn btn-primary">Get started →</a>
      </div>

      <button class="mobile-menu-btn" id="menuBtn" aria-label="Open menu">
        ☰
      </button>

    </div>
  </header>


  <!-- HERO -->
  <main>

    <section class="hero">
      <div class="container">

        <div class="hero-content reveal">

          <div class="eyebrow">
            <span class="eyebrow-dot"></span>
            The smarter way to build and scale
          </div>

          <h1>
            Everything your team needs to
            <span>move forward.</span>
          </h1>

          <p class="hero-description">
            SaaS gives modern teams one powerful platform to manage
            their workflows, understand their business, and grow with confidence.
          </p>

          <div class="hero-buttons">
            <a href="#contact" class="btn btn-primary">
              Start for free →
            </a>

            <a href="#product" class="btn btn-secondary">
              Explore product
            </a>
          </div>

          <div class="hero-note">
            No credit card required · Set up in minutes
          </div>

        </div>


        <!-- DASHBOARD MOCKUP -->
        <div class="dashboard-wrap reveal">

          <div class="dashboard">

            <div class="dashboard-top">
              <span class="window-dot"></span>
              <span class="window-dot"></span>
              <span class="window-dot"></span>
            </div>

            <div class="dashboard-body">

              <aside class="sidebar">
                <div class="sidebar-brand">SaaS</div>

                <div class="side-item active">Overview</div>
                <div class="side-item">Analytics</div>
                <div class="side-item">Projects</div>
                <div class="side-item">Customers</div>
                <div class="side-item">Team</div>
                <div class="side-item">Settings</div>

         
