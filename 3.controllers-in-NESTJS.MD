# Controllers in NestJS

A controller in NestJS is the part that receives incoming HTTP requests and returns responses to the client.

Controller handles the request and decides which service method should run.

Why controller is needed ?
When frontend or Postman hits an API like someone has to catch that request. That work is done by the controller. So controller is the entry point of a request inside a module.

A controller in an application typically handles the following responsibilities:

- **Receives request** – entry point for incoming HTTP requests
- **Reads params, query, body, headers** – extracts data from the request
- **Calls service** – delegates business logic to the service layer
- **Returns response** – sends back the appropriate output

Simplified Concept
- **Controller** → request handling  
- **Service** → business logic


How controller is created

```
nest g controller users

```


`users.controller.ts`

```

import { Controller, Get } from '@nestjs/common';

@Controller('users')
export class UsersController {
  @Get()
  findAll() {
    return 'All users';
  }
}

```

`@Controller()`
This decorator marks the class as a controller.

```
@Controller('users')
```
This means all routes inside this controller start with:

`/users`

