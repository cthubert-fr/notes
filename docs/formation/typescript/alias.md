---
layout: default
title: "Type alias - Typescript"
permalink: /formation/typescript/alias/
lang: fr
my_menu: menu-typescript.html
---

## Type alias

```ts
type StrNumBoo = string | number | boolean;

function test(arg1: StrNumBoo) {
    if(typeof arg1 === 'string') {}
    else { /* ... */ }
}
```
