chapter 9 文件和正则表达式

9.1 读取行

```scala
import scala.io.Source
val source = Source.fromFile("myfile.txt", "UTF-8")
val lineIterator = source.getLines

for (l <- lineIterator) println(l)

val lines = Source.getLines.toArray
val contents = Source.mkString
```

9.2 读取字符

```scala
for (c <- source) println(c)

// stream processing

val source = Source.fromFile("myfile.txt", "UTF-8")
val iter = source.buffered
while (iter.hasNext()) {
    if (iter.head) iter.next
  	else ...
}
source.close()
```

9.3 读取词法单元和数字

```scala
val tokens = source.mkString.split("\\S+")

val numbers = for (w <- tokens) yield w.toDouble
val numbers = tokens.map(_.toDouble)

println("How old are you? ")
val age = readInt()
```

9.4 从URL或其它源读取

```scala
val source = Source.FromURL("http://www.baidu.com", "UTF-8")
val source = Source.fromString("Hello, World")
val source = Source.stdin
```

9.5 读取二进制文件

```scala
val file = new File(filename)
val in = new FileInputStream(file)
val bytes = new Array[Byte](file.length.toInt)
in.read(bytes)
in.close()
```

9.6 写入文本文件

```scala
val out = new PrintWriter("numbers.txt")
for (i <- 1 to 100) out.println(i)
out.close()
```

9.7 访问目录

```scala
import java.io.File
def subdirs(dir: File): Iterator[File] = {
    val children = dir.listFiles.filter(_.isDirectory)
  	children.toIterator ++ children.toIterator.flatMap(subdirs _)
}
for (d <- subdirs(dir)) println(d)
```

9.8 序列化

```scala
val fred = new Person(...)
import java.io._
val out = new ObjectOutputStream(new FileOutputStream("/tmp/test.obj"))
out.writeObject(fred)
out.close()
val in = new ObjectInputStream(new FileInputStream("/tmp/test.obj"))
val savedFred = in.readObject().asInstanceOf[Person]
```

9.9 进程控制

```scala
import sys.process._
"ls -al .."!
```

9.10 正则表达式

```scala
val numPattern = "[0-9]+".r

for (matchString <- numPattern.findAllIn("99 bottles, 98 bottles"))
	println(matchString)

val ml = wsnumwsPattern.findFirstIn("99 bottles, 98 bottles")

numPattern.findPrefixOf("99 bottles, 98 bottles")
```

9.11 正则表达式组

```scala
val numitemPattern = "([0-9]+) ([a-z]+)".r

val numItemPattern(num, item) = "99 bottles"
```

