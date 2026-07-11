# erx-01-portofolio-web
Website portofolio pribadi saya.<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portofolio Erix Maulana Musa</title>
    <!-- Google Fonts & Font Awesome Icons -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root {
            --bg-color: #0d0e12;
            --card-bg: rgba(255, 255, 255, 0.03);
            --card-hover: rgba(255, 255, 255, 0.06);
            --border-color: rgba(255, 255, 255, 0.08);
            --accent-color: #ff9f43;
            --accent-glow: rgba(255, 159, 67, 0.3);
            --text-main: #ffffff;
            --text-muted: #9ca3af;
            --success-color: #10b981;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-main);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: flex-start;
            padding: 24px 16px;
            overflow-x: hidden;
            position: relative;
        }

        /* Efek Kilau Latar Belakang */
        body::before {
            content: '';
            position: absolute;
            top: -10%;
            right: -10%;
            width: 350px;
            height: 350px;
            background: radial-gradient(circle, rgba(255, 159, 67, 0.12) 0%, rgba(0,0,0,0) 70%);
            border-radius: 50%;
            z-index: 0;
            pointer-events: none;
        }

        .container {
            max-width: 480px;
            width: 100%;
            background: rgba(18, 20, 26, 0.65);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid var(--border-color);
            border-radius: 28px;
            padding: 28px 20px;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.7);
            z-index: 1;
            position: relative;
        }

        /* Kartu Profil */
        .profile-card {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            background: linear-gradient(180deg, rgba(255, 255, 255, 0.02) 0%, rgba(255, 255, 255, 0) 100%);
            border: 1px solid rgba(255, 255, 255, 0.04);
            padding: 24px 16px;
            border-radius: 24px;
            margin-bottom: 28px;
        }

        .avatar-glow {
            position: relative;
            width: 110px;
            height: 110px;
            border-radius: 50%;
            padding: 3px;
            background: linear-gradient(135deg, var(--accent-color), #ff5252);
            box-shadow: 0 0 20px rgba(255, 159, 67, 0.4);
            margin-bottom: 16px;
        }

        .avatar-glow img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 50%;
            background: #1e1e24;
        }

        .profile-info h1 {
            font-size: 1.4rem;
            font-weight: 700;
            letter-spacing: 0.3px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 6px;
        }

        .profile-info h1 i {
            color: #4bc0c0;
            font-size: 1.1rem;
        }

        .profile-info .tagline {
            font-size: 0.85rem;
            color: var(--text-muted);
            margin-top: 6px;
            line-height: 1.4;
        }

        .section {
            margin-bottom: 28px;
        }

        h2 {
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            color: var(--accent-color);
            margin-bottom: 14px;
            display: flex;
            align-items: center;
            gap: 8px;
            font-weight: 600;
        }

        /* Pendidikan */
        .education-timeline {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .edu-item {
            background: var(--card-bg);
            border-left: 3px solid var(--accent-color);
            padding: 12px 16px;
            border-radius: 0 16px 16px 0;
            border: 1px solid rgba(255,255,255,0.02);
            transition: background 0.3s;
        }

        .edu-item:hover {
            background: var(--card-hover);
        }

        .edu-title {
            font-weight: 600;
            font-size: 0.9rem;
        }

        .edu-year {
            font-size: 0.75rem;
            color: var(--text-muted);
            margin-top: 3px;
            display: flex;
            align-items: center;
            gap: 4px;
        }

        /* Grid Keahlian */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
        }

        .skill-card {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            padding: 14px 8px;
            border-radius: 16px;
            text-align: center;
            font-size: 0.78rem;
            font-weight: 500;
            transition: all 0.3s ease;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 8px;
        }

        .skill-card:hover {
            border-color: var(--accent-color);
            background: rgba(255, 159, 67, 0.04);
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(255, 159, 67, 0.15);
        }

        .skill-card i {
            font-size: 1.5rem;
            color: var(--accent-color);
        }

        /* List Bahasa */
        .lang-list {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .lang-card {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            padding: 12px 16px;
            border-radius: 14px;
            font-size: 0.85rem;
        }

        .lang-name {
            display: flex;
            align-items: center;
            gap: 8px;
            font-weight: 500;
        }

        .lang-level {
            color: var(--accent-color);
            font-size: 0.75rem;
            background: rgba(255, 159, 67, 0.12);
            padding: 4px 10px;
            border-radius: 20px;
            font-weight: 600;
        }

        /* Status Aktif */
        .status-container {
            background: rgba(16, 185, 129, 0.06);
            border: 1px dashed rgba(16, 185, 129, 0.3);
            border-radius: 16px;
            padding: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            font-size: 0.85rem;
            font-weight: 500;
            color: #10b981;
        }

        .status-dot {
            width: 8px;
            height: 8px;
            background-color: #10b981;
            border-radius: 50%;
            box-shadow: 0 0 10px #10b981;
            animation: pulse 1.8s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(0.95); box-shadow: 0 0 0 0 rgba(16, 185, 129, 0.5); }
            70% { transform: scale(1); box-shadow: 0 0 0 8px rgba(16, 185, 129, 0); }
            100% { transform: scale(0.95); box-shadow: 0 0 0 0 rgba(16, 185, 129, 0); }
        }
    </style>
