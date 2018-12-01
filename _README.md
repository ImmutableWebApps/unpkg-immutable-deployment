# unpkg-immutable-deployment

This repository is a supplement to [unpkg-immutable-example](https://github.com/ImmutableWebApps/unpkg-immutable-example). It is configured with GitHub Pages to deploy to https://immutablewebapps.org/unpkg-immutable-deployment/.

## Deployment Manifest

This is an [Immutable Web App](https://immutablewebapps.ord). The HTML is 100% configuration. The HTML contains all of the environment-specific values. All of the referenced assets are versioned, they contain no environment-specific values, and they are hosted externally.

Any published changes to this HTML is an atomic deployment of the Immutable Web App.

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>unpkg-immutable-example</title>
    <base href="/unpkg-immutable-example/">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <!-- versioned static assets -->
    <link rel="icon" type="image/x-icon" href="https://unpkg.com/@immutablewebapps/unpkg-immutable-example@0.0.5/dist/favicon.ico">
    <link rel="stylesheet" href="https://unpkg.com/@immutablewebapps/unpkg-immutable-example@0.0.5/dist/styles.css">

    <!-- environment variables -->
    <script>
      env = {
          production: true,
          color: "#F0FFF0"
      };
    </script>
  </head>
  <body>
    <!-- application binding -->
    <app-root></app-root>
    
    <!-- versioned static assets -->
    <script type="text/javascript" src="https://unpkg.com/@immutablewebapps/unpkg-immutable-example@0.0.5/dist/runtime.js"></script>
    <script type="text/javascript" src="https://unpkg.com/@immutablewebapps/unpkg-immutable-example@0.0.5/dist/polyfills.js"></script>
    <script type="text/javascript" src="https://unpkg.com/@immutablewebapps/unpkg-immutable-example@0.0.5/dist/main.js"></script>
  </body>
</html>
```

## `404.html`

The HTML file is called `404.html` to handle single-page app routing by using a [custom 404 page](https://help.github.com/articles/creating-a-custom-404-page-for-your-github-pages-site/)