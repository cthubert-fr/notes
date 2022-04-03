---
layout: default
title: "Les classes - Typescript"
permalink: /formation/typescript/class/
lang: fr
my_menu: menu-typescript.html
---

## Les classes

```ts
class Invoice {
    client: string;
    product: string;
    price: number;
    
    constructor(client: string, product: string, price: number) {
        this.client = client;
        this.product = product;
        this.price = price;
    }
}

const invoice1 = new Invoice('John', 'Gun', 5000);
```

### Héritage et polymorphisme

```ts
class Mother {
    name: string;
    hair: string;
    eyes: number;
    
    constructor(name: string, hair: string, eyes: number) {
        this.name = name;
        this.hair = hair;
        this.eyes = eyes;
    }
    
    speak() {
        console.log(`Je suis ${this.name} et j'ai des cheveux ${this.hair}`);
    }
}

class Children extends Mother {
    speak() {
        console.log(`I am ${this.name} and I have ${this.hair} hair`);
    }
    
    speakMothLang() {
        super.speak();
    }
}

const person1 = new Mother('Maria', 'Blond', 2);
console.log(person1);
person1.speak();

const person2 = new Children('John', 'Brown', 2);
console.log(person2);
person2.speak();
person2.speakMothLang();

const person3: Mother = new Children('Maurice', 'Blond', 2);
//person3.speakMothLang(); // appel impossible
person3.speak();
```

### Accessibilité

```ts
class Mother {
    private name: string;
    hair: string;
    eyes: number;
    
    constructor(name: string, hair: string, eyes: number) {
        this.name = name;
        this.hair = hair;
        this.eyes = eyes;
    }
    
    speak() {
        console.log(`Je suis ${this.name} et j'ai des cheveux ${this.hair}`);
    }
    
    getName() {
        return this.name;
    }
}

class Children extends Mother {
    speak() {
        console.log(`I am ${this.name} and I have ${this.hair} hair`);
    }
    
    speakMothLang() {
        super.speak();
    }
}

const person1 = new Mother('Maria', 'Blond', 2);
console.log(person1);
console.log(person1.getName());
person1.speak();

const person2 = new Children('John', 'Brown', 2);
console.log(person2);
person2.speak();
person2.speakMothLang();

const person3: Mother = new Children('Maurice', 'Blond', 2);
//person3.speakMothLang(); // appel impossible
person3.speak();
```

#### Code raccourcis

```ts
class Mother {
    private name: string;
    private eyes: number;

    constructor(name: string, eyes: number) {
        this.name = name;
        this.eyes = eyes;
    }
}

//
// Code équivalents :
class Mother2 {
    constructor(private name: string, private eyes: number) {}
}
```

### Mot-clé : static

```ts
class Person {
    static readonly TEST: number = 1234;

    static talk() {
        console.log('coucou');
    }
}

Person.talk();
console.log(Person.TEST);
```

#### Accessibilité : lecture seulement

Ne peut être affecter uniquement durant le constructeur.

```ts
class Voiture {
    constructor(readonly color: string) {}
}

const maVoiture = new Voiture('Blanche');
```

### Classe abstraite

```ts
abstract class Person {

    constructor(protected name: string) {}

    walk() {
        console.log('Je marche');
    }

    abstract updateName(newName: string): void;
}

class Mother extends Person {
    updateName(newName: string) {
        this.name = newName;
    }
}

const person = new P('Charlie');
person.walk();
```
