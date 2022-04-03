---
layout: default
title: "Variables - Typescript"
permalink: /formation/typescript/var/
lang: fr
my_menu: menu-typescript.html
---

## Variables

### Forcer le type

```ts
let fullName: string = `Steve Jobs`;
let age: number = 33;
let sentence: string = `Hello, my name is ${fullName}.

I'll be ${age + 1} years old next month.`;
```

### Différence const et let

* `const` la valeur doit être affectée lors de la définition et ne peut plus être changée.
* `let` la valeur est modifiable au cours du programme.


