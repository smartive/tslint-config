# TSLint Config provided by smartive

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

Configure tslint to use `@smartive/tslint-config`:

This package provides an empty configuration preset that just contains the `rulesDirectory`. That means you can easily use the rules in this package, but don't get any predefined configuration. To use it, just add it to the `extends` array in your `tslint.json`:

```javascript
{
   "extends": ["@smartive/tslint-config"]
   "rules": {
     ...
   }
}
```

## Release notes
The release notes can be found in the [release section](https://github.com/smartive/tslint-config/releases).
