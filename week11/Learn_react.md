# Learning react

How to create a 'Hello World' in React.js

```javascript
import React from 'react';
// This line allows you to use react
import ReactDOM from 'react-dom';
// This allows react to update the DOM

class Test extends React.Component {
// This statment creates an inheritance to React.Component which gives your component access to React.Component functions
  render() {
    return <h1>Hello World!</h1>;
  }
}

ReactDOM.render(<Test />, document.getElementById('root'));
```
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport"
      content="width=device-width, initial-scale=1" />
    <title>React App</title>
  </head>
  <body>

    <div id="root"></div>

  </body>
</html>
```

## Components

Components let you split the UI into independent, reusable pieces and think about each peice in isolation.

## Props

Props stands for properties.

Can be passed like function arguemtns

Props is read-only

Can only be used in a uni-directional flow (parent -> child)

## How to create your first react app

In the command line:
```
npm install -g create-react-app
npx create-react-app myfirstreact
cd myfirstreact
npm start
```

or 

```
create-react-app myproject --use-npm
```

Then go to ```localhost:3000```.

### Super

```javascript
class Car extends React.Component {
  constructor() {
    super();
    // super() executes the parent components constructor function giving access to all the functions of the parent component.
    this.state = {color: "red"};
  }
  render() {
    return <h2>I am a Car!</h2>;
  }
}
```