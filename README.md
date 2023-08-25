## Setup

Make sure to install the dependencies:

```bash
npm install

npm run  dev
```

## Pronlem

The problem is that Nuxt 3 users are not able to use the library because it fails internally in the method sdk.connectInjected(). That means, if you’re using the popular framework Nuxt, you can’t use Ronin.

Here are some of the errors it throws:

![Screenshot 2023-08-24 at 2 12 33 PM](https://github.com/pausanchezv/ronin-nuxt-bug/assets/16424328/57745421-fbc8-41c4-ac15-16f1643588bb)

And as soon as we click on one of them we see it’s trying to pick something it cannot find:

*Could not load content for http://localhost:3000/_nuxt/node_modules/.cache/vite/client/deps/null (HTTP error: status code 504, net::ERR_HTTP_RESPONSE_CODE_FAILURE)*

It is important to notice that Nuxt uses Vite underneath and that’s exactly what’s failing (note that in raw Vue 3 the whole thing behaves as expected).


