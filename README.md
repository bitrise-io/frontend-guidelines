# Frontend Dev Guidelines, tools

## Code style - [Prettier](https://prettier.io/docs/en/)

**Non-default options:**

```js
// .prettierrc
{
  "printWidth": 120,
  "singleQuote": true,
  "arrowParens": "always"
}
```

> *Note:* the [Require Prama](https://prettier.io/docs/en/options.html#require-pragma) option might be useful while transitioning

**CI**

Configure a [pre-commit hook](https://prettier.io/docs/en/precommit.html)

**Extra**

Check out the [Editor Integrations](https://prettier.io/docs/en/editors.html)

## TypeScript

Using [tslint-config-airbnb](https://github.com/progre/tslint-config-airbnb), [tslint-config-prettier](https://github.com/prettier/tslint-config-prettier)

```js
// tslint.json
{
  "defaultSeverity": "error",
  "extends": [
      "tslint:recommended",
      "tslint-config-airbnb",
      "tslint-config-prettier"
  ],
  "jsRules": {},
  "rules": {
    ...
    "ter-arrow-parens": [true, "always"],
    ...
  },
  "rulesDirectory": []
}
```

## Styling & Templates

### BEM

We use [BEM](http://getbem.com/introduction/) CSS class naming.
In short:

**B**lock: _Standalone entity that is meaningful on its own._
> Eg. `header`, `container`, `menu`, `checkbox`, `input`

**E**lement: _A part of a block that has no standalone meaning and is semantically tied to its block._
> Eg. `menu__item`, `list__item`, `checkbox__caption`, `header__title`

**M**odifier: _A flag on a block or element. Use them to change appearance or behavior._
> Eg. `menu__item--disabled`, `list__item--highlighted`, `checkbox--checked`, `button--primary`

### Templates

Use [angular-bem](https://github.com/tenphi/angular-bem) for BEM classes.

```html
<div class="header">
  <h1 class="header__title">
    Hello, and welcome to <span class="header__title--accented">Bitrise</span>
  </h1>
</div>
```

### SCSS

Linting with [stylelint](https://stylelint.io/)

We use an extended version of [stylelint-config-recommended](https://github.com/stylelint/stylelint-config-recommended) with a list of property orders.
See [.stylelintrc](.stylelintrc) for the list of rules.

Plugins: [stylelint-order](https://github.com/hudochenkov/stylelint-order)

Mixin naming convention:

_TODO_

### `package.json` scripts

```js
{
  ...
  "scripts": {
    ...
    "lint:style": "stylelint \"./**/*.scss\""
  }
}
```