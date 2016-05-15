iOS Digest #3 - 05/15/2016
=======================

**Header** 
[Name](Link)

## Coding
**Singletone in Swift**
[Singletons](https://thatthinginswift.com/singletons/)
The propert way to write singleton in Swift - one line singletone:
```Swift
class IOSDigest {
static let sharedInstance = IOSDigest()
}
```

The old, Objective-C way:
@implementation Kraken

```Objective-C
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

## Open Source

## Design

## Work

## Other

## Apps

##Tools 


