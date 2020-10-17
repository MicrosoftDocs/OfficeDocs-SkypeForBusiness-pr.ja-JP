---
title: ポートの概要-拡張可能なメッセージングおよびプレゼンスプロトコル (XMPP) フェデレーション
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c8d7f99b4a7c72b9eb039fb7447397e711caa36
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527924"
---
# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Lync Server 2013 でのポートの概要-拡張可能なメッセージングおよびプレゼンスプロトコル (XMPP) フェデレーション

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-20_

エッジサーバーに展開されている拡張メッセージングおよびプレゼンスプロトコル (XMPP) プロキシに対して定義されているポートとプロトコルは、XMPP フェデレーションパートナーからエッジサーバーへの通信を許可すると共に、エッジサーバーから XMPP フェデレーションパートナーへの通信を許可します。 ルールは、フロントエンドサーバーまたはフロントエンドプールからエッジサーバーまたはエッジプールへの内部接続ファイアウォール上にも定義されています。

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>XMPP のファイアウォールの概要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>プロトコル/TCP または UDP/ポート</th>
<th>送信元 (IP アドレス)</th>
<th>宛先 (IP アドレス)</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任意</p></td>
<td><p>アクセスエッジサービスインターフェイスの IP アドレス</p></td>
<td><p>XMPP 用の標準的なサーバー間通信。 フェデレーションされた XMPP パートナーからのエッジサーバー XMPP プロキシへの通信を許可します。</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>アクセスエッジサービスインターフェイスの IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>XMPP 用の標準的なサーバー間通信。 エッジサーバー XMPP プロキシからフェデレーションされた XMPP パートナーへの通信を許可します。</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>任意</p></td>
<td><p>内部エッジサーバーインターフェイス IP</p></td>
<td><p>フロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイからエッジサーバーへの内部 XMPP トラフィック</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の XMPP 構成の例-Google Talk との XMPP フェデレーション](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Lync Server 2013 での XMPP フェデレーションパートナーの管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

