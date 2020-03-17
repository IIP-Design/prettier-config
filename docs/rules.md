---
title: Rules
---

We find that the Prettier team does a good job in chosing sensible defaults so we have by and large preserved the recommended rules. The following four rules are where we diverge from Prettier's defaults. More information on these and all other Prettier configuration options can be found in the [Prettier documentation](https://prettier.io/docs/en/options.html).

### Line Endings

**Options:** `auto`, `lf`, `crlf`, `cr`

**Our Config:**

```json
"endOfLine": "lf"
```

**Default Prettier Config:**

```json
"endOfLine": "auto"
```

**Purpose:** There are two common types of line endings in text files: 1) the line feed (LF - `\n`) used by Linux and macOS and 2) the carriage return and line feed (CRLF - `\r\n`) used by Windows. This rule sets the default line ending for files in the project.

**Rationale:** Since the majority of our team uses macOS and there is little to no downside to doing so, we explicitly force LF line endings. This is principally because changing the line endings on a file will indicate a change to every line thereby obscuring meaningful modifications and rendering git diffs essentially useless.

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

**Rationale:** Team stylistic preference. We find that the default of 80 characters causes unneccessary line breaks, too frequently pushing to two lines what can comfortably fit in one. One hundred charachters is more to our taste.

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
  one: 'one', // Valid without quotation marks.
  2: 2, // Valid without quotation marks.
  'property-three': 'three', // Requires quotation marks.
  'property four': 'four' // Requires quotation marks.
};
```

**Rationale:** Team stylistic preference. Using the `consistent` option as we do, objects will default to no quotes around their keys unless one of their keys requires quotes to be a valid identifier. In these cases all keys in that object will be wrapped in quotation marks. We find objects to be more readable when either all or none of the properties are wrapped in quotation marks.

**Note:** Our choice may cause issue in the unlikely edgecase that you use a number as an object key since `obj[123]` is not the same as `obj['123']`. As such, we strongly recommend against using numbers to name object properties.

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
