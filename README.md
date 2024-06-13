### Метод: GET /tasks

Описание: Получение списка задач.

Параметры:
- completed (опционально): Булево значение, определяющее, должны ли быть включены завершенные задачи. По умолчанию false.
- date_range (опционально): Строка, представляющая диапазон дат для фильтрации задач по сроку выполнения. По умолчанию пустая строка, что означает отсутствие фильтрации по дате.

Возвращает: Список объектов TaskDTO в формате JSON.

Пример запроса:
GET /tasks?completed=true&date_range=2023-04-01..2023-04-30

### Метод: GET /tasks/{id}

Описание: Получение информации о задаче по идентификатору.

Параметры:
- id: Целое число, идентификатор задачи.

Возвращает: Объект TaskDTO в формате JSON.

Пример запроса:
GET /tasks/1

### Метод: POST /tasks

Описание: Создание новой задачи.

Тело запроса: Объект TaskDTO в формате JSON.

Возвращает: Статус HTTP 200 OK.

Пример запроса:

{
  "title": "Новая задача",
  "description": "Описание задачи",
  "dueDate": "2023-04-30",
  "completed": false
}

### Метод: PATCH /tasks

Описание: Обновление задачи.

Параметры:
- title: Строка, новый заголовок задачи.
- description: Строка, новое описание задачи.
- dueDate: Дата, новый срок выполнения задачи.
- completed: Булево значение, новый статус завершения задачи.

Возвращает: Объект TaskUpdatedDTO в формате JSON.

Пример запроса:

{
  "title": "Обновленная задача",
  "description": "Новое описание задачи",
  "dueDate": "2023-05-01",
  "completed": true
}

### Метод: PATCH /tasks/completed

Описание: Обновление статуса завершения задачи.

Тело запроса: Объект TaskCompleteUpdateDTO в формате JSON.

Возвращает: Объект TaskCompleteUpdateDTO в формате JSON.

Пример запроса:

{
  "title": "Задача с обновленным статусом",
  "completed": true
}

### Метод: DELETE /tasks

Описание: Удаление задачи.

Параметры:
- title: Строка, заголовок задачи, которую нужно удалить.

Возвращает: Статус HTTP 204 NO CONTENT.

Пример запроса:
DELETE /tasks?title=Заголовок
