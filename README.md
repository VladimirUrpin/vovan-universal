<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Психологический тест</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            background-color: #f5f5f5;
        }
        .screen {
            background: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            margin-bottom: 20px;
        }
        h1, h2 {
            color: #4a4a4a;
            text-align: center;
        }
        h3 {
            color: #555;
        }
        input, select, button {
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ddd;
            border-radius: 5px;
            width: 100%;
            box-sizing: border-box;
        }
        button {
            background-color: #4CAF50;
            color: white;
            border: none;
            cursor: pointer;
            font-size: 16px;
        }
        button:hover {
            background-color: #45a049;
        }
        .question {
            margin-bottom: 25px;
            padding-bottom: 15px;
            border-bottom: 1px solid #eee;
        }
        .options label {
            display: block;
            padding: 10px;
            margin: 5px 0;
            background-color: #f9f9f9;
            border-radius: 5px;
            cursor: pointer;
        }
        .options label:hover {
            background-color: #e9e9e9;
        }
        .options input {
            width: auto;
            margin-right: 10px;
        }
        .result-item {
            background: #f9f9f9;
            padding: 15px;
            margin: 10px 0;
            border-radius: 5px;
        }
        .positive {
            color: #2e7d32;
            background-color: #e8f5e9;
            padding: 10px;
            border-radius: 5px;
            margin: 5px 0;
        }
        .negative {
            color: #c62828;
            background-color: #ffebee;
            padding: 10px;
            border-radius: 5px;
            margin: 5px 0;
        }
        .solution {
            color: #1565c0;
            background-color: #e3f2fd;
            padding: 10px;
            border-radius: 5px;
            margin: 5px 0;
        }
        .hidden {
            display: none;
        }
        .trait-list {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin: 10px 0;
        }
        .trait {
            background: #e3f2fd;
            padding: 5px 10px;
            border-radius: 15px;
            font-size: 14px;
        }
    </style>
