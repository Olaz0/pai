# Проект "Node.js API + HTML Frontend + Docker"
![Описание изображения](https://photutorial.com/wp-content/uploads/2023/04/Featured-image-AI-image-generators-by-Midjourney-680x340.png)

## Описание проекта

Проект представляет собой полноценное веб-приложение, включающее в себя Node.js API, HTML фронтэнд, и контейнеризацию с использованием Docker.

## Структура проекта

project-root

│

├── api

│ ├── app.js

│ ├── routes

│ │ ├── apiRoutes.js

│ │ └── ...

│ └── package.json

│

├── frontend

│ ├── index.html

│ ├── styles.css

│ └── scripts.js

│

├── Dockerfile

└── docker-compose.yml


- **api**: Содержит код для Node.js API.
- **frontend**: Содержит HTML файл, стили и скрипты для фронтэнда.
- **Dockerfile**: Файл для создания Docker образа.
- **docker-compose.yml**: Файл для настройки Docker Compose.

## Зависимости

- Node.js
- npm
- Docker

## Установка и Запуск

1. **API:**

    ```bash
    cd api
    npm install
    node app.js
    ```

    API будет доступен по адресу `http://localhost:3000`.

2. **Frontend:**

    Откройте `frontend/index.html` в вашем браузере.

3. **Docker:**

    ```bash
    docker-compose up --build
    ```

    Приложение будет доступно по адресу `http://localhost:8080`.

## API Routes

- **GET /api/data**: Получить данные.
- **POST /api/data**: Отправить данные.

## Frontend

Открыть `frontend/index.html` в браузере для взаимодействия с фронтэндом.

## Docker

Проект поддерживает контейнеризацию через Docker. Вы можете использовать `docker-compose` для легкой установки и запуска.

## Заметки

- Убедитесь, что все зависимости установлены перед запуском приложения.
- Для разработки, вы можете использовать инструменты типа Nodemon для автоматического перезапуска сервера при изменениях в коде.
- Для фронтэнда вы можете использовать сборщики типа Webpack для управления зависимостями и билда.

