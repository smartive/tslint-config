# smartive TSLint Config

## Purpose

The rules in this package can be used to enforce consistent code style.

## Usage

Install from npm to your devDependencies  (https://www.npmjs.com/package/@smartive/tslint-config)

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
