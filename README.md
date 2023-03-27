# New Project Guide


## Project Option 1 - Manually set up Webpack, ESLint, Prettier, Babel, & Jest

### 1. Set up repository
Create new repo on GitHub & git clone it in the terminal.

### 2. Set up webpack
Open new project folder & set up Webpack following <a href="https://www.theodinproject.com/lessons/node-path-javascript-restaurant-page" target="_blank">these instructions</a> (everything in step 1) from the Odin Project restaurant project. To load CSS, follow <a href="https://webpack.js.org/guides/asset-management/#loading-css" target="_blank">these instructions</a>.
 Run `npx webpack --watch` so you don't have to rerun webpack every time you make a change.

To run web server, navigate to project directory in the terminal and run:

```
    npm i -g serve
    serve
```

### 3. Set up ESLint
Follow step 2 and step 4 of <a href="https://www.digitalocean.com/community/tutorials/linting-and-formatting-with-eslint-in-vs-code" target="_blank">these instructions</a>. Create a `.eslintignore` file and include `main.js` and `node_modules` in it.

### 4. Set up Prettier
Follow <a href="https://prettier.io/docs/en/install.html" target="_blank">these instructions</a>. To run Prettier upon saving, open the Visual Studio Code command palette and select `Preferences: Open User Settings`. Search for `Format on Save` setting and check the box.

### 5. Set up eslint-config-prettier to resolve conflicts
Follow <a href="https://github.com/prettier/eslint-config-prettier#installation" target="_blank">these instructions</a>.

### 6. If using Jest...
Install Babel using <a href="https://www.theodinproject.com/lessons/node-path-javascript-testing-practice" target="_blank">these instructions</a> (under the section "Using ES6 import statements with Jest." Then install Jest by running `npm install --save-dev jest`. Add the following to your package.json file:

```
    "scripts": {
      "test": "jest",
      "watch": "jest --watch *.js"
    }
```

Run `npm run watch` to run tests every time you save the project. Follow <a href="https://jestjs.io/docs/webpack" target="_blank">these instructions</a> for configuring Jest with webpack.

Add the following to your .eslintrc.json file (to override ESLint settings for jest test files):

```
    "overrides": [
        {
          "files": [
            "**/*.test.js"
          ],
          "env": {
            "jest": true
          }
        }
      ]
```

### 7. Upon project completion...
Follow <a href="https://gist.github.com/cobyism/4730490" target="_blank">these instructions</a>, starting at Step 2, to deploy your subfolder to GitHub Pages.


## Project Option 2 - Create React App

### 1. Set up project
Create a React app by running `npx create-react-app <project-name>`. 

### 2. Set up repository
Create an empty Github repo (do not add README.md). Connect Github repo to local project by changing into the project directory & running `git remote add origin git@github.com:<username>/<project-name>.git` (this line is displayed on Github project page under "push an existing repository from the command line."

### 3. Set up Prettier
Follow <a href="https://prettier.io/docs/en/install.html" target="_blank">these instructions</a>. To run Prettier upon saving, open the Visual Studio Code command palette and select `Preferences: Open User Settings`. Search for `Format on Save` setting and check the box.

### 4. Set up eslint-config-prettier to resolve conflicts
Run `npm install --save-dev eslint-config-prettier`. In your `package.json` file, add prettier to `eslintConfig`:

```
"eslintConfig": { 
  "extends": [ 
    "react-app", 
    "react-app/jest", 
    "prettier" 
  ] 
},
```

### 5. Upon project completion...
Follow <a href="https://medium.com/@isharamalaviarachchi/how-to-deploy-your-react-app-into-github-pages-b2c96292b18e" target="_blank">these instructions</a> to deploy your project to GitHub Pages.

