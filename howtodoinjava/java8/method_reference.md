# Method Reference
* in java8 可以引用 class 或 object 的 method, 如下 : `class::methodName`

## java8 有 4 种 method Reference
1. reference `static method`, `Math::max` 等于 Math.max(x, y)
2. reference `instance method from instance`, `System.out.println` 等于 `System.out.println(x)`
3. reference `instance method from class type`, `String::length` 等于 str.length()
4. reference `constructor`, `ArrayList::new` 等于 new ArrayList()

## reference static method - `Class::staticMethod`
```
List<Integer> integers = Arrays.asList(1, 23, 433, 5);
Optional<Integer> max = integers.stream().reduce(Math::max);
max.ifPresent(v -> System.out.println(v));
```

## ref instance method from instance - `instance::instanceMethod`
```
List<Integer> integers = Arrays.asList(1, 12, 433, 5);
Optional<Integer> max = integers.stream().reduce(Math::max);
max.ifPresent(System.out::println);
```

## ref instance method from class type - `Class::instanceMethod`

```
List<String> strings = Arrays.asList("how", "to", "do");
List<String> sorted = strings.stream().sorted(String::compareTo).collect(Collectors.toList());
```

## ref to constructor - `Class::new`

```
List<Integer> integers = IntStream.range(1, 100).boxed().collect(Collectors.toCollection(ArrayList::new));

```