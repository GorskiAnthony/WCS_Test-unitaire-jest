# Les test unitaire

Nous allons voir comment utiliser les test unitaire avec Jest.

## Installation

```bash
npm install --save-dev jest
```

## Configuration

```json
{
	"scripts": {
		"test": "jest"
	}
}
```

Avec l'option --coverage, nous pouvons voir le pourcentage de couverture de nos tests sur une page web.

```json
{
	"scripts": {
		"test": "jest --coverage"
	}
}
```

## Documentation

[https://jestjs.io/docs/en/getting-started](https://jestjs.io/docs/en/getting-started)

## Exemple

```js
// index.js
function sum(a, b) {
	return a + b;
}

module.exports = sum;
```

```js
// index.test.js
const sum = require("./index");

test("adds 1 + 2 to equal 3", () => {
	expect(sum(1, 2)).toBe(3);
});
```

## Exemple avec un objet

```js
// index.js
function sum(a, b) {
	return a + b;
}

function sumObject(obj) {
	return obj.a + obj.b;
}

module.exports = {
	sum,
	sumObject,
};
```

```js
// index.test.js
const { sum, sumObject } = require("./index");

test("adds 1 + 2 to equal 3", () => {
	expect(sum(1, 2)).toBe(3);
});

test("adds 1 + 2 to equal 3", () => {
	expect(sumObject({ a: 1, b: 2 })).toBe(3);
});
```

## Exemple avec un tableau

```js
// index.js
function sum(a, b) {
	return a + b;
}

function sumObject(obj) {
	return obj.a + obj.b;
}

function sumArray(arr) {
	return arr[0] + arr[1];
}

module.exports = {
	sum,
	sumObject,
	sumArray,
};
```

```js
// index.test.js

const { sum, sumObject, sumArray } = require("./index");

test("adds 1 + 2 to equal 3", () => {
	expect(sum(1, 2)).toBe(3);
});

test("adds 1 + 2 to equal 3", () => {
	expect(sumObject({ a: 1, b: 2 })).toBe(3);
});

test("adds 1 + 2 to equal 3", () => {
	expect(sumArray([1, 2])).toBe(3);
});
```

Etc.

## Anatomie d'un test

```js
test("description du test", () => {
	expect(1 + 2).toBe(3);
});
```

## Matcher

Si vous souhaitez voir les matcher, vous avez la documentation ici :
[https://jestjs.io/docs/en/using-matchers](https://jestjs.io/docs/en/using-matchers)
