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
(also converts string with numbers to Number DataType)
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

------------------
------------------

### Logical Operators

#### 1. OR `||`

- converts operands to bools, then checks for the first 'true' from LTR.
    - If true, then returns operand.
    - If all false, then return last operand.
```js
alert( null || 0 || 1 );        // 1
alert(undefined || null || 0);  // 0
```

- form of `if`. If one is false, then check if next is true.

- can be used to find first variable containing data, when others are empty.
```js
let defaultUser = undefined;
alert(null || defaultUser || "user"); // user
```

#### 2. AND `&&`

- works similarly as `||`. But checks for first falsy value instead. 
    - Returns last operand, if all true.
```js
result = value1 && value2 && value3
// result = value3
// (as long as value1&2 are not 0)

result = 1 && 2 && 3    // 3

alert( 1 && 5 );        // 5

alert( 1 && 2 && null && 3 ); // null
```

#### 3. NOT `!`

- converts oper to bool, and returns inverse of bool
```js
alert(!0);  // true
```

- double NOT `!!` can be used to convert oper to bool
operator ->  inverse bool -> bool
```js
alert( !!null );        // false
// is the same as..
alert( Boolean(null) ); // false
```

> ##### Priority Order
> `!` >> `&&` >> `||`
> 
> ```javascript
> alert( !!null || 2 && 3 || 4 );   // 3
> ```