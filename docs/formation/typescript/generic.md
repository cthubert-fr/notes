---
layout: default
title: "Type générique - Typescript"
permalink: /formation/typescript/generic/
lang: fr
my_menu: menu-typescript.html
---

## Type générique

```ts
function test<T>(arg: T): T {
    return arg;
}

let output1 = test('Hello'); // écriture équivalente : test<string>('Hello');
let output2 = test(404);
```

### Générique et interface

```ts
interface User<T> {
    id: number,
    data: T
}

const userMario: User<string[]> = {
    id: 24,
    data: ['Mario', 'Moderator']
}

const userTwo: User<{name: string, role: string}> = {
    id: 33,
    data: {name: 'Nathan', role: 'Admin'}
}
```

### Générique et classe

```ts
class DataBase<T> {
    data: Array<T> = [];

    saveData(value: T) {
        this.data.push(value)
    }

    getAllData() {
        return [...this.data]
    }
}

const db = new DataBase<string>();
db.saveData('first value');
```

### Générique : Readonly

```ts
interface Todo {
    title: string;
    description: string;
}

const myTodo: Readonly<Todo> = {
    title: 'Rdv',
    description: 'Travail'
}
```

### Générique : Record

```ts
type Category = "Personnal" | "Work";

interface Todo {
    title: string;
    description: string;
}


let tasks: Record<Category, Todo> = {
    Personnal: {
        title: 'Shopping',
        description: 'Buy sugar'
    },
    Work: {
        title: 'Development',
        description: 'Dev new feature'
    }
};

console.log(`${tasks.Personnal.title}`);
```

### Générique : Pick

```ts
interface Todo {
    title: string;
    description: string;
    completed: boolean;
}


let task1: Todo = {
    title: 'Test',
    description: 'Make test',
    completed: false
};

type TodoPreview = Pick<Todo, 'title' | 'completed'>;

let task2: TodoPreview = {
    title: 'Task 2',
    completed: true
};
```

### Générique : Omit

```ts
interface Todo {
    title: string;
    description: string;
    completed: boolean;
}


let task1: Todo = {
    title: 'Test',
    description: 'Make test',
    completed: false
};

type TodoPreview = Omit<Todo, 'description'>;

let task2: TodoPreview = {
    title: 'Task 2',
    completed: true
};
```

### Générique : Exclude

```ts
type Easing = 'ease-in' | 'ease-out' | 'ease-in-out';

type Animate = Exclude<Easing, 'ease-out'>

class UIElement {
    animate(x: number, y: number, easing: Easing) {
        if(easing === 'ease-in') { console.log('ease-in'); }
        else if(easing === 'ease-out') { console.log('ease-out'); }
        else { console.log('ease-in-out'); }
    }
}
```

### Générique : Extract

```ts
type Colors = 'Blue' | 'White' | 'Red' | 'Black';

type MyColors = Extract<Colors, 'Blue' | 'White' | 'Red'>;
```

### Générique : NonNullable

```ts
class Car {
    color: 'Green' | 'White' | 'Black'

    paint(color: NonNullable<Car['color']>) { console.log(color); }
}

const myCar = new Car();
myCar.paint('White');
```

### Générique : Parameters

```ts
function fetchUser(id: numer, username: string) {
    console.log(`Fetch user id ${id} | username ${username}`);
}

type FetchUserParams = Parameters<typeof fetchUser>;

function fetchLoggedUser(...params: FetchUserParams) {
    fetchUser(...params);
}

fetchLoggedUser(33, 'Rick');
```

### Générique : ReturnType

```ts
function fetchUser(id: numer, username: string) {
    console.log(`Fetch user id ${id} | username ${username}`);
    return '200 OK';
}

type FetchUserParams = Parameters<typeof fetchUser>;

type FetchUserReturn = ReturnType<typeof fetchUsers>;

function fetchLoggedUser(...params: FetchUserParams) {
    fetchUser(...params);

    let test: FetchUserReturn = '404';
}

fetchLoggedUser(33, 'Rick');
```
