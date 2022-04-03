---
layout: default
title: "Tuple - Typescript"
permalink: /formation/typescript/tuple/
lang: fr
my_menu: menu-typescript.html
---

## Type : tuple

* Fixer le nombre et le type d'élements.

```ts
//
// Fixer le type des données
let pair: [string, number];
pair[0] = 'age';
pair[1] = 42;
//
// autre affectation possible :
pair = ['age', 42];
```

Remarque(s) :
* la méthode `push` sur un tuple ajoute un élement sans tenir compte de la contraite du nombre d'élement.
