# Checking equality with `==`

You have seen how to use the `=` sign for assignment, for example:

```
let x = 6
#=> undefined
```

However sometimes we want to check for equality, and get a `true` or `false`
value back. For this we use the `==` operator.

```
1 == 1
#=> true

1 == 2
#=> false

"Hello" == "Hello"
#=> true

"Hello" == "hello"
#=> false

let friend = { name = "Alice", age: 24 }
#=> undefined

friend.name == "Alice"
#=> true

```

Notice however that arrays and objects are not equal even if they have the same
contents, they must literally be the same object.

```
[1, 2, 3] == [1, 2, 3]
#=> false

{ foo: "bar" } == { foo: "bar" }
#=> false
```

# Or logic with the `||` operator

Sometimes you need your code to choose between one thing and another based on
if the first thing is `undefined` or `false`. You can do that with `||`, the or
operator.

```
1 || 2
#=> 1

false || 3
#=> 3

undefined || "foo"
#=> "foo"

let jim = { name: "Jim", married: false }
#=> undefined

jim.married || "single"
#=> "single"

JSON.parse(localStorage.getItem("movies")) || []
#=> []
```


# `if`, `else`, and `else if`

You can program JavaScript to perform certain actions in specific conditions
using the `if` and `else` keywords.

Let's defined a function that returns an appropriate greeting for the hour of
day.

```
let greeting = function(hour) {
  if (hour < 12) {
    return "Good morning";
  }
}
#=> undefined
```

We can see now that the function will return `"Good morning"` for hours before
12, and return `undefined` for hours not before 12.

```
greeting(8)
#=> "Good morning"

greeting(16)
#=> undefined
```

This is good but what if we want to say `"Good afternoon"` as well?


```
greeting = function(hour) {
  if (hour < 12) {
    return "Good morning";
  } else {
    return "Good afternoon";
  }
}
#=> ƒ (hour) { if (hour < 12) { ...

greeting(10)
#=> "Good morning"

greeting(14)
#=> "Good afternoon"
```

Now What if we want to say `"Good evening"` for hours after 16?

```
greeting = function(hour) {
  if (hour < 12) {
    return "Good morning";
  } else if (hour < 16) {
    return "Good afternoon";
  } else {
    return "Good evening";
  }
}
#=> ƒ (hour) { if (hour < 12) { ...

greeting(7)
#-> "Good morning"

greeting(13)
#-> "Good afternoon"

greeting(18)
#-> "Good evening"
```

# Array#forEach()

Many times when working with arrays you will need to iterate and operate on the
contents of the array. the `Array` class has a method (or function) called
`forEach()` that does just this.

```
let heroes = ["Batman", "Captain Marvel", "The Flash"]

heroes.forEach(function(hero) {
  console.log(`${hero} will save us!`);
})
#=> Batman will save us!
#=> Captain Marvel will save us!
#=> The Flash will save us!
#=> undefined

let presidents = [
  { name: "Washington", number: 1 },
  { name: "Lincoln", number: 16 }
]

presidents.forEach(function(president) {
  console.log(`${president.name} was president number ${president.number}.`);
});
#=> Washington was president number 1.
#=> Lincoln was president number 16.
#=> undefined
```
