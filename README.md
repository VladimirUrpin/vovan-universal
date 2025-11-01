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
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
            margin-top: 1.5rem;
        }
        
        .portrait-card {
            background: white;
            border-radius: 8px;
            padding: 1.5rem;
            box-shadow: 0 3px 10px rgba(0,0,0,0.08);
        }
        
        .portrait-card h4 {
            color: var(--primary);
            margin-bottom: 0.8rem;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .portrait-number {
            font-size: 1.8rem;
            font-weight: bold;
            color: var(--accent);
            text-align: center;
            margin: 0.5rem 0;
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
                    <p>Определите благоприятные дни для важных событий</p>
                    
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
                        <h3>Благоприятные дни для вашего события</h3>
                        <div id="favorable-days"></div>
                        
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
                    <p>Полный анализ личности по Ф.И.О. с расчетом всех основных чисел</p>
                    
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
                        <div class="portrait-grid">
                            <div class="portrait-card">
                                <h4><i class="fas fa-user"></i> Число Жизненного Пути</h4>
                                <div class="portrait-number" id="portrait-life-path"></div>
                                <p id="portrait-life-path-desc"></p>
                            </div>
                            
                            <div class="portrait-card">
                                <h4><i class="fas fa-star"></i> Число Судьбы</h4>
                                <div class="portrait-number" id="portrait-destiny"></div>
                                <p id="portrait-destiny-desc"></p>
                            </div>
                            
                            <div class="portrait-card">
                                <h4><i class="fas fa-heart"></i> Число Души</h4>
                                <div class="portrait-number" id="portrait-soul"></div>
                                <p id="portrait-soul-desc"></p>
                            </div>
                            
                            <div class="portrait-card">
                                <h4><i class="fas fa-eye"></i> Число Внешнего Облика</h4>
                                <div class="portrait-number" id="portrait-appearance"></div>
                                <p id="portrait-appearance-desc"></p>
                            </div>
                            
                            <div class="portrait-card">
                                <h4><i class="fas fa-birthday-cake"></i> Число Дня Рождения</h4>
                                <div class="portrait-number" id="portrait-birthday"></div>
                                <p id="portrait-birthday-desc"></p>
                            </div>
                            
                            <div class="portrait-card">
                                <h4><i class="fas fa-balance-scale"></i> Число Кармического Долга</h4>
                                <div class="portrait-number" id="portrait-karmic"></div>
                                <p id="portrait-karmic-desc"></p>
                            </div>
                        </div>
                        
                        <div class="strengths">
                            <h4><i class="fas fa-star"></i> Ваши ключевые качества</h4>
                            <p id="portrait-strengths"></p>
                        </div>
                        
                        <div class="weaknesses">
                            <h4><i class="fas fa-exclamation-triangle"></i> Зоны развития</h4>
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
            
            // Простой расчет числа жизненного пути
            let lifePathNumber = reduceNumber(day) + reduceNumber(month) + reduceNumber(year);
            lifePathNumber = reduceNumber(lifePathNumber);
            
            document.getElementById('life-path-number').textContent = lifePathNumber;
            document.getElementById('life-path-description').textContent = getLifePathDescription(lifePathNumber);
            document.getElementById('life-path-strengths').textContent = getLifePathStrengths(lifePathNumber);
            document.getElementById('life-path-weaknesses').textContent = getLifePathWeaknesses(lifePathNumber);
            document.getElementById('life-path-advice').textContent = getLifePathAdvice(lifePathNumber);
            document.getElementById('life-path-result').style.display = 'block';
        });
        
        // Расчет совместимости - ПЕРЕПИСАННАЯ ФУНКЦИЯ
        document.getElementById('calculate-compatibility').addEventListener('click', function() {
            const person1Name = document.getElementById('person1-name').value;
            const person1Birthdate = new Date(document.getElementById('person1-birthdate').value);
            const person2Name = document.getElementById('person2-name').value;
            const person2Birthdate = new Date(document.getElementById('person2-birthdate').value);
            
            // Проверка введенных данных в зависимости от выбранного метода
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
            
            // Расчет чисел для обоих людей
            const person1Numbers = calculatePersonNumbers(person1Name, person1Birthdate, currentMethod);
            const person2Numbers = calculatePersonNumbers(person2Name, person2Birthdate, currentMethod);
            
            // Расчет совместимости
            const compatibility = calculateCompatibility(person1Numbers, person2Numbers, currentMethod);
            
            document.getElementById('compatibility-percentage').textContent = `${compatibility.percentage}%`;
            document.getElementById('compatibility-fill').style.width = `${compatibility.percentage}%`;
            document.getElementById('compatibility-description').textContent = compatibility.description;
            document.getElementById('compatibility-strengths').textContent = compatibility.strengths;
            document.getElementById('compatibility-weaknesses').textContent = compatibility.weaknesses;
            document.getElementById('compatibility-advice').textContent = compatibility.advice;
            document.getElementById('compatibility-result').style.display = 'block';
        });
        
        // Расчет планирования
        document.getElementById('calculate-planning').addEventListener('click', function() {
            const birthDate = new Date(document.getElementById('user-birthdate-planning').value);
            const eventType = document.getElementById('event-type').value;
            const period = document.getElementById('planning-period').value;
            
            if (isNaN(birthDate.getTime())) {
                alert('Пожалуйста, введите корректную дату рождения');
                return;
            }
            
            const favorableDays = calculateFavorableDays(birthDate, eventType, period);
            document.getElementById('favorable-days').innerHTML = favorableDays.days;
            document.getElementById('planning-advice').textContent = favorableDays.advice;
            document.getElementById('planning-result').style.display = 'block';
        });
        
        // Расчет матрицы судьбы
        document.getElementById('calculate-matrix').addEventListener('click', function() {
            const birthDate = new Date(document.getElementById('matrix-birthdate').value);
            if (isNaN(birthDate.getTime())) {
                alert('Пожалуйста, введите корректную дату рождения');
                return;
            }
            
            const matrix = calculateMatrix(birthDate);
            document.getElementById('matrix-container').innerHTML = matrix.grid;
            document.getElementById('matrix-description').innerHTML = matrix.description;
            document.getElementById('matrix-strengths').textContent = matrix.strengths;
            document.getElementById('matrix-weaknesses').textContent = matrix.weaknesses;
            document.getElementById('matrix-advice').textContent = matrix.advice;
            document.getElementById('matrix-result').style.display = 'block';
        });
        
        // Расчет нумерологического портрета
        document.getElementById('calculate-portrait').addEventListener('click', function() {
            const fullName = document.getElementById('full-name').value;
            const birthDate = new Date(document.getElementById('portrait-birthdate').value);
            
            if (!fullName || isNaN(birthDate.getTime())) {
                alert('Пожалуйста, заполните все поля');
                return;
            }
            
            const portrait = calculateNumerologyPortrait(fullName, birthDate);
            
            // Заполняем данные портрета
            document.getElementById('portrait-life-path').textContent = portrait.lifePath.number;
            document.getElementById('portrait-life-path-desc').textContent = portrait.lifePath.description;
            
            document.getElementById('portrait-destiny').textContent = portrait.destiny.number;
            document.getElementById('portrait-destiny-desc').textContent = portrait.destiny.description;
            
            document.getElementById('portrait-soul').textContent = portrait.soul.number;
            document.getElementById('portrait-soul-desc').textContent = portrait.soul.description;
            
            document.getElementById('portrait-appearance').textContent = portrait.appearance.number;
            document.getElementById('portrait-appearance-desc').textContent = portrait.appearance.description;
            
            document.getElementById('portrait-birthday').textContent = portrait.birthday.number;
            document.getElementById('portrait-birthday-desc').textContent = portrait.birthday.description;
            
            document.getElementById('portrait-karmic').textContent = portrait.karmic.number;
            document.getElementById('portrait-karmic-desc').textContent = portrait.karmic.description;
            
            document.getElementById('portrait-strengths').textContent = portrait.strengths;
            document.getElementById('portrait-weaknesses').textContent = portrait.weaknesses;
            document.getElementById('portrait-advice').textContent = portrait.advice;
            
            document.getElementById('portrait-result').style.display = 'block';
        });
        
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
        
        // ПЕРЕПИСАННАЯ ФУНКЦИЯ РАСЧЕТА ЧИСЕЛ ЧЕЛОВЕКА
        function calculatePersonNumbers(name, birthDate, method) {
            const numbers = {};
            
            // Расчет в зависимости от выбранного метода
            if (method === 'names' || method === 'combined') {
                if (name && name.trim() !== '') {
                    numbers.destiny = calculateDestinyNumber(name);
                    numbers.soul = calculateSoulNumber(name);
                    numbers.appearance = calculateAppearanceNumber(name);
                }
            }
            
            if (method === 'birthdates' || method === 'combined') {
                if (!isNaN(birthDate.getTime())) {
                    numbers.lifePath = calculateLifePathNumber(birthDate);
                    numbers.birthday = calculateBirthdayNumber(birthDate);
                    numbers.karmic = calculateKarmicNumber(birthDate);
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
        
        function calculateBirthdayNumber(birthDate) {
            return reduceNumber(birthDate.getDate());
        }
        
        function calculateKarmicNumber(birthDate) {
            const day = birthDate.getDate();
            const month = birthDate.getMonth() + 1;
            return reduceNumber(day + month);
        }
        
        // ПЕРЕПИСАННАЯ ФУНКЦИЯ РАСЧЕТА СОВМЕСТИМОСТИ
        function calculateCompatibility(person1, person2, method) {
            let compatibilityScore = 0;
            let maxScore = 0;
            
            // Расчет совместимости в зависимости от выбранного метода
            if (method === 'names' || method === 'combined') {
                if (person1.destiny && person2.destiny) {
                    const destinyDiff = Math.abs(person1.destiny - person2.destiny);
                    compatibilityScore += Math.max(0, 10 - destinyDiff) * 3;
                    maxScore += 30;
                }
                
                if (person1.soul && person2.soul) {
                    const soulDiff = Math.abs(person1.soul - person2.soul);
                    compatibilityScore += Math.max(0, 10 - soulDiff) * 2;
                    maxScore += 20;
                }
                
                if (person1.appearance && person2.appearance) {
                    const appearanceDiff = Math.abs(person1.appearance - person2.appearance);
                    compatibilityScore += Math.max(0, 10 - appearanceDiff) * 2;
                    maxScore += 20;
                }
            }
            
            if (method === 'birthdates' || method === 'combined') {
                if (person1.lifePath && person2.lifePath) {
                    const lifePathDiff = Math.abs(person1.lifePath - person2.lifePath);
                    compatibilityScore += Math.max(0, 10 - lifePathDiff) * 4;
                    maxScore += 40;
                }
                
                if (person1.birthday && person2.birthday) {
                    const birthdayDiff = Math.abs(person1.birthday - person2.birthday);
                    compatibilityScore += Math.max(0, 10 - birthdayDiff) * 1;
                    maxScore += 10;
                }
                
                if (person1.karmic && person2.karmic) {
                    const karmicDiff = Math.abs(person1.karmic - person2.karmic);
                    compatibilityScore += Math.max(0, 10 - karmicDiff) * 1;
                    maxScore += 10;
                }
            }
            
            // Расчет процента совместимости
            let percentage = maxScore > 0 ? Math.round((compatibilityScore / maxScore) * 100) : 50;
            
            // Ограничиваем процент от 20 до 100
            percentage = Math.max(20, Math.min(100, percentage));
            
            // Генерация описания результатов
            return generateCompatibilityResult(percentage, method);
        }
        
        function generateCompatibilityResult(percentage, method) {
            let description, strengths, weaknesses, advice;
            
            if (percentage >= 85) {
                description = "Исключительная совместимость! Ваши энергии идеально гармонируют друг с другом. Это редкое соединение, где партнеры взаимно дополняют и усиливают лучшие качества друг друга.";
                strengths = "Глубокая эмоциональная связь, полное взаимопонимание, общие цели и ценности, способность поддерживать друг друга в трудные моменты.";
                weaknesses = "Возможна излишняя зависимость друг от друга, риск потери индивидуальности в длительных отношениях.";
                advice = "Сохраняйте личное пространство и интересы, поддерживайте индивидуальное развитие.";
            } else if (percentage >= 70) {
                description = "Очень хорошая совместимость. У вас прочная основа для гармоничных отношений. Партнеры хорошо понимают друг друга и имеют схожие жизненные ориентиры.";
                strengths = "Сильная эмоциональная связь, общие интересы и ценности, способность конструктивно решать конфликты, взаимная поддержка.";
                weaknesses = "Периодические недопонимания из-за разного темперамента, возможны разногласия в вопросах быта и финансов.";
                advice = "Учитесь открытому и честному общению, находите компромиссы в спорных вопросах.";
            } else if (percentage >= 55) {
                description = "Умеренная совместимость. Отношения имеют потенциал, но потребуют работы и взаимных уступок. Партнеры могут многому научиться друг у друга.";
                strengths = "Взаимный интерес и притяжение, возможность роста через преодоление различий, взаимное обучение.";
                weaknesses = "Значительные различия в ценностях и жизненных приоритетах, частые недопонимания, разные темпы жизни.";
                advice = "Фокусируйтесь на общих целях и интересах, развивайте терпимость к различиям.";
            } else if (percentage >= 40) {
                description = "Сложная совместимость. Отношения будут требовать значительных усилий от обоих партнеров. Различия в основных жизненных подходах могут создавать постоянное напряжение.";
                strengths = "Возможность научиться терпимости и пониманию совершенно другого подхода к жизни, развитие гибкости.";
                weaknesses = "Постоянные конфликты и недопонимания, фундаментальные различия в ценностях и целях.";
                advice = "Трезво оценивайте, стоят ли отношения таких усилий, ищите точки соприкосновения.";
            } else {
                description = "Критически низкая совместимость. Отношения будут крайне сложными и энергозатратными. Фундаментальные различия в подходах к жизни могут сделать совместное существование практически невозможным.";
                strengths = "Возможность получить урок терпимости и понимания кардинально другого мировоззрения.";
                weaknesses = "Постоянные серьезные конфликты, полное непонимание мотивов и действий партнера.";
                advice = "Seriously consider whether this relationship is worth the emotional cost.";
            }
            
            // Добавляем информацию о методе расчета
            let methodInfo = "";
            switch(method) {
                case 'names':
                    methodInfo = " (расчет по именам)";
                    break;
                case 'birthdates':
                    methodInfo = " (расчет по датам рождения)";
                    break;
                case 'combined':
                    methodInfo = " (комбинированный расчет)";
                    break;
            }
            
            description += methodInfo;
            
            return {
                percentage,
                description,
                strengths,
                weaknesses,
                advice
            };
        }
        
        // Остальные функции остаются без изменений
        // ... (getLifePathDescription, getLifePathStrengths, getLifePathWeaknesses, getLifePathAdvice,
        // calculateFavorableDays, calculateMatrix, calculateNumerologyPortrait и другие вспомогательные функции)
        
        // Для краткости оставлю только сигнатуры этих функций, так как они не изменились
        function getLifePathDescription(number) { /* ... */ }
        function getLifePathStrengths(number) { /* ... */ }
        function getLifePathWeaknesses(number) { /* ... */ }
        function getLifePathAdvice(number) { /* ... */ }
        function calculateFavorableDays(birthDate, eventType, period) { /* ... */ }
        function calculateMatrix(birthDate) { /* ... */ }
        function calculateNumerologyPortrait(fullName, birthDate) { /* ... */ }
        // ... и другие функции
        
    </script>
</body>
</html>
