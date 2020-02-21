---
title: 'Lync Server 2013: XMPP フェデレーションパートナーのネゴシエーション設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab897bf5bc9d959089090ebeaaddc4d766549401
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a>Lync Server 2013 での XMPP フェデレーションパートナーのネゴシエーション設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-21_

XMPP パートナーの構成におけるネゴシエーションの種類の設定には、さまざまな組み合わせがあります。 これらの組み合わせのすべてが有効なわけではありません。 このトピックで詳細に記載されている表では、有効で有効な設定を定義しています。 一般的な構成については、第1の表で、考えられるすべての組み合わせの詳細な2番目の表で説明します。 *トランスポート層セキュリティ*(TLS) も使用できる**場合を除き**、*単純な認証およびセキュリティ層*(SASL) を使用することはできないことに注意してください。 SASL は暗号化されていない (読み取り可能な) 形式で送信されるため、TLS などの別の手段で保護されていない限り、送信しないでください。

### <a name="common-xmpp-federation-negotiation-methods"></a>よく使用される XMPP フェデレーションのネゴシエーション方式

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
<td><p>はい</p></td>
<td><p>SASL over TLS、TLS ダイヤルバック、TCP ダイヤルバック</p></td>
<td><p>TLS を必須にすると、XMPP フェデレーション パートナーが SASL をオプションまたは必須に設定していた場合は SASL が使用されます。SASL が利用できない場合は、ダイヤルバック over TLS が使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>省略可能</p></td>
<td><p>オプション</p></td>
<td><p>はい</p></td>
<td><p>SASL over TLS、TLS ダイヤルバック、TCP ダイヤルバック</p></td>
<td><p>きわめて柔軟なネゴシエーション方式が用意されているものの、これらの設定は XMPP フェデレーション パートナーの設定に依存します。パートナーが TLS をオプションまたは必須にしているのに SASL がサポートされていない場合は、TLS ダイヤルバックが利用できます。パートナーが TLS と SASL をオプションまたは必須に設定している場合は、最適な選択肢である TLS over SASL が使用されます。</p></td>
</tr>
<tr class="even">
<td><p>サポート対象外</p></td>
<td><p>サポート対象外</p></td>
<td><p>はい</p></td>
<td><p>TCP ダイヤルバック</p></td>
<td><p>多くの場合、使用できるソリューションは TCP ダイヤルバックのみです。ほかのオプションに比べると好ましくありませんが、ある程度の信頼は提供されます。</p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a>XMPP フェデレーション ネゴシエーション方式のマトリックス - すべて

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
<td><p>はい</p></td>
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
<td></td>
</tr>
<tr class="odd">
<td><p>オプション</p></td>
<td><p>必須</p></td>
<td><p>はい</p></td>
<td><p>SASL over TLS、TLS ダイヤルバック、TCP ダイヤルバック</p></td>
<td><div>

> [!WARNING]  
> SASL には TLS が必須です。 TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。


</div></td>
</tr>
<tr class="even">
<td><p>オプション</p></td>
<td><p>必須</p></td>
<td><p>False</p></td>
<td><p>SASL over TLS</p></td>
<td><div>

> [!WARNING]  
> SASL には TLS が必須です。 TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。


</div></td>
</tr>
<tr class="odd">
<td><p>サポート対象外</p></td>
<td><p>必須</p></td>
<td><p>はい</p></td>
<td><p>TCP ダイヤルバック</p></td>
<td><div>

> [!WARNING]  
> SASL には TLS が必須です。 TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。


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
> SASL には TLS が必須ですが　TLS は利用できないため、SASL/TLS は成功しません。TCP ダイヤルバックは False に設定され、使用されません。


</div></td>
</tr>
<tr class="odd">
<td><p>必須</p></td>
<td><p>省略可能</p></td>
<td><p>はい</p></td>
<td><p>SASL over TLS、TLS ダイヤルバック</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>必須</p></td>
<td><p>省略可能</p></td>
<td><p>False</p></td>
<td><p>SASL over TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>省略可能</p></td>
<td><p>オプション</p></td>
<td><p>はい</p></td>
<td><p>SASL over TLS、TLS ダイヤルバック、TCP ダイヤルバック</p></td>
<td><div>

> [!WARNING]  
> SASL には TLS が必須です。 TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。


</div></td>
</tr>
<tr class="even">
<td><p>省略可能</p></td>
<td><p>オプション</p></td>
<td><p>False</p></td>
<td><p>SASL over TLS</p></td>
<td><div>

> [!WARNING]  
> SASL には TLS が必須です。 TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。


</div></td>
</tr>
<tr class="odd">
<td><p>サポート対象外</p></td>
<td><p>オプション</p></td>
<td><p>はい</p></td>
<td><p>TCP ダイヤルバック</p></td>
<td><div>

> [!WARNING]  
> SASL には TLS が必須です。 TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する場合があります。


</div></td>
</tr>
<tr class="even">
<td><p>サポート対象外</p></td>
<td><p>オプション</p></td>
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
<td><p>はい</p></td>
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
<td><p>オプション</p></td>
<td><p>サポート対象外</p></td>
<td><p>はい</p></td>
<td><p>TLS ダイヤルバック、TCP ダイヤルバック</p></td>
<td><p>もう一方のエンドポイントが選択したネゴシエーションに基づいて、TCP または TLS ダイヤルバックを受け入れます。</p></td>
</tr>
<tr class="even">
<td><p>オプション</p></td>
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
<td><p>はい</p></td>
<td><p>TCP ダイヤルバック</p></td>
<td><p>利用できるネゴシエーション方式は TCP ダイヤルバック のみです。</p></td>
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


</div>

<span> </span>

</div>

</div>

</div>

