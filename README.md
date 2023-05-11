# greenwood-demo-platform-fly

A demonstration repo for using Greenwood on a server using the [hosting platform **Fly.io**](https://fly.io/).


## Setup
1. Clone this repository
1. Run `npm ci`
1. Run `npm run develop` to start the dev server

## Demo

The main demo is hosted at [https://restless-river-5040.fly.dev](https://restless-river-5040.fly.dev).  
- [`/`](https://restless-river-5040.fly.dev) - Home page that demonstrates the below API routes
- [`/artists`](https://restless-river-5040.fly.dev) - Artists page that makes a backend `fetch` call to render SSR artists data on the page
- [`/api/greeting?name{xxx}`](https://restless-river-5040.fly.dev/api/greeting) - An API that returns a JSON response and optionally uses the `name` query param for customization.  Otherwise returns a default message.
- [`/api/fragment`](https://restless-river-5040.fly.dev//api/fragment) - An API for returning fragments of server rendered Web Components as HTML, that are then appended to the DOM.  The same card component used in SSR also runs on the client to provide interactivity, like event handling.


## Self Hosting

Below is how to self host your own Greenwood app on Fly.io.

### Greenwood Configuration
First make a couple changes to your Greenwood project
1. Have the following npm scripts setup in your _package.json_
    ```json
    "scripts": {
      "...": "...",
      "build": "greenwood build",
      "start": "greenwood serve"
    }
    ```
1. Make sure **@greenwood/cli** package is a dependency in your _package.json_
    ```json
    "dependencies": {
      "@greenwood/cli": "~0.28.2"
    }
    ```

### Commands

Following [this guide](https://fly.io/docs/languages-and-frameworks/node/), after [installing](https://fly.io/docs/hands-on/install-flyctl/) and [logging into the Fly CLI](https://fly.io/docs/getting-started/log-in-to-fly/), do the following:
1. Run `fly launch`
1. Run `fly deploy`

That's it! 🎉