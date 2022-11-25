#### [`constructor`](#constructor) ES1

#### [`length`](#length) ES1

#### [`at()`](#at) ES13

#### [`concat()`](#concat) ES1

#### [`copyWithin()`](#copywithin) ES6

#### [`entries()`](#entries) ES6

#### [`every()`](#every) ES5

#### [`fill()`](#fill) ES6

#### [`filter()`](#filter) ES5

#### [`find()`](#find) ES6

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
Возвращает или устанавливает (меняет исходный массив) количество элементов в массиве.
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
arr.at(i)
```
```js
const arr = ['elem1', 'elem2', 'elem3'];
const lastElem = arr.at(-1);
console.log(lastElem); // 'elem3'
```

#### `concat()`
Возвращает новый массив, содержащий значения объединенных массивов (поверхностную копию) и/или значения.
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

#### `copyWithin()`
Копирует элементы внутри массива (меняет исходный массив), из указанного диапазона индексов, и вставляет, начиная с указанного индекса.
```js
arr.copyWithin(startPasteIndex*, [startCopyIndex = 0, endCopyIndexAfter = arr.length))
```
```js
const arr = ['elem1', 'elem2', 'elem3', 'elem4', 'elem5'];
arr.copyWithin(2);
console.log(arr); // ['elem1', 'elem2', 'elem1', 'elem2', 'elem3']

const arr = ['elem1', 'elem2', 'elem3', 'elem4', 'elem5'];
arr.copyWithin(0, 2);
console.log(arr); // ['elem3', 'elem4', 'elem5', 'elem4', 'elem5']

const arr = ['elem1', 'elem2', 'elem3', 'elem4', 'elem5'];
arr.copyWithin(1, 2, 3);
console.log(arr); // ['elem1', 'elem3', 'elem3', 'elem4', 'elem5']
```

#### `entries()`
Возвращает объект итератора массива `Array Iterator`, который содержит пары ключ/значение для каждого индекса в массиве.
```js
arr.entries()
```
```js
const arr = ['elem1', 'elem2', 'elem3'];
const iterator = arr.entries();
console.log(iterator); // Array Iterator {}
for (let item of iterator) {
  console.log(item); // [0, 'elem1'] [1, 'elem2'] [2, 'elem3']
}
```

#### `every()`
Возвращает `true`, если все элементы массива удовлетворяют условия функции. В противном случае возвращается `false`. Возвращает `true` при любом условии для пустого массива.
```js
arr.every((elem*, i, arr) => { ... })
```
```js
const arr = [19, 21, 32, 24, 35];
const isAllAdult = arr.every(elem => elem >= 18);
console.log(isAllAdult); // true
```

#### `fill()`
Заполняет все элементы массива от начального до конечного индексов одним значением. Меняет исходный массив.
```js
arr.fill(value*, [startIndex = 0, endIndexAfter = arr.length))
```
```js
const arr = ['elem1', 'elem2', 'elem3', 'elem4', 'elem5'];
arr.fill('newValue');
console.log(arr); // ['newValue', 'newValue', 'newValue', 'newValue', 'newValue']

const arr = ['elem1', 'elem2', 'elem3', 'elem4', 'elem5'];
arr.fill('newValue', 1, 4);
console.log(arr); // ['elem1', 'newValue', 'newValue', 'newValue', 'elem5']
```

#### `filter()`
Возвращает отфильтрованный массив со всеми элементами, которые удовлетворяют условия функции. В противном случае возвращается пустой массив.
```js
arr.filter((elem*, i, arr) => { ... })
```
```js
const arr = ['elem1', 'elem2', 'elem3', 1, 2, 3, true, false];
const filteredArr = arr.filter(elem => typeof elem === 'number');
console.log(filteredArr); // [1, 2, 3]
```

#### `find()`
Возвращает значение первого найденного в массиве элемента, которое удовлетворяет условия функции. В противном случае возвращается `undefined`.
```js
arr.find((elem*, i, arr) => { ... })
```
```js
const arr = [1, 2, 3, 4, 5];
const firstValue = arr.find(elem => elem > 2);
console.log(firstValue); // 3
```
