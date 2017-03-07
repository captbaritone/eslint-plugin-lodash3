# Property shorthand

When using certain method in Underscore such as map, it's possible to use the `_.property` callback shorthand. 
This rule will enforce whether or not to use shorthand when possible to keep consistency in your code.

**Fixable:** This rule (in "always" mode) is automatically fixable using the `--fix` flag on the command line.

## Rule Details

This rule takes one argument, when to use shorthand: `always` or `never` (default is always).

### `always`

Example of __incorrect__ code when configured to enforce `always` using the
shorthand:

```js
/*eslint Underscore/prop-shorthand: [2, "always"]*/
var admins = _.filter(users, function (user) {
  return user.isAdmin;
});
```

Example of __correct__ code when configured to enforce `always` using the
shorthand:

```js
/*eslint Underscore/prop-shorthand: [2, "always"]*/
var admins = _.filter(users, 'isAdmin');
```

### `never`

Example of __incorrect__ code when configured to enforce `never` using the
shorthand:

```js
/*eslint Underscore/prop-shorthand: [2, "never"]*/
var admins = _.filter(users, 'isAdmin');
```

Example of __correct__ code when configured to enforce `never` using the
shorthand:

```js
/*eslint Underscore/prop-shorthand: [2, "never"]*/
var admins = _.filter(users, function (user) {
  return user.isAdmin;
});
```

## When Not To Use It

If you do not want to enforce whether or not to use the `_.property` callback shorthand, then you can disable this rule.
