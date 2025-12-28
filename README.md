<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Elite Team PJBL</title>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;500;800&family=Playfair+Display:ital,wght@1,700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root {
            --bg: #05070a;
            --card-bg: rgba(255, 255, 255, 0.03);
            --border: rgba(255, 255, 255, 0.08);
            --accent: #c5a358; /* Gold Champagne - Elegan, bukan neon */
            --text: #ffffff;
            --text-dim: #94a3b8;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            outline: none;
        }

        body {
            background-color: var(--bg);
            color: var(--text);
            font-family: 'Plus Jakarta Sans', sans-serif;
            overflow-x: hidden;
            line-height: 1.6;
        }

        /* ----- BACKGROUND LIGHT EFFECT ----- */
        #cursor-glow {
            position: fixed;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(197, 163, 88, 0.1) 0%, transparent 70%);
            border-radius: 50%;
            pointer-events: none;
            transform: translate(-50%, -50%);
            z-index: 0;
            transition: width 0.3s, height 0.3s;
        }

        .content-wrapper {
            position: relative;
            z-index: 1;
            padding: 40px 20px;
        }

        /* ----- LOGO & NAV ----- */
        nav {
            max-width: 1200px;
            margin: 0 auto 80px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .brand-logo {
            font-weight: 800;
            font-size: 1.2rem;
            letter-spacing: 2px;
            color: var(--accent);
            text-transform: uppercase;
        }

        /* ----- HERO ----- */
        .hero {
            text-align: center;
            margin-bottom: 100px;
        }

        .hero h1 {
            font-size: clamp(2.5rem, 8vw, 5rem);
            font-weight: 800;
            line-height: 1;
            margin-bottom: 20px;
        }

        .hero h1 em {
            font-family: 'Playfair Display', serif;
            color: var(--accent);
        }

        /* ----- GRID SYSTEM ----- */
        .container {
            max-width: 1100px;
            margin: 0 auto;
        }

        /* KETUA (LEADER) - FULL DESIGN */
        .leader-section {
            display: flex;
            justify-content: center;
            margin-bottom: 60px;
        }

        .leader-card {
            background: linear-gradient(145deg, rgba(255,255,255,0.05) 0%, rgba(255,255,255,0) 100%);
            border: 1px solid var(--border);
            border-radius: 40px;
            padding: 50px;
            width: 100%;
            max-width: 800px;
            display: grid;
            grid-template-columns: 250px 1fr;
            gap: 40px;
            align-items: center;
            backdrop-filter: blur(10px);
            position: relative;
            box-shadow: 0 20px 50px rgba(0,0,0,0.5);
        }

        .leader-card:hover {
            border-color: var(--accent);
        }

        /* Foto Ketua */
        .leader-img {
            width: 250px;
            height: 300px;
            border-radius: 25px;
            object-fit: cover;
            filter: grayscale(100%);
            transition: 0.5s;
            border: 1px solid var(--border);
        }

        .leader-card:hover .leader-img {
            filter: grayscale(0%);
            transform: scale(1.02);
        }

        .leader-info h2 {
            font-size: 2.5rem;
            margin-bottom: 5px;
        }

        .leader-info .role {
            color: var(--accent);
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 2px;
            font-size: 0.8rem;
            margin-bottom: 20px;
            display: block;
        }

        .leader-info p {
            color: var(--text-dim);
            margin-bottom: 30px;
            font-size: 1rem;
        }

        .leader-socials {
            display: flex;
            gap: 15px;
        }

        .leader-socials a {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            border: 1px solid var(--border);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-decoration: none;
            transition: 0.3s;
        }

        .leader-socials a:hover {
            background: var(--accent);
            color: #000;
            border-color: var(--accent);
        }

        /* ANGGOTA GRID */
        .member-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
        }

        .member-card {
            background: var(--card-bg);
            border: 1px solid var(--border);
            border-radius: 30px;
            padding: 30px;
            text-align: center;
            transition: 0.4s;
        }

        .member-card:hover {
            background: rgba(255,255,255,0.06);
            transform: translateY(-10px);
        }

        .member-icon {
            font-size: 2rem;
            color: var(--accent);
            margin-bottom: 20px;
            opacity: 0.7;
        }

        .member-card h3 {
            font-size: 1.1rem;
            margin-bottom: 5px;
        }

        .member-card p {
            color: var(--text-dim);
            font-size: 0.8rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* FOOTER / BOTTOM */
        .footer-cta {
            margin-top: 120px;
            text-align: center;
            padding: 100px 20px;
            border-top: 1px solid var(--border);
        }

        .footer-cta h2 {
            font-family: 'Playfair Display', serif;
            font-size: 3rem;
            margin-bottom: 20px;
        }

        .btn-mail {
            display: inline-block;
            padding: 18px 40px;
            background: var(--accent);
            color: #000;
            text-decoration: none;
            border-radius: 100px;
            font-weight: 800;
            margin-top: 20px;
            transition: 0.3s;
        }

        .btn-mail:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 30px rgba(197, 163, 88, 0.3);
        }

        /* RESPONSIVE HP */
        @media (max-width: 850px) {
            .leader-card {
                grid-template-columns: 1fr;
                padding: 30px;
                text-align: center;
            }
            .leader-img {
                width: 100%;
                height: 350px;
                margin: 0 auto;
            }
            .leader-socials { justify-content: center; }
            .member-grid { grid-template-columns: repeat(2, 1fr); }
        }

        @media (max-width: 500px) {
            .member-grid { grid-template-columns: 1fr; }
            .hero h1 { font-size: 3rem; }
        }
    </style>
