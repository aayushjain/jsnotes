# #1c Special Methods (arrays)

Function | Description
--- | ---
`.push(...items)` | adds `items` to the end.
`.pop()` | removes and returns the last element.
`.shift()` | removes the element from the beginning and returns it.
`.unshift(...items)` | adds `items` to the beginning.
`.lenght` | last-index + 1. Can be used to truncate arrays as well.



- arrays are special type of objects, stored contiguously in memory.
- `push`/`pop()` is better to work with, rather than `shift`/`unshift()` as they operate only on the end of the array.
- always add items to an array in an ordered fashion, from start to end. Do not add randomly, and do not start adding from the end.

- `for..of()` is better than `for..in()` as FO operates over numeric properties only, whereas  FI goes over all.
    - FO gives access to current value only, not the whole element.
    - FO is optimized for arrays