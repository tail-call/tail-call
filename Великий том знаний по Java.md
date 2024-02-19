# Знания о джаве великие

## Примитивные типы

| Data Type | Size (in bits) | Range                                   |
|-----------|----------------|-----------------------------------------|
| byte      | 8              | -128 to 127                             |
| short     | 16             | -32,768 to 32,767                       |
| int       | 32             | -2^31 to 2^31-1                         |
| long      | 64             | -2^63 to 2^63-1                         |
| float     | 32             | approximately ±3.40282347E+38F          |
| double    | 64             | approximately ±1.7976931348623157E+308   |
| boolean   | -              | true or false                           |
| char      | 16             | any Unicode character                   |


## Что есть в джаве?

В джаве есть ассерты.

```java
public class Test {
    public static void main(String[] args) {
        int result = sum(1, 2);
        assert result == 3 : "Должно быть 3";
    }

    public static int sum(int a, int b) {
        return a + b;
    }
}
```

Также в ней есть трансиенты.

```java
import java.io.Serializable;

public class User implements Serializable {
    private String name;
    private transient String password; // Пароль не будет сериализован
}
```

И синкронайзды.

```java
public class Counter {
    private int count = 0; // Переменная счетчика

    // Увеличиваем счетчик на 1 в потокобезопасном режиме
    public synchronized void increment() {
        count++;
    }

    // Возвращает текущее значение счетчика в потокобезопасном режиме
    public synchronized int getCount() {
        return count;
    }
}
```

Также там есть модификатор `strictp`, гарантирующий, что все вычисления с плавающей точкой (включая те, что происходят внутри метода или в выражениях в классе, если `strictfp` применяется к классу) будут строго следовать IEEE 754 стандарту. 

```java
public strictfp class MyCalculations {
    public double sum(double a, double b) {
        return a + b; // Вычисления здесь будут строго соответствовать IEEE 754
    }
}
```

Записи есть там.

```java
public record Person (String name, String address) {}
```

Вот так можно создать список:

```java
List<String> words = Arrays.asList("Welcome", "to", "the", "world", "of", "pain");
```
