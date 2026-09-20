# <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>ServerVault — Minecraft & Discord Premade Servers</title>

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: Arial, Helvetica, sans-serif;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      background: #050505;
      color: white;
      overflow-x: hidden;
    }

    /* Background */
    body::before {
      content: "";
      position: fixed;
      width: 500px;
      height: 500px;
      background: #5865f2;
      filter: blur(180px);
      opacity: 0.18;
      top: -150px;
      left: -150px;
      z-index: -1;
    }

    body::after {
      content: "";
      position: fixed;
      width: 400px;
      height: 400px;
      background: #7c3aed;
      filter: blur(180px);
      opacity: 0.15;
      bottom: -100px;
      right: -100px;
      z-index: -1;
    }

    /* Navbar */
    nav {
      position: fixed;
      top: 15px;
      left: 50%;
      transform: translateX(-50%);
      width: 92%;
      max-width: 1100px;
      padding: 15px 22px;

      display: flex;
      justify-content: space-between;
      align-items: center;

      background: rgba(20, 20, 20, 0.65);
      border: 1px solid rgba(255,255,255,0.1);
      backdrop-filter: blur(20px);
      border-radius: 20px;

      z-index: 1000;
    }

    .logo {
      font-size: 21px;
      font-weight: 800;
      letter-spacing: 1px;
    }

    .logo span {
      color: #7289da;
    }

    nav a {
      color: #ccc;
      text-decoration: none;
      margin-left: 22px;
      font-size: 14px;
      transition: 0.3s;
    }

    nav a:hover {
      color: white;
    }

    .nav-btn {
      background: #5865f2;
      padding: 10px 16px;
      border-radius: 12px;
      color: white !important;
      font-weight: bold;
    }

    /* Hero */
    .hero {
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      padding: 120px 20px 60px;
    }

    .hero-content {
      max-width: 850px;
    }

    .badge {
      display: inline-block;
      padding: 8px 14px;
      border: 1px solid rgba(255,255,255,0.12);
      background: rgba(255,255,255,0.05);
      border-radius: 50px;
      font-size: 13px;
      color: #aaa;
      margin-bottom: 25px;
    }

    h1 {
      font-size: clamp(45px, 8vw, 90px);
      line-height: 0.95;
      font-weight: 900;
      letter-spacing: -4px;
    }

    h1 span {
      background: linear-gradient(90deg, #7289da, #9b7cff, #5865f2);
      -webkit-background-clip: text;
      color: transparent;
    }

    .hero p {
      max-width: 650px;
      margin: 28px auto;
      color: #999;
      font-size: 17px;
      line-height: 1.7;
    }

    .buttons {
      display: flex;
      justify-content: center;
      gap: 14px;
      flex-wrap: wrap;
    }

    .btn {
      text-decoration: none;
      padding: 15px 24px;
      border-radius: 14px;
      font-weight: bold;
      transition: 0.25s;
      display: inline-block;
    }

    .discord {
      background: #5865f2;
      color: white;
      box-shadow: 0 10px 35px rgba(88,101,242,0.3);
    }

    .discord:hover {
      transform: translateY(-4px);
      box-shadow: 0 15px 40px rgba(88,101,242,0.45);
    }

    .explore {
      color: white;
      border: 1px solid #333;
      background: rgba(255,255,255,0.04);
    }

    .explore:hover {
      background: rgba(255,255,255,0.09);
    }

    /* Sections */
    section {
      padding: 90px 20px;
      max-width: 1150px;
      margin: auto;
    }

    .section-title {
      text-align: center;
      margin-bottom: 50px;
    }

    .section-title h2 {
      font-size: 42px;
      margin-bottom: 12px;
    }

    .section-title p {
      color: #888;
    }

    /* Cards */
    .cards {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 22px;
    }

    .card {
      padding: 32px;
      border-radius: 24px;

      background: linear-gradient(
        145deg,
        rgba(255,255,255,0.08),
        rgba(255,255,255,0.025)
      );

      border: 1px solid rgba(255,255,255,0.1);
      backdrop-filter: blur(15px);

      transition: 0.3s;
    }

    .card:hover {
      transform: translateY(-8px);
      border-color: rgba(114,137,218,0.5);
    }

    .icon {
      font-size: 40px;
      margin-bottom: 20px;
    }

    .card h3 {
      font-size: 25px;
      margin-bottom: 12px;
    }

    .card p {
      color: #999;
      line-height: 1.7;
      margin-bottom: 22px;
    }

    .features {
      list-style: none;
    }

    .features li {
      color: #bbb;
      margin: 10px 0;
    }

    .features li::before {
      content: "✓";
      color: #7289da;
      margin-right: 10px;
      font-weight: bold;
    }

    /* Info */
    .info-box {
      padding: 40px;
      border-radius: 25px;
      text-align: center;

      background: rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.1);
    }

    .info-box h2 {
      font-size: 35px;
      margin-bottom: 15px;
    }

    .info-box p {
      max-width: 700px;
      margin: auto;
      color: #999;
      line-height: 1.8;
    }

    /* CTA */
    .cta {
      text-align: center;
    }

    .cta-box {
      padding: 70px 25px;
      border-radius: 30px;
      background:
        radial-gradient(circle at center, rgba(88,101,242,0.22), transparent 60%),
        rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.1);
    }

    .cta h2 {
      font-size: clamp(35px, 6vw, 60px);
      margin-bottom: 18px;
    }

    .cta p {
      color: #999;
      margin-bottom: 30px;
    }

    /* Footer */
    footer {
      text-align: center;
      padding: 35px 20px;
      color: #666;
      border-top: 1px solid rgba(255,255,255,0.07);
    }

    footer strong {
      color: #aaa;
    }

    /* Mobile */
    @media (max-width: 700px) {
      nav {
        padding: 13px 15px;
      }

      nav .links {
        display: none;
      }

      .cards {
        grid-template-columns: 1fr;
      }

      h1 {
        letter-spacing: -2px;
      }

      section {
        padding: 65px 18px;
      }
    }
  </style>
