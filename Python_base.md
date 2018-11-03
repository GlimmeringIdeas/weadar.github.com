# Python 语法

## 1、Mac安装Python
如果你正在使用Mac，系统是OS X>=10.9，那么系统自带的Python版本是2.7。要安装最新的Python 3.7，有两个方法：
方法一：从Python官网下载Python 3.7的[安装程序](https://www.python.org/ftp/python/3.7.0/python-3.7.0-macosx10.9.pkg)（网速慢的同学请移步[国内镜像](https://pan.baidu.com/s/1kU5OCOB#list/path=%2Fpub%2Fpython)），双击运行并安装；
方法二：如果安装了[Homebrew](https://brew.sh/)，直接通过命令`brew install python3`安装即可。



## 2、字符串
```python
print('I\'m ok,\n I learning python')
print('\\\n\\')
print('\\\t\\')
print('''line1
...line2
...line3''')
print('包含中文的str')
print(ord('A'))
print(ord('中'))
print(chr(66))
print(chr(25991))
print('\u4e2d\u6587')
'ABC'.encode('ascii')
'中文'.encode('utf-8')
# 'ABC'.decode('ascii')
# '\xe4\xb8\xad\xe6\x96\x87'.decode('utf-8')
b'\xe4\xb8\xad\xff'.decode('utf-8', errors='ignore')
len('ABC')
len('中文')
# len('中文').encode('utf-8')
print('Hello,%s' % 'world')# 通过‘%’来传入字符串
print('Hi, %s, you have $%d.' % ('Michael', 1000000))
print('Hello,{0},所有科目的成绩平均提升了{1:.1f}%'.format("小明",17.58))
print('Age: %s. Gender: %s' % (25, True))
print('growth rate: %d %%' % 7)
```



## 3、布尔值
```python
print(True)
print(False)
print(3 > 2)
print(3 < 5)
print(True and True)
print(True and False)
print(False and False)
print(5 > 3 and 3 < 1)
print(True or True)
print(False or True)
print(False or False)
print(5 > 3 or 3 < 1)
print(not True)
print(not False)
print(not 1 > 2)
```

## 4、常量
```python
print(10/3)
print(9/3)
print(10//3)
print(10%3)
```



## 5、列表
```python
classmates=['Michael','Bob','Tracy']
print(len(classmates))
print(classmates)
print(classmates[0])
classmates.append('Adam')
print(classmates)
classmates.insert(1,'Jack')
print(classmates)
print(classmates.pop(2))
print(classmates)
L=['Apple',123,True]
print(L)
subList=['asp','php']
list=['python','java',subList,'scheme']
print(list)
list[2][0]='X'
print(list)
list[2][1]='Y'
print(list)
```



## 6、条件判断

```python
age = 20
if age >= 18:
    print('your age is',age)
    print('adult')
    
name = 'python'
if name == 'java':
    print('This lesson is java')
else:
    print('This lesson is python')

input_birth = input('birth:')
birth = int(input_birth)
if birth < 2000:
    print('00前')
else:
    print('00后')
```

## 7、循环

```python
names = ['Michael','Bob','Tracy']
for name in names:
    print(name)

sum = 0
for x in [1,2,3,4,5,6,7,8,9,10]:
    sum = sum + x
print(sum)

print(list(range(5)))

sum = 0
n = 99
while n > 0:
    if n < 40:
        break
    # if n % 2 == 0:
    #     continue
    sum = sum + n
    n = n - 1
print(sum)
print('End')
```

## 8、字典

```python
names = ['Michael','Bob','Tracy']
scores = [95,89,76]
d = {'Michael':95,'Bob':89,'Tracy':76}
print(d['Michael'])
d{'Adam'} = 100
print(d)
print('weadar' in d)
d.get('Tracy')
d.pop('Bob')
print(d)
```

## 9、集合

```python
nsset = set([3,2,3,2,1])
print(nsset)
nsset.add(4)
print(nsset)
nsset.remove(3)
print(nsset)
tempset = set([5,3,4,4,1])
print(nsset & tempset)
print(nsset | tempset)
a = ['c', 'b', 'a']
a.sort()
print(a)
b = a.replace('a','A')
print(b)
```

## 10、函数

```python
print(abs(100))
print(abs(-20))
print(abs(12.34))
print(max(1,2))
print(max(2,3,1,-5))
print(int('123'))
print(float('12.34'))
print(str(100))
print(bool(1)) 
def nop(): # def定义函数
    pass # 不做任何操作
def my_abs(x):
    if not isinstance(x ,(int , float)):
        raise TypeError('bad operand type')
    if x >= 0:
        return x
   	else:
        return -x
    
import math
def move(x,y,step,angle=0):
    nx = x + step * math.cos(angle)
    ny = y - step * math.sin(angle)
    return nx,ny
x,y = move = (100,100,60,math.pi/6)
print(x,y)
#假设只写一个接收值
r = move = (100,100,60,math.pi/6)
print(r)#其实打印结果也是两个值
print(math.sqrt(2))


print()
print()
print()
print()
print()
print()
print()
print()
```





















------

[<返回目录](https://weadar.github.io/index)