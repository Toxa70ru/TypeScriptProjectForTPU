# Task Manager (Node.js + TypeScript)

Универсальный менеджер задач с REST API, web-интерфейсом и CLI.

## Запуск проекта

```sh
npm install
npm run build         # Сборка TypeScript в dist/
npm start             # Запуск сервера (http://localhost:3000)
# Для разработки:
npm run dev           # Автоматический рестарт при изменениях
```

## Web-интерфейс

- Открыть в браузере: [http://localhost:3000](http://localhost:3000)
- Возможности:
  - Просмотр, добавление, удаление, смена статуса задач
  - Фильтрация (все, активные, выполненные)
  - Сортировка (по дате, дедлайну, статусу)
  - Тёмная/светлая тема (переключатель, сохраняется)

## REST API

Базовый URL: `http://localhost:3000/api/tasks`

| Метод | URL              | Описание                  |
|-------|------------------|--------------------------|
| GET   | /tasks           | Получить все задачи       |
| GET   | /tasks/:id       | Получить задачу по ID     |
| POST  | /tasks           | Создать задачу            |
| PUT   | /tasks/:id       | Редактировать задачу      |
| DELETE| /tasks/:id       | Удалить задачу            |

### Примеры запросов

**Создать задачу:**
```sh
curl -X POST http://localhost:3000/api/tasks -H "Content-Type: application/json" -d '{"text":"Купить хлеб","deadline":"2025-09-30"}'
```

**Получить все задачи:**
```sh
curl http://localhost:3000/api/tasks
```

**Изменить статус:**
```sh
curl -X PUT http://localhost:3000/api/tasks/1 -H "Content-Type: application/json" -d '{"status":"Done"}'
```

## CLI

Выполняется через ts-node:

```sh
npx ts-node src/cli.ts list
npx ts-node src/cli.ts add "Текст задачи" "2025-09-30"
npx ts-node src/cli.ts done 1
npx ts-node src/cli.ts delete 1
npx ts-node src/cli.ts filter status=done
```

## Структура проекта

- `src/models` — интерфейсы и типы
- `src/controllers` — логика API
- `src/routes` — маршруты Express
- `src/utils` — работа с файлами
- `src/public` — web-интерфейс (Bootstrap)
- `src/cli.ts` — CLI-интерфейс
- `src/index.ts` — точка входа (Express)

---

**Автор:** (замените на своё имя)
