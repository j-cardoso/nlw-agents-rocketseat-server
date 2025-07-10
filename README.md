# NLW Agents - Server

Backend do projeto **NLW Agents** desenvolvido durante o evento NLW (Next Level Week) da Rocketseat.

## 🚀 Tecnologias

- **Node.js** - Runtime JavaScript
- **TypeScript** - Linguagem de programação
- **Fastify** - Framework web
- **Drizzle ORM** - ORM para PostgreSQL
- **PostgreSQL** - Banco de dados (com pgvector)
- **Zod** - Validação de schemas
- **Docker** - Containerização

## 📋 Pré-requisitos

- Node.js 18+
- Docker e Docker Compose
- PostgreSQL (via Docker)

## ⚙️ Configuração

1. **Clone o repositório**

```bash
git clone <repository-url>
cd server
```

2. **Instale as dependências**

```bash
npm install
```

3. **Configure as variáveis de ambiente**
   Crie um arquivo `.env` na raiz do projeto:

```env
PORT=3333
DATABASE_URL=postgresql://docker:docker@localhost:5432/agents
```

4. **Inicie o banco de dados**

```bash
docker-compose up -d
```

5. **Execute as migrações**

```bash
npx drizzle-kit migrate
```

6. **Popule o banco (opcional)**

```bash
npm run db:seed
```

## 🏃‍♂️ Executando o projeto

**Desenvolvimento:**

```bash
npm run dev
```

**Produção:**

```bash
npm start
```

O servidor estará disponível em `http://localhost:3333`

## 📁 Estrutura do Projeto

```
src/
├── db/
│   ├── schema/          # Schemas do banco (Drizzle)
│   ├── migrations/      # Migrações do banco
│   └── connection.ts    # Conexão com banco
├── http/
│   └── routes/          # Rotas da API
├── env.ts              # Configuração de variáveis
└── server.ts           # Servidor principal
```

## 🛠️ Scripts Disponíveis

- `npm run dev` - Executa em modo desenvolvimento com hot reload
- `npm start` - Executa em modo produção
- `npm run db:seed` - Popula o banco com dados iniciais

## 📝 Padrões de Projeto

- **TypeScript** para tipagem estática
- **Drizzle ORM** para queries type-safe
- **Zod** para validação de dados
- **Fastify** com type provider para APIs tipadas
- **Biome** para formatação e linting
- **Docker** para ambiente de desenvolvimento
