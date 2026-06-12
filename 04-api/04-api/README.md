# 🔌 Task Tracker API

## Обзор

REST API для управления задачами и досками.

## Endpoints

| Метод | Endpoint | Описание |
|-------|----------|----------|
| GET | `/boards` | Получить список досок |
| POST | `/boards` | Создать доску |
| GET | `/boards/{id}/cards` | Получить карточки доски |
| POST | `/boards/{id}/cards` | Создать карточку |
| PATCH | `/cards/{id}` | Обновить карточку |

## Примеры

### Создание доски
```bash
POST /boards
{
  "name": "Разработка продукта",
  "description": "Доска для команды разработки"
}
