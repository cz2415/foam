# sort_by_pinyin

* 根据拼音排序

```java
public class sortByPinyin {
    public static void main(String[] args) {
          String[] arr = { "刘刘", "李飞", "王五", "老三", "贝贝", "啊三" };
          Collator cmp = Collator.getInstance(java.util.Locale.CHINA);
          Arrays.sort(arr, cmp);
          List<String> list = Arrays.asList(arr);
          System.out.println(list);
	}
}
```