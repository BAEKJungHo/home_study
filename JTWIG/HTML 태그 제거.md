## HTML 태그 제거 

### 자바 코드

```java
import static com.lyncode.jtwig.functions.util.HtmlUtils.stripTags;

public class StripTagsExample {
    public static void main(String... args) {
        String result = stripTags("<!-- <a href='test'></a>--><a>Test</a>", "");
        // Produced result: Test
    }
}
```

### Dependency 추가

```xml
    <!-- lyncode -->
    <dependency>
        <groupId>com.lyncode</groupId>
        <artifactId>jtwig-functions</artifactId>
        <version>2.0.1</version>
    </dependency>
```

## Reference 

> https://blog.whitelife.co.kr/251