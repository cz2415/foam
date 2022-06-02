# distinct_by_key

根据指定属性去重

```java
    List<NucleicInfo> collect = unionList
            .stream()
            .filter(distinctByKey(NucleicInfo::getTestTime))
            .collect(Collectors.toList());

    /**
     * 根据指定 key 去重
     *
     * @param keyExtractor 获取 key 方法
     * @param <T>          类型
     * @return 去重结果
     */
    private static <T> Predicate<T> distinctByKey(Function<? super T, ?> keyExtractor) {
        Set<Object> seen = ConcurrentHashMap.newKeySet();
        return t -> keyExtractor.apply(t) != null && seen.add(keyExtractor.apply(t).toString());
    }
```