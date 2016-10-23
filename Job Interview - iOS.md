iOS Digest - iOS Job interview
=======================

## Swift
[The Swift Programming Language (Swift 3)](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Enumerations.html#//apple_ref/doc/uid/TP40014097-CH12-ID145)

## Design patterns
[Software design pattern](https://en.wikipedia.org/wiki/Software_design_pattern#Classification_and_list)

[Design Patterns in Swift](https://github.com/ochococo/Design-Patterns-In-Swift)

1.Creational patterns
* Builder vs telescoping constructor anti-pattern
* Factory
* Lazy initialization
* Object pool
* Prototype
* Singleton

2.Structural patterns
* Adapter pattern
* Composite

3.Behavioral patterns
* Chain of responsibility
* Command
* Delegation
* Iterator
* Observer or Publish/subscribe
* State

4.Architectural design pattern
* MVC
* [MVVM](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93viewmodel): Model, View, ViewModel, DataBinder

5.Concurrency patterns
* Lock
* Read-write lock
* Thread pool

## iOS Specific interview questions
* Weak vs unowned vs unsafe_unretained references
* @autoclosure?

* [Swift Asserts by Mike Ash](https://www.mikeash.com/pyblog/friday-qa-2016-03-04-swift-asserts.html)
The @autoclosure argument can be applied to an argument of function type which takes no parameters. At the call site, the caller provides an expression for that argument. This expression is then implicitly wrapped in a function, and that function is passed in as the parameter

```Swift
func f(@autoclosure value: () -> Int) {
print(value())
}

f(42)
```

```Swift
func f(value: () -> Int) {
print(value())
}

f({ 42 })
```

* Swift. Assert vs precondition

Assert only functions in non-optimized builds. When optimizations are enabled, the entire thing is compiled out.
Precondition performs the check even in optimized builds. This makes it a much better choice for most assertion checks, as long as the check is sufficiently fast.
[Swift Asserts by Mike Ash](https://www.mikeash.com/pyblog/friday-qa-2016-03-04-swift-asserts.html)

* Swift.Value types in swift (primitives, array, string, dictionary, struct, enum, and tuple) 
[Value and Reference Types](https://developer.apple.com/swift/blog/?id=10)

* Swift.What are Optionals?

[Optional - A type that can represent either a wrapped value or `nil`, the absence of a value.](https://github.com/apple/swift/blob/master/stdlib/public/core/Optional.swift)

* Swift.[How you would implement Optionals in Swift using Swift](https://github.com/jquave/JOptional/blob/Part1/JOptional/main.swift)


```Swift
enum MyOptional<T> {
    case None
    case Some(T)

    init(_ value: T) {
        self = .Some(value)
    }

    init() {
        self = .None
    }

    func unwrap() -> Any {
        switch self {
            case .Some(let x):
            return x
        default:
            assert(true, "Unexpectedly found nil while unwrapping an JOptional value")
        }
        return JOptional.None
    }

    postfix operator >! {}
    postfix func >! <T>(value: JOptional<T> ) -> Any {
        return value.unwrap()
    }

}

var optionalString = MyOptional("A String!")
var nilString = MyOptional()
var a = optionalString.unwrap()
```
* What is a protocol?

A protocol will tell the class, struct, or enum which adopts it what methods and properties it must implement.

* What is the delegation?

Delegation is a design pattern that enables a class or structure to hand off (or delegate) some of its responsibilities to an instance of another type

* What is the characteristics of Switch in Swift?

Any kind of data, you don’t need to explicitly break out the switch, statement must be exhaustive

* [NSLock vs @synchronized vs dispatch_semaphore_XXX](http://stackoverflow.com/questions/1215330/how-does-synchronized-lock-unlock-in-objective-c/1215541#1215541)

Warning: The NSLock class uses POSIX threads to implement its locking behavior. When sending an unlock message to an NSLock object, you must be sure that message is sent from the same thread that sent the initial lock message. Unlocking a lock from a different thread can result in undefined behavior.

* Swift. Protocols and classes
* Swift. Trailing clouser

[](https://www.toptal.com/ios/interview-questions)
[](https://www.toptal.com/swift/interview-questions)
[](https://www.raywenderlich.com/53962/ios-interview-questions)
[](https://www.codementor.io/ios/tutorial/ios-interview-tips-questions-answers-objective-c)
[](http://career.guru99.com/top-15-swift-interview-questions/)
[](https://www.raywenderlich.com/112027/reference-value-types-in-swift-part-1)

## Competency matrix for iOS developer

## To practice 
- [ ] Rebuild [Design Patterns In Swift] (https://github.com/ochococo/Design-Patterns-In-Swift) 
- [ ] Rebuild [adapter-pattern](http://jangorman.github.io/blog/2014/12/01/design-patterns-in-swift-adapter-pattern/)
- [ ] Rebuild [Swift solutions for Codility](https://github.com/arietis/codility-swift)
- [ ] [Build in Swift] (https://github.com/ochococo/Design-Patterns-In-Swift)
- [ ] Build in Swift Fraction and Matrix library


