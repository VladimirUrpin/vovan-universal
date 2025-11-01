<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NumerologyLab - Ваш Числовой Код</title>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        /* Сброс и базовые стили */
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; line-height: 1.6; color: #333; background-color: #f8f9fa; }

        /* Стили заголовков */
        h1, h2, h3 { color: #4a4a9c; margin-bottom: 0.5em; }
        h1 { font-size: 2.5rem; }
        h2 { font-size: 2rem; }

        /* Навигация */
        nav { background: linear-gradient(135deg, #6a11cb 0%, #2575fc 100%); color: white; padding: 1rem 0; box-shadow: 0 2px 5px rgba(0,0,0,0.1); }
        .nav-container { max-width: 1200px; margin: 0 auto; display: flex; justify-content: space-between; align-items: center; padding: 0 2rem; }
        .logo { font-size: 1.8rem; font-weight: bold; }
        .nav-links { display: flex; list-style: none; }
        .nav-links li { margin-left: 2rem; }
        .nav-links a { color: white; text-decoration: none; transition: opacity 0.3s; }
        .nav-links a:hover { opacity: 0.8; }

        /* Основной контент */
        .container { max-width: 1200px; margin: 2rem auto; padding: 0 2rem; }
        .hero { text-align: center; padding: 4rem 0; background: white; border-radius: 10px; margin-bottom: 2rem; box-shadow: 0 5px 15px rgba(0,0,0,0.05); }
        .hero p { font-size: 1.2rem; max-width: 600px; margin: 1rem auto; color: #666; }

        /* Секции и карточки */
        section { background: white; padding: 2rem; margin-bottom: 2rem; border-radius: 10px; box-shadow: 0 5px 15px rgba(0,0,0,0.05); }
        .calculator-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 2rem; margin-top: 2rem; }
        .calculator-card { background: #f8f9fa; padding: 1.5rem; border-radius: 8px; border-left: 4px solid #6a11cb; transition: transform 0.3s; cursor: pointer; }
        .calculator-card:hover { transform: translateY(-5px); }

        /* Формы */
        .calculator { max-width: 500px; margin: 0 auto; }
        .form-group { margin-bottom: 1rem; }
        label { display: block; margin-bottom: 0.5rem; font-weight: 600; }
        input[type="text"], input[type="date"] { width: 100%; padding: 0.75rem; border: 1px solid #ddd; border-radius: 4px; font-size: 1rem; }
        button { background: linear-gradient(135deg, #6a11cb 0%, #2575fc 100%); color: white; border: none; padding: 0.75rem 1.5rem; border-radius: 4px; font-size: 1rem; cursor: pointer; transition: opacity 0.3s; }
        button:hover { opacity: 0.9; }

        /* Результаты */
        .result { margin-top: 2rem; padding: 1.5rem; background: #eef2ff; border-radius: 8px; border-left: 4px solid #2575fc; display: none; }
        .master-number { color: #d4af37; font-weight: bold; }
        #compatibilityChart { max-width: 400px; margin: 1rem auto; }
    </style>
</head>
<body>
    <!-- Навигация -->
    <nav>
        <div class="nav-container">
            <div class="logo">NumerologyLab</div>
            <ul class="nav-links">
                <li><a href="#home">Главная</a></li>
                <li><a href="#life-path">Число Жизненного Пути</a></li>
                <li><a href="#compatibility">Совместимость</a></li>
            </ul>
        </div>
    </nav>

    <!-- Главная страница -->
    <div class="container" id="home">
        <section class="hero">
            <h1>Раскройте свой числовой код</h1>
            <p>NumerologyLab — это современный инструмент для самопознания. Узнайте свои сильные стороны, предназначение и будущее с помощью нумерологии.</p>
            <button onclick="scrollToSection('life-path')">Рассчитать свое число</button>
        </section>

        <section>
            <h2>Популярные калькуляторы</h2>
            <div class="calculator-grid">
                <div class="calculator-card" onclick="scrollToSection('life-path')">
                    <h3>Число Жизненного Пути</h3>
                    <p>Самое важное число в вашей нумерологической карте. Определяет жизненные задачи и ваш путь.</p>
                </div>
                <div class="calculator-card" onclick="scrollToSection('compatibility')">
                    <h3>Совместимость</h3>
                    <p>Узнайте, насколько вы гармонируете с вашим партнером, другом или коллегой.</p>
                </div>
            </div>
        </section>
    </div>

    <!-- Калькулятор 1: Число Жизненного Пути -->
    <div class="container" id="life-path">
        <section>
            <h2>Калькулятор: Число Жизненного Пути</h2>
            <p>Введите вашу дату рождения, чтобы рассчитать число, которое определяет основные тенденции вашей жизни.</p>
            
            <div class="calculator">
                <div class="form-group">
                    <label for="birthdate">Дата рождения:</label>
                    <input type="date" id="birthdate" required>
                </div>
                <button onclick="calculateLifePath()">Рассчитать Число Жизненного Пути</button>
                
                <div id="lifePathResult" class="result">
                    <h3>Результат:</h3>
                    <p>Ваше Число Жизненного Пути: <span id="lifePathNumber"></span></p>
                    <div id="lifePathDescription"></div>
                </div>
            </div>
        </section>
    </div>

    <!-- Калькулятор 2: Совместимость -->
    <div class="container" id="compatibility">
        <section>
            <h2>Калькулятор: Совместимость партнеров</h2>
            <p>Введите данные двух людей, чтобы узнать потенциал их отношений.</p>
            
            <div class="calculator">
                <div class="form-group">
                    <label for="person1Name">Имя первого человека:</label>
                    <input type="text" id="person1Name" placeholder="Например, Мария">
                </div>
                <div class="form-group">
                    <label for="person1Birthdate">Дата рождения первого человека:</label>
                    <input type="date" id="person1Birthdate" required>
                </div>
                
                <div class="form-group">
                    <label for="person2Name">Имя второго человека:</label>
                    <input type="text" id="person2Name" placeholder="Например, Алексей">
                </div>
                <div class="form-group">
                    <label for="person2Birthdate">Дата рождения второго человека:</label>
                    <input type="date" id="person2Birthdate" required>
                </div>
                
                <button onclick="calculateCompatibility()">Рассчитать совместимость</button>
                
                <div id="compatibilityResult" class="result">
                    <h3>Результат совместимости:</h3>
                    <p id="compatibilityPercentage"></p>
                    <canvas id="compatibilityChart"></canvas>
                    <div id="compatibilityDescription"></div>
                </div>
            </div>
        </section>
    </div>

    <script>
        // Вспомогательная функция для прокрутки к секции
        function scrollToSection(sectionId) {
            document.getElementById(sectionId).scrollIntoView({ behavior: 'smooth' });
        }

        // Функция для расчета Числа Жизненного Пути
        function calculateLifePath() {
            const birthdate = new Date(document.getElementById('birthdate').value);
            if (isNaN(birthdate)) {
                alert('Пожалуйста, введите корректную дату рождения.');
                return;
            }

            const day = birthdate.getDate();
            const month = birthdate.getMonth() + 1; // Месяцы с 0
            const year = birthdate.getFullYear();

            // Суммируем цифры даты
            let sum = sumDigits(day) + sumDigits(month) + sumDigits(year);

            // Сводим к однозначному числу, учитывая мастер-числа
            let lifePathNumber = reduceToSingleDigit(sum);

            // Проверяем, не является ли изначальная сумма мастер-числом
            if (sum === 11 || sum === 22 || sum === 33) {
                lifePathNumber = sum;
            }

            // Отображаем результат
            document.getElementById('lifePathNumber').innerHTML = `<span class="master-number">${lifePathNumber}</span>`;
            document.getElementById('lifePathDescription').innerHTML = getLifePathDescription(lifePathNumber);
            document.getElementById('lifePathResult').style.display = 'block';
        }

        // Функция для расчета суммы цифр числа
        function sumDigits(number) {
            let sum = 0;
            while (number > 0) {
                sum += number % 10;
                number = Math.floor(number / 10);
            }
            return sum;
        }

        // Функция для сведения к однозначному числу
        function reduceToSingleDigit(num) {
            while (num > 9 && num !== 11 && num !== 22 && num !== 33) {
                num = sumDigits(num);
            }
            return num;
        }

        // База данных описаний для Чисел Жизненного Пути
        function getLifePathDescription(number) {
            const descriptions = {
                1: "Вы прирожденный лидер, независимый и амбициозный. Ваша задача — вести за собой, а не следовать за другими. Вы обладаете сильной волей и оригинальным мышлением.",
                2: "Вы дипломат и миротворец. Ваша сила — в сотрудничестве, чувствительности и интуиции. Вы создаете гармонию и умеете работать в команде.",
                3: "Вы творческий, оптимистичный и общительный человек. Ваш дар — самовыражение через слово, искусство или юмор. Вы вдохновляете окружающих.",
                4: "Вы практичный, надежный и трудолюбивый строитель. Ваша задача — создавать прочные основы и системы. Вы цените стабильность и порядок.",
                5: "Вы свободолюбивый искатель приключений. Ваша стихия — перемены, свобода и новый опыт. Вы адаптивны и любите разнообразие.",
                6: "Вы заботливый и ответственный воспитатель. Ваша миссия — служение семье, дому и обществу. Вы стремитесь к гармонии и красоте.",
                7: "Вы аналитик и искатель истины. Ваш путь — это путь знаний, самоанализа и духовного поиска. Вы любите уединение и глубокие размышления.",
                8: "Вы сильный и властный организатор. Ваша сфера — деньги, власть и карьера. Вы умеете достигать материальных целей и управлять ресурсами.",
                9: "Вы гуманист и филантроп. Ваше предназначение — сострадание, служение человечеству и завершение циклов. Вы обладаете широким кругозором.",
                11: "Вы просветленный и вдохновляющий учитель. Это мастер-число высокой духовной вибрации. Вы призваны нести высшие идеи и вдохновлять массы.",
                22: "Вы мастер-строитель, способный воплощать грандиозные планы в реальность. Вы умеете объединять духовное и материальное для великих свершений.",
                33: "Вы великий учитель, посвятивший себя служению человечеству. Это число высшей ответственности, безусловной любви и жертвенности."
            };
            return `<p><strong>Расшифровка:</strong> ${descriptions[number] || "Описание для этого числа пока недоступно."}</p>`;
        }

        // Функция для расчета совместимости
        function calculateCompatibility() {
            const person1Birthdate = new Date(document.getElementById('person1Birthdate').value);
            const person2Birthdate = new Date(document.getElementById('person2Birthdate').value);

            if (isNaN(person1Birthdate) || isNaN(person2Birthdate)) {
                alert('Пожалуйста, введите корректные даты рождения для обоих людей.');
                return;
            }

            // Рассчитываем Числа Жизненного Пути для обоих
            const person1LifePath = calculateLifePathFromDate(person1Birthdate);
            const person2LifePath = calculateLifePathFromDate(person2Birthdate);

            // Простой расчет "совместимости" (для прототипа)
            // В реальности здесь должна быть сложная логика с матрицей совместимости
            const compatibilityScore = Math.abs(person1LifePath - person2LifePath);
            let percentage;

            if (compatibilityScore === 0) percentage = 95;
            else if (compatibilityScore <= 2) percentage = 80 - (compatibilityScore * 10);
            else if (compatibilityScore <= 4) percentage = 60 - ((compatibilityScore - 2) * 8);
            else percentage = 30;

            percentage = Math.max(10, Math.min(95, percentage)); // Ограничиваем проценты

            // Получаем имена
            const person1Name = document.getElementById('person1Name').value || "Первый партнер";
            const person2Name = document.getElementById('person2Name').value || "Второй партнер";

            // Отображаем результат
            document.getElementById('compatibilityPercentage').innerText = `Совместимость между ${person1Name} и ${person2Name}: ${percentage}%`;
            document.getElementById('compatibilityDescription').innerHTML = getCompatibilityDescription(percentage, person1LifePath, person2LifePath);
            document.getElementById('compatibilityResult').style.display = 'block';

            // Строим круговую диаграмму
            renderCompatibilityChart(percentage);
        }

        // Вспомогательная функция для расчета ЧЖП из даты
        function calculateLifePathFromDate(date) {
            const day = date.getDate();
            const month = date.getMonth() + 1;
            const year = date.getFullYear();

            let sum = sumDigits(day) + sumDigits(month) + sumDigits(year);
            return reduceToSingleDigit(sum);
        }

        // Генератор описания совместимости
        function getCompatibilityDescription(percentage, num1, num2) {
            let description = "";
            
            if (percentage >= 80) {
                description = `<p>Отличная совместимость! У вас много общего, и вы легко понимаете друг друга. Этот союз имеет все шансы стать гармоничным и долговечным.</p>`;
            } else if (percentage >= 60) {
                description = `<p>Хорошая совместимость. Вам есть над чем работать, но в целом ваши энергии хорошо сочетаются. Взаимное уважение и компромисс помогут укрепить отношения.</p>`;
            } else if (percentage >= 40) {
                description = `<p>Средняя совместимость. Вам может быть интересно вместе, но возможны недопонимания и конфликты. Потребуются усилия с обеих сторон для гармонизации.</p>`;
            } else {
                description = `<p>Низкая совместимость. Ваши жизненные пути и энергии значительно различаются. Это не значит, что отношения обречены, но они потребуют много работы и терпения.</p>`;
            }

            description += `<p><strong>Число Жизненного Пути ${num1}</strong> и <strong>Число Жизненного Пути ${num2}</strong> ${getCompatibilityByNumbers(num1, num2)}</p>`;
            
            return description;
        }

        // Простая логика совместимости по числам (для прототипа)
        function getCompatibilityByNumbers(num1, num2) {
            const compatiblePairs = ["1 и 5", "2 и 6", "3 и 5", "4 и 8", "6 и 9"];
            const pair = `${num1} и ${num2}`;
            const reversePair = `${num2} и ${num1}`;

            if (num1 === num2) return "имеют одинаковую вибрацию, что создает сильное взаимопонимание.";
            if (compatiblePairs.includes(pair) || compatiblePairs.includes(reversePair)) {
                return "хорошо сочетаются по энергии и дополняют друг друга.";
            }
            return "имеют разные вибрации, что может создавать как притяжение, так и напряжение.";
        }

        // Визуализация совместимости с помощью Chart.js
        function renderCompatibilityChart(percentage) {
            const ctx = document.getElementById('compatibilityChart').getContext('2d');
            
            // Уничтожаем предыдущий график, если он есть
            if (window.compatibilityChartInstance) {
                window.compatibilityChartInstance.destroy();
            }

            window.compatibilityChartInstance = new Chart(ctx, {
                type: 'doughnut',
                data: {
                    labels: ['Совместимость', 'Несовместимость'],
                    datasets: [{
                        data: [percentage, 100 - percentage],
                        backgroundColor: [
                            'rgba(106, 17, 203, 0.7)',
                            'rgba(200, 200, 200, 0.5)'
                        ],
                        borderColor: [
                            'rgba(106, 17, 203, 1)',
                            'rgba(200, 200, 200, 1)'
                        ],
                        borderWidth: 1
                    }]
                },
                options: {
                    responsive: true,
                    plugins: {
                        legend: {
                            position: 'bottom',
                        },
                        tooltip: {
                            callbacks: {
                                label: function(context) {
                                    return context.label + ': ' + context.raw + '%';
                                }
                            }
                        }
                    }
                }
            });
        }
    </script>
</body>
</html>
