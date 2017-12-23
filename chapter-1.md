Chapter 1  基础

1.1 scala 解释器

1.2 值和变量

```scala
val answer = 8 * 5 + 2 (不可变值)
var answer = 8 * 5 + 2 (可变变量)

val xmax, ymax = 100
var greeting, message: String = null
```

1.3 常用类型

```scala
Byte
Char
Short
Int
Long
Float
Double
Boolean
```

1.4 算术和操作符重载

```scala
val x: BigInt = 1234567
x * x * x

1 to 10
```

1.5 调用函数和方法

```scala
import scala.math._

sqrt(2)
pow(2, 4)
min(3, Pi)
```

1.6 apply方法

```scala
"hello"(4)
"hello".apply(4)

BigInt("1234567")
BigInt.apply("1234567")
```

练习
