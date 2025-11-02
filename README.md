<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Космос Чисел - NumerologyLab</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #2c3e50;
            --secondary: #3498db;
            --accent: #9b59b6;
            --light: #ecf0f1;
            --dark: #2c3e50;
            --success: #2ecc71;
            --warning: #f39c12;
            --danger: #e74c3c;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        html, body {
            max-width: 100%;
            overflow-x: hidden;
        }
        
        body {
            background-color: #f5f7fa;
            color: var(--dark);
            line-height: 1.6;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        /* Header */
        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 1rem 0;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .logo h1 {
            font-size: 1.8rem;
            font-weight: 700;
        }
        
        .logo-icon {
            font-size: 2rem;
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 1.5rem;
        }
        
        nav ul li a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            padding: 0.5rem 0.8rem;
            border-radius: 4px;
        }
        
        nav ul li a:hover {
            background-color: rgba(255,255,255,0.1);
        }
        
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(44, 62, 80, 0.8), rgba(44, 62, 80, 0.9)), url('https://images.unsplash.com/photo-1534447677768-be436bb09401?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-position: center;
            color: white;
            padding: 5rem 0;
            text-align: center;
            margin: 0;
            width: 100%;
            overflow-x: hidden;
        }
        
        .hero h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 2rem;
        }
        
        .btn {
            display: inline-block;
            background-color: var(--accent);
            color: white;
            padding: 0.8rem 1.5rem;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            font-size: 1rem;
        }
        
        .btn:hover {
            background-color: #8e44ad;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        /* Features Section */
        .features {
            padding: 5rem 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 3rem;
        }
        
        .section-title h2 {
            font-size: 2.2rem;
            color: var(--primary);
            margin-bottom: 0.5rem;
        }
        
        .section-title p {
            color: #7f8c8d;
            max-width: 600px;
            margin: 0 auto;
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .feature-card {
            background: white;
            border-radius: 10px;
            padding: 2rem;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: all 0.3s ease;
            text-align: center;
            cursor: pointer;
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
        }
        
        .feature-icon {
            font-size: 3rem;
            color: var(--secondary);
            margin-bottom: 1rem;
        }
        
        .feature-card h3 {
            font-size: 1.4rem;
            margin-bottom: 1rem;
            color: var(--primary);
        }
        
        /* Calculators Section */
        .calculators {
            padding: 5rem 0;
            background-color: #f8f9fa;
        }
        
        .calculator-tabs {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            justify-content: center;
            margin-bottom: 2rem;
        }
        
        .calculator-tab {
            background: white;
            padding: 1rem 1.5rem;
            border-radius: 30px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 3px 10px rgba(0,0,0,0.05);
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .calculator-tab.active {
            background-color: var(--secondary);
            color: white;
        }
        
        .calculator-content {
            background: white;
            border-radius: 10px;
            padding: 2rem;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            min-height: 500px;
        }
        
        .calculator-form {
            max-width: 600px;
            margin: 0 auto;
        }
        
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }
        
        .form-group input, .form-group select, .form-group textarea {
            width: 100%;
            padding: 0.8rem 1rem;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
        }
        
        .calculator-result {
            margin-top: 2rem;
            padding: 1.5rem;
            background-color: #f8f9fa;
            border-radius: 5px;
            display: none;
        }
        
        .calculator-result h3 {
            margin-bottom: 1rem;
            color: var(--primary);
        }
        
        .result-number {
            font-size: 3rem;
            font-weight: bold;
            color: var(--accent);
            text-align: center;
            margin: 1rem 0;
        }
        
        .strengths, .weaknesses, .advice {
            margin: 1.5rem 0;
            padding: 1rem;
            border-radius: 5px;
        }
        
        .strengths {
            background-color: rgba(46, 204, 113, 0.1);
            border-left: 4px solid var(--success);
        }
        
        .weaknesses {
            background-color: rgba(231, 76, 60, 0.1);
            border-left: 4px solid var(--danger);
        }
        
        .advice {
            background-color: rgba(52, 152, 219, 0.1);
            border-left: 4px solid var(--secondary);
        }
        
        /* Стили для дней планирования */
        .days-list {
            margin: 1.5rem 0;
        }
        
        .day-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0.8rem 1rem;
            margin-bottom: 0.5rem;
            background: white;
            border-radius: 5px;
            border-left: 4px solid var(--success);
            box-shadow: 0 2px 5px rgba(0,0,0,0.05);
        }
        
        .day-item.dangerous {
            border-left-color: var(--danger);
            background-color: rgba(231, 76, 60, 0.05);
        }
        
        .day-date {
            font-weight: 600;
            color: var(--dark);
        }
        
        .day-weekday {
            color: #7f8c8d;
            font-size: 0.9rem;
        }
        
        .day-description {
            color: #7f8c8d;
            font-size: 0.9rem;
        }
        
        .day-rating {
            font-weight: 600;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
        }
        
        .rating-good {
            background-color: rgba(46, 204, 113, 0.2);
            color: var(--success);
        }
        
        .rating-neutral {
            background-color: rgba(243, 156, 18, 0.2);
            color: var(--warning);
        }
        
        .rating-bad {
            background-color: rgba(231, 76, 60, 0.2);
            color: var(--danger);
        }
        
        .compatibility-result {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 1rem;
        }
        
        .compatibility-score {
            font-size: 2.5rem;
            font-weight: bold;
            color: var(--accent);
            text-align: center;
        }
        
        .compatibility-bar {
            width: 100%;
            height: 20px;
            background-color: #e0e0e0;
            border-radius: 10px;
            overflow: hidden;
            margin: 1rem 0;
        }
        
        .compatibility-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--danger), var(--warning), var(--success));
            border-radius: 10px;
            transition: width 1s ease;
        }
        
        .matrix-container {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
            max-width: 300px;
            margin: 0 auto;
        }
        
        .matrix-cell {
            aspect-ratio: 1;
            display: flex;
            align-items: center;
            justify-content: center;
            background-color: #f8f9fa;
            border-radius: 5px;
            font-weight: bold;
            font-size: 1.5rem;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        .matrix-cell.active {
            background-color: var(--accent);
            color: white;
        }
        
        .portrait-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem;
            margin-top: 1.5rem;
        }
        
        .portrait-card {
            background: white;
            border-radius: 8px;
            padding: 1.5rem;
            box-shadow: 0 3px 10px rgba(0,0,0,0.08);
            transition: all 0.3s ease;
        }
        
        .portrait-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .portrait-card h4 {
            color: var(--primary);
            margin-bottom: 0.8rem;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .portrait-number {
            font-size: 2.5rem;
            font-weight: bold;
            color: var(--accent);
            text-align: center;
            margin: 0.5rem 0;
        }
        
        .portrait-description {
            font-size: 0.9rem;
            color: #7f8c8d;
            line-height: 1.5;
        }
        
        /* Стили для выбора метода расчета совместимости */
        .method-selector {
            display: flex;
            gap: 1rem;
            margin-bottom: 1.5rem;
            flex-wrap: wrap;
        }
        
        .method-option {
            flex: 1;
            min-width: 150px;
            text-align: center;
            padding: 1rem;
            background: #f8f9fa;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .method-option.active {
            background: var(--secondary);
            color: white;
            border-color: var(--secondary);
        }
        
        .method-option:hover {
            border-color: var(--secondary);
        }
        
        .method-icon {
            font-size: 2rem;
            margin-bottom: 0.5rem;
        }
        
        /* Адаптивные стили для выбора метода */
        @media (max-width: 576px) {
            .method-selector {
                flex-direction: column;
            }
            
            .method-option {
                min-width: 100%;
            }
        }
        
        /* Blog Section */
        .blog {
            padding: 5rem 0;
        }
        
        .blog-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .blog-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: all 0.3s ease;
        }
        
        .blog-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }
        
        .blog-card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }
        
        .blog-card-content {
            padding: 1.5rem;
        }
        
        .blog-card h3 {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
            color: var(--primary);
        }
        
        .blog-card p {
            color: #7f8c8d;
            margin-bottom: 1rem;
        }
        
        .blog-card a {
            color: var(--secondary);
            text-decoration: none;
            font-weight: 500;
        }
        
        /* Footer */
        footer {
            background-color: var(--primary);
            color: white;
            padding: 3rem 0 1rem;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }
        
        .footer-column h3 {
            font-size: 1.2rem;
            margin-bottom: 1.5rem;
            position: relative;
            padding-bottom: 0.5rem;
        }
        
        .footer-column h3::after {
            content: '';
            position: absolute;
            left: 0;
            bottom: 0;
            width: 40px;
            height: 2px;
            background-color: var(--secondary);
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column ul li {
            margin-bottom: 0.8rem;
        }
        
        .footer-column ul li a {
            color: #bdc3c7;
            text-decoration: none;
            transition: all 0.3s ease;
        }
        
        .footer-column ul li a:hover {
            color: white;
            padding-left: 5px;
        }
        
        .copyright {
            text-align: center;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(255,255,255,0.1);
            color: #bdc3c7;
            font-size: 0.9rem;
        }
        
        /* Responsive */
        @media (max-width: 992px) {
            .matrix-container {
                max-width: 250px;
            }
            
            .matrix-cell {
                font-size: 1.2rem;
            }
        }
        
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                text-align: center;
            }
            
            nav ul {
                margin-top: 1rem;
                flex-wrap: wrap;
                justify-content: center;
            }
            
            nav ul li {
                margin: 0.5rem;
            }
            
            .hero h2 {
                font-size: 2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .calculator-tabs {
                flex-direction: column;
                align-items: center;
            }
            
            .calculator-tab {
                width: 100%;
                max-width: 300px;
                justify-content: center;
            }
            
            .day-item {
                flex-direction: column;
                align-items: flex-start;
                gap: 0.5rem;
            }
        }
        
        @media (max-width: 576px) {
            .mobile-menu-btn {
                display: block;
                position: absolute;
                top: 1rem;
                right: 1rem;
            }
            
            nav {
                display: none;
                width: 100%;
                margin-top: 1rem;
            }
            
            nav.active {
                display: block;
            }
            
            nav ul {
                flex-direction: column;
            }
            
            nav ul li {
                margin: 0.5rem 0;
            }
            
            .matrix-container {
                max-width: 200px;
            }
            
            .matrix-cell {
                font-size: 1rem;
            }
            
            .result-number {
                font-size: 2.5rem;
            }
            
            /* Исправления для hero секции на мобильных */
            .hero {
                padding: 3rem 0;
                margin: 0;
                width: 100%;
            }
            
            .hero h2 {
                font-size: 1.8rem;
                padding: 0 10px;
            }
            
            .hero p {
                font-size: 1rem;
                padding: 0 10px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <span class="logo-icon">🔢</span>
                    <h1>Космос Чисел</h1>
                </div>
                <button class="mobile-menu-btn">☰</button>
                <nav>
                    <ul>
                        <li><a href="#home">Главная</a></li>
                        <li><a href="#about">О нумерологии</a></li>
                        <li><a href="#calculators">Калькуляторы</a></li>
                        <li><a href="#compatibility">Совместимость</a></li>
                        <li><a href="#blog">Блог</a></li>
                        <li><a href="#contacts">Контакты</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <h2>Раскройте тайны вашей судьбы с помощью чисел</h2>
            <p>NumerologyLab превращает сложные нумерологические расчеты в простые инструменты для самопознания и планирования жизни</p>
            <a href="#calculators" class="btn">Рассчитайте свое Число Жизненного Пути</a>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features">
        <div class="container">
            <div class="section-title">
                <h2>Наши возможности</h2>
                <p>Откройте для себя полный спектр нумерологических инструментов для самопознания</p>
            </div>
            <div class="features-grid">
                <div class="feature-card" data-tab="life-path">
                    <div class="feature-icon">🌌</div>
                    <h3>Число Жизненного Пути</h3>
                    <p>Узнайте свое основное число, которое определяет ваш жизненный путь и предназначение</p>
                </div>
                <div class="feature-card" data-tab="compatibility">
                    <div class="feature-icon">💫</div>
                    <h3>Совместимость</h3>
                    <p>Проанализируйте совместимость с партнером, друзьями или коллегами по числам</p>
                </div>
                <div class="feature-card" data-tab="planning">
                    <div class="feature-icon">📅</div>
                    <h3>Планирование</h3>
                    <p>Определите благоприятные дни для важных событий с помощью нумерологии</p>
                </div>
                <div class="feature-card" data-tab="matrix">
                    <div class="feature-icon">📊</div>
                    <h3>Матрица Судьбы</h3>
                    <p>Получите полный нумерологический портрет с помощью современной матрицы</p>
                </div>
                <div class="feature-card" data-tab="portrait">
                    <div class="feature-icon">👤</div>
                    <h3>Нумерологический портрет</h3>
                    <p>Полный анализ личности по Ф.И.О. с детальной расшифровкой</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Calculators Section -->
    <section class="calculators" id="calculators">
        <div class="container">
            <div class="section-title">
                <h2>Нумерологические калькуляторы</h2>
                <p>Выберите нужный калькулятор и получите персональную расшифровку</p>
            </div>
            <div class="calculator-tabs">
                <div class="calculator-tab active" data-tab="life-path">
                    <i class="fas fa-user"></i> Число Жизненного Пути
                </div>
                <div class="calculator-tab" data-tab="compatibility">
                    <i class="fas fa-heart"></i> Совместимость
                </div>
                <div class="calculator-tab" data-tab="planning">
                    <i class="fas fa-calendar-alt"></i> Планирование
                </div>
                <div class="calculator-tab" data-tab="matrix">
                    <i class="fas fa-th"></i> Матрица Судьбы
                </div>
                <div class="calculator-tab" data-tab="portrait">
                    <i class="fas fa-id-card"></i> Нумерологический портрет
                </div>
            </div>
            <div class="calculator-content">
                <!-- Число Жизненного Пути -->
                <div class="calculator-form" id="life-path-form">
                    <h3>Расчет Числа Жизненного Пути</h3>
                    <p>Введите вашу дату рождения, чтобы узнать основное число вашей жизни</p>
                    <div class="form-group">
                        <label for="birth-date">Дата рождения</label>
                        <input type="date" id="birth-date" required>
                    </div>
                    <button class="btn" id="calculate-life-path">Рассчитать</button>
                    <div class="calculator-result" id="life-path-result">
                        <h3>Ваше Число Жизненного Пути</h3>
                        <div class="result-number" id="life-path-number"></div>
                        <p id="life-path-description"></p>
                        
                        <div class="strengths">
                            <h4><i class="fas fa-star"></i> Сильные стороны</h4>
                            <p id="life-path-strengths"></p>
                        </div>
                        
                        <div class="weaknesses">
                            <h4><i class="fas fa-exclamation-triangle"></i> Слабые стороны</h4>
                            <p id="life-path-weaknesses"></p>
                        </div>
                        
                        <div class="advice">
                            <h4><i class="fas fa-lightbulb"></i> Советы по развитию</h4>
                            <p id="life-path-advice"></p>
                        </div>
                    </div>
                </div>
                
                <!-- Совместимость -->
                <div class="calculator-form" id="compatibility-form" style="display: none;">
                    <h3>Расчет совместимости по числам судьбы</h3>
                    <p>Выберите метод расчета и введите данные двух людей для анализа их совместимости</p>
                    
                    <!-- Выбор метода расчета -->
                    <div class="method-selector">
                        <div class="method-option active" data-method="names">
                            <div class="method-icon"><i class="fas fa-user-friends"></i></div>
                            <div>По именам</div>
                        </div>
                        <div class="method-option" data-method="birthdates">
                            <div class="method-icon"><i class="fas fa-birthday-cake"></i></div>
                            <div>По датам рождения</div>
                        </div>
                        <div class="method-option" data-method="combined">
                            <div class="method-icon"><i class="fas fa-random"></i></div>
                            <div>Комбинированный</div>
                        </div>
                    </div>
                    
                    <!-- Форма для ввода данных -->
                    <div class="form-group">
                        <label for="person1-name">Имя первого человека</label>
                        <input type="text" id="person1-name" placeholder="Введите полное имя">
                    </div>
                    
                    <div class="form-group" id="person1-birthdate-group">
                        <label for="person1-birthdate">Дата рождения первого человека</label>
                        <input type="date" id="person1-birthdate">
                    </div>
                    
                    <div class="form-group">
                        <label for="person2-name">Имя второго человека</label>
                        <input type="text" id="person2-name" placeholder="Введите полное имя">
                    </div>
                    
                    <div class="form-group" id="person2-birthdate-group">
                        <label for="person2-birthdate">Дата рождения второго человека</label>
                        <input type="date" id="person2-birthdate">
                    </div>
                    
                    <button class="btn" id="calculate-compatibility">Рассчитать совместимость</button>
                    
                    <div class="calculator-result" id="compatibility-result">
                        <h3>Результат совместимости</h3>
                        <div class="compatibility-result">
                            <div class="compatibility-score" id="compatibility-percentage">0%</div>
                            <div class="compatibility-bar">
                                <div class="compatibility-fill" id="compatibility-fill" style="width: 0%"></div>
                            </div>
                            <p id="compatibility-description"></p>
                            
                            <div class="strengths">
                                <h4><i class="fas fa-star"></i> Сильные стороны отношений</h4>
                                <p id="compatibility-strengths"></p>
                            </div>
                            
                            <div class="weaknesses">
                                <h4><i class="fas fa-exclamation-triangle"></i> Проблемные зоны</h4>
                                <p id="compatibility-weaknesses"></p>
                            </div>
                            
                            <div class="advice">
                                <h4><i class="fas fa-lightbulb"></i> Советы для гармонии</h4>
                                <p id="compatibility-advice"></p>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Планирование -->
                <div class="calculator-form" id="planning-form" style="display: none;">
                    <h3>Нумерологическое планирование</h3>
                    <p>Определите благоприятные и опасные дни для важных событий на основе вашего числа жизненного пути</p>
                    
                    <div class="form-group">
                        <label for="user-birthdate-planning">Ваша дата рождения</label>
                        <input type="date" id="user-birthdate-planning">
                    </div>
                    
                    <div class="form-group">
                        <label for="event-type">Тип события</label>
                        <select id="event-type">
                            <option value="business">Бизнес/Карьера</option>
                            <option value="love">Любовь/Отношения</option>
                            <option value="health">Здоровье</option>
                            <option value="travel">Путешествия</option>
                            <option value="creativity">Творчество</option>
                            <option value="family">Семья/Дом</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="planning-period">Период планирования</label>
                        <select id="planning-period">
                            <option value="week">Следующая неделя</option>
                            <option value="month">Следующий месяц</option>
                            <option value="quarter">Следующий квартал</option>
                            <option value="year">Следующий год</option>
                        </select>
                    </div>
                    
                    <button class="btn" id="calculate-planning">Найти благоприятные дни</button>
                    
                    <div class="calculator-result" id="planning-result">
                        <h3>Рекомендации по планированию</h3>
                        
                        <div class="days-list" id="favorable-days">
                            <!-- Благоприятные дни будут добавлены здесь -->
                        </div>
                        
                        <div class="weaknesses">
                            <h4><i class="fas fa-exclamation-triangle"></i> Опасные дни</h4>
                            <div class="days-list" id="dangerous-days">
                                <!-- Опасные дни будут добавлены здесь -->
                            </div>
                        </div>
                        
                        <div class="advice">
                            <h4><i class="fas fa-lightbulb"></i> Рекомендации по планированию</h4>
                            <p id="planning-advice"></p>
                        </div>
                    </div>
                </div>
                
                <!-- Матрица Судьбы -->
                <div class="calculator-form" id="matrix-form" style="display: none;">
                    <h3>Матрица Судьбы</h3>
                    <p>Получите полный нумерологический портрет по дате рождения</p>
                    
                    <div class="form-group">
                        <label for="matrix-birthdate">Дата рождения</label>
                        <input type="date" id="matrix-birthdate">
                    </div>
                    
                    <button class="btn" id="calculate-matrix">Построить матрицу</button>
                    
                    <div class="calculator-result" id="matrix-result">
                        <h3>Ваша матрица судьбы</h3>
                        
                        <div class="matrix-container" id="matrix-container">
                            <!-- Матрица будет сгенерирована скриптом -->
                        </div>
                        
                        <div class="matrix-description" id="matrix-description"></div>
                        
                        <div class="strengths">
                            <h4><i class="fas fa-star"></i> Ваши таланты и способности</h4>
                            <p id="matrix-strengths"></p>
                        </div>
                        
                        <div class="weaknesses">
                            <h4><i class="fas fa-exclamation-triangle"></i> Кармические задачи</h4>
                            <p id="matrix-weaknesses"></p>
                        </div>
                        
                        <div class="advice">
                            <h4><i class="fas fa-lightbulb"></i> Рекомендации по развитию</h4>
                            <p id="matrix-advice"></p>
                        </div>
                    </div>
                </div>
                
                <!-- Нумерологический портрет -->
                <div class="calculator-form" id="portrait-form" style="display: none;">
                    <h3>Нумерологический портрет личности</h3>
                    <p>Полный анализ личности по Ф.И.О. с расчетом всех основных чисел и подробной расшифровкой</p>
                    
                    <div class="form-group">
                        <label for="full-name">Фамилия Имя Отчество</label>
                        <input type="text" id="full-name" placeholder="Введите ваше полное Ф.И.О." required>
                    </div>
                    
                    <div class="form-group">
                        <label for="portrait-birthdate">Дата рождения</label>
                        <input type="date" id="portrait-birthdate" required>
                    </div>
                    
                    <button class="btn" id="calculate-portrait">Создать портрет</button>
                    
                    <div class="calculator-result" id="portrait-result">
                        <h3>Ваш нумерологический портрет</h3>
                        <p class="portrait-intro">На основе вашего Ф.И.О. и даты рождения мы рассчитали ключевые нумерологические числа, которые раскрывают вашу личность, таланты и жизненный путь.</p>
                        
                        <div class="portrait-grid">
                            <div class="portrait-card">
                                <h4><i class="fas fa-user"></i> Число Жизненного Пути</h4>
                                <div class="portrait-number" id="portrait-life-path"></div>
                                <div class="portrait-description" id="portrait-life-path-desc"></div>
                            </div>
                            
                            <div class="portrait-card">
                                <h4><i class="fas fa-star"></i> Число Судьбы</h4>
                                <div class="portrait-number" id="portrait-destiny"></div>
                                <div class="portrait-description" id="portrait-destiny-desc"></div>
                            </div>
                            
                            <div class="portrait-card">
                                <h4><i class="fas fa-heart"></i> Число Души</h4>
                                <div class="portrait-number" id="portrait-soul"></div>
                                <div class="portrait-description" id="portrait-soul-desc"></div>
                            </div>
                            
                            <div class="portrait-card">
                                <h4><i class="fas fa-eye"></i> Число Внешнего Облика</h4>
                                <div class="portrait-number" id="portrait-appearance"></div>
                                <div class="portrait-description" id="portrait-appearance-desc"></div>
                            </div>
                            
                            <div class="portrait-card">
                                <h4><i class="fas fa-birthday-cake"></i> Число Дня Рождения</h4>
                                <div class="portrait-number" id="portrait-birthday"></div>
                                <div class="portrait-description" id="portrait-birthday-desc"></div>
                            </div>
                            
                            <div class="portrait-card">
                                <h4><i class="fas fa-balance-scale"></i> Число Кармического Долга</h4>
                                <div class="portrait-number" id="portrait-karmic"></div>
                                <div class="portrait-description" id="portrait-karmic-desc"></div>
                            </div>
                        </div>
                        
                        <div class="strengths">
                            <h4><i class="fas fa-star"></i> Ваши ключевые качества и таланты</h4>
                            <p id="portrait-strengths"></p>
                        </div>
                        
                        <div class="weaknesses">
                            <h4><i class="fas fa-exclamation-triangle"></i> Зоны развития и вызовы</h4>
                            <p id="portrait-weaknesses"></p>
                        </div>
                        
                        <div class="advice">
                            <h4><i class="fas fa-lightbulb"></i> Рекомендации для гармоничной жизни</h4>
                            <p id="portrait-advice"></p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Blog Section -->
    <section class="blog" id="blog">
        <div class="container">
            <div class="section-title">
                <h2>Полезные статьи о нумерологии</h2>
                <p>Углубите свои знания с помощью наших экспертных материалов</p>
            </div>
            <div class="blog-grid">
                <div class="blog-card">
                    <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Мастер-числа">
                    <div class="blog-card-content">
                        <h3>Мастер-числа 11, 22, 33: сила и ответственность</h3>
                        <p>Узнайте о особых вибрациях мастер-чисел и их влиянии на вашу жизнь</p>
                        <a href="#">Читать далее →</a>
                    </div>
                </div>
                <div class="blog-card">
                    <img src="https://images.unsplash.com/photo-1553406830-ef2513450d76?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Кармические числа">
                    <div class="blog-card-content">
                        <h3>Кармические числа: уроки прошлых жизней</h3>
                        <p>Как распознать и работать с кармическими числами 13, 14, 16 и 19</p>
                        <a href="#">Читать далее →</a>
                    </div>
                </div>
                <div class="blog-card">
                    <img src="https://images.unsplash.com/photo-1534447677768-be436bb09401?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Личный год">
                    <div class="blog-card-content">
                        <h3>Личный год: как планировать жизнь по циклам</h3>
                        <p>Определите свой текущий личный год и используйте его энергию для достижения целей</p>
                        <a href="#">Читать далее →</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contacts">
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>Космос Чисел</h3>
                    <p>NumerologyLab - ваш проводник в мире нумерологии. Мы превращаем сложные расчеты в простые инструменты для самопознания.</p>
                </div>
                <div class="footer-column">
                    <h3>Калькуляторы</h3>
                    <ul>
                        <li><a href="#">Число Жизненного Пути</a></li>
                        <li><a href="#">Число Судьбы</a></li>
                        <li><a href="#">Число Души</a></li>
                        <li><a href="#">Совместимость</a></li>
                        <li><a href="#">Матрица Судьбы</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Ресурсы</h3>
                    <ul>
                        <li><a href="#">Блог</a></li>
                        <li><a href="#">О нумерологии</a></li>
                        <li><a href="#">Словарь терминов</a></li>
                        <li><a href="#">Частые вопросы</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Контакты</h3>
                    <ul>
                        <li>Email: info@numerologylab.ru</li>
                        <li>Телефон: +7 (999) 123-45-67</li>
                        <li>Социальные сети:</li>
                        <li>
                            <a href="#">VK</a> | 
                            <a href="#">Telegram</a> | 
                            <a href="#">YouTube</a>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 NumerologyLab "Космос Чисел". Все права защищены.</p>
            </div>
        </div>
    </footer>

    <script>
        // Мобильное меню
        document.querySelector('.mobile-menu-btn').addEventListener('click', function() {
            document.querySelector('nav').classList.toggle('active');
        });
        
        // Кликабельные блоки функций
        document.querySelectorAll('.feature-card').forEach(card => {
            card.addEventListener('click', function() {
                const tabName = this.getAttribute('data-tab');
                switchToTab(tabName);
            });
        });
        
        // Табы калькуляторов
        const tabs = document.querySelectorAll('.calculator-tab');
        const forms = {
            'life-path': document.getElementById('life-path-form'),
            'compatibility': document.getElementById('compatibility-form'),
            'planning': document.getElementById('planning-form'),
            'matrix': document.getElementById('matrix-form'),
            'portrait': document.getElementById('portrait-form')
        };
        
        function switchToTab(tabName) {
            // Скрыть все формы
            Object.values(forms).forEach(form => {
                form.style.display = 'none';
            });
            
            // Показать выбранную форму
            forms[tabName].style.display = 'block';
            
            // Обновить активную вкладку
            tabs.forEach(t => t.classList.remove('active'));
            document.querySelector(`.calculator-tab[data-tab="${tabName}"]`).classList.add('active');
            
            // Прокрутить к калькуляторам
            document.getElementById('calculators').scrollIntoView({ behavior: 'smooth' });
        }
        
        tabs.forEach(tab => {
            tab.addEventListener('click', function() {
                const tabName = this.getAttribute('data-tab');
                switchToTab(tabName);
            });
        });
        
        // Выбор метода расчета совместимости
        let currentMethod = 'names';
        const methodOptions = document.querySelectorAll('.method-option');
        
        methodOptions.forEach(option => {
            option.addEventListener('click', function() {
                // Убрать активный класс у всех опций
                methodOptions.forEach(opt => opt.classList.remove('active'));
                // Добавить активный класс к выбранной опции
                this.classList.add('active');
                // Сохранить выбранный метод
                currentMethod = this.getAttribute('data-method');
                
                // Показать/скрыть поля ввода в зависимости от выбранного метода
                updateFormVisibility();
            });
        });
        
        function updateFormVisibility() {
            const nameFields = document.querySelectorAll('input[type="text"]');
            const dateFields = [
                document.getElementById('person1-birthdate-group'),
                document.getElementById('person2-birthdate-group')
            ];
            
            switch(currentMethod) {
                case 'names':
                    nameFields.forEach(field => field.style.display = 'block');
                    dateFields.forEach(field => field.style.display = 'none');
                    break;
                case 'birthdates':
                    nameFields.forEach(field => field.style.display = 'none');
                    dateFields.forEach(field => field.style.display = 'block');
                    break;
                case 'combined':
                    nameFields.forEach(field => field.style.display = 'block');
                    dateFields.forEach(field => field.style.display = 'block');
                    break;
            }
        }
        
        // Инициализация видимости полей при загрузке
        updateFormVisibility();
        
        // Вспомогательные функции
        function reduceNumber(num) {
            while (num > 9 && num !== 11 && num !== 22 && num !== 33) {
                let sum = 0;
                while (num > 0) {
                    sum += num % 10;
                    num = Math.floor(num / 10);
                }
                num = sum;
            }
            return num;
        }
        
        // Функции для жизненного пути
        function getLifePathDescription(number) {
            const descriptions = {
                1: "Вы - прирожденный лидер, независимый и амбициозный. Ваше предназначение - вести других, проявлять инициативу и создавать новое. Вы обладаете сильной волей и оригинальным мышлением, способны вдохновлять людей на свершения.",
                2: "Вы - дипломат и миротворец, чувствительный и интуитивный. Ваша роль - создавать гармонию, сотрудничать и поддерживать баланс в отношениях. Вы умеете слышать других и находить компромиссы.",
                3: "Вы - творческая личность, выразительный и оптимистичный. Ваше призвание - вдохновлять других, выражать красоту и радость через искусство, общение и самовыражение.",
                4: "Вы - практичный строитель, надежный и трудолюбивый. Ваша миссия - создавать прочный фундамент, систематизировать и организовывать. Вы цените стабильность и практичность.",
                5: "Вы - искатель свободы, адаптивный и любознательный. Ваш путь - исследовать мир, наслаждаться разнообразием и передавать свой опыт другим.",
                6: "Вы - воспитатель, ответственный и заботливый. Ваше предназначение - служить семье и обществу, создавать уют и гармонию в отношениях.",
                7: "Вы - мыслитель, аналитичный и духовный. Ваша задача - искать истину, развивать интуицию и делиться мудростью.",
                8: "Вы - организатор, амбициозный и эффективный. Ваша миссия - достигать материального успеха, управлять ресурсами и воплощать идеи в реальность.",
                9: "Вы - гуманист, сострадательный и идеалистичный. Ваше предназначение - служить человечеству, завершать циклы и нести любовь.",
                11: "Вы - просветленный, интуитивный и вдохновляющий. Ваша миссия - нести духовное озарение, вдохновлять других и служить высшим идеалам.",
                22: "Вы - мастер-строитель, практичный мечтатель. Ваша задача - реализовывать грандиозные планы на благо человечества.",
                33: "Вы - мастер-учитель, сострадательный и вдохновляющий. Ваше предназначение - служить через любовь, исцелять и возвышать человеческое сознание."
            };
            
            return descriptions[number] || "Описание для этого числа пока недоступно.";
        }
        
        function getLifePathStrengths(number) {
            const strengths = {
                1: "Лидерские качества, независимость, инициативность, оригинальность, решительность, амбициозность.",
                2: "Дипломатичность, чувствительность, интуиция, сотрудничество, терпение, тактичность.",
                3: "Креативность, оптимизм, коммуникабельность, артистизм, чувство юмора, энтузиазм.",
                4: "Надежность, практичность, трудолюбие, организованность, дисциплина, стабильность.",
                5: "Адаптивность, любознательность, прогрессивность, многосторонность, свобода, находчивость.",
                6: "Ответственность, заботливость, гармоничность, служение, сострадание, надежность.",
                7: "Аналитический ум, интуиция, мудрость, духовность, перфекционизм, проницательность.",
                8: "Организаторские способности, амбициозность, практичность, эффективность, сила воли, решимость.",
                9: "Гуманизм, сострадание, идеализм, терпимость, творчество, щедрость.",
                11: "Интуиция, вдохновение, идеализм, визионерство, чувствительность, духовность.",
                22: "Практическая мудрость, глобальное мышление, строительство, организация, мечтательность, реализация.",
                33: "Безусловная любовь, сострадание, исцеление, вдохновение, учительство, самопожертвование."
            };
            
            return strengths[number] || "Сильные стороны для этого числа пока не определены.";
        }
        
        function getLifePathWeaknesses(number) {
            const weaknesses = {
                1: "Эгоизм, агрессивность, нетерпимость, доминирование, импульсивность, упрямство.",
                2: "Чрезмерная чувствительность, нерешительность, зависимость от мнения других, пассивность.",
                3: "Поверхностность, расточительность, драматизация, нетерпение, разбросанность.",
                4: "Упрямство, консерватизм, излишняя практичность, медлительность, ригидность.",
                5: "Безответственность, непоследовательность, нетерпение, импульсивность, склонность к излишествам.",
                6: "Самопожертвование, чрезмерная опека, собственничество, критичность, мнительность.",
                7: "Цинизм, отстраненность, подозрительность, перфекционизм, скрытность.",
                8: "Материализм, властность, жесткость, трудоголизм, нетерпимость к слабостям.",
                9: "Сентиментальность, жертвенность, непрактичность, мечтательность, обидчивость.",
                11: "Нервозность, мечтательность без действия, сверхчувствительность, непрактичность.",
                22: "Давление ответственности, перфекционизм, трудоголизм, подавление эмоций.",
                33: "Чрезмерная жертвенность, эмоциональное выгорание, непрактичность, наивность."
            };
            
            return weaknesses[number] || "Слабые стороны для этого числа пока не определены.";
        }
        
        function getLifePathAdvice(number) {
            const advice = {
                1: "Развивайте терпимость к другим мнениям, учитесь сотрудничать, не подавляйте окружающих своей силой.",
                2: "Учитесь принимать решения самостоятельно, развивайте уверенность в себе, не бойтесь конфликтов.",
                3: "Сосредоточьтесь на глубине, а не на количестве проектов, развивайте дисциплину, избегайте поверхностности.",
                4: "Будьте более гибкими, открывайтесь новому, не зацикливайтесь на рутине, развивайте творческое начало.",
                5: "Учитесь завершать начатое, развивайте ответственность, найдите баланс между свободой и обязательствами.",
                6: "Не забывайте о собственных потребностях, устанавливайте здоровые границы, избегайте гиперопеки.",
                7: "Больше доверяйте людям, развивайте эмоциональный интеллект, не уходите в чрезмерную изоляцию.",
                8: "Развивайте духовность, не ставьте материальные цели выше человеческих отношений, учитесь отдыхать.",
                9: "Будьте более практичными, учитесь говорить 'нет', не позволяйте другим использовать вашу доброту.",
                11: "Заземляйте свои идеи, развивайте практические навыки, не пренебрегайте материальным миром.",
                22: "Уделяйте внимание личной жизни, не забывайте об отдыхе, развивайте эмоциональную сферу.",
                33: "Заботьтесь о себе, устанавливайте здоровые границы, не забывайте о практических аспектах жизни."
            };
            
            return advice[number] || "Советы по развитию для этого числа пока не доступны.";
        }
        
        // Расчет числа жизненного пути
        document.getElementById('calculate-life-path').addEventListener('click', function() {
            const birthDate = new Date(document.getElementById('birth-date').value);
            if (isNaN(birthDate.getTime())) {
                alert('Пожалуйста, введите корректную дату рождения');
                return;
            }
            
            const day = birthDate.getDate();
            const month = birthDate.getMonth() + 1;
            const year = birthDate.getFullYear();
            
            let lifePathNumber = reduceNumber(day) + reduceNumber(month) + reduceNumber(year);
            lifePathNumber = reduceNumber(lifePathNumber);
            
            document.getElementById('life-path-number').textContent = lifePathNumber;
            document.getElementById('life-path-description').textContent = getLifePathDescription(lifePathNumber);
            document.getElementById('life-path-strengths').textContent = getLifePathStrengths(lifePathNumber);
            document.getElementById('life-path-weaknesses').textContent = getLifePathWeaknesses(lifePathNumber);
            document.getElementById('life-path-advice').textContent = getLifePathAdvice(lifePathNumber);
            document.getElementById('life-path-result').style.display = 'block';
        });
        
        // Функции для расчета совместимости
        function calculatePersonNumbers(name, birthDate, method) {
            const numbers = {};
            
            if (method === 'names' || method === 'combined') {
                if (name && name.trim() !== '') {
                    numbers.destiny = calculateDestinyNumber(name);
                }
            }
            
            if (method === 'birthdates' || method === 'combined') {
                if (!isNaN(birthDate.getTime())) {
                    numbers.lifePath = calculateLifePathNumber(birthDate);
                }
            }
            
            return numbers;
        }
        
        function calculateLifePathNumber(birthDate) {
            const day = birthDate.getDate();
            const month = birthDate.getMonth() + 1;
            const year = birthDate.getFullYear();
            
            let lifePathNumber = reduceNumber(day) + reduceNumber(month) + reduceNumber(year);
            return reduceNumber(lifePathNumber);
        }
        
        function calculateDestinyNumber(name) {
            const letterValues = {
                'а': 1, 'б': 2, 'в': 3, 'г': 4, 'д': 5, 'е': 6, 'ё': 7, 'ж': 8, 'з': 9,
                'и': 1, 'й': 2, 'к': 3, 'л': 4, 'м': 5, 'н': 6, 'о': 7, 'п': 8, 'р': 9,
                'с': 1, 'т': 2, 'у': 3, 'ф': 4, 'х': 5, 'ц': 6, 'ч': 7, 'ш': 8, 'щ': 9,
                'ъ': 1, 'ы': 2, 'ь': 3, 'э': 4, 'ю': 5, 'я': 6
            };
            
            let sum = 0;
            const lowerName = name.toLowerCase();
            
            for (let i = 0; i < lowerName.length; i++) {
                const char = lowerName[i];
                if (letterValues[char]) {
                    sum += letterValues[char];
                }
            }
            
            return reduceNumber(sum);
        }
        
        function calculateCompatibility(person1, person2, method) {
            let compatibilityScore = 0;
            let maxScore = 0;
            
            if (method === 'names' || method === 'combined') {
                if (person1.destiny && person2.destiny) {
                    const destinyDiff = Math.abs(person1.destiny - person2.destiny);
                    compatibilityScore += Math.max(0, 10 - destinyDiff) * 5;
                    maxScore += 50;
                }
            }
            
            if (method === 'birthdates' || method === 'combined') {
                if (person1.lifePath && person2.lifePath) {
                    const lifePathDiff = Math.abs(person1.lifePath - person2.lifePath);
                    compatibilityScore += Math.max(0, 10 - lifePathDiff) * 5;
                    maxScore += 50;
                }
            }
            
            let percentage = maxScore > 0 ? Math.round((compatibilityScore / maxScore) * 100) : 50;
            percentage = Math.max(20, Math.min(100, percentage));
            
            return generateCompatibilityResult(percentage, method);
        }
        
        function generateCompatibilityResult(percentage, method) {
            let description, strengths, weaknesses, advice;
            
            if (percentage >= 85) {
                description = "Исключительная совместимость! Ваши энергии идеально гармонируют друг с другом.";
                strengths = "Глубокая эмоциональная связь, полное взаимопонимание, общие цели и ценности.";
                weaknesses = "Возможна излишняя зависимость друг от друга, риск потери индивидуальности.";
                advice = "Сохраняйте личное пространство и интересы, поддерживайте индивидуальное развитие.";
            } else if (percentage >= 70) {
                description = "Очень хорошая совместимость. У вас прочная основа для гармоничных отношений.";
                strengths = "Сильная эмоциональная связь, общие интересы и ценности, способность конструктивно решать конфликты.";
                weaknesses = "Периодические недопонимания из-за разного темперамента.";
                advice = "Учитесь открытому и честному общению, находите компромиссы в спорных вопросах.";
            } else if (percentage >= 55) {
                description = "Умеренная совместимость. Отношения имеют потенциал, но потребуют работы и взаимных уступок.";
                strengths = "Взаимный интерес и притяжение, возможность роста через преодоление различий.";
                weaknesses = "Значительные различия в ценностях и жизненных приоритетах, частые недопонимания.";
                advice = "Фокусируйтесь на общих целях и интересах, развивайте терпимость к различиям.";
            } else if (percentage >= 40) {
                description = "Сложная совместимость. Отношения будут требовать значительных усилий от обоих партнеров.";
                strengths = "Возможность научиться терпимости и пониманию совершенно другого подхода к жизни.";
                weaknesses = "Постоянные конфликты и недопонимания, фундаментальные различия в ценностях и целях.";
                advice = "Трезво оценивайте, стоят ли отношения таких усилий, ищите точки соприкосновения.";
            } else {
                description = "Критически низкая совместимость. Отношения будут крайне сложными и энергозатратными.";
                strengths = "Возможность получить урок терпимости и понимания кардинально другого мировоззрения.";
                weaknesses = "Постоянные серьезные конфликты, полное непонимание мотивов и действий партнера.";
                advice = "Seriously consider whether this relationship is worth the emotional cost.";
            }
            
            let methodInfo = "";
            switch(method) {
                case 'names': methodInfo = " (расчет по именам)"; break;
                case 'birthdates': methodInfo = " (расчет по датам рождения)"; break;
                case 'combined': methodInfo = " (комбинированный расчет)"; break;
            }
            
            description += methodInfo;
            
            return { percentage, description, strengths, weaknesses, advice };
        }
        
        // Расчет совместимости
        document.getElementById('calculate-compatibility').addEventListener('click', function() {
            const person1Name = document.getElementById('person1-name').value;
            const person1Birthdate = new Date(document.getElementById('person1-birthdate').value);
            const person2Name = document.getElementById('person2-name').value;
            const person2Birthdate = new Date(document.getElementById('person2-birthdate').value);
            
            let isValid = false;
            
            switch(currentMethod) {
                case 'names':
                    isValid = person1Name && person1Name.trim() !== '' && 
                             person2Name && person2Name.trim() !== '';
                    break;
                case 'birthdates':
                    isValid = !isNaN(person1Birthdate.getTime()) && 
                             !isNaN(person2Birthdate.getTime());
                    break;
                case 'combined':
                    isValid = (person1Name && person1Name.trim() !== '' || !isNaN(person1Birthdate.getTime())) && 
                             (person2Name && person2Name.trim() !== '' || !isNaN(person2Birthdate.getTime()));
                    break;
            }
            
            if (!isValid) {
                alert('Пожалуйста, заполните необходимые поля в соответствии с выбранным методом расчета');
                return;
            }
            
            const person1Numbers = calculatePersonNumbers(person1Name, person1Birthdate, currentMethod);
            const person2Numbers = calculatePersonNumbers(person2Name, person2Birthdate, currentMethod);
            
            const compatibility = calculateCompatibility(person1Numbers, person2Numbers, currentMethod);
            
            document.getElementById('compatibility-percentage').textContent = `${compatibility.percentage}%`;
            document.getElementById('compatibility-fill').style.width = `${compatibility.percentage}%`;
            document.getElementById('compatibility-description').textContent = compatibility.description;
            document.getElementById('compatibility-strengths').textContent = compatibility.strengths;
            document.getElementById('compatibility-weaknesses').textContent = compatibility.weaknesses;
            document.getElementById('compatibility-advice').textContent = compatibility.advice;
            document.getElementById('compatibility-result').style.display = 'block';
        });
        
        // Функции для планирования
        function createDayElement(day, rating) {
            const dayElement = document.createElement('div');
            dayElement.className = `day-item ${rating === 'bad' ? 'dangerous' : ''}`;
            
            const weekdayNames = ['вс', 'пн', 'вт', 'ср', 'чт', 'пт', 'сб'];
            const weekday = weekdayNames[day.date.getDay()];
            
            const ratingClass = rating === 'good' ? 'rating-good' : 'rating-bad';
            const ratingText = rating === 'good' ? 'Благоприятный' : 'Опасный';
            
            dayElement.innerHTML = `
                <div>
                    <div class="day-date">${day.date.getDate()}.${day.date.getMonth() + 1}.${day.date.getFullYear()}</div>
                    <div class="day-weekday">${weekday}</div>
                </div>
                <div class="day-description">${day.description}</div>
                <div class="day-rating ${ratingClass}">${ratingText}</div>
            `;
            
            return dayElement;
        }
        
        function calculatePlanning(birthDate, eventType, period) {
            const today = new Date();
            let daysCount, periodText;
            
            switch(period) {
                case 'week': daysCount = 7; periodText = 'неделю'; break;
                case 'month': daysCount = 30; periodText = 'месяц'; break;
                case 'quarter': daysCount = 90; periodText = 'квартал'; break;
                case 'year': daysCount = 365; periodText = 'год'; break;
                default: daysCount = 30; periodText = 'месяц';
            }
            
            const day = birthDate.getDate();
            const month = birthDate.getMonth() + 1;
            const year = birthDate.getFullYear();
            const lifePathNumber = reduceNumber(reduceNumber(day) + reduceNumber(month) + reduceNumber(year));
            
            const favorableDays = [];
            const dangerousDays = [];
            
            for (let i = 1; i <= daysCount; i++) {
                const currentDate = new Date(today);
                currentDate.setDate(today.getDate() + i);
                
                const currentDay = currentDate.getDate();
                const currentMonth = currentDate.getMonth() + 1;
                const currentYear = currentDate.getFullYear();
                
                const dayNumber = reduceNumber(currentDay);
                const monthNumber = reduceNumber(currentMonth);
                const yearNumber = reduceNumber(currentYear);
                const dateNumber = reduceNumber(dayNumber + monthNumber + yearNumber);
                
                const diff = Math.abs(dateNumber - lifePathNumber);
                
                if (diff <= 1) {
                    favorableDays.push({
                        date: currentDate,
                        description: getFavorableDayDescription(eventType),
                        rating: 'good'
                    });
                } else if (diff >= 5) {
                    dangerousDays.push({
                        date: currentDate,
                        description: getDangerousDayDescription(eventType),
                        rating: 'bad'
                    });
                }
            }
            
            favorableDays.sort((a, b) => a.date - b.date);
            dangerousDays.sort((a, b) => a.date - b.date);
            
            const maxDisplayDays = 10;
            const displayFavorableDays = favorableDays.slice(0, maxDisplayDays);
            const displayDangerousDays = dangerousDays.slice(0, maxDisplayDays);
            
            const adviceText = {
                'business': `В ближайшую ${periodText} планируйте важные деловые встречи и проекты на благоприятные дни.`,
                'love': `Для романтических встреч и важных разговоров в отношениях выбирайте благоприятные дни.`,
                'health': `Благоприятные дни идеальны для начала диет, оздоровительных процедур и медицинских консультаций.`,
                'travel': `Планируйте начало путешествий на благоприятные дни для безопасной и приятной поездки.`,
                'creativity': `Творческие проекты лучше начинать в благоприятные дни.`,
                'family': `Семейные мероприятия и важные разговоры планируйте на благоприятные дни.`
            };
            
            return {
                favorableDays: displayFavorableDays,
                dangerousDays: displayDangerousDays,
                advice: adviceText[eventType] || `Используйте благоприятные дни для продуктивной деятельности.`
            };
        }
        
        function getFavorableDayDescription(eventType) {
            const descriptions = {
                'business': 'Идеальный день для карьерных прорывов и важных переговоров',
                'love': 'Прекрасный день для романтических признаний и укрепления отношений',
                'health': 'Отличный день для начала оздоровительных программ',
                'travel': 'Идеальный день для начала путешествий',
                'creativity': 'Вдохновенный день для творческих проектов',
                'family': 'Прекрасный день для семейных мероприятий'
            };
            return descriptions[eventType] || 'Благоприятный день для запланированных дел';
        }
        
        function getDangerousDayDescription(eventType) {
            const descriptions = {
                'business': 'Возможны финансовые потери и конфликты на работе',
                'love': 'Высок риск ссор и недопонимания в отношениях',
                'health': 'Возможны проблемы со здоровьем, будьте осторожны',
                'travel': 'Возможны задержки и непредвиденные ситуации в поездках',
                'creativity': 'Творческий кризис, отсутствие вдохновения',
                'family': 'Возможны конфликты и разногласия в семье'
            };
            return descriptions[eventType] || 'Неблагоприятный день, будьте осторожны';
        }
        
        // Расчет планирования
        document.getElementById('calculate-planning').addEventListener('click', function() {
            const birthDate = new Date(document.getElementById('user-birthdate-planning').value);
            const eventType = document.getElementById('event-type').value;
            const period = document.getElementById('planning-period').value;
            
            if (isNaN(birthDate.getTime())) {
                alert('Пожалуйста, введите корректную дату рождения');
                return;
            }
            
            const planningResult = calculatePlanning(birthDate, eventType, period);
            
            document.getElementById('favorable-days').innerHTML = '';
            document.getElementById('dangerous-days').innerHTML = '';
            
            if (planningResult.favorableDays.length > 0) {
                planningResult.favorableDays.forEach(day => {
                    const dayElement = createDayElement(day, 'good');
                    document.getElementById('favorable-days').appendChild(dayElement);
                });
            } else {
                document.getElementById('favorable-days').innerHTML = '<p>Благоприятные дни не найдены в выбранном периоде.</p>';
            }
            
            if (planningResult.dangerousDays.length > 0) {
                planningResult.dangerousDays.forEach(day => {
                    const dayElement = createDayElement(day, 'bad');
                    document.getElementById('dangerous-days').appendChild(dayElement);
                });
            } else {
                document.getElementById('dangerous-days').innerHTML = '<p>Опасные дни не найдены в выбранном периоде.</p>';
            }
            
            document.getElementById('planning-advice').textContent = planningResult.advice;
            document.getElementById('planning-result').style.display = 'block';
        });
        
        // Функции для нумерологического портрета
        function getPortraitDescription(number, type) {
            const descriptions = {
                'lifePath': {
                    1: "Число Жизненного Пути 1 означает, что вы - прирожденный лидер и новатор. Ваша основная задача - учиться самостоятельности и проявлять инициативу. Вы созданы, чтобы вести других, а не следовать за кем-то. Ваша энергия направлена на создание нового и преобразование окружающего мира.",
                    2: "Число Жизненного Пути 2 указывает на вашу дипломатичность и чувствительность. Вы - миротворец, который стремится к гармонии и сотрудничеству. Ваша сила в умении слушать, понимать и объединять людей. Вы прекрасный партнер и командный игрок.",
                    3: "Число Жизненного Пути 3 раскрывает вашу творческую природу и оптимизм. Вы созданы для самовыражения, общения и распространения радости. Ваш дар - вдохновлять других через искусство, слова и позитивную энергию.",
                    4: "Число Жизненного Пути 4 делает вас практичным строителем и организатором. Вы цените стабильность, надежность и порядок. Ваша миссия - создавать прочные основы и систематизировать процессы для долгосрочного успеха.",
                    5: "Число Жизненного Пути 5 наделяет вас свободолюбием и любознательностью. Вы - исследователь, который жаждет разнообразия и новых впечатлений. Ваш путь - постоянное движение, обучение и адаптация к изменениям.",
                    6: "Число Жизненного Пути 6 указывает на вашу ответственность и заботливость. Вы - воспитатель, который находит fulfillment в служении семье и обществу. Ваша сила в создании гармонии, уюта и поддержки для близких.",
                    7: "Число Жизненного Пути 7 раскрывает вашу аналитическую и духовную природу. Вы - мыслитель, который ищет глубину и истину. Ваш путь - самопознание, анализ и развитие интуиции.",
                    8: "Число Жизненного Пути 8 делает вас амбициозным организатором и руководителем. Вы созданы для достижения материального успеха и управления ресурсами. Ваша сила в практической реализации идей.",
                    9: "Число Жизненного Пути 9 указывает на ваш гуманизм и сострадание. Вы - филантроп, который служит человечеству и стремится к всеобщему благу. Ваша миссия - завершать циклы и нести любовь."
                },
                'destiny': {
                    1: "Число Судьбы 1 означает, что ваше предназначение связано с лидерством и созданием нового. Вы должны научиться самостоятельности и уверенности в себе. Ваши таланты лучше всего раскрываются в предпринимательстве, управлении и инновационных проектах.",
                    2: "Число Судьбы 2 указывает на ваше предназначение в создании гармонии и партнерства. Вы должны развивать дипломатичность и терпение. Ваши таланты раскрываются в медиации, консультировании и работе в команде.",
                    3: "Число Судьбы 3 раскрывает ваше творческое предназначение. Вы должны развивать самовыражение и коммуникативные навыки. Ваши таланты лежат в области искусства, преподавания и публичных выступлений.",
                    4: "Число Судьбы 4 означает практическое предназначение. Вы должны развивать дисциплину и организованность. Ваши таланты раскрываются в строительстве, инженерии и системном администрировании.",
                    5: "Число Судьбы 5 указывает на предназначение, связанное со свободой и изменениями. Вы должны развивать адаптивность и любознательность. Ваши таланты раскрываются в путешествиях, продажах и коммуникациях.",
                    6: "Число Судьбы 6 раскрывает ваше предназначение в служении и заботе. Вы должны развивать ответственность и эмпатию. Ваши таланты лежат в области медицины, преподавания и семейного консультирования.",
                    7: "Число Судьбы 7 означает духовное и аналитическое предназначение. Вы должны развивать интуицию и критическое мышление. Ваши таланты раскрываются в исследованиях, психологии и эзотерике.",
                    8: "Число Судьбы 8 указывает на материальное и организационное предназначение. Вы должны развивать деловую хватку и управленческие навыки. Ваши таланты лежат в области финансов, управления и предпринимательства.",
                    9: "Число Судьбы 9 раскрывает ваше гуманитарное предназначение. Вы должны развивать сострадание и терпимость. Ваши таланты раскрываются в благотворительности, искусстве и международных отношениях."
                },
                'soul': {
                    1: "Число Души 1 означает, что в глубине души вы стремитесь к независимости и самореализации. Ваши истинные желания связаны с лидерством, оригинальностью и достижением личных целей.",
                    2: "Число Души 2 указывает на вашу глубокую потребность в гармонии и партнерстве. Вы искренне желаете любви, поддержки и эмоциональной связи с другими людьми.",
                    3: "Число Души 3 раскрывает вашу внутреннюю потребность в творческом самовыражении и радости. Вы жаждете признания, восхищения и возможности делиться своим оптимизмом.",
                    4: "Число Души 4 означает, что в глубине души вы цените стабильность и безопасность. Ваши истинные желания связаны с созданием прочного фундамента и надежных отношений.",
                    5: "Число Души 5 указывает на вашу внутреннюю жажду свободы и приключений. Вы искренне желаете разнообразия, новых впечатлений и отсутствия ограничений.",
                    6: "Число Души 6 раскрывает вашу глубокую потребность в любви и семейном счастье. Вы жаждете гармонии в отношениях и возможности заботиться о близких.",
                    7: "Число Души 7 означает, что в глубине души вы стремитесь к мудрости и духовному росту. Ваши истинные желания связаны с пониманием тайн жизни и самопознанием.",
                    8: "Число Души 8 указывает на вашу внутреннюю потребность в признании и материальном успехе. Вы искренне желаете власти, влияния и финансовой стабильности.",
                    9: "Число Души 9 раскрывает вашу глубокую потребность в служении и всеобщей любви. Вы жаждете сделать мир лучше и помочь тем, кто в этом нуждается."
                },
                'appearance': {
                    1: "Число Внешнего Облика 1 создает впечатление уверенного, независимого и амбициозного человека. Окружающие видят в вас лидера, который знает, чего хочет, и умеет этого достигать.",
                    2: "Число Внешнего Облика 2 создает образ дипломатичного, дружелюбного и тактичного человека. Люди воспринимают вас как приятного собеседника и надежного партнера.",
                    3: "Число Внешнего Облика 3 формирует впечатление творческого, обаятельного и оптимистичного человека. Окружающие видят в вас источник вдохновения и позитивной энергии.",
                    4: "Число Внешнего Облика 4 создает образ надежного, практичного и ответственного человека. Люди воспринимают вас как стабильного и заслуживающего доверия партнера.",
                    5: "Число Внешнего Облика 5 формирует впечатление свободолюбивого, динамичного и адаптивного человека. Окружающие видят в вас интересного и непредсказуемого собеседника.",
                    6: "Число Внешнего Облика 6 создает образ заботливого, ответственного и гармоничного человека. Люди воспринимают вас как надежную опору и источник поддержки.",
                    7: "Число Внешнего Облика 7 формирует впечатление мудрого, сдержанного и глубокомыслящего человека. Окружающие видят в вас источник мудрости и интуитивных прозрений.",
                    8: "Число Внешнего Облика 8 создает образ успешного, авторитетного и эффективного человека. Люди воспринимают вас как лидера, способного достигать поставленных целей.",
                    9: "Число Внешнего Облика 9 формирует впечатление великодушного, альтруистичного и духовного человека. Окружающие видят в вас источник мудрости и бескорыстной помощи."
                },
                'birthday': {
                    1: "Число Дня Рождения 1 наделяет вас врожденными лидерскими качествами, инициативностью и оригинальностью. Вы рождены, чтобы быть первым и создавать новое.",
                    2: "Число Дня Рождения 2 дает вам природную дипломатичность, чувствительность и способность к сотрудничеству. Вы рождены для создания гармонии и партнерства.",
                    3: "Число Дня Рождения 3 наделяет вас врожденным творческим потенциалом, оптимизмом и коммуникабельностью. Вы рождены для самовыражения и распространения радости.",
                    4: "Число Дня Рождения 4 дает вам природную практичность, организованность и надежность. Вы рождены для создания стабильности и прочных основ.",
                    5: "Число Дня Рождения 5 наделяет вас врожденной адаптивностью, любознательностью и свободолюбием. Вы рождены для исследований и разнообразия.",
                    6: "Число Дня Рождения 6 дает вам природную ответственность, заботливость и гармоничность. Вы рождены для служения семье и создания уюта.",
                    7: "Число Дня Рождения 7 наделяет вас врожденной аналитичностью, интуицией и духовностью. Вы рождены для поиска истины и самопознания.",
                    8: "Число Дня Рождения 8 дает вам природную амбициозность, практичность и эффективность. Вы рождены для достижения успеха и управления ресурсами.",
                    9: "Число Дня Рождения 9 наделяет вас врожденным гуманизмом, состраданием и идеализмом. Вы рождены для служения человечеству и всеобщего блага."
                },
                'karmic': {
                    1: "Число Кармического Долга 1 указывает на необходимость развивать независимость и уверенность в себе. В прошлых жизнях вы могли быть слишком зависимы от других, и теперь должны научиться стоять на собственных ногах.",
                    2: "Число Кармического Долга 2 указывает на необходимость развивать сотрудничество и терпимость. В прошлом вы могли быть слишком эгоистичны, и теперь должны научиться учитывать интересы других.",
                    3: "Число Кармического Долга 3 указывает на необходимость развивать самовыражение и радость жизни. В прошлых жизнях вы могли подавлять свои творческие способности, и теперь должны научиться их раскрывать.",
                    4: "Число Кармического Долга 4 указывает на необходимость развивать дисциплину и практичность. В прошлом вы могли быть безответственны, и теперь должны научиться создавать прочные основы.",
                    5: "Число Кармического Долга 5 указывает на необходимость развивать свободу и ответственность. В прошлых жизнях вы могли быть либо слишком ограничены, либо слишком безответственны, и теперь должны найти баланс.",
                    6: "Число Кармического Долга 6 указывает на необходимость развивать любовь и заботу о других. В прошлом вы могли пренебрегать семейными обязанности, и теперь должны научиться бескорыстной любви.",
                    7: "Число Кармического Долга 7 указывает на необходимость развивать веру и духовность. В прошлых жизнях вы могли быть слишком материалистичны, и теперь должны открыться духовным истинам.",
                    8: "Число Кармического Долга 8 указывает на необходимость развивать изобилие и щедрость. В прошлом вы могли злоупотреблять властью или богатством, и теперь должны научиться использовать ресурсы мудро.",
                    9: "Число Кармического Долга 9 указывает на необходимость развивать служение и всепрощение. В прошлых жизнях вы могли быть эгоистичны, и теперь должны научиться бескорыстной помощи другим."
                }
            };
            
            return descriptions[type] && descriptions[type][number] 
                ? descriptions[type][number] 
                : "Описание для этого числа пока недоступно.";
        }
        
        // Расчет нумерологического портрета
        document.getElementById('calculate-portrait').addEventListener('click', function() {
            const fullName = document.getElementById('full-name').value;
            const birthDate = new Date(document.getElementById('portrait-birthdate').value);
            
            if (!fullName || isNaN(birthDate.getTime())) {
                alert('Пожалуйста, заполните все поля');
                return;
            }
            
            // Расчет всех чисел для портрета
            const day = birthDate.getDate();
            const month = birthDate.getMonth() + 1;
            const year = birthDate.getFullYear();
            
            const lifePathNumber = reduceNumber(reduceNumber(day) + reduceNumber(month) + reduceNumber(year));
            const destinyNumber = calculateDestinyNumber(fullName);
            const soulNumber = calculateSoulNumber(fullName);
            const appearanceNumber = calculateAppearanceNumber(fullName);
            const birthdayNumber = reduceNumber(day);
            const karmicNumber = reduceNumber(day + month);
            
            // Заполнение данных портрета
            document.getElementById('portrait-life-path').textContent = lifePathNumber;
            document.getElementById('portrait-life-path-desc').innerHTML = getPortraitDescription(lifePathNumber, 'lifePath');
            
            document.getElementById('portrait-destiny').textContent = destinyNumber;
            document.getElementById('portrait-destiny-desc').innerHTML = getPortraitDescription(destinyNumber, 'destiny');
            
            document.getElementById('portrait-soul').textContent = soulNumber;
            document.getElementById('portrait-soul-desc').innerHTML = getPortraitDescription(soulNumber, 'soul');
            
            document.getElementById('portrait-appearance').textContent = appearanceNumber;
            document.getElementById('portrait-appearance-desc').innerHTML = getPortraitDescription(appearanceNumber, 'appearance');
            
            document.getElementById('portrait-birthday').textContent = birthdayNumber;
            document.getElementById('portrait-birthday-desc').innerHTML = getPortraitDescription(birthdayNumber, 'birthday');
            
            document.getElementById('portrait-karmic').textContent = karmicNumber;
            document.getElementById('portrait-karmic-desc').innerHTML = getPortraitDescription(karmicNumber, 'karmic');
            
            // Общие рекомендации
            document.getElementById('portrait-strengths').textContent = generatePortraitStrengths(lifePathNumber, destinyNumber);
            document.getElementById('portrait-weaknesses').textContent = generatePortraitWeaknesses(lifePathNumber, karmicNumber);
            document.getElementById('portrait-advice').textContent = generatePortraitAdvice(lifePathNumber, destinyNumber, karmicNumber);
            
            document.getElementById('portrait-result').style.display = 'block';
        });
        
        function calculateSoulNumber(name) {
            const letterValues = {
                'а': 1, 'е': 6, 'ё': 7, 'и': 1, 'о': 7, 'у': 3, 'ы': 2, 'э': 4, 'ю': 5, 'я': 6
            };
            
            let sum = 0;
            const lowerName = name.toLowerCase();
            const vowels = 'аеёиоуыэюя';
            
            for (let i = 0; i < lowerName.length; i++) {
                const char = lowerName[i];
                if (vowels.includes(char) && letterValues[char]) {
                    sum += letterValues[char];
                }
            }
            
            return reduceNumber(sum);
        }
        
        function calculateAppearanceNumber(name) {
            const letterValues = {
                'б': 2, 'в': 3, 'г': 4, 'д': 5, 'ж': 8, 'з': 9, 'й': 2, 'к': 3, 'л': 4, 
                'м': 5, 'н': 6, 'п': 8, 'р': 9, 'с': 1, 'т': 2, 'ф': 4, 'х': 5, 'ц': 6, 
                'ч': 7, 'ш': 8, 'щ': 9, 'ъ': 1, 'ь': 3
            };
            
            let sum = 0;
            const lowerName = name.toLowerCase();
            const consonants = 'бвгджзйклмнпрстфхцчшщъь';
            
            for (let i = 0; i < lowerName.length; i++) {
                const char = lowerName[i];
                if (consonants.includes(char) && letterValues[char]) {
                    sum += letterValues[char];
                }
            }
            
            return reduceNumber(sum);
        }
        
        function generatePortraitStrengths(lifePath, destiny) {
            const strengths = {
                1: "Сильная воля, лидерские качества, инициативность, оригинальность мышления.",
                2: "Дипломатичность, эмпатия, терпение, способность к сотрудничеству.",
                3: "Творческие способности, коммуникабельность, оптимизм, артистизм.",
                4: "Практичность, надежность, организованность, трудолюбие.",
                5: "Адаптивность, любознательность, прогрессивность, находчивость.",
                6: "Ответственность, заботливость, гармоничность, преданность.",
                7: "Аналитический ум, интуиция, мудрость, духовность.",
                8: "Организаторские способности, амбициозность, практичность, эффективность.",
                9: "Гуманизм, сострадание, идеализм, творчество."
            };
            
            return `Ваши ключевые качества: ${strengths[lifePath] || "уникальное сочетание различных талантов"} ${strengths[destiny] ? "Дополнительные сильные стороны: " + strengths[destiny] : ""}`;
        }
        
        function generatePortraitWeaknesses(lifePath, karmic) {
            const weaknesses = {
                1: "Эгоизм, нетерпимость, импульсивность, склонность к доминированию.",
                2: "Нерешительность, зависимость от мнения других, чрезмерная чувствительность.",
                3: "Поверхностность, расточительность, драматизация, нетерпение.",
                4: "Упрямство, консерватизм, излишняя практичность, сопротивление изменениям.",
                5: "Безответственность, непоследовательность, склонность к излишествам.",
                6: "Самопожертвование, чрезмерная опека, собственничество, критичность.",
                7: "Цинизм, отстраненность, подозрительность, перфекционизм.",
                8: "Материализм, властность, жесткость, трудоголизм.",
                9: "Сентиментальность, жертвенность, непрактичность, обидчивость."
            };
            
            return `Зоны развития: ${weaknesses[lifePath] || "работа над балансом различных качеств"} ${weaknesses[karmic] ? "Кармические вызовы: " + weaknesses[karmic] : ""}`;
        }
        
        function generatePortraitAdvice(lifePath, destiny, karmic) {
            const advice = {
                1: "Развивайте терпимость к другим мнениям, учитесь сотрудничать, не подавляйте окружающих своей силой.",
                2: "Учитесь принимать решения самостоятельно, развивайте уверенность в себе, не бойтесь конфликтов.",
                3: "Сосредоточьтесь на глубине, а не на количестве проектов, развивайте дисциплину, избегайте поверхностности.",
                4: "Будьте более гибкими, открывайтесь новому, не зацикливайтесь на рутине, развивайте творческое начало.",
                5: "Учитесь завершать начатое, развивайте ответственность, найдите баланс между свободой и обязательствами.",
                6: "Не забывайте о собственных потребностях, устанавливайте здоровые границы, избегайте гиперопеки.",
                7: "Больше доверяйте людям, развивайте эмоциональный интеллект, не уходите в чрезмерную изоляцию.",
                8: "Развивайте духовность, не ставьте материальные цели выше человеческих отношений, учитесь отдыхать.",
                9: "Будьте более практичными, учитесь говорить 'нет', не позволяйте другим использовать вашу доброту."
            };
            
            return `Рекомендации для гармоничной жизни: ${advice[lifePath] || "стремитесь к балансу во всех сферах жизни"} ${advice[karmic] ? "Особое внимание уделите: " + advice[karmic] : ""}`;
        }
        
        // Остальные калькуляторы (матрица) остаются без изменений
        document.getElementById('calculate-matrix').addEventListener('click', function() {
            const birthDate = new Date(document.getElementById('matrix-birthdate').value);
            if (isNaN(birthDate.getTime())) {
                alert('Пожалуйста, введите корректную дату рождения');
                return;
            }
            
            // Простая реализация матрицы
            const day = birthDate.getDate();
            const month = birthDate.getMonth() + 1;
            const year = birthDate.getFullYear();
            
            const firstNumber = reduceNumber(day);
            const secondNumber = reduceNumber(month);
            const thirdNumber = reduceNumber(year);
            const fourthNumber = reduceNumber(firstNumber + secondNumber + thirdNumber);
            
            let gridHTML = '';
            const numbers = [firstNumber, secondNumber, thirdNumber, fourthNumber];
            
            for (let i = 1; i <= 9; i++) {
                const isActive = numbers.includes(i);
                gridHTML += `<div class="matrix-cell ${isActive ? 'active' : ''}">${i}</div>`;
            }
            
            document.getElementById('matrix-container').innerHTML = gridHTML;
            document.getElementById('matrix-description').innerHTML = `
                <p>Ваша матрица содержит числа: <strong>${firstNumber}</strong> (день), 
                <strong>${secondNumber}</strong> (месяц), <strong>${thirdNumber}</strong> (год) и 
                <strong>${fourthNumber}</strong> (сумма).</p>`;
            
            document.getElementById('matrix-strengths').textContent = "Сильный аналитический ум, развитая интуиция, практичность.";
            document.getElementById('matrix-weaknesses').textContent = "Склонность к перфекционизму, трудности в принятии решений.";
            document.getElementById('matrix-advice').textContent = "Развивайте эмоциональный интеллект, учитесь делегировать задачи.";
            document.getElementById('matrix-result').style.display = 'block';
        });
    </script>
</body>
</html>
