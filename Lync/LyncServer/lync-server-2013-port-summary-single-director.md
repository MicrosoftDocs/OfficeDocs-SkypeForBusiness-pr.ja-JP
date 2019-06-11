---
title: 'Lync Server 2013: ポートの概要 - 単一のディレクター'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5568a37093f161caef6717df5d3a3f09be6f18c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a>ポートの概要 - Lync Server 2013 での単一のディレクター

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-20_

1つのディレクターのファイアウォールポート要件は、内部インターフェイスまたはリバースプロキシの内部通信ネットワークからディレクターとの通信を確立するために使用されるポートで構成されています。 Microsoft Lync Server 2013 は、既定では、ポート HTTP/TCP 8080 と HTTPS/TCP 4443 が、リバースプロキシからディレクターまで、およびフロントエンドプールとフロントエンドサーバーによって開かれることを想定しています。 さらに、エッジサーバーの内部インターフェイスからディレクターへのセッション開始プロトコル (SIP) 通信と、フロントエンドプールとフロントエンドサーバーへの通信が必要です。 SIP プロトコルは、SIP/MTLS/TCP 5061 をエッジサーバーからフロントエンドプールとフロントエンドサーバーに使用します。 SIP/MTLS/TCP 5061 によるディレクター、フロントエンドプール、フロントエンドサーバーからエッジサーバーの内部インターフェイスへの通信を可能にするルールも作成する必要があります。

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a>ファイアウォールの定義用の単一のディレクターポートとプロトコル

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Role/Protocol/TCP または UDP/ポート</th>
<th>送信元 IP アドレス</th>
<th>宛先 IP アドレス</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>リバースプロキシ内部インターフェイス</p></td>
<td><p>ディレクター</p></td>
<td><p>リバースプロキシの外部で最初に受信した通信は、ディレクターおよびフロントエンドサーバー web サービスに送信されます。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>リバースプロキシ内部インターフェイス</p></td>
<td><p>ディレクター</p></td>
<td><p>リバースプロキシの外部で最初に受信した通信は、ディレクターおよびフロントエンドサーバー web サービスに送信されます。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>ディレクター</p></td>
<td><p>フロントエンドサーバーまたはフロントエンドプール</p></td>
<td><p>ディレクターとフロントエンドサーバーとの間のサーバー間通信</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>内部クライアント</p></td>
<td><p>ディレクター web サービス</p></td>
<td><p>ディレクターは、内部および外部のクライアントに web サービスを提供します。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>内部クライアント</p></td>
<td><p>ディレクター web サービス</p></td>
<td><p>ディレクターは、内部および外部のクライアントに web サービスを提供します。</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>ディレクター</p></td>
<td><p>エッジサーバーからディレクターへの SIP コミュニケーションと、フロントエンドサーバー。</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>一元管理サービスコントローラー (ClsController) またはエージェント (ClasAgent) コマンドとログ収集</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>一元管理サービスコントローラー (ClsController) またはエージェント (ClasAgent) コマンドとログ収集</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任意</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>一元管理サービスコントローラー (ClsController) またはエージェント (ClasAgent) コマンドとログ収集</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

