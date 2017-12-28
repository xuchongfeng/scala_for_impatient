chapter 8 继承

8.1 扩展类

```scala
class Employee extends Person {
    var salary = 0.0
}
```

8.2 重写方法

```scala
public class Person {
    override def toString = getClass.getName + "[name=" + name + ""
}
```

8.3 类型检查和转换

```scala
if (p.isInstanceOf[Employee]) {
    val s = p.asInstanceOf[Employee]
}

p match {
    case s: Employee => ...
  	case _ => ...
}
```

8.4 保护字段和方法

8.5 超类的构造

```scala
class Employee extends Person {
    public Employee(String name, int age, double salary) {
        super(name, age)
        this.salary = salary
    }
}
```

8.6 重写字段

```scala

```

8.7 匿名子类

```scala
val alien = new Person("Fred") {
    def greeting = "Greetings, Earthling! My name is Fred."
}
```

8.8 抽象类

```scala
abstract class Person(val name: String) {
    def id: Int
}
```

8.9 抽象字段

```scala
abstract class Person {
    val id: Int
  	var name: String
}
```

8.10 构造顺序和提前定义

```scala
class Creature {
    val range: Int = 10
  	val env: Array[Int] = new Array[Int](range)
}

class Ant extends Creature {
    override val range = 2
}
```

8.12 对象相等性

```scala
final override def equals(other: Any) = {
    val that = other.asInstanceOf[Item]
  	if (that == null) false
  	else description == that.description && price == that.price
}
```

