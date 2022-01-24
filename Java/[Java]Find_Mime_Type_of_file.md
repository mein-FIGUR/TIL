# 파일의 Mime Type을 알아내는 방법

> 아래와 같은 방법을 통해 file의 mime type을 알 수 있다.
> 

### probeContentType

- `Files.probeContentType(path)`
    - **OS에 따라 작동하지 않을 수 있음**을 주의해야 한다.

```java
class ProbeTest {
    @Test
    public void whenUsingJava7_thenSuccess() {
        Path path = new File("product.png").toPath();
        String mimeType = Files.probeContentType(path);

        assertEquals(mimeType, "image/png");
    }
}
```

### URLConnetion

- `getContentType()`
    - **속도가 느리다**는 단점이 있다.

```java
class UrlConnectionTest {
    @Test
    public void whenUsingGetContentType_thenSuccess() {
        File file = new File("product.png");
        URLConnection connection = file.toURL().openConnection();
        String mimeType = connection.getContentType();

        assertEquals(mimeType, "image/png");
    }
}
```

- `guessContentTypeFromName()`
    - 내부의 FileNameMap을 통해 type을 알아내는 방식

```java
class UrlConnectionTest2{
    @Test
    public void whenUsingGuessContentTypeFromName_thenSuccess(){
        File file = new File("product.png");
        String mimeType = URLConnection.guessContentTypeFromName(file.getName());

        assertEquals(mimeType, "image/png");
    }

```

- `getFileNameMap()`
    - `URLConnection`을 활용해서 Mime Type을 찾는 방식 중 빠른 방식

```java
class UrlConnectionTest2{
    @Test
    public void whenUsingGetFileNameMap_thenSuccess(){
        File file = new File("product.png");
        FileNameMap fileNameMap = URLConnection.getFileNameMap();
        String mimeType = fileNameMap.getContentTypeFor(file.getName());

        assertEquals(mimeType, "image/png");
    }
}
```

- 내장된 테이블은 `JRE_HOME/lib`의 `content-types.properties`를 활용하는데, type이 다소 제한된다는 점이 있다.
- `content.types.user.table property`를 활용하여 사용자 테이블을 설정할 수 있다.
    
    ```java
    System.setProperty("content.types.user.table","<path-to-file>");
    ```
    

### MimeTypesFileTypeMap

- Java 6에서 온 클래스로, JDK 1.6에서 편리하다.
- `mime.types` 파일을 찾아 타입을 알아내는 방식으로, 파일을 찾을 수 없으면 `application/octet-stream`을 반환한다.
    - `mime.types` 파일을 찾는 방식은 다음과 같다.

    ![]([Java]Find_Mime_Type_of_file/mime_types_order.png)

    

```java
class UrlConnectionTest2{
    @Test
    public void whenUsingMimeTypesFileTypeMap_thenSuccess() {
        File file = new File("product.png");
        MimetypesFileTypeMap fileTypeMap = new MimetypesFileTypeMap();
        String mimeType = fileTypeMap.getContentType(file.getName());

        assertEquals(mimeType, "image/png");
    }
}
```

### jMieMagic

- build.gradle 에 추가한 이후 활용
    - `net.sf.jmimemagic:jmimemagic`

```java
class JMimeMagicTest{
    @Test
    public void whenUsingJmimeMagic_thenSuccess() {
        File file = new File("product.png");
        Magic magic = new Magic();
        MagicMatch match = magic.getMagicMatch(file, false);

        assertEquals(match.getMimeType(), "image/png");
    }
}
```

### Apache Tika

- build.gradle에 추가한 이후 활용
    - `org.apache.tika:tika-core`
    - Mime type을 찾는 메서드만 활용하기 위해, `tika-core` 적용

```java
class TikaTest{
    @Test
    public void whenUsingTika_thenSuccess() {
        File file = new File("product.png");
        Tika tika = new Tika();
        String mimeType = tika.detect(file);

        assertEquals(mimeType, "image/png");
    }
}
```

### REFERENCE

- [https://www.baeldung.com/java-file-mime-type](https://www.baeldung.com/java-file-mime-type)