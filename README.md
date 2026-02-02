<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>THE BOX — Web Series</title>
  <style>
    :root {
      --bg: #0a0a0a;
      --accent: #f5b233;
      --text: #f0f0f0;
      --muted: rgba(255,255,255,0.7);
      --max-width: 1200px;
    }
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body {
      font-family: 'Segoe UI', sans-serif;
      background: var(--bg);
      color: var(--text);
      scroll-behavior: smooth;
    }
    header {
      position: fixed;
      top: 0; left: 0; right: 0;
      background: rgba(0,0,0,0.8);
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 10px 20px;
      z-index: 100;
      box-shadow: 0 2px 10px rgba(0,0,0,0.6);
    }
    header img.logo {
      height: 50px;
    }
    nav a {
      color: var(--text);
      margin: 0 15px;
      text-decoration: none;
      font-weight: bold;
      transition: color 0.3s;
    }
    nav a:hover {
      color: var(--accent);
    }
    .hero {
      height: 100vh;
      background: url('THE_BOX_POSTER.jpeg') center/cover no-repeat;
      display: flex;
      align-items: center;
      justify-content: center;
      position: relative;
    }
    .hero::after {
      content: "";
      position: absolute;
      inset: 0;
      background: radial-gradient(circle at center, transparent 40%, rgba(0,0,0,0.8) 100%);
    }
    .hero-content {
      position: relative;
      text-align: center;
      z-index: 10;
    }
    .hero-content h1 {
      font-size: 48px;
      color: var(--accent);
      margin-bottom: 20px;
    }
    .hero-content p {
      font-size: 20px;
      color: var(--muted);
    }
    section {
      padding: 60px 20px;
      max-width: var(--max-width);
      margin: auto;
    }
    h2 {
      color: var(--accent);
      margin-bottom: 20px;
      text-align: center;
    }
    .episodes iframe {
      width: 100%;
      max-width: 640px;
      height: 360px;
      margin: 20px auto;
      display: block;
      border: none;
      box-shadow: 0 0 20px rgba(245,178,51,0.3);
    }
    .gallery {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
    }
    .gallery img {
      width: 300px;
      border-radius: 8px;
      box-shadow: 0 0 12px rgba(255,255,255,0.1);
    }
    .about {
      font-size: 1.1em;
      line-height: 1.6;
      color: var(--muted);
      max-width: 800px;
      margin: auto;
      text-align: center;
    }
    footer {
      text-align: center;
      padding: 20px;
      background: #111;
      color: #aaa;
      font-size: 0.9em;
    }
    @media (max-width: 768px) {
      .hero-content h1 { font-size: 36px; }
      .hero-content p { font-size: 16px; }
      .gallery img { width: 90%; }
    }
  </style>
</head>
<body>

  <header>
    <img src="THE_BOX_LOGO.png" alt="THE BOX Logo" class="logo" />
    <nav>
      <a href="#home">Home</a>
      <a href="#episodes">Episodes</a>
      <a href="#gallery">Gallery</a>
      <a href="#about">About</a>
    </nav>
  </header>

  <section class="hero" id="home">
    <div class="hero-content">
      <h1>THE BOX</h1>
      <p>Something strange is inside...</p>
    </div>
  </section>

  <section id="episodes" class="episodes">
    <h2>Episodes</h2>
    <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" allowfullscreen></iframe>
    <iframe src="https://www.youtube.com/embed/3GwjfUFyY6M" allowfullscreen></iframe>
  </section>

  <section id="gallery" class="gallery">
    <h2>Gallery</h2>
    <img src="https://picsum.photos/300/200?random=1" alt="Gallery Image 1" />
    <img src="https://picsum.photos/300/200?random=2" alt="Gallery Image 2" />
    <img src="https://picsum.photos/300/200?random=3" alt="Gallery Image 3" />
  </section>

  <section id="about" class="about">
    <h2>About the Series</h2>
    <p>
      “THE BOX” is a mystery thriller web series that explores the unknown. Each episode reveals secrets hidden inside a strange box that appeared out of nowhere. Follow the journey of suspense, fear, and discovery as the characters confront what lies within.
    </p>
  </section>

  <footer>
    &copy; <span id="year"></span> THE BOX Web Series. All rights reserved.
  </footer>

  <script>
    document.getElementById('year').textContent = new Date().getFullYear();
  </script>
</body>
</html>
