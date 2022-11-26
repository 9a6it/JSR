Свойство / Метод | Синтаксис
:--- | :---
[**`constructor`**](#constructor) | `arr.constructor`
[**`length`**](#length) | `arr.length`, `arr.length = number`
[**`at()`**](#at) | `arr.at(i)`
[**`concat()`**](#concat) | `arr1*.concat(arr2/value1, arr3/value2, ..., arrN//valueN)`
[**`copyWithin()`**](#copywithin) | `arr.copyWithin(startPasteIndex*, [startCopyIndex = 0, endCopyIndexAfter = arr.length))`
[**`entries()`**](#entries) | `arr.entries()`
[**`every()`**](#every) | `arr.every((elem*, i, arr) => { ... })`
[**`fill()`**](#fill) | `arr.fill(value*, [startPasteIndex = 0, endPasteIndexAfter = arr.length))`
[**`filter()`**](#filter) | `arr.filter((elem*, i, arr) => { ... })`
[**`find()`**](#find) | `arr.find((elem*, i, arr) => { ... })`
[**`findIndex()`**](#findindex) | `arr.findIndex((elem*, i, arr) => { ... })`
[**`findLast()`**](#findlast) | `arr.findLast((elem*, i, arr) => { ... })`
[**`findLastIndex()`**](#findlastindex) | `arr.findLastIndex((elem*, i, arr) => { ... })`
[**`flat()`**](#flat) | `arr.flat()`, `arr.flat(depth)`
[**`flatMap()`**](#flatmap) | `arr.flatMap((elem*, i, arr) => { ... })`
[**`forEach()`**](#foreach) | `arr.forEach((elem*, i, arr) => { ... })`


#### `constructor`
Возвращает `function Array() { [native code] }`. Можно использовать для определения, является ли переменная массивом.
```js
const arr = ['elem1', 'elem2', 'elem3'];
const constructor = arr.constructor;
console.log(constructor); // function Array() { [native code] }
```

#### `length`
Возвращает или устанавливает (меняет исходный массив) количество элементов в массиве.
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
const arr = ['elem1', 'elem2', 'elem3'];
const lastElem = arr.at(-1);
console.log(lastElem); // 'elem3'
```

#### `concat()`
Возвращает новый массив, содержащий значения объединенных массивов (поверхностную копию) и/или значения.
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
const arr = [19, 21, 32, 24, 35];
const isAllAdult = arr.every(elem => elem >= 18);
console.log(isAllAdult); // true
```

#### `fill()`
Заполняет все элементы массива от начального до конечного индексов одним значением. Меняет исходный массив.
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
const arr = ['elem1', 'elem2', 'elem3', 1, 2, 3, true, false];
const filteredArr = arr.filter(elem => typeof elem === 'number');
console.log(filteredArr); // [1, 2, 3]
```

#### `find()`
Возвращает значение первого найденного в массиве элемента, которое удовлетворяет условия функции. В противном случае возвращается `undefined`.
```js
const arr = [1, 2, 3, 4, 5];
const firstValue = arr.find(elem => elem > 2);
console.log(firstValue); // 3
```

#### `findIndex()`
Возвращает индекс первого найденного в массиве элемента, который удовлетворяет условия функции. В противном случае возвращается -1.
```js
const arr = [1, 2, 3, 4, 5];
const firstIndex = arr.findIndex(elem => elem > 2);
console.log(firstIndex); // 2
```

#### `findLast()`
Возвращает значение первого найденного элемента в массиве - с конца массива, которое удовлетворяет условия функции. Работает наоборот методу `find()`. В противном случае возвращается `undefined`.
```js
const arr = [1, 2, 3, 4, 5];
const lastValue = arr.findLast(elem => elem > 2);
console.log(lastValue); // 5
```

#### `findLastIndex()`
Возвращает индекс первого найденного в массиве элемента - с конца массива, который удовлетворяет условия функции. Работает наоборот методу `findIndex()`. В противном случае возвращается -1.
```js
const arr = [1, 2, 3, 4, 5];
const lastIndex = arr.findLastIndex(elem => elem > 2);
console.log(lastIndex); // 4
```

#### `flat()`
Возвращает массив со всеми элементами вложенного массива, объединенными в него рекурсивно до указанной глубины. Если задать `Infinity` в качестве значения глубины, то можно не считать вложенность и открывать массивы любой глубины.
```js
const arr = [1, 2, [3, 4, [5, 6]]];
const flatArr = arr.flat();
console.log(flatArr); // [1, 2, 3, 4, [5, 6]]

const arr = [1, 2, [3, 4, [5, 6]]];
const flatArr = arr.flat(2);
console.log(flatArr); // [1, 2, 3, 4, 5, 6]

const arr = [1, 2, [3, 4, [5, 6, [7, 8, [9, 10]]]]];
const flatArr = arr.flat(Infinity);
console.log(flatArr); // [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

#### `flatMap()`
Возвращает массив, сформированный путем применения заданной функции к каждому элементу массива, а затем сведения результата на один уровень. Идентичен `map()`, за которым следует `flat()` глубины (1), но немного более эффективен, чем вызов этих двух методов по отдельности - `arr.map(...args).flat()`. Но если глубина больше 1, то лучше сначала выровнить с помошью `flat()`.
```js
const arr = [1, 2, [3], [4, 5], 6, []];
const flatArr = arr.flatMap(elem => elem);
console.log(flatArr); // [1, 2, 3, 4, 5, 6]
```

#### `forEach()`
Вызывает функцию один раз для каждого элемента массива по порядку. Не выполняет функцию для элементов массива без значений. А также не возвращает результат выполнения - `undefined`.
```js
const arr = [1, 2, 3, 4, 5];
arr.forEach(elem => console.log(elem *2)); // 2, 4, 6, 8, 10
```

#### `from()`
Возвращает новый массив из массивоподобного (объектов со свойством `length` и элементами по индексным ключам) или итерируемого объектов (объектов, из которых можно достать их элементы, например `Map` или `Set`).
