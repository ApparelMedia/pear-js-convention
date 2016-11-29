# Styling

All the rules below are enforced with ESLint.  So all you need to do is enable eslint in your editor of choice and let your IDE do all the work for you.

## Coding Best Practices
1. React `props` variables should be defined in static `propTypes`
1. No unused variables in any scope ([Read More](http://eslint.org/docs/rules/no-unused-vars))
1. use `let` or `const` for better variable management([Read More](http://eslint.org/docs/rules/no-var))
1. Always lint before committing code

## Styles
1. We follow [JS Standard Style](http://standardjs.com/rules.html)!
1. Prefer single quotes whenever possible (string literals and HTML attributes) ([Read More](http://eslint.org/docs/rules/jsx-quotes#prefer-single))
1. Max length of 120 characters ([Read More](http://eslint.org/docs/rules/max-len))
1. No Horizontal Alignment (See Section below)
1. All files end with a blank line ([Read More](http://eslint.org/docs/rules/eol-last))

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
