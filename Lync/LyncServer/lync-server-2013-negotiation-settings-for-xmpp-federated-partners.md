---
title: 'Lync Server 2013: XMPP フェデレーション パートナーのネゴシエーション設定'
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
ms.openlocfilehash: 995ee34d0a2dcf28ca6aa4f8158d0e08d1533191
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a>Lync Server 2013 の XMPP フェデレーション パートナーのネゴシエーション設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-21_

XMPP パートナーの構成でのネゴシエーションの種類の設定には、さまざまな組み合わせが用意されています。 これらの組み合わせの一部は有効ではありません。 このトピックで詳しく説明する表では、有効な設定と無効な設定を定義しています。 一般的な構成は、最初の表の2番目の表で、可能なすべての組み合わせの詳細を示しています。 *トランスポート層セキュリティ*(TLS) も使用できる**場合を除き**、*単純な認証とセキュリティレイヤー* (SASL) を持つことはできないことに注意してください。 SASL は、暗号化されていない (読み取り可能な) 形式で送信され、TLS などの別の手段で保護されている場合を除き、送信しないでください。

### <a name="common-xmpp-federation-negotiation-methods"></a>一般的な XMPP のフェデレーションネゴシエーションの方法

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
<th>簡易認証とセキュリティレイヤー (SASL)</th>
<th>ダイヤルバックの認証</th>
<th>予期される認証方法</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>必須</p></td>
<td><p>必須</p></td>
<td><p>False</p></td>
<td><p>TLS 経由の SASL</p></td>
<td><p>TLS と SASL は、SASL メッセージストリームがセキュリティで保護されていることを確認するのに役立ちます。 コールバックは使用できません。 XMPP フェデレーションパートナーが TLS を必須またはオプションに設定していない場合は、フォールバックメソッドに使用できません。</p></td>
</tr>
<tr class="even">
<td><p>必須</p></td>
<td><p>省略可能</p></td>
<td><p>True</p></td>
<td><p>TLS 経由の SASL、TLS コールバック、TCP コールバック</p></td>
<td><p>XMPP フェデレーションパートナーが、オプションまたは必須の SASL に SASL を設定している場合は、TLS を要求することによって使用されます。 SASL が利用できない場合は、TLS 経由のダイヤルバックが使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>省略可能</p></td>
<td><p>省略可能</p></td>
<td><p>True</p></td>
<td><p>TLS 経由の SASL、TLS コールバック、TCP コールバック</p></td>
<td><p>提供されているネゴシエーションの方法は非常に柔軟ですが、これらの設定は XMPP フェデレーションパートナーの設定に依存します。 パートナーに TLS がオプションまたは必須であるが、SASL はサポートされていない場合は、TLS のコールバックが利用可能になります。 パートナーの TLS と SASL がオプションまたは必須に設定されている場合は、SASL を介した TLS の最適な選択が使用されます。</p></td>
</tr>
<tr class="even">
<td><p>サポート対象外</p></td>
<td><p>サポート対象外</p></td>
<td><p>True</p></td>
<td><p>TCP コールバック</p></td>
<td><p>多くの場合、TCP コールバックは唯一の解決策です。 他のオプションよりも望ましいのは、何らかの信頼レベルを提供することです。</p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a>XMPP フェデレーションネゴシエーションメソッドマトリックス-完了

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
<th>簡易認証とセキュリティレイヤー (SASL)</th>
<th>ダイヤルバックの認証</th>
<th>予期される認証方法</th>
<th>無効な構成のメモ、警告、またはエラー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>必須</p></td>
<td><p>必須</p></td>
<td><p>True</p></td>
<td><p>TLS 経由の SASL</p></td>
<td><div>

> [!WARNING]  
> SASL と TLS の両方が必要な場合、コールバックは動作しません。


</div></td>
</tr>
<tr class="even">
<td><p>必須</p></td>
<td><p>必須</p></td>
<td><p>False</p></td>
<td><p>TLS 経由の SASL</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>省略可能</p></td>
<td><p>必須</p></td>
<td><p>True</p></td>
<td><p>TLS 経由の SASL、TLS コールバック、TCP コールバック</p></td>
<td><div>

> [!WARNING]  
> SASL には TLS が必要です。 TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する可能性があります。


