# Interview Scheduler

## TDD
- If you want to manually test your components in isolation: use **Storybook**.
- If you want to run your entire application in development mode: use **webpack-dev-server**.
- If you want to run unit or integration tests from the command line: use **Jest**.
- If you wan to run automated end-to-end tests in the browser: use **Cypress**.

## Storybook

## webpack-dev-server
The *webpack-dev-server* should only be used for development. A production bundle should be built when deploying the application to the public.

## Jest
A test environment is an important consideration for any project. The ability to run tests using the Jest testing framework is built-in to the project. 

## Cypress
We will extend the testing of the UI to an automated system which will allow us to perform tests using simulated user interaction. 

## Babel: The JavaScript Compiler
Babel is a tool that is used to convert ES2015+ JavaScript into a backwards compatible version of JavaScript.  
Convert some code using the [Babel](https://babeljs.io/repl#?browsers=&build=&builtIns=false&corejs=3.21&spec=false&loose=false&code_lz=MYewdgzgLgBApgGzgWzmWBeGAeAFgJhmAQEMIIA5E1DAIjGrloD4rVsB6A5gKBn4FA&debug=false&forceAllTransforms=false&modules=false&shippedProposals=false&circleciRepo=&evaluate=false&fileSize=false&timeTravel=false&sourceType=module&lineWrap=false&presets=react&prettier=false&targets=&version=7.4.3&externalPlugins=&assumptions=%7B%7D) online compiler.

(Webpack: The Module Bundler)