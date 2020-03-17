# GPA/LAB Prettier Config

This package extends [Prettier](https://prettier.io/) with a custom configuration so that code can be automatically formatted to conform to the GPA/LAB style guide.

## Installation

Run the following command from the root of your project to install the custom configuration and the base Prettier package on which it is dependent:

```bash
npm install prettier @gpa-lab/prettier-config --save-dev
```

## Usage

Once installed, you can specify `@gpa-lab/prettier-config` as your preferred prettier configuration. There are several ways to to this:

1. Add the line `"prettier": "@gpa-lab/prettier-config"` to your project's `package.json`;
1. Export the string `"@gpa-lab/prettier-config"` from one of the supported config file types (`.prettierrc`, `.prettierrc.toml`, `prettier.config.js`, or `.prettierrc.js`);

## Extend

To add to or modify the rules implemented by the package, import the package into a `.prettierrc.js` file, modifies the rules you would like to change, and export your modifications.

For example, to keep all the rules defined by the package with the exception of the semicolon rule, your `.prettierrc.js` would look like so:

```js
module.exports = {
  ...require('@gpa-lab/prettier-config'),
  semi: false
};
```
