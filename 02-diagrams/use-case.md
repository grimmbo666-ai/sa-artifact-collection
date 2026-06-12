# 🎨 Use Case Diagram

## Actors
- **User** — основной пользователь системы
- **System** — автоматические процессы

## Use Cases

### UC-01: Управление досками
- Создать доску
- Редактировать доску
- Удалить доску
- Пригласить участника

### UC-02: Управление задачами
- Создать карточку
- Редактировать карточку
- Переместить карточку
- Удалить карточку
- Назначить исполнителя

### UC-03: Просмотр и фильтрация
- Фильтровать задачи по исполнителю
- Искать задачи
- Сортировать задачи

## Diagram

```plantuml
@startuml
left to right direction
skinparam packageStyle rectangle

actor User

rectangle "Task Tracker" {
  usecase "Создать доску" as UC1
  usecase "Создать карточку" as UC2
  usecase "Переместить карточку" as UC3
  usecase "Назначить исполнителя" as UC4
  usecase "Фильтровать задачи" as UC5
}

User --> UC1
User --> UC2
User --> UC3
User --> UC4
User --> UC5

UC2 ..> UC4 : include
@enduml
