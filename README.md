## Getting started


### Using `degit`

To create a new Sapper project based on Rollup locally, run

```bash
npx degit "rwildcard/svelte-barcode-scanner" my-app
```

[`degit`](https://github.com/Rich-Harris/degit) is a scaffolding tool that lets you create a directory from a branch in a repository.

Replace `my-app` with the path where you wish to create the project.




### Running the project

Once you have created the project, install dependencies and run the project in development mode:

```bash
cd my-app
npm install # or yarn
npm run dev
```

This will start the development server on [localhost:3000](http://localhost:3000). Open it and click around.


### Using TypeScript

By default, the template uses plain JavaScript. If you wish to use TypeScript instead, you need some changes to the project:

 * Add `typescript` as well as typings as dependences in `package.json`
 * Configure the bundler to use [`svelte-preprocess`](https://github.com/sveltejs/svelte-preprocess) and transpile the TypeScript code.
 * Add a `tsconfig.json` file
 * Update the project code to TypeScript

The template comes with a script that will perform these changes for you by running

```bash
node scripts/setupTypeScript.js
```

`@sapper` dependencies are resolved through `src/node_modules/@sapper`, which is created during the build. You therefore need to run or build the project once to avoid warnings about missing dependencies.

The script does not support webpack at the moment.

## Directory structure

The Project expects to find two directories in the root of your project —  `src` and `static`.


### src

The [src](src) directory contains the entry points for your app — `client.js`, `server.js` and (optionally) a `service-worker.js` — along with a `template.html` file and a `routes` directory.


#### src/routes

This is the heart of your Sapper app. There are two kinds of routes — *pages*, and *server routes*.

**Pages** are Svelte components written in `.svelte` files. When a user first visits the application, they will be served a server-rendered version of the route in question, plus some JavaScript that 'hydrates' the page and initialises a client-side router. From that point forward, navigating to other pages is handled entirely on the client for a fast, app-like feel. (Sapper will preload and cache the code for these subsequent pages, so that navigation is instantaneous.)

