---
layout: default
title: "Type : unknown - Typescript"
permalink: /formation/typescript/unknown-type/
lang: fr
my_menu: menu-typescript.html
---

## Type : unknown

```ts
//
// Test avec any
let inputData: any;
inputData = true;
console.log(typeof inputData); // boolean

let inputAge: number;
inputAge = inputData; // Aucun problème pour le compilateur...
console.age(typeof inputAge); // boolean

//
// Test avec unknown : KO
let inputData: unknown;
inputData = true; // même problème si l'on affecte un nombre...
console.log(typeof inputData); // boolean

let inputAge: number;
inputAge = inputData; // Problème pour le compilateur...
console.age(typeof inputAge); // boolean

//
// Test avec unknown : OK
let inputData: unknown;
inputData = 33; // même problème si l'on affecte un nombre...
console.log(typeof inputData); // number

let inputAge: number;
if(typeof inputData === 'number') {
    inputAge = inputData; // Aucun problème pour le compilateur...
    console.age(typeof inputAge); // number
}
```
