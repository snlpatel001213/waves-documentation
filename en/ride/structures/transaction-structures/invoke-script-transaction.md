# InvokeScriptTransaction

<table>
<tr>
  <th>Name</th>
  <th>Data type</th>
</tr>
<tr><td>dappAddress</td><td>
  <a href="#Address">Address</a>
</td></tr><tr><td>payment</td><td>
  OPTION[<a href="#AttachedPayment">AttachedPayment</a>]
</td></tr><tr><td>feeAssetId</td><td>
  OPTION[<a href="#ByteVector">ByteVector</a>]
</td></tr><tr><td>function</td><td>
  <a href="#String">String</a>
</td></tr><tr><td>args</td><td>
  LIST[<a href="#UNION(Boolean|ByteVector|Int|String)">UNION(Boolean|ByteVector|Int|String)</a>]
</td></tr><tr><td>id</td><td>
  <a href="#ByteVector">ByteVector</a>
</td></tr><tr><td>fee</td><td>
  <a href="#Int">Int</a>
</td></tr><tr><td>timestamp</td><td>
  <a href="#Int">Int</a>
</td></tr><tr><td>version</td><td>
  <a href="#Int">Int</a>
</td></tr><tr><td>sender</td><td>
  <a href="#Address">Address</a>
</td></tr><tr><td>senderPublicKey</td><td>
  <a href="#ByteVector">ByteVector</a>
</td></tr><tr><td>bodyBytes</td><td>
  <a href="#ByteVector">ByteVector</a>
</td></tr><tr><td>proofs</td><td>
  LIST[<a href="#ByteVector">ByteVector</a>]
</td></tr></table>
</td></tr>
