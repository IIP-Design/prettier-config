---
title: Rules
---

We find that the Prettier team does a good job in choosing sensible defaults so we have by and large preserved the recommended rules. The following four rules are where we diverge from Prettier's defaults. More information on these and all other Prettier configuration options can be found in the [Prettier documentation](https://prettier.io/docs/en/options.html).

### Arrow Function Parentheses

**Options:** `always`, `avoid`

**Our Config:**

```json
"arrowParens": "avoid"
```

**Default Prettier Config:**

```json
"arrowParens": "always"
```

**Purpose:** When an arrow function has a single parameter, the parentheses surrounding that parameter is optional. This options determines whether or not to require these optional parentheses.

**Rationale:** We believe that including these unnecessary parentheses make the code more noisy and thereby less readable. This was the default position for Prettier until v2.0.0. Adding additional arguments, default values, or type annotations becomes more burdensome when a function does not already have parentheses around it's parameters. The Prettier team felt this impact to developer experience outweighs the gains in readability provided by omitting the parentheses. We disagree.

### Print Width

**Options:** Any number.

**Our Config:**

```json
"printWidth": 100
```

**Default Prettier Config:**

```json
"printWidth": 80
```

**Purpose:** Specifies the maximum number of characters per line.

**Rationale:** Team stylistic preference. We find that the default of 80 characters causes unnecessary line breaks, too frequently pushing to two lines what can comfortably fit in one. One hundred characters is more to our taste.

### Quote Props

**Options:** `as-needed`, `consistent`, `preserve`

**Our Config:**

```json
"quoteProps": "consistent"
```

**Default Prettier Config:**

```json
"quoteProps": "as-needed"
```

**Purpose:** Determines whether or not to use quotation marks on the property keys of an object. In most cases object quotation marks can be omitted on object keys. However, if a key if not a valid identifier name (for example it contains a space) it must be wrapped in quotation marks.

```js
const myObject = {
  'one': 'one', // Valid without quotation marks.
  2: 2, // Valid without quotation marks.
  'property-three': 'three', // Requires quotation marks.
  'property four': 'four', // Requires quotation marks.
};
```

**Rationale:** Team stylistic preference. Using the `consistent` option as we do, objects will default to no quotes around their keys unless one of their keys requires quotes to be a valid identifier. In these cases all keys in that object will be wrapped in quotation marks. We find objects to be more readable when either all or none of the properties are wrapped in quotation marks.

**Note:** Our choice may cause issue in the unlikely edge case that you use a number as an object key since `obj[123]` is not the same as `obj['123']`. As such, we strongly recommend against using numbers to name object properties.

### Single Quotes

**Options:** `true`, `false`

**Our Config:**

```json
"singleQuote": true
```

**Default Prettier Config:**

```json
"singleQuote": false
```

**Purpose:** Prefers single quotes over double quotes (ignored in JSX props).

**Rationale:** Team stylistic preference. There are some considerations when it comes to escaping nested quotation marks or apostrophes, but mostly we just think it looks nicer.
