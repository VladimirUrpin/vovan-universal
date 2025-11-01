<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Космос Чисел - NumerologyLab</title>
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
        }
        
        .calculator-form {
            max-width: 500px;
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
        
        .form-group input {
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
                <div class="feature-card">
                    <div class="feature-icon">🌌</div>
                    <h3>Число Жизненного Пути</h3>
                    <p>Узнайте свое основное число, которое определяет ваш жизненный путь и предназначение</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">💫</div>
                    <h3>Совместимость</h3>
                    <p>Проанализируйте совместимость с партнером, друзьями или коллегами по числам</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">📅</div>
                    <h3>Планирование</h3>
                    <p>Определите благоприятные дни для важных событий с помощью нумерологии</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">📊</div>
                    <h3>Матрица Судьбы</h3>
                    <p>Получите полный нумерологический портрет с помощью современной матрицы</p>
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
                <div class="calculator-tab active" data-tab="life-path">Число Жизненного Пути</div>
                <div class="calculator-tab" data-tab="destiny">Число Судьбы</div>
                <div class="calculator-tab" data-tab="soul">Число Души</div>
                <div class="calculator-tab" data-tab="appearance">Число Внешнего Облика</div>
            </div>
            <div class="calculator-content">
                <div class="calculator-form" id="life-path-form">
                    <h3>Расчет Числа Жизненного Пути</h3>
                    <p>Введите вашу дату рождения, чтобы узнать основное число вашей жизни</p>
                    <div class="form-group">
                        <label for="birth-date">Дата рождения</label>
                        <input type="date" id="birth-date" required>
                    </div>
                    <button class="btn" id="calculate-life-path">Рассчитать</button>
                    <div class="calculator-result" id="life-path-result">
                        <h3>Ваше Число Жизненного Пути: <span id="life-path-number"></span></h3>
                        <p id="life-path-description"></p>
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
        
        // Табы калькуляторов
        const tabs = document.querySelectorAll('.calculator-tab');
        tabs.forEach(tab => {
            tab.addEventListener('click', function() {
                tabs.forEach(t => t.classList.remove('active'));
                this.classList.add('active');
                // Здесь должна быть логика смены форм калькуляторов
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
            document.getElementById('life-path-result').style.display = 'block';
        });
        
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
                1: "Вы - прирожденный лидер, независимый и амбициозный. Ваша сила в инициативе и способности начинать новые дела.",
                2: "Вы - дипломат и миротворец, чувствительный и интуитивный. Ваша сила в сотрудничестве и создании гармонии.",
                3: "Вы - творческая личность, выразительный и оптимистичный. Ваша сила в самовыражении и коммуникации.",
                4: "Вы - практичный строитель, надежный и трудолюбивый. Ваша сила в стабильности и создании прочного фундамента.",
                5: "Вы - искатель свободы, адаптивный и любознательный. Ваша сила в изменениях и разнообразии опыта.",
                6: "Вы - воспитатель, ответственный и заботливый. Ваша сила в служении и создании гармонии в отношениях.",
                7: "Вы - мыслитель, аналитичный и духовный. Ваша сила в поиске истины и внутренней мудрости.",
                8: "Вы - организатор, амбициозный и эффективный. Ваша сила в достижении материального успеха и власти.",
                9: "Вы - гуманист, сострадательный и идеалистичный. Ваша сила в завершении циклов и служении человечеству.",
                11: "Вы - просветленный, интуитивный и вдохновляющий. Ваша сила в духовном озарении и служении высшим идеалам.",
                22: "Вы - мастер-строитель, практичный мечтатель. Ваша сила в реализации грандиозных планов на благо человечества.",
                33: "Вы - мастер-учитель, сострадательный и вдохновляющий. Ваша сила в служении через любовь и исцеление."
            };
            
            return descriptions[number] || "Описание для этого числа пока недоступно.";
        }
    </script>
</body>
</html>
