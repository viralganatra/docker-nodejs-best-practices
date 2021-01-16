<div align="center">
<h1>Docker Node.js best practices 🐳 📦</h1>
<p>Docker Node.js development to production best practices with security in mind.</p>
</div>

<hr />

## What is this?

This is a set of good defaults and best practices when working with Node.js and Docker.

## Advantages for dev

* **Efficient images** - Only NPM packages are installed inside the container.
* **Zero config startup** - Use abstracted commands to build and start your app.
* **Debugging support** - Node runs with the inspect flag on the standard port (9229).
* **Easy local/Docker development** - Ability to run your app both within Docker and locally without conflicts with NPM packages.
* **Nodemon** - Automatically restart Node on file changes.
* **Edit locally while running Docker** - Source code is bind mounted into the container.
* **Configurable environment variables** - Edit the `.env` file to customise your app.

## Advantages for prod

* **Single place to upgrade Node.js version** - Node.js version declared once which is shared across all environments
* **Only prod dependencies** - No dev dependencies included in the final prod image.
* **Correct NODE_ENV** - `NODE_ENV` defaults to production both at build time and runtime.
* **Proper shutdown** - Graceful shutdown of Node.js using [stoppable](https://github.com/hunterloftis/stoppable).
* **Security** - Node runs as the user `node` rather than `root`.
* **Multi stage builds** - Single Dockerfile for dev/test and prod images.
* **Testability** - Separate test image for testing in a CI environment.

## Getting started

1. Clone this repo
1. Run `make build-dev` followed by `make start` to build and run the application
1. Visit http://localhost:3000 in your browser

## License

[MIT](LICENSE)
