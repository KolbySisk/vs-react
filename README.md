Author: Kolby Sisk

This project is the optimal way to start a .net core react app. It uses CRA (Create React App) to manage the build configuration.
Learn more about CRA:

+ https://facebook.github.io/react/blog/2016/07/22/create-apps-with-no-configuration.html
+ https://github.com/facebookincubator/create-react-app
+ https://tylermcginnis.com/create-react-app-and-the-future-of-creating-react-applications/

It's built on top of a blank .NET core web application.

<br />

## Dependencies
To get started you need to have

+ git
+ Node & NPM or Yarn (Yarn highly recommended)

<br />

## Getting started
```sh
git clone https://ksisk@git.datausadev.com/scm/data/vs-react-starter.git

cd vs-react-starter\src\react
npm install
npm start
```

Then you can open http://localhost:3000/ to see the app running

<br />

## Building for production
When you’re ready to deploy to production, run `npm run build` from within the `react` folder
This will create a `build` folder. Copy the contents of the `build` folder into the `wwwroot` folder.

Now you can run your project with IIS and see the production environment.

<br />

## Using sass/scss
Using sass or scss requires you to eject from CRA. This means your project will no longer be maintained by CRA, will no longer have access to the CRA CLI tools, and will not get future build config updates. In the future this may not be necessary so do some research before moving on.

```sh
npm install sass-loader node-sass --save-dev
npm run eject
```

Your webpack config will be placed in a config folder. Open it and add a new loader to the beginning of the module loader array:

{
  test: /\.scss$/,
  include: paths.appSrc,
  loaders: ["style", "css", "sass"]
},

Lastly you need to add `/\.scss$/,` to the loaders exclude array.

+ Reference: https://medium.com/@Connorelsea/using-sass-with-create-react-app-7125d6913760#.581wbzn76
+ Learn more about sass-loader: https://github.com/jtangelder/sass-loader
+ Learn more about webpack loaders: https://webpack.github.io/docs/loaders.html