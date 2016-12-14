# Project File Structure

## Anatomy of the project file Structure
```
/
├── .plop/          (configuration directory for plop)
├── .storybook/     (configuration directory for storybook)
├── bin/            (configuration directory for entry points of npm/yarn script executables)
├── build/          (configuration directory for build process, webpack for development, karma for testing)
├── config/         (configuration directory for this variables during the build process)
├── dist/           (generated directory for compiled assets from /src)
├── node_modules/   (generated directory from yarn/npm install)
├── server/         (configuration directory for development server)
├── src/            (source directory for app. details in the next article)
├── stories/        (configuration directory for storybook.  Also development initial state is in stories/scenarios)
├── tests/          (configuration directory for tests.  Currently not being used)
├── .editorconfig   (configuration file for editors)
├── .env            (environment variables for deployment and app, not in git)
├── .env.example    (example environment variable file)
├── .eslintignore   (list of files/folders to ignore for ESlint)
├── .eslintrc       (configuration file for ESLint)
├── .gitignore      (list of files/folders to ignore for git)
├── flightplan.js   (deployment configration files for FlightPlan)
├── package.json    (configuration json file for npm/yarn. Also has all script commands)
├── plopfile.js     (configuration file for plop commands)
├── README.md       (README for this project)
├── theme.js        (configuration file for antd custom theme)
└── yarn.lock       (lock file for yarn)
```

## `.plop` directory
This configuration directory has all the template files thats used to generate files using the `plop` micro-generator

## `.storybook` directory
This directory has all the configuration to get storybook up and running.  Remember that storybook does not have ANY knowledge of the app that is in the `src` directory.  

> **Note:** Storybook actually has no knowledge of the webpack.config.js that is in our `build` directory.  That's why you'll see a separate `webpack.config.js` in the `.storybook` directory.  If you make a change the the build configuration for the app, make sure you make the corresponding change in `.storybook` if you want to webpack functionality to match.

So what you see on `localhost:6006` when you run `yarn run storybook` is **totally** separate from the app.  This ensures that your components are self-contained, and loosely-coupled to the rest of your app.

## `bin` directory
The two files in this directory are called by npm/yarn when a corresponding command is issued.  We shouldn't have to change the files here too much, unless we want to change the serve or compile process.

## `build` directory
The important file in the `build` directory is the `webpack.config.js` file.

In the `webpack.config.js` file is where all the webpack configuration is set for our app.  However, the **values** of the numerious configurations are in the `config` directory.

## `config` directory
The `config` directory holds the files that configure the **build process** of the app, so much of the configuration is to configure the `webpack.config.js` in `build/`.  

## `server` directory
This directory only has the `main.js` file inside.  This is used to run our dev server.  We shouldn't have to change this file much.

## `src` directory
The most important directory in the whole project.  This has all of our app code and components.  Please see [Src File Structure](/redux/srcFileStructure.md) documentation for more.

## `stories` directory
This is the configuration directory for Storybook.  inside, you will find a `index.js` file and a `scenarios` directory.

### `stories/index.js`
This is the file that describes all the components to showcase in storybook.

### `stories/scenarios/*`
Under `scenarios`, it has all the initial states that's shared between storybook and the app during development.