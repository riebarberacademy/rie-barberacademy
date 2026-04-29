# rie-barberacademy
baru
```html
<!DOCTYPE html>
<html lang="ms">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rie BarberAcademy - Kelas Asas Gunting Rambut Profesional</title>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;700;800&display=swap" rel="stylesheet">
    
    <style>
        /* CSS Vanilla - Custom Reset & Variables */
        :root {
            --primary-gold: #D4AF37;
            --primary-gold-hover: #F3CA4A;
            --dark-bg: #121212;
            --darker-bg: #0A0A0A;
            --card-bg: #1E1E1E;
            --text-light: #F5F5F5;
            --text-muted: #A0A0A0;
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
            font-family: 'Montserrat', sans-serif;
            background-color: var(--dark-bg);
            color: var(--text-light);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Typography */
        h1, h2, h3, h4 {
            font-weight: 800;
            line-height: 1.2;
        }

        .highlight {
            color: var(--primary-gold);
        }

        /* Layout */
        .container {
            width: 100%;
            max-width: 1100px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .text-center { text-align: center; }
        .mt-2 { margin-top: 1rem; }
        .mb-2 { margin-bottom: 1rem; }
        .mb-4 { margin-bottom: 2rem; }
        
        /* Navbar */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background-color: rgba(10, 10, 10, 0.95);
            backdrop-filter: blur(10px);
            padding: 15px 0;
            z-index: 100;
            border-bottom: 1px solid #333;
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 800;
            color: var(--text-light);
            text-decoration: none;
            letter-spacing: 1px;
        }

        /* Buttons */
        .btn {
            display: inline-block;
            padding: 15px 35px;
            font-size: 1.1rem;
            font-weight: 700;
            border-radius: 5px;
            text-decoration: none;
            text-transform: uppercase;
            cursor: pointer;
            transition: all 0.3s ease;
            border: none;
            text-align: center;
        }

        .btn-gold {
            background-color: var(--primary-gold);
            color: var(--darker-bg);
            box-shadow: 0 4px 15px rgba(212, 175, 55, 0.3);
        }

        .btn-gold:hover {
            background-color: var(--primary-gold-hover);
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(212, 175, 55, 0.5);
        }

        .btn-outline {
            border: 2px solid var(--primary-gold);
            color: var(--primary-gold);
            background: transparent;
            padding: 10px 25px;
            font-size: 0.9rem;
        }

        .btn-outline:hover {
            background: var(--primary-gold);
            color: var(--darker-bg);
        }

        /* Hero Section */
        .hero {
            padding-top: 120px;
            padding-bottom: 80px;
            min-height: 100vh;
            display: flex;
            align-items: center;
            background: linear-gradient(to bottom, rgba(10,10,10,0.8), rgba(18,18,18,1)), url('https://images.unsplash.com/photo-1503951914875-452162b0f3f1?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80') center/cover no-repeat;
            text-align: center;
        }

        .hero h1 {
            font-size: clamp(2.5rem, 5vw, 4rem);
            margin-bottom: 20px;
            text-shadow: 2px 2px 10px rgba(0,0,0,0.8);
        }

        .hero p {
            font-size: clamp(1.1rem, 2vw, 1.5rem);
            color: #ddd;
            max-width: 800px;
            margin: 0 auto 40px auto;
        }

        /* Section Styling */
        section {
            padding: 80px 0;
        }

        .section-title {
            font-size: 2.5rem;
            margin-bottom: 20px;
        }

        .section-subtitle {
            color: var(--text-muted);
            font-size: 1.1rem;
            max-width: 700px;
            margin: 0 auto 50px auto;
        }

        /* Problem Section */
        .bg-darker {
            background-color: var(--darker-bg);
        }

        .problem-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .problem-card {
            background: var(--card-bg);
            padding: 30px;
            border-radius: 10px;
            border-top: 4px solid #444;
            transition: transform 0.3s ease;
        }

        .problem-card:hover {
            transform: translateY(-5px);
            border-color: var(--primary-gold);
        }

        /* Modules/Benefits */
        .module-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }

        .module-item {
            background: var(--card-bg);
            padding: 25px;
            border-radius: 8px;
            display: flex;
            align-items: flex-start;
            gap: 15px;
            border: 1px solid #333;
        }

        .module-icon {
            font-size: 2rem;
            color: var(--primary-gold);
        }

        /* Gallery Section */
        .gallery-wrapper {
            position: relative;
            display: flex;
            align-items: center;
            max-width: 1000px;
            margin: 0 auto;
        }

        .gallery-container {
            display: flex;
            overflow-x: auto;
            scroll-snap-type: x mandatory;
            scroll-behavior: smooth;
            gap: 15px;
            padding: 20px 0;
            -ms-overflow-style: none; /* IE & Edge */
            scrollbar-width: none; /* Firefox */
        }

        .gallery-container::-webkit-scrollbar {
            display: none; /* Chrome, Safari & Opera */
        }

        .gallery-item {
            flex: 0 0 auto;
            width: 300px;
            height: 300px;
            object-fit: cover;
            border-radius: 10px;
            scroll-snap-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.5);
            border: 2px solid #333;
            transition: transform 0.3s ease;
        }

        .gallery-item:hover {
            transform: scale(1.05);
            border-color: var(--primary-gold);
        }

        .gallery-btn {
            background: var(--primary-gold);
            color: var(--darker-bg);
            border: none;
            width: 45px;
            height: 45px;
            border-radius: 50%;
            font-size: 1.5rem;
            font-weight: bold;
            cursor: pointer;
            position: absolute;
            z-index: 10;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 10px rgba(0,0,0,0.5);
            transition: all 0.3s;
        }

        .gallery-btn:hover {
            background: var(--primary-gold-hover);
            transform: scale(1.1);
        }

        .prev-btn { left: -20px; }
        .next-btn { right: -20px; }

        /* Testimonial Section */
        .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .testimonial-card {
            background: var(--darker-bg);
            padding: 30px;
            border-radius: 10px;
            border: 1px solid #333;
            position: relative;
        }
        
        .testimonial-card::before {
            content: '"';
            font-size: 4rem;
            color: rgba(212, 175, 55, 0.2);
            position: absolute;
            top: 10px;
            left: 20px;
            font-family: serif;
        }

        /* Lead Capture Form Section (The Core for Conversion) */
        .cta-section {
            background: linear-gradient(135deg, #1A1A1A 0%, #000000 100%);
            border-top: 2px solid var(--primary-gold);
            border-bottom: 2px solid var(--primary-gold);
            padding: 100px 0;
        }

        .form-container {
            background: var(--card-bg);
            max-width: 600px;
            margin: 0 auto;
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }

        .form-group {
            margin-bottom: 20px;
            text-align: left;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: #ddd;
        }

        .form-control {
            width: 100%;
            padding: 15px;
            background: var(--darker-bg);
            border: 1px solid #444;
            color: white;
            border-radius: 5px;
            font-size: 1rem;
            font-family: 'Montserrat', sans-serif;
            transition: border-color 0.3s;
        }

        .form-control:focus {
            outline: none;
            border-color: var(--primary-gold);
        }

        .form-submit-btn {
            width: 100%;
            margin-top: 10px;
        }

        /* Custom Success Message Box */
        .success-box {
            display: none;
            background: rgba(46, 204, 113, 0.1);
            border: 1px solid #2ecc71;
            padding: 30px;
            border-radius: 10px;
            text-align: center;
        }

        .success-box h3 {
            color: #2ecc71;
            margin-bottom: 10px;
        }

        /* Footer */
        footer {
            background: var(--darker-bg);
            padding: 40px 0;
            text-align: center;
            color: var(--text-muted);
            border-top: 1px solid #222;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero { padding-top: 100px; }
            .section-title { font-size: 2rem; }
            .form-container { padding: 25px; }
            nav .btn-outline { display: none; } /* Hide small button on mobile for cleaner look */
            .prev-btn, .next-btn { display: none; } /* Sembunyikan butang di mobile, bergantung pada swipe */
            .gallery-item { width: 250px; height: 250px; }
        }
    </style>
</head>
<body>

    <!-- Navigation -->
    <nav>
        <div class="container nav-container">
            <a href="#" class="logo">RIE <span class="highlight">BARBER</span>ACADEMY</a>
            <a href="#daftar" class="btn btn-outline">Daftar Sekarang</a>
        </div>
    </nav>

    <!-- Hero Section (Attention) -->
    <header class="hero">
        <div class="container">
            <h1>Ubah Minat Anda Menjadi <br><span class="highlight">Kerjaya Menguntungkan!</span></h1>
            <p>Sertai Kelas Asas Gunting Rambut Profesional dari kosong hingga pandai. Belajar teknik 'fade' moden, pengurusan kedai, dan jana pendapatan lumayan dalam masa kurang 4 minggu.</p>
            <a href="#daftar" class="btn btn-gold">Tempah Tempat Anda Sekarang</a>
            <p class="mt-2" style="font-size: 0.9rem; color: #aaa;">*Tempat sangat terhad. Pengambilan bulan ini hampir penuh.</p>
        </div>
    </header>

    <!-- Problem & Agitation Section (Interest) -->
    <section class="bg-darker text-center" id="masalah">
        <div class="container">
            <h2 class="section-title">Bosan Bekerja Makan Gaji?</h2>
            <p class="section-subtitle">Adakah anda menghadapi situasi di bawah? Jika ya, ini adalah petanda anda perlukan kemahiran baru yang kalis ekonomi.</p>
            
            <div class="problem-grid">
                <div class="problem-card">
                    <div class="module-icon mb-2">📉</div>
                    <h3>Gaji Tidak Cukup</h3>
                    <p class="mt-2 text-muted">Kos sara hidup semakin tinggi tapi gaji masih di takuk lama. Anda perlukan kemahiran yang boleh jana "side income" atau kerjaya sepenuh masa yang stabil.</p>
                </div>
                <div class="problem-card">
                    <div class="module-icon mb-2">🏢</div>
                    <h3>Tiada Kebebasan Masa</h3>
                    <p class="mt-2 text-muted">Terikat dengan waktu pejabat 9 pagi - 5 petang. Nak jadi 'boss' kepada diri sendiri dan kawal masa kerja anda?</p>
                </div>
                <div class="problem-card">
                    <div class="module-icon mb-2">✂️</div>
                    <h3>Minat Tapi Tak Tahu Bermula</h3>
                    <p class="mt-2 text-muted">Suka tengok video gunting rambut di TikTok/IG tapi tak tahu teknik sebenar, cara pegang mesin, atau cara layan pelanggan dengan betul.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Solution & Modules (Desire) -->
    <section id="modul">
        <div class="container">
            <div class="text-center">
                <h2 class="section-title">Kenapa Pilih <span class="highlight">Rie BarberAcademy?</span></h2>
                <p class="section-subtitle">Kami bukan sekadar mengajar cara potong rambut. Kami melatih anda menjadi seorang usahawan barber yang berjaya.</p>
            </div>

            <div class="module-list mt-2">
                <div class="module-item">
                    <div class="module-icon">💈</div>
                    <div>
                        <h4>Teknik Potongan Moden & Klasik</h4>
                        <p class="text-muted" style="font-size: 0.9rem; margin-top: 5px;">Kuasai teknik Zero Fade, Mid Fade, Taper, Pompadour, Crop dan banyak lagi. Dari asas hingga advance.</p>
                    </div>
                </div>
                <div class="module-item">
                    <div class="module-icon">🤲</div>
                    <div>
                        <h4>100% Praktikal (Hands-on)</h4>
                        <p class="text-muted" style="font-size: 0.9rem; margin-top: 5px;">Kurang teori yang membosankan. Anda akan terus berlatih menggunakan model sebenar di bawah pantauan tenaga pengajar.</p>
                    </div>
                </div>
                <div class="module-item">
                    <div class="module-icon">💼</div>
                    <div>
                        <h4>Peralatan Lengkap Disediakan</h4>
                        <p class="text-muted" style="font-size: 0.9rem; margin-top: 5px;">Tak perlu pening beli barang. Mesin Wahl, gunting, sikat - semuanya disediakan sepanjang sesi kelas.</p>
                    </div>
                </div>
                <div class="module-item">
                    <div class="module-icon">📜</div>
                    <div>
                        <h4>Sijil Penyertaan Profesional</h4>
                        <p class="text-muted" style="font-size: 0.9rem; margin-top: 5px;">Tingkatkan kredibiliti anda. Sijil akan diberikan sebagai bukti anda telah tamat latihan profesional.</p>
                    </div>
                </div>
                <div class="module-item">
                    <div class="module-icon">📈</div>
                    <div>
                        <h4>Bimbingan Bisnes & Pemasaran</h4>
                        <p class="text-muted" style="font-size: 0.9rem; margin-top: 5px;">Belajar cara nak buka kedai sendiri, cara set harga, dan tarik pelanggan baru menggunakan sosial media.</p>
                    </div>
                </div>
                <div class="module-item">
                    <div class="module-icon">🤝</div>
                    <div>
                        <h4>Peluang Pekerjaan Disediakan</h4>
                        <p class="text-muted" style="font-size: 0.9rem; margin-top: 5px;">Pelajar cemerlang akan diserap terus bekerja di cawangan Rie Barbershop atau dicadangkan ke rakan industri.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Gallery Section (Swipeable) -->
    <section class="text-center" id="galeri" style="border-top: 1px solid #222;">
        <div class="container">
            <h2 class="section-title">Galeri <span class="highlight">Akademi</span></h2>
            <p class="section-subtitle">Suasana kelas, sesi praktikal, dan hasil kerja pelajar kami.</p>

            <div class="gallery-wrapper">
                <button class="gallery-btn prev-btn" onclick="scrollGallery(-1)">&#10094;</button>
                <div class="gallery-container" id="galleryContainer">
                    <img src="https://images.unsplash.com/photo-1503951914875-452162b0f3f1?auto=format&fit=crop&w=400&q=80" alt="Galeri Barber 1" class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1585747860715-2ba37e788b70?auto=format&fit=crop&w=400&q=80" alt="Galeri Barber 2" class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1599351431202-1e0f0137899a?auto=format&fit=crop&w=400&q=80" alt="Galeri Barber 3" class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1621605815971-fbc98d665033?auto=format&fit=crop&w=400&q=80" alt="Galeri Barber 4" class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1593702275687-f8b402bf1fe5?auto=format&fit=crop&w=400&q=80" alt="Galeri Barber 5" class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1622286342621-4bd786c2447c?auto=format&fit=crop&w=400&q=80" alt="Galeri Barber 6" class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1605497788044-5a32c7078486?auto=format&fit=crop&w=400&q=80" alt="Galeri Barber 7" class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1512496015851-a1dc8e100fb6?auto=format&fit=crop&w=400&q=80" alt="Galeri Barber 8" class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1620331311520-246422fd82f9?auto=format&fit=crop&w=400&q=80" alt="Galeri Barber 9" class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1503951458645-643d53bfd90f?auto=format&fit=crop&w=400&q=80" alt="Galeri Barber 10" class="gallery-item">
                </div>
                <button class="gallery-btn next-btn" onclick="scrollGallery(1)">&#10095;</button>
            </div>
        </div>
    </section>

    <!-- Testimonials (Social Proof) -->
    <section class="bg-darker" id="testimoni">
        <div class="container text-center">
            <h2 class="section-title">Apa Kata <span class="highlight">Alumni Kami?</span></h2>
            <p class="section-subtitle">Mereka bermula dari kosong. Kini mereka bangga dengan kerjaya baru mereka.</p>

            <div class="testimonial-grid">
                <div class="testimonial-card text-left">
                    <p style="margin-bottom: 20px; position: relative; z-index: 1;">"Dulu kerja kilang, sekarang dah ada kerusi sendiri di barbershop. Kelas Rie Barber memang detail. Cikgu sangat sabar ajar walaupun tangan saya keras mulanya."</p>
                    <div style="display: flex; align-items: center; gap: 15px;">
                        <div style="width: 50px; height: 50px; background: #333; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-weight: bold; color: var(--primary-gold);">A</div>
                        <div>
                            <h4 style="font-size: 1rem;">Ahmad Faizal</h4>
                            <p class="highlight" style="font-size: 0.8rem;">Barber Sepenuh Masa</p>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card text-left">
                    <p style="margin-bottom: 20px; position: relative; z-index: 1;">"Modul bisnes dia mahal! Bukan setakat ajar fade je, tapi ajar macam mana nak layan customer sampai dia repeat. Bulan pertama habis kelas terus dapat job."</p>
                    <div style="display: flex; align-items: center; gap: 15px;">
                        <div style="width: 50px; height: 50px; background: #333; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-weight: bold; color: var(--primary-gold);">K</div>
                        <div>
                            <h4 style="font-size: 1rem;">Khairul Anwar</h4>
                            <p class="highlight" style="font-size: 0.8rem;">Freelance Barber</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Lead Capture Form (Action) -->
    <section class="cta-section text-center" id="daftar">
        <div class="container">
            <h2 class="section-title">Mula Langkah Pertama Anda Hari Ini!</h2>
            <p class="section-subtitle" style="color: white;">Daftar minat anda sekarang untuk menerima <span class="highlight" style="font-weight: bold; font-size: 1.2rem;">Diskaun Early Bird 20%</span> dan risalah modul kelas secara PERCUMA melalui WhatsApp.</p>

            <div class="form-container" id="leadFormWrapper">
                <form id="leadForm">
                    <div class="form-group">
                        <label for="fullName">Nama Penuh</label>
                        <input type="text" id="fullName" class="form-control" placeholder="Masukkan nama penuh anda" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="phoneNum">Nombor WhatsApp</label>
                        <input type="tel" id="phoneNum" class="form-control" placeholder="Cth: 0123456789" required>
                    </div>

                    <div class="form-group">
                        <label for="email">Alamat E-mel</label>
                        <input type="email" id="email" class="form-control" placeholder="Cth: anda@email.com" required>
                    </div>

                    <div class="form-group" style="margin-top: 10px;">
                        <label style="display: flex; align-items: center; gap: 10px; font-weight: normal; font-size: 0.9rem; cursor: pointer;">
                            <input type="checkbox" required> Saya bersetuju untuk dihubungi oleh pihak Rie BarberAcademy.
                        </label>
                    </div>

                    <button type="submit" class="btn btn-gold form-submit-btn">Dapatkan Diskaun & Modul Sekarang</button>
                    <p style="font-size: 0.8rem; color: #888; margin-top: 15px;">Maklumat anda selamat dan tidak akan dikongsi kepada pihak ketiga (No Spam).</p>
                </form>
            </div>

            <!-- Custom Message Box for Success (Replaces window.alert) -->
            <div id="successMessage" class="success-box" style="max-width: 600px; margin: 0 auto;">
                <h3>🎉 Tahniah! Pendaftaran Berjaya.</h3>
                <p>Terima kasih kerana berminat dengan Rie BarberAcademy. Pasukan kami akan menghubungi anda melalui WhatsApp sebentar lagi beserta diskaun 20% dan risalah modul.</p>
                <button class="btn btn-outline mt-2" onclick="resetForm()" style="margin-top: 20px;">Tutup & Kembali</button>
            </div>

        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <h3 class="highlight mb-2">Rie BarberAcademy</h3>
            <p>Melahirkan Barber Profesional Berkualiti Sejak 2020.</p>
            <p class="mt-2" style="font-size: 0.8rem; color: #666;">&copy; 2026 Rie BarberAcademy. Hak Cipta Terpelihara.</p>
        </div>
    </footer>

    <!-- JavaScript Vanilla -->
    <script>
        // Handle Form Submission for Lead Capture
        const leadForm = document.getElementById('leadForm');
        const formWrapper = document.getElementById('leadFormWrapper');
        const successMessage = document.getElementById('successMessage');

        leadForm.addEventListener('submit', function(e) {
            e.preventDefault(); // Prevent page reload
            
            // Get values (In a real app, you would send this to a backend/CRM API via fetch)
            const name = document.getElementById('fullName').value;
            const phone = document.getElementById('phoneNum').value;
            const email = document.getElementById('email').value;

            // Log output to console for demo purpose
            console.log('Lead Baru Diterima:');
            console.log('Nama:', name);
            console.log('Telefon:', phone);
            console.log('Email:', email);

            // Hide form, show custom success message box
            formWrapper.style.display = 'none';
            successMessage.style.display = 'block';
        });

        // Function to reset the form and state
        function resetForm() {
            leadForm.reset();
            successMessage.style.display = 'none';
            formWrapper.style.display = 'block';
        }

        // Add sticky effect to navbar when scrolling
        window.addEventListener('scroll', function() {
            const nav = document.querySelector('nav');
            if (window.scrollY > 50) {
                nav.style.boxShadow = '0 2px 10px rgba(0,0,0,0.5)';
            } else {
                nav.style.boxShadow = 'none';
            }
        });

        // Function untuk scroll Galeri (Desktop Buttons)
        function scrollGallery(direction) {
            const container = document.getElementById('galleryContainer');
            // Dapatkan lebar item + gap (anggaran 315px di desktop)
            const item = document.querySelector('.gallery-item');
            const scrollAmount = item.offsetWidth + 15; 
            container.scrollBy({ left: scrollAmount * direction, behavior: 'smooth' });
        }
    </script>
</body>
</html>


```
