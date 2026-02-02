<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>THE BOX — Official Hub</title>
  <meta name="description" content="THE BOX — cinematic mystery web series hub." />
  <style>
    :root{
      --bg:#0b0602;
      --panel:#120a03;
      --accent:#f5b233;
      --accent-2:#ff9f2c;
      --muted:rgba(255,255,255,0.92);
      --glass: rgba(255,255,255,0.03);
      --max-width:1200px;
      --radius:12px;
      --ease:cubic-bezier(.2,.9,.2,1);
    }
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;background:linear-gradient(180deg,#070403 0%, #0b0602 70%);color:#fff;font-family:Inter, system-ui, -apple-system, "Segoe UI", Roboto, Arial}
    a{color:inherit;text-decoration:none}
    img{display:block;max-width:100%;height:auto}

    /* Header */
    header {
      position:fixed; inset:0 0 auto 0; height:72px; display:flex; align-items:center; justify-content:space-between;
      padding:10px 24px; z-index:120; backdrop-filter: blur(8px);
      background: linear-gradient(180deg, rgba(6,3,1,0.6), rgba(6,3,1,0.35));
      border-bottom: 1px solid rgba(255,255,255,0.03);
    }
    .brand { display:flex; align-items:center; gap:14px; }
    .logo-box { width:64px; height:64px; border-radius:10px; overflow:hidden; display:grid; place-items:center; background:linear-gradient(90deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01)); box-shadow:0 10px 30px rgba(0,0,0,0.6) }
    .brand .title { font-weight:700; letter-spacing:1px; color:var(--accent); font-size:18px }
    nav { display:flex; gap:18px; align-items:center; }
    nav a { color:var(--muted); font-weight:600; padding:8px 12px; border-radius:8px; transition: all .18s var(--ease); }
    nav a:hover { color:#111; background:linear-gradient(90deg,var(--accent),var(--accent-2)); transform:translateY(-3px); box-shadow:0 8px 30px rgba(255,159,44,0.06) }

    /* --- FRONT PAGE HERO (FULL-IMAGE) --- */
    /* The hero now uses the poster as the full front page background.
       Buttons and title are centered on top of the poster. */
    .hero {
      min-height:100vh;
      width:100%;
      position:relative;
      display:flex;
      align-items:center;
      justify-content:center;
      overflow:hidden;
      margin-top:72px; /* keep header space */
      background: center/cover no-repeat url('THE_BOX_POSTER.jpeg');
    }
    /* subtle dark overlay for readability */
    .hero::before{
      content:"";position:absolute;inset:0;
      background:linear-gradient(180deg, rgba(0,0,0,0.25), rgba(0,0,0,0.6));
      z-index:1;
    }
    .hero::after{
      content:"";position:absolute;inset:0;
      background: radial-gradient(60% 60% at 50% 40%, rgba(0,0,0,0) 0%, rgba(0,0,0,0.28) 40%, rgba(0,0,0,0.85) 100%);
      z-index:2;
    }

    /* Center overlay content (title + buttons) */
    .hero-content{
      position:relative;z-index:10;text-align:center;padding:28px;max-width:1100px;width:100%;
      display:flex;flex-direction:column;align-items:center;gap:18px;
    }
    .title {
      color:var(--accent);font-size:48px;font-weight:800;letter-spacing:1px;text-shadow:0 6px 30px rgba(245,178,51,0.08);
      margin:0;
    }
    .tagline { color:var(--muted);font-size:18px;margin-top:6px }

    /* Buttons on the poster */
    .controls { display:flex;gap:14px;margin-top:18px;flex-wrap:wrap;justify-content:center }
    .btn {
      display:inline-flex;align-items:center;gap:10px;padding:12px 20px;border-radius:999px;font-weight:700;cursor:pointer;
      border:1px solid rgba(255,255,255,0.06);transition:transform .18s var(--ease),box-shadow .18s var(--ease);
      backdrop-filter: blur(4px);
    }
    .btn-primary { background:linear-gradient(90deg,var(--accent),var(--accent-2)); color:#111; box-shadow:0 14px 40px rgba(245,178,51,0.18) }
    .btn-ghost { background:rgba(255,255,255,0.04); color:var(--muted) }
    .btn:hover{ transform:translateY(-6px) }

    .hero-foot { margin-top:10px;color:rgba(255,255,255,0.75);font-size:13px }

    /* --- REST OF SITE (unchanged) --- */
    main { background:#070403 }
    section { padding:72px 20px; max-width:var(--max-width); margin:0 auto; color:var(--muted) }
    h2 { color:var(--accent); text-align:center; margin-bottom:28px; font-size:28px }

    .episodes-grid { display:grid; grid-template-columns: repeat(2, 1fr); gap:28px; align-items:start; }
    .card { background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01)); border-radius:12px; padding:14px; overflow:hidden; border:1px solid rgba(255,255,255,0.03); transition: transform .22s var(--ease), box-shadow .22s var(--ease); }
    .card:hover { transform: translateY(-8px); box-shadow: 0 30px 80px rgba(0,0,0,0.6), 0 10px 30px rgba(245,178,51,0.04) }
    .thumb { width:100%; height:220px; border-radius:8px; overflow:hidden; background:#120a03; display:block; }
    .meta { padding:12px 6px 6px 6px }
    .meta h3 { margin:0 0 6px 0; font-size:18px; color:var(--muted) }
    .meta p { margin:0; color:var(--muted); font-size:14px }

    .gallery { display:grid; grid-template-columns: repeat(3, 1fr); gap:18px; align-items:start; }
    .gallery .gimg { border-radius:10px; overflow:hidden; transition: transform .25s var(--ease), box-shadow .25s var(--ease); }
    .gallery .gimg:hover { transform: translateY(-8px) scale(1.02); box-shadow: 0 30px 80px rgba(0,0,0,0.6) }

    .lore-grid { display:grid; grid-template-columns: repeat(3, 1fr); gap:20px; }
    .lore-card { padding:18px; border-radius:12px; background:var(--panel); border:1px solid rgba(255,255,255,0.03); color:var(--muted) }

    footer { padding:36px 20px; text-align:center; color:#9b9b9b; background:linear-gradient(180deg, rgba(0,0,0,0.02), rgba(0,0,0,0.06)); margin-top:40px }

    /* Modal */
    .modal { position:fixed; inset:0; display:none; place-items:center; z-index:200; background: rgba(0,0,0,0.75); padding:20px; }
    .modal.open { display:grid }
    .modal .frame { width:100%; max-width:1000px; aspect-ratio:16/9; background:#000; border-radius:12px; overflow:hidden; box-shadow:0 30px 80px rgba(0,0,0,0.8) }
    .modal .close { position:absolute; top:22px; right:22px; background:rgba(255,255,255,0.06); border-radius:8px; padding:8px 10px; cursor:pointer; color:var(--muted) }

    /* Responsive */
    @media (max-width:1000px){
      .episodes-grid { grid-template-columns: 1fr; }
      .gallery { grid-template-columns: repeat(2, 1fr); }
      .lore-grid { grid-template-columns: repeat(2, 1fr); }
      .hero { background-position:center 30% }
      .title { font-size:36px }
    }
    @media (max-width:600px){
      header { padding:8px 12px; height:64px }
      .brand .title { display:none }
      .gallery { grid-template-columns: 1fr; }
      .lore-grid { grid-template-columns: 1fr }
      .hero-content { padding:18px }
      .title { font-size:28px }
      .controls { flex-direction:column }
      .btn { width:220px; justify-content:center }
    }
  </style>
</head>
<body>

  <header>
    <div class="brand">
      <div class="logo-box" aria-hidden="true">
        <img src="THE_BOX_LOGO.png" alt="THE BOX logo" style="width:86%;height:86%;object-fit:contain">
      </div>
      <div class="title">THE BOX</div>
    </div>

    <nav aria-label="Primary">
      <a href="#home">Home</a>
      <a href="#episodes">Episodes</a>
      <a href="#gallery">Gallery</a>
      <a href="#lore">Lore</a>
      <a href="#about">About</a>
    </nav>
  </header>

  <!-- FRONT PAGE HERO (full-image) -->
  <section class="hero" id="home" aria-label="Main poster">
    <div class="hero-content" role="region" aria-label="Hero content">
      <h1 class="title">THE BOX</h1>
      <p class="tagline">Something strange is inside...</p>

      <div class="controls">
        <button class="btn btn-primary" id="openTrailer" aria-controls="trailer">Watch Trailer</button>
        <a class="btn btn-ghost" href="#episodes">View Episodes</a>
      </div>

      <div class="hero-foot">New episodes released weekly • Replace placeholders with your videos</div>
    </div>
  </section>

  <main>
    <section id="episodes">
      <h2>Episodes</h2>
      <div class="episodes-grid">
        <article class="card" role="article" aria-label="Episode 1">
          <a class="thumb" href="#ep1" onclick="return false;">
            <img src="https://picsum.photos/800/450?random=21" alt="Episode 1 thumbnail">
          </a>
          <div class="meta">
            <h3>Episode 1 — The Arrival</h3>
            <p>When the box appears, the town's quiet life fractures. Strange phenomena begin.</p>
            <div style="margin-top:12px">
              <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="Episode 1" allowfullscreen style="width:100%;height:260px;border:none;border-radius:8px"></iframe>
            </div>
          </div>
        </article>

        <article class="card" role="article" aria-label="Episode 2">
          <a class="thumb" href="#ep2" onclick="return false;">
            <img src="https://picsum.photos/800/450?random=22" alt="Episode 2 thumbnail">
          </a>
          <div class="meta">
            <h3>Episode 2 — Secrets Within</h3>
            <p>Clues point to a hidden history. Tensions rise and alliances shift.</p>
            <div style="margin-top:12px">
              <iframe src="https://www.youtube.com/embed/3GwjfUFyY6M" title="Episode 2" allowfullscreen style="width:100%;height:260px;border:none;border-radius:8px"></iframe>
            </div>
          </div>
        </article>
      </div>
    </section>

    <section id="gallery">
      <h2>Gallery</h2>
      <div class="gallery" role="list">
        <div class="gimg" role="listitem"><img src="https://picsum.photos/600/400?random=31" alt="Gallery image 1"></div>
        <div class="gimg" role="listitem"><img src="https://picsum.photos/600/400?random=32" alt="Gallery image 2"></div>
        <div class="gimg" role="listitem"><img src="https://picsum.photos/600/400?random=33" alt="Gallery image 3"></div>
      </div>
    </section>

    <section id="lore">
      <h2>Lore</h2>
      <div class="lore-grid">
        <div class="lore-card">
          <h4 style="color:var(--accent);margin-bottom:8px">Origins</h4>
          <p>Legends speak of objects that bridge worlds. The box's arrival rekindles old myths and new fears.</p>
        </div>
        <div class="lore-card">
          <h4 style="color:var(--accent);margin-bottom:8px">The Box</h4>
          <p>Not merely a container, it reacts to people. Its light reveals memories and fractures reality.</p>
        </div>
        <div class="lore-card">
          <h4 style="color:var(--accent);margin-bottom:8px">Characters</h4>
          <p>Complex protagonists and ambiguous motives. Trust is scarce; every choice has a cost.</p>
        </div>
      </div>
    </section>

    <section id="about">
      <h2>About</h2>
      <div style="max-width:900px;margin:0 auto;color:var(--muted);line-height:1.6;text-align:center">
        <p>“THE BOX” is a cinematic web series blending mystery, psychological tension, and supernatural intrigue. This site is a hub for episodes, behind-the-scenes imagery, and the evolving lore. Replace placeholder media with your final assets to complete the experience.</p>
      </div>
    </section>
  </main>

  <footer>
    <div style="max-width:var(--max-width);margin:0 auto;padding:8px 20px;display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap">
      <div style="color:#bdbdbd">© <span id="year"></span> THE BOX</div>
      <div style="color:#bdbdbd">Follow: <span style="color:var(--accent)">Instagram</span> • <span style="color:var(--accent)">Twitter</span></div>
    </div>
  </footer>

  <!-- Trailer modal -->
  <div id="trailerModal" class="modal" aria-hidden="true" role="dialog" aria-label="Trailer">
    <button class="close" id="closeModal" aria-label="Close trailer">✕</button>
    <div class="frame" id="modalFrame"></div>
  </div>

  <script>
    // Year
    document.getElementById('year').textContent = new Date().getFullYear();

    // Trailer modal logic
    const openBtn = document.getElementById('openTrailer');
    const modal = document.getElementById('trailerModal');
    const closeBtn = document.getElementById('closeModal');
    const frame = document.getElementById('modalFrame');

    const TRAILER_URL = "https://www.youtube.com/embed/dQw4w9WgXcQ?autoplay=1&rel=0";

    openBtn.addEventListener('click', () => {
      frame.innerHTML = '<iframe src="' + TRAILER_URL + '" title="Trailer" allow="autoplay; fullscreen" style="width:100%;height:100%;border:0"></iframe>';
      modal.classList.add('open');
      modal.setAttribute('aria-hidden','false');
      document.body.style.overflow = 'hidden';
    });

    closeBtn.addEventListener('click', closeModal);
    modal.addEventListener('click', (e) => { if (e.target === modal) closeModal(); });

    function closeModal(){
      modal.classList.remove('open');
      modal.setAttribute('aria-hidden','true');
      frame.innerHTML = '';
      document.body.style.overflow = '';
    }

    // Parallax hero background (subtle)
    const hero = document.querySelector('.hero');
    const bg = document.querySelector('.hero');
    hero.addEventListener('mousemove', (e) => {
      const rect = hero.getBoundingClientRect();
      const x = (e.clientX - rect.left) / rect.width - 0.5;
      const y = (e.clientY - rect.top) / rect.height - 0.5;
      hero.style.backgroundPosition = `${50 + x * 3}% ${50 + y * 3}%`;
    });
    hero.addEventListener('mouseleave', () => { hero.style.backgroundPosition = 'center'; });
  </script>
</body>
</html>
