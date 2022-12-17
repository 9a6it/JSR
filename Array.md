#### [:book:](README.md) / `Array`

Свойство / Метод | Синтаксис
:--- | :---
[**`Array.from()`**](#top-arrayfrom) | `Array.from(target)`, `Array.from(target, (el*, i*) => { ... })`
[**`Array.isArray()`**](#top-arrayisarray) | `Array.isArray(target)`
[**`Array.of()`**](#top-arrayof) | `Array.of(el1, el2*, ..., elN*)`
[**`Array.prototype`**](#top-arrayprototype) | `Array.prototype.customPropertyOrMethodName = theCode`
[**`constructor`**](#top-constructor) | `arr.constructor`
[**`length`**](#top-length) | `arr.length`, `arr.length = number`
[**`at()`**](#top-at) | `arr.at(i)`
[**`concat()`**](#top-concat) | `arr1.concat(arr2*/val1*, arr3*/val2*, ..., arrN*/valN*)`
[**`copyWithin()`**](#top-copywithin) | `arr.copyWithin(startInsertIndex, [startCopyIndex* = 0, endCopyIndexAfter* = arr.length))`
[**`entries()`**](#top-entries) | `arr.entries()`
[**`every()`**](#top-every) | `arr.every((el, i*, arr*) => { ... })`
[**`fill()`**](#top-fill) | `arr.fill(val, [startInsertIndex* = 0, endInsertIndexAfter* = arr.length))`
[**`filter()`**](#top-filter) | `arr.filter((el, i*, arr*) => { ... })`
[**`find()`**](#top-find) | `arr.find((el, i*, arr*) => { ... })`
[**`findIndex()`**](#top-findindex) | `arr.findIndex((el, i*, arr*) => { ... })`
[**`findLast()`**](#top-findlast) | `arr.findLast((el, i*, arr*) => { ... })`
[**`findLastIndex()`**](#top-findlastindex) | `arr.findLastIndex((el, i*, arr*) => { ... })`
[**`flat()`**](#top-flat) | `arr.flat(depth*)`
[**`flatMap()`**](#top-flatmap) | `arr.flatMap((el, i*, arr*) => { ... })`
[**`forEach()`**](#top-foreach) | `arr.forEach((el, i*, arr*) => { ... })`
[**`includes()`**](#top-includes) | `arr.includes(searchElement, startSearchIndex* = 0)`
[**`indexOf()`**](#top-indexof) | `arr.indexOf(searchElement, startSearchIndex* = 0)`
[**`join()`**](#top-join) | `arr.join(separator*)`
[**`keys()`**](#top-keys) | `arr.keys()`
[**`lastIndexOf()`**](#top-lastindexof) | `arr.lastIndexOf(searchElement, startReverseSearchIndex* = arr.length)`
[**`map()`**](#top-map) | `arr.map((el, i*, arr*) => { ... })`
[**`pop()`**](#top-pop) | `arr.pop()`
[**`push()`**](#top-push) | `arr.push(el1, el2*, ..., elN*)`
[**`reduce()`**](#top-reduce) | `arr.reduce((acc, el, i*, arr*) => { ... }, initialValue*)`
[**`reduceRight()`**](#top-reduceright) | `arr.reduceRight((acc, el, i*, arr*) => { ... }, initialValue*)`
[**`reverse()`**](#top-reverse) | `arr.reverse()`
[**`shift()`**](#top-shift) | `arr.shift()`
[**`slice()`**](#top-slice) | `arr.slice(startCopyIndex* = 0, endCopyIndexAfter* = arr.length)`
[**`some()`**](#top-some) | `arr.some((el, i*, arr*) => { ... })`
[**`sort()`**](#top-sort) | `arr.sort(compareFunction*)`, `arr.sort((a, b) => a - b)`, `arr.sort((a, b) => b - a)`
[**`splice()`**](#top-splice) | `arr.splice(startInsertOrDeleteIndex, deleteQuantity, insertElement1, insertElement2, ..., insertElementN)`
[**`toLocaleString()`**](#top-tolocalestring) | `arr.toLocaleString(locales*, options*)`
[**`toString()`**](#top-tostring) | `arr.toString()`
[**`unshift()`**](#top-unshift) | `arr.unshift(el1, el2*, ..., elN*)`
[**`values()`**](#top-values) | `arr.values()`

####  [**:top:**](#book--array) `Array.from()`
Возвращает новый массив из массивоподобного (объектов со свойством `length` и элементами по индексным ключам) или итерируемого объектов (объектов, из которых можно достать их элементы, например `Map` или `Set`).
```js
const str = 'Text';
const strToArr = Array.from(str);
console.log(strToArr); // ['T', 'e', 'x', 't']

var map = new Map([[1, 2], [2, 4], [4, 8]]);
const mapToArr = Array.from(map);
console.log(mapToArr); // [[1, 2], [2, 4], [4, 8]]

const set = new Set(['el1', 'el2', 'el3']);
const setToArr = Array.from(set);
console.log(setToArr); // ['el1', 'el2', 'el3']

const str = 'ABCDE';
const indexes = Array.from(str, (el, i) => i);
console.log(indexes); // [0, 1, 2, 3, 4]
```

####  [**:top:**](#book--array) `Array.isArray()`
Возвращает `true`, если объект является массивом и `false`, если он массивом не является.
```js
const arr = '1';
const isArray = Array.isArray(arr);
console.log(isArray); // false
```

####  [**:top:**](#book--array) `Array.of()`
Возвращает новый экземпляр массива `Array` из произвольного числа аргументов, вне зависимости от числа или типа аргумента.
```js
const newArr = Array.of(7);
console.log(newArr); // [7], newArr.length = 1

const newArr = Array.of(1, 2, 3);
console.log(newArr); // [1, 2, 3], newArr.length = 3
```

#### [**:top:**](#book--array) `Array.prototype`
Позволяет добавлять новые свойства и методы к объекту `Array`. При построении свойства все массивы будут задавать свойства и его значение по умолчанию. При построении метода, этот метод будет доступен всем массивам. Может перезатереть встроенные свойства и методы, поэтому нужно быть осторжным с именами.
```js
Array.prototype.typeArr = function() {
  var output = [];
  for (i = 0; i < this.length; i++) {
    output[i] = typeof this[i];
  };
  return output;
};

const arr = ['123', 123, true, 'ECMA', [1, 2], { id: 10 }, undefined, null];
const result = arr.typeArr();
console.log(result); // ['string', 'number', 'boolean', 'string', 'object', 'object', 'undefined', 'object']
```

#### [**:top:**](#book--array) `constructor`
Возвращает `function Array() { [native code] }`. Можно использовать для определения, является ли переменная массивом.
```js
const arr = ['el1', 'el2', 'el3'];
const constructor = arr.constructor;
console.log(constructor); // function Array() { [native code] }
```

#### [**:top:**](#book--array) `length`
Возвращает или устанавливает (меняет исходный массив) количество элементов в массиве.
```js
const arr = ['el1', 'el2', 'el3'];
const length = arr.length;
console.log(length); // 3

const arr = ['el1', 'el2', 'el3'];
arr.length = 2;
console.log(arr); // ['el1', 'el2']
```

#### [**:top:**](#book--array) `at()`
Возвращает элемент массива с заданным индексом.
```js
const arr = ['el1', 'el2', 'el3'];
const lastEl = arr.at(-1);
console.log(lastEl); // 'el3'
```

####  [**:top:**](#book--array) `concat()`
Возвращает новый массив, содержащий значения объединенных массивов (поверхностную копию) и/или значения.
```js
const arr1 = ['el1', 'el2', 'el3'];
const arr2 = [1, 2, 3];
const arr3 = [true, false];
const newArr = arr1.concat(arr2, arr3, 'newEl');
console.log(newArr); // ['el1', 'el2', 'el3', 1, 2, 3, true, false, 'newEl']
```

####  [**:top:**](#book--array) `copyWithin()`
Копирует элементы внутри массива (меняет исходный массив), из указанного диапазона индексов, и вставляет, начиная с указанного индекса.
```js
const arr = ['el1', 'el2', 'el3', 'el4', 'el5'];
arr.copyWithin(2);
console.log(arr); // ['el1', 'el2', 'el1', 'el2', 'el3']

const arr = ['el1', 'el2', 'el3', 'el4', 'el5'];
arr.copyWithin(0, 2);
console.log(arr); // ['el3', 'el4', 'el5', 'el4', 'el5']

const arr = ['el1', 'el2', 'el3', 'el4', 'el5'];
arr.copyWithin(1, 2, 3);
console.log(arr); // ['el1', 'el3', 'el3', 'el4', 'el5']
```

####  [**:top:**](#book--array) `entries()`
Возвращает итератор массива `Array Iterator`, который содержит пары ключ/значение для каждого индекса в массиве.
```js
const arr = ['el1', 'el2', 'el3'];
const iterator = arr.entries();
console.log(iterator); // Array Iterator {}
for (let item of iterator) {
  console.log(item); // [0, 'el1'] [1, 'el2'] [2, 'el3']
}
```

####  [**:top:**](#book--array) `every()`
Возвращает `true`, если все элементы массива удовлетворяют условия функции. В противном случае возвращается `false`. Возвращает `true` при любом условии для пустого массива.
```js
const arr = [19, 21, 32, 24, 35];
const isAllAdult = arr.every(el => el >= 18);
console.log(isAllAdult); // true
```

####  [**:top:**](#book--array) `fill()`
Заполняет все элементы массива от начального до конечного индексов одним значением. Меняет исходный массив.
```js
const arr = ['el1', 'el2', 'el3', 'el4', 'el5'];
arr.fill('newValue');
console.log(arr); // ['newValue', 'newValue', 'newValue', 'newValue', 'newValue']

const arr = ['el1', 'el2', 'el3', 'el4', 'el5'];
arr.fill('newValue', 1, 4);
console.log(arr); // ['el1', 'newValue', 'newValue', 'newValue', 'el5']
```

####  [**:top:**](#book--array) `filter()`
Возвращает отфильтрованный массив со всеми элементами, которые удовлетворяют условия функции. В противном случае возвращается пустой массив.
```js
const arr = ['el1', 'el2', 'el3', 1, 2, 3, true, false];
const filteredArr = arr.filter(el => typeof el === 'number');
console.log(filteredArr); // [1, 2, 3]
```

####  [**:top:**](#book--array) `find()`
Возвращает значение первого найденного в массиве элемента, которое удовлетворяет условия функции. В противном случае возвращается `undefined`.
```js
const arr = [1, 2, 3, 4, 5];
const firstValue = arr.find(el => el > 2);
console.log(firstValue); // 3
```

####  [**:top:**](#book--array) `findIndex()`
Возвращает индекс первого найденного в массиве элемента, который удовлетворяет условия функции. В противном случае возвращается -1.
```js
const arr = [1, 2, 3, 4, 5];
const firstIndex = arr.findIndex(el => el > 2);
console.log(firstIndex); // 2
```

####  [**:top:**](#book--array) `findLast()`
Возвращает значение первого найденного элемента в массиве - с конца массива, которое удовлетворяет условия функции. Работает наоборот методу `find()`. В противном случае возвращается `undefined`.
```js
const arr = [1, 2, 3, 4, 5];
const lastValue = arr.findLast(el => el > 2);
console.log(lastValue); // 5
```

####  [**:top:**](#book--array) `findLastIndex()`
Возвращает индекс первого найденного в массиве элемента - с конца массива, который удовлетворяет условия функции. Работает наоборот методу `findIndex()`. В противном случае возвращается -1.
```js
const arr = [1, 2, 3, 4, 5];
const lastIndex = arr.findLastIndex(el => el > 2);
console.log(lastIndex); // 4
```

####  [**:top:**](#book--array) `flat()`
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

####  [**:top:**](#book--array) `flatMap()`
Возвращает массив, сформированный путем применения заданной функции к каждому элементу массива, а затем сведения результата на один уровень. Идентичен `map()`, за которым следует `flat()` глубины (1), но немного более эффективен, чем вызов этих двух методов по отдельности - `arr.map(...args).flat()`. Но если глубина больше 1, то лучше сначала выровнить с помошью `flat()`.
```js
const arr = [1, 2, [3], [4, 5], 6, []];
const flatArr = arr.flatMap(el => el);
console.log(flatArr); // [1, 2, 3, 4, 5, 6]
```

####  [**:top:**](#book--array) `forEach()`
Вызывает функцию один раз для каждого элемента массива по порядку. Не выполняет функцию для элементов массива без значений. А также не возвращает результат выполнения, `undefined`.
```js
const arr = [1, 2, 3, 4, 5];
arr.forEach(el => console.log(el * 2)); // 2, 4, 6, 8, 10
```

####  [**:top:**](#book--array) `includes()`
Возвращает результат наличия искомого элемента в массиве.
```js
const arr = [1, true, NaN, 'el4'];
const hasNan = arr.includes(NaN);
console.log(hasNan); // true

const arr = [1, true, NaN, 'el4'];
const hasNan = arr.includes(NaN, -1);
console.log(hasNan); // false
```

####  [**:top:**](#book--array) `indexOf()`
Возвращает первый индекс, по которому данный элемент был найден в массиве или -1, если такого индекса нет. В отличие от `includes()`, для `NaN`, независимо от наличия будет возвращаться -1.
```js
const arr = [1, true, NaN, 'el4'];
const firstIndexOfElement = arr.indexOf(NaN);
console.log(firstIndexOfElement); // -1

const arr = [1, true, NaN, 'el4'];
const firstIndexOfElement = arr.indexOf('el4', 2);
console.log(firstIndexOfElement); // 3
```

####  [**:top:**](#book--array) `join()`
Возвращает, объединив все элементы массива (или массивоподобного объекта) в одну строку. Любой элемент массива, который имеет значение `undefined` или `null`, будет преобразован в пустую строку.
```js
const arr = [1, 2, 3, 4, 5];
const arrToStr = arr.join();
console.log(arrToStr); // '1,2,3,4,5'

const arr = [1, 2, 3, 4, 5];
const arrToStr = arr.join('');
console.log(arrToStr); // '12345'

const arr = ['el1', 'el2', NaN, null, undefined];
const arrToStr = arr.join('-');
console.log(arrToStr); // 'el1-el2-NaN--'
```

####  [**:top:**](#book--array) `keys()`
Возвращает итератор массива `Array Iterator`, содержащий ключи каждого индекса в массиве.
```js
const arr = ['el1', 'el2'];
const iterator = arr.keys();
console.log(iterator); // Array Iterator {}
console.log(iterator.next()); // { value: 0, done: false }
console.log(iterator.next()); // { value: 1, done: false }
console.log(iterator.next()); // { value: undefined, done: true }

const arr = ['el1', 'el2', 'el3'];
const iterator = arr.keys();
for (const i of iterator) {
  console.log(i); // 0 1 2
}
```

####  [**:top:**](#book--array) `lastIndexOf()`
Возвращает последний индекс, по которому данный элемент может быть найден в массиве или -1, если такого индекса нет. Массив просматривается от конца к началу.
```js
const arr = ['JS', 'HTML', 'JS', 'CSS'];
const lastIndexOfElement = arr.lastIndexOf('JS');
console.log(lastIndexOfElement); // 2
const lastIndexOfElement = arr.lastIndexOf('JS', 1);
console.log(lastIndexOfElement); // 0
```

####  [**:top:**](#book--array) `map()`
Возвращает новый массив с результатом вызова указанной функции для каждого элемента массива.
```js
const arr = [4, 9, 16, 25];
const newArr = arr.map(Math.sqrt);
console.log(newArr); // [2, 3, 4, 5]

const arr = ['el1', 'el2', 'el3', 'el4', 'el5'];
const auxArr = arr.map(el => el.charAt(0).toUpperCase() + el.slice(1).toLowerCase());
const newArr = auxArr.map(el => 'new' + el);
console.log(newArr); // ['newEl1', 'newEl2', 'newEl3', 'newEl4', 'newEl5']
```

####  [**:top:**](#book--array) `pop()`
Удаляет последний элемент из массива и возвращает его значение.
```js
const arr = ['el1', 'el2', 'el3', 'el4', 'el5'];
const delValue1 = arr.pop();
console.log(delValue1); // 'el5'
const delValue2 = arr.pop();
console.log(delValue2); // 'el4'
```

####  [**:top:**](#book--array) `push()`
Добавляет один или более элементов в конец массива и возвращает новую длину массива.
```js
const arr = [];
const newArr = arr.push('el1', 'el2');
console.log(newArr); // 2
```

####  [**:top:**](#book--array) `reduce()`
Применяет функцию-редюсер к каждому элементу массива (слева-направо), возвращая одно результирующее значение. Функция не будет вызвана для удалённых, или пропущенных элементов массива. Если массив имеет только один элемент (независимо от позиции) и не указано `initialValue` (значение, используемое в качестве первого аргумента первого вызова функции обратного вызова), или если `initialValue` предоставляется, но массив пуст, то значение этого элемента будет возвращено без вызова функции.
```js
const arr = [5, 10, 15];
const sum = arr.reduce((acc, el) => acc + el);
console.log(sum); // 30

const arr = [5, 10, 15];
const doubled = arr.reduce((acc, el) => {
  acc.push(el * 2);
  return acc;
}, []);
console.log(doubled); // [10, 20, 30]

const bankAccounts = [
  { id: '123', amount: 19 },
  { id: '345', amount: 33 },
  { id: '567', amount: 4 },
  { id: '789', amount: 20 },
];
const totalAmount = bankAccounts.reduce((sum, currentAccount) => sum + currentAccount.amount, 0);
console.log(totalAmount); // 76
```

####  [**:top:**](#book--array) `reduceRight()`
Применяет функцию-редюсер к каждому элементу массива (справа-налево), возвращая одно результирующее значение. Функция не будет вызвана для удалённых, или пропущенных элементов массива. Если массив имеет только один элемент (независимо от позиции) и не указано `initialValue` (значение, используемое в качестве первого аргумента первого вызова функции обратного вызова), или если `initialValue` предоставляется, но массив пуст, то значение этого элемента будет возвращено без вызова функции.
```js
const arr = [5, 10, 15];
const doubled = arr.reduceRight((acc, el) => {
  acc.push(el * 2);
  return acc;
}, []);
console.log(doubled); // [30, 20, 10]
```

####  [**:top:**](#book--array) `reverse()`
Меняет массив, обращая порядок следования элементов массива наоборот. Первый элемент массива становится последним, а последний - первым.
```js
const arr = ['el1', 'el2', 'el3', 'el4', 'el5'];
const reverseArr = arr.reverse();
console.log(reverseArr); // ['el5', 'el4', 'el3', 'el2', 'el1']
```

####  [**:top:**](#book--array) `shift()`
Меняет массив, удаляя первый элемент из массива и возвращает его значение. Этот метод меняет длину массива. Если длина массива равно `length = 0`, вернётся значение `undefined`.
```js
const arr = ['el1', 'el2', 'el3', 'el4', 'el5'];
const delValue = arr.shift();
console.log(delValue); // el1
console.log(arr); // ['el2', 'el3', 'el4', 'el5']
```

####  [**:top:**](#book--array) `slice()`
Возвращает новый массив, содержащий копию части исходного массива.
```js
const arr = ['el1', 'el2', 'el3', 'el4', 'el5'];
const newArr = arr.slice();
console.log(newArr); // ['el1', 'el2', 'el3', 'el4', 'el5']

const arr = ['el1', 'el2', 'el3', 'el4', 'el5'];
const newArr = arr.slice(1, 4);
console.log(newArr); // ['el2', 'el3', 'el4']
```

####  [**:top:**](#book--array) `some()`
Проверяет, удовлетворяет ли какой-либо элемент массива условию, заданному в передаваемой функции. Возвращает `true` и останавливается, если функция возвращает `true` для одного из элементов массива или возвращает `false`, если функция возвращает `false` для всех элементов массива. Также возвращает `false` при любом условии для пустого массива.
```js
const arr = [18, 21, 31, 14, 25];
const hasOneKid = arr.some(el => el < 18);
console.log(hasOneKid); // true
```

####  [**:top:**](#book--array) `sort()`
На месте сортирует элементы массива и возвращает отсортированный массив. Если функция сравнения не предоставляется, элементы сортируются путём преобразования их в строки и сравнения строк в порядке следования кодовых точек Unicode.
```js
const arr = ['el1', 'el2', true, false, 1, 0];
const sortedArr = arr.sort();
console.log(sortedArr); // [0, 1, 'el1', 'el2', false, true]

const arr = [204, 155, 94, 199, 67];
const lowToHigh = arr.sort((a, b) => a - b);
console.log(lowToHigh); // [67, 94, 155, 199, 204]

const arr = [204, 155, 94, 199, 67];
const highToLow = arr.sort((a, b) => b - a);
console.log(highToLow); // [204, 199, 155, 94, 67]
```

####  [**:top:**](#book--array) `splice()`
Меняет массив за счёт удаления существующих элементов, и/или добавления новых элементов в массив, и возвращает удаленные элементы в новом массиве.
```js
const arr = ['el1', 'el2', 'el3', 'el4', 'el5'];
const delEls = arr.splice(2, 0, 'newValue1', 'newValue2');
console.log(arr); // ['el1', 'el2', 'newValue1', 'newValue2', 'el3', 'el4', 'el5']
console.log(delEls); // []

const arr = ['el1', 'el2', 'el3', 'el4', 'el5'];
const delEls = arr.splice(2, 2);
console.log(arr); // ['el1', 'el2', 'el5']
console.log(delEls); // ['el3', 'el4']
```

#### [**:top:**](#book--array) `toLocaleString()`
Возвращает строковое представление элементов массива. Элементы преобразуются в строки с использованием своих собственных методов `toLocaleString` и эти строки разделяются локале-зависимой строкой (например, запятой ",").
```js
const arr = [1, 2, 'El', true];
const output = arr.toLocaleString();
console.log(output); // '1,2,El,true'
typeof output; // 'string'
```

#### [**:top:**](#book--array) `toString()`
Возвращает строковое представление элементов массива безо всяких параметров.
```js
const arr = [1, 2, 3, false, 'lastEl'];
const arrToStr = arr.toString();
console.log(arrToStr); // '1,2,3,false,lastEl'
```

#### [**:top:**](#book--array) `unshift()`
Добавляет переданные элементы в начало массива и возвращает новую длину массива.
```js
const arr = ['el1', 'el2', 'el3'];
const newLength = arr.unshift('newValue');
console.log(newLength); // 4
console.log(arr); // ['newValue', 'el1', 'el2', 'el3']
```

#### [**:top:**](#book--array) `values()`
Возвращает итератор массива `Array Iterator`, содержащий значения для каждого индекса в массиве.
```js
const arr = ['el1', 'el2', 'el3'];;
const iterator = arr.values();
console.log(iterator); // Array Iterator {}
console.log(iterator.next().value); // el1
console.log(iterator.next().value); // el2
console.log(iterator.next().value); // el3
```
