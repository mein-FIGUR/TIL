# String[] 을 ArrayList로 변환

- `Arrays.asList` 활용
```java
import java.util.ArrayList;
import java.util.Arrays;

public class testCode {
    public static void main(String[] args){
        String[] words = new String[] {"apple", "banana", "watermelon"};
        ArrayList<String> wordsArrayList = new ArrayList<>(Arrays.asList(words));

        System.out.println(Arrays.toString(words));
        System.out.println(wordsArrayList);
    }
}

```