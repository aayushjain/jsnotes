# #4 Control Statements

## If Statement

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


## Conditional `?:`
```js
let var = (evaluation) ? true : false 
```
