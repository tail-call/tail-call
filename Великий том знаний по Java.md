# Знания о джаве великие

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
