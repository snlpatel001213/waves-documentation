# Временная метка блока

**Временна́я метка блока** — время [генерации блока](/blockchain/block/block-generation.md).

Время указывается в миллисекундах, которые прошли с начала [эпохи Unix](https://ru.wikipedia.org/wiki/Unix-%D0%B2%D1%80%D0%B5%D0%BC%D1%8F).

Когда [узел](/blockchain/node.md) получает новый блок из [сети блокчейна](/blockchain/blockchain-network.md), он проверяет, что значение временной метки блока не опережает время [UTC](https://ru.wikipedia.org/wiki/%D0%92%D1%81%D0%B5%D0%BC%D0%B8%D1%80%D0%BD%D0%BE%D0%B5_%D0%BA%D0%BE%D0%BE%D1%80%D0%B4%D0%B8%D0%BD%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D0%BE%D0%B5_%D0%B2%D1%80%D0%B5%D0%BC%D1%8F) более чем на 100 миллисекунд.

Значение временной метки блока валидируется узлами по формуле из FPoS.
