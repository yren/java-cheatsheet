## Streams API

* java8 引入 Streams API 用来处理集合数据，包括 filter, transformation ...
例子：

```
//  使用 stream api 过滤掉集合中以 prefix 开头的 string, items.stream() 表示你想用 stream api 处理 item 数据
 List<String> items;
String prefix;
List<String> filterList = items.stream().filter(e -> (!e.startsWith(prefix))).collect(Collectors.toList());
``` 

## External iteration vs. Internal iteration

### External iteration
* Java7 及以前, collections framework 使用 External iteration. 集合类实现了 Iterable 接口， 例如:

```
public class IterationExample {
    public static void main(String[] args) {
        List<String> alphabets = Arrays.asList(new String[]{"a", "b", "c", "d"});
        for (String letter: alphabets) {
            System.out.println(letter.toUpperCase());
        }
    } 
}
```
Or:
```
public class IterationExample {
    public static void main(String[] args) {
        List<String> alphabets = Arrays.asList(new String[] {"a", "b", "c", "d"});
        Iterator<String> iterator = alphabets.listIterator();
        while (iterator.hasNext()) {
            System.out.println(iterator.next().toUpperCase());
        }
    }
}
```
* External Iteration 的问题

1. for-each loop/ iterator 都是按照顺序处理集合给定元素。
2. 减少了控制顺序的机会，也许重新排序后会有更好的效率, parallel, short-circuit, laziness

### Internal iteration
* 有时候 External iteration 的顺序处理是我们想要的，但效率不一定最高，这是 internal iteration 可以帮助我们，我们每个元素需要执行的逻辑，什么顺序，或如何执行我们就不管了。

```
public class IterationExamples {
    public static void main(String[] args) {
        List<String> alphabets = Arrays.asList(new String[]{"a", "b", "c", "d"});
        alphabets.forEach(l -> l.toUpperCase());
    }
}
```
