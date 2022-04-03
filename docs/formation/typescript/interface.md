---
layout: default
title: "Interface - Typescript"
permalink: /formation/typescript/interface/
lang: fr
my_menu: menu-typescript.html
---

## Interface

```ts
interface Person {
    name: string;

    speak(): void;
}

class Mother implements Person {
    name: string;

    constructor(name: string) {
        this.name = name;
    }

    speak() {
        console.log("Bonjour, je m'appelle " + this.name);
    }
}

const person = new Mother('Monique');
person.speak();
```