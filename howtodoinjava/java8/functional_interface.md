# Functional Interface
## source
* https://howtodoinjava.com/java-8/functional-interface-tutorial/

## Functional Interface

* Functional Interface 叫做 Single Abstract Method interface, (SAM). 只有一个抽象方法的接口。@FunctionalInterface 用于 compile 检查。

```
@FunctionalInterface
public interface MyFunctionalInterface {
    public void firstWork();
}
```

* 注意，没有 `@FunctionalInterface` 的接口依然可以是合法的 FunctionalInterface, annotation 只用于编译器检查错误。

* 接口中实现 Object 方法，不算违法 FunctionalInterface, 以下是合法的 FunctionalInterface

```
@FunctionalInterface
public interface MyFirstInterface {
    public void firstWork()
    
    @Override
    public String toString();
}
``` 