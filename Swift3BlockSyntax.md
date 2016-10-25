# Swift 3 closures and Cheatsheet

## Closures { () -> () in }
Closures are self-contained blocks of functionality that can be passed around and used in your code.
Closures are similair to Blocks in Objective-C
Global and nested functions are actually special cases of closures.
Closures are **Reference** types

### Defining a Closure

```Swift
{ (parameters) -> return type in
statements
}
```

```Swift
var answerToTheUltimateQuestion = { (a: Int) -> (Int) in return a*0 + 42}
answerToTheUltimateQuestion(10)
```

### Closure as a parameter in a function

**sorted(by:)** - method provided by a Swift standard library, sorts an array, based on sorting closure

```Swift
let minorCharacters = ["Agrajag", "Mrs Alice Beeblebrox", "The Allitnils", "Aseed", "Colin"]

func sortBackward(_ s1: String, _ s2: String) -> Bool {
    return s1 > s2
}

var reversedNames = minorCharacters.sorted(by: sortBackward)

```
or you can add closure directly as an argument

```Swift

let majorCharacters = [ "Arthur Dent", "Ford Prefect", "Zaphod Beeblebrox", "Marvin the Paranoid Android", "Trillian", "Slartibartfast"]

var reversedNames1 = majorCharacters.sorted(by: { (name1: String, name2: String) -> Bool in return name1 > name2 })

```

Swift can infer the types of its parameters and return type

```Swift
var reversedNames1 = majorCharacters.sorted(by: { (name1, name2) in return name1 > name2 })

```

### Shorthand Argument Names

Swift also provide shorthand argument names $0, $1 ... 
For a ingle-expression closures you can omit the **retrun** keyword  

```Swift
var reversedNames1 = majorCharacters.sorted(by: { $0 > $1 })

```

### Closures can capture references to any constants and variables from their surrounding context
Use Weak and unowned  

```Swift
func findTheAnswer(forValue value: Int) -> () -> Bool {
    var theAnswer = 0
        func DeepThought() -> Bool {
            if theAnswer + value == 42{
                return true
            }
            return false
        }
    return DeepThought
}

```

### Trailing closure
A clouser in function’s final argument can be written after the function call’s parentheses

Long version
```Swift
func answer(toTheQuestion: () -> Void){
    toTheQuestion()
}

answer( toTheQuestion: {
    print("42")
})
```

Short version
```Swift
answer {
    print("42")
}
```

### Escaping Closures





### Autoclosure
The @autoclosure argument can be applied to an argument of function type which takes no parameters. At the call site, the caller provides an expression for that argument. This expression is then implicitly wrapped in a function, and that function is passed in as the parameter

```Swift
func AnswerToTheUltimateQuestion( answer: @autoclosure () -> Int) { 
    print(answer()) 
}

AnswerToTheUltimateQuestion(answer: 42)
```
is equal to

```Swift
func AnswerToTheUltimateQuestion( answer: () -> Int) {
    print(answer())
}

AnswerToTheUltimateQuestion(answer: {42})
```

## Functions
Functions are self-contained chunks of code that perform a specific task

### Defining a Functions

Calling Function
Function Type
Function is a first class citizen
passing and returning a function

Varadic functions


TODO
[ ] Trailing Closures

[x] Autoclosures

[ ] Escaping Closures

[ ] Closures Are Reference Types

Inspired by 
[fuckingswiftblocksyntax.com](http://fuckingswiftblocksyntax.com/)

[fuckingclosuresyntax.com](http://fuckingclosuresyntax.com/)

[swiftblocksyntax](https://github.com/chasseurmic/swiftblocksyntax)

[Swift Asserts by Mike Ash](https://www.mikeash.com/pyblog/friday-qa-2016-03-04-swift-asserts.html)
