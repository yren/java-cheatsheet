# translate source
* https://howtodoinjava.com/core-java/generics/complete-java-generics-tutorial/

## why generics

## how generics works in java

## type of generics

### generic type class or interface
```
class DemoClass {
  private Object t;
  public void set(Object t) {this.t = t;}
  public Object get() {return t;}
}
```

```
class DemoClass<T> {
  private T t;
  public void set(T t) {this.t = t;}
  public T get() {return t;}
}
```
现在 DemoClass 不会被用错误的 type 了。

```
DemoClass<String> instance = new DemoClass<String>();
instance.set("hello");
```
