# INTRODUCTION

NestJS is a progressive Node.js framework used to build scalable, maintainable, and enterprise-level backend applications.

NestJS is a structured backend framework for Node.js that helps developers build scalable server-side applications using TypeScript, modular architecture, dependency injection, and decorators inspired by Angular.

⚡ Core Features of NestJS
- 1.TypeScript First
- 2.Modular Architecture
- 3.Dependency Injection
- 4.Decorator Based Programming
- 5.Supports Enterprise Patterns
   - ✅ Microservices
   - ✅ WebSockets
   - ✅ GraphQL
   - ✅ Kafka / RabbitMQ
   - ✅ Authentication (JWT, Passport)
   - ✅ Caching
   - ✅ Validation
   - ✅ Guards / Interceptors / Pipes
- 6.Works with Databases Easily
    NestJS integrates with:
    - PostgreSQL
    - MySQL
    - MongoDB
    - Redis
    Using ORMs like:
    - TypeORM
    - Prisma
    - Sequelize



# Setting up NestJS Environment (Step by Step)

⭐ Step 1 — Install Node.js
- ✅ Node 18+ or 20+

⭐ Step 2 — Install Nest CLI

```
npm install -g @nestjs/cli

```

```
nest -v

```

⭐ Step 3 — Create New Nest Project

```
nest new my-nest-app

```

⭐ Step 4 — Go inside Project

```
cd my-nest-app

```

⭐ Step 5 — Run Application

```
npm run start:dev

```

# NestJS Files and Folder Structure

📁 Root Level Structure
```
my-app/
│
├── node_modules/
├── src/
├── test/
├── package.json
├── tsconfig.json
├── nest-cli.json
└── README.md

```

⭐ node_modules/
Contains all installed packages.

⭐ package.json
Contains:
- dependencies
- scripts
- project info

⭐ nest-cli.json
Nest CLI configuration file.
Defines:
- source folder
- compiler options

⭐ tsconfig.json
TypeScript configuration.

Controls:
- compilation
- strict mode
- module system

⭐ MOST IMPORTANT → src Folder
This is where REAL development happens.
```
src/
│
├── main.ts
├── app.module.ts
├── app.controller.ts
├── app.service.ts

```

🔥 main.ts (Entry Point)

This file starts your NestJS server.
Node starts → main.ts runs → server starts.


```
async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  await app.listen(3000);
}
bootstrap();

```

🔥 app.module.ts (Root Module)
This is the heart of NestJS app.
All modules are connected here.

```
@Module({
  imports: [],
  controllers: [AppController],
  providers: [AppService],
})
export class AppModule {}

```

🔥 app.controller.ts (Handles Requests)

Controller handles:
- GET
- POST
- PUT
- DELETE

```
@Controller()
export class AppController {

  @Get()
  getHello() {
    return "Hello";
  }

}

```

🔥 app.service.ts (Business Logic)
Service contains logic.

```
@Injectable()
export class AppService {
  getHello() {
    return "Hello";
  }
}

```




