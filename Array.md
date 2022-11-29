Свойство / Метод | Синтаксис
:--- | :---
[**`constructor`**](#constructor) | `arr.constructor`
[**`length`**](#length) | `arr.length`, `arr.length = number`
[**`at()`**](#at) | `arr.at(i)`
[**`concat()`**](#concat) | `arr1.concat(arr2*/value1*, arr3*/value2*, ..., arrN*//valueN*)`
[**`copyWithin()`**](#copywithin) | `arr.copyWithin(startInsIndex, [startCopyIndex* = 0, endCopyIndexAfter* = arr.length))`
[**`entries()`**](#entries) | `arr.entries()`
[**`every()`**](#every) | `arr.every((el, i*, arr*) => { ... })`
[**`fill()`**](#fill) | `arr.fill(value, [startInsIndex* = 0, endInsIndexAfter* = arr.length))`
[**`filter()`**](#filter) | `arr.filter((el, i*, arr*) => { ... })`
[**`find()`**](#find) | `arr.find((el, i*, arr*) => { ... })`
[**`findIndex()`**](#findindex) | `arr.findIndex((el, i*, arr*) => { ... })`
[**`findLast()`**](#findlast) | `arr.findLast((el, i*, arr*) => { ... })`
[**`findLastIndex()`**](#findlastindex) | `arr.findLastIndex((el, i*, arr*) => { ... })`
[**`flat()`**](#flat) | `arr.flat(depth*)`
[**`flatMap()`**](#flatmap) | `arr.flatMap((el, i*, arr*) => { ... })`
[**`forEach()`**](#foreach) | `arr.forEach((el, i*, arr*) => { ... })`
[**`from()`**](#from) | `Array.from(arr)`, `Array.from(arr, (el*, i*) => { ... })`
[**`includes()`**](#includes) | `arr.includes(searchElement, startSearchIndex* = 0)`
[**`indexOf()`**](#indexof) | `arr.indexOf(searchElement, startSearchIndex* = 0)`
[**`Array.isArray()`**](#arrayisarray) | `Array.isArray(target)`
[**`join()`**](#join) | `arr.join(separator*)`
[**`keys()`**](#keys) | `arr.keys()`
[**`lastIndexOf()`**](#lastindexof) | `arr.lastIndexOf(searchElement, startReverseSearchIndex* = arr.length)`
[**`map()`**](#map) | `arr.map((el, i*, arr*) => { ... })`
[**`Array.of()`**](#arrayof) | `Array.of(el1, el2*, ..., elN*)`
[**`pop()`**](#pop) | `arr.pop()`
[**`push()`**](#push) | `arr.push(el1, el2*, ..., elN*)`
[**`reduce()`**](#reduce) | `arr.reduce((acc, el, i*, arr*) => { ... }, initValue*)`
[**`reduceRight()`**](#reduceright) | `arr.reduceRight((acc, el, i*, arr*) => { ... }, initlValue*)`
[**`reverse()`**](#reverse) | `arr.reverse()`
[**`shift()`**](#shift) | `arr.shift()`
[**`slice()`**](#slice) | `arr.slice(startCopyIndex* = 0, endCopyIndexAfter* = arr.length)`
[**`some()`**](#some) | `arr.some((el, i*, arr*) => { ... })`
[**`sort()`**](#sort) | `arr.sort(compareFn*)`, `arr.sort((a, b) => a - b)`
[**`splice()`**](#splice) | `arr.splice(startInsOrDelIndex, delQt, insEl1, insEl2, ..., insElN)`


#### `constructor`
Возвращает `function Array() { [native code] }`. Можно использовать для определения, является ли переменная массивом.
```js
const arr = ['el1', 'el2', 'el3'];
const constructor = arr.constructor;
console.log(constructor); // function Array() { [native code] }
```

#### `length`
Возвращает или устанавливает (меняет исходный массив) количество элементов в массиве.
```js
const arr = ['el1', 'el2', 'el3'];
const length = arr.length;
console.log(length); // 3

const arr = ['el1', 'el2', 'el3'];
arr.length = 2;
console.log(arr); // ['el1', 'el2']
```

#### `at()`
Возвращает элемент массива с заданным индексом.
```js
const arr = ['el1', 'el2', 'el3'];
const lastEl = arr.at(-1);
console.log(lastEl); // 'el3'
```

#### `concat()`
Возвращает новый массив, содержащий значения объединенных массивов (поверхностную копию) и/или значения.
```js
const arr1 = ['el1', 'el2', 'el3'];
const arr2 = [1, 2, 3];
const arr3 = [true, false];
const newArr = arr1.concat(arr2, arr3, 'newEl');
console.log(newArr); // ['el1', 'el2', 'el3', 1, 2, 3, true, false, 'newEl']
```

#### `copyWithin()`
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

#### `entries()`
Возвращает итератор массива `Array Iterator`, который содержит пары ключ/значение для каждого индекса в массиве.
```js
const arr = ['el1', 'el2', 'el3'];
const iterator = arr.entries();
console.log(iterator); // Array Iterator {}
for (let item of iterator) {
  console.log(item); // [0, 'el1'] [1, 'el2'] [2, 'el3']
}
```

#### `every()`
Возвращает `true`, если все элементы массива удовлетворяют условия функции. В противном случае возвращается `false`. Возвращает `true` при любом условии для пустого массива.
```js
const arr = [19, 21, 32, 24, 35];
const isAllAdult = arr.every(el => el >= 18);
console.log(isAllAdult); // true
```

#### `fill()`
Заполняет все элементы массива от начального до конечного индексов одним значением. Меняет исходный массив.
```js
const arr = ['el1', 'el2', 'el3', 'el4', 'el5'];
arr.fill('newValue');
console.log(arr); // ['newValue', 'newValue', 'newValue', 'newValue', 'newValue']

const arr = ['el1', 'el2', 'el3', 'el4', 'el5'];
arr.fill('newValue', 1, 4);
console.log(arr); // ['el1', 'newValue', 'newValue', 'newValue', 'el5']
```

#### `filter()`
Возвращает отфильтрованный массив со всеми элементами, которые удовлетворяют условия функции. В противном случае возвращается пустой массив.
```js
const arr = ['el1', 'el2', 'el3', 1, 2, 3, true, false];
const filteredArr = arr.filter(el => typeof el === 'number');
console.log(filteredArr); // [1, 2, 3]
```

#### `find()`
Возвращает значение первого найденного в массиве элемента, которое удовлетворяет условия функции. В противном случае возвращается `undefined`.
```js
const arr = [1, 2, 3, 4, 5];
const firstValue = arr.find(el => el > 2);
console.log(firstValue); // 3
```

#### `findIndex()`
Возвращает индекс первого найденного в массиве элемента, который удовлетворяет условия функции. В противном случае возвращается -1.
```js
const arr = [1, 2, 3, 4, 5];
const firstIndex = arr.findIndex(el => el > 2);
console.log(firstIndex); // 2
```

#### `findLast()`
Возвращает значение первого найденного элемента в массиве - с конца массива, которое удовлетворяет условия функции. Работает наоборот методу `find()`. В противном случае возвращается `undefined`.
```js
const arr = [1, 2, 3, 4, 5];
const lastValue = arr.findLast(el => el > 2);
console.log(lastValue); // 5
```

#### `findLastIndex()`
Возвращает индекс первого найденного в массиве элемента - с конца массива, который удовлетворяет условия функции. Работает наоборот методу `findIndex()`. В противном случае возвращается -1.
```js
const arr = [1, 2, 3, 4, 5];
const lastIndex = arr.findLastIndex(el => el > 2);
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
const flatArr = arr.flatMap(el => el);
console.log(flatArr); // [1, 2, 3, 4, 5, 6]
```

#### `forEach()`
Вызывает функцию один раз для каждого элемента массива по порядку. Не выполняет функцию для элементов массива без значений. А также не возвращает результат выполнения, `undefined`.
```js
const arr = [1, 2, 3, 4, 5];
arr.forEach(el => console.log(el * 2)); // 2, 4, 6, 8, 10
```

#### `from()`
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

#### `includes()`
Возвращает результат наличия искомого элемента в массиве.
```js
const arr = [1, true, NaN, 'el4'];
const hasNan = arr.includes(NaN);
console.log(hasNan); // true

const arr = [1, true, NaN, 'el4'];
const hasNan = arr.includes(NaN, -1);
console.log(hasNan); // false
```

#### `indexOf()`
Возвращает первый индекс, по которому данный элемент был найден в массиве или -1, если такого индекса нет. В отличие от `includes()`, для `NaN`, независимо от наличия будет возвращаться -1.
```js
const arr = [1, true, NaN, 'el4'];
const firstIndexOfElement = arr.indexOf(NaN);
console.log(firstIndexOfElement); // -1

const arr = [1, true, NaN, 'el4'];
const firstIndexOfElement = arr.indexOf('el4', 2);
console.log(firstIndexOfElement); // 3
```

#### `Array.isArray()`
Возвращает `true`, если объект является массивом и `false`, если он массивом не является.
```js
const arr = '1';
const isArray = Array.isArray(arr);
console.log(isArray); // false
```

#### `join()`
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

#### `keys()`
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

#### `lastIndexOf()`
Возвращает последний индекс, по которому данный элемент может быть найден в массиве или -1, если такого индекса нет. Массив просматривается от конца к началу.
```js
const arr = ['JS', 'HTML', 'JS', 'CSS'];
const lastIndexOfElement = arr.lastIndexOf('JS');
console.log(lastIndexOfElement); // 2
const lastIndexOfElement = arr.lastIndexOf('JS', 1);
console.log(lastIndexOfElement); // 0
```

#### `map()`
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

#### `Array.of()`
Возвращает новый экземпляр массива `Array` из произвольного числа аргументов, вне зависимости от числа или типа аргумента.
```js
const newArr = Array.of(7);
console.log(newArr); // [7], newArr.length = 1

const newArr = Array.of(1, 2, 3);
console.log(newArr); // [1, 2, 3], newArr.length = 3
```

#### `pop()`
Удаляет последний элемент из массива и возвращает его значение.
```js
const arr = ['el1', 'el2', 'el3', 'el4', 'el5'];
const delValue1 = arr.pop();
console.log(delValue1); // el5
const delValue2 = arr.pop();
console.log(delValue2); // el4
```

#### `push()`
Добавляет один или более элементов в конец массива и возвращает новую длину массива.
```js
const arr = [];
const addValue = arr.push('el1', 'el2');
console.log(addValue); // 2
```

#### `reduce()`
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
  { id: "123", amount: 19 },
  { id: "345", amount: 33 },
  { id: "567", amount: 4 },
  { id: "789", amount: 20 },
];
const totalAmount = bankAccounts.reduce((sum, currentAccount) => sum + currentAccount.amount, 0);
console.log(totalAmount); // 76
```

#### `reduceRight()`
Применяет функцию-редюсер к каждому элементу массива (справа-налево), возвращая одно результирующее значение. Функция не будет вызвана для удалённых, или пропущенных элементов массива. Если массив имеет только один элемент (независимо от позиции) и не указано `initialValue` (значение, используемое в качестве первого аргумента первого вызова функции обратного вызова), или если `initialValue` предоставляется, но массив пуст, то значение этого элемента будет возвращено без вызова функции.
```js
const arr = [5, 10, 15];
const doubled = arr.reduceRight((acc, el) => {
  acc.push(el * 2);
  return acc;
}, []);
console.log(doubled); // [30, 20, 10]
```

#### `reverse()`
Меняет массив, обращая порядок следования элементов массива наоборот. Первый элемент массива становится последним, а последний - первым.
```js
const arr = ['el1', 'el2', 'el3', 'el4', 'el5'];
const reverseArr = arr.reverse();
console.log(reverseArr); // ['el5', 'el4', 'el3', 'el2', 'el1']
```

#### `shift()`
Меняет массив, удаляя первый элемент из массива и возвращает его значение. Этот метод меняет длину массива. Если длина массива равно `length = 0`, вернётся значение `undefined`.
```js
const arr = ['el1', 'el2', 'el3', 'el4', 'el5'];
const delValue = arr.shift();
console.log(delValue); // el1
console.log(arr); // ['el2', 'el3', 'el4', 'el5']
```

#### `slice()`
Возвращает новый массив, содержащий копию части исходного массива.
```js
const arr = ['el1', 'el2', 'el3', 'el4', 'el5'];
const newArr = arr.slice();
console.log(newArr); // ['el1', 'el2', 'el3', 'el4', 'el5']

const arr = ['el1', 'el2', 'el3', 'el4', 'el5'];
const newArr = arr.slice(1, 4);
console.log(newArr); // ['el2', 'el3', 'el4']
```

#### `some()`
Проверяет, удовлетворяет ли какой-либо элемент массива условию, заданному в передаваемой функции. Возвращает `true` и останавливается, если функция возвращает `true` для одного из элементов массива или возвращает `false`, если функция возвращает `false` для всех элементов массива. Также возвращает `false` при любом условии для пустого массива.
```js
const arr = [18, 21, 31, 14, 25];
const hasOneKid = arr.some(el => el < 18);
console.log(hasOneKid); // true
```

#### `sort()`
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

#### `splice()`
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

#### `
