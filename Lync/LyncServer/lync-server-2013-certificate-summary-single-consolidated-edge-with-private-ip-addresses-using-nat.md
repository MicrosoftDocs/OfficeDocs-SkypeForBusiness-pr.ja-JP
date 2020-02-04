---
title: 'Lync Server 2013: 証明書の概要 - NAT を使用したプライベート IP アドレスを持つ単一統合エッジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 6de6680e-5f47-48e6-8e06-4994d710ea6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398519(v=OCS.15)
ms:contentKeyID: 48184433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b76ba1e92c6c396b81e0a815a9b1368f90b8b85d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>証明書の概要 - Lync Server 2013 内の NAT を使用したプライベート IP アドレスを持つ単一統合エッジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

Microsoft Lync Server 2013 は、証明書を使って、他のサーバーを相互認証したり、サーバーやサーバーからクライアントにデータを暗号化したりします。 証明書には、サーバーに関連付けられているドメインネームシステム (DNS) レコードと証明書のサブジェクト名 (SN) とサブジェクトの代替名 (SAN) の名前が一致している必要があります。 サーバー、DNS レコード、証明書エントリを正常にマッピングするには、DNS に登録されているサーバーの完全修飾ドメイン名と、証明書の SN および SAN エントリを慎重に計画する必要があります。

エッジサーバーの外部インターフェイスに割り当てられている証明書は、公開証明機関 (CA) から要求されます。 統合された通信の目的で証明書を提供することに成功したことを示すパブリック[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395)ca は、次の記事に記載されています。 証明書を要求するときは、Lync Server 展開ウィザードで生成された証明書の要求を使用するか、Lync Server 管理シェルコマンドレットまたはパブリック CA によって提供されたプロセスを使用して手動で要求を作成することができます。 証明書管理用の Lync Server 管理シェルコマンドレットの詳細については、「 [Lync server 2013 の証明書と認証コマンドレット](https://docs.microsoft.com/powershell/module/skype/)」を参照してください。証明書は、アクセスエッジサービスインターフェイス、Web 会議エッジサービスインターフェイス、音声/ビデオ認証サービスに割り当てられます。 音声/ビデオ認証サービスは、音声とビデオのストリームを暗号化するために証明書を使用しない A/V Edge サービスと混同しないようにしてください。 内部の Edge Server インターフェイスは、内部 (組織) CA またはパブリック CA の証明書の証明書を使用できます。 内部インターフェイス証明書は、SN のみを使用します。 SAN エントリは必要ありません。

<div>


> [!NOTE]  
> 次の表は、参照用のサブジェクト代替名の一覧の2番目の SIP エントリ (sip.fabrikam.com) を示しています。 組織内の各 SIP ドメインについて、証明書のサブジェクトの [代替名] リストに記載されている対応する FQDN を追加する必要があります。



</div>

<div>

## <a name="certificates-required-for-single-consolidated-edge-with-private-ip-addresses-using-nat"></a>NAT を使用するプライベート IP アドレスを持つ単一の統合エッジに必要な証明書


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
<th>サブジェクト名 (SN)</th>
<th>サブジェクト代替名 (SAN)/Order</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>単一連結エッジ (外部エッジ)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>証明書はパブリック CA からのものである必要があり、AOL とのパブリック IM 接続が展開される場合は、サーバーの EKU とクライアントの EKU を持っている必要があります。 証明書は、次のための外部エッジインターフェイスに割り当てられます。</p>
<ul>
<li><p>アクセス エッジ</p></li>
<li><p>会議エッジ</p></li>
<li><p>音声ビデオ エッジ</p></li>
</ul>
<p>San は、トポロジビルダーの定義に基づいて、自動的に証明書に追加されることに注意してください。 必要に応じて、必要に応じて SAN エントリを追加します。これには、サポートが必要な追加の SIP ドメインや他のエントリも含まれます。 サブジェクト名は SAN でレプリケートされ、正しい操作のために存在している必要があります。</p></td>
</tr>
<tr class="even">
<td><p>単一連結エッジ (内部エッジ)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>SAN は必要ありません</p></td>
<td><p>証明書は、パブリックまたはプライベート CA によって発行され、サーバーの EKU を含む必要があります。 証明書は、内部エッジインターフェイスに割り当てられます。</p></td>
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
<td><p>外部/アクセスエッジ</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>証明書はパブリック CA からのものである必要があり、AOL とのパブリック IM 接続が展開される場合は、サーバーの EKU とクライアントの EKU を持っている必要があります。 証明書は、次のための外部エッジインターフェイスに割り当てられます。</p>
<ul>
<li><p>アクセス エッジ</p></li>
<li><p>会議エッジ</p></li>
<li><p>音声ビデオ エッジ</p></li>
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

