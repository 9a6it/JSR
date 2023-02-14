#### [:book:](README.md) / `String`

Свойство / Метод | Синтаксис
:--- | :---
[**`String.fromCharCode()`**](#top-stringfromcharcode) | `String.fromCharCode(num1, num2*, ..., numN*)`
[**`String.fromCodePoint()`**](#top-stringfromcodepoint) | `String.fromCodePoint(num1, num2*, ..., numN*)`
[**`String.raw()`**](#top-stringraw) | `` String.raw`templateString` ``
[**`at()`**](#top-at) | `str.at(i)`

####  [**:top:**](#book--string) `String.fromCharCode()`
Возвращает строку, созданную из указанной последовательности кодовых точек. Допустимый диапозон значений составляет от 0 до 65535 (0xFFFF). Числа больше 0xFFFF будут усечены.
```js
let utfToStr = String.fromCharCode(72, 69, 76, 76, 79);
console.log(utfToStr); // 'HELLO'
```

####  [**:top:**](#book--string) `String.fromCodePoint()`
Возвращает строку, созданную из указанной последовательности кодовых точек. Улучшенная версия метода `String.fromCharCode`. Позволяет работать со значениями выше 65535. На данный момент их около 150 000.
```js
let utfToStr = String.fromCodePoint(194564);
console.log(utfToStr); // '你'
```

####  [**:top:**](#book--string) `String.raw()`
Возвращает необработанную строковую форму строки шаблона.
```js
const strPath = 'C:\Users\Ghost';
console.log(strPath); // 'C:UsersGhost' - не то что мы хотели получить

const rawPath = String.raw`C:\Users\Ghost`;
console.log(rawPath); // 'C:\Users\Ghost'
```

####  [**:top:**](#book--string) `at()`
Возвращает символ указанного индекса строки.
```js
const str = 'Docker';
const lastCharacter = str.at(-1);
console.log(lastCharacter); // 'r'
```
