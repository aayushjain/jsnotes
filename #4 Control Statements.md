# #4 Control Statements

## 1. If Statement

```js
if ( evaluation ) {
    exec this block if eval is true
}
else if ( eval2 ){
    exec this block if eval2 is true
}
else{
    exec this if all above are false
}
```

#### Cases when `if` is false:
```js
if (""){};
if (0) {}; 
if (NaN) {};
if (null) {};
if (false) {};
if (undefined) {};
```

#### Cases when `if` is true:
```javascript
if (1){};
if (true) {};

let x;
if (x=1) {}; //assignment returns true
             //for all values except 0
if (x == 1) {};
```


### Conditional `?:`
```js
let var = (evaluation) ? true : false 
```


## 2. While Statement

- when number of statements is not definite

- executes through loop-body as long as condition is true

```javascript
while (conditionIsTruthy) {
  // exec block
}
```
### Do-while Statement
 
```js
 do {
  // exec block
} while (conditionIsTruthy);
```

## 3. For Statement

- when you have definite number of iterations in mind

```javascript
for (init; condition; iter) {
    // loop-body
}
```

#### Nested control:

```js
outer: for (let i = 0; i < 3; i++) { //use `outer` label to idenitfy where to break/continue
  for (let j = 0; j < 3; j++) {

    let input = prompt(`Value at coords (${i},${j})`, '');
    // if an empty string or canceled, then break out of both loops
    
    if (!input) break outer; // (*)
    // do something with the value...
  }
}
alert('Done!');
```

## 4. Switch Statement

- enters case body only when **strict equality** found until break
- does not compare further if/when atleast case is true

```js
let a = 2 + 2;

switch (a) {
  case 3:
    alert( 'Too small' );
    break;
  case 4:
    alert( 'Exactly!' );    // if (a === 4)
    break;
  case 5:
    alert( 'Too large' );
    break;
  case 'what':
    alert('invalid input');
    break;
  case 'huge number':
  default:        // club two cases together
    alert( "I don't know such values" );
}
```

----
----

User Interaction:

#### 1. Prompt
`prompt(question, [default])`  
- Ask for input after a ques.
    - Returns user-input.
    - If cancel/escape, then returns null.

#### 2. Confirm
`confirm(question)`
- Ask a ques.
    - Returns 1 when user presses Ok.
    - Returns 0 when user presses Cancel.

#### 3. Alert
`alert(message)`
- Output a message/text string.

##### Prompt, Confirm and Alerts are _modal_. Code exec is paused when user input is required. Interaction is restricted as long as value is not returned.
