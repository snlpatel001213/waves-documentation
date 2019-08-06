# Built-in functions

## [Account data storage functions](/ride/built-in-functions/account-data-storage-functions.md)

| # | Name | Description | Complexity |
| :--- | :--- | :--- | :--- |
| 1 | assetBalancе(Address|Alias, ByteVector): Int | Gets account balance by token ID | 100 |
| 2 | getBinary(Address|Alias, String): ByteVector|Unit | Gets an array of bytes by key | 100 |
| 3 | getBinaryValue(Address|Alias, String): ByteVector | Gets an array of bytes by key. Throws an exception if there is no data | 100 |
| 4 | getBoolean(Address|Alias, String): Boolean|Unit | Gets a boolean value by key | 100 |
| 5 | getBooleanValue(Address|Alias, String): Boolean | Gets a boolean value by key. Throws an exception if there is no data | 100 |
| 6 | getInteger(Address|Alias, String): Int|Unit | Gets an integer by key | 100 |
| 7 | getIntegerValue(Address|Alias, String): Int | Gets an integer by key. Throws an exception if there is no data | 100 |
| 8 | getString(Address|Alias, String): String|Unit | Gets a string by key | 100 |
| 9 | getStringValue(Address|Alias, String): String | Gets a string by key. Throws an exception if there is no data | 100 |
| 10 | wavesBalance(Address|Alias): Int | Gets account balance in [WAVES](/blockchain/token/waves.md) | 109 |

## [Blockchain functions](/ride/built-in-functions/blockchain-functions.md)

| # | Name | Description | Complexity |
| :--- | :--- | :--- | :--- |
| 1 | assetInfo(ByteVector): АssetUnit | Gets the information about a [token](/blockchain/token.md) | 100 |
| 2 | blockInfoByHeight(Int): BlockInfo |Unit | Gets the information about a [block](/blockchain/block.md) by the [block height](/blockchain/block/block-height.md) | 100 |
| 3 | transactionHeightById(ByteVector):  Int |Unit | Gets the [block height](/blockchain/block/block-height.md) of a transaction | 100 |
| 4 | transferTransactionById(ByteVector): TransferTransaction |Unit | Gets the data of a [transfer transaction](/blockchain/transaction-type/transfer-transaction.md) | 100 |

## [Byte array functions](/ride/built-in-functions/byte-array-functions.md)

| # | Name | Description | Complexity |
| :--- | :--- | :--- | :--- |
| 1 | drop(ByteVector, Int): ByteVector | Drops the first `n` bytes of an array of bytes | 1 |
| 2 | dropRight(ByteVector, Int): ByteVector | Drops the last `n` bytes of an array of bytes | 19 |
| 3 | size(ByteVector): Int | Returns the size of an array of bytes | 1 |
| 4 | take(ByteVector, Int): ByteVector | Takes the first `n` bytes from an array of bytes | 1 |
| 5 | takeRight(ByteVector, Int): ByteVector | Takes the last `n` bytes from an array of bytes | 19 |

## [Converting functions](/ride/built-in-functions/converting-functions.md)

| # | Name | Description | Complexity |
| :--- | :--- | :--- | :--- |
| 1 | addressFromPublicKey(ByteVector): Address | Converts account public key to [address](/blockchain/address.md) | 82 |
| 2 | parseInt(String): Int|Unit | Converts the string representation of a number to its integer equivalent | 20 |
| 3 | parseIntValue(String): Int | Converts the string representation of a number to its integer equivalent.Raises an exception if the string cannot be parsed | 20 |
| 4 | toBytes(Boolean): ByteVector | Converts a boolean to an array of bytes | 1 |
| 5 | toBytes(Int): ByteVector | Converts an integer to an array of bytes | 1 |
| 6 | toBytes(String): ByteVector | Converts a string to an array of bytes | 1 |
| 7 | toInt(ByteVector): Int | Converts an array of bytes to an integer | 10 |
| 8 | toInt(ByteVector, Int): Int | Converts an array of bytes to an integer starting from a certain index | 10 |
| 9 | toString(Address): String | Converts an [address](/blockchain/address.md) to a string | 10 |
| 10 | toString(Boolean): String | Converts a boolean to a string | 1 |
| 11 | toString(Int): String | Converts an integer to a string | 1 |
| 12 | toUtf8String(ByteVector): String | Converts an array of bytes to a UTF-8 string | 20 |

