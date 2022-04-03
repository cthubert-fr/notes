---
layout: default
title: "Mixins - Typescript"
permalink: /formation/typescript/mixin/
lang: fr
my_menu: menu-typescript.html
---

## Mixins

```ts
class Person {
    speak() { console.log('je parle'); }
    walk() { console.log('je marche'); }
}

class Alien {
    telepathy() { console.log('test'); }
}

type Class = new (...args: any[]) => any;

function PersonMixin<Base extends Class>(base: Base) {
    return class extends base {
        speak() { console.log('je parle'); }
        walk() { console.log('je marche'); }
    }
}

function AlienMixin<Base extends Class>(base: Base) {
    return class extends base {
        telepathy() { console.log('test'); }
    }
}

const PersonAndAlien = PersonMixin(AlienMixin(class {

}));

const testMixin = new PersonAndAlien();
testMixin.speak();
testMixin.walk();
testMixin.telepathy();

//
//
// Le code suivant est valide :
//
interface Roger extends Person, Alien {};

const test: Roger = {
    speak(): void {},
    walk(): void {},
    telepathy(): void {}
}
```
