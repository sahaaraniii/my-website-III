# my-website-III

<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Perkenalan Diri | Saharani</title>

    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: #f2f8f2;
            color: #234b36;
            overflow-x: hidden;
        }

        /* NAVBAR */
        nav {
            width: 100%;
            padding: 20px 8%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(255,255,255,0.9);
            backdrop-filter: blur(10px);
            position: fixed;
            top: 0;
            z-index: 100;
            box-shadow: 0 3px 15px rgba(0,0,0,0.05);
        }

        .logo {
            font-size: 25px;
            font-weight: 800;
            color: #16834c;
        }

        .logo span {
            color: #a4c639;
        }

        nav ul {
            display: flex;
            gap: 30px;
            list-style: none;
        }

        nav ul li a {
            text-decoration: none;
            color: #315b42;
            font-weight: 500;
            transition: 0.3s;
        }

        nav ul li a:hover {
            color: #20a45e;
        }

        /* HERO */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 130px 8% 70px;
            background: linear-gradient(135deg, #e4f5e8, #f7fff7);
            position: relative;
            overflow: hidden;
        }

        .hero-content {
            text-align: center;
            max-width: 750px;
            z-index: 2;
            animation: fadeUp 1.2s ease;
        }

        .hero h4 {
            color: #23965b;
            letter-spacing: 3px;
            margin-bottom: 15px;
        }

        .hero h1 {
            font-size: clamp(42px, 8vw, 75px);
            color: #176b40;
            font-weight: 800;
        }

        .hero h1 span {
            color: #9cbd36;
        }

        .hero p {
            font-size: 17px;
            line-height: 1.9;
            margin: 20px 0 30px;
            color: #55725e;
        }

        .btn {
            display: inline-block;
            padding: 13px 30px;
            background: #16834c;
            color: white;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: 0.3s;
            box-shadow: 0 8px 20px rgba(22,131,76,0.2);
        }

        .btn:hover {
            background: #0d6135;
            transform: translateY(-5px);
        }

        /* DECORATION */
        .circle {
            position: absolute;
            border-radius: 50%;
            background: rgba(117, 182, 117, 0.13);
            animation: floating 5s infinite ease-in-out;
        }

        .circle.one {
            width: 250px;
            height: 250px;
            top: 15%;
            left: -80px;
        }

        .circle.two {
            width: 180px;
            height: 180px;
            bottom: 10%;
            right: -40px;
            animation-delay: 1s;
        }

        .leaf {
            position: absolute;
            font-size: 45px;
            opacity: 0.3;
            animation: floating 4s infinite ease-in-out;
        }

        .leaf.one {
            top: 22%;
            right: 15%;
        }

        .leaf.two {
            bottom: 20%;
            left: 12%;
            animation-delay: 2s;
        }

        /* ABOUT */
        section {
            padding: 90px 8%;
        }

        .section-title {
            text-align: center;
            margin-bottom: 45px;
        }

        .section-title h2 {
            font-size: 35px;
            color: #176b40;
        }

        .section-title p {
            color: #78927d;
            margin-top: 10px;
        }

        .about-box {
            max-width: 900px;
            margin: auto;
            background: white;
            padding: 40px;
            border-radius: 25px;
            box-shadow: 0 10px 35px rgba(25,90,50,0.08);
            text-align: center;
            line-height: 2;
            transition: 0.4s;
        }

        .about-box:hover {
            transform: translateY(-8px);
        }

        .about-box .emoji {
            font-size: 55px;
            margin-bottom: 15px;
        }

        /* BIODATA */
        .biodata {
            background: #e8f4e9;
        }

        .card-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 25px;
            max-width: 1000px;
            margin: auto;
        }

        .card {
            background: white;
            padding: 30px 20px;
            border-radius: 20px;
            text-align: center;
            box-shadow: 0 8px 25px rgba(0,0,0,0.04);
            transition: 0.4s;
            border-bottom: 4px solid #8fbd55;
        }

        .card:hover {
            transform: translateY(-12px);
            box-shadow: 0 15px 30px rgba(22,131,76,0.13);
        }

        .card .icon {
            font-size: 40px;
            margin-bottom: 15px;
        }

        .card h3 {
            color: #16834c;
            margin-bottom: 10px;
        }

        .card p {
            font-size: 14px;
            color: #69816e;
            line-height: 1.8;
        }

        /* MOTIVATION */
        .motivation {
            text-align: center;
            background: linear-gradient(135deg, #176b40, #27965b);
            color: white;
        }

        .motivation h2 {
            font-size: 30px;
            margin-bottom: 20px;
        }

        .motivation p {
            max-width: 700px;
            margin: auto;
            line-height: 2;
            color: #e1f4e6;
        }

        .heart {
            font-size: 35px;
            margin-top: 20px;
            animation: heartbeat 1.5s infinite;
        }

        /* FOOTER */
        footer {
            text-align: center;
            padding: 25px;
            background: #124d30;
            color: #d6ebda;
            font-size: 13px;
        }

        /* ANIMATION */
        @keyframes fadeUp {
            from {
                opacity: 0;
                transform: translateY(40px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes floating {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-20px);
            }
        }

        @keyframes heartbeat {
            0%, 100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.2);
            }
        }

        .reveal {
            opacity: 0;
            transform: translateY(35px);
            transition: all 0.8s ease;
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* RESPONSIVE HP */
        @media(max-width: 600px) {
            nav {
                padding: 15px 5%;
            }

            nav ul {
                gap: 12px;
            }

            nav ul li a {
                font-size: 11px;
            }

            .logo {
                font-size: 20px;
            }

            .hero p {
                font-size: 14px;
            }

            section {
                padding: 70px 6%;
            }

            .about-box {
                padding: 25px;
            }

            .section-title h2 {
                font-size: 28px;
            }
        }
    </style>
</head>

<body>

    <!-- NAVBAR -->
    <nav>
        <div class="logo">Saha<span>rani.</span></div>

        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#biodata">Biodata</a></li>
        </ul>
    </nav>

    <!-- HERO -->
    <section class="hero" id="home">

        <div class="circle one"></div>
        <div class="circle two"></div>

        <div class="leaf one">🌿</div>
        <div class="leaf two">🍃</div>

        <div class="hero-content">
            <h4>WELCOME TO MY PERSONAL WEBSITE</h4>

            <h1>HELLO, I'M <span>SAHARANI</span></h1>

            <p>
                Halo semuanya! 👋<br>
                Perkenalkan, nama saya Saharani.
                Saya dari kelas TRPL B.
                Senang berkenalan dengan Anda semua!
                Semoga kita bisa saling mengenal dan berbagi pengalaman.
            </p>

            <a href="#about" class="btn">Kenali Saya Lebih Dekat ✨</a>
        </div>

    </section>

    <!-- ABOUT -->
    <section id="about">

        <div class="section-title reveal">
            <h2>About Me 🌱</h2>
            <p>Sedikit cerita tentang diri saya</p>
        </div>

        <div class="about-box reveal">
            <div class="emoji">🌻</div>

            <p>
                Halo! Saya <b>Saharani</b>, seorang mahasiswa
                yang sedang menempuh pendidikan di
                <b>Politeknik Indonusa Surakarta</b>.

                Saya merupakan lulusan SMK Muhammadiyah Sumpiuh.
                Saat ini saya berada di kelas <b>TRPL B</b>.

                Saya senang mempelajari hal-hal baru,
                mendapatkan pengalaman, bertemu teman baru,
                dan mengembangkan kemampuan diri.
                Mari bersama-sama belajar dan berkembang!
            </p>
        </div>

    </section>

    <!-- BIODATA -->
    <section class="biodata" id="biodata">

        <div class="section-title reveal">
            <h2>My Biodata 🍀</h2>
            <p>Informasi singkat tentang saya</p>
        </div>

        <div class="card-container">

            <div class="card reveal">
                <div class="icon">👩</div>
                <h3>Nama</h3>
                <p>Saharani</p>
            </div>

            <div class="card reveal">
                <div class="icon">🎓</div>
                <h3>Kelas</h3>
                <p>TRPL B</p>
            </div>

            <div class="card reveal">
                <div class="icon">📍</div>
                <h3>Asal</h3>
                <p>Pacitan, Jawa Timur</p>
            </div>

            <div class="card reveal">
                <div class="icon">🏫</div>
                <h3>Asal Sekolah</h3>
                <p>SMK Muhammadiyah Sumpiuh</p>
            </div>

            <div class="card reveal">
                <div class="icon">📚</div>
                <h3>Pendidikan Sekarang</h3>
                <p>Politeknik Indonusa Surakarta</p>
            </div>

            <div class="card reveal">
                <div class="icon">💻</div>
                <h3>Status</h3>
                <p>Mahasiswa</p>
            </div>

        </div>

    </section>

    <!-- MOTIVATION -->
    <section class="motivation">

        <h2 class="reveal">Keep Learning, Keep Growing! 🌿</h2>

        <p class="reveal">
            "Jangan takut mencoba hal baru,
            karena setiap langkah kecil adalah bagian
            dari perjalanan menuju kesuksesan."

            <br><br>

            Terima kasih sudah mengunjungi website perkenalan saya.
            Senang berkenalan dengan Anda semua!
        </p>

        <div class="heart">💚</div>

    </section>

    <!-- FOOTER -->
    <footer>
        <p>© 2026 Saharani | My Personal Website 🌿</p>
        <p>Made with 💚 and Creativity</p>
    </footer>

    <!-- JAVASCRIPT -->
    <script>

        // ANIMASI SAAT SCROLL
        const reveals = document.querySelectorAll(".reveal");

        function revealOnScroll() {
            reveals.forEach(element => {
                const windowHeight = window.innerHeight;
                const elementTop = element.getBoundingClientRect().top;
                const visible = 100;

                if (elementTop < windowHeight - visible) {
                    element.classList.add("active");
                }
            });
        }

        window.addEventListener("scroll", revealOnScroll);

        // JALANKAN SAAT HALAMAN DIBUKA
        revealOnScroll();

    </script>

</body>
</html>
