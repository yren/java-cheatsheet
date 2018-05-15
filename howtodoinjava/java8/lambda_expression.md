# translate source
* https://howtodoinjava.com/java-8/complete-lambda-expressions-tutorial-in-java/

## Java Lambda Expression
Lambda Express 是 Java 8 引入的一个新特性。

### 什么是 Lambda Expression 
Lambda expression 是 anonymous function （匿名函数）, i.e. 一个 function 没有名字和标识符。

换言之，Lambda expression 作为一个 constant value, 写在需要它的地方，一般作为参数传给方法。

Lambda expession 的一个重要特性是，在它出现的 context 中执行 (听上去有点拗口)。相似的 Lambda Expression 在不同的地方会有不同的执行结果。

Lambda expressio 的动人之处在于，它为 java 面向对象 (OOP) 编程引入了函数式编程的特性。在大部分 OOP 语言中 object 和 instance 是他们的一等公民, function 只能依附于某个 object.

在函数式编程中， 你可以定义 function, 把他们作为变量引用，作为参数传给方法。 JavaScript 是个好的例子，你可以把 callback 作为参数传给方法。 java 中一直没有这个有用的特性，直到 java8 引入了 Lambda Expression

一个典型的 Lambda Expression 看上去如下:
```
(x, y) -> x + y
```

基本 Lambda Expession 语法:
```
ether
(parameter) -> expression
or 
(parameters) -> {statements;}
or
() -> expression
```

例子:
```
(int a, int b) -> a * b
(a, b) -> a - b 
() -> 99 // take no parameter, return 99 
```