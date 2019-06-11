---
title: ポートの概要-拡張可能なメッセージングとプレゼンスプロトコル (XMPP) フェデレーション
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b36a74393a8c61d5281bb009d212ee0bb12cf0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>ポート概要-Lync Server 2013 での拡張可能なメッセージングとプレゼンスプロトコル (XMPP) フェデレーション

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-20_

エッジサーバーに展開された拡張メッセージングとプレゼンスプロトコル (XMPP) プロキシ用に定義されたポートとプロトコルを使うと、XMPP フェデレーションパートナーからエッジサーバーへの通信が可能になり、エッジサーバーから XMPP への通信も可能になります。フェデレーションパートナー。 フロントエンドサーバーまたはフロントエンドプールからエッジサーバーまたはエッジプールへのルールも定義されています。

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>拡張メッセージングとプレゼンスプロトコルのファイアウォールの概要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocol/TCP または UDP/ポート</th>
<th>ソース (IP アドレス)</th>
<th>宛先 (IP アドレス)</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任意</p></td>
<td><p>Access Edge サービスインターフェイスの IP アドレス</p></td>
<td><p>XMPP 向けの標準的なサーバー間通信ポート。 フェデレーションされた XMPP パートナーからエッジサーバーの XMPP プロキシへの通信を許可します。</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Access Edge サービスインターフェイスの IP アドレス</p></td>
<td><p>任意</p></td>
<td><p>XMPP 向けの標準的なサーバー間通信ポート。 エッジサーバーの XMPP プロキシからフェデレーションされた XMPP パートナーへの通信を許可します。</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>任意</p></td>
<td><p>内部エッジサーバーインターフェイス IP</p></td>
<td><p>フロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイからエッジサーバーへの内部の XMPP トラフィック</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での XMPP 構成の例  - Google Talk との XMPP フェデレーション](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Lync Server 2013 での組織の XMPP フェデレーション パートナーの管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

