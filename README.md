<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
    <title>CheatsHubPro — Читы для Minecraft</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;800;900&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg: #08080f;
            --bg-secondary: rgba(17, 17, 24, 0.85);
            --card: rgba(22, 22, 31, 0.75);
            --card-hover: rgba(30, 30, 42, 0.9);
            --accent: #7c5cff;
            --accent2: #00d4ff;
            --accent3: #ff6b9d;
            --accent-glow: rgba(124, 92, 255, 0.6);
            --text: #f0f0fa;
            --text-muted: #a0a0b8;
            --border: rgba(255, 255, 255, 0.08);
            --radius: 16px;
            --transition: 0.35s cubic-bezier(0.4, 0, 0.2, 1);
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
            font-family: 'Inter', 'Segoe UI', system-ui, sans-serif;
            background: var(--bg);
            color: var(--text);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            overflow-x: hidden;
            position: relative;
        }

        /* Анимированный фон с частицами */
        #particles-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            pointer-events: none;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 24px;
            width: 100%;
        }

        /* Header */
        header {
            background: rgba(10, 10, 18, 0.7);
            backdrop-filter: blur(15px);
            -webkit-backdrop-filter: blur(15px);
            border-bottom: 1px solid var(--border);
            position: sticky;
            top: 0;
            z-index: 100;
            transition: background 0.3s;
        }

        .header-inner {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 16px 24px;
            flex-wrap: wrap;
            gap: 12px;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 900;
            letter-spacing: -1px;
            color: var(--text);
            display: flex;
            align-items: center;
            gap: 8px;
            user-select: none;
            cursor: pointer;
            transition: transform 0.3s;
        }

        .logo:hover {
            transform: scale(1.05);
        }

        .logo-icon {
            font-size: 2rem;
            animation: pulse 2.5s infinite;
            filter: drop-shadow(0 0 10px var(--accent-glow));
        }

        .logo span {
            background: linear-gradient(135deg, var(--accent), var(--accent2));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); filter: drop-shadow(0 0 10px var(--accent-glow)); }
            50% { transform: scale(1.15); filter: drop-shadow(0 0 20px var(--accent-glow)); }
        }

        .search-box {
            position: relative;
            flex: 1;
            max-width: 380px;
            min-width: 220px;
        }

        .search-box input {
            width: 100%;
            padding: 12px 45px 12px 20px;
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.15);
            border-radius: 30px;
            color: var(--text);
            font-size: 1rem;
            outline: none;
            transition: var(--transition);
            backdrop-filter: blur(5px);
        }

        .search-box input:focus {
            border-color: var(--accent);
            box-shadow: 0 0 20px var(--accent-glow), inset 0 0 10px rgba(124, 92, 255, 0.2);
            background: rgba(255, 255, 255, 0.08);
        }

        .search-box input::placeholder {
            color: var(--text-muted);
        }

        .search-icon {
            position: absolute;
            right: 18px;
            top: 50%;
            transform: translateY(-50%);
            color: var(--text-muted);
            pointer-events: none;
            font-size: 1.1rem;
        }

        /* Hero */
        .hero {
            text-align: center;
            padding: 80px 20px 60px;
            position: relative;
            background: radial-gradient(ellipse at center, rgba(124, 92, 255, 0.25) 0%, transparent 70%);
        }

        .hero::before {
            content: '';
            position: absolute;
            inset: 0;
            background: linear-gradient(180deg, rgba(124, 92, 255, 0.08) 0%, transparent 100%);
            pointer-events: none;
        }

        .hero h1 {
            font-size: 4rem;
            font-weight: 900;
            letter-spacing: -2px;
            margin-bottom: 16px;
            background: linear-gradient(135deg, #ffffff 0%, #c8b8ff 50%, #80d4ff 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            filter: drop-shadow(0 0 20px rgba(124, 92, 255, 0.4));
            animation: titleGlow 4s ease-in-out infinite;
        }

        @keyframes titleGlow {
            0%, 100% { filter: drop-shadow(0 0 20px rgba(124, 92, 255, 0.4)); }
            50% { filter: drop-shadow(0 0 35px rgba(124, 92, 255, 0.7)); }
        }

        .hero p {
            color: var(--text-muted);
            font-size: 1.3rem;
            max-width: 600px;
            margin: 0 auto 32px;
            line-height: 1.6;
        }

        .stats {
            display: flex;
            justify-content: center;
            gap: 24px;
            flex-wrap: wrap;
        }

        .stat {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 14px 24px;
            font-weight: 700;
            color: var(--text);
            backdrop-filter: blur(10px);
            transition: var(--transition);
            cursor: default;
        }

        .stat:hover {
            border-color: var(--accent);
            box-shadow: 0 0 20px var(--accent-glow);
            transform: translateY(-3px);
        }

        .stat span {
            color: var(--accent2);
            font-size: 1.5rem;
            font-weight: 900;
        }

        /* Filter bar */
        .filter-bar {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin: 40px 0;
            flex-wrap: wrap;
        }

        .filter-btn {
            padding: 12px 26px;
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid var(--border);
            border-radius: 30px;
            color: var(--text-muted);
            cursor: pointer;
            font-size: 0.9rem;
            font-weight: 600;
            transition: var(--transition);
            user-select: none;
            backdrop-filter: blur(5px);
            letter-spacing: 0.5px;
        }

        .filter-btn:hover {
            color: var(--text);
            border-color: var(--accent);
            background: rgba(124, 92, 255, 0.1);
            box-shadow: 0 0 20px rgba(124, 92, 255, 0.3);
        }

        .filter-btn.active {
            background: linear-gradient(135deg, var(--accent), #5a3fd9);
            border-color: transparent;
            color: #fff;
            box-shadow: 0 8px 25px var(--accent-glow);
        }

        /* Cheats Grid */
        .cheats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 20px;
            padding-bottom: 60px;
        }

        .cheat-card {
            background: var(--card);
            border: 1px solid var(--border);
            border-radius: var(--radius);
            padding: 24px;
            display: flex;
            flex-direction: column;
            gap: 16px;
            transition: var(--transition);
            cursor: default;
            position: relative;
            overflow: hidden;
            backdrop-filter: blur(10px);
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
        }

        .cheat-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, var(--accent), var(--accent2), var(--accent3));
            background-size: 300% 100%;
            opacity: 0;
            transition: var(--transition);
            animation: gradientShift 6s ease infinite;
        }

        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .cheat-card:hover {
            background: var(--card-hover);
            border-color: rgba(124, 92, 255, 0.6);
            transform: translateY(-6px) scale(1.02);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.5), 0 0 30px var(--accent-glow);
            z-index: 2;
        }

        .cheat-card:hover::before {
            opacity: 1;
        }

        .cheat-header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 10px;
            flex-wrap: wrap;
        }

        .cheat-name {
            font-size: 1.3rem;
            font-weight: 800;
            letter-spacing: -0.5px;
            color: var(--text);
            transition: color 0.3s;
        }

        .cheat-card:hover .cheat-name {
            color: var(--accent2);
        }

        .cheat-badge {
            font-size: 0.7rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            padding: 6px 12px;
            border-radius: 20px;
            font-weight: 700;
            background: rgba(124, 92, 255, 0.15);
            color: var(--accent2);
            border: 1px solid rgba(124, 92, 255, 0.3);
            white-space: nowrap;
            backdrop-filter: blur(5px);
            transition: var(--transition);
        }

        .cheat-card:hover .cheat-badge {
            background: rgba(124, 92, 255, 0.3);
            box-shadow: 0 0 15px rgba(124, 92, 255, 0.4);
        }

        .cheat-badge.client { background: rgba(124, 92, 255, 0.15); color: #c8a8ff; border-color: rgba(124, 92, 255, 0.3); }
        .cheat-badge.utility { background: rgba(0, 212, 255, 0.15); color: #80e0ff; border-color: rgba(0, 212, 255, 0.3); }
        .cheat-badge.bypass { background: rgba(255, 107, 157, 0.15); color: #ff9ec2; border-color: rgba(255, 107, 157, 0.3); }

        .download-btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            padding: 12px 20px;
            background: linear-gradient(135deg, var(--accent), #6a4ae0);
            border: none;
            border-radius: 10px;
            color: #fff;
            font-weight: 700;
            font-size: 0.95rem;
            cursor: pointer;
            transition: var(--transition);
            text-decoration: none;
            margin-top: auto;
            min-width: 140px;
            letter-spacing: 0.5px;
            position: relative;
            overflow: hidden;
        }

        .download-btn:hover {
            background: linear-gradient(135deg, #8f6eff, #7c5cff);
            box-shadow: 0 8px 25px var(--accent-glow);
            transform: translateY(-2px);
        }

        .download-btn:active {
            transform: scale(0.96);
        }

        .download-btn.pending {
            background: var(--text-muted);
            pointer-events: none;
            opacity: 0.7;
        }

        .no-results {
            text-align: center;
            padding: 80px 20px;
            color: var(--text-muted);
        }

        .no-results span {
            font-size: 4rem;
            display: block;
            margin-bottom: 20px;
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px); }
        }

        /* Footer */
        footer {
            background: rgba(10, 10, 18, 0.8);
            backdrop-filter: blur(10px);
            border-top: 1px solid var(--border);
            padding: 28px 0;
            text-align: center;
            margin-top: auto;
        }

        footer .disclaimer {
            color: var(--text-muted);
            font-size: 0.8rem;
            margin-top: 8px;
        }

        @media (max-width: 600px) {
            .hero h1 { font-size: 2.5rem; }
            .header-inner { flex-direction: column; align-items: stretch; }
            .search-box { max-width: 100%; }
            .cheats-grid { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>
    <canvas id="particles-canvas"></canvas>

    <header>
        <div class="container header-inner">
            <div class="logo">
                <span class="logo-icon">⚡</span>
                Cheats<span>Hub</span>Pro
            </div>
            <div class="search-box">
                <input type="text" id="searchInput" placeholder="Поиск чита..." autocomplete="off" />
                <span class="search-icon">🔍</span>
            </div>
        </div>
    </header>

    <section class="hero">
        <div class="container">
            <h1>Minecraft Cheats</h1>
            <p>Лучшие читы для Minecraft в одном месте. Быстро, безопасно, бесплатно.</p>
            <div class="stats">
                <div class="stat"><span id="totalCheats">0</span> читов</div>
                <div class="stat"><span>100%</span> бесплатно</div>
                <div class="stat"><span>24/7</span> обновления</div>
            </div>
        </div>
    </section>

    <main class="container">
        <div class="filter-bar">
            <button class="filter-btn active" data-filter="all">Все</button>
            <button class="filter-btn" data-filter="client">Клиенты</button>
            <button class="filter-btn" data-filter="utility">Утилиты</button>
            <button class="filter-btn" data-filter="bypass">Обходы</button>
        </div>

        <div id="cheatsGrid" class="cheats-grid"></div>

        <div id="noResults" class="no-results" style="display: none;">
            <span>😕</span>
            <p>Ничего не найдено. Попробуйте другой запрос.</p>
        </div>
    </main>

    <footer>
        <div class="container">
            <p>© 2025 CheatsHubPro. Все права защищены.</p>
            <p class="disclaimer">Только для образовательных целей. Используйте на свой страх и риск.</p>
        </div>
    </footer>

    <script>
        (function() {
            // ======== Читы с реальными ссылками (где доступны) ========
            // Если url пустой (null), то кнопка покажет "Скоро..." и ничего не откроет
            const cheats = [
                { name: 'Delta Client', category: 'client', badge: 'Клиент', url: null },
                { name: 'Zenith Client', category: 'client', badge: 'Клиент', url: null },
                { name: 'Нурсултан Celestial', category: 'client', badge: 'Клиент', url: null },
                { name: 'Meteor Client', category: 'client', badge: 'Клиент', url: 'https://meteorclient.com' },
                { name: 'Impact Client', category: 'client', badge: 'Клиент', url: 'https://impactclient.net' },
                { name: 'Wurst Client', category: 'client', badge: 'Клиент', url: 'https://www.wurstclient.net/download/' },
                { name: 'LiquidBounce', category: 'client', badge: 'Клиент', url: 'https://liquidbounce.net' },
                { name: 'Aristois', category: 'client', badge: 'Клиент', url: 'https://aristois.net' },
                { name: 'Salhack', category: 'client', badge: 'Клиент', url: 'https://github.com/ionar2/salhack' },
                { name: 'Kami Blue', category: 'client', badge: 'Клиент', url: 'https://github.com/zeroeightysix/KAMI' },
                { name: 'ForgeHax', category: 'utility', badge: 'Утилита', url: 'https://github.com/fr1kin/ForgeHax' },
                { name: 'BleachHack', category: 'client', badge: 'Клиент', url: 'https://bleachhack.org' },
                { name: 'Sigma', category: 'client', badge: 'Клиент', url: null },
                { name: 'Phobos', category: 'client', badge: 'Клиент', url: null },
                { name: 'Ares', category: 'client', badge: 'Клиент', url: 'https://aresclient.org' },
                { name: 'Inertia Client', category: 'client', badge: 'Клиент', url: 'https://inertiaclient.com' },
                { name: 'Creepy Salhack', category: 'client', badge: 'Клиент', url: null },
                { name: 'FDP Client', category: 'client', badge: 'Клиент', url: null },
                { name: 'Raven B+', category: 'client', badge: 'Клиент', url: 'https://github.com/Kopamed/Raven-bPLUS' },
                { name: 'SeedCrackerX', category: 'utility', badge: 'Утилита', url: 'https://github.com/19MisterX98/SeedcrackerX' },
                { name: 'Baritone', category: 'utility', badge: 'Утилита', url: 'https://github.com/cabaletta/baritone' },
                { name: 'Nodus', category: 'client', badge: 'Клиент', url: null },
                { name: 'Huzuni', category: 'client', badge: 'Клиент', url: null },
                { name: 'Exhibition', category: 'client', badge: 'Клиент', url: null },
                { name: 'Jigsaw', category: 'client', badge: 'Клиент', url: null },
                { name: 'Remix', category: 'client', badge: 'Клиент', url: null },
                { name: 'Crystalware', category: 'client', badge: 'Клиент', url: null },
                { name: 'Skilled', category: 'client', badge: 'Клиент', url: null },
                { name: 'Virtue', category: 'client', badge: 'Клиент', url: null },
                { name: 'Astolfo', category: 'client', badge: 'Клиент', url: null },
                { name: 'Vape V4', category: 'bypass', badge: 'Обход', url: null },
                { name: 'Vape Lite', category: 'bypass', badge: 'Обход', url: null },
                { name: 'Entropy', category: 'bypass', badge: 'Обход', url: null },
                { name: 'Whiteout', category: 'bypass', badge: 'Обход', url: null },
                { name: 'Drip Lite', category: 'bypass', badge: 'Обход', url: null },
                { name: 'Ghost Client X', category: 'bypass', badge: 'Обход', url: null },
                { name: 'ZeroDay', category: 'bypass', badge: 'Обход', url: null }
            ];

            const grid = document.getElementById('cheatsGrid');
            const searchInput = document.getElementById('searchInput');
            const noResults = document.getElementById('noResults');
            const totalCheatsSpan = document.getElementById('totalCheats');
            const filterBtns = document.querySelectorAll('.filter-btn');

            let currentFilter = 'all';
            let currentSearch = '';

            totalCheatsSpan.textContent = cheats.length;

            function renderCheats() {
                const filtered = cheats.filter(cheat => {
                    const matchesFilter = currentFilter === 'all' || cheat.category === currentFilter;
                    const matchesSearch = cheat.name.toLowerCase().includes(currentSearch.toLowerCase());
                    return matchesFilter && matchesSearch;
                });

                grid.innerHTML = '';
                noResults.style.display = filtered.length === 0 ? 'block' : 'none';

                filtered.forEach(cheat => {
                    const card = document.createElement('div');
                    card.className = 'cheat-card';

                    const header = document.createElement('div');
                    header.className = 'cheat-header';

                    const name = document.createElement('h3');
                    name.className = 'cheat-name';
                    name.textContent = cheat.name;

                    const badge = document.createElement('span');
                    badge.className = `cheat-badge ${cheat.category}`;
                    badge.textContent = cheat.badge;

                    header.appendChild(name);
                    header.appendChild(badge);

                    const btn = document.createElement('button');
                    btn.className = 'download-btn';

                    if (cheat.url) {
                        // Если есть реальная ссылка, делаем кнопку-ссылку
                        btn.textContent = '⬇ Скачать';
                        btn.addEventListener('click', () => {
                            window.open(cheat.url, '_blank');
                        });
                    } else {
                        // Если ссылки нет, показываем заглушку
                        btn.textContent = '⬇ Скачать';
                        btn.addEventListener('click', function() {
                            this.textContent = '⏳ Скоро...';
                            this.classList.add('pending');
                            setTimeout(() => {
                                this.textContent = '⬇ Скачать';
                                this.classList.remove('pending');
                            }, 1500);
                        });
                    }

                    card.appendChild(header);
                    card.appendChild(btn);
                    grid.appendChild(card);
                });
            }

            filterBtns.forEach(btn => {
                btn.addEventListener('click', () => {
                    filterBtns.forEach(b => b.classList.remove('active'));
                    btn.classList.add('active');
                    currentFilter = btn.dataset.filter;
                    renderCheats();
                });
            });

            searchInput.addEventListener('input', (e) => {
                currentSearch = e.target.value;
                renderCheats();
            });

            renderCheats();

            // ======== Фоновые частицы (звёзды) ========
            const canvas = document.getElementById('particles-canvas');
            const ctx = canvas.getContext('2d');
            let particles = [];
            const particleCount = 80;

            function resizeCanvas() {
                canvas.width = window.innerWidth;
                canvas.height = window.innerHeight;
            }

            class Particle {
                constructor() {
                    this.reset();
                }
                reset() {
                    this.x = Math.random() * canvas.width;
                    this.y = Math.random() * canvas.height;
                    this.size = Math.random() * 2 + 0.5;
                    this.speedX = (Math.random() - 0.5) * 0.3;
                    this.speedY = (Math.random() - 0.5) * 0.3;
                    this.opacity = Math.random() * 0.7 + 0.3;
                }
                update() {
                    this.x += this.speedX;
                    this.y += this.speedY;
                    if (this.x < 0 || this.x > canvas.width || this.y < 0 || this.y > canvas.height) {
                        this.reset();
                    }
                }
                draw() {
                    ctx.beginPath();
                    ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                    ctx.fillStyle = `rgba(200, 190, 255, ${this.opacity})`;
                    ctx.fill();
                }
            }

            function initParticles() {
                particles = [];
                for (let i = 0; i < particleCount; i++) {
                    particles.push(new Particle());
                }
            }

            function animateParticles() {
                ctx.clearRect(0, 0, canvas.width, canvas.height);
                particles.forEach(p => {
                    p.update();
                    p.draw();
                });
                requestAnimationFrame(animateParticles);
            }

            window.addEventListener('resize', () => {
                resizeCanvas();
                initParticles();
            });

            resizeCanvas();
            initParticles();
            animateParticles();
        })();
    </script>
</body>
</html>
