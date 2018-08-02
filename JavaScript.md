## 区分大小写

JavaScript 是一种区分大小写的语言。这意味着 JavaScript 的关键字、变量名、函数名、以及任何其他的标识符必须使用一致的大小写形式。比如 atguigu、Atguigu 或 ATGUIGU 是不同的变量名。

```
var jinyunlong = "jinyunlong";// 定义jinyunlong变量
console.log(jinyunlong);// 打印jinyunlong变量
var Jinyunlong = "Jinyunlong";// 定义Jinyunlong变量
console.log(Jinyunlong);// 打印Jinyunlong变量
var JINYUNLONG = "JINYUNLONG";// 定义JINYUNLONG变量
console.log(JINYUNLONG);// 打印JINYUNLONG变量
```

> **值得注意的是:** 在 JavaScript 中定义变量名和函数名时应该特别注意。

## 空格和换行

JavaScript 会忽略出现在代码中的空格、制表符和换行符。

由于可以自由地在代码中使用空格、制表符和换行符，所以采用整齐、一致的缩进来形成统一的编码风格，从而提高代码的可读性显得尤为重要。

JavaScript 还可以识别水平制表符、垂直制表符、换页符等，JavaScript 将以下字符识别为行结束符：换行符、回车符、行分隔符、段分隔符等。回车符加换行符在一起被解析为一个单行结束符。

## 可选的分号

JavaScript 的语句一般是以一个分号作为结尾。当然，JavaScript 也允许忽略这个分号。如果省略分号，则由解释器确定语句的结尾，如下述代码：

```
var sum = a + b// 即使没有分号也是有效的语句 —— 不推荐
var diff = a - b;// 有效的语句 —— 推荐
```

> **值得注意的是:** 在 JavaScript 中，虽然语句结尾的分号不是必需的，但还是建议任何时候都不要省略。使用分号是一个非常好的编程习惯。

## 注释

在编写 JavaScript 代码时，经常利用注释为代码添加说明。注释的内容会被 JavaScript 解释器/引擎忽略，JavaScript 支持两种格式的注释:

- 单行注释

```
// 这里是单行注释
```

- 多行注释

```
/*
 * 这里是多行注释
 */
```

> **值得注意的是:** 上述注释的第二行是以星号开始，但这并不是必需的。

## 语句

JavaScript代码将多行组合成一个代码块，每个代码块一般是以左花括号（{）开始，以右花括号（}）结束。例如下述代码:

```
if(test){
	test = false;
	alert(test);
}
```

> **值得注意的是:** 一般在执行多行代码时才需要语句块，但最好是始终都使用花括号将代码块进行包裹。

## 关键字

JavaScript 定义了一组具有特定用途的关键字，这些关键字可用于表示语句的开始或结束、或者执行特定操作等。也就是说，定义变量名或、函数名或对象名时不能使用这些名称。

