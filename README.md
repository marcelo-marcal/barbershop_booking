# barbershop_booking
Agendamento de Serviços em Barbearia


## Getting Started

First, run the development server:

`npx create-next-app@latest`

```
What is your project named? my-app
*(Qual é o nome do seu projeto?) my-app*

Would you like to use TypeScript? No / Yes = Yes
*(Você gostaria de usar TypeScript?) Não / Sim*

Would you like to use ESLint? No / Yes = Yes
*(Você gostaria de usar ESLint?) Não / Sim*

Would you like to use Tailwind CSS? No / Yes = Yes
*(Você gostaria de usar Tailwind CSS?) Não / Sim*

Would you like to use `src/` directory? No / Yes = No
*(Você gostaria de usar o diretório `src/`?) Não / Sim*

Would you like to use App Router? (recommended) No / Yes = Yes
*(Você gostaria de usar o App Router?) [Recomendado] Não / Sim*

Would you like to customize the default import alias? No / Yes = No
*(Você gostaria de personalizar o alias de importação padrão?) Não / Sim*

What import alias would you like configured? @/*
*(Qual alias de importação você gostaria de configurar?) @/*
```


```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/basic-features/font-optimization) to automatically optimize and load Inter, a custom Google Font.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.

### .env
`DATABASE_URL=mysql://user:password@localhost:3306/dbname`

### Configuração do Prisma: 
`schema.prisma`
```
generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "mysql"
  url      = env("DATABASE_URL")
}
```

### Remova o Diretório Atual de Migração:
`rm -rf prisma/migrations`

### Inicie uma Nova Migração:
`npx prisma migrate dev`

### Reinicie o Servidor:
`yarn dev`


### Prisma & Supabase
##### - Configuração do Supabase
`https://supabase.com/`
    - Criar uma conta e uma organização
    - Ir para *Project Settings → Database* e copiar ***connection string***
    - Colar *connection string* no `.env` com a sua senha
  
`npx prisma db push`

### API Key do Google

Acessar [Google Developers Console](https://console.cloud.google.com/) e criar um projeto.  Ao criá-lo, selecioná-lo e ir em ***Menu → Credenciais → ID do Cliente OAuth***. Configurar as telas de consentimento e colocar a seguinte URL como ***URL de Redirecionamento:***

[`http://localhost:3000/api/auth/callback/google`](http://localhost:3000/api/auth/callback/google)

Após isso, pegar as chaves geradas e colocar no `.env` do projeto.