## Data transaction functions

| # | Name | Description | Complexity |
| :--- | :--- | :--- | :--- |
| 1 | addressFromRecipient(Address|Alias): Address | Gets the corresponding [address](/blockchain/address.md) of the [alias](/blockchain/alias.md) | 100 |
| 2 | getInteger(List[DataEntry], String): Int|Unit | Gets an integer value from a list of data entires by key | 10 |
| 3 | getInteger(List[DataEntry], Int): Int|Unit | Gets an integer value from a list of data entires by index | 30 |
| 4 | getIntegerValue(List[DataEntry], String): Int | Gets an integer value from a list of data entires by key. Throws an exception if there is no data | 10 |
| 5 | getIntegerValue(List[DataEntry], Int): Int | Gets an integer value from a list of data entires by index. Throws an exception if there is no data | 30 |
| 6 | getBoolean(List[DataEntry], String): Boolean|Unit | Gets a boolean value from a list of data entires by key | 10 |
| 7 | getBoolean(List[DataEntry], Int): Boolean|Unit | Gets a boolean value from a list of data entires by index | 30 |
| 8 | getBooleanValue(List[DataEntry], String): Boolean | Gets a boolean value from a list of data entires by key. Throws an exception if there is no data | 10 |
| 9 | getBooleanValue(List[DataEntry], Int): Boolean | Gets a boolean value from a list of data entires by index. Throws an exception if there is no data | 30 |
| 10 | getBinary(List[DataEntry], String): ByteVector|Unit | Gets a binary value from a list of data entires by key | 10 |
| 11 | getBinary(List[DataEntry], Int): ByteVector|Unit | Gets a binary value from a list of data entires by index | 30 |
| 12 | getBinaryValue(ListDataEntry, String): ByteVector | Gets a binary value from a list of data entires by key. Throws an exception if there is no data | 10 |
| 13 | getBinaryValue(List[DataEntry], Int): ByteVector | Gets a binary value from a list of data entires by index. Throws an exception if there is no data | 30 |
| 14 | getString(List[DataEntry] String): String|Unit | Gets a string value from a list of data entires by key | 10 |
| 15 | getString(List[DataEntry], Int): String|Unit | Gets a string value from a list of data entires by index | 30 |
| 16 | getStringValue(List[DataEntry], String): String | Gets a string value from a list of data entires by key. Throws an exception if there is no data | 10 |
| 17 | getStringValue(List[DataEntry], Int): String | Gets a string value from a list of data entires by index. Throws an exception if there is no data | 30 |

## Decoding functions

