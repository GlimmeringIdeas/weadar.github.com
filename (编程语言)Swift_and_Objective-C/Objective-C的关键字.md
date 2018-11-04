## Objective-C的关键字和参数类型

#### @property

>  在普通类中自动生成_proertyName成员变量和getter、setter方法的声明和实现。

```objective-c
// Girl.h
#import <Foundation/Foundation.h>
@interface Girl : NSObject
@property (nonatomic, copy) NSString *name;
@property (nonatomic, copy) NSString *boyFriend;

/**
上述通过property生成的对象相当于声明了setter、getter方法
- (NSString *)name;
- (void)setName:(NSString *)name;

- (NSString *)boyFriend;
- (void)setBoyFriend:(NSString *)boyFriend;
*/
@end
```



> 在protocol、category中使用@property中只会生成setter、getter方法的声明。
>
> 在category中让对象进行实现，需要用到objc_setAssociatedObject、objc_getAssociatedObject



#### @synthesize

> 如果在@property里面没有对应的出现@synthesize，那就会默认自动创建@synthsize var = _var; ，自动生成 _var变量

```objective-c
// Girl.m

#import "Girl.h"
@implementation Girl
/* *************** MARK: 方法一 *************** */
// 如果不去手动定义一个变量，那么单独写getter或setter没有问题，但是同时重写就会报错了。
{
    NSString* _name; //手动注册变量
}
- (NSString *)name{
    if (!_name) {
        _name = @"zhangli";
    }
    return _name;
}
- (void)setName:(NSString *)name{
    _name = name;
}

/* *************** MARK: 方法二 *************** */
// 属性boyFriend原本是对应于_boyFriend变量的，这里通过@synthesize改变了属性、getter、setter对应的变量。（这点很有用处，比如可以在子类修改父类中readonly属性的值。）
//当然，如果不需要自定义实现setter、getter，那么只需要写一个@synthesize property = newName；

@synthesize boyFriend = man; //使用@synthesize,将属性对应于变量
- (NSString *)boyFriend {
    if (!man) {
        man = @"Jerod";
    }
    return man;
}
- (void)setBoyFriend:(NSString *)boyFriend{
    man = boyFriend;
}

@end
```



#### @dynamic

> 告诉编译器，属性setter和getter方法是用户自己实现的不用自动生成。
>
> 如果一个属性被声明了@dynamic var，如果不熟悉setter、getter方法，那么在编译阶段不会报错。一旦使用了instance.var = var_value，那么就会崩溃。



#### readonly

> 只产生getter，不产生setter。而且getter方法里面不能由下划线属性，如果要，必须先用@synthesize age =_age



#### assign

> 简单的赋值操作，不会对索引计数进行更改。适合基本数据类型。



#### retain / strong



#### nonatomic



#### automic



#### copy



#### weak





---

[<返回目录](https://weadar.github.io/index)