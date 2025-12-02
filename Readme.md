# Upload Server

A high-performance image upload server built with modern web technologies and cloud storage integration.

## 🚀 Tech Stack

- **Runtime**: Node.js 22 with ESM modules
- **Framework**: [Fastify](https://www.fastify.io/) - Fast and low overhead web framework
- **Database**: PostgreSQL with [Drizzle ORM](https://orm.drizzle.team/)
- **Validation**: [Zod](https://zod.dev/) - TypeScript-first schema validation
- **Cloud Storage**: AWS S3 integration
- **API Documentation**: Swagger/OpenAPI with automatic schema generation
- **Testing**: Vitest
- **Code Quality**: Biome (linter & formatter)
- **Type System**: TypeScript 5.7

## 📋 Prerequisites

- Node.js 22+
- Docker & Docker Compose
- npm or yarn

## 🛠️ Installation

```bash
npm install
```

## 🗄️ Database Setup

Start the PostgreSQL database:

```bash
docker-compose up -d
```

Generate and apply migrations:

```bash
npm run db:generate
npm run db:migrate
```

## 📝 Environment Variables

Create a `.env` file based on `.env`:

```env
PORT=3333
NODE_ENV=development
DATABASE_URL="postgresql://docker:docker@localhost:5432/upload"
```

For testing, create a `.env.test` file with test database credentials.

## 🏃 Running

**Development mode** (with auto-reload):

```bash
npm run dev
```

**Production build**:

```bash
npm run build
```

## 🧪 Testing

Run tests:

```bash
npm test
```

Watch mode:

```bash
npm run test:watch
```

## 📚 API Documentation

Once the server is running, access the interactive API docs at:

```
http://localhost:3333/docs
```

## 💾 Database Management

- **Drizzle Studio** (visual database manager):

  ```bash
  npm run db:studio
  ```

- **Generate migrations** after schema changes:

  ```bash
  npm run db:generate
  ```

- **Migrate test database**:
  ```bash
  npm run db:migrate:test
  ```

## 📦 Project Structure

```
src/
├── env.ts                          # Environment validation
├── infra/
│   ├── db/
│   │   ├── index.ts               # Database connection
│   │   ├── schemas/               # Drizzle table definitions
│   │   └── migrations/            # SQL migrations
│   └── http/
│       ├── server.ts              # Fastify server setup
│       ├── transform-swagger-schema.ts
│       └── routes/                # API endpoints
```

## 🚢 Docker

The project includes a `docker-compose.yml` for PostgreSQL setup with automatic initialization via `docker/init.sql`.

## 📄 License

ISC
