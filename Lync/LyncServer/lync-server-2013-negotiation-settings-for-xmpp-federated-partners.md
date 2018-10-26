---
title: 'Lync Server 2013: XMPP フェデレーション パートナーのネゴシエーション設定'
TOCTitle: XMPP フェデレーション パートナーのネゴシエーション設定
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ552456(v=OCS.15)
ms:contentKeyID: 49115248
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の XMPP フェデレーション パートナーのネゴシエーション設定

 

_**トピックの最終更新日:** 2015-03-09_

XMPP パートナーの構成におけるネゴシエーションの種類の設定では、幅広い組み合わせが可能です。こうした組み合わせのすべてが有効というわけではありません。このトピックの表で、有効な設定と無効な設定を示します。よく使用される構成は 1 番目の表に記載し、2 番目の表には可能な組み合わせをすべて記載しています。 *簡易認証およびセキュリティ層* (SASL) を使用するには、 *トランスポート層セキュリティ* (TLS) も **使用可能である必要がある**ことに注意してください。SASL は暗号化されていない (可読) 形式で送信されます。ほかの方法 (TLS など) で保護しないまま送信しないでください。

### よく使用される XMPP フェデレーションのネゴシエーション方式

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>トランスポート層セキュリティ (TLS)</th>
<th>簡易認証およびセキュリティ層 (SASL)</th>
<th>ダイヤルバック認証</th>
<th>期待される認証方式</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>必須</p></td>
<td><p>必須</p></td>
<td><p>False</p></td>
<td><p>SASL over TLS</p></td>
<td><p>SASL メッセージ ストリームをセキュアにするために TLS と SASL が必要です。ダイヤルバックは利用できません。XMPP フェデレーション パートナーが TLS を必須またはオプションに設定していない場合の代替手段には使用できません。</p></td>
</tr>
<tr class="even">
<td><p>必須</p></td>
<td><p>省略可能</p></td>
<td><p>True</p></td>
<td><p>SASL over TLS、TLS ダイヤルバック、TCP ダイヤルバック</p></td>
<td><p>TLS を必須にすると、XMPP フェデレーション パートナーが SASL をオプションまたは必須に設定していた場合は SASL が使用されます。SASL が利用できない場合は、ダイヤルバック over TLS が使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>省略可能</p></td>
<td><p>省略可能</p></td>
<td><p>True</p></td>
<td><p>SASL over TLS、TLS ダイヤルバック、TCP ダイヤルバック</p></td>
<td><p>きわめて柔軟なネゴシエーション方式が用意されているものの、これらの設定は XMPP フェデレーション パートナーの設定に依存します。パートナーが TLS をオプションまたは必須にしているのに SASL がサポートされていない場合は、TLS ダイヤルバックが利用できます。パートナーが TLS と SASL をオプションまたは必須に設定している場合は、最適な選択肢である TLS over SASL が使用されます。</p></td>
</tr>
<tr class="even">
<td><p>サポート対象外</p></td>
<td><p>サポート対象外</p></td>
<td><p>True</p></td>
<td><p>TCP ダイヤルバック</p></td>
<td><p>多くの場合、使用できるソリューションは TCP ダイヤルバックのみです。ほかのオプションに比べると好ましくありませんが、ある程度の信頼は提供されます。</p></td>
</tr>
</tbody>
</table>


### XMPP フェデレーション ネゴシエーション方式のマトリックス - すべて

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>トランスポート層セキュリティ (TLS)</th>
<th>簡易認証およびセキュリティ層 (SASL)</th>
<th>ダイヤルバック認証</th>
<th>期待される認証方式</th>
<th>無効な構成に関するメモ、警告、またはエラー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>必須</p></td>
<td><p>必須</p></td>
<td><p>True</p></td>
<td><p>SASL over TLS</p></td>
<td><div>

> [!WARNING]
> SASL と TLS の両方が必須の場合、ダイヤルバックは機能しません。


</div></td>
</tr>
<tr class="even">
<td><p>必須</p></td>
<td><p>必須</p></td>
<td><p>False</p></td>
<td><p>SASL over TLS</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>省略可能</p></td>
<td><p>必須</p></td>
<td><p>True</p></td>
<td><p>SASL over TLS、TLS ダイヤルバック、TCP ダイヤルバック</p></td>
<td><div>

