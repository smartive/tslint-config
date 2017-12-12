# TSLint configuration provided by smartive

The rules in this package are based on [TSLint Config Airbnb](https://github.com/progre/tslint-config-airbnb) (also see [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)) and modified to fit our company's coding guidelines.

## Rule extensions

### Line length (`max-line-length`)

The maximum line length got extended to 125 characters in order to match TypeScript's demand of longer lines due to type declarations.

### Member ordering (`member-ordering`)

Added a requirement for a meaningful ordering of class members ([fields-first](https://github.com/palantir/tslint/blob/master/src/rules/memberOrderingRule.ts#L47-L60)).

### Ordered Imports

Requires that import statements be alphabetized and grouped.

### Enable increment / decrement statements (`no-increment-decrement`)

Re-enabled incremenent (`++`) and decrements (`--`) operations to get rid of unwanted and unreadalbe workarounds.

### Check return type of functions (`typedef`)

Added `call-signature` rule to enforce return type definitions for functions.

### Allow variables with leading underscores (`variable-name`)

Due to the fact that in some cases you need underscores as variable prefixes (unused variables as function parameters, private properties with getter / setter, ..) leading underscores got enabled.

### Allow Boolean Literal Compare

Allows comparing boolean literal to values, like `if (x === true)`. This rule apparently exists to prevent confusion for new
developers, but can become relevant if `x` can be `true | false | null`.

*This rule only works if [Type Information / Checking is available](https://palantir.github.io/tslint/rules/no-boolean-literal-compare/).*

### No Strict Boolean Expressions
With `strict-boolean-expressions` only boolean values can be used with `!`, `&&`, `||`, ternary operators, if conditions and loops.
JavaScript allows quite a few neat shorthand expressions with non-boolean value, which we don't want to prohibit.

*This rule only works if [Type Information / Checking is available](https://palantir.github.io/tslint/rules/no-boolean-literal-compare/).*

## Usage

Install using NPM:

```sh
npm install --save-dev @smartive/tslint-config
```

To activate the rules, add the following `extends` declaration to your TSLint configuration (e.g. `tslint.json`):

```json
{
   "extends": "@smartive/tslint-config",
   "rules": {
     ... // additional custom rules
   }
}
```

### Usage with React

Install the config the same way as above, but activate the rules in your TSLint configuration like this:

```json
{
  "extends": "@smartive/tslint-config/tslint-react",
   "rules": {
     ... // additional custom rules
   }
}
```

## React Rule Extensions

### Allow variables in PascalCase

React components are usually named in `PascalCase`, so this should be explicitly allowed - especially when used with Higher Order
Components like `const ButtonWithSpinner = withSpinner(Button);`.

### Allow JSX Boolean Value

The developer should be allowed to declare boolean props in appropriate ways. Values should be skipped if reasonable (`<Button primary />`). Also the ability to calculate values dynamically (`<Button active={isActive} />` which might result in `active={true}`) should
be possible.

### Allow Multiline JSX

Multiline JSX expressions are allowed for things like map calls. `jsx-no-multiline-js` is too intrusive and we trust other tools,
like Code Reviews, to prevent an increase in unreadable code.

### Import Name

Sometimes filenames are not very meaningful and developers should be allowed to change default import statements, as they have the
same possibility with aliases for named imports (`import { Foo as Bar } from 'foo';`).

## Release notes
The release notes can be found in the [release section](https://github.com/smartive/tslint-config/releases).
