# LintDemo

This is a demo project to show how to establish Lint (*ESLint+Prettier+Husky*) to your project based on VSCode.

If you want to know how to to so from 0, please follow me.

## 1. ESLint

install ESLint:
CLI: npm i eslint -g

init .eslintrc file:
CLI: eslint --init

install ESLint Plugin of VSCode and allow it

There are plenty of rules which you can use to customize your own code style, for these rules, please refer to:
https://eslint.org/docs/rules/

## 2.Prettier

With the help of ESLint, you can see the *error* or *warning* of your code in real time, but you still need to fix each of these issues manually, if you want to fix all of the issues **automaticllly at once**, you can use Prettier for this purpose, and it will format your file on save at once.

install Prettier:
CLI: npm i prettier -D

install Prettier Plugin of VSCode and allow it 

PS: If your prettier doesn't work, try to search prettier on VSCode settings to Enable it, only if yu can see Prettier is marked on the status bar at the buttom of VSCode, you can make use of it

Also,iIf you want to format automatically on save, you should open the **editor.formatOnSave** setting of VSCode as well

So, basically, your Prettier coding restriction rules shold be the same as your ESLint rules, otherwise, Prettier will change your code to obey the Presstier rules on save, no matter what you have done during editting, which may loose some rules you want in ESLint.

## 3. Husky & lint-staged
Husky is the plugin to help you pre-check your code style just before commit it successfully, it is very helpful to ensure the code quality over organization.

install husky:
npm i husky lint-staged -D

set it on package.json:
```
"husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  },
  "lint-staged": {
    "src/**/*.{js,jsx,json}": [
      "yarn prettier --write",
      "yarn eslint --fix"
    ]
  }
```


