# WHAT IS REST API ?

A REST API is a way for two applications to talk to each other over `HTTP` using standard methods like:

## HTTP Methods

- **GET** – Retrieve data from the server
- **POST** – Send new data to the server
- **PUT** – Update/replace existing data
- **PATCH** – Partially update existing data
- **DELETE** – Remove data from the server


Full form:

`REST` = Representational State Transfer
`API` = Application Programming Interface

A REST API is a set of rules that allows frontend and backend, or one system and another system, to communicate using HTTP requests and responses.


REST API follows some rules / principles.
These are called REST constraints.

There are mainly 6 properties of REST API.

⭐ 1. Client – Server Architecture
Frontend and Backend are separate systems.

⭐ 2. Stateless (VERY IMPORTANT)
Stateless means:
Server does not store client session or previous request memory.
Every request must contain all required information.

⭐ 3. Cacheable
REST responses can be cached.
This means:
If data does not change frequently, client or proxy can store response.

⭐ 4. Uniform Interface
REST APIs must follow consistent structure.

⭐ 5. Layered System
REST allows multiple layers between client and server.

⭐ 6. Code on Demand (Optional Property)
This is optional.
Server can send executable code to client.
