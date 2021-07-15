# component-library
Testing how to build a component library in Github and import to React. This will effectively clone the library for it to be used as a module in React. This is an alternative to publishing with npm and can be used as a free way of hosting private packages.

## important commands 
In order to use components created with jsx, you must use the below command to compile the file and make it compatible with React. Anytime you edit the original jsx file, you must recompile with the below command.

```sh
# compiles all files in components directory and outputs in compiled-components (jsx -> js)

# NOTE: in order to have the node_modules, you must run 'npm install' to load all the dependencies

./node_modules/@babel/cli/bin/babel.js components -d compiled-components --plugins=@babel/plugin-transform-react-jsx 
```

## how to import the library into your project

```sh
# while in your project's root directory, run this command:

npm install git://github.com/micsparre/component-library.git#commit-ish"

# replace 'commit-ish' with a valid commit sha, version tag, or branch name (dafault will be your master branch)
```
After running, you should see the name of the repo show up as a dependency in your package.json

## how to import single components into your code
```sh
# Assume we have a file TestComponent.js inside of the compiled-components directory

# To use this component, include the following line at the top of your file

import { TestComponent } from 'component-library/compiled-components/TestComponent';
````

## things to remember
Make sure to commit and push any changes you make in this library to ensure they can be used remotely by others.

Whenever you create a component with jsx, you must compile it so it can be imported and used elsewhere. *Importing the jsx component WILL NOT work.