# #2 Type Conversion

### 1. String conversion

_convert values from one type to another_

- use `String(variable)` to explicitly convert that variable to a string.
```js
     let value = true;
     alert(typeof value); // boolean
     
     value = String(value); // now value is a string "true"
     alert(typeof value); // string
```

### 2. Numeric Conversion

- use `Number(variable)` explicitly convert that variable to a number.
```js
let str = "123";
alert(typeof str); // string

let num = Number(str);  // becomes a number 123
alert(typeof num)       // number
```

- using division `/`, subtraction `-` or multiplication `*` operator automatically converts that string to number for operation.
```js
alert("6"/"2");     // output is 3
alert("2" * "3");   // output is 6
alert("" - 1 + 0);          // output is -1
alert(" \t \n  " - 1 + 0);  // output is -1
alert("4" - 2);     // output is 2
```

- but when used on normal strings, you get `NaN`.
```js
alert(Number("an arbitrary string instead of a number"));
// NaN, conversion failed
```

- when one of the strings in a concatenation is a string, rest are all made strings as well.
```js
alert( '1' + 2 ); // "12" (string to the left)
```


##### Numeric Conversion Rules:

> For strings, starting and trailing whitespaces are truncated. If resultant string is empty, result is `0`. If string contains only numbers, then output is an integer. If string contains text other than in the below table, then the result is `NaN`.
> 
> | Input     | Output |
> | --------- | ------ |
> | undefined | NaN    |
> | null      | 0      |
> | true      | 1      |
> | false     | 0      |

```javascript
alert( Number("   123   ") ); // 123
alert( Number("123z") );      // NaN (error reading a number at "z")
alert( Number(true) );        // 1
alert( Number(false) );       // 0
alert (Number("   true "))    // NaN
```


### 3. Boolean Conversion

| Input                                                                                          | Output |
| ---------------------------------------------------------------------------------------------- | ------ |
|`0`, `''`, `null`, `undefined`, and `NaN` | false  |
| everything else                                                                                           | true       |

Sample Code:
```javascript
alert( Boolean("") )        // false
alert( Boolean(" ") )       // true
alert( Boolean("0") )       // true
alert( Boolean(0) )         // false
alert( Boolean(null + 1))   // true
alert( Boolean(null + 0))   // false
```