# Styling

## PHPStorm Style files
Most of the styles can be quickly imported to your PHPStorm with these two files.

## Coding Best Practices
1. React `props` should be defined in `propTypes`
1. No unused variables in any scope
1. use `let` or `const` for better variable management
1. Always lint before committing code

## Styles
1. Prefer single quotes on string literals (and HTML attributes)
1. Max length of 120 characters
1. No Horizontal Alignment (See Notes below)
1. All files end with a blank line

### No Horizontal Alignment

We **do not** want horizontal alignment in our javascript code.

This is Horizontal Alignment, notice the white space:
```js
let options = {  // Not good even if it looks pretty
  name     : 'Hao',
  gender   : 'male',
  location : 'Chicago'
}
```

We simply want:
```js
let options = {
  name: 'Hao',
  gender: 'male',
  location: 'Chicago'
}
```

"Alignment can aid readability, but it creates problems for future maintenance. Consider a future change that needs to touch just one line. This change may leave the formerly-pleasing formatting mangled... 

More often it prompts the coder (perhaps you) to adjust whitespace on nearby lines as well, possibly triggering a cascading series of reformattings. That one-line change now has a "blast radius." This can at worst result in pointless busywork, but at best it still corrupts version history information, slows down reviewers and exacerbates merge conflicts." - Google Java Style Guide
