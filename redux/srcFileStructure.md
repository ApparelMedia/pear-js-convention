# `src` File Structure

**All app-related files are located in `src` directory of the project**

## Anatomy of the `src` directory
```
src
├── actions/      (All Actions)
├── components/   (All Components)
├── constants/    (App-related constants)
├── containers/   (All Containers that are not tied to the routes)
├── layouts/      (Layouts for nav outside of the route pages)
├── reducers/     (All Reducers)
├── routes/       (All Route pages)
├── static/       (State files that will be copied to dist/ directory)
├── store/        (Configuration directory to generate the Redux Store)
├── styles/       (App-level styles, like sass variables)
├── support/      (Helper functions)
├── index.html    (Starter html file)
└── main.js       (Entry javascript file)
```

## `actions` directory
Actions in redux is not *really* tied to any other parts of the app.  This means that as long as you have access to the `dispatch` function from the `store`, you can dispatch an action.

Actions, like any feature of Redux (javascript for that matter), can all be written in one file, but we will strive for better organization.

I propose we group our actions in the intended objects.  For example, if the action type is `OPEN_MODAL`, then that action will be in `actions/modal.js`.

> **Note**, even if there is no `modal` property in the state, the action file is still called `modal.js`. This is to highlight the fact that actions are not tied to the state at all.

## `constants` directory

The files in the `constants` directory will always `export default` some data.

The data outputed by the files are basically data that would be in the `state`, except these data will NOT change.

One example is the steps/sequence to create a group.  No matter how the user interacts with the site, the number and sequence of the steps will not change.  Even if later on, the business wants the user **to have the ability** to change the number of steps to create a user, we can easily move the data to our state and add a reducer.

## `layouts` directory
TODO

## `reducers` directory
The name of the files in the `reducers` directory is tied to the name of the property in the state that they are responsible for.
For example, if there is a `visibleModal` property in the state, then the file responsible for that property is called `reducers/visibleModal.js`.

You can simply generate the reducer by using `plop`.  It will add a default file in `reducers` and add the reducer to `combineReducers` function in the `store/reducers.js` file.

## `routes` directory
TODO

## `static` directory
This is the directory that houses all the files that are related to the app and will be copied to the `/dist` directory when we run `yarn run deploy:prod`.

## `store` directory
There are only two files in the `store` directory, and there shouldn't be any more.  The goal of the store directory is to isolate the responsibility to create a Redux `store`.

The `reducers.js` file generates and exports a reducer function by utilizing the `combineReducers` convenience function.

The `createStore.js` file exports the `store`.

## `styles` directory
The `styles` directory has all the scss files that hold top-level styles and global variables for our components.  
All the files in the `styles` directory can be available from within the components' scss files by doing `@import` inside of the component scss files like so:
```css
@import '~styles/variables/colors';  /* importing /src/styles/variables/colors.scss */
```
> *Note* The `~` in the `@import` string is the symbol that signifies that the string is a relative path, then webpack does the rest to resolve the path.

## `support` directory
The goal of the `support` directory is to have a collection of helper functions that can be accessible globally.  They are mostly convenience functions.

## `index.html` file

This is the starting html where all the javascript is loaded and executed.

This file is copied to /dist/ directory when we run `yarn run deploy:prod`.

This file is also the template or guide in which we should model after the html served the server framework if we are integrating the react app inside one.

## `main.js` file

`main.js` is the entry point of the React/Redux app.
The file grabs the `initialState` and creates the `store`, bootstraps the rest of the app and enable extensions based on environment (production or dev).