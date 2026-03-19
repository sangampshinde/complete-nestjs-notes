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

# Module in NestJS

A module in NestJS is a class marked with the @Module() decorator that groups related parts of an application together.

It is used to organize:
- controllers
- services
- providers
- imports
- exports

You can think of a module as a feature container.


A module in NestJS is a building block that organizes related functionality into one unit.

Step-by-step understanding

Step 1: NestJS app starts from a root module

Every NestJS app has one main module, usually:

```
app.module.ts

```
This is called the root module.

```
import { Module } from '@nestjs/common';
import { AppController } from './app.controller';
import { AppService } from './app.service';

@Module({
  imports: [],
  controllers: [AppController],
  providers: [AppService],
})
export class AppModule {}

```

Step 2: A module is just a class with @Module()

```
import { Module } from '@nestjs/common';

@Module({})
export class UsersModule {}

```

This is the basic structure of a module.

The `@Module()` decorator accepts metadata.

Step 3: Understand the parts inside @Module()

A module usually contains these properties:

```

@Module({
  imports: [],
  controllers: [],
  providers: [],
  exports: [],
})

```
1. controllers
Controllers handle incoming HTTP requests.

```
controllers: [UsersController]

```

This means this module contains the UsersController.

2. providers

Providers usually mean services.
They contain business logic

```
providers: [UsersService]

```

This means this module can use `UsersService`.

3. imports

If one module needs another module, we import it.

```
imports: [AuthModule]

```

This means current module wants to use something from `AuthModule`.

4. exports

If a module wants to share its providers with other modules, it exports them.

```
exports: [UsersService]

```

Now other modules can use `UsersService` after importing `UsersModule`.


Real example step by step

Let us create a `UsersModule`.

Step 1: Generate module

```
nest g module users

```

```
import { Module } from '@nestjs/common';

@Module({})
export class UsersModule {}

```

Step 2: Generate controller

```
nest g controller users
```

Step 3: Generate service

```
nest g service users

```

you complete modules

```
import { Module } from '@nestjs/common';
import { UsersController } from './users.controller';
import { UsersService } from './users.service';

@Module({
  controllers: [UsersController],
  providers: [UsersService],
})
export class UsersModule {}

```


Folder structure of a module

```

src/
  users/
    users.module.ts
    users.controller.ts
    users.service.ts

```


bigger projects

```

src/
  users/
    dto/
      create-user.dto.ts
      update-user.dto.ts
    entities/
      user.entity.ts
    users.module.ts
    users.controller.ts
    users.service.ts

```

Root module and feature module

Root Module
This is the main module of the whole application.

Example:

`AppModule`
`Feature Module`

These are modules for specific features.

Examples:

`UsersModule`
`AuthModule`
`OrdersModule`

Then root module imports them.

Example:
```
import { Module } from '@nestjs/common';
import { UsersModule } from './users/users.module';
import { AuthModule } from './auth/auth.module';

@Module({
  imports: [UsersModule, AuthModule],
})
export class AppModule {}

```

This means:
- app will include users feature
- app will include auth feature


Important CLI commands

Create module:

```
nest g module users
```

Create controller:

```
nest g controller users
```
Create service:

```
nest g service users
```
Create complete resource:

```
nest g resource users
```