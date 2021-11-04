+++
title = "Setup PostgreSQL With TypeORM"
tags = [
  "postgres",
  "node.js",
  "sql",
  "typeorm"
]
categories = [
  "PostgreSQL"
]
date = "2021-10-04"
+++

# Setup PostgreSQL With TypeORM
## What is an ORM ?
ORM Stands For Object Relational Mapping Used To Convert Data Between Incompatible Type System Using Object Oriented Programming Languages Like JavaScript, TypeScript, Python
## Popular ORM's
* JavaScript
    - Sequelize
    - Prisma
* TypeScript
    - TypeORM
    - Mikro-ORM
* Python
    - SQLAlchemy
    - Django ORM

## Why TypeORM
If You Know Me, I Am a Big Fan Of TypeScript And I Like Both Mikro-ORM And TypeORM But The Thing With TypeORM That It Is More Of Like TypeScript Syntax. Basically I Like TypeORM Syntax Than Mikro-ORM

## Setting Up TypeORM
* Requirements
    - [Node.js](https://nodejs.org)
    - [NPM](https://npmjs.com)

### Creating A Basic Node.js App
```bash
# NPM
npm init
# Yarn
yarn init
```
### Adding TypeScript
```bash
# NPM
npm install -D typescript @types/node nodemon
# Yarn
yarn add -D typescript @types/node nodemon
```
* Dependencies
    - typescript - Compiler For TypeScript
    - @types/node - Types For Node.js
    - nodemon - Restarts The Server On Changes
    
Open Your package.json And Add Scripts To It
```json
"scripts": {
    "start": "node dist/index.js",
    "dev": "nodemon dist/index.js",
    "watch": "tsc -w"
}
```
Now We Need A tsconfig.json, So Instead Of Typing tsconfig.json From Scratch Let's Generate It
```bash
npx tsconfig.json
```
Select Node.js When Asked To Enter Your Framework

### Run The Application
Create a File src/index.ts And Add This Code To It
```ts
console.log('hello world')
```
Now Open a Terminal And Run watch Command
```bash
# NPM
npm run watch
# Yarn
yarn watch
```
Open Another Terminal And Run dev Command
```bash
# NPM
npm run dev
# Yarn
yarn dev
```
You Should See **hello world**
### Add TypeORM 
```bash
# NPM
npm install typeorm pg reflect-metadata
# Yarn
yarn add typeorm pg reflect-metadata
```
* Dependencies
    - typeorm - Base TypeORM Package
    - pg - Postgres Driver For Node.js
    - reflect-metadata - Required For TypeORM
Now We Can Create A Connection To Our Database
Open src/index.ts and add async connection to typeorm
```ts
import "reflect-metadata"

const main = async () => {
    console.log('hello world')
}

main().catch(err => console.error(err))
```
Now we can use async/await syntax inside main function
we can setting up typeorm connection using two ways:
ormconfig.json
createConnection()
