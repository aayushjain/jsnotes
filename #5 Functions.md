# #5 Functions

- reusable code blocks

```javascript
function funcName(  param1,
                    param2 = "default value",
                    param3 = func2()
                 ) {        // fn declaration
  //
  // func body
  //
  
  return (param1 + 4);      // optional
}

funcName(args);             // invocation
funcName(args);

```

OR

```javascript
let funcName = function (params) {
                            // fn expression
  //
  // func body
  //
  return param;  
};  // semicolon suggested to stop let assignment
```
- func in JS is a value in itself
- local vars in func body not accessible outside
- global vars (vars declared outside func body) accessible inside
- global vars can be modified permanently. ___use with caution.___
- if same name var both inside and outside, then inside is used first.
- prefer to pass vars to func, process locally.
- follows **call-by-value**, not call-by-ref.
- func with no return or just `return`, returns `undefined`
- prefer to wrap return statements in parantheses, and dont start params from new line

```js
let func1 = function(){
...
};

let func2 = func1;
// copies code of func1 to func2
// notice absence of func1 braces
```

- prefer func declaration over func expression.
- use func expression for dynamic conditional assignment
- func declaration has local scope, but
- assigning a function to global variable in a block makes the func logic available outside that block too. ie the func can be accessed outside too.

```javascript
let age = prompt("What is your age?", 18);
let welcome;        // global var

if (age < 18) {

    welcome = function() {
        alert("Hello!");
        };          // local defn inside if

    }
else {
    welcome = function() {
        alert("Greetings!");
        };

    }

welcome();          // global invocation
                    // outside if
```

### Arrow Functions

    let func = (arg1, arg2, ...argN) => expression
    
is the same as

    let func = function(arg1, arg2, ...argN) {
      return expression;
    };
    
#### example: 
```javascript
let sum1 = (a, b) => a + b;
    // oneline arrow fn does not need return

let sum2 = (a, b) => {
    let result = a + b;
    return result; 
    // curly braces require return
};

alert( sum1(1, 2) );    // 3
alert( sum2(1, 2) );    // 3
```

