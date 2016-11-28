# IDE Integration

## PHPStorm
1. download `/static/PHPStorm_Code_Inspector.xml` and `/static/PHPStorm_Code_Style_Javascript.xml` in [this github repo](https://github.com/ApparelMedia/pear-js-convention).
1. import `PHPStorm_Code_Inspector.xml` to Preferences > Editor > Inspections in PHPStorm
2. import `PHPStorm_Code_Style_Javascript.xml` to Preferences > Editor > Code Style > Javascript

To Import, navigate to the respective preference view, click on the "Manage..." button, then Import.

You can now simply press `alt+cmd+L` to auto format the current file, and will fix about 90% of eslint errors

## Atom
1. install `linter-eslint` in atom preferences
2. As you type, you'll see eslint errors


## Sublime Text
install `https://packagecontrol.io/packages/ESLint` (follow instructions)
Optionally install `https://packagecontrol.io/packages/ESLint-Formatter`
