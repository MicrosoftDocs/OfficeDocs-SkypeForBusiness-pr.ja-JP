---
title: 'Lync Server 2013: 証明書の概要-拡張可能なメッセージングとプレゼンスプロトコル (XMPP) フェデレーション'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49105661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01b21c8b09d93f8d2788424f2c8f440e1dec66b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>証明書の概要-Lync Server 2013 での拡張可能なメッセージングとプレゼンスプロトコル (XMPP) フェデレーション

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-12-23_

拡張メッセージングとプレゼンスプロトコル (XMPP) パートナーとの通信を有効にして確立するための証明書要件には、XMPP ドメインの追加レコードが必要です。 サブジェクトの代替名 (SAN) として証明書に含まれているレコードは、XMPP 通信に参加できるドメインです。 ドメイン全体で XMPP を有効にする場合や、ユーザーのサブセットに対して XMPP を有効にしている場合は、ドメインのルートレベルのドメイン (たとえば、contoso.com) にすることができます (例: corp.contoso.com)。

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
<p>contoso.com</p></td>
<td><p>最初の3つの SAN エントリは、フルエッジサーバーの通常の SAN エントリです。 Contoso.com は、ルートドメインレベルで XMPP パートナーとのフェデレーションを行うために必要なエントリです。 このエントリは、サフィックス contoso.com を持つすべてのドメインで XMPP を許可します。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での XMPP 構成の例  - Google Talk との XMPP フェデレーション](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Lync Server 2013 でエッジ サーバー証明書を計画する](lync-server-2013-plan-for-edge-server-certificates.md)  


[Lync Server 2013 用のエッジ証明書のセットアップ](lync-server-2013-set-up-edge-certificates.md)  
[要求-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[設定-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

