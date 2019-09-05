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
    <td>Тип <a href="https://docs.wavesplatform.com/ru/blockchain/order.html">ордера</a></td>
  </tr>
  <tr>
    <td>2</td>
    <td>lastBlock</td>
    <td><a href="https://docs.wavesplatform.com/ru/blockchain/blockchain/blockchain-height.html">Высота блокчейна</a> в момент выполненияскрипта</td>
  </tr>
  <tr>
    <td>3</td>
    <td>height</td>
    <td>Информация о последнем <a href="https://docs.wavesplatform.com/ru/blockchain/block.html">блоке</a> блокчейна в момент выполнения скрипта</td>
  </tr>
  <tr>
    <td>4</td>
    <td>nil</td>
    <td>Переменная, которая содержит пустой <a href="https://docs.wavesplatform.com/ru/ride/data-types/list.html">список.</a><br>Используется для создания списков. Например, вместо:<br>
<pre>
<code class=“lang-ride”>
    let b = [5,6]
</code>
</pre>
    можно написать:
<pre>
<code class=“lang-ride”>
    let a = 5::6::nil
</code>
</pre>
    </td>
  </tr>
  <tr>
    <td>5</td>
    <td>
      <ol>
        <li>NOALG</li><li>MD5</li>
        <li>SHA1</li><li>SHA224</li>
        <li>SHA256</li><li>SHA384</li>
        <li>SHA512</li><li>SHA3224</li>
        <li>SHA3256</li><li>SHA3384</li>
        <li>SHA3512</li></ol>
    </td>
    <td>Переменные, которые передаются в качестве первого параметра в  функцию <a href="https://docs.wavesplatform.com/ru/ride/functions/built-in-functions/verification-functions.html">rsaVerify</a>.<br> Все переменные, кроме NOALG, обозначают алгоритмы хеширования, которые применяются к данным. Если передать NOALG, то данные хешироваться не будут</td>
  </tr>
  <tr>
    <td>6</td>
    <td>Sell</td>
    <td>Тип <a href="https://docs.wavesplatform.com/ru/blockchain/order.html">ордера</a></td>
  </tr>
  <tr>
    <td>7</td>
    <td>this</td>
    <td><a href="https://docs.wavesplatform.com/ru/blockchain/address.html">Адрес</a> отправителя транзакции или информация о <a href="https://docs.wavesplatform.com/ru/blockchain/token.html">токене</a></td>
  </tr>
  <tr>
    <td>8</td>
    <td>tx</td>
    <td><a href="https://docs.wavesplatform.com/ru/blockchain/transaction.html">Транзакция</a> или <a href="https://docs.wavesplatform.com/ru/blockchain/order.html">ордера</a></td>
  </tr>
  <tr>
    <td>9</td>
    <td>unit</td>
    <td>Переменная, которая содержит объект типа <a href="https://docs.wavesplatform.com/ru/ride/data-types/unit.html">Unit</a>. Переменная используется программистом для получения объекта типа Unit. <br><b>Пример 1</b><br> Функция deposit переводит 5 <a href="https://docs.wavesplatform.com/ru/blockchain/token/wavelet.html">WAVELET</a> на аккаунт, который <a href="https://docs.wavesplatform.com/ru/ride/functions/callable-function.html">вызвал</a> эту функцию.
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
У WAVES нет <a href="/blockchain/token/token-id.md">ID токена</a>; вместо ID передается unit.<br><b>Пример 2</b><br>Функция <a href="/ride/functions/built-in-functions/blockchain-functions.md">assetInfo</a> запрашивает информацию о токене по его ID. Далее функция isDefined проверяет, что токен с таким ID существует на блокчейне.
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
