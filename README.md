# Docker сборка nuxt & bitrix

# Инструкция

## Установка
1. git pull
2. `docker-compose -d --profile backend up --build`
3. Установить bitrix через `bitrixsetup.php` в `/www/`
```
Доступы к бд
host: db
db: bitrix
login: bitrix
password: 123
```
4. Если nuxt проекта ещё нет, нужно создать его и разместить в `/www/frontend/app`.
5. Затем пересобрать проект с frontend `docker-compose -d up --build`.

<br>

Дирректива `--build` используется для пересборки. <br>
Дирректива `-d` используется для запуска в режиме демона

1. Для запуска всего приложения:
```
docker-compose -d up --build
```

2. Для запуска только backend:
```
docker-compose -d --profile backend up --build
```

## Структура
```
├── compose.yaml
├── frontend
│   └── dockerfile
├── mysql
│   └── 8.0
├── nginx
│   ├── conf
│   ├── dockerfile
│   └── nginx.conf
├── php
│   └── 8.3
├── www
│    ├── bitrix
│    ├── local
│    ├── upload
│    ├── frontend
│    │   ├── .dockerignore
│    │   └── app
│    │        ├── .nuxt
│    │        │   ├── app.config.mjs
│    │        │   ├── components.d.ts
│    │        │   ├── dev
│    │        │   ├── dist
│    │        │   ├── imports.d.ts
│    │        │   ├── manifest
│    │        │   ├── nitro.json
│    │        │   ├── nuxt.d.ts
│    │        │   ├── nuxt.json
│    │        │   ├── schema
│    │        │   ├── tsconfig.json
│    │        │   ├── tsconfig.server.json
│    │        │   └── types
│    │        ├── .output
│    │        │   └── public
│    │        ├── README.md
│    │        ├── app.vue
│    │        ├── node_modules
│    │        ├── nuxt.config.ts
│    │        ├── package-lock.json
│    │        ├── package.json
│    │        ├── public
│    │        │   ├── favicon.ico
│    │        │   └── robots.txt
│    │        ├── server
│    │        │   └── tsconfig.json
│    │        └── tsconfig.json
```

- `/www/bitrix/` - ядро битрикса 
- `/www/frontend/app/` - фронт на nuxt.js