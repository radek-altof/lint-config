# Linting configuration

Custom ESlint & Stylelint configuration.


## ESLint

The rules are defined in [`eslint.json`](eslint.json). Complete list of ESLint rules can be found here: https://eslint.org/docs/rules/


## Stylelint

The rules are defined in [`stylelint.json`](stylelint.json). Complete list of Stylelint rules can be found here: https://stylelint.io/user-guide/rules/


## Installation

```sh
$ npm i @radek-altof/lint-config --save-dev
```


## Configuration

Extend your ESLint and Stylelint config files. Ex.:

```json
{
  "extends": ["./node_modules/@radek-altof/lint-config/eslint.json"]
} 
```


## Grunt

Install grunt dependencies.

```sh
$ npm i grunt-eslint --save-dev
$ npm i grunt-stylelint --save-dev
```

Update `gruntfile.js` in your project.

```javascript
grunt.initConfig({
  eslint: {
    options: {
      configFile: 'eslint.json',
      fix: grunt.option('fix')
    },
    target: ['js/*.js']
  },
  stylelint: {
    options: {
      configFile: 'stylelint.json',
      syntax: 'scss',
      fix: grunt.option('fix')
    },
    src: [ 'css/*.scss' ]
  }
});
```

Lint your code.

```sh
$ grunt eslint 
```

```sh
$ grunt stylelint
```