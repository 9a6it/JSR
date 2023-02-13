#### [:book:](README.md) / `String`

Свойство / Метод | Синтаксис
:--- | :---
[**`String.fromCharCode()`**](#top-stringfromcharcode) | `String.fromCharCode(num1, num2*, ..., numN*)`
[**`String.fromCodePoint()`**](#top-stringfromcodepoint) | `String.fromCodePoint(num1, num2*, ..., numN*)`
[**`String.raw()`**](#top-stringraw) | `` String.raw`templateString` ``

####  [**:top:**](#book--string) `String.fromCharCode()`
Возвращает строку, созданную из указанной последовательности кодовых единиц UTF-16.
```js
let utf16ToStr = String.fromCharCode(72, 69, 76, 76, 79);
console.log(utf16ToStr); // 'HELLO'
```

####  [**:top:**](#book--string) `String.fromCodePoint()`
Возвращает строку, созданную из указанной последовательности кодовых точек (UTF-32).
```js
let utf32ToStr = String.fromCodePoint(72, 69, 76, 76, 79);
console.log(utf32ToStr); // '𝌆a𝌇'
```

####  [**:top:**](#book--string) `String.raw()`
Возвращает необработанную строковую форму строки шаблона.
```js
const strPath = 'C:\Users\Ghost';
console.log(strPath); // 'C:UsersGhost' - не то что мы хотели получить

const rawPath = String.raw`C:\Users\Ghost`;
console.log(rawPath); // 'C:\Users\Ghost'
```
