## ES6TP

#### Notes on ECMAScript in theory and practice

- Axel Rauschmayer [@rauschma](https://twitter.com/rauschma)
- Aaron Frost [@js_dev](https://twitter.com/js_dev)

https://github.com/aaronfrost/es6-workshop


###### Notes

Rhino is javascript mascot for O'Reily but I don't know why.

Ek-ma? Not spell out ECMA? Haha

Javascipt is a trademarked name, so the official name is ECMA Script.  Javascript is just one implementation of ECMAScript

Goals: make JS better

- for complex applications
- for libraries (including the DOM)
- as a target of code generators

ES6 is the last huge upgrade, ES7+ will be upgraded every year with very small releases.

Run Statically (dev time) or Dynamically (runtime)


#### Features

##### Variables and Scoping


`var` is function scoped and `let, const` is block scoped

##### Destructing

```es6

let obj = { first: 'Jane', last: 'Doe'}
let { first: f, last: l } = obj

// f and l are now vars with 'Jane' and 'Doe' values

```

This works with arrays and objects and multiple return values

##### Modules

The `modules.exports` var is being setup with front end development

Named exports

```es6
// lib/math.js

let notExported = 'abc';
export function square(x) {
  return x*x;
}
export const MY_CONSTANT = 123;

// main1.js
import {square} from 'lib/math';
console.log(square(3));

//main2.js
import * as math from 'lib/math';
console.log(math.square(3));
```

Default exports

```es6
export default function(...) { ... }

import myFunc from 'myFunc';
```
