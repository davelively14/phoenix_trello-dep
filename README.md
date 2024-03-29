# PhoenixTrello

This is my version of the tutorial, [Trello tribute with Phoenix and React](http://codeloveandboards.com/blog/2016/01/04/trello-tribute-with-phoenix-and-react-pt-1/), by Ricardo Garcia Vega on his Code, Love and Boards blog.

## Modifications

I did not use the no-brunch option. Instead, I used the installation as laid out in another tutorial, [ReactPx](https://github.com/davelively14/reactpx).  I did add the other front end packages from npm listed under 'Front-end Basic Structure' on part 2 of the tutorial.

### React install instructions

#### npm builds
Install the build files from npm.  From the command line in the main path directory of the project:

```
$ npm install --save react react-dom babel-preset-react
```

#### [brunch-config.js](/brunch-config.js)
Open the `brunch-config.js` file and add the `presets:` array to the `babel` block in `plugins`:
```javascript
plugins: {
  babel: {
>   presets: ["es2015", "react"],
    ignore: [/web\/static\/vendor/]
  }
},
```

In the same file, add the `whitelist:` array in the npm block:
```javascript
npm: {
  enabled: true,
> whitelist: ["phoenix", "phoenix_html", "react", "react-dom"]
}
```

#### [app.js](/web/static/js/app.js)
Open the `app.js` file and add the following to the end of the file:
```javascript
import React from "react"
import ReactDOM from "react-dom"
```

#### Confirm installation
```
$ brunch build
```

### Other package installation

One of the packages, redux-simple-router, has been deprecated. Instead, use `react-router-redux`.  Here's the list of other npm packages we installed:

```
npm install --save react-router react-router-redux bourbon bourbon-neat history
```
