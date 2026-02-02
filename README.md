<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>THE BOX — Official</title>
  <meta name="description" content="Official page for THE BOX — a mystery thriller." />
  <meta property="og:title" content="THE BOX — Official" />
  <meta property="og:description" content="Something strange is inside..." />
  <meta property="og:image" content="assets/images/poster.jpg" />
  <meta property="og:type" content="website" />

  <style>
    :root{
      --bg:#070707;
      --accent:#f5b233;
      --muted:rgba(255,255,255,0.9);
      --max-width:1400px;
      --logo-size:64px;
    }
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;background:var(--bg);color:#fff;font-family:Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial}
    a{color:inherit;text-decoration:none}

    /* Logo */
    .logo {
      position:fixed;
      top:18px;
      left:18px;
      z-index:60;
      display:flex;
      align-items:center;
      gap:10px;
      padding:6px;
      border-radius:14px;
      background: linear-gradient(180deg, rgba(255,255,255,0.03), rgba(255,255,255,0.02));
      backdrop-filter: blur(6px);
      -webkit-backdrop-filter: blur(6px);
      box-shadow: 0 6px 20px rgba(0,0,0,0.6);
    }
    .logo-img{
      display:block;
      width:var(--logo-size);
      height:var(--logo-size);
      object-fit:contain;
      border-radius:8px;
      background:transparent;
    }

    /* Main hero */
    .hero {
      min-height:100vh;
      width:100%;
      display:grid;
      place-items:center;
      overflow:hidden;
      position:relative;
    }
    .hero-bg{
      position:absolute;inset:0;
      background-position:center;
      background-size:cover;
      background-repeat:no-repeat;
      filter:brightness(.58) saturate(.98);
      transform:scale(1.03);
    }

    /* Subtle vignette */
    .hero::after{
      content:"";position:absolute;inset:0;
      background: radial-gradient(60% 60% at 50% 40%, rgba(0,0,0,0) 0%, rgba(0,0,0,0.28) 40%, rgba(0,0,0,0.7) 100%);
      pointer-events:none;
    }

    /* Center content (minimal) */
    .hero-content{
      position:relative;z-index:30;
      text-align:center;
      max-width:1100px;
      width:100%;
      padding:28px;
      display:flex;
      flex-direction:column;
      align-items:center;
      gap:22px;
    }

    /* Big translucent card for optional copy */
    .card {
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border-radius:14px;
      padding:18px 22px;
      color:var(--muted);
      backdrop-filter: blur(6px);
      -webkit-backdrop-filter: blur(6px);
      box-shadow: 0 12px 40px rgba(0,0,0,0.6);
    }

    /* Play CTA */
    .play {
      display:inline-flex;
      align-items:center;
      gap:12px;
      background:rgba(255,255,255,0.06);
      padding:12px 18px;
      border-radius:999px;
      color:var(--muted);
      font-weight:600;
      border:1px solid rgba(255,255,255,0.04);
      transition: transform .16s ease, background .16s ease;
    }
    .play:hover{ transform:translateY(-4px); background:rgba(255,255,255,0.08) }

    .play .dot{
      width:44px;height:44px;display:grid;place-items:center;
      background:linear-gradient(90deg,#ffb34a,#f5b233);
      border-radius:50%;
      box-shadow: 0 8px 24px rgba(245,178,51,0.25);
    }
    .play .dot svg{ width:18px; height:18px; fill:#111; margin-left:3px }

    /* Footer / small info */
    footer.site-footer{
      position:relative;z-index:30;margin-top:28px;color:rgba(255,255,255,0.65);font-size:13px;
    }

    /* Small screens */
    @media (max-width:720px){
      :root{--logo-size:52px}
      .card{padding:14px}
      .play{padding:10px 14px}
      .play .dot{width:40px;height:40px}
    }
  </style>
</head>
<body>
  <!-- Logo (image only, no textual site title) -->
  <a class="logo" href="/" aria-label="Home">
    <img class="logo-img" src="assets/images/the-box-logo.png" alt="Site logo">
  </a>

  <main class="hero" role="main" aria-label="Main poster">
    <!-- Background uses the main hero image from the repo -->
    <div class="hero-bg" style="background-image: url('assets/images/poster.jpg');" role="img" aria-label="Main poster image"></div>

    <div class="hero-content">
      <div class="card" aria-hidden="false">
        <!-- Minimal copy: keep it short and atmospheric -->
        <p style="margin:0;font-size:18px;color:rgba(255,255,255,0.92);letter-spacing:0.6px">
          Something strange is inside...
        </p>
      </div>

      <!-- Play CTA — link to trailer section or open modal (placeholder link) -->
      <a class="play" href="#trailer" title="Watch Trailer" role="button">
        <span class="dot" aria-hidden="true">
          <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" focusable="false" aria-hidden="true"><path d="M6 4l12 8-12 8z"/></svg>
        </span>
        <span style="font-size:15px">Watch Trailer</span>
      </a>

      <footer class="site-footer">
        &copy; <span id="year"></span>. All rights reserved.
      </footer>
    </div>
  </main>

  <!-- Hidden trailer anchor (replace with iframe if available) -->
  <section id="trailer" style="display:none; padding:32px;">
    <!-- Embed your trailer here -->
  </section>

  <script>
    document.getElementById('year').textContent = new Date().getFullYear();
  </script>
</body>
</html>
