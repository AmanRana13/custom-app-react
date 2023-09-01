# Create your own Create React App Template

Create React App is a convienient way to start building a new single-page application in React. Your app only needs one build dependency `react-scripts`. Under the hood it uses webpack, Babel, ESLint, and other amazing projects to power your app.

## Make it your own

If you don't like the default scaffold of create react app it really easy to adjust.

- Start by creating a folder called `cra-template`.

- Cd into the folder and run `yarn init -y` or `npm init -y` if your prefer npm. This will generate a basic `package.json` file for you.

- Create a `template.json` with your specific template settings. Any dependencies you add here will be added to the final dependency list.

```json
{
  "package": {
    "dependencies": {
      "@emotion/react": "^11.11.1",
      "@emotion/styled": "^11.11.0",
      "@mui/material": "^5.14.7",
      "@reduxjs/toolkit": "^1.9.5",
      "@testing-library/jest-dom": "^5.17.0",
      "@testing-library/react": "^11.2.7",
      "@testing-library/user-event": "^12.8.3",
      "@types/jest": "^26.0.24",
      "@types/node": "^12.20.55",
      "@types/react": "^17.0.65",
      "axios": "^1.5.0",
      "react": "^18.2.0",
      "react-dom": "^18.2.0",
      "react-redux": "^8.1.2",
      "react-router-dom": "^6.15.0",
      "react-scripts": "5.0.1",
      "tss-react": "^4.9.0",
      "typescript": "^4.9.5",
      "web-vitals": "^1.1.2"
    },
    "eslintConfig": {
      "extends": ["react-app", "react-app/jest"]
    },
    "devDependencies": {
      "@types/react-dom": "^18.2.7"
    }
  }
}
```

- Create a `template` folder.

- Create a `gitignore` file with the content below. Make sure to omit the dot.

```yml
# See https://help.github.com/articles/ignoring-files/ for more about ignoring files.

# dependencies
/node_modules
/.pnp
.pnp.js

# testing
/coverage

# production
/build

# misc
.DS_Store
.env.local
.env.development.local
.env.test.local
.env.production.local

npm-debug.log*
yarn-debug.log*
yarn-error.log*
```

- Inside the `template` folder create a `public` folder with the following `index.html`.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <meta name="theme-color" content="#000000" />
    <meta
      name="description"
      content="Web site created using create-react-app"
    />
    <link rel="apple-touch-icon" href="%PUBLIC_URL%/logo192.png" />
    <!--
      manifest.json provides metadata used when your web app is installed on a
      user's mobile device or desktop. See https://developers.google.com/web/fundamentals/web-app-manifest/
    -->
    <link rel="manifest" href="%PUBLIC_URL%/manifest.json" />
    <!--
      Notice the use of %PUBLIC_URL% in the tags above.
      It will be replaced with the URL of the `public` folder during the build.
      Only files inside the `public` folder can be referenced from the HTML.

      Unlike "/favicon.ico" or "favicon.ico", "%PUBLIC_URL%/favicon.ico" will
      work correctly both with client-side routing and a non-root public URL.
      Learn how to configure a non-root public URL by running `npm run build`.
    -->
    <title>React App</title>
  </head>
  <body>
    <noscript>You need to enable JavaScript to run this app.</noscript>
    <div id="root"></div>
    <!--
      This HTML file is a template.
      If you open it directly in the browser, you will see an empty page.

      You can add webfonts, meta tags, or analytics to this file.
      The build step will place the bundled scripts into the <body> tag.

      To begin the development, run `npm start` or `yarn start`.
      To create a production bundle, use `npm run build` or `yarn build`.
    -->
  </body>
</html>
```

- Inside the `template` folder create a `src` folder and an `index.tsx` in it.

```ts
import React from "react";
import ReactDOM from "react-dom/client";
import "./index.css";
import App from "./App";
import reportWebVitals from "./reportWebVitals";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

reportWebVitals();
```

- Inside the `template/src` folder create a `App.tsx` file.

```ts
import React from "react";

const App = () => {
  return <div>My CRA template</div>;
};

export default App;
```

- Test that your scaffold is working locally by running

```bash
npx create-react-app my-app --template file:.
```

## Publish to npm

```bash
npm publish
```

## Use your published template in a project

```bash
npx create-react-app my-app --template your-template-name
```

```bash
npx create-react-app my-app --template barebones
```
