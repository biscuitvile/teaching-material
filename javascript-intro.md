# Undefined

In JavaScript, `undefined` represents nothing. Some expressions in JavaScript
will return values, and some will return `undefined`.

In this text lines that start with `#=>` indicate the return values of
expressions, don't type these lines in the console.

# Variables & Numbers

Variables are a way to store a value in memory. We will use `let` and `const`
to declare variables.

```
let x = 2
#=> undefined

const y = 4
#=> undefined

x
#=> 2

y
#=> 4

let sum = x + y
#=> undefined

sum
#=> 6
```

Use `let` when you are setting a value that might change, use `const` when you
know the value won't change.

```
let age = 21
#=> undefined

const name = "Jane"
#=> undefined

age = 22
#=> 22
```

In this example if we can change `age` from `21` to `22` because we declared it
with the `let` keyword. Try to change name and see what happens.

```
name = "Bob"
```
If you try this you won't get a value back but instead an error will be raised:

_Uncaught TypeError: Assignment to constant variable._

# Strings

Strings represent text and can be made a few different ways. Use single or
double quotation marks to make simple strings:

```
'Hello, world'
#=> "Hello, world"

"JavaScript is useful!"
#=> "JavaScript is useful!"
```

You can't use apostrophes in strings decalred with single quotes, so double
quotes are better for most strings:

```
let sentence = "It's able to contain apostrophes"
#=> undefined
```

If you try this with single quotes `'It's not able'` you will get an error:

_Uncaught SyntaxError: Unexpected identifier_

# String Interpolation

String interpolation is when you read the value of one string inside another:

```
let favoriteColor = "blue"
#=> undefined

`The sky is ${favoriteColor}.`
#=> "The sky is blue."
```

# Arrays

Arrays are used to contain collections of data:

```
let fruits = ["Apple", "Orange"]
#=> undefined
```

You can access items in arrays by using an index number that starts at zero:

```
fruits[0]
#=> "Apple"

fruits[1]
#=> "Orange"
```

You can perform math to create an index:

```
let veggies = ["Kale", "Spinach", "Turnip", "Cucumber"]
#=> undefined

veggies[1 + 2]
#=> "Cucumber"
```

Or use a variable as an index:

```
let index = 2
#=> undefined

veggies[index]
#=> "Turnip"

fruits[index]
#=> undefined
```

Notice that when we try to look up an index that doesn't exist we get `undefined`.

Remember that arrays can contain otherr arrays.

# Objects

In JavaScript objects are used to store key / value pairs (often called properties):

```
let kevin = {
  name: "Kevin",
  age: 13,
  colors: ["Black", "White", "Auburn"],
  breed: "Domestic Shorthair"
}
#=> undefined

kevin.name
#=> "Kevin"

kevin["name"]
#=> "Kevin

kevin.age
#=> 13

kevin.colors[0]
#=> "Black"
```

Remember that arrays can also contain objects. Additionally, the property value
of an object can be another object.

# Functions

Functions perform calculations or actions. Most (but not all) functions return
a value with the `return` keyword:

```
let myFunc = function() {
  return 2;
}
#=> undefined

myFunc
#=> ƒ (input) { return 2; }
```

Notice that calling the function `myFunc` just returns the definition of the
function, but not the value `2` that we expect. This is because in order to
call a function we must use the `()` characters:

```
myFunc()
#=> 2
```

Functions can take arguments which make them more useful:

```
let addTwo = function(number) {
  return number + 2;
}
#=> undefined

addTwo(2)
#=> 4

addTwo(98)
#=> 100
```

Notice that the word `number` in the `addTwo` function could be anything that
you want and would still work the same:

```
addTwo = function(input) {
  return input + 2;
}
#=> ƒ (input) { return input + 2; }

addTwo(4)
#=> 6
```

# JSON

JSON is an acronym for JavaScript Object Notation. It is a way to represent objects as strings.

```
JSON.stringify(kevin)
#=> "{"name":"Kevin","age":13,"colors":["Black","White","Auburn"],"breed":"Domestic Shorthair"}"
```

You can turn JSON strings back into objects like this:

```
let alice = JSON.parse(`{"name": "Alice"}`)
#=> undefined

alice.name
#=> "Alice"
```
