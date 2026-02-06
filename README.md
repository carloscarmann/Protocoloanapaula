.


[index.
html](https://github.com/user-attachments/files/25117836/index.html)
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta http-equiv="Content-Security-Policy" content="default-src 'self' 'unsafe-inline' 'unsafe-eval' https://cdn.jsdelivr.net data: blob:;">
    <title>Protocolo de Cutting Avançado - Ana Paula</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-pink: #ff006e;
            --secondary-pink: #ff4d94;
            --dark-bg: #0a0a0a;
            --card-bg: #1a1a1a;
            --white: #ffffff;
            --gray: #888888;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: var(--dark-bg);
            color: var(--white);
            overflow-x: hidden;
            position: relative;
        }

        /* Animated Background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            opacity: 0.1;
            overflow: hidden;
        }

        .bg-animation::before {
            content: '';
            position: absolute;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle at 50% 50%, var(--primary-pink) 0%, transparent 50%);
            animation: rotate 20s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        /* Particles */
        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: var(--primary-pink);
            border-radius: 50%;
            opacity: 0.6;
            animation: float-particle linear infinite;
        }

        @keyframes float-particle {
            0% {
                transform: translateY(100vh) translateX(0) scale(0);
                opacity: 0;
            }
            10% {
                opacity: 0.6;
            }
            90% {
                opacity: 0.6;
            }
            100% {
                transform: translateY(-100vh) translateX(100px) scale(1);
                opacity: 0;
            }
        }

        /* Header */
        header {
            position: relative;
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            text-align: center;
            overflow: hidden;
            z-index: 1;
        }

        .signature {
            font-size: 1.2rem;
            letter-spacing: 4px;
            text-transform: uppercase;
            color: var(--primary-pink);
            margin-bottom: 1rem;
            position: relative;
            animation: glowPulse 3s ease-in-out infinite;
        }

        @keyframes glowPulse {
            0%, 100% {
                text-shadow: 0 0 10px var(--primary-pink),
                             0 0 20px var(--primary-pink),
                             0 0 30px var(--primary-pink);
            }
            50% {
                text-shadow: 0 0 20px var(--primary-pink),
                             0 0 40px var(--primary-pink),
                             0 0 60px var(--primary-pink);
            }
        }

        h1 {
            font-size: 4rem;
            font-weight: 900;
            margin-bottom: 2rem;
            background: linear-gradient(135deg, var(--white) 0%, var(--primary-pink) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: slideIn 1s ease-out;
            cursor: pointer;
            transition: all 0.5s ease;
            letter-spacing: 2px;
        }

        h1:hover {
            letter-spacing: 8px;
            transform: scale(1.05);
            filter: drop-shadow(0 0 30px var(--primary-pink));
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .client-info {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 2rem;
            margin-top: 3rem;
            max-width: 600px;
        }

        .info-card {
            background: rgba(255, 0, 110, 0.1);
            border: 1px solid var(--primary-pink);
            padding: 1.5rem;
            border-radius: 15px;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }

        .info-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 40px rgba(255, 0, 110, 0.3);
        }

        .info-label {
            font-size: 0.9rem;
            color: var(--gray);
            margin-bottom: 0.5rem;
        }

        .info-value {
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--primary-pink);
        }

        /* Navigation */
        nav {
            position: sticky;
            top: 0;
            background: rgba(10, 10, 10, 0.95);
            backdrop-filter: blur(20px);
            padding: 1.5rem 0;
            z-index: 1000;
            border-bottom: 1px solid rgba(255, 0, 110, 0.2);
        }

        .nav-container {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: center;
            gap: 2rem;
            flex-wrap: wrap;
            padding: 0 2rem;
        }

        .day-btn {
            background: transparent;
            border: 2px solid var(--primary-pink);
            color: var(--white);
            padding: 0.8rem 2rem;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: bold;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .day-btn::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-radius: 50%;
            background: var(--primary-pink);
            transform: translate(-50%, -50%);
            transition: width 0.5s ease, height 0.5s ease;
            z-index: -1;
        }

        .day-btn:hover::before {
            width: 300px;
            height: 300px;
        }

        .day-btn:hover {
            color: var(--dark-bg);
            transform: scale(1.05);
        }

        .day-btn.active {
            background: var(--primary-pink);
            color: var(--dark-bg);
        }

        /* Main Content */
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 4rem 2rem;
            position: relative;
            z-index: 1;
        }

        .day-section {
            display: none;
            animation: fadeIn 0.8s ease-out;
        }

        .day-section.active {
            display: block;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .day-header {
            text-align: center;
            margin-bottom: 4rem;
        }

        .day-title {
            font-size: 3rem;
            margin-bottom: 1rem;
            background: linear-gradient(135deg, var(--primary-pink) 0%, var(--white) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .calorie-info {
            font-size: 1.2rem;
            color: var(--gray);
        }

        .calorie-value {
            color: var(--primary-pink);
            font-weight: bold;
        }

        /* Meal Cards */
        .meals-grid {
            display: grid;
            gap: 3rem;
            margin-bottom: 4rem;
        }

        .meal-card {
            background: var(--card-bg);
            border-radius: 30px;
            padding: 3rem;
            position: relative;
            transform-style: preserve-3d;
            transition: all 0.8s cubic-bezier(0.23, 1, 0.32, 1);
            border: 1px solid rgba(255, 0, 110, 0.1);
            overflow: hidden;
            filter: blur(0px);
            opacity: 1;
            z-index: 1;
        }

        .meal-card.focused {
            transform: translateY(-30px) scale(1.05) rotateX(0deg);
            box-shadow: 0 50px 100px rgba(255, 0, 110, 0.6);
            border-color: var(--primary-pink);
            z-index: 100;
            filter: blur(0px);
            opacity: 1;
        }

        .meal-card.blurred {
            filter: blur(8px);
            opacity: 0.3;
            transform: scale(0.95);
        }

        .meal-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 5px;
            background: linear-gradient(90deg, var(--primary-pink), var(--secondary-pink));
            transform: scaleX(0);
            transform-origin: left;
            transition: transform 0.5s ease;
        }

        .meal-card:hover::before {
            transform: scaleX(1);
        }

        .meal-card:hover {
            transform: translateY(-15px) rotateX(2deg);
            box-shadow: 0 30px 60px rgba(255, 0, 110, 0.3);
            border-color: var(--primary-pink);
        }

        .meal-header {
            display: flex;
            align-items: center;
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .meal-icon {
            width: 70px;
            height: 70px;
            background: linear-gradient(135deg, var(--primary-pink), var(--secondary-pink));
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .meal-info h3 {
            font-size: 1.8rem;
            margin-bottom: 0.5rem;
        }

        .meal-time {
            color: var(--gray);
            font-size: 1rem;
        }

        .options-container {
            display: grid;
            gap: 2rem;
        }

        .option {
            background: rgba(255, 255, 255, 0.03);
            border-radius: 20px;
            padding: 2rem;
            border-left: 4px solid var(--primary-pink);
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .option:hover {
            background: rgba(255, 0, 110, 0.1);
            transform: translateX(10px);
        }

        .option-title {
            font-size: 1.2rem;
            font-weight: bold;
            color: var(--primary-pink);
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .option-title::before {
            content: '●';
            font-size: 1.5rem;
        }

        .ingredients-list {
            list-style: none;
            display: grid;
            gap: 0.8rem;
        }

        .ingredient {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 0.5rem 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
        }

        .ingredient::before {
            content: '✓';
            color: var(--primary-pink);
            font-weight: bold;
            font-size: 1.2rem;
        }

        /* Special Saturday Card */
        .alcohol-info {
            background: linear-gradient(135deg, rgba(255, 0, 110, 0.2), rgba(255, 0, 110, 0.05));
            border-radius: 20px;
            padding: 2rem;
            margin-top: 2rem;
            border: 2px solid var(--primary-pink);
        }

        .alcohol-title {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--primary-pink);
        }

        .alcohol-options {
            display: grid;
            gap: 1rem;
            margin-bottom: 1.5rem;
        }

        .alcohol-option {
            background: rgba(0, 0, 0, 0.3);
            padding: 1rem;
            border-radius: 10px;
            border-left: 3px solid var(--secondary-pink);
        }

        .rules-list {
            list-style: none;
            display: grid;
            gap: 0.8rem;
        }

        .rule {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 0.5rem;
        }

        .rule::before {
            content: '⚠️';
            font-size: 1.2rem;
        }

        /* Scroll to top button */
        .scroll-top {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, var(--primary-pink), var(--secondary-pink));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            opacity: 0;
            transition: all 0.3s ease;
            z-index: 1000;
            border: none;
            color: var(--white);
            font-size: 1.5rem;
        }

        .scroll-top.visible {
            opacity: 1;
        }

        .scroll-top:hover {
            transform: scale(1.1) translateY(-5px);
            box-shadow: 0 10px 30px rgba(255, 0, 110, 0.5);
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 3rem 2rem;
            background: rgba(255, 0, 110, 0.05);
            border-top: 1px solid rgba(255, 0, 110, 0.2);
            position: relative;
            z-index: 1;
        }

        .footer-signature {
            font-size: 1.5rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
            background: linear-gradient(135deg, var(--primary-pink), var(--white));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .footer-tagline {
            color: var(--gray);
            font-style: italic;
        }

        .footer-warning {
            margin-top: 2rem;
            font-size: 0.9rem;
            color: var(--gray);
        }

        /* Responsive */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }

            .day-title {
                font-size: 2rem;
            }

            .meal-card {
                padding: 2rem;
            }

            .nav-container {
                gap: 1rem;
            }

            .day-btn {
                padding: 0.6rem 1.5rem;
                font-size: 0.9rem;
            }

            .welcome-text {
                font-size: 2rem;
            }

            .tracking-grid {
                grid-template-columns: 1fr;
            }

            .client-info {
                grid-template-columns: 1fr;
            }
        }

        /* Tracking Module */
        .tracking-section {
            background: rgba(255, 0, 110, 0.05);
            padding: 4rem 0;
            margin-top: 4rem;
            border-top: 1px solid rgba(255, 0, 110, 0.2);
        }

        .tracking-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 2rem;
            margin-top: 3rem;
        }

        .tracking-card {
            background: var(--card-bg);
            border-radius: 30px;
            padding: 2.5rem;
            border: 1px solid rgba(255, 0, 110, 0.1);
            transition: all 0.3s ease;
        }

        .tracking-card:hover {
            border-color: var(--primary-pink);
            box-shadow: 0 20px 60px rgba(255, 0, 110, 0.2);
            transform: translateY(-5px);
        }

        .tracking-title {
            font-size: 1.8rem;
            margin-bottom: 1.5rem;
            color: var(--primary-pink);
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .tracking-title::before {
            content: '';
            width: 40px;
            height: 40px;
            background: linear-gradient(135deg, var(--primary-pink), var(--secondary-pink));
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .input-group {
            margin-bottom: 1.5rem;
        }

        .input-label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--gray);
            font-size: 0.9rem;
        }

        .input-field {
            width: 100%;
            padding: 1rem;
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 0, 110, 0.2);
            border-radius: 10px;
            color: var(--white);
            font-size: 1rem;
            transition: all 0.3s ease;
        }

        .input-field:focus {
            outline: none;
            border-color: var(--primary-pink);
            box-shadow: 0 0 20px rgba(255, 0, 110, 0.3);
        }

        .save-btn {
            width: 100%;
            padding: 1rem;
            background: linear-gradient(135deg, var(--primary-pink), var(--secondary-pink));
            border: none;
            border-radius: 10px;
            color: var(--white);
            font-size: 1rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .save-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 30px rgba(255, 0, 110, 0.5);
        }

        .history-list {
            max-height: 400px;
            overflow-y: auto;
            margin-top: 1rem;
        }

        .history-item {
            background: rgba(255, 255, 255, 0.03);
            padding: 1rem;
            border-radius: 10px;
            margin-bottom: 1rem;
            border-left: 3px solid var(--primary-pink);
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: all 0.3s ease;
        }

        .history-item:hover {
            background: rgba(255, 0, 110, 0.1);
            transform: translateX(5px);
        }

        .history-date {
            color: var(--gray);
            font-size: 0.9rem;
        }

        .history-value {
            color: var(--primary-pink);
            font-weight: bold;
            font-size: 1.2rem;
        }

        .chart-container {
            background: rgba(255, 255, 255, 0.03);
            border-radius: 15px;
            padding: 2rem;
            margin-top: 2rem;
            height: 300px;
            position: relative;
        }

        .chart-canvas {
            width: 100%;
            height: 100%;
        }

        .metrics-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 1rem;
            margin-bottom: 2rem;
        }

        .metric-box {
            background: rgba(255, 0, 110, 0.1);
            padding: 1.5rem;
            border-radius: 15px;
            text-align: center;
            border: 1px solid rgba(255, 0, 110, 0.2);
        }

        .metric-label {
            color: var(--gray);
            font-size: 0.9rem;
            margin-bottom: 0.5rem;
        }

        .metric-value {
            color: var(--primary-pink);
            font-size: 1.8rem;
            font-weight: bold;
        }

        .metric-change {
            font-size: 0.9rem;
            margin-top: 0.5rem;
        }

        .metric-change.positive {
            color: #4ade80;
        }

        .metric-change.negative {
            color: #f87171;
        }

        .delete-btn {
            background: rgba(255, 0, 0, 0.2);
            border: 1px solid rgba(255, 0, 0, 0.3);
            color: #ff4444;
            padding: 0.5rem 1rem;
            border-radius: 5px;
            cursor: pointer;
            font-size: 0.9rem;
            transition: all 0.3s ease;
        }

        .delete-btn:hover {
            background: rgba(255, 0, 0, 0.4);
            transform: scale(1.05);
        }

        /* Custom Scrollbar */
        .history-list::-webkit-scrollbar {
            width: 8px;
        }

        .history-list::-webkit-scrollbar-track {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
        }

        .history-list::-webkit-scrollbar-thumb {
            background: var(--primary-pink);
            border-radius: 10px;
        }

        /* Loading Animation */
        .loading {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, var(--dark-bg) 0%, #1a0a14 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            z-index: 9999;
            animation: fadeOut 1s ease-out 5s forwards;
        }

        @keyframes fadeOut {
            to {
                opacity: 0;
                visibility: hidden;
            }
        }

        .welcome-text {
            font-size: 3rem;
            font-weight: 900;
            margin-bottom: 2rem;
            background: linear-gradient(135deg, var(--white) 0%, var(--primary-pink) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: welcomeSlide 1.5s ease-out;
        }

        @keyframes welcomeSlide {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .loading-spinner {
            width: 80px;
            height: 80px;
            border: 4px solid rgba(255, 0, 110, 0.1);
            border-top-color: var(--primary-pink);
            border-radius: 50%;
            animation: spin 1s linear infinite;
            margin-top: 2rem;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        .loading-progress {
            width: 300px;
            height: 4px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            margin-top: 2rem;
            overflow: hidden;
        }

        .loading-bar {
            height: 100%;
            background: linear-gradient(90deg, var(--primary-pink), var(--secondary-pink));
            width: 0;
            animation: loadProgress 5s ease-out forwards;
            box-shadow: 0 0 20px var(--primary-pink);
        }

        @keyframes loadProgress {
            to { width: 100%; }
        }

        @media (max-width: 768px) {
            .metrics-grid {
                grid-template-columns: 1fr;
            }

            .tracking-grid {
                grid-template-columns: 1fr;
            }

            .tracking-card {
                grid-column: span 1 !important;
            }
        }
    </style>
</head>
<body>
    <div class="loading">
        <div class="welcome-text">Bem-vinda, Ana Paula! ✨</div>
        <div class="loading-spinner"></div>
        <div class="loading-progress">
            <div class="loading-bar"></div>
        </div>
    </div>

    <div class="bg-animation"></div>

    <header>
        <div class="signature">SIGNATURE - CARLOS EDUARDO</div>
        <h1>PROTOCOLO DE CUTTING AVANÇADO</h1>
        <div class="client-info">
            <div class="info-card">
                <div class="info-label">Cliente</div>
                <div class="info-value">Ana Paula</div>
            </div>
            <div class="info-card">
                <div class="info-label">Idade</div>
                <div class="info-value">31 anos</div>
            </div>
            <div class="info-card">
                <div class="info-label">Peso Atual</div>
                <div class="info-value">68kg</div>
            </div>
            <div class="info-card">
                <div class="info-label">Altura</div>
                <div class="info-value">1,60m</div>
            </div>
            <div class="info-card">
                <div class="info-label">Duração</div>
                <div class="info-value">4 semanas</div>
            </div>
        </div>
    </header>

    <nav>
        <div class="nav-container">
            <button class="day-btn active" onclick="showDay('segunda', this)">Segunda</button>
            <button class="day-btn" onclick="showDay('terca', this)">Terça</button>
            <button class="day-btn" onclick="showDay('quarta', this)">Quarta</button>
            <button class="day-btn" onclick="showDay('quinta', this)">Quinta</button>
            <button class="day-btn" onclick="showDay('sexta', this)">Sexta</button>
            <button class="day-btn" onclick="showDay('sabado', this)">Sábado</button>
            <button class="day-btn" onclick="showDay('domingo', this)">Domingo</button>
        </div>
    </nav>

    <div class="container">
        <!-- SEGUNDA-FEIRA -->
        <div id="segunda" class="day-section active">
            <div class="day-header">
                <h2 class="day-title">Segunda-feira</h2>
                <p class="calorie-info">Calorias: <span class="calorie-value">1.500 kcal</span></p>
            </div>

            <div class="meals-grid">
                <div class="meal-card">
                    <div class="meal-header">
                        <div class="meal-icon">🌅</div>
                        <div class="meal-info">
                            <h3>Café da Manhã</h3>
                            <p class="meal-time">7h às 8h</p>
                        </div>
                    </div>
                    <div class="options-container">
                        <div class="option">
                            <div class="option-title">Opção 1</div>
                            <ul class="ingredients-list">
                                <li class="ingredient">150g de iogurte grego natural desnatado</li>
                                <li class="ingredient">30g de aveia em flocos</li>
                                <li class="ingredient">100g de morango picado</li>
                                <li class="ingredient">10g de pasta de amendoim integral</li>
                                <li class="ingredient">Canela em pó à vontade</li>
                            </ul>
                        </div>
                        <div class="option">
                            <div class="option-title">Opção 2</div>
                            <ul class="ingredients-list">
                                <li class="ingredient">40g de goma para tapioca</li>
                                <li class="ingredient">100g de peito de frango desfiado</li>
                                <li class="ingredient">20g de queijo cottage</li>
                                <li class="ingredient">Tomate picado à vontade</li>
                                <li class="ingredient">Manjericão fresco à vontade</li>
                            </ul>
                        </div>
                        <div class="option">
                            <div class="option-title">Opção 3</div>
                            <ul class="ingredients-list">
                                <li class="ingredient">1 banana média amassada</li>
                                <li class="ingredient">100g de ricota amassada</li>
                                <li class="ingredient">20g de aveia em flocos</li>
                                <li class="ingredient">Canela em pó à vontade</li>
                                <li class="ingredient">Misturar tudo e fazer panqueca em frigideira antiaderente</li>
                            </ul>
                        </div>
                    </div>
                </div>

                <div class="meal-card">
                    <div class="meal-header">
                        <div class="meal-icon">☕</div>
                        <div class="meal-info">
                            <h3>Lanche da Manhã</h3>
                            <p class="meal-time">10h às 11h</p>
                        </div>
                    </div>
                    <div class="options-container">
                        <div class="option">
                            <div class="option-title">Opção 1</div>
                            <ul class="ingredients-list">
                                <li class="ingredient">3 fatias de peito de peru defumado</li>
                                <li class="ingredient">1 fatia de queijo branco</li>
                                <li class="ingredient">Alface à vontade</li>
                                <li class="ingredient">Tomate à vontade</li>
                                <li class="ingredient">Mostarda à vontade</li>
                                <li class="ingredient">1 maçã pequena</li>
                            </ul>
                        </div>
                        <div class="option">
                            <div class="option-title">Opção 2</div>
                            <ul class="ingredients-list">
                                <li class="ingredient">200ml de leite desnatado</li>
                                <li class="ingredient">100g de mamão papaia</li>
                                <li class="ingredient">10g de semente de chia</li>
                                <li class="ingredient">Gelo e adoçante à vontade</li>
                                <li class="ingredient">Bater tudo no liquidificador</li>
                            </ul>
                        </div>
                        <div class="option">
                            <div class="option-title">Opção 3</div>
                            <ul class="ingredients-list">
                                <li class="ingredient">150g de queijo cottage</li>
                                <li class="ingredient">80g de frutas vermelhas variadas (morango, framboesa, amora)</li>
                                <li class="ingredient">5g de amêndoas picadas</li>
                            </ul>
                        </div>
                    </div>
                </div>

                <div class="meal-card">
                    <div class="meal-header">
                        <div class="meal-icon">🍽️</div>
                        <div class="meal-info">
                            <h3>Almoço</h3>
                            <p class="meal-time">12h30 às 13h30</p>
                        </div>
                    </div>
                    <div class="options-container">
                        <div class="option">
                            <div class="option-title">Opção 1</div>
                            <ul class="ingredients-list">
                                <li class="ingredient">150g de peito de frango grelhado</li>
                                <li class="ingredient">100g de batata doce assada</li>
                                <li class="ingredient">150g de brócolis cozido no vapor</li>
                                <li class="ingredient">Salada verde à vontade (alface, rúcula, pepino, tomate)</li>
                                <li class="ingredient">1 colher de chá de azeite extra virgem</li>
                            </ul>
                        </div>
                        <div class="option">
                            <div class="option-title">Opção 2</div>
                            <ul class="ingredients-list">
                                <li class="ingredient">120g de carne moída de patinho (7% de gordura) refogada</li>
                                <li class="ingredient">120g de abóbora cabotiá cozida</li>
                                <li class="ingredient">100g de vagem refogada</li>
                                <li class="ingredient">80g de arroz branco cozido</li>
                                <li class="ingredient">Salada crua à vontade (alface, cenoura ralada, repolho)</li>
                                <li class="ingredient">Tempero: alho, cebola, sal, cheiro verde</li>
                            </ul>
                        </div>
                        <div class="option">
                            <div class="option-title">Opção 3</div>
                            <ul class="ingredients-list">
                                <li class="ingredient">180g de filé de tilápia assado no forno</li>
                                <li class="ingredient">150g de abobrinha italiana grelhada</li>
                                <li class="ingredient">100g de tomate assado</li>
                                <li class="ingredient">80g de feijão cozido</li>
                                <li class="ingredient">Ervas frescas à vontade (salsinha, cebolinha, manjericão)</li>
                                <li class="ingredient">1 colher de chá de azeite extra virgem</li>
                                <li class="ingredient">Limão à vontade</li>
                            </ul>
                        </div>
                    </div>
                </div>

                <div class="meal-card">
                    <div class="meal-header">
                        <div class="meal-icon">🥤</div>
                        <div class="meal-info">
                            <h3>Lanche da Tarde</h3>
                            <p class="meal-time">16h às 17h</p>
                        </div>
                    </div>
                    <div class="options-container">
                        <div class="option">
                            <div class="option-title">Opção 1</div>
                            <ul class="ingredients-list">
                                <li class="ingredient">2 fatias de pão integral light</li>
                                <li class="ingredient">80g de atum em lata (escorrido da água)</li>
                                <li class="ingredient">Alface à vontade</li>
                                <li class="ingredient">Tomate à vontade</li>
                                <li class="ingredient">Cenoura ralada à vontade</li>
                                <li class="ingredient">Mostarda ou limão à vontade</li>
                            </ul>
                        </div>
                        <div class="option">
                            <div class="option-title">Opção 2</div>
                            <ul class="ingredients-list">
                                <li class="ingredient">20g de goma para tapioca</li>
                                <li class="ingredient">80g de frango desfiado</li>
                                <li class="ingredient">10g de requeijão light</li>
                                <li class="ingredient">Temperos à vontade</li>
                            </ul>
                        </div>
                        <div class="option">
                            <div class="option-title">Opção 3</div>
                            <ul class="ingredients-list">
                                <li class="ingredient">120g de iogurte natural desnatado</li>
                                <li class="ingredient">50g de ricota</li>
                                <li class="ingredient">Meia banana pequena</li>
                                <li class="ingredient">5g de cacau em pó 100%</li>
                            </ul>
                        </div>
                    </div>
                </div>

                <div class="meal-card">
                    <div class="meal-header">
                        <div class="meal-icon">🌙</div>
                        <div class="meal-info">
                            <h3>Jantar</h3>
                            <p class="meal-time">19h30 às 20h30</p>
                        </div>
                    </div>
                    <div class="options-container">
                        <div class="option">
                            <div class="option-title">Opção 1</div>
                            <ul class="ingredients-list">
                                <li class="ingredient">120g de carne moída magra de patinho refogada</li>
                                <li class="ingredient">100g de abobrinha refogada</li>
                                <li class="ingredient">Salada verde grande à vontade (alface, agrião, pepino, rúcula)</li>
                                <li class="ingredient">Temperos naturais à vontade (alho, cebola, pimenta, ervas)</li>
                            </ul>
                        </div>
                        <div class="option">
                            <div class="option-title">Opção 2</div>
                            <ul class="ingredients-list">
                                <li class="ingredient">120g de peixe grelhado</li>
                                <li class="ingredient">150g de vagem grelhada</li>
                                <li class="ingredient">Salada de folhas variadas à vontade</li>
                                <li class="ingredient">Vinagre balsâmico à vontade</li>
                                <li class="ingredient">Limão siciliano à vontade</li>
                                <li class="ingredient">Ervas frescas à vontade</li>
                            </ul>
                        </div>
                        <div class="option">
                            <div class="option-title">Opção 3</div>
                            <ul class="ingredients-list">
                                <li class="ingredient">140g de peito de frango desfiado</li>
                                <li class="ingredient">100g de cogumelo champignon refogado</li>
                                <li class="ingredient">80g de palmito em conserva (bem escorrido)</li>
                                <li class="ingredient">Molho de soja light (2 colheres de sopa)</li>
                                <li class="ingredient">Gengibre ralado à vontade</li>
                                <li class="ingredient">Salada crua à vontade</li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- TERÇA-FEIRA -->
        <div id="terca" class="day-section">
            <div class="day-header">
                <h2 class="day-title">Terça-feira</h2>
                <p class="calorie-info">Calorias: <span class="calorie-value">1.500 kcal</span></p>
            </div>
            <p style="text-align: center; color: var(--gray); font-size: 1.2rem; margin-bottom: 2rem;">
                Mesmo cardápio de segunda-feira
            </p>
        </div>

        <!-- QUARTA-FEIRA -->
        <div id="quarta" class="day-section">
            <div class="day-header">
                <h2 class="day-title">Quarta-feira</h2>
                <p class="calorie-info">Calorias: <span class="calorie-value">1.500 kcal</span></p>
            </div>
            <p style="text-align: center; color: var(--gray); font-size: 1.2rem; margin-bottom: 2rem;">
                Mesmo cardápio de segunda e terça-feira
            </p>
        </div>

        <!-- QUINTA-FEIRA -->
        <div id="quinta" class="day-section">
            <div class="day-header">
                <h2 class="day-title">Quinta-feira</h2>
                <p class="calorie-info">Calorias: <span class="calorie-value">1.500 kcal</span></p>
            </div>
            <p style="text-align: center; color: var(--gray); font-size: 1.2rem; margin-bottom: 2rem;">
                Mesmo cardápio de segunda e terça-feira
            </p>
        </div>

        <!-- SEXTA-FEIRA -->
        <div id="sexta" class="day-section">
            <div class="day-header">
                <h2 class="day-title">Sexta-feira</h2>
                <p class="calorie-info">Calorias: <span class="calorie-value">1.700 kcal</span> | Preparação para o fim de semana</p>
            </div>
            <p style="text-align: center; color: var(--gray); font-size: 1.2rem; margin-bottom: 2rem;">
                Porções ligeiramente maiores do cardápio base (aproximadamente +15% em cada refeição)
            </p>
        </div>

        <!-- SÁBADO -->
        <div id="sabado" class="day-section">
            <div class="day-header">
                <h2 class="day-title">Sábado</h2>
                <p class="calorie-info">Calorias: <span class="calorie-value">1.900 kcal</span> | Dia Social com Álcool</p>
            </div>
            
            <div class="meals-grid">
                <div class="meal-card">
                    <div class="meal-header">
                        <div class="meal-icon">🍷</div>
                        <div class="meal-info">
                            <h3>Jantar Social</h3>
                            <p class="meal-time">19h30 às 21h</p>
                        </div>
                    </div>
                    <div class="options-container">
                        <div class="option">
                            <div class="option-title">Refeição Base</div>
                            <ul class="ingredients-list">
                                <li class="ingredient">150g de proteína magra (frango, peixe ou carne magra)</li>
                                <li class="ingredient">Legumes grelhados à vontade (abobrinha, berinjela, pimentão, tomate)</li>
                                <li class="ingredient">Salada verde grande à vontade</li>
                                <li class="ingredient">1 colher de chá de azeite extra virgem</li>
                            </ul>
                        </div>
                    </div>

                    <div class="alcohol-info">
                        <h4 class="alcohol-title">🍷 Bebida Alcoólica Permitida (escolher apenas UMA opção)</h4>
                        <div class="alcohol-options">
                            <div class="alcohol-option">
                                <strong>Opção 1:</strong> 2 taças de vinho tinto seco (250ml no total)
                            </div>
                            <div class="alcohol-option">
                                <strong>Opção 2:</strong> 3 doses de destilado puro (vodka, whisky ou gim) com água com gás e limão
                            </div>
                            <div class="alcohol-option">
                                <strong>Opção 3:</strong> 2 latas de cerveja sem álcool
                            </div>
                        </div>

                        <h4 class="alcohol-title" style="margin-top: 1.5rem;">⚠️ Regras Obrigatórias</h4>
                        <ul class="rules-list">
                            <li class="rule">Comer toda a refeição ANTES de começar a beber</li>
                            <li class="rule">Intercalar cada dose ou taça com 1 copo grande de água</li>
                            <li class="rule">Parar de beber até às 22h</li>
                            <li class="rule">Beber 1 litro de água antes de dormir</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>

        <!-- DOMINGO -->
        <div id="domingo" class="day-section">
            <div class="day-header">
                <h2 class="day-title">Domingo</h2>
                <p class="calorie-info">Calorias: <span class="calorie-value">1.400 kcal</span> | Compensação</p>
            </div>
            <p style="text-align: center; color: var(--gray); font-size: 1.2rem; margin-bottom: 2rem;">
                Porções reduzidas do cardápio base (aproximadamente -7% em cada refeição)
            </p>
        </div>
    </div>

    <!-- Tracking Section -->
    <section class="tracking-section">
        <div class="container">
            <div class="day-header">
                <h2 class="day-title">Acompanhamento e Progresso</h2>
                <p class="calorie-info">Monitore sua evolução <span class="calorie-value">semana a semana</span></p>
            </div>

            <!-- Metrics Overview -->
            <div class="metrics-grid">
                <div class="metric-box">
                    <div class="metric-label">Peso Atual</div>
                    <div class="metric-value" id="currentWeight">68.0</div>
                    <div class="metric-change" id="weightChange">kg</div>
                </div>
                <div class="metric-box">
                    <div class="metric-label">Meta</div>
                    <div class="metric-value">63.0</div>
                    <div class="metric-change">kg</div>
                </div>
                <div class="metric-box">
                    <div class="metric-label">Progresso</div>
                    <div class="metric-value" id="progressValue">0.0</div>
                    <div class="metric-change">kg perdidos</div>
                </div>
            </div>

            <div class="tracking-grid">
                <!-- Weight Tracking -->
                <div class="tracking-card">
                    <h3 class="tracking-title">📊 Peso Semanal</h3>
                    <div class="input-group">
                        <label class="input-label">Data</label>
                        <input type="date" class="input-field" id="weightDate">
                    </div>
                    <div class="input-group">
                        <label class="input-label">Peso (kg)</label>
                        <input type="number" step="0.1" class="input-field" id="weightInput" placeholder="Ex: 67.5">
                    </div>
                    <button class="save-btn" onclick="saveWeight()">Salvar Peso</button>
                    
                    <div class="chart-container">
                        <canvas id="weightChart" class="chart-canvas"></canvas>
                    </div>

                    <div class="history-list" id="weightHistory"></div>
                </div>

                <!-- Measurements Tracking -->
                <div class="tracking-card">
                    <h3 class="tracking-title">📏 Medidas Corporais</h3>
                    <div class="input-group">
                        <label class="input-label">Data</label>
                        <input type="date" class="input-field" id="measureDate">
                    </div>
                    <div class="input-group">
                        <label class="input-label">Cintura (cm)</label>
                        <input type="number" step="0.1" class="input-field" id="waistInput" placeholder="Ex: 75.0">
                    </div>
                    <div class="input-group">
                        <label class="input-label">Quadril (cm)</label>
                        <input type="number" step="0.1" class="input-field" id="hipsInput" placeholder="Ex: 95.0">
                    </div>
                    <div class="input-group">
                        <label class="input-label">Abdômen (cm)</label>
                        <input type="number" step="0.1" class="input-field" id="bellyInput" placeholder="Ex: 80.0">
                    </div>
                    <button class="save-btn" onclick="saveMeasurements()">Salvar Medidas</button>

                    <div class="history-list" id="measureHistory"></div>
                </div>

                <!-- Progress Chart -->
                <div class="tracking-card" style="grid-column: span 2;">
                    <h3 class="tracking-title">📈 Evolução Completa</h3>
                    <div class="chart-container" style="height: 400px;">
                        <canvas id="progressChart" class="chart-canvas"></canvas>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <button class="scroll-top" onclick="scrollToTop()">↑</button>

    <footer>
        <div class="footer-signature">Carlos Eduardo - SIGNATURE Personal Elite</div>
        <p class="footer-tagline">"Resultados que parecem impossíveis, com métodos que fazem sentido."</p>
        <p class="footer-warning">Protocolo desenvolvido exclusivamente para Ana Paula.<br>Reprodução ou compartilhamento proibidos.</p>
    </footer>

    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script>
        'use strict';
        
        // Safari localStorage check
        function isLocalStorageAvailable() {
            try {
                const test = '__localStorage_test__';
                localStorage.setItem(test, test);
                localStorage.removeItem(test);
                return true;
            } catch(e) {
                return false;
            }
        }

        // Fallback storage for Safari private mode
        let fallbackStorage = {};

        function getStorage() {
            if (isLocalStorageAvailable()) {
                return localStorage;
            }
            return {
                getItem: (key) => fallbackStorage[key] || null,
                setItem: (key, value) => { fallbackStorage[key] = value; },
                removeItem: (key) => { delete fallbackStorage[key]; }
            };
        }

        const storage = getStorage();
        // Create particles
        function createParticles() {
            const bgAnimation = document.querySelector('.bg-animation');
            const particleCount = 50;
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.animationDuration = (Math.random() * 10 + 10) + 's';
                particle.style.animationDelay = Math.random() * 5 + 's';
                bgAnimation.appendChild(particle);
            }
        }

        // Initialize particles
        createParticles();

        // Set default dates
        document.getElementById('weightDate').valueAsDate = new Date();
        document.getElementById('measureDate').valueAsDate = new Date();

        // Local Storage Functions
        function getWeightHistory() {
            return JSON.parse(storage.getItem('weightHistory') || '[]');
        }

        function getMeasureHistory() {
            return JSON.parse(storage.getItem('measureHistory') || '[]');
        }

        function saveWeight() {
            const date = document.getElementById('weightDate').value;
            const weight = parseFloat(document.getElementById('weightInput').value);
            
            if (!date || !weight) {
                alert('Por favor, preencha todos os campos!');
                return;
            }

            const history = getWeightHistory();
            history.push({ date, weight, timestamp: Date.now() });
            history.sort((a, b) => new Date(a.date) - new Date(b.date));
            storage.setItem('weightHistory', JSON.stringify(history));
            
            document.getElementById('weightInput').value = '';
            updateWeightDisplay();
            updateMetrics();
        }

        function saveMeasurements() {
            const date = document.getElementById('measureDate').value;
            const waist = parseFloat(document.getElementById('waistInput').value);
            const hips = parseFloat(document.getElementById('hipsInput').value);
            const belly = parseFloat(document.getElementById('bellyInput').value);
            
            if (!date || !waist || !hips || !belly) {
                alert('Por favor, preencha todos os campos!');
                return;
            }

            const history = getMeasureHistory();
            history.push({ date, waist, hips, belly, timestamp: Date.now() });
            history.sort((a, b) => new Date(a.date) - new Date(b.date));
            storage.setItem('measureHistory', JSON.stringify(history));
            
            document.getElementById('waistInput').value = '';
            document.getElementById('hipsInput').value = '';
            document.getElementById('bellyInput').value = '';
            updateMeasureDisplay();
            updateProgressChart();
        }

        function deleteWeight(timestamp) {
            let history = getWeightHistory();
            history = history.filter(item => item.timestamp !== timestamp);
            storage.setItem('weightHistory', JSON.stringify(history));
            updateWeightDisplay();
            updateMetrics();
        }

        function deleteMeasure(timestamp) {
            let history = getMeasureHistory();
            history = history.filter(item => item.timestamp !== timestamp);
            storage.setItem('measureHistory', JSON.stringify(history));
            updateMeasureDisplay();
            updateProgressChart();
        }

        function updateMetrics() {
            const history = getWeightHistory();
            if (history.length > 0) {
                const latestWeight = history[history.length - 1].weight;
                const initialWeight = 68.0;
                const progress = initialWeight - latestWeight;
                
                document.getElementById('currentWeight').textContent = latestWeight.toFixed(1);
                document.getElementById('progressValue').textContent = progress.toFixed(1);
                
                const changeElement = document.getElementById('weightChange');
                if (progress > 0) {
                    changeElement.textContent = '↓ ' + progress.toFixed(1) + ' kg';
                    changeElement.className = 'metric-change positive';
                } else if (progress < 0) {
                    changeElement.textContent = '↑ ' + Math.abs(progress).toFixed(1) + ' kg';
                    changeElement.className = 'metric-change negative';
                } else {
                    changeElement.textContent = 'kg';
                    changeElement.className = 'metric-change';
                }
            }
        }

        function updateWeightDisplay() {
            const history = getWeightHistory();
            const container = document.getElementById('weightHistory');
            container.innerHTML = '';
            
            history.reverse().forEach(item => {
                const div = document.createElement('div');
                div.className = 'history-item';
                div.innerHTML = `
                    <div>
                        <div class="history-date">${new Date(item.date).toLocaleDateString('pt-BR')}</div>
                        <div class="history-value">${item.weight.toFixed(1)} kg</div>
                    </div>
                    <button class="delete-btn" onclick="deleteWeight(${item.timestamp})">Excluir</button>
                `;
                container.appendChild(div);
            });
            
            updateWeightChart();
        }

        function updateMeasureDisplay() {
            const history = getMeasureHistory();
            const container = document.getElementById('measureHistory');
            container.innerHTML = '';
            
            history.reverse().forEach(item => {
                const div = document.createElement('div');
                div.className = 'history-item';
                div.innerHTML = `
                    <div>
                        <div class="history-date">${new Date(item.date).toLocaleDateString('pt-BR')}</div>
                        <div style="font-size: 0.9rem; color: var(--gray); margin-top: 0.5rem;">
                            Cintura: ${item.waist}cm | Quadril: ${item.hips}cm | Abdômen: ${item.belly}cm
                        </div>
                    </div>
                    <button class="delete-btn" onclick="deleteMeasure(${item.timestamp})">Excluir</button>
                `;
                container.appendChild(div);
            });
        }

        // Charts
        let weightChart, progressChart;

        function updateWeightChart() {
            const history = getWeightHistory();
            const ctx = document.getElementById('weightChart');
            
            if (weightChart) {
                weightChart.destroy();
            }

            weightChart = new Chart(ctx, {
                type: 'line',
                data: {
                    labels: history.map(item => new Date(item.date).toLocaleDateString('pt-BR')),
                    datasets: [{
                        label: 'Peso (kg)',
                        data: history.map(item => item.weight),
                        borderColor: '#ff006e',
                        backgroundColor: 'rgba(255, 0, 110, 0.1)',
                        borderWidth: 3,
                        fill: true,
                        tension: 0.4
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: {
                            labels: { color: '#ffffff' }
                        }
                    },
                    scales: {
                        y: {
                            ticks: { color: '#ffffff' },
                            grid: { color: 'rgba(255, 255, 255, 0.1)' }
                        },
                        x: {
                            ticks: { color: '#ffffff' },
                            grid: { color: 'rgba(255, 255, 255, 0.1)' }
                        }
                    }
                }
            });
        }

        function updateProgressChart() {
            const measureHistory = getMeasureHistory();
            const ctx = document.getElementById('progressChart');
            
            if (progressChart) {
                progressChart.destroy();
            }

            progressChart = new Chart(ctx, {
                type: 'line',
                data: {
                    labels: measureHistory.map(item => new Date(item.date).toLocaleDateString('pt-BR')),
                    datasets: [
                        {
                            label: 'Cintura (cm)',
                            data: measureHistory.map(item => item.waist),
                            borderColor: '#ff006e',
                            backgroundColor: 'rgba(255, 0, 110, 0.1)',
                            borderWidth: 2,
                            tension: 0.4
                        },
                        {
                            label: 'Quadril (cm)',
                            data: measureHistory.map(item => item.hips),
                            borderColor: '#ff4d94',
                            backgroundColor: 'rgba(255, 77, 148, 0.1)',
                            borderWidth: 2,
                            tension: 0.4
                        },
                        {
                            label: 'Abdômen (cm)',
                            data: measureHistory.map(item => item.belly),
                            borderColor: '#ff80b3',
                            backgroundColor: 'rgba(255, 128, 179, 0.1)',
                            borderWidth: 2,
                            tension: 0.4
                        }
                    ]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: {
                            labels: { color: '#ffffff' }
                        }
                    },
                    scales: {
                        y: {
                            ticks: { color: '#ffffff' },
                            grid: { color: 'rgba(255, 255, 255, 0.1)' }
                        },
                        x: {
                            ticks: { color: '#ffffff' },
                            grid: { color: 'rgba(255, 255, 255, 0.1)' }
                        }
                    }
                }
            });
        }

        // Initialize on load
        window.addEventListener('load', () => {
            updateWeightDisplay();
            updateMeasureDisplay();
            updateMetrics();
            updateProgressChart();
        });

        // Show specific day
        function showDay(day, button) {
            // Hide all sections
            document.querySelectorAll('.day-section').forEach(section => {
                section.classList.remove('active');
            });
            
            // Remove active class from all buttons
            document.querySelectorAll('.day-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            
            // Show selected section
            document.getElementById(day).classList.add('active');
            
            // Add active class to clicked button
            button.classList.add('active');
            
            // Scroll to top of content
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Scroll to top button
        window.addEventListener('scroll', () => {
            const scrollTop = document.querySelector('.scroll-top');
            if (window.pageYOffset > 300) {
                scrollTop.classList.add('visible');
            } else {
                scrollTop.classList.remove('visible');
            }
        });

        function scrollToTop() {
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Add focus effect to meal cards
        document.querySelectorAll('.meal-card').forEach(card => {
            card.addEventListener('mouseenter', function() {
                const allCards = this.closest('.meals-grid').querySelectorAll('.meal-card');
                
                // Add blurred class to all cards
                allCards.forEach(c => {
                    if (c !== this) {
                        c.classList.add('blurred');
                    }
                });
                
                // Add focused class to this card
                this.classList.add('focused');
            });
            
            card.addEventListener('mouseleave', function() {
                const allCards = this.closest('.meals-grid').querySelectorAll('.meal-card');
                
                // Remove all classes
                allCards.forEach(c => {
                    c.classList.remove('blurred', 'focused');
                });
            });
        });

        // Parallax effect on scroll
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const parallax = document.querySelector('.bg-animation');
            if (parallax) {
                parallax.style.transform = `translateY(${scrolled * 0.5}px)`;
            }
        });
    </script>
</body>
</html>
