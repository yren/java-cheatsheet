# Default Method
## source
https://howtodoinjava.com/java-8/default-methods-in-java-8/

## Default Method
* java8 允许接口中含有 non-abstract 方法。这些方法声明为 default method. java 8 中引入 default method 是为了支持 lambda 表达式。

* default method 使你可以为接口添加新功能，并且不用破坏老代码的兼容性。例如:

```
// 任何实现 Moveable 接口的类可以直接调用 instance.move() 方法
public interface Moveable {
    default void move() {
        System.out.println("I'm moving");
    }
}
```

* 实现类也可以 `@Override` default method