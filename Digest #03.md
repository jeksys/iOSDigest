iOS Digest #3 - 05/15/2016
=======================

## Coding
**Swift 3.0**
[What's new in Swift 3.0](https://www.hackingwithswift.com/swift3)

**Singletone in Swift**
[Singletons](https://thatthinginswift.com/singletons/)
The propert way to write singleton in Swift - one line singletone:
```Swift
    class IOSDigest {
    static let sharedInstance = IOSDigest()
}
```

The old, Objective-C way:
```Objective-C
@implementation IOSDigest

+ (instancetype)sharedInstance {
    static IOSDigest *sharedInstance = nil;
    static dispatch_once_t onceToken;

    dispatch_once(&onceToken, ^{
        sharedInstance = [[IOSDigest alloc] init];
    });
    return sharedInstance;
}

@end
```

**Sustainable code**
[How to make your code sustainable](https://vimeo.com/138774243)
Do you often develop your code from scratch? Don't forget about people who will support it later
You code will evlove. 

**Pattern matching in Swift**
[Pattern Matching](http://alisoftware.github.io/swift/pattern-matching/2016/03/27/pattern-matching-1)

**Protocols vs Categories**
[Protocol-Oriented Views in Swift](https://www.natashatherobot.com/protocol-oriented-views-in-swift)

[CATEGORIES CONSIDERED HARMFUL](http://www.catehuston.com/blog/2016/02/04/categories-considered-harmful/)

**MVC as Massive View Controllers**
[Fixing Massive View Controller](http://clean-swift.com/clean-swift-ios-architecture/)


## Open Source
**Networking**
[Simple HTTP Networking](https://github.com/3lvis/Networking)
```Swift
    let networking = Networking(baseURL: "https://api-news.layervault.com/api/v2")
    networking.GET("/stories") { JSON, error in
        if let JSON = JSON {
        // Stories JSON: https://api-news.layervault.com/api/v2/stories
    }
}
```

**Theme manager**
[https://github.com/jiecao-fm/SwiftTheme](https://github.com/jiecao-fm/SwiftTheme)

## Other
**Android**
[Instant Apps](https://developer.android.com/topic/instant-apps/index.html)
Apple please make instant apps for iOS, it's so cool