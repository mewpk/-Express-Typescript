# Express-Typescript
## Create a package.json file
Start by creating a new directory wherever you keep your side projects in your local development environment. Inside that directory, use npm’s initializer command to create a package.json file:


```npm init --yes```

## Installing TypeScript

```npm i -D typescript @types/express @types/node```

The -D flag, also known as the --dev flag, is a specification for the package manager to install these libraries as devDependencies.

## Generating tsconfig.json

```npx tsc --init```

## Create an Express server with a .ts extension

Now, you can easily convert the minimal server code in index.js to an index.ts file.

First, rename the file to index.ts. The .ts extension is a file extension that determines what TypeScript files are compiled to JavaScript files later when we build the server.

Open the index.ts file and modify it, as shown below:

```
import express, { Express, Request, Response } from 'express';
import dotenv from 'dotenv';

dotenv.config();

const app: Express = express();
const port = process.env.PORT;

app.get('/', (req: Request, res: Response) => {
  res.send('Express + TypeScript Server');
});

app.listen(port, () => {
  console.log(`⚡️[server]: Server is running at https://localhost:${port}`);
});
```