</div></td>
</tr>
<tr class="even">
<td><p>省略可能</p></td>
<td><p>必須</p></td>
<td><p>False</p></td>
<td><p>TLS 経由の SASL</p></td>
<td><div>

> [!WARNING]  
> SASL には TLS が必要です。 TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する可能性があります。


</div></td>
</tr>
<tr class="odd">
<td><p>サポート対象外</p></td>
<td><p>必須</p></td>
<td><p>True</p></td>
<td><p>TCP コールバック</p></td>
<td><div>

> [!WARNING]  
> SASL には TLS が必要です。 TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する可能性があります。


</div></td>
</tr>
<tr class="even">
<td><p>サポート対象外</p></td>
<td><p>必須</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> 有効な構成ではありません


</div></td>
<td><div>

> [!WARNING]  
> SASL には TLS が必要であるため、TLS は利用できません。 SASL/TLS は成功しません。 TCP コールバックは false に設定されているため、使用できません。


</div></td>
</tr>
<tr class="odd">
<td><p>必須</p></td>
<td><p>省略可能</p></td>
<td><p>True</p></td>
<td><p>Tls による SASL、TLS のコールバック</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>必須</p></td>
<td><p>省略可能</p></td>
<td><p>False</p></td>
<td><p>TLS 経由の SASL</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>省略可能</p></td>
<td><p>省略可能</p></td>
<td><p>True</p></td>
<td><p>TLS 経由の SASL、TLS コールバック、TCP コールバック</p></td>
<td><div>

> [!WARNING]  
> SASL には TLS が必要です。 TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する可能性があります。


</div></td>
</tr>
<tr class="even">
<td><p>省略可能</p></td>
<td><p>省略可能</p></td>
<td><p>False</p></td>
<td><p>TLS 経由の SASL</p></td>
<td><div>

> [!WARNING]  
> SASL には TLS が必要です。 TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する可能性があります。


</div></td>
</tr>
<tr class="odd">
<td><p>サポート対象外</p></td>
<td><p>省略可能</p></td>
<td><p>True</p></td>
<td><p>TCP コールバック</p></td>
<td><div>

> [!WARNING]  
> SASL には TLS が必要です。 TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する可能性があります。


</div></td>
</tr>
<tr class="even">
<td><p>サポート対象外</p></td>
<td><p>省略可能</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> 有効な構成ではありません


</div></td>
<td><div>

> [!WARNING]  
> SASL には TLS が必要です。 TLS をオプションとして許可すると、セッションのネゴシエーションが失敗する可能性があります。


</div></td>
</tr>
<tr class="odd">
<td><p>必須</p></td>
<td><p>サポート対象外</p></td>
<td><p>True</p></td>
<td><p>TLS のコールバック</p></td>
<td><p>構成により、TLS のコールバックが可能になります。</p></td>
</tr>
<tr class="even">
<td><p>必須</p></td>
<td><p>サポート対象外</p></td>
<td><p>False</p></td>
<td><p>有効な構成ではありません</p></td>
<td><div>

> [!WARNING]  
> SASL またはダイヤルバックを有効にする必要があります。


</div></td>
</tr>
<tr class="odd">
<td><p>省略可能</p></td>
<td><p>サポート対象外</p></td>
<td><p>True</p></td>
<td><p>TLS のダイヤルバック, TCP コールバック</p></td>
<td><p>他のエンドポイントのネゴシエーションの選択肢に基づいて、TCP または TLS のコールバックが受け入れられます。</p></td>
</tr>
<tr class="even">
<td><p>省略可能</p></td>
<td><p>サポート対象外</p></td>
<td><p>False</p></td>
<td><p>有効な構成ではありません</p></td>
<td><div>

> [!WARNING]  
> SASL またはダイヤルバックを有効にする必要があります。


</div></td>
</tr>
<tr class="odd">
<td><p>サポート対象外</p></td>
<td><p>サポート対象外</p></td>
<td><p>True</p></td>
<td><p>TCP コールバック</p></td>
<td><p>TCP コールバックは、唯一利用可能なネゴシエーションの方法です。</p></td>
</tr>
<tr class="even">
<td><p>サポート対象外</p></td>
<td><p>サポート対象外</p></td>
<td><p>False</p></td>
<td><p>有効な構成ではありません</p></td>
<td><div>

> [!WARNING]  
> SASL またはダイヤルバックを有効にする必要があります。


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

