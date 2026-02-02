<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>THE BOX - Web Series</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(to bottom, #0d0d0d, #1a1a1a);
      color: #f0f0f0;
    }
    header {
      display: flex;
      align-items: center;
      padding: 10px 20px;
      background-color: #111;
      box-shadow: 0 2px 5px rgba(0,0,0,0.5);
    }
    header img.logo {
      height: 60px;
      margin-right: 20px;
    }
    nav a {
      color: #f0f0f0;
      margin: 0 15px;
      text-decoration: none;
      font-weight: bold;
      transition: color 0.3s;
    }
    nav a:hover {
      color: #ffcc00;
    }
    .main-poster {
      text-align: center;
      margin: 40px 0;
    }
    .main-poster img {
      max-width: 90%;
      height: auto;
      box-shadow: 0 0 20px rgba(255, 204, 0, 0.3);
    }
    section {
      padding: 40px 20px;
      border-top: 1px solid #333;
    }
    h2 {
      color: #ffcc00;
      margin-bottom: 20px;
    }
    .episodes iframe {
      width: 100%;
      max-width: 600px;
      height: 340px;
      margin: 20px auto;
      display: block;
      border: none;
      box-shadow: 0 0 10px rgba(255,255,255,0.2);
    }
    .gallery img {
      width: 100%;
      max-width: 300px;
      margin: 10px;
      border-radius: 5px;
      box-shadow: 0 0 10px rgba(255,255,255,0.1);
    }
    .about {
      max-width: 600px;
      margin: auto;
      font-size: 1.1em;
      line-height: 1.6;
    }
    footer {
      text-align: center;
      padding: 20px;
      background-color: #111;
      font-size: 0.9em;
      color: #aaa;
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

  <div class="main-poster" id="home">
    <img src="THE_BOX_POSTER.jpeg" alt="Main Poster" />
  </div>

  <section class="episodes" id="episodes">
    <h2>Episodes</h2>
    <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" allowfullscreen></iframe>
    <iframe src="https://www.youtube.com/embed/3GwjfUFyY6M" allowfullscreen></iframe>
  </section>

  <section class="gallery" id="gallery">
    <h2>Gallery</h2>
    <img src="https://picsum.photos/300/200?random=1" alt="Gallery Image 1" />
    <img src="https://picsum.photos/300/200?random=2" alt="Gallery Image 2" />
    <img src="https://picsum.photos/300/200?random=3" alt="Gallery Image 3" />
  </section>

  <section class="about" id="about">
    <h2>About the Series</h2>
    <p>
      “THE BOX” is a gripping mystery thriller that explores the unknown. Each episode unravels secrets hidden inside a strange box that appeared out of nowhere. Follow the journey of discovery, suspense, and danger as characters confront their deepest fears.
    </p>
  </section>

  <footer>
    &copy; 2026 THE BOX Web Series. All rights reserved.
  </footer>

  <script>
    // Future enhancements: dynamic episode loading, theme toggles, etc.
    console.log("Welcome to THE BOX website.");
  </script>

</body>
</html>
