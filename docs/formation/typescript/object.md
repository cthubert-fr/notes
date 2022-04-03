---
layout: default
title: "Objet - Typescript"
permalink: /formation/typescript/object/
lang: fr
my_menu: menu-typescript.html
---

## Objet

```ts
const member: {
    level: [string, number]
} = {
    level: ['admin', 1]
};
//
// opération possible :
member.level[0] = 'visitor';
//
// Type object
let bus: {
    color: string;
    date: number;
    speed: number;
};
//
// opération possible
bus.color = 'yellow';
```
