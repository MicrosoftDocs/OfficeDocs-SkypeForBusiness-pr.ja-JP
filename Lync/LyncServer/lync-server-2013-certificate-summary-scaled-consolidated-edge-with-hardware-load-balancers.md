---
title: 証明書の概要 - 拡張統合エッジ (ロード バランサー機器を使用)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 894a9f3e-7cba-4915-8fdf-e52f2f25126f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398692(v=OCS.15)
ms:contentKeyID: 48184729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccba3f1facf8d687f4448efc7aeff053f50b3be7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>証明書の概要 - Lync Server 2013 の拡張統合エッジ (ロード バランサー機器を使用)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

Microsoft Lync Server 2013 は、証明書を使って、他のサーバーを相互認証したり、サーバーやサーバーからクライアントにデータを暗号化したりします。 証明書には、サーバーに関連付けられているドメインネームシステム (DNS) レコードと証明書のサブジェクト名 (SN) とサブジェクトの代替名 (SAN) の名前が一致している必要があります。 サーバー、DNS レコード、証明書エントリを正常にマッピングするには、DNS に登録されているサーバーの完全修飾ドメイン名と、証明書の SN および SAN エントリを慎重に計画する必要があります。

エッジサーバーの外部インターフェイスに割り当てられている証明書は、公開証明機関 (CA) から要求されます。 統合された通信の目的で証明書を提供することに成功したことを示すパブリック[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395)ca は、次の記事に記載されています。 証明書を要求するときは、Lync Server 展開ウィザードで生成された証明書の要求を使用するか、またはパブリック CA によって提供されるプロセスによって要求を手動で作成することができます。 証明書を割り当てる場合、証明書は、アクセスエッジサービスインターフェイス、Web 会議エッジサービスインターフェイス、および音声/ビデオ認証サービスに割り当てられます。 音声/ビデオ認証サービスは、音声とビデオのストリームを暗号化するために証明書を使用しない A/V Edge サービスと混同しないようにしてください。 内部の Edge Server インターフェイスは、内部 (組織) CA またはパブリック CA の証明書の証明書を使用できます。 内部インターフェイス証明書は、SN のみを使用します。 SAN エントリは必要ありません。

<div>


> [!NOTE]
> 次の表は、参照用のサブジェクト代替名の一覧の2番目の SIP エントリ (sip.fabrikam.com) を示しています。 組織内の各 SIP ドメインについて、証明書のサブジェクトの [代替名] リストに記載されている対応する FQDN を追加する必要があります。



</div>

<div>

## <a name="certificates-required-for-scaled-consolidated-edge-with-hardware-load-balancers"></a>ハードウェアロードバランサーを使った統合エッジの拡大に必要な証明書


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>コンポーネント</th>
<th>サブジェクト名</th>
<th>サブジェクト代替名 (SAN)/Order</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1つの統合エッジサーバー (外部エッジ)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>証明書はパブリック CA からのものである必要があり、AOL とのパブリック IM 接続が展開される場合は、サーバーの EKU とクライアントの EKU を持っている必要があります。 さらに、スケールエッジサーバーの場合、証明書の秘密キーはエクスポート可能であり、証明書と秘密キーが各エッジサーバーにコピーされる必要があります。証明書は、次のような外部エッジインターフェイスに割り当てられます。</p>
<ul>
<li><p>アクセス エッジ サービス</p></li>
<li><p>Web 会議エッジ サービス</p></li>
<li><p>音声ビデオ エッジ サービス</p></li>
</ul>
<p>San は、トポロジビルダーの定義に基づいて、自動的に証明書に追加されることに注意してください。 必要に応じて、必要に応じて SAN エントリを追加します。これには、サポートが必要な追加の SIP ドメインや他のエントリも含まれます。 サブジェクト名は SAN でレプリケートされ、正しい操作のために存在している必要があります。</p></td>
</tr>
<tr class="even">
<td><p>1つの統合エッジサーバー (内部エッジ)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>SAN は必要ありません</p></td>
<td><p>証明書は、パブリックまたはプライベート CA によって発行され、サーバーの EKU を含む必要があります。 証明書は、内部エッジサーバーインターフェイスに割り当てられます。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>証明書の概要–パブリックインスタントメッセージング接続


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>コンポーネント</th>
<th>サブジェクト名</th>
<th>サブジェクト代替名 (SAN)/Order</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部/アクセスエッジサービス</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>証明書はパブリック CA からのものである必要があり、AOL とのパブリック IM 接続が展開される場合は、サーバーの EKU とクライアントの EKU を持っている必要があります。 証明書は、次のための外部エッジインターフェイスに割り当てられます。</p>
<ul>
<li><p>アクセス エッジ サービス</p></li>
<li><p>Web 会議エッジ サービス</p></li>
<li><p>音声ビデオ エッジ サービス</p></li>
</ul>
<p>San は、トポロジビルダーの定義に基づいて、自動的に証明書に追加されることに注意してください。 必要に応じて、必要に応じて SAN エントリを追加します。これには、サポートが必要な追加の SIP ドメインや他のエントリも含まれます。 サブジェクト名は SAN でレプリケートされ、正しい操作のために存在している必要があります。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>拡張メッセージングとプレゼンスプロトコルの証明書の概要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>コンポーネント</th>
<th>サブジェクト名</th>
<th>サブジェクト代替名 (SAN)/Order</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>エッジサーバーまたはエッジプールのアクセスエッジサービスに割り当てる</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>xmpp.contoso.com</p>
<p><strong>*.contoso.com</strong></p></td>
<td><p>最初の3つの SAN エントリは、フルエッジサーバーの通常の SAN エントリです。 Contoso.com は、ルートドメインレベルで XMPP パートナーとのフェデレーションを行うために必要なエントリです。 このエントリを使用すると、contoso.com サフィックスの付いたすべてのドメインで XMPP が許可されます。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