</head>
<body>
    <!-- Экран ввода данных -->
    <div id="userInfoScreen" class="screen">
        <h1>Психологический тест</h1>
        <p>Пройдите тест, чтобы узнать больше о своем психологическом портрете</p>
        
        <label for="userName">Ваше имя:</label>
        <input type="text" id="userName" placeholder="Введите ваше имя">
        
        <label for="userBirthdate">Дата рождения:</label>
        <input type="date" id="userBirthdate">
        
        <label for="userGender">Ваш пол:</label>
        <select id="userGender">
            <option value="male">Мужской</option>
            <option value="female">Женский</option>
        </select>
        
        <button id="startTest">Начать тест</button>
    </div>

    <!-- Экран теста -->
    <div id="testScreen" class="screen hidden">
        <h2>Ответьте на вопросы</h2>
        <div id="questionsContainer"></div>
        <button id="submitTest">Получить результат</button>
    </div>

    <!-- Экран результатов -->
    <div id="resultScreen" class="screen hidden">
        <h2>Ваш психологический портрет</h2>
        <div id="resultContent"></div>
        <button id="viewResults">Посмотреть все результаты</button>
        <button id="newTest">Пройти тест заново</button>
    </div>

    <!-- Экран истории результатов -->
    <div id="historyScreen" class="screen hidden">
        <h2>История ваших результатов</h2>
        <div id="historyContent"></div>
        <button id="backToResults">Назад к результатам</button>
        <button id="clearHistory">Очистить историю</button>
    </div>

    <script>
        // Данные теста
        const testQuestions = [
            {
                question: "Как вы обычно реагируете на стрессовые ситуации?",
                options: [
                    "Стараюсь сохранять спокойствие и искать решение",
                    "Нуждаюсь в поддержке и совете близких",
                    "Становлюсь раздражительным и эмоциональным",
                    "Отстраняюсь и стараюсь побыть один",
                    "Активно действую, чтобы решить проблему"
                ]
            },
            {
                question: "Что для вас важнее в общении с людьми?",
                options: [
                    "Честность и прямота",
                    "Взаимопонимание и эмоциональная связь",
                    "Веселье и позитивная атмосфера",
                    "Глубокие, содержательные разговоры",
                    "Практическая польза от общения"
                ]
            },
            {
                question: "Как вы принимаете важные решения?",
                options: [
                    "Тщательно анализирую все варианты",
                    "Прислушиваюсь к своей интуиции",
                    "Советуюсь с близкими или экспертами",
                    "Действую импульсивно, по настроению",
                    "Выбираю самый практичный вариант"
                ]
            },
            {
                question: "Что лучше описывает ваш подход к работе?",
                options: [
                    "Ставлю цели и систематически их достигаю",
                    "Ищу творческий подход и вдохновение",
                    "Работаю в комфортном, спокойном темпе",
                    "Много общаюсь с коллегами, работа в команде",
                    "Беру на себя ответственность и веду за собой"
                ]
            },
            {
                question: "Как вы проводите свободное время?",
                options: [
                    "Занимаюсь саморазвитием, читаю, учусь",
                    "Встречаюсь с друзьями, общаюсь",
                    "Занимаюсь творчеством или хобби",
                    "Отдыхаю дома, смотрю фильмы",
                    "Активный отдых, спорт, путешествия"
                ]
            },
            {
                question: "Как вы ведете себя в конфликтных ситуациях?",
                options: [
                    "Стараюсь найти компромисс",
                    "Избегаю конфликтов, уступаю",
                    "Отстаиваю свою позицию активно",
                    "Анализирую причины конфликта",
                    "Обращаюсь к третьей стороне для помощи"
                ]
            },
            {
                question: "Что для вас значит успех?",
                options: [
                    "Достижение поставленных целей",
                    "Гармония в личной жизни",
                    "Признание окружающих",
                    "Возможность самореализации",
                    "Финансовая стабильность и безопасность"
                ]
            },
            {
                question: "Как вы учитесь новому?",
                options: [
                    "Систематически, по плану",
                    "Через практику и опыт",
                    "В процессе общения с другими",
                    "Интуитивно, методом проб и ошибок",
                    "Только когда это действительно необходимо"
                ]
            },
            {
                question: "Как вы проявляете заботу о близких?",
                options: [
                    "Помогаю практическими действиями",
                    "Поддерживаю эмоционально, выслушиваю",
                    "Дарю подарки, делаю сюрпризы",
                    "Провожу с ними много времени",
                    "Даю советы, помогаю решать проблемы"
                ]
            },
            {
                question: "Что вас мотивирует?",
                options: [
                    "Чувство долга и ответственности",
                    "Желание помогать другим",
                    "Стремление к признанию",
                    "Интерес и любопытство",
                    "Личный рост и развитие"
                ]
            }
        ];

        // Типы личности по результатам теста
        const personalityTypes = {
            "Аналитик": {
                description: "Вы логичны, рациональны и цените знания. Принимаете решения на основе анализа, а не эмоций.",
                traits: ["рациональность", "любознательность", "независимость", "критическое мышление", "системность"],
                strengths: [
                    "Способность глубоко анализировать ситуации",
                    "Объективность в принятии решений",
                    "Любовь к обучению и саморазвитию",
                    "Надежность и последовательность"
                ],
                weaknesses: [
                    "Склонность к чрезмерному анализу и сомнениям",
                    "Трудности в выражении эмоций",
                    "Излишняя критичность к себе и другим",
                    "Сложности в спонтанных ситуациях"
                ],
                solutions: [
                    "Учитесь доверять интуиции и принимать быстрые решения",
                    "Развивайте эмоциональный интеллект",
                    "Практикуйте спонтанные действия",
                    "Находите баланс между анализом и действием"
                ]
            },
            "Эмпат": {
                description: "Вы чувствительны к эмоциям других, заботливы и стремитесь к гармонии в отношениях.",
                traits: ["чувствительность", "заботливость", "дипломатичность", "интуитивность", "отзывчивость"],
                strengths: [
                    "Отличное понимание эмоций других людей",
                    "Способность создавать гармоничные отношения",
                    "Умение поддерживать и утешать",
                    "Развитая интуиция в общении"
                ],
                weaknesses: [
                    "Склонность принимать все близко к сердцу",
                    "Трудности в установлении границ",
                    "Эмоциональное выгорание от чужих проблем",
                    "Излишняя уступчивость"
                ],
                solutions: [
                    "Учитесь устанавливать здоровые границы",
                    "Практикуйте эмоциональную саморегуляцию",
                    "Находите время для восстановления сил",
                    "Развивайте навык говорить 'нет'"
                ]
            },
            "Лидер": {
                description: "Вы уверены в себе, решительны и умеете вдохновлять других. Прирожденный организатор.",
                traits: ["уверенность", "решительность", "амбициозность", "ответственность", "инициативность"],
                strengths: [
                    "Способность вести за собой людей",
                    "Быстрое принятие решений",
                    "Умение брать на себя ответственность",
                    "Энергичность и целеустремленность"
                ],
                weaknesses: [
                    "Склонность к доминированию",
                    "Нетерпимость к ошибкам других",
                    "Трудности в принятии чужого руководства",
                    "Импульсивность в некоторых ситуациях"
                ],
                solutions: [
                    "Учитесь слушать и учитывать мнение других",
                    "Развивайте терпимость к чужим ошибкам",
                    "Практикуйте делегирование полномочий",
                    "Находите баланс между лидерством и сотрудничеством"
                ]
            },
            "Творец": {
                description: "Вы креативны, оригинальны и цените самовыражение. Видите мир под уникальным углом.",
                traits: ["креативность", "оригинальность", "гибкость", "мечтательность", "вдохновенность"],
                strengths: [
                    "Богатое воображение и творческие способности",
                    "Умение находить нестандартные решения",
                    "Гибкость и адаптивность",
                    "Способность вдохновлять других"
                ],
                weaknesses: [
                    "Неорганизованность и непунктуальность",
                    "Сложности с рутинными задачами",
                    "Эмоциональная нестабильность",
                    "Трудности в доведении дел до конца"
                ],
                solutions: [
                    "Создавайте структуру и распорядок дня",
                    "Учитесь планировать и завершать проекты",
                    "Находите баланс между творчеством и дисциплиной",
                    "Развивайте эмоциональную стабильность"
                ]
            },
            "Хранитель": {
                description: "Вы надежны, практичны и цените стабильность. На вас можно положиться в любой ситуации.",
                traits: ["надежность", "практичность", "лояльность", "традиционность", "стабильность"],
                strengths: [
                    "Высокая надежность и ответственность",
                    "Практический подход к решению задач",
                    "Преданность и верность",
                    "Умение создавать стабильность"
                ],
                weaknesses: [
                    "Сопротивление изменениям",
                    "Излишний консерватизм",
                    "Трудности в принятии рисков",
                    "Склонность к рутине"
                ],
                solutions: [
                    "Учитесь принимать и адаптироваться к изменениям",
                    "Пробуйте новые подходы постепенно",
                    "Развивайте гибкость мышления",
                    "Находите баланс между стабильностью и развитием"
                ]
            }
        };

        // Элементы DOM
        const userInfoScreen = document.getElementById('userInfoScreen');
        const testScreen = document.getElementById('testScreen');
        const resultScreen = document.getElementById('resultScreen');
        const historyScreen = document.getElementById('historyScreen');
        const questionsContainer = document.getElementById('questionsContainer');
        const resultContent = document.getElementById('resultContent');
        const historyContent = document.getElementById('historyContent');

        // Кнопки
        const startTestBtn = document.getElementById('startTest');
        const submitTestBtn = document.getElementById('submitTest');
        const viewResultsBtn = document.getElementById('viewResults');
        const newTestBtn = document.getElementById('newTest');
        const backToResultsBtn = document.getElementById('backToResults');
        const clearHistoryBtn = document.getElementById('clearHistory');

        // Текущие данные пользователя
        let currentUser = {};
        let userAnswers = [];

        // Инициализация теста
        function initTest() {
            // Создаем вопросы
            questionsContainer.innerHTML = '';
            testQuestions.forEach((question, index) => {
                const questionElement = document.createElement('div');
                questionElement.className = 'question';
                questionElement.innerHTML = `
                    <h3>${index + 1}. ${question.question}</h3>
                    <div class="options">
                        ${question.options.map((option, optionIndex) => `
                            <label>
                                <input type="radio" name="question${index}" value="${optionIndex}">
                                ${option}
                            </label>
                        `).join('')}
                    </div>
                `;
                questionsContainer.appendChild(questionElement);
            });
        }

        // Расчет нумерологического числа жизненного пути
        function calculateLifePathNumber(birthdate) {
            const date = new Date(birthdate);
            let day = date.getDate();
            let month = date.getMonth() + 1;
            let year = date.getFullYear();
            
            // Функция для сокращения числа до одной цифры (кроме мастер-чисел)
            const reduceNumber = (num) => {
                while (num > 9 && num !== 11 && num !== 22 && num !== 33) {
                    num = Math.floor(num / 10) + (num % 10);
                }
                return num;
            };
            
            // Сокращаем день, месяц и год
            day = reduceNumber(day);
            month = reduceNumber(month);
            year = reduceNumber(year);
            
            // Суммируем и сокращаем итоговое число
            let lifePathNumber = day + month + year;
            lifePathNumber = reduceNumber(lifePathNumber);
            
            return lifePathNumber;
        }

        // Описание нумерологических чисел
        function getNumerologyDescription(number) {
            const descriptions = {
                1: {
                    title: "ЛИДЕР",
                    description: "Вы - прирожденный лидер, новатор и первооткрыватель. Обладаете сильной волей, независимостью и стремлением к достижению целей.",
                    characteristics: ["Самостоятельность", "Инициативность", "Решительность", "Смелость", "Оригинальность"],
                    lifePurpose: "Быть первопроходцем, создавать новое, вдохновлять других своим примером."
                },
                2: {
                    title: "МИРОТВОРЕЦ",
                    description: "Вы - дипломат, чувствительная и тактичная личность. Обладаете даром гармонизации отношений и создания сотрудничества.",
                    characteristics: ["Дипломатичность", "Чувствительность", "Тактичность", "Сотрудничество", "Интуиция"],
                    lifePurpose: "Создавать гармонию, объединять людей, поддерживать баланс в отношениях."
                },
                3: {
                    title: "ТВОРЕЦ",
                    description: "Вы - творческая, оптимистичная и общительная личность. Обладаете художественными талантами и даром самовыражения.",
                    characteristics: ["Креативность", "Коммуникабельность", "Оптимизм", "Талантливость", "Радость жизни"],
                    lifePurpose: "Вдохновлять других, создавать красоту, выражать себя через творчество."
                },
                4: {
                    title: "ПРАКТИК",
                    description: "Вы - надежный, практичный и стабильный человек. Обладаете способностью строить прочные основы и систематизировать процессы.",
                    characteristics: ["Надежность", "Практичность", "Стабильность", "Трудолюбие", "Системность"],
                    lifePurpose: "Создавать прочные структуры, обеспечивать стабильность, воплощать идеи в реальность."
                },
                5: {
                    title: "ИССЛЕДОВАТЕЛЬ",
                    description: "Вы - свободолюбивый, адаптивный и любознательный искатель приключений. Обладаете жаждой разнообразия и новых впечатлений.",
                    characteristics: ["Свободолюбие", "Адаптивность", "Любознательность", "Энергичность", "Многосторонность"],
                    lifePurpose: "Исследовать мир, привносить изменения, наслаждаться свободой и разнообразием жизни."
                },
                6: {
                    title: "ХРАНИТЕЛЬ",
                    description: "Вы - заботливый, ответственный и гармонизирующий человек. Обладаете даром создания уюта и заботы о других.",
                    characteristics: ["Заботливость", "Ответственность", "Гармоничность", "Семейственность", "Служение"],
                    lifePurpose: "Создавать уют и гармонию, заботиться о близких, нести ответственность за других."
                },
                7: {
                    title: "МУДРЕЦ",
                    description: "Вы - аналитик, исследователь и искатель истины. Обладаете глубоким умом и стремлением к познанию скрытых знаний.",
                    characteristics: ["Аналитичность", "Мудрость", "Интуиция", "Самоанализ", "Духовность"],
                    lifePurpose: "Искать истину, анализировать и систематизировать знания, делиться мудростью."
                },
                8: {
                    title: "ОРГАНИЗАТОР",
                    description: "Вы - амбициозный, авторитетный и практичный лидер. Обладаете способностью к организации и материальному успеху.",
                    characteristics: ["Амбициозность", "Организованность", "Практичность", "Авторитетность", "Эффективность"],
                    lifePurpose: "Достигать успеха, организовывать процессы, создавать материальное благополучие."
                },
                9: {
                    title: "ГУМАНИСТ",
                    description: "Вы - сострадательный, альтруистичный и многогранный человек. Обладаете широким кругозором и стремлением помогать человечеству.",
                    characteristics: ["Сострадание", "Альтруизм", "Многогранность", "Терпимость", "Мудрость"],
                    lifePurpose: "Служить человечеству, помогать другим, нести любовь и сострадание."
                },
                11: {
                    title: "ПРОСВЕТИТЕЛЬ",
                    description: "Вы - одухотворенная, интуитивная и вдохновляющая личность. Обладаете повышенной чувствительностью и духовным видением.",
                    characteristics: ["Духовность", "Интуиция", "Вдохновенность", "Чувствительность", "Идеализм"],
                    lifePurpose: "Вдохновлять других, нести духовные истины, быть проводником высших знаний."
                },
                22: {
                    title: "СТРОИТЕЛЬ",
                    description: "Вы - практичный идеалист, мастер-творец, способный воплощать грандиозные планы в реальность.",
                    characteristics: ["Практический идеализм", "Созидательность", "Масштабность", "Реализация", "Воплощение"],
                    lifePurpose: "Строить великие проекты, воплощать масштабные идеи, создавать нечто значимое для человечества."
                },
                33: {
                    title: "УЧИТЕЛЬ",
                    description: "Вы - служитель человечества, сострадательный лидер, несущий высшую степень заботы и любви.",
                    characteristics: ["Служение", "Сострадание", "Любовь", "Руководство", "Просвещение"],
                    lifePurpose: "Учить человечество любви и состраданию, служить высшим идеалам, вдохновлять на духовное развитие."
                }
            };
            
            return descriptions[number] || {
                title: "УНИКАЛЬНАЯ ЛИЧНОСТЬ",
                description: "Вы обладаете уникальной комбинацией качеств и особым предназначением в жизни.",
                characteristics: ["Уникальность", "Многогранность", "Особенность"],
                lifePurpose: "Найти свой уникальный путь и реализовать особое предназначение."
            };
        }

        // Определение типа личности по ответам
        function determinePersonalityType(answers) {
            // Подсчет баллов для каждого типа
            const scores = {
                "Аналитик": 0,
                "Эмпат": 0,
                "Лидер": 0,
                "Творец": 0,
                "Хранитель": 0
            };
            
            // Каждый ответ добавляет баллы определенному типу
            const answerMapping = {
                0: "Аналитик",    // Ответ 0 -> Аналитик
                1: "Эмпат",       // Ответ 1 -> Эмпат
                2: "Лидер",       // Ответ 2 -> Лидер
                3: "Творец",      // Ответ 3 -> Творец
                4: "Хранитель"    // Ответ 4 -> Хранитель
            };
            
            answers.forEach(answer => {
                const type = answerMapping[answer];
                if (type) {
                    scores[type] += 1;
                }
            });
            
            // Находим тип с максимальным количеством баллов
            let maxScore = 0;
            let personalityType = "Аналитик";
            
            for (const [type, score] of Object.entries(scores)) {
                if (score > maxScore) {
                    maxScore = score;
                    personalityType = type;
                }
            }
            
            return personalityType;
        }

        // Сохранение результатов
        function saveResult(user, personalityType, numerologyNumber) {
            let results = JSON.parse(localStorage.getItem('psychTestResults')) || [];
            
            const result = {
                id: Date.now(),
                name: user.name,
                birthdate: user.birthdate,
                gender: user.gender,
                personalityType: personalityType,
                numerologyNumber: numerologyNumber,
                date: new Date().toLocaleString('ru-RU')
            };
            
            results.push(result);
            localStorage.setItem('psychTestResults', JSON.stringify(results));
            
            return result;
        }

        // Показать историю результатов
        function showHistory() {
            const results = JSON.parse(localStorage.getItem('psychTestResults')) || [];
            
            if (results.length === 0) {
                historyContent.innerHTML = '<p>У вас пока нет сохраненных результатов.</p>';
                return;
            }
            
            // Сортируем результаты по дате (новые сверху)
            results.sort((a, b) => b.id - a.id);
            
            historyContent.innerHTML = results.map(result => {
                const numerologyInfo = getNumerologyDescription(result.numerologyNumber);
                return `
                    <div class="result-item">
                        <h3>${result.name} - ${result.date}</h3>
                        <p><strong>Психотип:</strong> ${result.personalityType}</p>
                        <p><strong>Число жизненного пути:</strong> ${result.numerologyNumber} - ${numerologyInfo.title}</p>
                        <p><strong>Описание:</strong> ${numerologyInfo.description}</p>
                    </div>
                `;
            }).join('');
        }

        // Очистка истории
        function clearHistory() {
            if (confirm('Вы уверены, что хотите очистить всю историю результатов?')) {
                localStorage.removeItem('psychTestResults');
                showHistory();
            }
        }

        // Обработчики событий
        startTestBtn.addEventListener('click', () => {
            const name = document.getElementById('userName').value;
            const birthdate = document.getElementById('userBirthdate').value;
            const gender = document.getElementById('userGender').value;
            
            if (!name || !birthdate) {
                alert('Пожалуйста, заполните все поля');
                return;
            }
            
            currentUser = { name, birthdate, gender };
            userInfoScreen.classList.add('hidden');
            testScreen.classList.remove('hidden');
        });

        submitTestBtn.addEventListener('click', () => {
            // Собираем ответы
            userAnswers = [];
            let allAnswered = true;
            
            for (let i = 0; i < testQuestions.length; i++) {
                const selectedOption = document.querySelector(`input[name="question${i}"]:checked`);
                if (selectedOption) {
                    userAnswers.push(parseInt(selectedOption.value));
                } else {
                    allAnswered = false;
                    break;
                }
            }
            
            if (!allAnswered) {
                alert('Пожалуйста, ответьте на все вопросы');
                return;
            }
            
            // Определяем тип личности
            const personalityType = determinePersonalityType(userAnswers);
            const numerologyNumber = calculateLifePathNumber(currentUser.birthdate);
            
            // Сохраняем результат
            const result = saveResult(currentUser, personalityType, numerologyNumber);
            
            // Получаем описания
            const personalityInfo = personalityTypes[personalityType];
            const numerologyInfo = getNumerologyDescription(numerologyNumber);
            
            // Показываем результат
            resultContent.innerHTML = `
                <div class="result-item">
                    <h3>${currentUser.name}, ваш психологический портрет</h3>
                    
                    <h4>🎭 Ваш психотип: ${personalityType}</h4>
                    <p>${personalityInfo.description}</p>
                    
                    <div class="trait-list">
                        ${personalityInfo.traits.map(trait => `<span class="trait">${trait}</span>`).join('')}
                    </div>
                    
                    <h4>✅ Сильные стороны:</h4>
                    ${personalityInfo.strengths.map(strength => `<div class="positive">${strength}</div>`).join('')}
                    
                    <h4>⚠️ Зоны роста:</h4>
                    ${personalityInfo.weaknesses.map(weakness => `<div class="negative">${weakness}</div>`).join('')}
                    
                    <h4>💡 Рекомендации для развития:</h4>
                    ${personalityInfo.solutions.map(solution => `<div class="solution">${solution}</div>`).join('')}
                    
                    <h4>🔮 Ваше число жизненного пути: ${numerologyNumber}</h4>
                    <p><strong>${numerologyInfo.title}</strong></p>
                    <p>${numerologyInfo.description}</p>
                    
                    <h5>Характерные черты:</h5>
                    <div class="trait-list">
                        ${numerologyInfo.characteristics.map(char => `<span class="trait">${char}</span>`).join('')}
                    </div>
                    
                    <h5>Жизненное предназначение:</h5>
                    <p><em>${numerologyInfo.lifePurpose}</em></p>
                    
                    <p><strong>Дата тестирования:</strong> ${result.date}</p>
                </div>
            `;
            
            testScreen.classList.add('hidden');
            resultScreen.classList.remove('hidden');
        });

        viewResultsBtn.addEventListener('click', () => {
            showHistory();
            resultScreen.classList.add('hidden');
            historyScreen.classList.remove('hidden');
        });

        newTestBtn.addEventListener('click', () => {
            userAnswers = [];
            currentUser = {};
            document.getElementById('userName').value = '';
            document.getElementById('userBirthdate').value = '';
            document.getElementById('userGender').value = 'male';
            
            resultScreen.classList.add('hidden');
            userInfoScreen.classList.remove('hidden');
        });

        backToResultsBtn.addEventListener('click', () => {
            historyScreen.classList.add('hidden');
            resultScreen.classList.remove('hidden');
        });

        clearHistoryBtn.addEventListener('click', clearHistory);

        // Инициализация при загрузке
        document.addEventListener('DOMContentLoaded', initTest);
    </script>
</body>
</html>