> [!WARNING]
> SASL には TLS が必須です。TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。


</div></td>
</tr>
<tr class="even">
<td><p>省略可能</p></td>
<td><p>必須</p></td>
<td><p>False</p></td>
<td><p>SASL over TLS</p></td>
<td><div>

> [!WARNING]
> SASL には TLS が必須です。TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。


</div></td>
</tr>
<tr class="odd">
<td><p>サポート対象外</p></td>
<td><p>必須</p></td>
<td><p>True</p></td>
<td><p>TCP ダイヤルバック</p></td>
<td><div>

> [!WARNING]
> SASL には TLS が必須です。TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。


</div></td>
</tr>
<tr class="even">
<td><p>サポート対象外</p></td>
<td><p>必須</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]
> 無効な構成


</div></td>
<td><div>

> [!WARNING]
> SASL には TLS が必須ですが TLS は利用できないため、SASL/TLS は成功しません。TCP ダイヤルバックは False に設定され、使用されません。


</div></td>
</tr>
<tr class="odd">
<td><p>必須</p></td>
<td><p>省略可能</p></td>
<td><p>True</p></td>
<td><p>SASL over TLS、TLS ダイヤルバック</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>必須</p></td>
<td><p>省略可能</p></td>
<td><p>False</p></td>
<td><p>SASL over TLS</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>省略可能</p></td>
<td><p>省略可能</p></td>
<td><p>True</p></td>
<td><p>SASL over TLS、TLS ダイヤルバック、TCP ダイヤルバック</p></td>
<td><div>

> [!WARNING]
> SASL には TLS が必須です。TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。


</div></td>
</tr>
<tr class="even">
<td><p>省略可能</p></td>
<td><p>省略可能</p></td>
<td><p>False</p></td>
<td><p>SASL over TLS</p></td>
<td><div>

> [!WARNING]
> SASL には TLS が必須です。TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。


</div></td>
</tr>
<tr class="odd">
<td><p>サポート対象外</p></td>
<td><p>省略可能</p></td>
<td><p>True</p></td>
<td><p>TCP ダイヤルバック</p></td>
<td><div>

> [!WARNING]
> SASL には TLS が必須です。TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。


</div></td>
</tr>
<tr class="even">
<td><p>サポート対象外</p></td>
<td><p>省略可能</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]
> 無効な構成


</div></td>
<td><div>

> [!WARNING]
> SASL には TLS が必須です。TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。


</div></td>
</tr>
<tr class="odd">
<td><p>必須</p></td>
<td><p>サポート対象外</p></td>
<td><p>True</p></td>
<td><p>TLS ダイヤルバック</p></td>
<td><p>TLS ダイヤルバックを許可する構成です。</p></td>
</tr>
<tr class="even">
<td><p>必須</p></td>
<td><p>サポート対象外</p></td>
<td><p>False</p></td>
<td><p>無効な構成</p></td>
<td><div>

> [!WARNING]
> SASL またはダイヤルバックを有効化する必要があります。


</div></td>
</tr>
<tr class="odd">
<td><p>省略可能</p></td>
<td><p>サポート対象外</p></td>
<td><p>True</p></td>
<td><p>TLS ダイヤルバック、TCP ダイヤルバック</p></td>
<td><p>もう一方のエンドポイントが選択したネゴシエーションに基づいて、TCP または TLS ダイヤルバックを受け入れます。</p></td>
</tr>
<tr class="even">
<td><p>省略可能</p></td>
<td><p>サポート対象外</p></td>
<td><p>False</p></td>
<td><p>無効な構成</p></td>
<td><div>

> [!WARNING]
> SASL またはダイヤルバックを有効化する必要があります。


</div></td>
</tr>
<tr class="odd">
<td><p>サポート対象外</p></td>
<td><p>サポート対象外</p></td>
<td><p>True</p></td>
<td><p>TCP ダイヤルバック</p></td>
<td><p>利用できるネゴシエーション方式は TCP ダイヤルバックのみです。</p></td>
</tr>
<tr class="even">
<td><p>サポート対象外</p></td>
<td><p>サポート対象外</p></td>
<td><p>False</p></td>
<td><p>無効な構成</p></td>
<td><div>

> [!WARNING]
> SASL またはダイヤルバックを有効化する必要があります。


</div></td>
</tr>
</tbody>
</table>

