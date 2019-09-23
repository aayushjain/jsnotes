# #1d Map and Set

> - **Map** is a collection of key-value pairs like objects, but where the keys can be of any data-type(unlike objs where keys are just strings).
Maps can have objs as keys too.
> - **Set** is a special type collection – “set of values” (without keys), where each value must be unique.
> 
> Iteration over `Map` and `Set` is always in the insertion order, so we can’t say that these collections are unordered, but we can’t reorder elements or directly get an element by its number.

### Maps

| Function              | Description                                                                        |
| --------------------- | ---------------------------------------------------------------------------------- |
| `new Map()`           | creates the map.                                                                   |
| `map.set(key, value)` | stores the value by the key.                                                       |
| `.delete(key)`        | removes the value by the key.                                                      |
| `.get(key)`           | returns the value by the key, `undefined` if `key` doesn’t exist in map.           |
| `.has(key)`           | returns `true` if the `key` exists, `false` otherwise.                             |
| `.clear()`            | removes everything from the map.                                                   |
| `.size`               | returns the current element count.                                                 |
| `map.keys()`          | returns an iterable for keys                                                       |
| `map.values()`        | returns an iterable for values                                                     |
| `map.entries()`       | returns an iterable for entries `[key, value]`, it’s used by default in `for..of`. |


```javascript
let recipeMap = new Map();

recipeMap.set('cucumber', 500)
         .set('tomatoes', 350)
         .set('onion', 50);
         // .set returns map only, so you can do chaining


// 1 iterate over keys (vegetables)
for (let vegetable of recipeMap.keys()) {
  alert(vegetable); // cucumber, tomatoes, onion
}

// 2 iterate over values (amounts)
for (let amount of recipeMap.values()) {
  alert(amount); // 500, 350, 50
}

// 3 iterate over [key, value] entries
for (let entry of recipeMap) { // the same as of recipeMap.entries()
  alert(entry); // cucumber,500 (and so on)
}

// 4 Map has a built-in forEach method, similar to Array, 
// that runs the function for each (key, value) pair
recipeMap.forEach( (value, key, map) => {
  alert(`${key}: ${value}`); // cucumber: 500 etc
});
```

### Sets

| Function            | Description                                                                                                      |
| ------------------- | ---------------------------------------------------------------------------------------------------------------- |
| `new Set(iterable)` | creates the set, and if an `iterable` object is provided (usually an array), copies values from it into the set. |
| `set.add(value)`    | adds a value, returns the set itself.                                                                            |
| `.delete(value)`    | removes the value, returns `true` if `value` existed at the moment of the call, otherwise `false`.               |
| `.clear()`          | removes everything from the set.                                                                                 |
| `.size`             | is the elements count.                                                                                           |
| `.keys()`           | returns an iterable object for values,                                                                           |
| `.values()`         | same as `set.keys()`, for compatibility with `Map`,                                                              |
| `.entries()`        | returns an iterable object for entries `[value, value]`, exists for compatibility with `Map`.                    |

- can loop using `for..of`.
```javascript
let set = new Set(["oranges", "apples", "bananas"]);

for (let value of set) alert(value);        // using FO

// the same with forEach:
set.forEach((value, valueAgain, set) => {   // using forEach
  alert(value);
});
```

---
---

### WeakMap and WeakSet

- `WeakMap` is map-like collection that allows ___only objects as keys___ and removes them together with associated value once they become inaccessible.

- `WeakSet` is set-like collection that ___stores only objects___ and removes them once they become inaccessible.

- Both of them do not support methods and properties that refer to all keys or their count. Only individual operations are allowed.

- `WeakMap` and `WeakSet` are used as “secondary” data structures in addition to the “main” object storage.
Once the object is removed from the main storage, if it is only found as the key of `WeakMap` or in a `WeakSet`, it will be cleaned up automatically.