</head>

<body>

  <!-- NAVBAR -->
  <nav>
    <div class="logo">
      Server<span>Vault</span>
    </div>

    <div class="links">
      <a href="#home">Home</a>
      <a href="#servers">Servers</a>
      <a href="#about">About</a>
      <a
        href="https://discord.gg/p8E5PwT5q"
        target="_blank"
        class="nav-btn">
        Discord
      </a>
    </div>
  </nav>


  <!-- HERO -->
  <main id="home" class="hero">
    <div class="hero-content">

      <div class="badge">
        ⚡ Premium Premade Servers
      </div>

      <h1>
        Build Less.<br>
        <span>Play More.</span>
      </h1>

      <p>
        Get high-quality premade Minecraft and Discord servers
        designed to help you launch your community faster.
        Ready-to-use setups, clean designs and powerful features.
      </p>

      <div class="buttons">

        <a
          href="https://discord.gg/p8E5PwT5q"
          target="_blank"
          class="btn discord">
          Join Our Discord
        </a>

        <a href="#servers" class="btn explore">
          Explore Servers
        </a>

      </div>

    </div>
  </main>


  <!-- SERVERS -->
  <section id="servers">

    <div class="section-title">
      <h2>What We Provide</h2>
      <p>Premade setups for Minecraft and Discord communities.</p>
    </div>

    <div class="cards">

      <!-- Minecraft -->
      <div class="card">

        <div class="icon">⛏️</div>

        <h3>Minecraft Servers</h3>

        <p>
          Ready-made Minecraft server setups that can help
          you launch your server without starting everything
          from scratch.
        </p>

        <ul class="features">
          <li>Premade server setups</li>
          <li>PvP & Survival setups</li>
          <li>Plugins & configurations</li>
          <li>Custom server designs</li>
          <li>Easy setup</li>
        </ul>

      </div>


      <!-- Discord -->
      <div class="card">

        <div class="icon">💬</div>

        <h3>Discord Servers</h3>

        <p>
          Professionally organized Discord server templates
          for gaming communities, Minecraft servers and more.
        </p>

        <ul class="features">
          <li>Premade channel layouts</li>
          <li>Staff & support sections</li>
          <li>Ticket system structure</li>
          <li>Community-ready design</li>
          <li>Clean permissions setup</li>
        </ul>

      </div>

    </div>
  </section>


  <!-- ABOUT -->
  <section id="about">

    <div class="info-box">

      <h2>Why Choose Us?</h2>

      <p>
        Starting a Minecraft or Discord community takes time.
        Our premade servers give you a strong starting point
        so you can focus on your community instead of spending
        hours creating everything from zero.
      </p>

    </div>

  </section>


  <!-- CTA -->
  <section class="cta">

    <div class="cta-box">

      <h2>Ready to Start?</h2>

      <p>
        Join our Discord to see available Minecraft and Discord
        premade servers and get support.
      </p>

      <a
        href="https://discord.gg/p8E5PwT5q"
        target="_blank"
        class="btn discord">
        Join Discord →
      </a>

    </div>

  </section>


  <!-- FOOTER -->
  <footer>

    <p>
      © 2026 <strong>ServerVault</strong>.
      Minecraft & Discord Premade Servers.
    </p>

  </footer>


</body>
</html>
