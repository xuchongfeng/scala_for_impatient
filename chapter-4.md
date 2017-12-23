chapter 4 映射和元组

4.1 映射

```scala
val scores = Map(("1", 1), ("2", 2))
```

4.2 获取映射的值

```scala
val value = scores("1")
```

4.3 更新映射的值

```scala
scores("1") = "one"
val newScores = scores + ("Bob" -> 19, "Alice" -> 20)
```

4.4 迭代

```scala
for ((k, v) <- scores) {
    println("%s %d", k, v)
}
```

4.5 排序

```scala
val scores = scala.Collections.immutable.SortedMap(scores)
```

4.7 元组

```scala
val t = (1, "h")
t._1
t._2
```

4.8 zip

```scala
val x = Array(1,2,3)
val y = Array(4,5,6)
val pairs = x.zip(y)
```

