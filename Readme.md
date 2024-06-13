# Creating and Sharing React Components with TypeScript and CSS
This is a template you can use to create react components that you can share over npm install.

# Prerequisites
* Node.js and npm installed
Basic knowledge of React
An NPM account


1. Set Up Your Project:
Create a local Node.js package directory using `npm init`.
Initialize a Git repository using `git init` and commit your code.
Create a `src` folder and add your components.

Clone this repository using 
`git clone https://github.com/denisekhuu/react-component-base.git`

```bash
mycomponent
├── src/
├── package.json
├── tsconfig.json
└── webpack.config.js
```

In package.json, change the following configurations to your liking

```json
{
  "name": <package-name>,
  "version": "1.0.0",
  "description": "",
  "main": "dist/index.js",
  "types": "dist/types/index.d.ts",
  "scripts": {
    "build": "webpack --config webpack.config.js"
  },
  "keywords": [],
  "author": <your-name>,
  "license": <preferred-licence>,
  "devDependencies": {
    "css-loader": "^7.1.2",
    "style-loader": "^4.0.0",
    "ts-loader": "^9.5.1",
    "typescript": "^5.4.5",
    "webpack": "^5.92.0",
    "webpack-cli": "^5.1.4"
    ...
  },
  "dependencies": {
    "@types/react": "^18.3.3",
    "@types/react-dom": "^18.3.0",
    "react": "^18.3.1",
    "react-dom": "^18.3.1"
    ...
  }
}

```

2. Add Your React Component: Add your component code to the `src` file and add your needed dependencies.

# Test Locally

```bash
mycomponent
├── src/
├── package.json
├── tsconfig.json
└── webpack.config.js

my-react-app
├── src/
...

1. Install the needed Dependencies

  > If we want to use npm link, we need to make sure that react is not included a second time in our dependencies. This is important to avoid bundling multiple versions of React, which can cause issues such as useState not being found. Therefore, run the following to omit them. 

`npm install --production --omit=peer` 



2. Inside your package-folder, use `npm link` to test your package locally. This command allows you to expose your package and use it in local projects as if it were downloaded from npm

`npm link`


3. Inside your react app, run 

`npm link <my-component-name>` 

```typescript
import React from 'react';
//import { Button } from '../../src/index';
import { Button } from 'eta-base';

import './App.css';

function App() {
  const handleClick = () => {
    console.log('Button clicked!');
  };

  return (
    <div className="App">
      <Button text="Click me" onClick={handleClick} />
    </div>
  );
}

export default App;
```


Start your App to see your component

```bash
npm start
```

For a tutorial how to create the base from scratch:
https://github.com/denisekhuu/denisekhuu.github.io/blob/main/tutorials/create-a-react-component.md
