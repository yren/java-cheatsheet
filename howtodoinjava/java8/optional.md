# Java8 Optionals
## Source
* https://howtodoinjava.com/java-8/java-8-optionals-complete-reference/

## Java8 Optionals 是如何工作的
* Optional 使用一个 non-null 值来替换可能为 null 的情形。Optional 包含 non-null reference (present), 包含 nothing (absent)

```
Optional<Integer> canEmpty = Optional.of(5);
canEmpty.isPresent(); // return true
canEmpty.get(); // return 5

Optional<Integer> canEmpty = Optional.empty();
canEmpty.isPresent(); // return false
```

* 可以把 Optional 看做一个 single value container, 或者包含值或者没有

## Creating Optional objects
1. use `Optional.empty()` create empty optional.

```
Optional<Integer> possible = Optional.empty();
```

2. use `Optional.of()` 使用 non-null 值生成 optional obj, 如果传入 null ，会抛 NullPointerException

```
Optional<Integer> possible = Optional.of(5);
```

3. use `Optional.ofNullable()` 创建一个可以包含 null 的对象

```
Optional<Integer> possible = Optional.ofNullable(null);
possible = Optional.ofNullable(5);
```

## Do something if Optional value present

```
Optional<Integer> possible = Optional.of(5);
possible.ifPresent(System.out::println);
```

or

```
if (possible.isPresent()) {
    System.out.println(possible.get());
}
```

## Default/absent values and actions

```
// 假设 companyOptional 由某个方法返回
Optional<Company> companyOptional = Optional.empty();


// check optional , 如果 present 返回它，
// else 创建一个 Company object 返回
Company company = companyOptional.orElse(new Company());

// or you can throw an exception
Company company = companyOptional.orElseThrow(IllegalStateException::new);
```

## Reject certain values using the filter method

```
Optional<Company> opt = Optional.empty();
opt.filter(company -> "Finance".equals(company.getName()))
    .ifPresent(() -> System.out.println("Finance is present"));
```

