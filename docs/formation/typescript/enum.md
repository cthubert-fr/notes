---
layout: default
title: "Enumération - Typescript"
permalink: /formation/typescript/enum/
lang: fr
my_menu: menu-typescript.html
---

## Enumération

```ts
/*
ADMIN = 0
MODERATOR = 1
SUPPORT = 2
USER_READ_ONLY = 3
*/

const users = {
    pseudo: 'Batman',
    level: 2
};

if(users.level === 2) {
    console.log(`Bienvenue ${users.pseudo}, vous travaillez au service support !`);
}

//
// exemple avec enum
enum Level {
    ADMIN,           // 0
    MODERATOR,       // 1
    SUPPORT,         // 2
    USER_READ_ONLY   // 3
}

const userTwo = {
    pseudo: 'John Wick',
    level: Level.ADMIN
}

if(userTwo.level === Level.ADMIN) {
    console.log(`Bienvenue ${userTwo.pseudo}, vous êtes administrateur !`);
}

//
// autre exemple
enum Color {
    Blue = 1,
    White = 8
    Red = 9
}

let colorName: string = Color[1];
console.log(colorName); // Blue
```
