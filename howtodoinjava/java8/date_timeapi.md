# Date/Time api changes
* JSR-310 提供了新的 Date/Time api

## Dates
* 新的 api 中使用 `LocalDate`, `LocalTime`, `LocalDateTime` 取代原来的 `Date` 类。

1. `LocalDate` 表示日期，没有时间和时区信息
2. `LocalTime` 表示时间, 没有日期和时区信息
3. `LocalDateTime` 表示日期和时间，没有时区信息


如果需要带有时区的日期时间信息，可以用 `OffsetDate`, `OffsetTime`, `OffsetDateTime` 三个类。使用信息可以用 `ZoneId`, 通过 `"+5:30"` 或 `"Europe/Paris"` 表示
```
LocalDate localDate = LocalDate.now();
LocalTime localTime = LocalTime.of(12, 20);
LocalDateTime localDateTime = LocalDateTime.now();
OffsetDateTime offsetDateTime = OffsetDateTime.now();
ZonedDateTime zonedDateTime = ZonedDateTime.now(ZoneId.of("Europe/Paris"));
```

## Timestamp and Duration
* 表示特定的时间点可以用 `Instant`， 它精确到 `nanoseconds`, `Instant` 可以进行 `+`, `-`, 比较操作

```
Instant instant = Instant.now();
Instant ins1 = instant.plus(Duration.ofMillis(5000));
Instant ins2 = instant.minus(Duration.ofMillis(5000));
Instant ins3 = instant.minusSecond(10);
```
