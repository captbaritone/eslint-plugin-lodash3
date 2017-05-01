[![Build Status](https://travis-ci.org/captbaritone/eslint-plugin-underscore.svg?branch=master)](https://travis-ci.org/captbaritone/eslint-plugin-underscore)

Forked from [eslint-plugin-lodash](https://github.com/wix/eslint-plugin-lodash)

ESLint-plugin-underscore
===================

[![Greenkeeper badge](https://badges.greenkeeper.io/captbaritone/eslint-plugin-underscore.svg)](https://greenkeeper.io/)

Linting rules for [Underscore](http://underscorejs.org/)

# Installation

Install [ESLint](https://www.github.com/eslint/eslint) either locally or globally.

    npm install eslint

If you installed `ESLint` globally, you have to install the Underscore plugin
globally too. Otherwise, install it locally.

    $ npm install eslint-plugin-underscore

# Configuration

Add `plugins` section and specify ESLint-plugin-underscore as a plugin.

```json
{
  "plugins": ["underscore"]
}
```


Finally, enable all of the rules that you would like to use.

```javascript
{
  "rules": {
    "underscore/collection-return": 2,
    "underscore/identity-shorthand": [2, "always"],
    "underscore/jquery-each": [2, "never"],
    "underscore/jquery-extend": [2, "never"],
    "underscore/jquery-proxy": [2, "never"],
    "underscore/matches-shorthand": [2, "always"],
    "underscore/no-return-value-from-each-iteratee": 2,
    "underscore/no-unnecessary-bind": 2,
    "underscore/prefer-chain": [2, 3],
    "underscore/prefer-compact": 2,
    "underscore/prefer-constant": 2,
    "underscore/prefer-filter": 2,
    "underscore/prefer-findwhere": 2,
    "underscore/prefer-invoke": 2,
    "underscore/prefer-map": 2,
    "underscore/prefer-matches": 2,
    "underscore/prefer-noop": 2,
    "underscore/prefer-pick": [2, {objectsLargerThan: 3}],
    "underscore/prefer-pluck": 2,
    "underscore/prefer-reject": 2,
    "underscore/prefer-times": 2,
    "underscore/prefer-underscore-method": 2,
    "underscore/prefer-underscore-typecheck": 2,
    "underscore/prefer-where": 2,
    "underscore/preferred-alias": 2,
    "underscore/prop-shorthand": [2, "always"],

    // The below rules are not (yet) supported
    "underscore/no-single-chain": 2,
    "underscore/unwrap": 2,
    "underscore/no-double-unwrap": 2,
    "underscore/prefer-wrapper-method": 2,
    "underscore/prefer-lodash-chain": 2,
    "underscore/chain-style": [2, "as-needed"]
  }
}
```

# List of supported rules

* [collection-return](docs/rules/collection-return.md): Always return a value in iteratees of Underscore collection methods that aren't `each`.
* [identity-shorthand](docs/rules/identity-shorthand.md): Prefer identity shorthand syntax.
* [jquery-each](docs/rules/jquery-each.md): Standardize on either Underscore's or jQuery's each function.
* [jquery-extend](docs/rules/jquery-extend.md): Standardize on either Underscore's or jQuery's extend function.
* [jquery-proxy](docs/rules/jquery-proxy.md): Standardize on either Underscore's bind or jQuery's proxy function.
* [matches-shorthand](docs/rules/matches-shorthand.md): Prefer matches shorthand syntax.
* [no-return-value-from-each-iteratee](docs/rules/no-return-value-from-each-iteratee.md): Do not return a value from the iteratee of `_.each`.
* [no-unnecessary-bind](docs/rules/no-unnecessary-bind.md): Prefer passing `thisArg` over binding.
* [prefer-chain](docs/rules/prefer-chain.md): Prefer chain over nested Underscore calls.
* [prefer-compact](docs/rules/prefer-compact.md): Prefer `_.compact` over `_.filter` for only truthy values.
* [prefer-constant](docs/rules/prefer-constant.md): Prefer `_.constant` over functions returning literals.
* [prefer-filter](docs/rules/prefer-filter.md): Prefer `_.filter` over `_.each` with an `if` statement inside.
* [prefer-findwhere](docs/rules/prefer-findwhere.md): Prefer `_.findWhere` over `_.find` when using matcher shorthand. (fixable)
* [prefer-invoke](docs/rules/prefer-invoke.md): Prefer using `_.invoke` over `_.map` with a method call inside.
* [prefer-map](docs/rules/prefer-map.md): Prefer `_.map` over `_.each` with a `push` inside.
* [prefer-matches](docs/rules/prefer-matches.md): Prefer `_.matches` over conditions like `a.foo === 1 && a.bar === 2 && a.baz === 3`.
* [prefer-noop](docs/rules/prefer-noop.md): Prefer `_.noop` over empty functions.
* [prefer-pick](docs/rules/prefer-pick.md): Prefer `_.pick` over defining an object that is a subset of another object.
* [prefer-pluck](docs/rules/prefer-pluck.md): Prefer `_.pluck` over `_.map` when using property shorthand. (fixable)
* [prefer-reject](docs/rules/prefer-reject.md): Prefer `_.reject` over filter with `!(expression)` or `x.prop1 !== value`.
* [prefer-times](docs/rules/prefer-times.md): Prefer `_.times` over `_.map` without using the iteratee's arguments.
* [prefer-underscore-method](docs/rules/prefer-underscore-method.md): Prefer using Underscore collection methods (e.g. `_.map`) over native array methods.
* [prefer-underscore-typecheck](docs/rules/prefer-underscore-typecheck.md): Prefer using `_.is*` methods over `typeof` and `instanceof` checks when applicable.
* [prefer-where](docs/rules/prefer-where.md): Prefer `_.where` over `_.filter` when using matcher shorthand. (fixable)
* [preferred-alias](docs/rules/preferred-alias.md): Preferred aliases.
* [prop-shorthand](docs/rules/prop-shorthand.md): Prefer property shorthand syntax. (fixable)

# List of Lodash rules which are __not__ yet supported

* [no-single-chain](docs/rules/no-single-chain.md): Prevent chaining syntax for single method, e.g. `_(x).map().value()`.
* [unwrap](docs/rules/unwrap.md): Prevent chaining without evaluation via `value()` or non-chainable methods like `max()`.
* [no-double-unwrap](docs/rules/no-double-unwrap.md): Do not use `.value()` on chains that have already ended (e.g. with `max()` or `reduce()`).
* [prefer-wrapper-method](docs/rules/prefer-wrapper-method.md): Prefer using array and string methods in the chain and not the initial value, e.g. `_(str).split(' ')...`
* [prefer-lodash-chain](docs/rules/prefer-lodash-chain.md): Prefer using Lodash chains (e.g. `_.map`) over native and mixed chains.
* [chain-style](docs/rules/chain-style.md): Enforce a specific chain style: explicit, implicit, or explicit only when necessary.

# License

ESLint-plugin-underscore is licensed under the [MIT License](http://www.opensource.org/licenses/mit-license.php).

[npm-url]: https://npmjs.org/package/eslint-plugin-underscore
[npm-image]: http://img.shields.io/npm/v/eslint-plugin-underscore.svg?style=flat-square
