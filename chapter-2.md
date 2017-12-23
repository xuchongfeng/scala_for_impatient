chapter 2 控制结构与函数

2.1 条件表达式

```scala
if (x > 0) 1 else -1
if (x > 0) 1 else ()
```

2.2 语句终止

```scala
if (n > 0) {r = r * n; n -= 1}
if (n > 0) {
    r = r * n
    n -= 1
}
```

2.3 块表达式和赋值

```scala
x = 1 // return Uint
```

2.4 输入与输出

```scala
val name = readLine("Your name: ")
print("Your age: ")
val age = readInt()
println("Hello, %s! Next year, your age will be %d.", name, age + 1)
```

2.5 循环

```scala
while (n > 0) {
  r = r * n
  n -= 1
}

for (i <- 1 to n) r = r * i

val s = "hello"
var sum = 0
for (i <- 0 util s.length)
	sum += s(i)
```

​	无`continue`和`break`，可以使用如下方法

- 使用`Boolean`控制变量	
- 使用嵌套函数，从函数中使用`return`返回
- 使用`breaks`对象

2.6 高级`for`循环和`for`推导式

```scala
for (i <- 1 to 3; j <- 1 to 3 if i != j)
	print((10 * i) + j)

for (i <- 1 to 3; from = 4 - i; j <- from to 3)
	print((10 * i) + j)
```

2.7 函数

```scala
def abs(x: Double) = if (x >= 0) x else -x

def fac(n: Int) = {
    var r = 1
    for (i <- 1 to n) r = r * i
    r
}

// 递归函数，需要指明返回类型
def fac(n: Int): Int = if (n <= 0) 1 else n * fac(n-1)
```

2.8 默认参数和带名参数

```scala
def decorate(str: String, left: String = "[", right: String = "]") = left + str + right
```

2.9 变长参数

```scala
def sum(args: Int*) = {
    var result = 0
    for (arg <- args) result += arg
    result
}

val s = sum(1 to 5: _*)
```

2.10 过程

```scala
def printPic() {
    println("---------------")
    println("-.-.-.-.-.-.-.-")
    println("---------------")
}
```



2.11 懒值

```scala
lazy val x = sum(1 to 1000000: _*)
```



2.12 异常

```scala
try {
  process(new URL("www.baidu.com"))
} catch {
  case _: MalformedURLException => println("")
  case ex: IOException => ex.printStackTrace()
}

try {
} catch {
} finally {
}
```