[![img](https://github.com/jyl/front-end-notes/raw/master/ecmascript-5/01.png)](https://github.com/jyl/front-end-notes/blob/master/ecmascript-5/01.png)

## 保留字

JavaScript 除了定义了一组关键字，还定义了一组同样不能作为变量名、函数名或对象名的保留字。保留字可能在将来被作为新的关键字出现的。

[![img](https://github.com/jyl/front-end-notes/raw/master/ecmascript-5/02.png)](https://github.com/jyl/front-end-notes/blob/master/ecmascript-5/02.png)



## 变量

### 什么是变量

变量是存储数据信息的容器。

变量被认为是有名字的容器。在代码中，使用变量名为值命名，需要遵守一定的规则。

> **值得注意的是:**
>
> - 在 JavaScript 代码中，必须先声明一个变量，这个变量才能被使用。
> - JavaScript 中的变量是弱类型的，也称之为松散类型的。所谓弱类型/松散类型就是可以用来保存任何类型的数据。

```
var v = 100;
v = "string";
```

### 变量的声明

在 JavaScript 代码中，使用变量前应当先声明。变量是使用关键字 `var` 声明的。

#### 只声明未初始化，变量的值自动取值为 undefined

- 一行代码只声明一个变量:

```
var sum;// 值为undefined
var msg;// 值为undefined
```

- 一行代码声明多个变量

```
var x, y, z;// 值为undefined
```

### 将变量的声明和初始化合写在一起

- 一行代码只声明一个变量并赋值:

```
var sum = 100;// 值为 100
var msg = "this is message";// 值为 this is message
```

- 一行代码声明多个变量并赋值:

```
var x = 0, y = 1, z = 2;
```

> **值得注意的是:** 等号（=）是赋值运算符。

### 命名规则

变量的命名需要遵守一定的规则的，具体规则如下:

- 必须以字母、下划线（_）、美元符号（$）开始。
- 不能以数字开头。
- 不能使用关键字和保留字作为名称。
- 由于 JavaScript 是区分大小写的，大写字母与小写字母并不冲突。
- 名称最好有明确的含义。
- 可以采用“下划线命名法”、“小驼峰命名法”或“大驼峰命名法” 之一，在开发团队内进行协调统一。

### 声明的问题

#### 重复的声明

使用 `var` 语句重复声明变量是合法且无害的。但是如果重复声明并初始化的，这就表示重复声明并初始化。由于 JavaScript 变量只能存储一个数据，之前存储的数据会被覆盖。

```
var msg = "this is message";// 值为 this is message
var msg = 100;// 值为 100
```

#### 遗漏的声明

- 直接读取一个没有声明的变量的值，JavaScript会报错。
- 为一个没有声明的变量初始化，是合法的，但并不推荐这样使用。

### 变量的使用

对声明的变量既可以读取操作，也可以赋值操作。

- 读取操作

```
var message;// 只声明未初始化
console.log(message);// 输出 undefined
var msg = “this is message”;// 声明并初始化
console.log(msg);// 输出 this is message
```

- 赋值操作

```
var message;// 只声明未初始化
message = "this is message";// 初始化操作
var msg = "this is message";// 值会被覆盖
msg = "this is another message";// 重新赋值
```

## 常量

### 什么是常量

常量就是一个只读（read-only）的变量。

常量与变量类似，同样用于存储数据信息。只是常量的数据一旦被定义，便不能被修改。

> **值得注意的是:**
>
> - 常量名习惯使用全大写形式。
> - ECMAScript 5新增了声明常量使用的关键字 const。
> - 如果省略const关键字，JavaScript会认为是一个变量。

### 常量的声明

- 在 ECMAScript 5 版本前，没有定义常量的语法。使用 `var` 关键字定义变量，人为规定值不改变，也可以是不严格的常量。

```
var MY_CONST = 10;
```

- 在 ECMAScript 5 版本后，提供了关键字 `const` 定义常量。

```
const MY_FAV = 100;
```

> **值得注意的是:** 常量的声明，必须进行初始化操作，否则会报错误。
>
> ```
> const FOO; // SyntaxError: missing = in const declaration
> ```

### 常量的使用

常量一旦被声明并初始化，值并不能被改变。常量的使用只能进行读取操作:

```
// 定义常量MY_FAV并赋值7
const MY_FAV = 7;

// 在 Firefox 和 Chrome 这会失败但不会报错(在 Safari这个赋值会成功)
MY_FAV = 20;
console.log(MY_FAV); // 输出 7
const MY_FAV = 20; // 尝试重新声明会报错 
var MY_FAV = 20;// MY_FAV 保留给上面的常量，这个操作会失败
console.log(MY_FAV);// MY_FAV 依旧为7
```

 

 JavaScript 提供了一组用于操作数据值的运算符。

- 算数运算符（+  -  *  /  %  ++  --）
- 比较运算符（>  >=  <  <=  ==  !=  ===  !==）
- 逻辑运算符（&&  ||  !）
- 赋值运算符（=  +=  -=  *=  /=  %=  ）
- 字符串连接运算符（+）
- 三元运算符（? :）
- 特殊运算符（typeof  instanceof  delete）

## 算数运算符

给定 A=20 B=10 条件，下述表格描述算数运算符:

| 运算符 | 描述                         | 例子        |
| ------ | ---------------------------- | ----------- |
| +      | 两个运算数相加               | A + B = 30  |
| -      | 第一个运算数减去第二个运算数 | A – B = 10  |
| *      | 两个运算数相乘               | A * B = 200 |
| /      | 第一个运算数除以第二个运算数 | A / B = 2   |
| %      | 求余运算符，计算整除后的余数 | A % B = 0   |
| ++     | 增量运算符，整数值逐次加 1   | A++ = 21    |
| --     | 减量运算符，整数值逐次减 1   | A-- = 19    |

算数运算符的基本操作比较简单，但下述情况需要特别注意:

- 如果运算数中的一个或两个是字符串类型，JavaScript 会自动转换为数字值，再进行计算。
- 如果运算数中的一个或两个是字符串类型，但其中的字符不是数字，JavaScript 会自动转换数字值失败，得到 NaN 结果。
- 任何一个运算数是 NaN，结果都是 NaN。
- 布尔值 false 和 true 会转换为 0 和 1 进行计算。

### 求余运算符

求余运算符，用于计算两个运算数整除后的余数。

```javascript
console.log( 10 % 3 );// 输出 1

console.log( -10 % 3 );// 输出 -1

console.log( 10 % -3 );// 输出 1

console.log( -10 % -3 );// 输出 -1
```

### 自增运算符

自增运算符，用于整数值逐次加 1。分别具有两种用法:

- 前置型：自增运算符位于运算数之前。先加 1，再赋值。
- 后置型：自增运算符位于运算数之后。先赋值，再加 1。

```javascript
var x = 3;
console.log( x++ );// 输出 3
console.log( x );// 输出 4

var y = 3;
console.log( ++y );// 输出 4
console.log( y );// 输出 4
```

### 自减运算符

自减运算符，用于整数值逐次减 1。分别具有两种用法:

- 前置型：自增运算符位于运算数之前。先减 1，再赋值。
- 后置型：自增运算符位于运算数之后。先赋值，再减 1。

```javascript
var x = 3;
console.log( x-- );// 输出 3
console.log( x );// 输出 2

var y = 3;
console.log( --y );// 输出 2
console.log( y );// 输出 2
```

## 比较运算符

给定 A=20 B=10条件，下述表格描述比较运算符:

| 运算符 | 描述                                                        | 例子            |
| ------ | ----------------------------------------------------------- | --------------- |
| ==     | 检查两个运算数的值是否相等，如果相等则结果为 true           | A == B 为 false |
| !=     | 检查两个运算数的值是否不等，如果不等则结果为 true           | A != B 为 true  |
| >      | 检查左边运算数是否大于右边运算数，如果是则结果为 true       | A > B 为 true   |
| >=     | 检查左边运算数是否大于或等于右边运算数，如果是则结果为 true | A >= B 为 true  |
| <      | 检查左边运算数是否小于右边运算数，如果是则结果为 true       | A < B 为 false  |
| <=     | 检查左边运算数是否小于或等于右边运算数，如果是则结果为 true | A <= B 为 false |

### 全等与全不等

| 运算符 | 描述                                          |
| ------ | --------------------------------------------- |
| ===    | 两个运算数的值相等并且类型相同时，结果为 true |
| !==    | 两个运算数的值不等或者类型不同时，结果为 true |

```javascript
var x = 10;
var y = '10';

console.log( x == y );// 输出 true
console.log( x === y );// 输出 false
console.log( x != y );// 输出 false
console.log( x !== y );// 输出 true
```

### isNaN 函数

isNaN() 函数用于判断其参数是否为 NaN（非数字值）。

多用于检测使用类型转换函数进行数据类型转换后的结果是否为合法的数字值。

> **值得注意的是:** NaN 与任何值（包括自身）进行比较，结果都是 false。不能使用 `==` 或者 `===` 运算符判断某个值是否是 NaN，而只能使用isNaN() 函数。

```javascript
console.log(isNaN(parseInt('123.45a')));// 输出 true

console.log(isNaN('123.45a'));// 输出 true

console.log(isNaN(Number('123.45a')));// 输出 true
```

## 逻辑运算符

给定 A=20 B=10条件，下述表格描述比较运算符:

| 运算符 | 描述                                                         | 例子               |
| ------ | ------------------------------------------------------------ | ------------------ |
| `&&`   | 逻辑与运算符。如果两个运算数都是 true，则返回 true           | A && B 为 true     |
| `||`   | 逻辑或运算符。如果两个运算数中任何一个是 true，则返回 true   | A                  |
| `!`    | 逻辑非运算符。用于改变运算数的逻辑状态。如果逻辑状态为 true，则通过逻辑非运算符是逻辑状态改为 false | !(A && B) 为 false |

### 逻辑与运算符

| B1    | B2    | B1 && B2 |
| ----- | ----- | -------- |
| false | false | false    |
| false | true  | false    |
| true  | false | false    |
| true  | true  | true     |

```javascript
console.log( false && true );// 输出 false
console.log( true && true );// 输出 true

// 数字值 1 和 0 转换为布尔值 true 和 false
console.log( 1 && 0 );// 输出 false

// 空字符串转换为布尔值 false，非空字符串转换为布尔值 true
console.log( "" && "atguigu" );// 输出 false
```

### 逻辑或运算符

| B1    | B2    | B1 或 B2 |
| ----- | ----- | -------- |
| false | false | false    |
| false | true  | true     |
| true  | false | true     |
| true  | true  | true     |

```javascript
console.log( false || true );// 输出 true
console.log( false || false );// 输出 false

// 数字值 1 和 0 转换为布尔值 true 和 false
console.log( 1 || 0 );// 输出 true

// 空字符串转换为布尔值 false，非空字符串转换为布尔值 true
console.log( "" || "atguigu" );// 输出 true
```

### 逻辑非运算符

| B1    | !B1   |
| ----- | ----- |
| false | true  |
| true  | false |

```javascript
console.log( !true );// 输出 false

console.log( !1 );// 输出 false

console.log( !"atguigu" );// 输出 false
```

> **值得注意的是:** 能被转换为 false 的值有null, 0, NaN, 空字符串("") 和 undefined。

### 逻辑短路原则

所谓短路原则，就是只要确定运算符前面的运算数为 true 或 false，就可以确定返回结果为 true 或 false。

- 逻辑与运算符
  - 逻辑与运算符前面为false，结果都将返回逻辑与运算符前面的。
  - 逻辑与运算符前面为true，结果都将返回逻辑与运算符后面的值。
- 逻辑或运算符
  - 逻辑或运算符前面为false，结果都将返回逻辑或运算符后面的值。
  - 逻辑或运算符前面为true，结果都将返回逻辑或运算符前面的值。

## 赋值运算符

赋值运算符用于为变量或属性进行赋值操作。

```javascript
var atguigu = "atguigu";// 将字符串 "atguigu" 赋值给变量 atguigu
var obj.x = 1;// 将数字值 1 赋值给 obj 对象的 x 属性
```

赋值运算符就是将右边运算数的值赋给左边运算数。

```javascript
C = A + B;// 将A+B的值赋给C
```

| 运算符 | 描述                                                         | 例子                    |
| ------ | ------------------------------------------------------------ | ----------------------- |
| +=     | 加等赋值运算符，将右边运算符与左边运算符相加并将运算结果赋给左边运算数 | C += A 相当于 C = C + A |
| -=     | 减等赋值运算符，将左边运算数减去右边运算数并将运算结果赋给左边运算数 | C -= A 相当于 C = C - A |
| *=     | 乘等赋值运算符，将右边运算数乘以左边运算数并将运算结果赋给左边运算数 | C *= A 相当于 C = C * A |
| /=     | 除等赋值运算符， 将左边运算数除以右边运算数并将运算结果赋值给左边运算数 | C /= A 相当于 C = C / A |
| %=     | 模等赋值运算符，用两个运算数做取模运算并将运算结果赋值给左边运算数 | C %= A 相当于 C = C % A |

> **值得注意的是:** C += A由于运行时可以进行优化，执行效率都要优于C = C + A。

### 字符串连接运算符

字符串连接运算符使用的是加法运算符（+）。

- 两个运算数都是数字值时，"+"用于两个运算数相加计算。
- 两个运算数中的一个是字符串时，"+"用于字符串连接计算。

```javascript
var num1 = 1;
var num2 = 2;
var num3 = num1 + num2; // 加法计算

var num4 = "4";
var num5 = num1 + num4; //字符串拼接计算 
```

## 条件运算符

条件运算符，首先判断一个表达式是真或假，然后根据判断结果执行两个给定指令中的一个。

| 运算符 | 描述       | 说明                     |
| ------ | ---------- | ------------------------ |
| ? :    | 条件表达式 | 如果条件为真 ? X值 : Y值 |

```javascript
var age = 20;
var msg = age > 18 ? "成年人" : "未成年人";
```

### 条件运算符嵌套

条件运算符中，每个表达式可以又是一个条件运算表达式，称为条件运算的嵌套。

```javascript
var score = 85;
var result = score >= 80 ? "优秀" : (
			score >= 60 ? "合格" ："不合格"
		);
```

上述代码的执行顺序如下:

1. 执行 score >= 60 ? "合格" ："不合格" 条件运算符。
2. 根据上一行的计算结果，再执行 score >= 80 ? "优秀" : 条件运算符

### 运算符的优先级

下面的表将所有运算符按照优先级的不同从高到低排列:

