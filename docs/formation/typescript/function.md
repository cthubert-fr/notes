---
layout: default
title: "Fonction - Typescript"
permalink: /formation/typescript/function/
lang: fr
my_menu: menu-typescript.html
---

## Fonction

```ts
function ageIn3Years(age: number) {
    return age + 3;
}

//
// Autre écriture possible
const ageIn3Years = (age: number) => {
    return age + 3;
}

// Dans les des deux déclarations précédentes :
// * le type de retour est géré par inférence

console.log(typeof ageIn3Years(30));

//
// Exemple de type de retour forcer à la déclaration
// (non recommandé, il vaut mieux laisser faire l'inférence)
function ageIn3Years(age: number) : number {
    return age + 3;
}
```

```ts
function ageIn3Years(age: number) {
    return age + 3;
}

//
// Utilisation du type Function
function showText(arg) {
    console.log(arg);
}

let maFonctionTest: Function;
maFonctionTest = ageIn3Years;
console.log('Test 1 ', maFonctionTest(30)); // 33

maFonctionTest = showText;
console.log('Test 2 ', maFonctionTest(30)); // Erreur !! maFonctionTest n'est pas une fonction

//
// Autre exemple
let maFonction: (age: number) => number;
maFonction = ageIn3Years;
```

```ts
//
// Fonction sans retour (void)
function showMessage() {
    console.log('Coucou');
}

console.log(showMessage()); // affiche : undefined
```

### Paramètres optionnel et par défaut

#### Exemple problématique

```ts
function buildName(firstName: string, lastName: string) {
    return firstName + ' ' + lastName;
}

let result1 = buildName('Bob');
console.log(result1); // Bob undefined
```

#### Solution : argument facultatif

```ts
function buildName(firstName: string, lastName?: string) {
    if(lastName) { return firstName + ' ' + lastName; }
    else { return firstName; }
}

let result1 = buildName('John', 'Wick');
console.log(result1); // John Wick

let result1 = buildName('Bob');
console.log(result1); // Bob
```

#### Autre solution : argument par défaut

```ts
function buildName(firstName: string, lastName = 'Wick') {
    return firstName + ' ' + lastName;
}

let result1 = buildName('John');
console.log(result1); // John Wick
//
// même résultat avec l'appel suivant :
//let result1 = buildName('John', undefined);
```

Note : le paramètre par défaut peut être définit sur le premier paramètre, dans ce cas nécessiter de passer undefined pour utiliser la valeur par défaut (voir exemple).

```ts
function buildName(firstName = 'John', lastName: string) {
    return firstName + ' ' + lastName;
}

let result1 = buildName(undefined, 'Wick');
console.log(result1); // John Wick
```

### Type : rest

```ts
let colors = function(arg1: string, arg2: string, arg2: string) {
    for(let i in arguments) {
        console.log(arguments[i]);
    }
}

colors('Blue', 'White', 'Red');
```

```ts
const divColors = document.getElementById("colors");

let colors = function (arg1: string, ...restOfColors: string[]) {
    const h1 = document.createElement('h1');
    h1.innerHTML = `Titre : ${arg1}`;
    divColors.appendChild(h1);
    
    const ul = document.createElement('ul');
    for(let i in restOfColors) {
        let li = document.createElement('li');
        li.innerHTML = restOfColors[i];
        ul.appendChild(li);
    }
    divsColors.appendChild(ul);
}

colors('Liste 1 :', 'Blue', 'White', 'Red');

let colorsTest: (arg1: string, ...rest: string[]) => string = colors;
```

### Fonction callback

```ts
function test(age: number, show: (arg: number) => void) {
    const ageIn3Years = age + 3;
    show(ageIn3Years);
}

test(30, (age) => console.log(age));
```

### Union type

```ts
function test(arg1: number | string, arg2: number | string) {
    let result;
    if(typeof arg1 == 'number' && typeof arg2 === 'number') {
        result = arg1 + arg2;
    } else if(typeof arg1 == 'string' && typeof arg2 == 'string') {
        result = arg1 + arg2;
    } else {
        result = arg1.toString() + arg2.toString();
    }
    return result;
}

console.log(test(13, 20)); // 33
console.log(test("Bonjour ", 33)); // Bonjour 33
```

### Literal type

```ts
function total(arg1: number, arg2: number, totalversion: 'getStringValue') {
    let result;
    if(totalversion == 'getStringVersion') {
        result = arg1.toString() + arg2.toString();
    } else {
        result = arg1 + arg2;
    }
    return result;
}

const totalOne = total(20, 22, 'getStringValue');
```
