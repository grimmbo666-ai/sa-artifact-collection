# 🔄 Sequence Diagram: Создание карточки задачи

## Участники
- **User** — пользователь
- **Frontend** — веб-интерфейс
- **Backend** — серверная часть
- **Database** — база данных

## Диаграмма

```plantuml
@startuml
autonumber
actor User
participant "Frontend" as Frontend
participant "Backend API" as Backend
database "Database" as DB

User -> Frontend: Нажимает "Добавить карточку"
Frontend -> Frontend: Открывает форму создания

User -> Frontend: Вводит данные (название, описание)
Frontend -> Backend: POST /api/cards\n{title, description, deadline}

activate Backend
Backend -> Backend: Валидация данных
Backend -> DB: INSERT INTO cards\nVALUES (...)
DB --> Backend: ID созданной карточки
Backend --> Frontend: 201 Created\n{card_id, status}
deactivate Backend

Frontend -> Frontend: Обновляет доску
Frontend --> User: Показывает новую карточку
@enduml
