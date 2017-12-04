# TSLint configuration provided by smartive

The rules in this package are based on [TSLint Config Airbnb](https://github.com/progre/tslint-config-airbnb) (also see [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)) and modified to fit our company's coding guidelines.

## Rule extensions

### Line length (`max-line-length`)

The maximum line length got extended to 125 characters in order to match TypeScript's demand of longer lines due to type declarations.

### Member ordering (`member-ordering`)

Added a requirement for a meaningful ordering of class members ([fields-first](https://github.com/palantir/tslint/blob/master/src/rules/memberOrderingRule.ts#L47-L60)).

### Enable increment / decrement statements (`no-increment-decrement`)

Re-enabled incremenent (`++`) and decrements (`--`) operations to get rid of unwanted and unreadalbe workarounds.

### Check return type of functions (`typedef`)

Added `call-signature` rule to enforce return type definitions for functions.

### Allow variables with leading underscores (`variable-name`)

Due to the fact that in some cases you need underscores as variable prefixes (unused variables as function parameters, private properties with getter / setter, ..) leading underscores got enabled.

## Usage

Install using NPM:

```sh
npm install --save-dev @smartive/tslint-config
```

To activate the rules, add the following `extends` declaration to your TSLint configuration (e.g. `tslint.json`):

```javascript
{
   "extends": "@smartive/tslint-config",
   "rules": {
     ... // additional custom rules
   }
}
```

## Release notes
The release notes can be found in the [release section](https://github.com/smartive/tslint-config/releases).
