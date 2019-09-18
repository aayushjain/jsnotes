# #6 Objects

- collection of properties defined as a `key:value` pair, and declared by `{...}`, called an object literal.
```javascript
let user = {
  name          : "John",
  age           : 30,
  "fav color"   : "red",
  // prefer to end last property with a comma,
  // although not necessary, it helps when adding new props
};

// access using dot notation
alert( user.name ); // John

// prefer square-bracket notation for access
alert( user["fav color"] );

// to remove property, use delete
delete user.age;
delete user["fav color"];

// access key flexibly
let key = prompt("What do you want to know about the user?", "name");
alert( user.[key] );    // john, dynamic, possible
alert( user.key );      // undefined, error, not possible
```

- keys can be dynamic, if needed
```javascript
let fruit = prompt("Which fruit?", "apple");

let bag = {
  [fruit]: 5, // apple: 5
};

alert( bag.apple ); // 5, if fruit is "apple"
```

- shorthand method
```js
function makeUser(name, age) {
  return {
    name,               // same as name: name
    age,                // same as age: age 
    "fav color",        // can mix normal+shorthand
  };
}

let user = makeUser("John", 30, "red");
alert(user.name); // John
```


- use \_in\_ to check if key exists
```js
alert( "name" in user );
// true, returns bool
```
- use `.hasOwnProperty` to check is key exists (_preferred method_)
```js
alert( user.hasOwnProperty("name") );
//true, returns bool
```

- use `for..in` to loop over keys in an object.
    - can declare vars inside `for` syntax
```js
for (let prop in user) {
  alert( prop );
  alert( user[prop] );
  // prints out all keys and values in Obj
}
```

-  no new memory is allocated when object is assigned to another variable. It works as _call-by-reference_.
```js
let a = {};
let b = a;          // copy the reference

alert( a == b );    // true
                    // both vars refer same obj
alert( a === b );   // true

b = {};             // redeclare b as empty obj

alert( a == b );    // false
                    // both vars are diff objs
```

- constant objects can have their properties changed, because reassignment/modification of property is not reassignment of object.
```js
const user = {
  name: "John"
};

user.age = 25;   // no error
alert(user.age); // 25

user = {         // error
  name: "Pete"
};
```


