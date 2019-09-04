# Функции верификации

| 1 | Название | Описание | Сложность |
| :--- | :--- | :--- | :--- |
| 1 | [checkMerkleProof(ByteVector, ByteVector, ByteVector): Boolean](#check-merkle-proof) | Проверяет, является ли дерево хешей частью [дерева Меркла](https://ru.wikipedia.org/wiki/Дерево_хешей).<br>Для хеширования дерева Меркла используется [Blake2b256](https://en.wikipedia.org/wiki/BLAKE_%28hash_function%29). | 30 |
| 2 | [rsaVerify(digestAlgorithmType, ByteVector, ByteVector, ByteVector): Boolean](#rsa-verify) | Проверяет подпись [RSA](https://ru.wikipedia.org/wiki/RSA) | 300 |
| 3 | [sigVerify(ByteVector, ByteVector, ByteVector): Boolean](#sig-verify) | Проверяет подпись [Curve25519](https://en.wikipedia.org/wiki/Curve25519) | 100 |


## checkMerkleProof(ByteVector, ByteVector, ByteVector): Boolean<a id="check-merkle-proof"></a>

Проверяет, является ли дерево хешей частью [дерева Меркла](https://ru.wikipedia.org/wiki/Дерево_хешей).

Для хеширования [дерева Меркла](https://ru.wikipedia.org/wiki/Дерево_хешей) используется [Blake2b256](https://en.wikipedia.org/wiki/BLAKE_%28hash_function%29).

``` ride
checkMerkleProof(merkleRoot: ByteVector, merkleProof: ByteVector, valueBytes: ByteVector): Boolean
```

### Параметры

#### merkleRoot: ByteVector

Корневой хеш дерева Меркла.

#### merkleProof: ByteVector

Массив байтов дерева Меркла, подтверждающего транзакцию.

#### valueBytes: ByteVector

Дерево хешей.

## rsaVerify(digestAlgorithmType, ByteVector, ByteVector, ByteVector): Boolean<a id="rsa-verify"></a>

Проверяет подпись [RSA](https://ru.wikipedia.org/wiki/RSA).

``` ride
rsaVerify(digest: digestAlgorithmType, message: ByteVector, sig: ByteVector, pub: ByteVector): Boolean
```

### Параметры

#### `digest`: digestAlgorithmType

Идентификатор реализации алгоритма [RSA](https://ru.wikipedia.org/wiki/RSA).

digestAlgorithmType представляет собой [объединение](/ride/data-types/union.md), которое включает в себя следующие типы данных:

* MD5
* SHA1
* SHA224
* SHA256
* SHA384
* SHA512
* SHA3224
* SHA3256
* SHA3384
* SHA3512

Объект каждого из перечисленных типов данных является идентификатором реализации алгоритма RSA.

#### `message`: ByteVector

Сообщение.

#### `sig`: ByteVectore

Подпись.

#### `pub`: ByteVectore

Открытый ключ.

## sigVerify(ByteVector, ByteVector, ByteVector): Boolean<a id="sig-verify"></a>

Проверяет подпись [Curve25519](https://en.wikipedia.org/wiki/Curve25519).

``` ride
sigVerify(message: ByteVector, sig: ByteVector, pub: ByteVector): Boolean
```

### Параметры

#### `message`: ByteVector

Сообщение.

#### `sig`: ByteVectore

Подпись.

#### `pub`: ByteVectore

Открытый ключ [аккаунта](/blockchain/account.md).
