---
layout: default
title: "any - Typescript"
permalink: /formation/typescript/any/
lang: fr
my_menu: menu-typescript.html
---

## Type : any

Le type quelconque, pour stocker ce que l'on souhaite, est géré via `any`.

```ts
let anyData: any = 'Toto';
console.log(typeof anyData); // string
anyData = 33;
console.log(typeof anyData); // number

//
// autre exemple tableau de type quelconque
let anyDataArray: any[] = [];
anyDataArray = ['Toto', 33, true];
console.log(typeof anyDataArray); // object
```
