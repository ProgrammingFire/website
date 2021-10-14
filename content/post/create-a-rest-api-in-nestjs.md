+++
title = "Create A REST API In NestJS"
description = "Learn Nest.js By Creating A REST API. Nest.js Is A Node.js Framework For Building Server Side Applications.The reason why i like nest.js is because the code is organized a lot in diffrent modules, controllers and services"
tags = [
  "video",
  "nestjs",
  "api",
  "project"
]
date = "2021-10-09"
+++

{{< youtube q488cm7UQIo >}}

## Learn Nest.js By Creating A REST API

### Nest.js Is A Node.js Framework For Building Server Side Applications

The reason why i like nest.js is because the code is organized a lot in diffrent modules, controllers and services

### Creating A New Application In Nest.js

Installing Nest.js CLI:

```bash
npm install -g @nestjs/cli
```

Creating New Application:

```bash
nest new my-api
```

Choose Your Preferred Package Manager

### Start The Application

Go To `my-api` Folder Using `cd` Command

```bash
cd my-api
```

Run The Application In `Production`:

```bash
npm run start
```

Run The Application In `Developement`:

```bash
npm run start:dev
```

### Testing The API

For Testing Out API We Use Something Like `Postman`, `Curl` Or `Thunder Client`. For This Tutorial We Are Going To Use `Thunder Client`

Let's Test Our `Hello World` Endpoint That Comes With Nest.js Sample API

```http
GET http://localhost:3000/
```

**Output**:

```json
Hello World
```

Folder Structure

```
├── src
│ ├── main.ts
│ └── app.controller.ts
│ ├── app.controller.spec.ts
│ ├── app.module.ts
│ └── app.service.ts
```

Here's a brief overview of those core files:
| File Name | File Description
| ------------------------ | ------------------------------------------------------------------------------------------------------------------- |
| `app.controller.ts` | A basic controller with a single route. |
| `app.controller.spec.ts` | The unit tests for the controller. |
| `app.module.ts` | The root module of the application. |
| `app.service.ts` | A basic service with a single method. |
| `main.ts` | The entry file of the application which uses the core function `NestFactory` to create a Nest application instance. |

Let's Just Change The `app.controller.ts` File:

```ts
// Before
@Get() // GET /
getHello() {
	return "Hello World"
}

// After
@Get("hello") // GET /hello
getHello() {
	return "Hello World"
}
```