</head>
<body>

    <div id="cursor-glow"></div>

    <div class="content-wrapper">
        <nav>
            <div class="brand-logo">PJBL TEAM</div>
            <div style="font-size: 0.7rem; opacity: 0.5;">Reizo</div>
        </nav>

        <section class="hero">
            <p style="text-transform: uppercase; letter-spacing: 4px; font-size: 0.7rem; margin-bottom: 10px; color: var(--accent);">this is my team</p>
            <h1>Project <em>PJBL</em> Yayubi.</h1>
        </section>

        <div class="container">
            <div class="leader-section">
                <div class="leader-card">
                    <img src="images wajah_foto.jpg.jpg" alt="Leader" class="leader-img">
                    <div class="leader-info">
                        <span class="role"></span>
                        <h2>Reizo Rajendra Dianta</h2>
                        <p>Memimpin tim web mengajarkanku ketelitian. Menjadi YouTuber mengajarkanku keberanian. itulah caraku menjadi confident</p>
                        <div class="leader-socials">
                            <a href="https://www.instagram.com/reizo_rajendra?igsh=MWxoeTlmcWt6YzRuaw=="><i class="fab fa-instagram"></i></a>
                            <a href="https://www.youtube.com/@ZEARS_GAMINg"><i class="fab fa-youtube"></i></a>
                            <a href="https://www.tiktok.com/@zearsg?_r=1&_t=ZS-92bGJwwQMA1"><i class="fab fa-tiktok"></i></a>
                        </div>
                    </div>
                </div>
            </div>

            <div class="member-grid">
                <div class="member-card">
                    <div class="member-icon"><i class="fas fa-terminal"></i></div>
                    <h3>Cahaya Fitri Darmawan</h3>
                    <p>Anggota</p>
                </div>
                <div class="member-card">
                    <div class="member-icon"><i class="fas fa-bezier-curve"></i></div>
                    <h3>Diva Risnu Windy Wulandary</h3>
                    <p>Anggota</p>
                </div>
                <div class="member-card">
                    <div class="member-icon"><i class="fas fa-video"></i></div>
                    <h3>Fanezza Anandita Putri</h3>
                    <p>Anggota</p>
                </div>
                <div class="member-card">
                    <div class="member-icon"><i class="fas fa-hashtag"></i></div>
                    <h3>Ibanisa Dewi Pratiwi</h3>
                    <p>Anggota</p>
                </div>
                <div class="member-card">
                    <div class="member-icon"><i class="fas fa-code"></i></div>
                    <h3>Ubaydilla Alvaro Gibran Syahpalevi </h3>
                    <p>Anggota</p>
                </div>
                <div class="member-card">
                    <div class="member-icon"><i class="fas fa-shield-halved"></i></div>
                    <h3>Reizo Rajendra Dianta</h3>
                    <p>Full stack &QA Engineer</p>
                </div>
            </div>
        </div>

        <section class="footer-cta">
            <h2> Code together,  <em>grow together</em>.</h2>
            <p>Seluruh proses PJBL kami.</p>
            <a href="" class="btn-mail">LINK YOUTUBE REIZO</a>
        </section>
    </div>

    <script>
        // Efek Lampu Mengikuti Kursor
        const glow = document.getElementById('cursor-glow');
        document.addEventListener('mousemove', (e) => {
            glow.style.left = e.clientX + 'px';
            glow.style.top = e.clientY + 'px';
        });

        // Reveal on Scroll
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = 1;
                    entry.target.style.transform = "translateY(0)";
                }
            });
        }, { threshold: 0.1 });

        document.querySelectorAll('.member-card, .leader-card').forEach(el => {
            el.style.opacity = 0;
            el.style.transform = "translateY(40px)";
            el.style.transition = "all 0.8s cubic-bezier(0.16, 1, 0.3, 1)";
            observer.observe(el);
        });
    </script>
</body>
</html>
