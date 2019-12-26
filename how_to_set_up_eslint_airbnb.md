Resources:
- https://eslint.org/docs/user-guide/getting-started
- https://medium.com/dailyjs/adding-eslint-to-your-project-7bd4feca35a8

### Install eslint
`npm install eslint --save-dev`

### Copy and paste airbnb package.json file into your directory
https://raw.githubusercontent.com/airbnb/javascript/master/packages/eslint-config-airbnb/package.json

### Run the eslint wizard
`npx eslint --init`

#### Selections
- Use a popular style guide: Airbnb
- Not React (unless you're using it)
- JSON (could be JavaScript or YAML too, your choice)

ESLint will create an `.eslintrc.json` configuration file in your directory.

### Sample Usage
`npx eslint yourfile.js`, add the `--fix` option to automatically fix violations. 
