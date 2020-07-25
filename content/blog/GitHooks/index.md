---
title: GitHooks
date: "2020-07-26T08:56:37.121Z"
description: Supercharge your development workflow
---

Ever merged code that caused breaking changes 🙋🏼‍♂️?

There are several ways to mitigate this risk. 
One is to configure your continuous integration build pipelines to catch these errors. 
Another is to catch errors before you even commit your changes, let alone push them onto your feature branch. 
This can be achieved with a pre-commit hook.

On my projects, I like to have both.

A pre-commit hook allows you to run all manner of checks when committing your code. 
If any of your checks fail, the commit doesn't go through. 
In this sense, it's really doing the same as your CI but is catching the errors earlier on in the workflow.

[Husky](https://www.npmjs.com/package/husky) is an easy-to-use tool to configure the commands that you want to run before each commit (you could also do this before each push by replacing `"pre-commit"` with `"pre-push"`)

For example, you may choose to run the following checks before each commit:
- tests (you can choose to run the whole test suit or just the tests for the code that you are committing)
- linting (eslint and typescript, if configured)
- formatting (e.g. prettier)


#### Basic Setup
Run tests before each commit. Install [husky dependencies](https://www.npmjs.com/package/husky).
> .huskyrc
```
{
  "hooks": {
    "pre-commit": "npm run test"
  }
}
```

#### Intermediate Setup
Run tests and linting before each commit. Install [husky dependencies](https://www.npmjs.com/package/husky) and [lintstaged dependencies](https://www.npmjs.com/package/lint-staged?activeTab=dependencies)
> .huskyrc
```
{
  "hooks": {
    "pre-commit": "lint-staged && npm run test"
  }
}
```

> .lintstagedrc
```
{
  "*.+(js|ts|tsx)": [ // the file extensions you want to lint
    "eslint" // your lint runner
  ]
}
```

#### Advanced Setup
Run tests, linting and code formatting before each commit. [husky dependencies](https://www.npmjs.com/package/husky), [lintstaged dependencies](https://www.npmjs.com/package/lint-staged?activeTab=dependencies) and [prettier dependencies](https://prettier.io/docs/en/install.html)
> .huskyrc
```
{
  "hooks": {
    "pre-commit": "lint-staged && npm run test"
  }
}
```
> .lintstagedrc
```
{
  "*.+(js|ts|tsx)": [ // the file extensions you want to lint
    "eslint" // your lint runner
  ],
  "**/*.+(js|ts|tsx)": [ // the file extensions you want to format
    "prettier --write", // --write flag instructs prettier to overwrite files
    "git add"
  ]
}
```

#### Roundup
If you're working alone a project, then the basic or intermediate setups will already give your project a boost by catching failing tests and linting errors. 

The advanced setup is great for keeping a consistent code format when collaborating with others. Everyone can work with their preferred text editor format settings locally and prettier will ensure that the code is reverted back to the settings outlined .prettierrc (which should be in the project's root directory) when commiting code to version control.