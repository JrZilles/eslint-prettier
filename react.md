## Install eslint + prettier with airbnb style and Typescript in REACT

```bash
# install eslint
yarn add eslint -D

# start configuration
yarn eslint --init
```

### Answer the question with the following:

1. How would you like to use ESLint?
    - To Check syntax and find problems
2. What type of modules does your project use?
    - Javascript modules (import/export)
3. Which framework does your project use?
    - React
4. Does your project use Typescript?
    - Yes
5. Where does your code run?
    - Browser
6. What format do you want your config file to be in?
    - Javascript
7. Would you like to install them now?
    - Yes
8. Which package manager do you want to use?
    - yarn


### Now we need to install the missing airbnb dependencies:

```bash
# install airbnb dependencies
npx install-peerdeps --dev eslint-config-airbnb
```
replace the extends `'eslint:recommended'` in the file `.eslintrc.cjs` with `'airbnb', 'airbnb/hooks'`

### Now we need to install the config for typescript:

```bash
yarn add eslint-config-airbnb-typescript -D
```

### Modify the .eslintrc.cjs

1. to the `extends` add `'airbnb-typescript'` after the `'airbnb'`
2. to the `parseOptions` add `project: './tsconfig.json'`

### Modify the tsconfig.json

1. to the `include` add `".eslintrc.cjs"`

### Install prettier:

```bash
yarn add prettier eslint-config-prettier eslint-plugin-prettier -D
```

### Create a file `.prettierrc.cjs`

```javascript
module.exports = {
  singleQuote: true,
  bracketSpacing: false,
  bracketSameLine: false,
  arrowParens: 'avoid',
  printWidth: 120,
  tabWidth: 2,
  useTabs: false,
  semi: true,
  endOfLine: 'auto'
}
```

### Modify the .eslintrc.cjs

1. to the `plugins` add `'prettier'`
2. to the `extends` add `'plugin:prettier/recommended'` *(this should be the last one)*
