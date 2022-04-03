---
layout: default
title: "Assertion - Typescript"
permalink: /formation/typescript/assertion/
lang: fr
my_menu: menu-typescript.html
---

## Assertion

```ts
// 'as-syntax'
let someValue: unknown = 'My text value';

let strLength = (someValue as string).length;

console.log(strLength);

// Autre écriture 'angle-bracket'
let someValue: unknown = 'My text value';

let strLength = (<string>someValue).length;

console.log(strLength);
```

### Exemple assertion

```ts
const firstName = document.getElementById('firstName');
// autre syntaxe : const firstName = <HTMLInputElement>document.getElementById('firstName');
console.log(typeof firstName); // object

const firstName = document.getElementById('firstName') as HTMLInputElement;
// autre syntaxe : const firstName = <HTMLInputElement>document.getElementById('firstName');
console.log(firstName.value);
```

### Autre exemple

```ts
const form = document.querySelector('#signupForm') as HTMLFormElement;
console.log(form.children);
```
