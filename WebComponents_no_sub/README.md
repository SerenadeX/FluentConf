# Diving into Web components

Standards of Web Components

5 problems of web developers

1. No native templates
2. undescriptive markup
3. No style and DOM encapsulation
4. No budling
5. No component standard

There needs to be one standard of web components.

- Templates – inert, reusable markup
- Custom Elements – Define our own elements
- Shadow DOM – Encapsulated markup and styling
- Imports – Bundle HTML, JS, CSS into one reference



### Templates

- HTML in script tags `<script type="text/custom-name-here">`
- Hidden Dom Elements `<div style="display: none">Some template</div>`

```html
<template>
```

1. Inert – Does nothing
2. Won't load assets until cloned and inserted
3. Can be traversed
4. Can be placed practically anywhere

### Custom Elements

Undescriptive markup is a problem.  People use `<div>` to contain things.

Descriptive markup:

- Conveys add info
- improves SEO
- Enhances accessibility
- Speeds development
- Aids maintenance

Custom elements need a dash in the name for namespacing issues `<my-element></my-element>`.  They can extend existing elements `<button is="uber-button">`


1. Register new element via `registerElement()`
2. Append to DOM via `appendChild()`

4 ways to instantiate

1. Markup `<pluralsight-comment />`
2. new Operator
3. createElement
4. innerHTML

Lifecycle callback methods

`createdCallback` – instance created
`attachedCallback` – instance added to DOM
`detachedCallback` – instance removed from DOM
`attributeChangedCallback(attributeName, oldValue, newValue)` – attributs added, removed or updated





### Shadow DOM

Avoiding style conflicts requires highly specific CSS selectors, or you can use `!important`.  No guarantee another style won't conflict.

Light DOM vs. Shadow DOM

`<iframe>` and `<canvas>` is too strong of a separation


JavaScript is not encapsulated in a Shadow DOM



### Imports

`<link rel="import" href="myBootstrapStuff.html">`

Imports can be used for themes, component library, app sections, A whole app!

http://jonrimmer.github.io/are-we-componentized-yet/

Webcomponents.js
