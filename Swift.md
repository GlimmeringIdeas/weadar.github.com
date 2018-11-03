# Swift



- `print("hello , swift")`，这句代码在Swift中是完整的程序，不需要像Objective-C 一样引入`main()`函数，也不需要在语句结尾上加上分号。

- `let number_let = 70`描述的是常量值，这种是不能修改的严谨类型。`var number_var : String = 70`描述的是变量值，可以支持修改，并且可以在变量名后面设置类型。不需要像Objective-C一样声明常量类型`NSString * number_int = 70`。

- 创建一个常量，显式指定类型为Float并指定初始值为4

  ```swift
  let label = "the width is"
  let width = 94
  // String()方法：转换let为String类型
  let widthLabel = label + String(width)
  // 另一种转换为String类型的方式
  let widthLabel = label + "\(width)"
  ```

  > 第4行代码中，如果把String()删除的话，系统报错为“Binary operator '+' cannot be applied to operands of type 'String' and 'Int'”

  

- 解决了Objective-C双引号内需要在写双引号的状态。使用一对三个单引号（`"""`）来包含多行字符串内容，字符串中的内容（包括引号、空格、换行符等）都会保留下来。

  ```swift
  var msg1 = "from apple developer webside"
  var msg2 = "from developer blog"
  let swift_quotation = """
  Learn Swift "\(msg1+msg2)" when I have time
  """
  
  // 如果你的代码中，多行字符串字面量包含换行符的话，则多行字符串字面量中也会包含换行符。如果你想换行，以便加强代码的可读性，但是你又不想在你的多行字符串字面量中出现换行符的话，你可以用在行尾写一个反斜杠（\）作为续行符。
  let softWrappedQuotation = """
  The White Rabbit put on his spectacles.  "Where shall I begin, \
  please your Majesty?" he asked.
  
  "Begin at the beginning," the King said gravely, "and go on \
  till you come to the end; then stop."
  """
  ```

  > 在使用"""的时候一定要另起一行。
  >
  > 如果 let swift_quotation = """ Learn Swift "\(msg1+msg2)" when I have time """ 这样子写是不生效的。报错为：**error: multi-line string literal closing delimiter must begin on a new line let swift_quotation = """Learn Swift "\(msg1+msg2)" when I have time""" **

  

- 元祖，把多个值组成一个复合值。元组内的值可以是任意的，并不要求是相同类型。

  ```swift
  // 创建元祖，http404Error的类型是(Int,String)
  let http404Error = (404,"Not Found") 
  // 将一个元祖的内容分解
  let (statusCode,statusMessage) = http404Error
  // 如果只需要一部分的元祖值
  let (statusCode,_) = http404Error
  // 通过下标来访问元祖内容
  print("Console statusCode is \(http404Error.0) \n Console statusMessage is \(http404Error.1)")
  
  // 也可以在定义的时候给元祖中的元素命名,那么可以通过元素名来访问
  let http404Error = (statusCode:404,statusMessage:"Not Found") 
  print("Console statusCode is \(http404Error.statusCode) \n Console statusMessage is \(http404Error.statusMessage)")
  ```

- 可选值类型，Swift通过可选值（optionals）类型来处理可能缺失的情况。

  可选类型表示两种可能：或者有值，那么你可以解析可选类型来访问到这个值；或者根本没有值。

  > Objective-C 中的没有这个特性，最接近的写法是：一个需要return值的方法，要不返回一个对象要不返回 `nil`，`nil` 表示“缺少一个合法的对象”。然而，这只对对象起作用——对于结构体，基本的 C 类型或者枚举类型不起作用。对于这些类型，Objective-C 方法一般会返回一个特殊值（比如 `NSNotFound`）来暗示值缺失。这种方法假设方法的调用者知道并记得对特殊值进行判断。然而，Swift 的可选类型可以让你暗示*任意类型*的值缺失，并不需要一个特殊值。

- 区间运算符

  *闭区间运算符*`(a...b)`   定义一个包含从 `a` 到 `b`（包括 `a` 和 `b`）的所有值的区间。`a` 的值不能超过 `b`。闭区间运算符在迭代一个区间的所有值时是非常有用的，如在 `for-in` 循环中：

  ```swift
  for index in 1...5 {
  
  }
  
  // 闭区间操作符有另一个表达形式，可以表达往一侧无限延伸的区间 —— 例如，一个包含了数组从索引 2 到结尾的所有值的区间。在这些情况下，你可以省略掉区间操作符一侧的值。这种区间叫做单侧区间，因为操作符只有一侧有值。
  for name in names[2...] {
      print(name)
  }
  // Brian
  // Jack
  
  for name in names[...2] {
      print(name)
  }
  ```

  *半开区间运算符* `(a..<b)`   定义一个从 `a` 到 `b` 但不包括 `b` 的区间。之所以称为*半开区间*，是因为该区间包含第一个值而不包括最后的值。半开区间的实用性在于当你使用一个从 0 开始的列表（如数组）时，非常方便地从0数到列表的长度。

  ```swift
  let names = ["Anna", "Alex", "Brian", "Jack"]
  let count = names.count
  for i in 0..<count {
  	print("第 \(i + 1) 个人叫 \(names[i])")
  }
  // 半开区间操作符也有单侧表达形式，附带上它的最终值。就像你使用区间去包含一个值，最终值并不会落在区间内。
  for name in names[..<2] {
      print(name)
  }
  ```



## 字符串和字符（Strings and Characters）

```swift
  // 计算字符串的长度
  let text_length = "字符串的长度"
  print("the number of characters in text_length is \(text_length.count)");
  // 每一个 String 值都有一个关联的索引（index）类型，String.Index，它对应着字符串中的每一个 Character 的位置。
  text_length[greeting.startIndex] // 字
  
  // 使用 startIndex 属性可以获取一个 String 的第一个 Character 的索引。使用 endIndex 属性可以获取最后一个 Character 的后一个位置的索引。因此，endIndex 属性不能作为一个字符串的有效下标。如果 String 是空串，startIndex 和 endIndex 是相等的。
  text_length[greeting.index(before:greeting.endIndex)] // 度
  text_length[greeting.index(after:greeting.startIndex)] // 符
  
  // 通过调用 String 的 index(before:) 或 index(after:) 方法，可以立即得到前面或后面的一个索引。您还可以通过调用 index(_:offsetBy:) 方法来获取对应偏移量的索引，这种方式可以避免多次调用 index(before:) 或 index(after:) 方法。
  let index = greeting.index(greeting.startIndex,offsetBy:3)
  greeting[index] //的
  
  // 使用 indices 属性会创建一个包含全部索引的范围（Range），用来在一个字符串中访问单个字符。
  for index in greeting.indices {
      print("\(greeting[index])",terminator:" ")
  }
  // 字 符 串 的 长 度 
  
  // 调用 insert(_:at:) 方法可以在一个字符串的指定索引插入一个字符，调用 insert(contentsOf:at:) 方法可以在一个字符串的指定索引插入一个段字符串。
  text_length.insert("!", at: text_length.endIndex)
  // text_length 变量现在等于 "字符串的长度!"
  
  text_length.insert(contentsOf:" 啊", at: text_length.index(before: text_length.endIndex))
  // text_length 变量现在等于 "字符串的长度 啊!"
  
  // 调用 remove(at:) 方法可以在一个字符串的指定索引删除一个字符，调用 removeSubrange(_:) 方法可以在一个字符串的指定索引删除一个子字符串。
  text_length.remove(at: text_length.index(before: text_length.endIndex))
  // text_length 现在等于 "字符串的长度 啊"
  
  let range = text_length.index(text_length.endIndex, offsetBy: -2)..<text_length.endIndex
  text_length.removeSubrange(range)
  // text_length 现在等于 "字符串的长度"
  
  // 字符串/字符可以用等于操作符（==）和不等于操作符（!=）
  let quotation = "We're a lot alike, you and I."
  let sameQuotation = "We're a lot alike, you and I."
  if quotation == sameQuotation {
      print("These two strings are considered equal")
  }
  
  // 通过调用字符串的 hasPrefix(_:)/hasSuffix(_:) 方法来检查字符串是否拥有特定前缀/后缀，两个方法均接收一个 String 类型的参数，并返回一个布尔值。
```

- Swift独有的子字符串，使用下标可以把从字符串中获取一个子字符串或者 `prefix(_:)` 之类的方法 就可以得到一个 `SubString` 的实例，而非另外一个 `String`。Swift 里的 `SubString` 绝大部分函数都跟 `String` 一样，意味着你可以使用同样的方式去操作 `SubString` 和 `String`。然而，跟 `String` 不同的是，你只有在短时间内需要操作字符串时，才会使用 `SubString`。当你需要长时间保存结果时，就把 `SubString` 转化为 `String` 的实例：

  ```swift
  let greeting = "Hello, world!"
  let index = greeting.index(of: ",") ?? greeting.endIndex
  let beginning = greeting[..<index]
  // beginning 的值为 "Hello"
  
  // 把结果转化为 String 以便长期存储。
  let newString = String(beginning)
  ```

## 集合类型（Collection Types）

Collection类型，`Arrays`、`Sets` 和 `Dictionaries` 三种基本的*集合类型*用来存储集合数据。数组（Arrays）是有序数据的集。集合（Sets）是无序无重复数据的集。字典（Dictionaries）是无序的键值对的集。这些类型中存储的数据值类型必须明确。

```swift
// 创建一个空数组
var array_empty = []
var diction_empty = [:]
// 创建一个由特定数据类型构成的空数组
var array_empty = [String]()
var diction_empty = [String:String]()
// 构造
var array:[String] = ["female","male"]
var diction = [
  "born":"1989",
  "sex":"female"
]

// 拼接数组
array_empty.append("Unknown")

// 使用加法操作符（+）来组合两种已存在的相同类型数组。新数组的数据类型会被从两个数组的数据类型中推断出来
var anotherThreeDoubles = Array(repeating: 2.5, count: 3) // anotherThreeDoubles 被推断为 [Double]，等价于 [2.5, 2.5, 2.5]
var sixDoubles = threeDoubles + anotherThreeDoubles // sixDoubles 被推断为 [Double]，等价于 [0.0, 0.0, 0.0, 2.5, 2.5, 2.5]
```

## 控制流（Control Flow）

```swift
一、For-In 循环
//  for-in 循环来遍历一个数组中的所有元素
let names = ["Anna", "Alex", "Brian", "Jack"]
for name in names {
    print("Hello, \(name)!")
}
// for-in 循环来遍历一个字典中的所有元素。注意：字典的内容理论上是无序的，遍历元素时的顺序是无法确定的。将元素插入字典的顺序并不会决定它们被遍历的顺序
let numberOfLegs = ["spider": 8, "ant": 6, "cat": 4]
for (animalName, legCount) in numberOfLegs {
    print("\(animalName)s have \(legCount) legs")
}

While 循环
While
Repeat-While
条件语句
If
Switch
不存在隐式的贯穿
区间匹配
元组
值绑定（Value Bindings）
Where
复合型 Cases
控制转移语句
Continue
Break
循环语句中的 break
Switch 语句中的 break
贯穿（Fallthrough）
带标签的语句
提前退出
检测 API 可用性
```





## 函数（Functions）

```swift
一、函数的定义与调用

二、函数参数与返回值
1. 无参数函数

2. 多参数函数

3. 无返回值函数

4. 多重返回值函数

5. 可选元组返回类型

三、函数参数标签和参数名称

1. 指定参数标签

2. 忽略参数标签

3. 默认参数值

4. 可变参数

5. 输入输出参数

四、函数类型

1. 使用函数类型

2. 函数类型作为参数类型

3. 函数类型作为返回类型

五、嵌套函数
```



## 闭包（Closures）

```swift
一、闭包表达式
1. 排序方法

2. 闭包表达式语法

3. 根据上下文推断类型

4. 单表达式闭包隐式返回

5. 参数名称缩写

6. 运算符方法

二、尾随闭包

三、值捕获

四、闭包是引用类型

五、逃逸闭包

六、自动闭包

```



## 枚举（Enumerations）

```swift
一、枚举语法
二、使用 Switch 语句匹配枚举值
三、关联值
四、原始值
1. 原始值的隐式赋值
2. 使用原始值初始化枚举实例
五、递归枚举
```



## 类和结构体（Classes and Structures）

```swift
一、类和结构体对比
1. 定义语法
2. 类和结构体实例
属性访问
结构体类型的成员逐一构造器
结构体和枚举是值类型
类是引用类型
恒等运算符
指针
类和结构体的选择
字符串、数组、和字典类型的赋值与复制行为
```



## 属性（Properties）

```swift
存储属性
常量结构体的存储属性
延迟存储属性
存储属性和实例变量
计算属性
简化 Setter 声明
只读计算属性
属性观察器
全局变量和局部变量
类型属性
类型属性语法
获取和设置类型属性的值
```



## 方法（Methods）

```swift
实例方法（Instance Methods）
self 属性
在实例方法中修改值类型
在可变方法中给 self 赋值
类型方法
```



## 继承（Inheritance）

```swift
定义一个基类
子类生成
重写
访问超类的方法，属性及下标
重写方法
重写属性
重写属性的 Getters 和 Setters
重写属性观察器
防止重写
```



## 构造过程（Initialization）

```swift
	存储属性的初始赋值
构造器
默认属性值
自定义构造过程
构造参数
参数名和参数标签
不带参数标签的构造器参数
可选属性类型
构造过程中常量属性的赋值
默认构造器
结构体的逐一成员构造器
值类型的构造器代理
类的继承和构造过程
指定构造器和便利构造器
指定构造器和便利构造器的语法
类的构造器代理规则
两段式构造过程
构造器的继承和重写
构造器的自动继承
指定构造器和便利构造器实践
可失败构造器
枚举类型的可失败构造器
带原始值的枚举类型的可失败构造器
构造失败的传递
重写一个可失败构造器
init!可失败构造器
必要构造器
通过闭包或函数设置属性的默认值
```



## 析构过程（Deinitialization）

```swift
析构过程原理
析构器实践
```



## 可选链式调用（Optional_Chaining）

```swift
	使用可选链式调用代替强制展开
为可选链式调用定义模型类
通过可选链式调用访问属性
通过可选链式调用来调用方法
通过可选链式调用访问下标
访问可选类型的下标
连接多层可选链式调用
在方法的可选返回值上进行可选链式调用
```



## 错误处理

```swift
表示并抛出错误
处理错误
用 throwing 函数传递错误
用 Do-Catch 处理错误
将错误转换成可选值
禁用错误传递
指定清理操作
```



## 类型转换（Type_Casting）

```swift
为类型转换定义类层次
检查类型
向下转型
Any 和 AnyObject 的类型转换
```





## 嵌套类型（Nested_Types）

```swift
嵌套类型实践
引用嵌套类型
```



## 协议（Protocols）

```swift
协议语法
属性要求
方法要求
异变方法要求
构造器要求
协议构造器要求的类实现
可失败构造器要求
协议作为类型
委托
在扩展里添加协议遵循
有条件地遵循协议
在扩展里声明采纳协议
协议类型的集合
协议的继承
类专属的协议
协议合成
检查协议一致性
可选的协议要求
协议扩展
提供默认实现
为协议扩展添加限制条件
```



## 泛型（Generics）

```swift
泛型所解决的问题
泛型函数
类型参数
命名类型参数
泛型类型
扩展一个泛型类型
类型约束
类型约束语法
类型约束实践
关联类型
关联类型实践
通过扩展一个存在的类型来指定关联类型
给关联类型添加约束
在关联类型约束里使用协议
泛型 Where 语句
具有泛型 Where 子句的扩展
具有泛型 Where 子句的关联类型
```







------

[<返回目录](https://weadar.github.io/index)