<!DOCTYPE html>
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
        .hidden {
            display: none;
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
                traits: ["рациональность", "любознательность", "независимость", "критическое мышление"]
            },
            "Эмпат": {
                description: "Вы чувствительны к эмоциям других, заботливы и стремитесь к гармонии в отношениях.",
                traits: ["чувствительность", "заботливость", "дипломатичность", "интуитивность"]
            },
            "Лидер": {
                description: "Вы уверены в себе, решительны и умеете вдохновлять других. Прирожденный организатор.",
                traits: ["уверенность", "решительность", "амбициозность", "ответственность"]
            },
            "Творец": {
                description: "Вы креативны, оригинальны и цените самовыражение. Видите мир под уникальным углом.",
                traits: ["креативность", "оригинальность", "гибкость", "мечтательность"]
            },
            "Хранитель": {
                description: "Вы надежны, практичны и цените стабильность. На вас можно положиться в любой ситуации.",
                traits: ["надежность", "практичность", "лояльность", "традиционность"]
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

        // Расчет нумерологического числа
        function calculateLifePathNumber(birthdate) {
            const date = new Date(birthdate);
            const day = date.getDate();
            const month = date.getMonth() + 1;
            const year = date.getFullYear();
            
            const sumDigits = (num) => {
                let sum = 0;
                while (num) {
                    sum += num % 10;
                    num = Math.floor(num / 10);
                }
                return sum;
            };
            
            let lifePathNumber = sumDigits(day) + sumDigits(month) + sumDigits(year);
            
            while (lifePathNumber > 9 && lifePathNumber !== 11 && lifePathNumber !== 22 && lifePathNumber !== 33) {
                lifePathNumber = sumDigits(lifePathNumber);
            }
            
            return lifePathNumber;
        }

        // Описание нумерологических чисел
        function getNumerologyDescription(number) {
            const descriptions = {
                1: "Лидер, новатор, независимый. Вы обладаете сильной волей и стремитесь к достижению целей.",
                2: "Дипломат, миротворец, чувствительный. Вы цените гармонию и сотрудничество.",
                3: "Творец, оптимист, общительный. Вы обладаете художественными талантами и даром самовыражения.",
                4: "Практик, строитель, надежный. Вы цените стабильность и системный подход.",
                5: "Исследователь, новатор, свободолюбивый. Вы стремитесь к разнообразию и приключениям.",
                6: "Заботливый, ответственный, гармонизатор. Вы стремитесь к служению и созданию уюта.",
                7: "Аналитик, мудрец, искатель истины. Вы цените знания и самоанализ.",
                8: "Организатор, авторитет, амбициозный. Вы стремитесь к успеху и материальному благополучию.",
                9: "Гуманист, альтруист, сострадательный. Вы обладаете широким кругозором и стремитесь помогать другим.",
                11: "Просветитель, вдохновитель, интуитивный. Вы обладаете повышенной чувствительностью и духовностью.",
                22: "Строитель, мастер-творец, практичный идеалист. Вы способны воплощать грандиозные планы в реальность.",
                33: "Учитель, служитель человечества, сострадательный лидер. Вы обладаете высшей степенью заботы о других."
            };
            
            return descriptions[number] || "Уникальная и многогранная личность с особым предназначением.";
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
            answers.forEach((answer, index) => {
                switch(answer) {
                    case 0: scores["Аналитик"] += 1; break;
                    case 1: scores["Эмпат"] += 1; break;
                    case 2: scores["Лидер"] += 1; break;
                    case 3: scores["Творец"] += 1; break;
                    case 4: scores["Хранитель"] += 1; break;
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
            const results = JSON.parse(localStorage.getItem('psychTestResults')) || [];
            const result = {
                id: Date.now(),
                name: user.name,
                birthdate: user.birthdate,
                gender: user.gender,
                personalityType: personalityType,
                numerologyNumber: numerologyNumber,
                date: new Date().toLocaleDateString('ru-RU')
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
            
            historyContent.innerHTML = results.map(result => `
                <div class="result-item">
                    <h3>${result.name} (${result.date})</h3>
                    <p><strong>Психотип:</strong> ${result.personalityType}</p>
                    <p><strong>Число жизненного пути:</strong> ${result.numerologyNumber}</p>
                    <p><strong>Описание по нумерологии:</strong> ${getNumerologyDescription(result.numerologyNumber)}</p>
                </div>
            `).join('');
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
            
            testQuestions.forEach((_, index) => {
                const selectedOption = document.querySelector(`input[name="question${index}"]:checked`);
                if (selectedOption) {
                    userAnswers.push(parseInt(selectedOption.value));
                } else {
                    allAnswered = false;
                }
            });
            
            if (!allAnswered) {
                alert('Пожалуйста, ответьте на все вопросы');
                return;
            }
            
            // Определяем тип личности
            const personalityType = determinePersonalityType(userAnswers);
            const numerologyNumber = calculateLifePathNumber(currentUser.birthdate);
            
            // Сохраняем результат
            const result = saveResult(currentUser, personalityType, numerologyNumber);
            
            // Показываем результат
            resultContent.innerHTML = `
                <div class="result-item">
                    <h3>${currentUser.name}, ваш психологический портрет</h3>
                    <p><strong>Ваш психотип:</strong> ${personalityType}</p>
                    <p>${personalityTypes[personalityType].description}</p>
                    <p><strong>Характерные черты:</strong> ${personalityTypes[personalityType].traits.join(', ')}</p>
                    
                    <p><strong>Ваше число жизненного пути (по нумерологии):</strong> ${numerologyNumber}</p>
                    <p>${getNumerologyDescription(numerologyNumber)}</p>
                    
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

        // Инициализация при загрузке
        document.addEventListener('DOMContentLoaded', initTest);
    </script>
</body>
</html>
