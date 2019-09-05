# Встроенные переменные

**Встроенная переменная** — переменная [контекста скрипта](/ride/script/script-context.md).

## Список встроенных переменных
<table style="width:100%">
  <tr>
    <th>№</th>
    <th>Имя</th>
    <th>Описание</th>
  </tr>
  <tr>
    <td>1</td>
    <td>Buy</td>
    <td>Тип <a href="/blockchain/order.md">ордера</a></td>
  </tr>
  <tr>
    <td>2</td>
    <td>lastBlock</td>
    <td>Высота [блокчейна](/blockchain/blockchain/blockchain-height.md) в момент выполненияскрипта</td>
  </tr>
  <tr>
    <td>3</td>
    <td>height</td>
    <td>Информация о последнем [блоке](/blockchain/block.md) блокчейна в момент выполнения скрипта</td>
  </tr>
  <tr>
    <td>4</td>
    <td>nil</td>
    <td>Переменная, которая содержит пустой [список](/ride/data-types/list.md).<br>Используется для создания списков. Например, вместо:<br>```let b = [5,6]```<br> можно написать:<br>```let a = 5::6::nil```</td>
  </tr>
  <tr>
    <td>5</td>
    <td><ol><li>NOALG</li><li>MD5</li><li>SHA1</li><li>SHA224</li><li>SHA256</li><li>SHA384</li><li>SHA512</li><li>SHA3224</li> <li>SHA3256</li><li>SHA3384</li><li>SHA3512</li></ol></td>
    <td>Переменные, которые передаются в качестве первого параметра в  функцию [rsaVerify](/ride/functions/built-in-functions/verification-functions.md).<br> Все переменные, кроме NOALG, обозначают алгоритмы хеширования, которые применяются к данным. Если передать NOALG, то данные хешироваться не будут</td>
  </tr>
  <tr>
    <td>6</td>
    <td>Sell</td>
    <td>Тип [ордера](/blockchain/order.md)</td>
  </tr>
  <tr>
    <td>7</td>
    <td>this</td>
    <td>[Адрес](/blockchain/address.md) отправителя транзакции или информация о [токене](/blockchain/token.md)</td>
  </tr>
  <tr>
    <td>8</td>
    <td>tx</td>
    <td>[Транзакция](/blockchain/transaction.md) или [ордер](/blockchain/order.md)</td>
  </tr>
  <tr>
    <td>9</td>
    <td>unit</td>
    <td>Переменная, которая содержит объект типа [Unit](ru/ride/data-types/unit.md). Переменная используется программистом для получения объекта типа Unit. <br>**Пример 1**<br> Функция deposit переводит 5 [WAVELET](/blockchain/token/wavelet.md) на аккаунт, который [вызвал](/ride/functions/callable-function.md) эту функцию.<br>
    <pre>
    <code class=“lang-ride”>
    {-# STDLIB_VERSION 3 #-}
    {-# CONTENT_TYPE DAPP #-}
    {-# SCRIPT_TYPE ACCOUNT #-}

    @Callable(inv)
    func deposit() = {
      TransferSet([
        ScriptTransfer(inv.caller, 5, unit) # Перевести 5 WAVELET на аккаунт inv.caller. Вместо ID токена указан unit
        ])
    }
    </code>
    </pre>
    У WAVES нет [ID токена](/blockchain/token/token-id.md); вместо ID передается unit.<br>**Пример 2**<br>Функция [assetInfo](/ride/functions/built-in-functions/blockchain-functions.md) запрашивает информацию о токене по его ID. Далее функция isDefined проверяет, что токен с таким ID существует на блокчейне.
    <pre>
    <code class=“lang-ride”>
    {-# STDLIB_VERSION 3 #-}
{-# CONTENT_TYPE EXPRESSION #-}
{-# SCRIPT_TYPE ACCOUNT #-}

let asset = assetInfo(base58'8LQW8f7P5d5PZM7GtZEBgaqRPGSzS3DfPuiXrURJ4AJS')

token.isDefined()
    </code>
    </pre>
    Вместо вызова функции isDefined можно использовать равенство с unit.
    <pre>
    <code class=“lang-ride”>
    asset != unit
    # Выражение asset != unit эквивалентно выражению token.isDefined(
    </code>
    </pre>
  </td>
  </tr>
</table>
