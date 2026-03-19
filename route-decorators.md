# route decorators in NestJS

Route decorators in NestJS are used to connect an HTTP request to a controller method.

A route decorator tells NestJS which HTTP method and which route URL should call a particular function.

Common Route Decorators in NestJS

NestJS provides decorators to define routes inside a controller:

- **@Get()** – Handle HTTP GET requests
- **@Post()** – Handle HTTP POST requests
- **@Put()** – Handle HTTP PUT requests
- **@Patch()** – Handle HTTP PATCH requests
- **@Delete()** – Handle HTTP DELETE requests

```typescript
import { Controller, Get, Post, Put, Patch, Delete } from '@nestjs/common';

@Controller('users')
export class UsersController {
  @Get()
  findAll() {
    return 'Retrieve all users';
  }

  @Post()
  create() {
    return 'Create a new user';
  }

  @Put(':id')
  update() {
    return 'Update user by ID';
  }

  @Patch(':id')
  partialUpdate() {
    return 'Partially update user by ID';
  }

  @Delete(':id')
  remove() {
    return 'Delete user by ID';
  }
}