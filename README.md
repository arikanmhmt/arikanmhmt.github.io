<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Modern Website</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary-color: #2563eb;
            --secondary-color: #1e40af;
            --bg-light: #ffffff;
            --bg-dark: #1a1a1a;
            --text-light: #1f2937;
            --text-dark: #e5e7eb;
            --sidebar-light: #f3f4f6;
            --sidebar-dark: #262626;
            --card-light: #ffffff;
            --card-dark: #333333;
            --hover-light: #f3f4f6;
            --hover-dark: #404040;
        }

        [data-theme="dark"] {
            --bg-color: var(--bg-dark);
            --text-color: var(--text-dark);
            --sidebar-bg: var(--sidebar-dark);
            --card-bg: var(--card-dark);
            --hover-bg: var(--hover-dark);
        }

        [data-theme="light"] {
            --bg-color: var(--bg-light);
            --text-color: var(--text-light);
            --sidebar-bg: var(--sidebar-light);
            --card-bg: var(--card-light);
            --hover-bg: var(--hover-light);
        }

        body {
            line-height: 1.6;
            color: var(--text-color);
            background-color: var(--bg-color);
            display: flex;
            min-height: 100vh;
            transition: background-color 0.3s, color 0.3s;
        }

        .sidebar {
            width: 250px;
            background-color: var(--sidebar-bg);
            padding: 2rem 1rem;
            position: fixed;
            height: 100vh;
            box-shadow: 2px 0 4px rgba(0,0,0,0.1);
            transition: background-color 0.3s;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--primary-color);
            margin-bottom: 2rem;
            padding: 0 1rem;
        }

        .nav-links {
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--text-color);
            padding: 0.75rem 1rem;
            border-radius: 0.375rem;
            transition: background-color 0.3s, color 0.3s;
        }

        .nav-links a:hover {
            background-color: var(--hover-bg);
            color: var(--primary-color);
        }

        .theme-toggle {
            position: fixed;
            bottom: 2rem;
            left: 1rem;
            padding: 0.75rem 1rem;
            background-color: var(--primary-color);
            color: white;
            border: none;
            border-radius: 0.375rem;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .theme-toggle:hover {
            background-color: var(--secondary-color);
        }

        .main-content {
            margin-left: 250px;
            padding: 2rem;
            width: calc(100% - 250px);
        }

        .content-section {
            max-width: 900px;
            margin: 0 auto;
            display: none;
        }

        .content-section.active {
            display: block;
        }

        .section-title {
            font-size: 2rem;
            color: var(--primary-color);
            margin-bottom: 2rem;
        }

        .card {
            background-color: var(--card-bg);
            padding: 2rem;
            border-radius: 0.5rem;
            margin-bottom: 2rem;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            transition: transform 0.3s, background-color 0.3s;
        }

        .card:hover {
            transform: translateY(-5px);
        }

        .card h3 {
            color: var(--primary-color);
            margin-bottom: 1rem;
        }

        @media (max-width: 768px) {
            .sidebar {
                width: 100%;
                height: auto;
                position: relative;
            }

            .main-content {
                margin-left: 0;
                width: 100%;
            }

            body {
                flex-direction: column;
            }

            .theme-toggle {
                position: static;
                margin-top: 1rem;
                width: 100%;
            }
        }
    </style>
</head>
<body data-theme="light">
    <aside class="sidebar">
        <div class="logo">Logo</div>
        <nav class="nav-links">
            <a href="#" data-section="home">Ana Sayfa</a>
            <a href="#" data-section="about">Hakkımızda</a>
            <a href="#" data-section="services">Hizmetler</a>
            <a href="#" data-section="contact">İletişim</a>
        </nav>
        <button class="theme-toggle">Tema Değiştir</button>
    </aside>

    <main class="main-content">
        <section id="home" class="content-section active">
            <h1 class="section-title">Ana Sayfa</h1>
            <div class="card">
                <h3>Hoş Geldiniz</h3>
                <p>Modern ve kullanıcı dostu web sitemize hoş geldiniz. Size en iyi hizmeti sunmak için buradayız.</p>
            </div>
        </section>

        <section id="about" class="content-section">
            <h1 class="section-title">Hakkımızda</h1>
            <div class="card">
                <h3>Biz Kimiz?</h3>
                <p>Profesyonel ve yenilikçi çözümler üreten bir ekibiz. Müşteri memnuniyeti bizim için en önemli öncelik.</p>
            </div>
        </section>

        <section id="services" class="content-section">
            <h1 class="section-title">Hizmetlerimiz</h1>
            <div class="card">
                <h3>Web Tasarım</h3>
                <p>Modern ve responsive web tasarım hizmetleri sunuyoruz.</p>
            </div>
            <div class="card">
                <h3>Dijital Pazarlama</h3>
                <p>SEO ve sosyal medya yönetimi ile dijital varlığınızı güçlendiriyoruz.</p>
            </div>
        </section>

        <section id="contact" class="content-section">
            <h1 class="section-title">İletişim</h1>
            <div class="card">
                <h3>Bize Ulaşın</h3>
                <p>Email: info@example.com</p>
                <p>Telefon: +90 123 456 7890</p>
                <p>Adres: İstanbul, Türkiye</p>
            </div>
        </section>
    </main>

    <script>
        // Tema değiştirme fonksiyonu
        const themeToggle = document.querySelector('.theme-toggle');
        themeToggle.addEventListener('click', () => {
            const body = document.body;
            const currentTheme = body.getAttribute('data-theme');
            const newTheme = currentTheme === 'light' ? 'dark' : 'light';
            body.setAttribute('data-theme', newTheme);
        });

        // Sayfa değiştirme fonksiyonu
        const navLinks = document.querySelectorAll('.nav-links a');
        const sections = document.querySelectorAll('.content-section');

        navLinks.forEach(link => {
            link.addEventListener('click', (e) => {
                e.preventDefault();
                const targetSection = link.getAttribute('data-section');
                
                sections.forEach(section => {
                    section.classList.remove('active');
                    if (section.id === targetSection) {
                        section.classList.add('active');
                    }
                });
            });
        });
    </script>
</body>
</html>