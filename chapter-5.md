chapter 5 类

5.1 简单类和无参方法

```scala
class Counter {
  private var value = 0
  def increment(): Unit = {
    value += 1
  }
  def current = value
}

val myCounter = new Counter
myCounter.increment()
println(myCounter.current)
```

5.2 get和set属性

```scala
class Counter {
  private var value = 0
  def increment(): Unit = {
    value += 1
  }
  def current = value
  def getValue = value
  def setValue(value: Int) = {
    this.value = value
  }
}

val myCounter = new Counter
myCounter.increment()
println(myCounter.current)

myCounter.setValue(100)
println(myCounter.current)
```

5.4 对象私有字段

```scala
class Counter {
  private var value = 0
  private[this] var key = "key"
}
```

5.5 Bean

5.6 辅助构造函数

```scala
class Person {
    private var name = ""
    private var age = 0
    
  	def this(name:String) {
        this()
      	this.name = name
    }
  
  	def this(name:String, age:Int) {
        this(name)
      	this.age = age
    }
}

val p1 = new Person
val p2 = new Person("jack")
val p3 = new Person("alice", 12)
```

5.7 主构造器

```scala
class Person(val name: String, val age: Int) {
    ...
}
```

5.8 嵌套类

```scala
class Network {
    class Member(val name: String) {
        val contacts = new ArrayBuffer[Member]
    }
  	private val members = new ArrayBuffer[Member]
  	def join(name: String) = {
        val m = new Member(name)
      	members += m
      	m
    }
}
```

