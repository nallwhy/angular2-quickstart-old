# angular2-quickstrat
Simple Angular2 project quickstart guide

## Setting
- npm
```
npm init -y
npm i angular2 systemjs --save --save-exact
npm i typescript live-server --save-dev
```

- ./package.json
```javascript
{
  ...
  "scripts": {
    "tsc": "tsc -p src -w",
    "start": "live-server --open=src"
  }
  ...
}
```

- create folder
```
mkdir -p src/app
```

- ./src/index.html
```html
<html>
  <head>
    <script src="../node_modules/systemjs/dist/system.src.js"></script>
    <script src="../node_modules/angular2/bundles/angular2.dev.js"></script>
    <script>
      System.config({
        packages: {'app': {defaultExtension: 'js'}}
      });
      System.import('app/app');
    </script>
  </head>
  <body>
    <my-app>Loading</my-app>
  </body>
</html>
```

- ./src/tsconfig.json
```json
{
  "compilerOptions": {
    "target": "ES5",
    "module": "commonjs",
    "sourceMap": true,
    "emitDecoratorMetadata": true,
    "experimentalDecorators": true,
    "removeComments": false,
    "noImplicitAny": false
  }
}
```

- ./src/app/app.ts
```javascript
import {bootstrap, Component} from 'angular2/angular2';

@Component({
  selector: 'my-app',
  template: '<h1>My First Angular 2 App</h1>'
})
class AppComponent {}

bootstrap(AppComponent);
```

## Run
```
npm run tsc
npm start
```
