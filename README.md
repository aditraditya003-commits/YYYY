# Pride-Of-Nusantara
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Pride of Nusantara</title>

  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link
    href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=Playfair+Display:wght@600;700;800&display=swap"
    rel="stylesheet"
  />

  <style>
    :root {
      --green-950: #10251d;
      --green-900: #173b2c;
      --green-800: #245c43;
      --green-700: #347655;
      --green-100: #e3f0e5;
      --cream: #f8f5ed;
      --gold: #e7a83e;
      --text: #24362d;
      --muted: #6b7d72;
      --white: #ffffff;
      --shadow: 0 18px 45px rgba(18, 54, 39, 0.12);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: "DM Sans", sans-serif;
      color: var(--text);
      background: var(--cream);
      line-height: 1.7;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    .container {
      width: min(1120px, calc(100% - 40px));
      margin: auto;
    }

    header {
      position: fixed;
      z-index: 20;
      top: 0;
      width: 100%;
      color: white;
      transition: 0.3s;
    }

    header.scrolled {
      background: rgba(16, 37, 29, 0.96);
      box-shadow: 0 3px 20px rgba(0, 0, 0, 0.12);
    }

    .navbar {
      min-height: 78px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 30px;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 10px;
      font-weight: 700;
      letter-spacing: 0.3px;
    }

    .brand-icon {
      width: 38px;
      height: 38px;
      display: grid;
      place-items: center;
      border-radius: 50%;
      background: var(--gold);
      color: var(--green-950);
      font-size: 20px;
    }

    nav {
      display: flex;
      gap: 28px;
      font-size: 14px;
      font-weight: 600;
    }

    nav a {
      opacity: 0.88;
      transition: 0.2s;
    }

    nav a:hover {
      color: var(--gold);
      opacity: 1;
    }

    .hero {
      min-height: 720px;
      display: flex;
      align-items: center;
      color: white;
      background:
        linear-gradient(90deg, rgba(10, 36, 26, 0.9), rgba(10, 36, 26, 0.42)),
        url("https://images.unsplash.com/photo-1516026672322-bc52d61a55d5?auto=format&fit=crop&w=1800&q=85")
        center/cover;
    }

    .hero-content {
      max-width: 680px;
      padding-top: 70px;
    }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 9px;
      color: var(--gold);
      font-size: 13px;
      font-weight: 700;
      letter-spacing: 2px;
      text-transform: uppercase;
      margin-bottom: 20px;
    }

    .eyebrow::before {
      content: "";
      width: 32px;
      height: 2px;
      background: var(--gold);
    }

    h1,
    h2,
    h3 {
      font-family: "Playfair Display", serif;
      line-height: 1.15;
    }

    h1 {
      font-size: clamp(48px, 8vw, 92px);
      margin-bottom: 24px;
    }

    .hero p {
      max-width: 570px;
      color: #e1eee5;
      font-size: 18px;
      margin-bottom: 34px;
    }

    .button {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      border: 0;
      border-radius: 999px;
      padding: 14px 23px;
      background: var(--gold);
      color: var(--green-950);
      cursor: pointer;
      font: inherit;
      font-weight: 700;
      transition: 0.25s;
    }

    .button:hover {
      transform: translateY(-3px);
      background: #f3bd59;
      box-shadow: 0 10px 25px rgba(231, 168, 62, 0.25);
    }

    .intro {
      padding: 100px 0 55px;
      text-align: center;
    }

    .section-label {
      color: var(--green-700);
      font-size: 13px;
      letter-spacing: 2px;
      font-weight: 700;
      text-transform: uppercase;
      margin-bottom: 12px;
    }

    .intro h2 {
      color: var(--green-900);
      font-size: clamp(34px, 5vw, 54px);
      margin-bottom: 18px;
    }

    .intro p {
      max-width: 670px;
      margin: auto;
      color: var(--muted);
    }

    .filters {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 10px;
      margin: 34px 0 40px;
    }

    .filter-btn {
      border: 1px solid #cbdccc;
      border-radius: 999px;
      background: transparent;
      color: var(--green-800);
      padding: 9px 18px;
      cursor: pointer;
      font: inherit;
      font-size: 14px;
      font-weight: 600;
      transition: 0.2s;
    }

    .filter-btn.active,
    .filter-btn:hover {
      background: var(--green-800);
      color: white;
      border-color: var(--green-800);
    }

    .species-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 26px;
      padding-bottom: 110px;
    }

    .card {
      overflow: hidden;
      background: white;
      border-radius: 22px;
      box-shadow: var(--shadow);
      transition: 0.3s;
    }

    .card:hover {
      transform: translateY(-7px);
      box-shadow: 0 25px 55px rgba(18, 54, 39, 0.18);
    }

    .card.hidden {
      display: none;
    }

    .card-image {
      height: 280px;
      overflow: hidden;
      position: relative;
    }

    .card-image img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: 0.5s;
    }

    .card:hover .card-image img {
      transform: scale(1.06);
    }

    .category {
      position: absolute;
      left: 18px;
      top: 18px;
      border-radius: 999px;
      padding: 6px 12px;
      background: rgba(255, 255, 255, 0.9);
      color: var(--green-800);
      font-size: 12px;
      font-weight: 700;
    }

    .card-body {
      padding: 26px;
    }

    .card h3 {
      color: var(--green-900);
      font-size: 29px;
      margin-bottom: 3px;
    }

    .scientific {
      color: var(--green-700);
      font-size: 14px;
      font-style: italic;
      margin-bottom: 17px;
    }

    .card-description {
      color: #607067;
      font-size: 15px;
    }

    .fact {
      display: flex;
      gap: 12px;
      align-items: flex-start;
      margin-top: 22px;
      padding: 15px;
      border-radius: 12px;
      background: var(--green-100);
      color: var(--green-900);
      font-size: 14px;
    }

    .fact span {
      font-size: 23px;
      line-height: 1.2;
    }

    .fact strong {
      display: block;
      color: var(--green-800);
      margin-bottom: 3px;
    }

    .closing {
      padding: 105px 0;
      color: white;
      text-align: center;
      background:
        linear-gradient(rgba(23, 59, 44, 0.92), rgba(23, 59, 44, 0.96)),
        url("https://images.unsplash.com/photo-1500534623283-312aade485b7?auto=format&fit=crop&w=1800&q=80")
        center/cover;
    }

    .closing h2 {
      font-size: clamp(34px, 5vw, 52px);
      margin-bottom: 24px;
    }

    .closing p {
      max-width: 780px;
      margin: auto;
      color: #dcebe0;
      font-size: 17px;
    }

    footer {
      padding: 25px 0;
      background: var(--green-950);
      color: #b8cabc;
      text-align: center;
      font-size: 13px;
    }

    @media (max-width: 700px) {
      .navbar {
        min-height: 68px;
      }

      nav {
        display: none;
      }

      .hero {
        min-height: 650px;
      }

      .species-grid {
        grid-template-columns: 1fr;
      }

      .intro {
        padding-top: 75px;
      }

      .card-image {
        height: 230px;
      }
    }
  </style>
