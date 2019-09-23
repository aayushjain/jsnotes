# #1b Special Methods (strings)

- `.length` is a numeric property for all strings. Not a function

      alert( `My\n`.length ); // 3
      
- use square brackets at end of `strings[pos]` to access character. Can also use `.charAt(pos)`.
    - use `str[str.length - 1]` to access last element
```javascript
let str = `Hello`;
alert( str.charAt(0) );         // H
alert( str[str.length - 1] );   // o

alert( str[1000] );        // undefined
alert( str.charAt(1000) ); // '' (empty string)
```

Function | Description
--|--
`.toUpperCase()` | convert str to uppercase
`.toLowerCase()` | convert str to lowercase
`.indexOf(substr, pos)` | look for the `substr` in `str`, start from `pos`. Return position where match was found or `-1` if nothing is found.
`.lastIndexOf(substr, pos)` | similar as above, but searches from end/RTL/reverse
`.includes(substr, pos)` | returns `true` if str contains `substr`; else false.
`.startsWith(substr)` | return `true` if str starts with substr
`.endsWith(substr)` | return `true` if str ends with substr
`.slice(start [, end ])` (___preferred___) | returns substring from `start` to `end-1`. If `end` is not supplied, substring goes till string end. Negative values are allowed for reverse access.
`.substring(start [, end ])` | same as `slice`, but allows `start` to be greater than `end`. Negative values are __not__ allowed.
`.substr(start [, length])` | returns the substring from `start` of given `length`. (start can be negative here)
`.codePointAt(pos)` | return ascii code for char at `pos`
`.fromCodePoint(code)` | get character from asciicode
`.trim()` | trims spaces from the beginning and end of string
`.repeat(n)` | repeats the string `n` times.

Important Difference:
| method                  | selects..                                   | negatives                |
| ----------------------- | ------------------------------------------- | ------------------------ |
| `slice(start, end)`     | from `start` to `end` (not including `end`) | allows negatives         |
| `substring(start, end)` | between `start` and `end`                   | negative values mean `0` |
| `substr(start, length)` | from `start` get `length` characters        | allows negative `start`  |