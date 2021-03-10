#                       javscript basics


While HTML and CSS control the content and styling of a page, JavaScript is used to make it interactive. In the JavaScript Algorithm and Data Structures Certification, you'll learn the fundamentals of JavaScript including variables, arrays, objects, loops, and functions.

Once you have the fundamentals down, you'll apply that knowledge by creating algorithms to manipulate strings, factorialize numbers, and even calculate the orbit of the International Space Station.

Along the way, you'll also learn two important programing styles or paradigms: Object Oriented Programing (OOP), and Functional Programing (FP).

## strings:  
#### Converting strings to numbers with vanilla JavaScript:

In JavaScript, you can represent a number is an actual number (ex. `42`), or as a string (ex. `'42'`).

If you were to use a strict comparison to compare the two, it would fail because they’re two different types of objects

```js
var num1 = 42;
var num2 = '42';
if (num1 === num2) {
    console.log(true);
} else {
    console.log(false);
}
// Will log `false`
```

Today, let’s look at three different ways to convert a string into a number.

#### `parseInt()` [#](https://gomakethings.com/converting-strings-to-numbers-with-vanilla-javascript/#parseint)

The `parseInt()` method converts a string into an integer (a whole number).

It accepts two arguments. The first argument is the string to convert. The second argument is called the `radix`. This is the base number used in mathematical systems. For our use, it should always be `10`.

```js
var text = '42px';
var integer = parseInt(text, 10);
// returns 42
```

#### `parseFloat()` [#](https://gomakethings.com/converting-strings-to-numbers-with-vanilla-javascript/#parsefloat)

The `parseFloat()` method converts a string into a point number (a number with decimal points). You can even pass in strings with random text in them.

```js
var text = '3.14someRandomStuff';
var pointNum = parseFloat(text);
// returns 3.14
```

#### `Number()` [#](https://gomakethings.com/converting-strings-to-numbers-with-vanilla-javascript/#number)

The `Number()` method converts a string to a number.

Sometimes it’s an integer. Other times it’s a point number. And if you pass in a string with random text in it, you’ll get `NaN`, an acronym for “Not a Number.”

As a result of this inconsistency, it’s a less safe choice than `parseInt()` and `parseFloat()`. If you know the format of the number you’d like, use those instead. If you want the string to fail with `NaN` if it has other characters in it, `Number()` may actually be a better choice.

```js
// Convert strings
Number('123'); // returns 123
Number('12.3'); // returns 12.3
Number('3.14someRandomStuff'); // returns NaN
Number('42px'); // returns NaN
```



#### `string.repeat`

The `repeat()` method constructs and returns a new string which contains the specified number of copies of the string on which it was called, concatenated together.

```js
const chorus = 'Because I\'m happy. ';

console.log(`Chorus lyrics for "Happy": ${chorus.repeat(27)}`);

// expected output: "Chorus lyrics for "Happy": Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. "

```





#### **`concat()`**

The `concat()` method concatenates the string arguments to the calling string and returns a new string.

```js
const str1 = 'Hello';
const str2 = 'World';

console.log(str1.concat(' ', str2));
// expected output: "Hello World"

console.log(str2.concat(', ', str1));
// expected output: "World, Hello"
```





#           Javascript Basic Data-structure 




## **Array:**

The Array object is used to store multiple values in a single variable.

The JavaScript Array class is a global object that is used in the construction of arrays; which are high-level, list-like objects.

Arrays are list-like objects whose prototype has methods to perform traversal and mutation operations. Neither the length of a JavaScript array nor the types of its elements are fixed. Since an array's length can change at any time, and data can be stored at non-contiguous locations in the array, JavaScript arrays are not guaranteed to be dense; this depends on how the programmer chooses to use them. In general, these are convenient characteristics; but if these features are not desirable for your particular use, you might consider using typed arrays.



 





### Methods:

