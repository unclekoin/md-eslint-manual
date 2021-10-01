# ESLint manual
* [Getting Started with ESLint](https://eslint.org/docs/user-guide/getting-started)
* [Setup ESLINT and PRETTIER in React app](https://dev.to/knowankit/setup-eslint-and-prettier-in-react-app-357b)
### Start
```shell
> npm install eslint -g
# or
> npm install eslint --save-dev
```
```shell
> eslint --init
```
### We answer the questions:
1. To check syntax, find problems, and enforce code style
2. JavaScript modules (import/export)
3. React
4. TypeScript Yes/No
5. Browser
6. Use a popular style guide
7. Standard: ...
8. JavaScript
9. Yes

```javascript
// .eslintrc.js
module.exports = {
  env: {
    browser: true,
    es2021: true
  },
  extends: ["plugin:react/recommended", "standard"],
  parserOptions: {
    ecmaFeatures: {
      jsx: true
    },
    ecmaVersion: 12,
    sourceType: "module"
  },
  plugins: ["react"],
  rules: {
    indent: ["error", 2],
    semi: [2, "always"],
    "space-before-function-paren": ["error", "never"],
    quotes: ["error", "double", { allowTemplateLiterals: true }]
  }
};
```
or 
```javascript
// .eslintrc.js
module.exports = {
    env: {
        browser: true,
        es2021: true
    },
    extends: ["plugin:react/recommended", "standard"],
    parserOptions: {
        ecmaFeatures: {
            jsx: true
        },
        ecmaVersion: 12,
        sourceType: "module"
    },
    plugins: ["react"],
    rules: {
        semi: [2, "always"],
        indent: [0, 4, { SwitchCase: 1 }],
        "space-before-function-paren": [
            "error",
            {
                anonymous: "always",
                named: "never",
                asyncArrow: "always"
            }
        ],
        quotes: [
            "error",
            "double",
            {
                allowTemplateLiterals: true
            }
        ]
    }
};
```
### Create .prettierrc.js
```javascript
// .prettierrc.js
module.exports = {
  trailingComma: "none",
  tabWidth: 2,
  semi: true
};
```
```shell
> npx prettier --write .
```
or
```json
// package.json
  "scripts": {
    "format": "npx prettier -write ."
  },
  ```