---
layout: default
title: "Tableaux - Typescript"
permalink: /formation/typescript/array/
lang: fr
my_menu: menu-typescript.html
---

## Tableaux

### Syntaxe typage tableau

```ts
let colors: string[] = ['blue', 'white', 'red'];
//
// équivalents à :
let otherColors: Array<string> = ['blue', 'black'];
//
// Opérations sur le tableau :
otherColors[1] = 'white';
otherColors.push('red');
```

###  Tableau avec différents type

```ts
//
// le tableau data acceptera des chaînes de caractères, des nombres ou des booléens.
// NOTE : le type des données est ici géré par inférence.
let data = ['a text', 200, true];
//
// opérations possibles
data[1] = '200 OK';
data.push('<html>...</html>')
```

### Tableau X Union type

```ts
//
// la tableau data n'accepte ici que des chaînes de caractères et des nombres
let data: (string | number)[] = ['test', 200];
```
