# Notes to myself

---------------------------------------------------------

    Pollyfill
    
A polyfill is a piece of code (usually JavaScript on the Web) used to provide modern functionality on older browsers that do not natively support it.

The reason why polyfills are not used exclusively is for better functionality and better performance. Native implementations of APIs can do more and are faster than polyfills.

array.prottype.function()

tanımlı degil veya desteklemiyorsa biz tanımlıyoruz.
------------------------------------------------------------

    js using in html 

we have two way.

-   inline
    <script></script>   
    
-   extarnel
    <script src='filepath/script.js'> </script>
    
------------------------------------------------------------

    Js code excecution


JS Engine
                                            
|Our Code|     ===>===>   |Parser|----->|Convertion to Machine Language|----->|Code  Runs|

     
------------------------------------------------------------

                    SSH

ssh-keygen -t rsa -b 4096 -C "eposta@adresiniz.com"    //create

cat ~/.ssh/id_rsa.pub                   // show

------------------------------------------------------------
                         var, let , const

function varTest() {
  var x = 1;
  if (true) {
    var x = 2;  // same variable
    console.log(x);  // 2
  }
  console.log(x);  // 2
}

function letTest() {
  let x = 1;
  if (true) {
    let x = 2;  // different variable
    console.log(x);  // 2
  }
  console.log(x);  // 1
}

const is not subject to Variable Hoisting too, which means that const declarations do not move to the top of the current execution context.
Also note that ES6 code will run only in browsers that support it. Older devices and browsers that do not support ES6 will return a syntax error.

------------------------------

                ${expression} 
                
let a = 8;
let b = 34;
let msg = `The sum is ${a+b}`;
//output : 'The sum is 42'


-------------------------

The ---for...in-- loop is intended for iterating over the enumerable keys of an ---object.---

let obj = {a: 1, b: 2, c: 3};
for (let v in obj) {
  console.log(v);
}

The for...of loop, which creates a loop iterating over iterable objects.(array)

let list = ["x", "y", "z"];
for (let val of list) {
  console.log(val);
}
also string use 

for (let ch of "Hello") {
  console.log(ch);
}
------------------------------

const add = (x, y) => {
  let sum = x + y;  
  console.log(sum);
}

\\\\\\

const greet = x => "Welcome " + x;


\\\\\\\

const x = () => alert("Hi");


--------------------
                                    Object method assign() 
                                    
puting the default values right in the signature of the functions.

const test = (a, b = 3, c = 42) => {
  return a + b + c;
}
console.log(test(5)); //50 

--------------------

Object method assign() that allows us to combine multiple sources into one target to create a single new object.
Object.assign() is also useful for creating a duplicate of an existing object.

let person = {
    name: 'Jack',
    age: 18,
    sex: 'male'
};
let student = {
    name: 'Bob',
    age: 20,
    xp: '2'
};

let newStudent = Object.assign({}, person, student);

console.log(newStudent.name); // Bob
console.log(newStudent.age); // 20
console.log(newStudent.sex); // male
console.log(newStudent.xp); // 2

\\\\\\\\\\
let newPerson = person; //  newPerson references person
newPerson.name = 'Bob'; 

console.log(person.name); // Bob
console.log(newPerson.name); // Bob
\\\\\\\\\\\\
let person = {
  name: 'Jack',
  age: 18
};

let newPerson = Object.assign({}, person); 
newPerson.name = 'Bob';

console.log(person.name); // Jack
console.log(newPerson.name); // Bob

-----------------------------

                        Array Destructuring in ES6
                        
let arr = ['1', '2', '3'];
let [one, two, three] = arr;

console.log(one); // 1
console.log(two); // 2
console.log(three); // 3      

/////////////

let a = () => {
    return [1, 3, 2];
};

let [one, , two] = a();

console.log(one); // 1
console.log(two); // 2

////////////////

swaping value

let a, b, c = 4, d = 8;
[a, b = 6] = [2]; // a = 2, b = 6

