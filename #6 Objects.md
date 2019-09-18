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

- copy properties from one obj to another (**clone**)
```js
let user = {
    name: "John",
    age: 30
    };

let clone = {};         // new empty object

for (let key in user) {
    clone[key] = user[key];
}       // copy properties

clone.name = "Pete"; // changed data in clone

alert( user.name ); // John in original object
                    // copied value, not reference
                    
// But this method will fail if one property
// contains nested properties, as those will
// be copied by reference. Not value.
```

- use `Object.assign` for simple cloing _(preferred method)_
```js
let clone = Object.assign({}, user);
// copies all props of user into empty object and returns it
```

- Preferably, we should use the cloning loop that examines each value of `user[key]`, and
    - if it’s an object, then replicate its structure as well. That is called “_deep cloning_”.
- Or use the method `_.cloneDeep(obj)` from Lodash library in JS.

---
---

### Garbage Collection

- happens automatically when objects are unreachable (not being referenced ny any other var).
You cannot initiate or abort GC manually.

- a pack of interlinked objects can become unreachable as a whole; and will thus be destroyed by the GC.
    - removing all incoming refs make an obj unreachable.
    - only incoming references make an object reachable. outgoing refs don't matter.
- objects referencing each other, but isolated together from the _root_ make the whole "island" of objects => unreachable.

```javascript
let user = {
    name: "John"
};

let admin = user;
alert(admin.name);  // John
admin.name = "Wick"

alert(user.name);   // Wick

user = null;    // GC is not fired here,
                // coz admin is still referring to that obj

alert(admin.name);  // Wick
alert(user.name);   // TypeError, user is null
```

### Algorithm  
###### Mark and Sweep

1. "Mark"/Remember all roots @ global
2. Visit each root, and mark all outgoing refs from them.
3. Visit each ref, and mark their refs sp as not to revisit them again.
4. Continue until all objects are reachable from the root.
5. Unmarked objects are removed.

`Suggested Reading:` [A tour of V8: Garbage Collection](http://jayconrod.com/posts/55/a-tour-of-v8-garbage-collection).