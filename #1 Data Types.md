# #1 Data Types

> Always prefer `let` over `var` (according to the new standard) because `let` does not allow redeclaration, but var overwrites the existing value.
> Also when dealing with loops, a `let` variable is accessible in only the scop of the function or block in which it is declared, unlike a `var` variable which is accessible outside too.
> 
> Also, expressions in JS are evaluated Left-to-Right.
>```javascript
> print(10 + 2 + "Volvo" + 16 + 4)
> // output is 12Volvo164
> ```
> 
> Data types in JS are dynamic. 
> ```javascript
> let x;        // Now x is undefined
> x = 5;        // Now x is a Number
> x = "John";   // Now x is a String 
>```
> 


### 1. Numbers

> `let n = 1234`, or
> `let n = 12.34`

* has both int and floats
* special nums are: `Infinity`, `-Infinity` and `NaN`.
* `NaN` represents a computational error. It is a result of an incorrect or an undefined mathematical operation. It is sticky, ie **any further operation on `NaN` returns `NaN`**.

      alert( ("not a number" / 2) + 5 ); // NaN


### 2. Strings

> can be `'single ticks'`,
> `"double ticks"`, and
> `` `backticks` ``    <-- _Best approach_ (template literals)


- no `char` type in JS
- can use _newline_ with backticks only
- operation inside `${ }` in a template literal is first computed, converted to a string, and included at that position.
```javascript
let user = `Aayush`
print( `Hello ${user}!` )
// output is "Hello Aayush!"

alert( `the result of 1 plus 2 is ${1 + 2}` );
// the result of 1 plus 2 is 3
```

- use backslash as escape characters for quotes:
```js
let quote = "\"No\", said Rosa Parks.";
alert(quote);
// "No", said Rosa Parks.
```

- use single backslash or plus-sign to trim lines to 80chars, and continue on next
```js
print("You can use a\
backslash to break \
strings.");

print("But the preferred " +
"method is using the" +
"plus operator as most " +
"browsers support + over \.")
```

### 3. Booleans

- can be `true` or `false`.
- can be derived from expressions, and assigned to variables.   

      let isGreater = 4 > 2
      alert( isGreater );   // true
     
### 4. Null

`let age = NULL` means that the variable 'age' is empty. It has no value. Nothing.

### 5. Undefined

`let age;` means that variable 'age' has been declared, but “value is not assigned”. You can 'unset' any variable back to unassigned if required.

> #### Note
> - Normally, we use `null` to assign an "empty" or "unknown" value to a variable, and we use `undefined` for checks like seeing if a variable has been assigned. 
> - `null` is set explicitly. `undefined` is set automtically.
> -   `null` is an assigned value. It means _nothing._
> - `undefined` means a variable has been declared but not defined yet.
> - `null !== undefined` but `null == undefined`.


### 6. Objects

- used to store collections of data and more complex entities.

### 7. Symbols

- used to create unique identifiers for objects. 


---
---

#### typeof

- is both function, and operator, ie  `typeof x` is the same as `typeof(x)`.
```js
typeof undefined    // "undefined"
typeof 0            // "number"
typeof true         // "boolean"
typeof "foo"        // "string"
typeof Symbol("id") // "symbol"
typeof Math         // "object"
typeof null         // "object" (wrong)
typeof alert        // "function"
```

- Returns a string with the name of the type, like "string".
- For `null` returns "object" – this is an error in the language, it is not actually an object.

