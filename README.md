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
                    <p>Введите данные двух людей для анализа их совместимости по датам рождения и именам</p>
                    
                    <div class="form-group">
                        <label for="person1-name">Имя первого человека</label>
                        <input type="text" id="person1-name" placeholder="Введите полное имя">
                    </div>
                    
                    <div class="form-group">
                        <label for="person1-birthdate">Дата рождения первого человека</label>
                        <input type="date" id="person1-birthdate">
                    </div>
                    
                    <div class="form-group">
                        <label for="person2-name">Имя второго человека</label>
                        <input type="text" id="person2-name" placeholder="Введите полное имя">
                    </div>
                    
                    <div class="form-group">
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
        
        // Расчет совместимости
        document.getElementById('calculate-compatibility').addEventListener('click', function() {
            const person1Name = document.getElementById('person1-name').value;
            const person1Birthdate = new Date(document.getElementById('person1-birthdate').value);
            const person2Name = document.getElementById('person2-name').value;
            const person2Birthdate = new Date(document.getElementById('person2-birthdate').value);
            
            if ((!person1Name && isNaN(person1Birthdate.getTime())) || (!person2Name && isNaN(person2Birthdate.getTime()))) {
                alert('Пожалуйста, заполните хотя бы имена или даты рождения для обоих людей');
                return;
            }
            
            // Расчет чисел для обоих людей
            const person1Numbers = calculatePersonNumbers(person1Name, person1Birthdate);
            const person2Numbers = calculatePersonNumbers(person2Name, person2Birthdate);
            
            // Расчет совместимости
            const compatibility = calculateCompatibility(person1Numbers, person2Numbers);
            
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
        
        function getLifePathDescription(number) {
            const descriptions = {
                1: "Вы - прирожденный лидер, независимый и амбициозный. Ваше предназначение - вести других, проявлять инициативу и создавать новое. Вы обладаете сильной волей и оригинальным мышлением, способны вдохновлять людей на свершения. Ваша энергия направлена на достижение целей и преобразование окружающего мира.",
                2: "Вы - дипломат и миротворец, чувствительный и интуитивный. Ваша роль - создавать гармонию, сотрудничать и поддерживать баланс в отношениях. Вы умеете слышать других и находить компромиссы. Ваша сила в способности объединять людей и создавать прочные связи, основанные на взаимном уважении и понимании.",
                3: "Вы - творческая личность, выразительный и оптимистичный. Ваше призвание - вдохновлять других, выражать красоту и радость через искусство, общение и самовыражение. Вы обладаете даром слова и художественным восприятием мира. Ваша энергия привлекает людей и создает атмосферу праздника.",
                4: "Вы - практичный строитель, надежный и трудолюбивый. Ваша миссия - создавать прочный фундамент, систематизировать и организовывать. Вы цените стабильность и практичность. Ваша сила в умении превращать идеи в реальные проекты и доводить начатое до конца.",
                5: "Вы - искатель свободы, адаптивный и любознательный. Ваш путь - исследовать мир, наслаждаться разнообразием и передавать свой опыт другим. Вы ненавидите рутину и ограничения. Ваша энергия направлена на поиск новых возможностей и расширение горизонтов.",
                6: "Вы - воспитатель, ответственный и заботливый. Ваше предназначение - служить семье и обществу, создавать уют и гармонию в отношениях. Вы природный целитель и советчик. Ваша сила в способности создавать безопасное пространство для роста и развития близких.",
                7: "Вы - мыслитель, аналитичный и духовный. Ваша задача - искать истину, развивать интуицию и делиться мудростью. Вы стремитесь к глубине понимания мира и себя. Ваша энергия направлена на исследование тайн бытия и поиск ответов на фундаментальные вопросы.",
                8: "Вы - организатор, амбициозный и эффективный. Ваша миссия - достигать материального успеха, управлять ресурсами и воплощать идеи в реальность. Вы обладаете деловой хваткой. Ваша сила в умении видеть возможности для роста и превращать их в конкретные результаты.",
                9: "Вы - гуманист, сострадательный и идеалистичный. Ваше предназначение - служить человечеству, завершать циклы и нести любовь. Вы стремитесь к всеобщему благу. Ваша энергия направлена на помощь другим и создание более справедливого мира.",
                11: "Вы - просветленный, интуитивный и вдохновляющий. Ваша миссия - нести духовное озарение, вдохновлять других и служить высшим идеалам. Вы - мост между материальным и духовным. Ваша сила в способности видеть глубинные связи и передавать высшие истины.",
                22: "Вы - мастер-строитель, практичный мечтатель. Ваша задача - реализовывать грандиозные планы на благо человечества, сочетая духовное видение с практической реализацией. Вы способны превращать утопические идеи в работающие системы.",
                33: "Вы - мастер-учитель, сострадательный и вдохновляющий. Ваше предназначение - служить через любовь, исцелять и возвышать человеческое сознание. Вы - пример безусловной любви. Ваша сила в способности трансформировать боль в мудрость."
            };
            
            return descriptions[number] || "Описание для этого числа пока недоступно.";
        }
        
        function getLifePathStrengths(number) {
            const strengths = {
                1: "Лидерские качества, независимость, инициативность, оригинальность, решительность, амбициозность, смелость, новаторство, уверенность в себе, способность начинать новые проекты.",
                2: "Дипломатичность, чувствительность, интуиция, сотрудничество, терпение, тактичность, адаптивность, способность к компромиссу, эмпатия, умение слушать.",
                3: "Креативность, оптимизм, коммуникабельность, артистизм, чувство юмора, энтузиазм, обаяние, выразительность, многогранность, вдохновенность.",
                4: "Надежность, практичность, трудолюбие, организованность, дисциплина, стабильность, терпение, методичность, основательность, честность.",
                5: "Адаптивность, любознательность, прогрессивность, многосторонность, свобода, находчивость, общительность, предприимчивость, гибкость, жажда приключений.",
                6: "Ответственность, заботливость, гармоничность, служение, сострадание, надежность, художественный вкус, способность создавать уют, преданность, гуманизм.",
                7: "Аналитический ум, интуиция, мудрость, духовность, перфекционизм, проницательность, наблюдательность, глубина, самодостаточность, поиск истины.",
                8: "Организаторские способности, амбициозность, практичность, эффективность, сила воли, решимость, деловая хватка, управленческие навыки, материальная успешность.",
                9: "Гуманизм, сострадание, идеализм, терпимость, творчество, щедрость, мудрость, всепрощение, художественные способности, филантропия.",
                11: "Интуиция, вдохновение, идеализм, визионерство, чувствительность, духовность, просветленность, идеализм, способность к трансформации, мечтательность.",
                22: "Практическая мудрость, глобальное мышление, строительство, организация, мечтательность, реализация, управление масштабными проектами, преобразование идей в реальность.",
                33: "Безусловная любовь, сострадание, исцеление, вдохновение, учительство, самопожертвование, духовное руководство, способность возвышать других, трансцендентность."
            };
            
            return strengths[number] || "Сильные стороны для этого числа пока не определены.";
        }
        
        function getLifePathWeaknesses(number) {
            const weaknesses = {
                1: "Эгоизм, агрессивность, нетерпимость, доминирование, импульсивность, упрямство, склонность к манипуляции, нетерпеливость, чрезмерная независимость, склонность к риску.",
                2: "Чрезмерная чувствительность, нерешительность, зависимость от мнения других, пассивность, мнительность, обидчивость, склонность к жертвенности, неуверенность в себе.",
                3: "Поверхностность, расточительность, драматизация, нетерпение, разбросанность, болтливость, тщеславие, неорганизованность, склонность к сплетням.",
                4: "Упрямство, консерватизм, излишняя практичность, медлительность, ригидность, скупость, педантичность, сопротивление изменениям, чрезмерный контроль.",
                5: "Безответственность, непоследовательность, нетерпение, импульсивность, склонность к излишествам, непостоянство, склонность к зависимостям, непредсказуемость.",
                6: "Самопожертвование, чрезмерная опека, собственничество, критичность, мнительность, ревность, склонность к мученичеству, вмешательство в чужие дела.",
                7: "Цинизм, отстраненность, подозрительность, перфекционизм, скрытность, пессимизм, чрезмерная аналитика, социальная изоляция, высокомерие.",
                8: "Материализм, властность, жесткость, трудоголизм, нетерпимость к слабостям, жажда контроля, алчность, манипулятивность, пренебрежение чувствами других.",
                9: "Сентиментальность, жертвенность, непрактичность, мечтательность, обидчивость, склонность к депрессии, разочарованность, наивность, непоследовательность.",
                11: "Нервозность, мечтательность без действия, сверхчувствительность, непрактичность, эмоциональная нестабильность, склонность к иллюзиям, перфекционизм.",
                22: "Давление ответственности, перфекционизм, трудоголизм, подавление эмоций, чрезмерный контроль, маниакальность, непосильные обязательства, выгорание.",
                33: "Чрезмерная жертвенность, эмоциональное выгорание, непрактичность, наивность, мученичество, потеря себя в служении другим, эмоциональная зависимость."
            };
            
            return weaknesses[number] || "Слабые стороны для этого числа пока не определены.";
        }
        
        function getLifePathAdvice(number) {
            const advice = {
                1: "Развивайте терпимость к другим мнениям, учитесь сотрудничать, не подавляйте окружающих своей силой. Находите баланс между лидерством и умением слушать. Развивайте эмпатию и учитесь ценить вклад других людей.",
                2: "Учитесь принимать решения самостоятельно, развивайте уверенность в себе, не бойтесь конфликтов. Находите баланс между заботой о других и заботой о себе. Развивайте assertiveness - умение отстаивать свои границы.",
                3: "Сосредоточьтесь на глубине, а не на количестве проектов, развивайте дисциплину, избегайте поверхностности. Научитесь доводить начатое до конца. Развивайте финансовую грамотность и практические навыки.",
                4: "Будьте более гибкими, открывайтесь новому, не зацикливайтесь на рутине, развивайте творческое начало. Учитесь импровизировать и принимать изменения. Развивайте эмоциональный интеллект.",
                5: "Учитесь завершать начатое, развивайте ответственность, найдите баланс между свободой и обязательствами. Развивайте постоянство в отношениях и проектах. Учитесь концентрации и глубине.",
                6: "Не забывайте о собственных потребностях, устанавливайте здоровые границы, избегайте гиперопеки. Учитесь говорить 'нет' когда это необходимо. Развивайте собственную идентичность вне служения другим.",
                7: "Больше доверяйте людям, развивайте эмоциональный интеллект, не уходите в чрезмерную изоляцию. Находите баланс между анализом и действием. Развивайте практические навыки общения.",
                8: "Развивайте духовность, не ставьте материальные цели выше человеческих отношений, учитесь отдыхать. Находите баланс между работой и личной жизнью. Развивайте щедрость и альтруизм.",
                9: "Будьте более практичными, учитесь говорить 'нет', не позволяйте другим использовать вашу доброту. Развивайте здоровый эгоизм и самозащиту. Учитесь отстаивать свои интересы.",
                11: "Заземляйте свои идеи, развивайте практические навыки, не пренебрегайте материальным миром. Находите баланс между духовным и материальным. Учитесь воплощать идеи в реальность.",
                22: "Уделяйте внимание личной жизни, не забывайте об отдыхе, развивайте эмоциональную сферу. Находите баланс между глобальными проектами и простыми радостями. Учитесь делегировать задачи.",
                33: "Заботьтесь о себе, устанавливайте здоровые границы, не забывайте о практических аспектах жизни. Находите баланс между служением другим и заботой о себе. Развивайте практическую мудрость."
            };
            
            return advice[number] || "Советы по развитию для этого числа пока не доступны.";
        }
        
        function calculatePersonNumbers(name, birthDate) {
            const numbers = {};
            
            // Расчет числа жизненного пути
            if (!isNaN(birthDate.getTime())) {
                const day = birthDate.getDate();
                const month = birthDate.getMonth() + 1;
                const year = birthDate.getFullYear();
                
                numbers.lifePath = reduceNumber(day) + reduceNumber(month) + reduceNumber(year);
                numbers.lifePath = reduceNumber(numbers.lifePath);
            }
            
            // Расчет числа судьбы
            if (name && name.trim() !== '') {
                numbers.destiny = calculateDestinyNumber(name);
            }
            
            return numbers;
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
        
        function calculateCompatibility(person1, person2) {
            // Расчет совместимости на основе чисел жизненного пути и судьбы
            let compatibilityScore = 0;
            let factors = 0;
            
            if (person1.lifePath && person2.lifePath) {
                const lifePathDiff = Math.abs(person1.lifePath - person2.lifePath);
                compatibilityScore += (10 - lifePathDiff) * 4;
                factors++;
            }
            
            if (person1.destiny && person2.destiny) {
                const destinyDiff = Math.abs(person1.destiny - person2.destiny);
                compatibilityScore += (10 - destinyDiff) * 3;
                factors++;
            }
            
            // Если есть оба фактора, нормализуем оценку
            let percentage = factors > 0 ? Math.round(compatibilityScore / (factors * 10) * 100) : 50;
            percentage = Math.max(20, Math.min(100, percentage));
            
            let description, strengths, weaknesses, advice;
            
            if (percentage >= 85) {
                description = "Исключительная совместимость! Ваши энергии идеально гармонируют друг с другом. Это редкое соединение, где партнеры взаимно дополняют и усиливают лучшие качества друг друга. Отношения основаны на глубоком понимании, взаимном уважении и общих жизненных ценностях.";
                strengths = "Глубокая эмоциональная связь, полное взаимопонимание, общие цели и ценности, способность поддерживать друг друга в трудные моменты, взаимное уважение к индивидуальности, гармония в бытовых вопросах.";
                weaknesses = "Возможна излишняя зависимость друг от друга, риск потери индивидуальности в длительных отношениях, сложности с установлением личных границ.";
                advice = "Сохраняйте личное пространство и интересы, поддерживайте индивидуальное развитие, регулярно обсуждайте ожидания и границы в отношениях.";
            } else if (percentage >= 70) {
                description = "Очень хорошая совместимость. У вас прочная основа для гармоничных отношений. Партнеры хорошо понимают друг друга и имеют схожие жизненные ориентиры. Отношения могут развиваться в позитивном направлении при взаимных усилиях.";
                strengths = "Сильная эмоциональная связь, общие интересы и ценности, способность конструктивно решать конфликты, взаимная поддержка, уважение к различиям, стабильность в отношениях.";
                weaknesses = "Периодические недопонимания из-за разного темперамента, возможны разногласия в вопросах быта и финансов, необходимость работать над коммуникацией.";
                advice = "Учитесь открытому и честному общению, находите компромиссы в спорных вопросах, уважайте различия в темпераментах и подходах к жизни.";
            } else if (percentage >= 55) {
                description = "Умеренная совместимость. Отношения имеют потенциал, но потребуют работы и взаимных уступок. Партнеры могут многому научиться друг у друга, но различия в подходах к жизни могут создавать напряжение.";
                strengths = "Взаимный интерес и притяжение, возможность роста через преодоление различий, взаимное обучение, развитие терпимости, обогащение опыта друг друга.";
                weaknesses = "Значительные различия в ценностях и жизненных приоритетах, частые недопонимания, разные темпы жизни, возможна борьба за лидерство в отношениях.";
                advice = "Фокусируйтесь на общих целях и интересах, развивайте терпимость к различиям, учитесь слушать и понимать точку зрения партнера, устанавливайте четкие правила общения.";
            } else if (percentage >= 40) {
                description = "Сложная совместимость. Отношения будут требовать значительных усилий от обоих партнеров. Различия в основных жизненных подходах могут создавать постоянное напряжение и недопонимание.";
                strengths = "Возможность научиться терпимости и пониманию совершенно другого подхода к жизни, развитие гибкости, получение ценного опыта преодоленияDifficulties.";
                weaknesses = "Постоянные конфликты и недопонимания, фундаментальные различия в ценностях и целях, эмоциональная несовместимость, трудности в нахождении общего языка.";
                advice = "Трезво оценивайте, стоят ли отношения таких усилий, ищите точки соприкосновения и общие интересы, рассматривайте возможность профессиональной помощи в налаживании коммуникации.";
            } else {
                description = "Критически низкая совместимость. Отношения будут крайне сложными и энергозатратными. Фундаментальные различия в подходах к жизни могут сделать совместное существование практически невозможным без постоянных конфликтов.";
                strengths = "Возможность получить урок терпимости и понимания кардинально другого мировоззрения, развитие навыков конфликтологии в экстремальных условиях.";
                weaknesses = "Постоянные серьезные конфликты, полное непонимание мотивов и действий партнера, эмоциональное истощение, отсутствие общих точек соприкосновения.";
                advice = "Seriously consider whether this relationship is worth the emotional cost. If you decide to continue, seek professional counseling and establish very clear boundaries.";
            }
            
            return {
                percentage,
                description,
                strengths,
                weaknesses,
                advice
            };
        }
        
        function calculateFavorableDays(birthDate, eventType, period) {
            const today = new Date();
            let daysCount, periodText;
            
            switch(period) {
                case 'week':
                    daysCount = 7;
                    periodText = 'неделю';
                    break;
                case 'month':
                    daysCount = 30;
                    periodText = 'месяц';
                    break;
                case 'quarter':
                    daysCount = 90;
                    periodText = 'квартал';
                    break;
                case 'year':
                    daysCount = 365;
                    periodText = 'год';
                    break;
                default:
                    daysCount = 30;
                    periodText = 'месяц';
            }
            
            // Генерация уникальных благоприятных дней (без дублирования)
            const favorableDaysCount = 3 + Math.floor(Math.random() * 3);
            const usedDays = new Set();
            let daysHTML = `<p>Наиболее благоприятные дни в ближайшую ${periodText}:</p><ul>`;
            
            for (let i = 0; i < favorableDaysCount; i++) {
                let randomDay;
                let attempts = 0;
                
                // Гарантируем уникальность дат
                do {
                    randomDay = new Date(today);
                    randomDay.setDate(today.getDate() + Math.floor(Math.random() * daysCount));
                    attempts++;
                } while (usedDays.has(randomDay.toDateString()) && attempts < 20);
                
                usedDays.add(randomDay.toDateString());
                
                const day = randomDay.getDate();
                const month = randomDay.getMonth() + 1;
                const year = randomDay.getFullYear();
                
                daysHTML += `<li><strong>${day}.${month}.${year}</strong> - благоприятный день для вашего события</li>`;
            }
            
            daysHTML += '</ul>';
            
            const adviceText = {
                'business': "В эти дни ваша энергия будет направлена на достижение карьерных целей. Планируйте важные встречи, переговоры и начало новых проектов. Особенно эффективны будут действия, связанные с инновациями и стратегическим планированием.",
                'love': "Эти дни благоприятны для романтических встреч, признаний в любви и укрепления отношений. Откройте сердце для новых возможностей. Идеальное время для глубоких разговоров и совместного планирования будущего.",
                'health': "В эти дни эффективны начало диет, оздоровительных практик и медицинских процедур. Слушайте свое тело и дайте ему необходимое. Особенно благоприятны дни для начала новых спортивных routines и консультаций со специалистами.",
                'travel': "Эти дни идеальны для начала путешествий и исследовательских поездок. Новые места принесут вдохновение и ценный опыт. Планируйте маршруты, которые расширят ваш кругозор и принесут новые знакомства.",
                'creativity': "В эти дни творческая энергия на пике. Начинайте художественные проекты, пишите, рисуйте, выражайте себя без ограничений. Особенно благоприятны дни для collaboration и представления своих работ публике.",
                'family': "Эти дни благоприятны для семейных мероприятий, улучшения домашней атмосферы и решения бытовых вопросов. Идеальное время для обсуждения важных семейных тем и укрепления связей между родственниками."
            };
            
            return {
                days: daysHTML,
                advice: adviceText[eventType] || "Используйте эти дни для продуктивной деятельности в выбранной сфере. Сфокусируйтесь на действиях, которые приблизят вас к вашим целям."
            };
        }
        
        function calculateMatrix(birthDate) {
            const day = birthDate.getDate();
            const month = birthDate.getMonth() + 1;
            const year = birthDate.getFullYear();
            
            // Расчет чисел для матрицы
            const firstNumber = reduceNumber(day);
            const secondNumber = reduceNumber(month);
            const thirdNumber = reduceNumber(year);
            const fourthNumber = reduceNumber(firstNumber + secondNumber + thirdNumber);
            
            // Создание сетки матрицы 3x3
            let gridHTML = '';
            const numbers = [firstNumber, secondNumber, thirdNumber, fourthNumber];
            
            for (let i = 1; i <= 9; i++) {
                const isActive = numbers.includes(i);
                gridHTML += `<div class="matrix-cell ${isActive ? 'active' : ''}">${i}</div>`;
            }
            
            const description = `<p>Ваша матрица содержит числа: <strong>${firstNumber}</strong> (день рождения), <strong>${secondNumber}</strong> (месяц рождения), <strong>${thirdNumber}</strong> (год рождения) и <strong>${fourthNumber}</strong> (суммарное число судьбы).</p>
            <p>Активные числа в вашей матрице указывают на ключевые энергии, влияющие на вашу жизнь. Каждое число несет определенную вибрацию и оказывает специфическое воздействие на различные аспекты вашего бытия.</p>`;
            
            const strengths = "Сильный аналитический ум, развитая интуиция, практичность в сочетании с творческим подходом к решению задач, способность к глубокой концентрации, умение видеть скрытые закономерности, талант к систематизации информации.";
            const weaknesses = "Склонность к перфекционизму, occasional трудности в принятии решений, периодическая неуверенность в собственных силах, tendency к чрезмерному анализу ситуаций, сложности с быстрой адаптацией к изменениям.";
            const advice = "Развивайте эмоциональный интеллект и навыки межличностного общения. Учитесь делегировать задачи и доверять другим. Находите баланс между работой и отдыхом. Практикуйте техники принятия решений в условиях неопределенности. Развивайте гибкость мышления и открытость новому опыту.";
            
            return {
                grid: gridHTML,
                description,
                strengths,
                weaknesses,
                advice
            };
        }
        
        function calculateNumerologyPortrait(fullName, birthDate) {
            const name = fullName.toUpperCase();
            
            // Расчет числа жизненного пути
            const day = birthDate.getDate();
            const month = birthDate.getMonth() + 1;
            const year = birthDate.getFullYear();
            
            let lifePathNumber = reduceNumber(day) + reduceNumber(month) + reduceNumber(year);
            lifePathNumber = reduceNumber(lifePathNumber);
            
            // Расчет числа судьбы (по ФИО)
            const letterValues = {
                'А': 1, 'Б': 2, 'В': 3, 'Г': 4, 'Д': 5, 'Е': 6, 'Ё': 7, 'Ж': 8, 'З': 9,
                'И': 1, 'Й': 2, 'К': 3, 'Л': 4, 'М': 5, 'Н': 6, 'О': 7, 'П': 8, 'Р': 9,
                'С': 1, 'Т': 2, 'У': 3, 'Ф': 4, 'Х': 5, 'Ц': 6, 'Ч': 7, 'Ш': 8, 'Щ': 9,
                'Ъ': 1, 'Ы': 2, 'Ь': 3, 'Э': 4, 'Ю': 5, 'Я': 6
            };
            
            let destinySum = 0;
            for (let i = 0; i < name.length; i++) {
                const char = name[i];
                if (letterValues[char]) {
                    destinySum += letterValues[char];
                }
            }
            const destinyNumber = reduceNumber(destinySum);
            
            // Расчет числа души (гласные)
            const vowels = 'АЕЁИОУЫЭЮЯ';
            let soulSum = 0;
            for (let i = 0; i < name.length; i++) {
                const char = name[i];
                if (vowels.includes(char) && letterValues[char]) {
                    soulSum += letterValues[char];
                }
            }
            const soulNumber = reduceNumber(soulSum);
            
            // Расчет числа внешнего облика (согласные)
            let appearanceSum = 0;
            for (let i = 0; i < name.length; i++) {
                const char = name[i];
                if (!vowels.includes(char) && letterValues[char]) {
                    appearanceSum += letterValues[char];
                }
            }
            const appearanceNumber = reduceNumber(appearanceSum);
            
            // Расчет числа дня рождения
            const birthdayNumber = reduceNumber(day);
            
            // Расчет кармического числа
            const karmicNumber = reduceNumber(day + month);
            
            return {
                lifePath: {
                    number: lifePathNumber,
                    description: getLifePathShortDescription(lifePathNumber)
                },
                destiny: {
                    number: destinyNumber,
                    description: getDestinyDescription(destinyNumber)
                },
                soul: {
                    number: soulNumber,
                    description: getSoulDescription(soulNumber)
                },
                appearance: {
                    number: appearanceNumber,
                    description: getAppearanceDescription(appearanceNumber)
                },
                birthday: {
                    number: birthdayNumber,
                    description: getBirthdayDescription(birthdayNumber)
                },
                karmic: {
                    number: karmicNumber,
                    description: getKarmicDescription(karmicNumber)
                },
                strengths: "Вы обладаете редким сочетанием аналитического ума и творческих способностей. Ваша сильная воля сочетается с развитой интуицией, что позволяет вам достигать поставленных целей нестандартными путями. Вы умеете вдохновлять людей и создавать вокруг себя гармоничную атмосферу.",
                weaknesses: "Иногда вы можете быть излишне критичны к себе и окружающим. Склонность к перфекционизму может замедлять ваше движение вперед. Временами вы испытываете трудности с принятием быстрых решений в условиях неопределенности.",
                advice: "Развивайте навыки быстрого принятия решений и учитесь доверять своей интуиции. Практикуйте техники эмоциональной саморегуляции. Находите баланс между работой и отдыхом. Учитесь делегировать задачи и принимать помощь от других. Развивайте гибкость в общении с разными типами личности."
            };
        }
        
        function getLifePathShortDescription(number) {
            const descriptions = {
                1: "Лидер, новатор, первооткрыватель",
                2: "Дипломат, миротворец, сотрудник",
                3: "Творец, коммуникатор, оптимист",
                4: "Строитель, организатор, практик",
                5: "Исследователь, новатор, авантюрист",
                6: "Воспитатель, защитник, гармонизатор",
                7: "Аналитик, мудрец, исследователь",
                8: "Организатор, руководитель, материалист",
                9: "Гуманист, филантроп, учитель",
                11: "Вдохновитель, просветитель, визионер",
                22: "Строитель-практик, мастер, реализатор",
                33: "Учитель, целитель, служитель"
            };
            return descriptions[number] || "Уникальный путь";
        }
        
        function getDestinyDescription(number) {
            const descriptions = {
                1: "Ваше предназначение - лидерство и создание нового",
                2: "Ваша миссия - гармонизация отношений и сотрудничество",
                3: "Ваша судьба - творческое самовыражение и вдохновение",
                4: "Ваша задача - создание прочных основ и систем",
                5: "Ваш путь - свобода, изменения и расширение горизонтов",
                6: "Ваше призвание - служение семье и обществу",
                7: "Ваша цель - поиск истины и глубинного знания",
                8: "Ваша миссия - материальное воплощение идей",
                9: "Ваше предназначение - служение человечеству",
                11: "Ваша судьба - духовное просвещение и вдохновение",
                22: "Ваша задача - практическая реализация глобальных идей",
                33: "Ваше призвание - служение через любовь и исцеление"
            };
            return descriptions[number] || "Уникальное предназначение";
        }
        
        function getSoulDescription(number) {
            const descriptions = {
                1: "Вы стремитесь к независимости и самореализации",
                2: "Ваша душа жаждет гармонии и партнерства",
                3: "Вы ищете самовыражения и творческой реализации",
                4: "Ваша душа ценит стабильность и безопасность",
                5: "Вы стремитесь к свободе и новым впечатлениям",
                6: "Ваша душа ищет любви и семейного счастья",
                7: "Вы стремитесь к мудрости и духовному росту",
                8: "Ваша душа жаждет признания и материального успеха",
                9: "Вы ищете служения и помощи другим",
                11: "Ваша душа стремится к духовному просветлению",
                22: "Вы жаждете практической реализации великих идей",
                33: "Ваша душа ищет безусловной любви и служения"
            };
            return descriptions[number] || "Уникальные душевные стремления";
        }
        
        function getAppearanceDescription(number) {
            const descriptions = {
                1: "Вы производите впечатление уверенного и независимого человека",
                2: "Вас воспринимают как дипломатичного и дружелюбного",
                3: "Вы кажетесь творческим и обаятельным",
                4: "Вас видят надежным и практичным",
                5: "Вы производите впечатление свободолюбивого и динамичного",
                6: "Вас воспринимают как заботливого и ответственного",
                7: "Вы кажетесь мудрым и сдержанным",
                8: "Вас видят успешным и авторитетным",
                9: "Вы производите впечатление великодушного и альтруистичного",
                11: "Вас воспринимают как вдохновенного и духовного",
                22: "Вы кажетесь практичным мечтателем",
                33: "Вас видят как сострадательного и мудрого"
            };
            return descriptions[number] || "Уникальное внешнее впечатление";
        }
        
        function getBirthdayDescription(number) {
            const descriptions = {
                1: "Талант лидерства и инициативы",
                2: "Дар дипломатии и сотрудничества",
                3: "Творческие способности и коммуникабельность",
                4: "Практичность и организаторские способности",
                5: "Адаптивность и любознательность",
                6: "Ответственность и заботливость",
                7: "Аналитический ум и интуиция",
                8: "Деловая хватка и амбициозность",
                9: "Гуманизм и щедрость",
                10: "Уверенность в себе и лидерские качества",
                11: "Вдохновенность и духовность",
                12: "Творческий подход и коммуникабельность",
                13: "Практичность и трудолюбие",
                14: "Адаптивность и свобода",
                15: "Ответственность и семейные ценности",
                16: "Аналитический ум и глубина",
                17: "Деловые качества и уверенность",
                18: "Гуманизм и альтруизм",
                19: "Лидерство и независимость",
                20: "Дипломатия и чувствительность",
                21: "Творчество и оптимизм",
                22: "Практическая мудрость и масштабность",
                23: "Адаптивность и коммуникабельность",
                24: "Ответственность и гармония",
                25: "Аналитические способности и интуиция",
                26: "Деловые качества и партнерство",
                27: "Гуманизм и мудрость",
                28: "Лидерство и уверенность",
                29: "Чувствительность и интуиция",
                30: "Творчество и самовыражение",
                31: "Практичность и инициатива"
            };
            return descriptions[number] || "Уникальный врожденный талант";
        }
        
        function getKarmicDescription(number) {
            const descriptions = {
                1: "Урок независимости и уверенности в себе",
                2: "Урок сотрудничества и терпимости",
                3: "Урок самовыражения и радости жизни",
                4: "Урок дисциплины и практичности",
                5: "Урок свободы и ответственности",
                6: "Урок любви и заботы о других",
                7: "Урок веры и духовного развития",
                8: "Урок изобилия и щедрости",
                9: "Урок служения и всепрощения",
                10: "Урок лидерства и инициативы",
                11: "Урок духовного просветления",
                12: "Урок творческого самовыражения",
                13: "Урок практичности и усердия",
                14: "Урок адаптивности и свободы",
                15: "Урок любви и ответственности",
                16: "Урок мудрости и самопознания",
                17: "Урок успеха и уверенности",
                18: "Урок гуманизма и альтруизма",
                19: "Урок лидерства и независимости",
                20: "Урок дипломатии и чувствительности",
                21: "Урок творчества и оптимизма",
                22: "Урок практической реализации",
                23: "Урок адаптивности и общения",
                24: "Урок гармонии и ответственности",
                25: "Урок интуиции и анализа",
                26: "Урок партнерства и успеха",
                27: "Урок мудрости и гуманизма",
                28: "Урок уверенности и лидерства",
                29: "Урок интуиции и чувствительности",
                30: "Урок самовыражения и творчества",
                31: "Урок инициативы и практичности"
            };
            return descriptions[number] || "Уникальный кармический урок";
        }
    </script>
</body>
</html>