[c, d] = [d, c]; // c = 8, d = 4

-----------------------------

                Object Destructuring in ES6


let obj = {h:100, s: true};
let {h, s} = obj;

console.log(h); // 100
console.log(s); // true

////////

let a, b; ({a, b} = {a: 'Hello ', b: 'Jack'});

console.log(a + b); // Hello Jack

/////////

let {a, b} = {a: 'Hello ', b: 'Jack'};
console.log(a + b); //// Hello Jack

///////
var obj = {id: 42, name: "Jack"};

let {id = 10, age = 20} = obj;

console.log(id); // 42
console.log(age); // 20



---------------


const obj1 = { foo: 'bar', x: 42 };
const obj2 = { foo: 'baz', y: 5 };

const clonedObj = {...obj1}; // { foo: "bar", x: 42 }
const mergedObj = {...obj1, ...obj2}; // { foo: "baz", x: 42, y: 5 }


--------

                                    Map object

The syntax new Map([iterable]) creates a Map object where iterable is an array or any other iterable object whose elements are arrays (with a key/value pair each).

An Object is similar to Map but there are important differences that make using a Map preferable in certain cases:
1) The keys can be any type including functions, objects, and any primitive.
2) You can get the size of a Map.
3) You can directly iterate over Map.
4) Performance of the Map is better in scenarios involving frequent addition and removal of key/value pairs.

let map = new Map([['k1', 'v1'], ['k2', 'v2']]);


Methods
set(key, value) Adds a specified key/value pair to the map. If the specified key already exists, value corresponding to it is replaced with the specified value.
get(key) Gets the value corresponding to a specified key in the map. If the specified key doesn't exist, undefined is returned.
has(key) Returns true if a specified key exists in the map and false otherwise.
delete(key) Deletes the key/value pair with a specified key from the map and returns true. Returns false if the element does not exist.
clear() Removes all key/value pairs from map.
keys() Returns an Iterator of keys in the map for each element.
values() Returns an Iterator of values in the map for each element.
entries() Returns an Iterator of array[key, value] in the map for each element.


let map = new Map();

map.set('k1', 'v1').set('k2', 'v2');

console.log(map.get('k1')); // v1

console.log(map.has('k2')); // true

for (let kv of map.entries())
  console.log(kv[0] + " : " + kv[1]);

-----------------

                                    Set object

A Set object can be used to hold unique values (no repetitions are allowed).
A value in a set can be anything (objects and primitive values).

The syntax new Set([iterable]) creates a Set object where iterable is an array or any other iterable object of values.

The size property returns the number of distinct values in a set.

let set = new Set([1, 2, 4, 2, 59, 9, 4, 9, 1]);


Methods
add(value) Adds a new element with the given value to the Set.
delete(value) Deletes a specified value from the set.
has(value) Returns true if a specified value exists in the set and false otherwise.
clear() Clears the set.
values() Returns an Iterator of values in the set.

let set = new Set();

set.add(5).add(9).add(59).add(9);

console.log(set.has(9));

for (let v of set.values())
  console.log(v);

------------------

                        Promise
                        
A Promise is a better way for asynchronous programming when compared to the common way of using a setTimeout() type of method.

setTimeout(function() {
  console.log("Work 1");
  setTimeout(function() {
    console.log("Work 2");
  }, 1000);
}, 1000);
console.log("End");


\\\\\\\
function asyncFunc(work) {
  return new Promise(function(resolve, reject) {
    if (work === "")
      reject(Error("Nothing"));
    setTimeout(function() {
      resolve(work);
    }, 1000);
  });
}

asyncFunc("Work 1") // Task 1
.then(function(result) {
  console.log(result);
  return asyncFunc("Work 2"); // Task 2
}, function(error) {
  console.log(error);
})
.then(function(result) {
  console.log(result);
}, function(error) {
  console.log(error);
});
console.log("End");