</head>
<body>

    <div class="container">
        <!-- Profile Utama -->
        <div class="profile-card">
            <div class="avatar-glow">
                <!-- Foto Anda sudah tertanam otomatis di file unduhan atas -->
                <img src="FOTO_PROFIL_ANDA_ADA_DI_SINI" alt="Erix Maulana Musa">
            </div>
            <div class="profile-info">
                <h1>Erix Maulana Musa <i class="fa-solid fa-circle-check"></i></h1>
                <p class="tagline">Kreatif, disiplin, dan siap mengeksplorasi tantangan baru di dunia digital & industri.</p>
            </div>
        </div>

        <!-- Riwayat Pendidikan -->
        <div class="section">
            <h2><i class="fa-solid fa-graduation-cap"></i> Pendidikan</h2>
            <div class="education-timeline">
                <div class="edu-item">
                    <div class="edu-title">MA Negeri 1 Nganjuk</div>
                    <div class="edu-year"><i class="fa-regular fa-calendar"></i> 2023 - 2026</div>
                </div>
                <div class="edu-item">
                    <div class="edu-title">MTS Al Fatah</div>
                    <div class="edu-year"><i class="fa-regular fa-calendar"></i> 2020 - 2023</div>
                </div>
                <div class="edu-item">
                    <div class="edu-title">MI Negeri 12 Lanji</div>
                    <div class="edu-year"><i class="fa-regular fa-calendar"></i> 2014 - 2020</div>
                </div>
            </div>
        </div>

        <!-- Keahlian Software -->
        <div class="section">
            <h2><i class="fa-solid fa-wand-magic-sparkles"></i> Software Skills</h2>
            <div class="skills-grid">
                <div class="skill-card">
                    <i class="fa-solid fa-bezier-curve"></i>
                    <span>Canva</span>
                </div>
                <div class="skill-card">
                    <i class="fa-solid fa-video"></i>
                    <span>CapCut</span>
                </div>
                <div class="skill-card">
                    <i class="fa-solid fa-clapperboard"></i>
                    <span>Alight Motion</span>
                </div>
            </div>
        </div>

        <!-- Keahlian Gaming -->
        <div class="section">
            <h2><i class="fa-solid fa-gamepad"></i> Game Skills</h2>
            <div class="skills-grid">
                <div class="skill-card">
                    <i class="fa-solid fa-crosshairs"></i>
                    <span>PUBG</span>
                </div>
                <div class="skill-card">
                    <i class="fa-solid fa-shield-halved"></i>
                    <span>Mobile Legends</span>
                </div>
                <div class="skill-card">
                    <i class="fa-solid fa-fire"></i>
                    <span>Free Fire</span>
                </div>
            </div>
        </div>

        <!-- Kemampuan Bahasa -->
        <div class="section">
            <h2><i class="fa-solid fa-language"></i> Kemampuan Bahasa</h2>
            <div class="lang-list">
                <div class="lang-card">
                    <div class="lang-name"><i class="fa-solid fa-earth-asia"></i> Bahasa Jepang</div>
                    <span class="lang-level">Aktif / Komunikasi</span>
                </div>
                <div class="lang-card">
                    <div class="lang-name"><i class="fa-solid fa-comments"></i> Bahasa Inggris</div>
                    <span class="lang-level">Sehari-hari</span>
                </div>
            </div>
        </div>

        <!-- Status -->
        <div class="section">
            <div class="status-container">
                <div class="status-dot"></div>
                <span>Tersedia untuk Kerja Sama & Kesempatan Baru</span>
            </div>
        </div>

        <div style="text-align: center; font-size: 0.78rem; color: var(--text-muted); border-top: 1px solid var(--border-color); padding-top: 20px;">
            © 2026 Erix Maulana Musa. All rights reserved.
        </div>
    </div>

</body>
</html>

