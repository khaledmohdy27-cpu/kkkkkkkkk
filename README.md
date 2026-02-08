<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Coding With Me</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: Arial, sans-serif;
    }

    body {
      background: white;
      color: #444;
      transition: 0.3s;
    }

    /* Dark mode */
    body.dark {
      background: #0B1E30;
      color: #ddd;
    }

    /* Navbar */
    .navbar {
      position: fixed;
      top: 0;
      width: 100%;
      height: 64px;
      background: rgba(15, 42, 68, 0.9);
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 0 40px;
      color: white;
      z-index: 1000;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .brand img {
      height: 32px;
      border-radius: 50%;
    }

    .title {
      font-weight: bold;
    }

    .subtitle {
      font-size: 12px;
      color: #ccc;
    }

    .navbar button {
      background: transparent;
      border: 1px solid rgba(255,255,255,0.3);
      color: white;
      padding: 6px 10px;
      cursor: pointer;
      border-radius: 5px;
    }

    /* Hero */
    .hero {
      height: 80vh;
      background: linear-gradient(135deg, #0F2A44, #1F6FB2);
      display: flex;
      justify-content: center;
      align-items: center;
      color: white;
      padding-top: 64px;
    }

    .hero-content {
      text-align: center;
      animation: fadeUp 0.8s ease;
    }

    .hero-content img {
      height: 90px;
      margin-bottom: 20px;
      border-radius: 50%;
    }

    .hero-content h1 {
      font-size: 48px;
    }

    .hero-content p {
      margin-top: 10px;
      color: #ddd;
      border-radius: 5px;
    }

    /* Sections */
    .section {
      padding: 100px 20px;
      text-align: center;
    }

    .section h2 {
      font-size: 32px;
      margin-bottom: 10px;
    }

    .section p {
      opacity: 0.8;
    }

    .section.gray {
      background: #F5F7FA;
    }

    body.dark .section.gray {
      background: #0E2438;
    }

    .section.dark {
      background: #0F2A44;
      color: white;
    }

    /* Portfolio cards */
    .projects {
      display: flex;
      justify-content: center;
      gap: 20px;
      margin-top: 20px;
      flex-wrap: wrap;
    }

    .project-card {
      background: #eee;
      padding: 20px;
      border-radius: 8px;
      width: 150px;
      transition: 0.3s;
    }

    .project-card:hover {
      background: #ddd;
      transform: translateY(-5px);
    }

    body.dark .project-card {
      background: #1A3A55;
      color: #fff;
    }

    body.dark .project-card:hover {
      background: #25577A;
    }

    /* Footer */
    footer {
      background: #0F2A44;
      color: #ccc;
      padding: 40px 20px;
      text-align: center;
    }

    .footer-content {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 10px;
      margin-bottom: 10px;
    }

    .footer-content img {
      height: 32px;
      border-radius: 50%;
    }

    /* Animation */
    @keyframes fadeUp {
      from {
        opacity: 0;
        transform: translateY(30px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    /* Responsive */
    @media (max-width: 768px) {
      .hero-content h1 {
        font-size: 32px;
      }
      .navbar {
        padding: 0 20px;
      }
      .projects {
        flex-direction: column;
        align-items: center;
      }
    }
  </style>
</head>
<body>

  <!-- Navbar -->
  <nav class="navbar">
    <div class="brand">
      <img src="https://uploads.onecompiler.io/442mbqand/44cuhcctp/khalrd%20pic.jpeg" alt="Logo">
      <div>
        <span class="title">Coding With Me</span>
        <span class="subtitle">Khaled Mohammed</span>
      </div>
    </div>
    <button id="themeToggle">🌙 Dark</button>
  </nav>

  <!-- Hero -->
  <section class="hero">
    <div class="hero-content">
      <img src="https://uploads.onecompiler.io/442mbqand/44cuhcctp/khalrd%20pic.jpeg" alt="Coding With Me">
      <h1>Coding With Me</h1>
      <p>Khaled Mohammed</p>
    </div>
  </section>

  <!-- Sections -->
  <section class="section" id="about">
    <h2>About</h2>
    <p> I am Khaled mohammed ,software Engineer </p>
  </section>

  <section class="section gray" id="services">
    <h2>Services</h2>
    <p> programming </p>
  </section>

  <section class="section" id="portfolio">
    <h2>Portfolio</h2>
    <p>بعض من مشاريعي السابقة:</p>
    <div class="projects">
      <div class="project-card">📌 موقع شخصي</div>
      <div class="project-card">📌 تطبيق إدارة مهام</div>
      <div class="project-card">📌 متجر إلكتروني</div>
    </div>
  </section>

  <section class="section dark" id="contact">
    <h2>Contact</h2>
    <p>connect us: <strong>khaledmahdy27@gmail.com</strong></p>
  </section>

  <!-- Footer -->
  <footer>
    <div class="footer-content">
      <img src="https://uploads.onecompiler.io/442mbqand/44cuhcctp/khalrd%20pic.jpeg" alt="Logo">
      <div>
        <strong>Coding With Me</strong>
        <div>Khaled Mohammed</div>
      </div>
    </div>
    <p>© 2026 Coding With Me. All rights reserved.</p>
  </footer>

  <script>
    const toggleBtn = document.getElementById("themeToggle");
    const body = document.body;

    // Load saved theme
    if (localStorage.getItem("theme") === "dark") {
      body.classList.add("dark");
      toggleBtn.textContent = "☀️ Light";
    }

    // Toggle theme
    toggleBtn.onclick = () => {
      body.classList.toggle("dark");

      if (body.classList.contains("dark")) {
        localStorage.setItem("theme", "dark");
        toggleBtn.textContent = "☀️ Light";
      } else {
        localStorage.setItem("theme", "light");
        toggleBtn.textContent = "🌙 Dark";
      }
    };
  </script>
</body>
</html>
