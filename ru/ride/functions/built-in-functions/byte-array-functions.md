# Функции массива байтов

| # | Название | Описание | Сложность |
| :--- | :--- | :--- | :--- |
| 1 | [drop(ByteVector, Int): ByteVector](#drop) | Удаляет первые N байтов из массива байтов | 1 |
| 2 | [dropRight(ByteVector, Int): ByteVector](#dropright) | Удаляет последние N байтов из массива байтов | 19 |
| 3 | [size(ByteVector): Int](#size) | Возвращает размер массива байтов | 1 |
| 4 | [take(ByteVector, Int): ByteVector](#take) | Возвращает первые N байтов массива байтов | 1 |
| 5 | [takeRight(ByteVector, Int): ByteVector](#takeright) | Возвращает последние N байтов массива байтов | 19 |

## drop(ByteVector, Int): ByteVector <a id="drop"></a>

Удаляет первые N байтов из массива байтов.

``` ride
drop(xs: ByteVector, number: Int): ByteVector
```

### Параметры

#### `xs`: ByteVector

Массив байтов.

#### `number`: Int

Количество байтов с начала массива байтов.

## dropRight(ByteVector, Int): ByteVector <a id="dropright"></a>

Удаляет последние N байтов из массива байтов.

``` ride
dropRight(xs: ByteVector, number: Int): ByteVector
```

### Параметры

#### `xs`: ByteVector

Массив байтов.

#### `number`: Int

Количество последних байтов.

## size(ByteVector): Int <a id="size"></a>

Возвращает размер массива байтов.

``` ride
size(byteVector: ByteVector): Int
```

### Параметры

#### `byteVector`: ByteVector

Массив байтов.

## take(ByteVector, Int): ByteVector <a id="take"></a>

Возвращает первые N байтов массива байтов

``` ride
take(xs: ByteVector, number: Int): ByteVector
```

### Параметры

#### `xs`: ByteVector

Массив байтов.

#### `number`: Int

Количество первых байтов.

## takeRight(ByteVector, Int): ByteVector <a id="takeright"></a>

Возвращает последние N байтов массива байтов

``` ride
takeRight(xs: ByteVector, number: Int): ByteVector
```

### Параметры

#### `xs`: ByteVector

Массив байтов.

#### `number`: Int

Количество последних байтов.