| # | Name | Description | Complexity |
| :--- | :--- | :--- | :--- |
| 1 | addressFromString(String): Address|Unit | Decodes address from [Base58](https://en.wikipedia.org/wiki/Base58) string | 124 |
| 2 | addressFromStringValue(String): Address | Decodes address from [Base58](https://en.wikipedia.org/wiki/Base58) string.Raises an exception if the address cannot be decoded | 124 |
| 3 | fromBase16String(String): ByteVector | Decodes [Base16](https://en.wikipedia.org/wiki/Hexadecimal) string to an array of bytes | 10 |
| 4 | fromBase58String(String): ByteVector | Decodes [Base58](https://en.wikipedia.org/wiki/Base58) string to an array of bytes | 10 |
| 5 | fromBase64String(String): ByteVector | Decodes [Base64](https://en.wikipedia.org/wiki/Base64) string to an array of bytes | 10 |

## [Encoding functions](/ride/built-in-functions/encoding-and-decoding-functions.md)

| # | Name | Description | Complexity |
| :--- | :--- | :--- | :--- |
| 1 | toBase16String(ByteVector): String | Encodes array of bytes to [Base16](https://en.wikipedia.org/wiki/Hexadecimal) string | 10 |
| 2 | toBase58String(ByteVector): String | Encodes array of bytes to [Base58](https://en.wikipedia.org/wiki/Base58) string | 10 |
| 3 | toBase64String(ByteVector): String | Encodes array of bytes to [Base64](https://en.wikipedia.org/wiki/Base64) string | 10 |

## [Exception functions](/ride/built-in-functions/exception-functions.md)

| # | Name | Description | Complexity |
| :--- | :--- | :--- | :--- |
| 1 | throw() | Raises an exception | 1 |
| 2 | throw(String) | Raises an exception with a message | 1 |

## Hashing functions

| # | Name | Description | Complexity |
| :--- | :--- | :--- | :--- |
| 1 | blake2b256(ByteVector): ByteVector | Hashes an array of bytes using [BLAKE-256](https://en.wikipedia.org/wiki/BLAKE_%28hash_function%29) | 10 |
| 2 | keccak256(ByteVector): ByteVector | Hashes an array of bytes using [SHA-3-256](https://en.wikipedia.org/wiki/SHA-3) | 10 |
| 3 | sha256(ByteVector): ByteVector | Hashes an array of bytes using [SHA-256](https://en.wikipedia.org/wiki/SHA-2) | 10 |

## [List functions](/ride/built-in-functions/list-functions.md)

| # | Name | Description | Complexity |
| :--- | :--- | :--- | :--- |
| 1 | getElement(List[T], Int): T | Gets the element by index | 2 |
| 2 | cons(T, List[T]): List[T] | Inserts the element at the beginning of the list | 2 |
| 3 | size(List[T]): Int | Returns the size of the list | 2 |

## [Math functions](/ride/built-in-functions/math-functions.md)

| # | Name | Description | Complexity |
| :--- | :--- | :--- | :--- |
| 1 | fraction(Int, Int, Int): Int | Multiplies and divides an integer to avoid the integer overflow | 1 |
| 2 | log(Int, Int, Int, Int, Int, Union): Int | Calculates logarithm of the number | 100 |
| 3 | pow(Int, Int, Int, Int, Int, Union): Int | Raises the number to a power | 100 |

## Optional value functions

| # | Name | Description | Complexity |
| :--- | :--- | :--- | :--- |
| 1 | extract(T|Unit): T | Gets a data type from an union | 13 |
| 2 | isDefined(List[T]|Unit): Boolean | Checks if a value is not an union | 1 |
| 3 | value(T|Unit): T | Gets a data type from an union | 13 |
| 4 | valueOrErrorMessage(T|Unit, String): T | Gets a data type from an union. Throws an exception if there is no data | 13 |

## [String functions](/ride/built-in-functions/string-functions.md)

| # | Name | Description | Complexity |
| :--- | :--- | :--- | :--- |
| 1 | drop(String, Int): String | Drops the first `n` characters of a string | 1 |
| 2 | dropRight(String, Int): String | Drops the last `n` characters of a string | 19 |
| 3 | indexOf(String, String): Int|Unit | Returns the index of the first occurrence of a substring | 20 |
| 4 | indexOf(String, String, Int): Int|Unit | Returns the index of the first occurrence of a substring after a certain index | 20 |
| 5 | size(String): Int | Returns the size of a string | 1 |
| 6 | split(String, String): List[String] | Splits a string delimited by a separator into a list of substrings. | 100 |
| 7 | take(String, Int): String | Takes the first `n` characters from a string | 1 |
| 8 | takeRight(String, Int): String | Takes the last `n` characters from a string | 19 |

## [Verification functions](/ride/built-in-functions/verification-functions.md)

| # | Name | Description | Complexity |
| :--- | :--- | :--- | :--- |
| 1 | checkMerkleProof(ByteVector, ByteVector, ByteVector): Boolean | Verifies if a tree of hashes is part of the [Merkle tree](https://en.wikipedia.org/wiki/Merkle_tree).<br> [Blake2b256](https://en.wikipedia.org/wiki/BLAKE_%28hash_function%29) is used to hash the [Merkle tree](https://en.wikipedia.org/wiki/Merkle_tree). | 30 |
| 2 | rsaVerify(digestAlgorithmType, ByteVector, ByteVector, ByteVector): Boolean | Verifies a [RSA](https://en.wikipedia.org/wiki/RSA_%28cryptosystem%29) signature | 300 |
| 3 | sigVerify(ByteVector, ByteVector, ByteVector): Boolean | Verifies a [Curve25519](https://en.wikipedia.org/wiki/Curve25519) signature | 100 |
