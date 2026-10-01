# Restful-Booker API Tests

Тестирование REST API https://restful-booker.herokuapp.com

## Что внутри
- Postman-коллекция: 14 запросов, 41 автотест
- 49 тест-кейсов (позитив + негатив)
- 11 баг-репортов

## Структура
\`\`\`
.
├── postman/
│   ├── Restful-Booker-API-Tests.postman_collection.json
│   └── Restful-Booker-API-Tests.postman_environment.json
├── docs/
│   └── test-cases-and-bugs.xlsx
├── screenshots/
│   └── run-summary.png
└── README.md
\`\`\`

## Как запустить

### Postman
1. Импортировать коллекцию и environment из `postman/`
2. Выбрать окружение `Restful-Booker API Tests`
3. Collection → **Run** → Run `Restful-Booker API Tests`

### Newman
\`\`\`bash
npm install -g newman
newman run postman/Restful-Booker-API-Tests.postman_collection.json \
  -e postman/Restful-Booker-API-Tests.postman_environment.json
\`\`\`

## Результаты прогона
- Тестов: 41
- Passed: 41
- Failed: 0
- Errors: 0

## Найденные баги
11 багов, см. `docs/test-cases-and-bugs.xlsx`. Ключевые:
- **BUG-010** (Critical): 500 Internal Server Error на невалидные запросы
- **BUG-007** (Major): фильтр по checkin/checkout не находит существующие брони
- **BUG-001** (Major): POST /auth возвращает 200 при неверных credentials

## Стек
Postman, Newman, REST, HTTP, RFC 7231/7235