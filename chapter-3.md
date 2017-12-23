chapter 3  数组相关操作

3.1 定长数组

```scala
val nums = new Array[Int](10)
val s = new Array[String](10)
val s = Array("Hello", "World")
s(0) = "Goodbye"
```

3.2 变长数组

```scala
import scala.collection.mutable.ArrayBuffer

val b = ArrayBuffer[Int]()
b += 1
b += (1,2,3,4)
b ++= Array(8, 13, 21)
b.trimEnd(5)

// result
b: scala.collection.mutable.ArrayBuffer[Int] = ArrayBuffer()
res0: b.type = ArrayBuffer(1)
res1: b.type = ArrayBuffer(1, 1, 2, 3, 4)
res2: b.type = ArrayBuffer(1, 1, 2, 3, 4, 8, 13, 21)
```

3.3 遍历数组和数组缓冲

```scala
for (i <- 0 until a.length) println(i + ":" + a(i))
```

3.4 数组转换

```scala
val a = Array(2,3,5,7)
val result = for (elem <- a) yield 2 * elem
val result = for (elem <- a if elem % 2 == 0) yield 2 * elem

a.filter {_ % 2 == 0} map {2 * _}
```

3.5 常用算法

```scala
val a = Array(1,2,3,4)
scala.util.Sorting.quicksort(a)

min, max, quickSort
```

3.7 多维数组

```scala
val matrix = Array.ofDim[Double](3,4)
matrix(row)(col) = 42
```

