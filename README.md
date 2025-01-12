# Docker сборка nuxt & bitrix

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

`/www/bitrix/` - ядро битрикса
`/www/frontend/app/` - фронт на nuxt.js