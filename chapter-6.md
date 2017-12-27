chapter 6 对象

6.1 单例对象

```scala
object Accounts {
  private var lastNumber = 0
  def newUniqueNumber() = {
    lastNumber += 1
    lastNumber
  }
}
```

6.2 伴生对象

```scala
class Account {
    val id = Account.newUniqueNumber()
  	private var balance = 0.0
  	def deposit(amount: Double) {
        balance += amount
    }
}

object Account {
  private var lastNumber = 0
  def newUniqueNumber() = {
    lastNumber += 1
    lastNumber
  }
}

```

6.3 扩展类或特质的对象

```scala
abstract class UndoableAction(val description: String) {
    def undo(): Uint
  	def redo(): Uint
}

object DoNothingAction extends UndoableAction("Do nothing") {
    override def undo() {}
  	override def redo() {}
}
```

6.4 Apply方法

```scala
Array(100) // Array.apply(100) => Array[Int](100)
new Array(100) // Array.this(100) => Array[Nothing] 100 null element
```

6.5 应用程序对象

```scala
object Hello extends App {
    if (args.length > 0)
  		println("Hello, " + args(0))
  	else
  		println("Hello, World!")
}
```

6.6 枚举

```scala
object TrafficLightColor extends Enumeration {
    type TrafficLightColor = Value
  	val Red, Yellow, Green = Value
}

import TrafficLightColor._
def doWhat(color: TrafficLightColor) = {
    if (color == Red) "stop"
  	else if (color == Yellow) "hurry up"
  	else "go"
}
```

