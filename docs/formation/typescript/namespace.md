---
layout: default
title: "Espace de noms VS Module - Typescript"
permalink: /formation/typescript/namespace/
lang: fr
my_menu: menu-typescript.html
---

## Espace de noms VS Module

### Espace de noms

Dans IPerson.ts :

```ts
namespace App {
    inteface IPerson {
        name: string;
        age: number;
    }

    export class Person implements IPerson {
        name: string;
        age: number;

        constructor(name: string, age: number) {
            this.name = name;
            this.age = age;
        }
    }
}
```

Dans script.ts :

```ts
/// <reference path="IPerson.ts" />
namespace App {
    const person = new Person('Albert', 45);
}
```

Dans tsconfig.json, afin de ne générer qu'un seul fichier Javascript :
```json
"module": "amd",
"outFile": "./public/app.js"
```

### Modules ES6

Dans IPerson.ts :

```ts
inteface IPerson {
    name: string;
    age: number;
}

export class Person implements IPerson {
    name: string;
    age: number;

    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }
}
```

Dans script.ts :

```ts
import { Person } from './IPerson.js'

const person = new Person('Albert', 45);
```

Dans index.html :
```html
<script type="module" src="./script.js" defer></script>
```

Dans tsconfig.json :
```json
"module": "es2015"
```
