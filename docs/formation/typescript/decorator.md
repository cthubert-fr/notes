---
layout: default
title: "Décorateur - Typescript"
permalink: /formation/typescript/decorator/
lang: fr
my_menu: menu-typescript.html
---

## Décorateur

### Première approche

```ts
function Test(constructor: Function) {
    console.log(constructor);
}

@Test
class Car {
    constructor(private name: string, private color: string) {}
    carDetails() {
        return `Marque: ${this.name} | Couleur: ${this.color}`
    }
}
```

### Factory

```ts
function Test(hw: string) {
    return function (constructor: Function) {
        console.log(constructor);
        console.log(hw);
    }
}

@Test('hello world')
class Car {
    constructor(private name: string, private color: string) {}
    carDetails() {
        return `Marque: ${this.name} | Couleur: ${this.color}`
    }
}
```

### Autre exemple de décorateur

```ts
function Test(id: string) {
    return function (target: any) {
        const el = document.getElementById(id)!;
        const h1 = document.createElement('h1');

        const objCar = new target('Aston Martin', 'Noir');
        h1.innerText = objCar.carDetails();
        el.append(h1);
    }
}

@Test('title')
class Car {
    constructor(private name: string, private color: string) {}
    carDetails() {
        return `Marque: ${this.name} | Couleur: ${this.color}`
    }
}
```
