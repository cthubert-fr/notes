---
layout: default
title: "never - Typescript"
permalink: /formation/typescript/never/
lang: fr
my_menu: menu-typescript.html
---

## Type : never

```ts
type StrNum = string | number;

function test(value: StrNum) {
    if(typeof value === 'string') { return value.length; }
    else if(typeof value === 'number') { return value.toString(); }
    else { const error: never = value; }
}

//
// Autre exemple
function throwError(errMsg): never {
    throw new Error(errMsg);
}

function getTotal(arg: number) {
    if(arg < 5) {
         return throwError('Attention param < 5');
    } else if(arg === 5) {
        console.log(arg);
    } else {
        return arg + 10;
    }
}
```
