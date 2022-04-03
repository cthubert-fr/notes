---
layout: default
title: "Pattern Singleton - Typescript"
permalink: /formation/typescript/singleton-pattern/
lang: fr
my_menu: menu-typescript.html
---

## Pattern Singleton

```ts
class Company {
    totalEmployees: number;

    private static instance: Company;

    private constructor(total: number) {
        this.totalEmployees = total;
    }

    static getInstance() {
        if(this.instance) {
            return this.instance;
        }
        this.instance = new Company(500);
        return this.instance;
    }
}

const company = Company.getInstance();
```