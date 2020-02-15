---
title: 'Lync Server 2013: 証明書の概要-拡張可能なメッセージングおよびプレゼンスプロトコル (XMPP) フェデレーション'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49105661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13d2b80ed223f7779b406615806c1c00fd0fc860
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>証明書の概要-Lync Server 2013 での拡張可能なメッセージングおよびプレゼンスプロトコル (XMPP) フェデレーション

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-12-23_

Extensible Messaging and Presence Protocol (XMPP) パートナーとの通信を有効にして確立するための証明書要件では、XMPP ドメインの追加レコードが必要になります。サブジェクトの別名 (SAN) として証明書に含まれているレコードは、XMPP 通信に参加できるドメインになります。ドメイン全体に対して XMPP を有効にする場合はドメインをルートレベル ドメイン (例: contoso.com) とし、ユーザーのサブセットに対して XMPP を有効にする場合は子ドメイン (例: corp.contoso.com、finance.contoso.com) を選択できます。

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>Extensible Messaging and Presence Protocol の証明書の概要


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
<th>サブジェクトの別名 (SAN)/順序</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>エッジサーバーまたはエッジプールのアクセスエッジサービスへの割り当て</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>contoso.com</p></td>
<td><p>最初の3つの SAN エントリは、完全なエッジサーバーの通常の SAN エントリです。 contoso.com は、ルート ドメイン レベルでの XMPP パートナーとのフェデレーションに必要なエントリです。 このエントリには、contoso.com というサフィックスを持つすべてのドメインで XMPP が許可されます。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の XMPP 構成の例-Google Talk との XMPP フェデレーション](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Lync Server 2013 でエッジサーバー証明書を計画する](lync-server-2013-plan-for-edge-server-certificates.md)  


[Lync Server 2013 のエッジ証明書のセットアップ](lync-server-2013-set-up-edge-certificates.md)  
[要求-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[設定-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

