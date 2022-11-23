#### [`constructor`](#constructor) ES1

#### [`length`](#length) ES1

#### [`at()`](#at) ES13

#### [`concat()`](#concat) ES1

#### [`copyWithin()`](#copywithin.md)

#### `constructor`
Возвращает `function Array() { [native code] }`. Можно использовать для определения, является ли переменная массивом.
```js
arr.constructor
```
```js
const arr = ['elem1', 'elem2', 'elem3'];
const constructor = arr.constructor;
console.log(constructor); // function Array() { [native code] }
```

#### `length`
Устанавливает или возвращает количество элементов в массиве.
```js
arr.length
arr.length = number
```
```js
const arr = ['elem1', 'elem2', 'elem3'];
const length = arr.length;
console.log(length); // 3

const arr = ['elem1', 'elem2', 'elem3'];
arr.length = 2;
console.log(arr); // ['elem1', 'elem2']
```

#### `at()`
Возвращает элемент массива с заданным индексом.
```js
arr.at(index)
```
```js
const arr = ['elem1', 'elem2', 'elem3'];
const lastElem = arr.at(-1);
console.log(lastElem); // 'elem3'
```

#### `concat()`
Возвращает новый массив, содержащий значения объединенных массивов (поверхностную копию) и/или значений.
```js
arr1*.concat(arr2, arr3, ..., arrN)
arr1*.concat(value1, value2, ..., valueN)
```
```js
const arr1 = ['elem1', 'elem2', 'elem3'];
const arr2 = [1, 2, 3];
const arr3 = [true, false];
const newArr = arr1.concat(arr2, arr3, 'newElem');
console.log(newArr); // ['elem1', 'elem2', 'elem3', 1, 2, 3, true, false, 'newElem']
```

