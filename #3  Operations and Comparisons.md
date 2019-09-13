# #3  Operations and Comparisons

> For complete operator precedence guide, check out [this table](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence#Table).
> 
>summary: `()` > `post++` > `--pre` > `!` > `**` > `*, /,  %` > `+, -` > `<<, >>` > `<, <=, >, >=, in` > `==, !=, ===, !== ` > `&&` > `||` > `?:` > `=, +=, *=` > `,`
 
### Operators

#### 1. Unary

- `-` operand reverses the sign
```js
let x =1; x = -x; alert(x); // -1
```

- `+` operand converts to positive
```js
let y = -2;
y = +y;
alert(y);       // 2
alert( +false); // 0
alert( +true);  // -1
```

- `+` operand concatenates two strings
```js
let str = "my " + "string"
alert(str) // "my string"
```

- unary plus operators are applied first
```js
let a = "2", b = "3";
alert (+a + +b); // 5
// same as: alert (Number(a) + Number(b));
```

- `*` happens before `+`. To control evaluation, use parantheses.
```js
let x = 2 * 2 + 1;
alert(x);   // 5

x = 2 * (2 + 1);
alert(x);   // 6
```

- chain assignments using `=`
```js
let a, b, c;
a = b = c = 3+3;
alert(a); // 6
alert(b); // 6
alert(c); // 6
```

- `=` assigns a value, and then returns it
```js
let a=1, b=2;

let c = 3 - (a = b + 1);

alert(a); // 3
alert(c); // 0
```

- `%` is modulo (remainder of division)
- `**` is exponent (raised to power)
- `++` and `--` are increments. postfix and prefix rules apply.
```js
let a = 2;
alert( 2 * a++); // 4, not 6
// one action per line is suggested. 
```

- `,` is used to evaluate several expressions, but only last one is returned.
```js
let a = (1 + 2, 3 + 4);
alert( a ); // 7 (the result of 3 + 4)
```

#### 2. Binary operators

- `+` concatenates two strings


-   **Multiplicative** Operators
    *   The `*` Operator
    *   The `/` Operator
    *   The `%` Operator
-   **Additive** Operators
    *   The Addition operator (`+`)
    *   The Subtraction Operator (`-`)
-   **Bitwise Shift** Operators
    *   The Left Shift Operator (`<<`)
    *   The Signed Right Shift Operator (`>>`)
    *   The Unsigned Right Shift Operator (`>>>`)
-   **Relational** Operators
    *   The Less-than Operator (`<`)
    *   The Greater-than Operator (`>`)
    *   The Less-than-or-equal Operator (`<=`)
    *   The Greater-than-or-equal Operator (`>=`)
    *   The `instanceof` operator
    *   The `in` operator
-   **Equality** Operators
    *   The Equals Operator (`==`)
    *   The Does-not-equals Operator (`!=`)
    *   The Strict Equals Operator (`===`)
    *   The Strict Does-not-equal Operator (`!==`)
-   **Binary Bitwise** Operators (`&`, `^`, `|`)
-   **Binary Logical** Operators (`&&`, `||`)


- Logical operatros are also capable of string comparison:
```js
alert( 'Z' > 'A' );         // true
alert( 'Glow' > 'Glee' );   // true
alert( 'Bee' > 'Be' );      // true
alert( '2' > 1 );           // true, string '2' becomes a number 2
alert( '01' == 1 );         // true, string '01' becomes a number 1
alert( true == 1 );         // true
alert( false == 0 );        // true
```

------------------
------------------

### Comparisons

- `==` is not treated the same as `>=` and its variants.

```js
alert( null > 0 );  // false
alert( null == 0 ); // false
alert( null >= 0 ); // true
```
- `undefined` only equals `null` in value, nothing else.
```js
alert( undefined > 0 );     // false
alert( undefined < 0 );     // false
alert( undefined == 0 );    // false
alert( undefined == null);  // true
```