</head>

<body>
  <header id="header">
    <div class="container navbar">
      <a href="#home" class="brand">
        <span class="brand-icon">🌿</span>
        <span>Pride of Nusantara</span>
      </a>

      <nav>
        <a href="#home">Beranda</a>
        <a href="#species">Eksplorasi</a>
        <a href="#closing">Pelestarian</a>
      </nav>
    </div>
  </header>

  <main>
    <section class="hero" id="home">
      <div class="container hero-content">
        <div class="eyebrow">Kekayaan alam Indonesia</div>
        <h1>Pride of<br />Nusantara</h1>
        <p>
          Mengenal keindahan flora dan fauna Indonesia sebagai warisan alam
          yang perlu dihargai, dijaga, dan dilestarikan bersama.
        </p>
        <a class="button" href="#species">
          Jelajahi Sekarang <span>↓</span>
        </a>
      </div>
    </section>

    <section class="container intro" id="species">
      <div class="section-label">Flora & Fauna</div>
      <h2>Keajaiban Nusantara</h2>
      <p>
        Setiap spesies memiliki keunikan, peran, dan cerita yang menjadikannya
        bagian penting dari kekayaan hayati Indonesia.
      </p>

      <div class="filters">
        <button class="filter-btn active" data-filter="all">Semua</button>
        <button class="filter-btn" data-filter="flora">Flora</button>
        <button class="filter-btn" data-filter="fauna">Fauna</button>
      </div>
    </section>

    <section class="container species-grid">
      <article class="card" data-type="flora">
        <div class="card-image">
          <img
            src="https://images.unsplash.com/photo-1649871675958-780ac69ded08?q=80&w=572&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
            alt="Bunga anggrek Bulan"
          />
          <span class="category">Flora</span>
        </div>
        <div class="card-body">
          <h3>Anggrek Bulan</h3>
          <div class="scientific">Phalaenopsis amabilis</div>
          <p class="card-description">
            Anggrek Bulan merupakan salah satu bunga yang menjadi kebanggaan
            Indonesia. Kelopaknya berwarna putih dengan bentuk menyerupai bulan.
            Bunga ini dikenal karena keindahan dan daya tahannya, serta banyak
            ditemukan di wilayah Indonesia beriklim tropis.
          </p>
          <div class="fact">
            <span>🌙</span>
            <div>
              <strong>Fun fact</strong>
              Ditetapkan sebagai salah satu bunga nasional Indonesia dengan
              sebutan <b>Puspa Pesona</b>.
            </div>
          </div>
        </div>
      </article>

      <article class="card" data-type="fauna">
        <div class="card-image">
          <img
            src="https://images.unsplash.com/photo-1648726442622-5cd3abeccaa8?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
            alt="Komodo"
          />
          <span class="category">Fauna</span>
        </div>
        <div class="card-body">
          <h3>Komodo</h3>
          <div class="scientific">Varanus komodoensis</div>
          <p class="card-description">
            Komodo adalah reptil endemik Indonesia yang terkenal sebagai kadal
            terbesar yang masih hidup. Komodo dapat ditemukan di beberapa pulau
            Nusa Tenggara, terutama di wilayah Taman Nasional Komodo.
          </p>
          <div class="fact">
            <span>🦎</span>
            <div>
              <strong>Fun fact</strong>
              Komodo dapat memiliki panjang sekitar 3 meter dan berat lebih
              dari 70 kg.
            </div>
          </div>
        </div>
      </article>

      <article class="card" data-type="flora">
        <div class="card-image">
          <img
            src="https://images.unsplash.com/photo-1654180467459-cb1948a82073?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
            alt="Bunga Rafflesia"
          />
          <span class="category">Flora</span>
        </div>
        <div class="card-body">
          <h3>Rafflesia arnoldii</h3>
          <div class="scientific">Rafflesia arnoldii</div>
          <p class="card-description">
            Rafflesia arnoldii merupakan flora unik Indonesia. Bunga ini
            berukuran sangat besar dan mengeluarkan aroma seperti daging
            membusuk. Rafflesia hidup sebagai tumbuhan parasit tanpa batang,
            daun, maupun akar.
          </p>
          <div class="fact">
            <span>🌺</span>
            <div>
              <strong>Fun fact</strong>
              Bunganya dapat memiliki diameter lebih dari 1 meter.
            </div>
          </div>
        </div>
      </article>

      <article class="card" data-type="fauna">
        <div class="card-image">
          <img
            src="https://images.unsplash.com/photo-1561731216-c3a4d99437d5?auto=format&fit=crop&w=1000&q=85"
            alt="Harimau Sumatera"
          />
          <span class="category">Fauna</span>
        </div>
        <div class="card-body">
          <h3>Harimau Sumatera</h3>
          <div class="scientific">Panthera tigris sumatrae</div>
          <p class="card-description">
            Harimau Sumatera adalah subspesies harimau yang hidup alami di Pulau
            Sumatera. Ukurannya relatif lebih kecil sehingga mampu bergerak di
            hutan yang lebat. Sebagai predator puncak, harimau ini berperan
            penting dalam menjaga keseimbangan ekosistem.
          </p>
          <div class="fact">
            <span>🐯</span>
            <div>
              <strong>Fun fact</strong>
              Harimau Sumatera merupakan satu-satunya populasi harimau yang
              masih bertahan di Indonesia.
            </div>
          </div>
        </div>
      </article>
    </section>

    <section class="closing" id="closing">
      <div class="container">
        <div class="section-label">Pesan Penutup</div>
        <h2>Warisan alam untuk masa depan</h2>
        <p>
          Keempatnya menunjukkan bahwa Indonesia bukan hanya kaya akan budaya,
          tetapi juga memiliki keanekaragaman flora dan fauna yang luar biasa.
          Dari indahnya Anggrek Bulan dan uniknya Rafflesia arnoldii hingga
          Komodo dan Harimau Sumatera yang menjadi bagian penting dari ekosistem,
          semuanya merupakan kekayaan alam yang perlu dikenal, dihargai, dan
          dilestarikan oleh generasi sekarang maupun yang akan datang.
        </p>
      </div>
    </section>
  </main>

  <footer>
    © 2026 Pride of Nusantara · Mari bersama melestarikan kekayaan alam Indonesia 🇮🇩
  </footer>

  <script>
    const header = document.getElementById("header");

    window.addEventListener("scroll", () => {
      header.classList.toggle("scrolled", window.scrollY > 30);
    });

    const buttons = document.querySelectorAll(".filter-btn");
    const cards = document.querySelectorAll(".card");

    buttons.forEach((button) => {
      button.addEventListener("click", () => {
        buttons.forEach((item) => item.classList.remove("active"));
        button.classList.add("active");

        const filter = button.dataset.filter;

        cards.forEach((card) => {
          const shouldShow =
            filter === "all" || card.dataset.type === filter;

          card.classList.toggle("hidden", !shouldShow);
        });
      });
    });
  </script>
</body>
</html>
