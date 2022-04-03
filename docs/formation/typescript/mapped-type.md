---
layout: default
title: "Mapped type - Typescript"
permalink: /formation/typescript/mapped-type/
lang: fr
my_menu: menu-typescript.html
---

## Mapped type

```ts
type Props = 'Prop1' | 'Prop2' | 'Prop3';

type MyMappedTypes = {
    [P in Props] : boolean;
}

type MyType = MyMappedTypes<Props>;
```