[more methods...](https://www.w3schools.com/jsref/jsref_obj_array.asp)



#### **push() and unshift():**

An array's length, like the data types it can contain, is not fixed. Arrays can be defined with a length of any number of elements, and elements can be added or removed over time; in other words, arrays are mutable. In this challenge, we will look at two methods with which we can programmatically modify an array: Array.push() and Array.unshift().


let twentyThree = 'XXIII'; let romanNumerals = ['XXI', 'XXII'];  romanNumerals.unshift('XIX', 'XX'); // now equals ['XIX', 'XX', 'XXI', 'XXII']  romanNumerals.push(twentyThree); // now equals ['XIX', 'XX', 'XXI', 'XXII', 'XXIII']Notice that we can also pass variables, which allows us even greater flexibility in dynamically modifying our array's data.



#### pop() and shift():

Both push() and unshift() have corresponding methods that are nearly functional opposites: pop() and shift(). As you may have guessed by now, instead of adding, pop() *removes* an element from the end of an array, while shift() removes an element from the beginning. The key difference between pop() and shift() and their cousins push() and unshift(), is that neither method takes parameters, and each only allows an array to be modified by a single element at a time.

Let's take a look:

```javascript
let greetings = ['whats up?', 'hello', 'see ya!'];  greetings.pop(); // now equals ['whats up?', 'hello']  greetings.shift(); // now equals ['hello']
```


#### Splice():

Ok, so we've learned how to remove elements from the beginning and end of arrays using shift() and pop(), but what if we want to remove an element from somewhere in the middle? Or remove more than one element at once? Well, that's where splice() comes in. splice() allows us to do just that: **remove any number of consecutive elements** from anywhere in an array.

[see more…](https://devdocs.io/javascript/global_objects/array/splice)



**Remove Items Using splice():**

```js
const months = ['Jan', 'March', 'April', 'June']; months.splice(1, 0, 'Feb'); // inserts at index 1 console.log(months); // expected output: Array ["Jan", "Feb", "March", "April", "June"]  months.splice(4, 1, 'May'); // replaces 1 element at index 4 console.log(months); // expected output: Array ["Jan", "Feb", "March", "April", "May"]
```



#### **slice():**

The next method we will cover is slice(). Rather than modifying an array, slice() copies or *extracts* a given number of elements to a new array, leaving the array it is called upon untouched. slice() takes only 2 parameters — the first is the index at which to begin extraction, and the second is the index at which to stop extraction (extraction will occur up to, but not including the element at this index). Consider this:

[read more…](https://devdocs.io/javascript/global_objects/array/slice)

```js
let weatherConditions = ['rain', 'snow', 'sleet', 'hail', 'clear'];  let todaysWeather = weatherConditions.slice(1, 3); // todaysWeather equals ['snow', 'sleet']; // weatherConditions still equals ['rain', 'snow', 'sleet', 'hail', 'clear']
```



#### **Spread Operator/...**

While slice() allows us to be selective about what elements of an array to copy, among several other useful tasks, ES6's new spread operator allows us to easily copy *all* of an array's elements, in order, with a simple and highly readable syntax. The spread syntax simply looks like this: …

In practice, we can use the spread operator to copy an array like so:

**Copy an Array with the Spread Operator:**

**let** **thisArray = [****true****,** **true****,** **undefined****,** **false****,** **null****];**** ****let** **thatArray = [...thisArray];**** ****// thatArray equals [true, true, undefined, false, null]**** ****// thisArray remains unchanged and thatArray contains the same elements as thisArray**



**Combine Arrays with the Spread Operator:**

**let** **thisArray = [****'sage'****,** **'rosemary'****,** **'parsley'****,** **'thyme'****];**** **** ****let** **thatArray = [****'basil'****,** **'cilantro'****, ...thisArray,** **'coriander'****];**** ****// thatArray now equals ['basil', 'cilantro', 'sage', 'rosemary', 'parsley', 'thyme', 'coriander']**** **** ****// thatArray now equals ['basil', 'cilantro', 'sage', 'rosemary', 'parsley', 'thyme', 'coriander']**







#### **indexOf():**

Since arrays can be changed, or *mutated*, at any time, there's no guarantee about where a particular piece of data will be on a given array, or if that element even still exists. Luckily, JavaScript provides us with another built-in method, indexOf(), that allows us to quickly and easily check for the presence of an element on an array. indexOf() takes an element as a parameter, and when called, it returns the position, or index, of that element, or -1 if the element does not exist on the array.

For example:

let fruits = ['apples', 'pears', 'oranges', 'peaches', 'pears'];  fruits.indexOf('dates'); // returns -1 fruits.indexOf('oranges'); // returns 2 fruits.indexOf('pears'); // returns 1, the first index at which the element exists





#### **hasOwnProperty():**

JavaScript provides us with two different ways to do this. One uses the hasOwnProperty() method and the other uses the in keyword. If we have an object users with a property of Alan, we could check for its presence in either of the following ways:



users.hasOwnProperty('Alan'); 'Alan' in users; //both return true





#### **for...in Statement:**

Sometimes you may need to iterate through all the keys within an object. This requires a specific syntax in JavaScript called a for...in statement. For our users object, this could look like:

for (let user in users) {  console.log(user); }  // logs: Alan Jeff Sarah Ryan







#### **Object.keys():**



We can also generate an array which contains all the keys stored in an object using the Object.keys() method and passing in an object as the argument. This will return an array with strings representing each property in the object. Again, there will be no specific order to the entries in the array.

const object1 = {  a: 'somestring',  b: 42,  c: false };  console.log(Object.keys(object1)); // expected output: Array ["a", "b", "c"]














#    Javascript Basic Algorithm-scripting  





#### **join():**

The join() method creates and returns a new string by concatenating all of the elements in an array (or an [array-like object](https://wiki.developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#Working_with_array-like_objects)), separated by commas or a specified separator string. If the array has only one item, then that item will be returned without using the separator.

const elements = ['Fire', 'Air', 'Water'];  console.log(elements.join()); // expected output: "Fire,Air,Water"  console.log(elements.join('')); // expected output: "FireAirWater"  console.log(elements.join('-')); // expected output: "Fire-Air-Water"











#### **find():**


The **find()** method returns the **value** of the **first element** in the provided array that satisfies the provided testing function.

const array1 = [5, 12, 8, 130, 44];  const found = array1.find(element => element > 10);  console.log(found); // expected output: 12





#### **charAt():**

The[ String](https://devdocs.io/javascript/global_objects/string) object's charAt() method returns a new string consisting of the single UTF-16 code unit located at the specified offset into the string. :


````js
const sentence = 'The quick brown fox jumps over the lazy dog.';

const index = 4;

console.log(`The character at index ${index} is ${sentence.charAt(index)}`);

// expected output: "The character at index 4 is q"
````



# [Javascript Object Oriented Programming](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#object-oriented-programming)



#### **Create a Method on an Object **

Objects can have a special type of property, called a method.

Methods are properties that are functions. This adds different behavior to an object. Here is the `duck` example with a method:

```javascript
let duck = {
  name: "Aflac",
  numLegs: 2,
  sayName: function() {return "The name of this duck is " + duck.name + ".";}
};
duck.sayName();
// Returns "The name of this duck is Aflac."
```

The example adds the `sayName` method, which is a function that returns a sentence giving the name of the `duck`. Notice that the method accessed the `name` property in the return statement using `duck.name`. The next challenge will cover another way to do this.

#### **Make Code More Reusable with the this Keyword**

The last challenge introduced a method to the `duck` object. It used `duck.name` dot notation to access the value for the `name` property within the return statement:

```
sayName: function() {return "The name of this duck is " + duck.name + ".";}
```

While this is a valid way to access the object's property, there is a pitfall here. If the variable name changes, any code referencing the original name would need to be updated as well. In a short object definition, it isn't a problem, but if an object has many references to its properties there is a greater chance for error.

A way to avoid these issues is with the `this` keyword:

```js
let duck = {
  name: "Aflac",
  numLegs: 2,
  sayName: function() {return "The name of this duck is " + this.name + ".";}
};
```

`this` is a deep topic, and the above example is only one way to use it. In the current context, `this` refers to the object that the method is associated with: `duck`. If the object's name is changed to `mallard`, it is not necessary to find all the references to `duck` in the code. It makes the code reusable and easier to read.

#### **Define a Constructor Function**

Constructors are functions that create new objects. They define properties and behaviors that will belong to the new object. Think of them as a blueprint for the creation of new objects.

Here is an example of a constructor:

```js
function Bird() {
  this.name = "Albert";
  this.color = "blue";
  this.numLegs = 2;
}
```

This constructor defines a `Bird` object with properties `name`, `color`, and `numLegs` set to Albert, blue, and 2, respectively. Constructors follow a few conventions:

- Constructors are defined with a capitalized name to distinguish them from other functions that are not `constructors`.
- Constructors use the keyword `this` to set properties of the object they will create. Inside the constructor, `this` refers to the new object it will create.
- Constructors define properties and behaviors instead of returning a value as other functions might.



#### **Use a Constructor to Create Objects**

Here's the `Bird` constructor from the previous challenge:

```js
function Bird() {
  this.name = "Albert";
  this.color  = "blue";
  this.numLegs = 2;
  // "this" inside the constructor always refers to the object being created
}

let blueBird = new Bird();
```

Notice that the `new` operator is used when calling a constructor. This tells JavaScript to create a new instance of `Bird` called `blueBird`. Without the `new` operator, `this` inside the constructor would not point to the newly created object, giving unexpected results. Now `blueBird` has all the properties defined inside the `Bird` constructor:

```js
blueBird.name; // => Albert
blueBird.color; // => blue
blueBird.numLegs; // => 2
```

Just like any other object, its properties can be accessed and modified:

```js
blueBird.name = 'Elvira';
blueBird.name; // => Elvira
```





#### **Extend Constructors to Receive Arguments**

The `Bird` and `Dog` constructors from last challenge worked well. However, notice that all `Birds` that are created with the `Bird` constructor are automatically named Albert, are blue in color, and have two legs. What if you want birds with different values for name and color? It's possible to change the properties of each bird manually but that would be a lot of work:

```js
let swan = new Bird();
swan.name = "Carlos";
swan.color = "white";
```

Suppose you were writing a program to keep track of hundreds or even thousands of different birds in an aviary. It would take a lot of time to create all the birds, then change the properties to different values for every one. To more easily create different `Bird` objects, you can design your Bird constructor to accept parameters:

```js
function Bird(name, color) {
  this.name = name;
  this.color = color;
  this.numLegs = 2;
}
```

Then pass in the values as arguments to define each unique bird into the `Bird` constructor: `let cardinal = new Bird("Bruce", "red");` This gives a new instance of `Bird` with name and color properties set to Bruce and red, respectively. The `numLegs` property is still set to 2. The `cardinal` has these properties:

```js
cardinal.name // => Bruce
cardinal.color // => red
cardinal.numLegs // => 2
```

The constructor is more flexible. It's now possible to define the properties for each `Bird` at the time it is created, which is one way that JavaScript constructors are so useful. They group objects together based on shared characteristics and behavior and define a blueprint that automates their creation.





#### **Verify an Object's Constructor with instanceof**

Anytime a constructor function creates a new object, that object is said to be an instance of its constructor. JavaScript gives a convenient way to verify this with the `instanceof` operator. `instanceof` allows you to compare an object to a constructor, returning `true` or `false` based on whether or not that object was created with the constructor. Here's an example:

```js
let Bird = function(name, color) {
  this.name = name;
  this.color = color;
  this.numLegs = 2;
}

let crow = new Bird("Alexis", "black");

crow instanceof Bird; // => true
```

If an object is created without using a constructor, `instanceof` will verify that it is not an instance of that constructor:

```js
let canary = {
  name: "Mildred",
  color: "Yellow",
  numLegs: 2
};

canary instanceof Bird; // => false
```

**Exercise:**- Create a new instance of the `House` constructor, calling it `myHouse` and passing a number of bedrooms. Then, use `instanceof` to verify that it is an instance of `House`.

```js

function House(numBedrooms) {

 this.numBedrooms = numBedrooms;

}

// Only change code below this line

let myHouse = new House(4);

console.log(myHouse instanceof House);
```

#### **Understand Own Properties** 

In the following example, the `Bird` constructor defines two properties: `name` and `numLegs`:

```js
function Bird(name) {
  this.name  = name;
  this.numLegs = 2;
}

let duck = new Bird("Donald");
let canary = new Bird("Tweety");
```

`name` and `numLegs` are called `own` properties, because they are defined directly on the instance object. That means that `duck` and `canary` each has its own separate copy of these properties. In fact every instance of `Bird` will have its own copy of these properties. The following code adds all of the `own` properties of `duck` to the array `ownProps`:

```js
let ownProps = [];

for (let property in duck) {
  if(duck.hasOwnProperty(property)) {
    ownProps.push(property);
  }
}

console.log(ownProps); // prints [ "name", "numLegs" ]
```

#### **Use Prototype Properties to Reduce Duplicate Code**

Since `numLegs` will probably have the same value for all instances of `Bird`, you essentially have a duplicated variable `numLegs` inside each `Bird` instance.

This may not be an issue when there are only two instances, but imagine if there are millions of instances. That would be a lot of duplicated variables.

A better way is to use `Bird’s` `prototype`. Properties in the `prototype` are shared among ALL instances of `Bird`. Here's how to add `numLegs` to the `Bird prototype`:

```js
Bird.prototype.numLegs = 2;
```

Now all instances of `Bird` have the `numLegs` property.

```js
console.log(duck.numLegs);  // prints 2
console.log(canary.numLegs);  // prints 2
```

Since all instances automatically have the properties on the `prototype`, think of a `prototype` as a "recipe" for creating objects. Note that the `prototype` for `duck` and `canary` is part of the `Bird` constructor as `Bird.prototype`. Nearly every object in JavaScript has a `prototype` property which is part of the constructor function that created it.





#### **Understand the Constructor Property**

There is a special `constructor` property located on the object instances `duck` and `beagle` that were created in the previous challenges:

```js
let duck = new Bird();
let beagle = new Dog();

console.log(duck.constructor === Bird);  //prints true
console.log(beagle.constructor === Dog);  //prints true
```

Note that the `constructor` property is a reference to the constructor function that created the instance. The advantage of the `constructor` property is that it's possible to check for this property to find out what kind of object it is. Here's an example of how this could be used:

```js
function joinBirdFraternity(candidate) {
  if (candidate.constructor === Bird) {
    return true;
  } else {
    return false;
  }
}
```

**Note**
Since the `constructor` property can be overwritten (which will be covered in the next two challenges) it’s generally better to use the `instanceof` method to check the type of an object.

#### **Change the Prototype to a New Object**

Up until now you have been adding properties to the `prototype` individually:

```js
Bird.prototype.numLegs = 2;
```

This becomes tedious after more than a few properties.

```js
Bird.prototype.eat = function() {
  console.log("nom nom nom");
}

Bird.prototype.describe = function() {
  console.log("My name is " + this.name);
}
```

A more efficient way is to set the `prototype` to a new object that already contains the properties. This way, the properties are added all at once:

```js
Bird.prototype = {
  numLegs: 2, 
  eat: function() {
    console.log("nom nom nom");
  },
  describe: function() {
    console.log("My name is " + this.name);
  }
};
```

#### **Set the Constructor Property when Changing the Prototype**

There is one crucial side effect of manually setting the prototype to a new object. It erases the `constructor` property! This property can be used to check which constructor function created the instance, but since the property has been overwritten, it now gives false results:

```js
duck.constructor === Bird; // false -- Oops
duck.constructor === Object; // true, all objects inherit from Object.prototype
duck instanceof Bird; // true, still works
```

To fix this, whenever a prototype is manually set to a new object, remember to define the `constructor` property:

```js
Bird.prototype = {
  constructor: Bird, // define the constructor property
  numLegs: 2,
  eat: function() {
    console.log("nom nom nom");
  },
  describe: function() {
    console.log("My name is " + this.name); 
  }
};
```

#### **Understand Where an Object’s Prototype Comes From**

Just like people inherit genes from their parents, an object inherits its `prototype` directly from the constructor function that created it. For example, here the `Bird` constructor creates the `duck` object:

```js
function Bird(name) {
  this.name = name;
}

let duck = new Bird("Donald");
```

`duck` inherits its `prototype` from the `Bird` constructor function. You can show this relationship with the `isPrototypeOf` method:

```js
Bird.prototype.isPrototypeOf(duck);
// returns true
```





#### **Understand the Prototype Chain**

All objects in JavaScript (with a few exceptions) have a `prototype`. Also, an object’s `prototype` itself is an object.

```js
function Bird(name) {
  this.name = name;
}

typeof Bird.prototype; // yields 'object'
```

Because a `prototype` is an object, a `prototype` can have its own `prototype`! In this case, the `prototype` of `Bird.prototype` is `Object.prototype`:

```js
Object.prototype.isPrototypeOf(Bird.prototype); // returns true
```

How is this useful? You may recall the `hasOwnProperty` method from a previous challenge:

```js
let duck = new Bird("Donald");
duck.hasOwnProperty("name"); // yields true
```

The `hasOwnProperty` method is defined in `Object.prototype`, which can be accessed by `Bird.prototype`, which can then be accessed by `duck`. This is an example of the `prototype` chain. In this `prototype` chain, `Bird` is the `supertype` for `duck`, while `duck` is the `subtype`. `Object` is a `supertype` for both `Bird` and `duck`. `Object` is a `supertype` for all objects in JavaScript. Therefore, any object can use the `hasOwnProperty` method.
[More...](https://community.risingstack.com/javascript-prototype-chain-inheritance/#:~:text=The%20Prototype%20Chain,-Every%20object%20has&text=When%20an%20attribute%20is%20called,or%20the%20end%20is%20reached.)

#### **Use Inheritance So You Don't Repeat Yourself**

There's a principle in programming called Don't Repeat Yourself (DRY). The reason repeated code is a problem is because any change requires fixing code in multiple places. This usually means more work for programmers and more room for errors.

Notice in the example below that the `describe` method is shared by `Bird` and `Dog`:

```js
Bird.prototype = {
  constructor: Bird,
  describe: function() {
    console.log("My name is " + this.name);
  }
};

Dog.prototype = {
  constructor: Dog,
  describe: function() {
    console.log("My name is " + this.name);
  }
};
```

The `describe` method is repeated in two places. The code can be edited to follow the DRY principle by creating a `supertype` (or parent) called `Animal`:

```js
function Animal() { };

Animal.prototype = {
  constructor: Animal, 
  describe: function() {
    console.log("My name is " + this.name);
  }
};
```

Since `Animal` includes the `describe` method, you can remove it from `Bird` and `Dog`:

```js
Bird.prototype = {
  constructor: Bird
};

Dog.prototype = {
  constructor: Dog
};
```





#### **Inherit Behaviors from a Supertype**

In the previous challenge, you created a `supertype` called `Animal` that defined behaviors shared by all animals:

```js
function Animal() { }
Animal.prototype.eat = function() {
  console.log("nom nom nom");
};
```

This and the next challenge will cover how to reuse `Animal's` methods inside `Bird` and `Dog` without defining them again. It uses a technique called inheritance. This challenge covers the first step: make an instance of the `supertype` (or parent). You already know one way to create an instance of `Animal` using the `new` operator:

```js
let animal = new Animal();
```

There are some disadvantages when using this syntax for inheritance, which are too complex for the scope of this challenge. Instead, here's an alternative approach without those disadvantages:

```js
let animal = Object.create(Animal.prototype);
```

`Object.create(obj)` creates a new object, and sets `obj` as the new object's `prototype`. Recall that the `prototype` is like the "recipe" for creating an object. By setting the `prototype` of `animal` to be `Animal's` `prototype`, you are effectively giving the `animal` instance the same "recipe" as any other instance of `Animal`.

```js
animal.eat(); // prints "nom nom nom"
animal instanceof Animal; // => true
```

#### **Set the Child's Prototype to an Instance of the Parent**

In the previous challenge you saw the first step for inheriting behavior from the supertype (or parent) `Animal`: making a new instance of `Animal`.

This challenge covers the next step: set the `prototype` of the subtype (or child)—in this case, `Bird`—to be an instance of `Animal`.

```js
Bird.prototype = Object.create(Animal.prototype);
```

Remember that the `prototype` is like the "recipe" for creating an object. In a way, the recipe for `Bird` now includes all the key "ingredients" from `Animal`.

```js
let duck = new Bird("Donald");
duck.eat(); // prints "nom nom nom"
```

`duck` inherits all of `Animal`'s properties, including the `eat` method.





#### **Reset an Inherited Constructor Property**

When an object inherits its `prototype` from another object, it also inherits the supertype's constructor property.

Here's an example:

```js
function Bird() { }
Bird.prototype = Object.create(Animal.prototype);
let duck = new Bird();
duck.constructor // function Animal(){...}
```

But `duck` and all instances of `Bird` should show that they were constructed by `Bird` and not `Animal`. To do so, you can manually set `Bird's` constructor property to the `Bird` object:

```js
Bird.prototype.constructor = Bird;
duck.constructor // function Bird(){...}
```

#### **Add Methods After Inheritance**

A constructor function that inherits its `prototype` object from a super type constructor function can still have its own methods in addition to inherited methods.

For example, `Bird` is a constructor that inherits its `prototype` from `Animal`:

```js
function Animal() { }
Animal.prototype.eat = function() {
  console.log("nom nom nom");
};
function Bird() { }
Bird.prototype = Object.create(Animal.prototype);
Bird.prototype.constructor = Bird;
```

In addition to what is inherited from `Animal`, you want to add behavior that is unique to `Bird` objects. Here, `Bird` will get a `fly()` function. Functions are added to `Bird's` `prototype` the same way as any constructor function:

```js
Bird.prototype.fly = function() {
  console.log("I'm flying!");
};
```

Now instances of `Bird` will have both `eat()` and `fly()` methods:

```js
let duck = new Bird();
duck.eat(); // prints "nom nom nom"
duck.fly(); // prints "I'm flying!"
```

#### **Override Inherited Methods**

In previous lessons, you learned that an object can inherit its behavior (methods) from another object by referencing its `prototype` object:

```js
ChildObject.prototype = Object.create(ParentObject.prototype);
```

Then the `ChildObject` received its own methods by chaining them onto its `prototype`:

```js
ChildObject.prototype.methodName = function() {...};
```

It's possible to override an inherited method. It's done the same way - by adding a method to `ChildObject.prototype` using the same method name as the one to override. Here's an example of `Bird` overriding the `eat()` method inherited from `Animal`:

```js
function Animal() { }
Animal.prototype.eat = function() {
  return "nom nom nom";
};
function Bird() { }

// Inherit all methods from Animal
Bird.prototype = Object.create(Animal.prototype);

// Bird.eat() overrides Animal.eat()
Bird.prototype.eat = function() {
  return "peck peck peck";
};
```

If you have an instance `let duck = new Bird();` and you call `duck.eat()`, this is how JavaScript looks for the method on `duck’s` `prototype` chain:

1. duck => Is eat() defined here? No.
2. Bird => Is eat() defined here? => Yes. Execute it and stop searching.
3. Animal => eat() is also defined, but JavaScript stopped searching before reaching this level.
4. Object => JavaScript stopped searching before reaching this level.



#### **Use a Mixin to Add Common Behavior Between Unrelated Objects**

As you have seen, behavior is shared through inheritance. However, there are cases when inheritance is not the best solution. Inheritance does not work well for unrelated objects like `Bird` and `Airplane`. They can both fly, but a `Bird` is not a type of `Airplane` and vice versa.

For unrelated objects, it's better to use mixins. A mixin allows other objects to use a collection of functions.

```js
let flyMixin = function(obj) {
  obj.fly = function() {
    console.log("Flying, wooosh!");
  }
};
```

The `flyMixin` takes any object and gives it the `fly` method.

```js
let bird = {
  name: "Donald",
  numLegs: 2
};

let plane = {
  model: "777",
  numPassengers: 524
};

flyMixin(bird);
flyMixin(plane);
```

Here `bird` and `plane` are passed into `flyMixin`, which then assigns the `fly` function to each object. Now `bird` and `plane` can both fly:

```js
bird.fly(); // prints "Flying, wooosh!"
plane.fly(); // prints "Flying, wooosh!"
```

Note how the mixin allows for the same `fly` method to be reused by unrelated objects `bird` and `plane`.



#### **Use Closure to Protect Properties Within an Object from Being Modified Externally**

In the previous challenge, `bird` had a public property `name`. It is considered public because it can be accessed and changed outside of `bird`'s definition.

```js
bird.name = "Duffy";
```

Therefore, any part of your code can easily change the name of `bird` to any value. Think about things like passwords and bank accounts being easily changeable by any part of your codebase. That could cause a lot of issues.

The simplest way to make this public property private is by creating a variable within the constructor function. This changes the scope of that variable to be within the constructor function versus available globally. This way, the variable can only be accessed and changed by methods also within the constructor function.

```js
function Bird() {
  let hatchedEgg = 10; // private variable

  /* publicly available method that a bird object can use */
  this.getHatchedEggCount = function() { 
    return hatchedEgg;
  };
}
let ducky = new Bird();
ducky.getHatchedEggCount(); // returns 10
```

Here `getHatchedEggCount` is a privileged method, because it has access to the private variable `hatchedEgg`. This is possible because `hatchedEgg` is declared in the same context as `getHatchedEggCount`. In JavaScript, a function always has access to the context in which it was created. This is called `closure`.



#### **Understand the Immediately Invoked Function Expression (IIFE)**

A common pattern in JavaScript is to execute a function as soon as it is declared:

```js
(function () {
  console.log("Chirp, chirp!");
})(); // this is an anonymous function expression that executes right away
// Outputs "Chirp, chirp!" immediately
```

Note that the function has no name and is not stored in a variable. The two parentheses () at the end of the function expression cause it to be immediately executed or invoked. This pattern is known as an immediately invoked function expression or IIFE.



#### **Use an IIFE to Create a Module**

An immediately invoked function expression (IIFE) is often used to group related functionality into a single object or module. For example, an earlier challenge defined two mixins:

```js
function glideMixin(obj) {
  obj.glide = function() {
    console.log("Gliding on the water");
  };
}
function flyMixin(obj) {
  obj.fly = function() {
    console.log("Flying, wooosh!");
  };
}
```

We can group these mixins into a module as follows:

```js
let motionModule = (function () {
  return {
    glideMixin: function(obj) {
      obj.glide = function() {
        console.log("Gliding on the water");
      };
    },
    flyMixin: function(obj) {
      obj.fly = function() {
        console.log("Flying, wooosh!");
      };
    }
  }
})(); // The two parentheses cause the function to be immediately invoked
```

Note that you have an immediately invoked function expression (IIFE) that returns an object `motionModule`. This returned object contains all of the mixin behaviors as properties of the object. The advantage of the module pattern is that all of the motion behaviors can be packaged into a single object that can then be used by other parts of your code. Here is an example using it:

```js
motionModule.glideMixin(duck);
duck.glide();
```







# [Functional Programming](https://youtube.com/playlist?list=PL0zVEGEvSaeEd9hlmCXrk5yUyqUag-n84)



### IMP Method

####  [`array.filter`](https://devdocs.io/javascript/global_objects/array/filter)

The `filter()` method **creates a new array** with all elements that pass the test implemented by the provided function.

```js
const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];

const result = words.filter(word => word.length > 6);

console.log(result);
// expected output: Array ["exuberant", "destruction", "present"]
```






#### **Functional Programming**

Functional programming is a style of programming where solutions are simple, isolated functions, without any side effects outside of the function scope.

```
INPUT -> PROCESS -> OUTPUT
```

Functional programming is about:

1. Isolated functions - there is no dependence on the state of the program, which includes global variables that are subject to change
2. Pure functions - the same input always gives the same output
3. Functions with limited side effects - any changes, or mutations, to the state of the program outside the function are carefully controlled



#### **Understand Functional Programming Terminology**

The FCC Team had a mood swing and now wants two types of tea: green tea and black tea. General Fact: Client mood swings are pretty common.

With that information, we'll need to revisit the `getTea` function from last challenge to handle various tea requests. We can modify `getTea` to accept a function as a parameter to be able to change the type of tea it prepares. This makes `getTea` more flexible, and gives the programmer more control when client requests change.

But first, let's cover some functional terminology:

Callbacks are the functions that are slipped or passed into another function to decide the invocation of that function. You may have seen them passed to other methods, for example in `filter`, the callback function tells JavaScript the criteria for how to filter an array.

Functions that can be assigned to a variable, passed into another function, or returned from another function just like any other normal value, are called first class functions. In JavaScript, all functions are first class functions.

The functions that take a function as an argument, or return a function as a return value are called higher order functions.

When the functions are passed in to another function or returned from another function, then those functions which gets passed in or returned can be called a lambda.









 