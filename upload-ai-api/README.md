- npm init -y

- npm i typescript @types/node tsx -D

- npm i fastify

```
import { fastify } from "fastify";

const app = fastify();

app.get("/", () => {
  return "Hello World";
});

app.listen({
  port: 3333,
});
```

- curl http://localhost:3333

- Rest Client => vscode extension

- npm i prisma -D
- npx prisma init --datasource-provider sqlite

Prisma vscode extension
settings json prisma format on save true

```
  "[prisma]": {
    "editor.defaultFormatter": "Prisma.prisma",
    "editor.formatOnSave": true
  }
```

serviços para upload de arquivos
amazon s3
cloudfare r2

depois de criar o schema no prisma
npx prisma migrate dev
colocar uma descrição ex.: create videos and prompts

visualizar o banco
npx prisma studio

enviar arquivos semelhante ao multer do express
npm i @fastify/multipart

npm i zod

npm i openai

npm i dotenv -D

npm i @fastify/cors

npm i ai

seed.ts => colocar dentro da pasta do prisma
adicionar no package.json

```
  "prisma": {
    "seed": "tsx prisma/seed.ts"
  },
```

npx prisma db seed
