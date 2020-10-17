---
title: 'Lync Server 2013: ポートの概要-DNS と HLB 負荷分散'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - DNS and HLB load balanced
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48185149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6ba03a73538426b9c820388f65e728c36881148
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527944"
---
# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>ポートの概要-Lync Server 2013 での DNS および HLB の負荷分散

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-22_

単一ディレクターのファイアウォールポート要件は、内部インターフェイスまたはリバースプロキシの内部接続ネットワークからディレクターとの通信を確立するために使用されるポートで構成されます。 Microsoft Lync Server 2013 既定では、ポート HTTP/TCP 8080 および HTTPS/TCP 4443 を、フロントエンドプールおよびフロントエンドサーバーに加えて、ディレクターへのリバースプロキシから開くことが想定されています。 さらに、エッジサーバーの内部インターフェイスから、ディレクターおよびフロントエンドプールおよびフロントエンドサーバーへのセッション開始プロトコル (SIP) 通信が必要です。 SIP プロトコルは、エッジサーバーの SIP/MTLS/TCP 5061 を使用して、フロントエンドプールおよびフロントエンドサーバーに対して使用します。 ディレクター、フロントエンドプールおよびフロントエンドサーバーからエッジサーバーの内部インターフェイスへの SIP/MTLS/TCP 5061 通信を許可するルールも作成する必要があります。

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a>ファイアウォール定義用の単一ディレクターポートとプロトコル

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>役割/プロトコル/TCP または UDP/ポート</th>
<th>送信元 IP アドレス</th>
<th>宛先 IP アドレス</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>リバース プロキシの内部インターフェイス</p></td>
<td><p>ディレクターハードウェアロードバランサーの VIP</p></td>
<td><p>リバースプロキシの外部側で最初に受信された通信は、ディレクター HLB VIP およびフロントエンドサーバー web サービスに送信されます。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>リバース プロキシの内部インターフェイス</p></td>
<td><p>ディレクターハードウェアロードバランサーの VIP</p></td>
<td><p>リバースプロキシの外部側で最初に受信された通信は、ディレクター HLB VIP およびフロントエンドサーバー web サービスに送信されます。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>ディレクター</p></td>
<td><p>フロントエンドプールまたはフロントエンドサーバー</p></td>
<td><p>ディレクター HLB VIP とフロントエンドサーバーまたはフロントエンドサーバーとの間のサーバー間通信。</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>内部クライアント</p></td>
<td><p>ディレクターハードウェアロードバランサーの VIP</p></td>
<td><p>ディレクターは、内部および外部クライアントに web サービスを提供します。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>内部クライアント</p></td>
<td><p>ディレクターハードウェアロードバランサーの VIP</p></td>
<td><p>ディレクターは、内部および外部クライアントに web サービスを提供します。</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>エッジサーバーの内部インターフェイス</p></td>
<td><p>ディレクター</p></td>
<td><p>フロントエンドサーバーに加えて、エッジサーバーからディレクターへの SIP 通信。</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任意</p></td>
<td><p>ディレクター</p></td>
<td><p>集中ログサービスコントローラー (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任意</p></td>
<td><p>ディレクター</p></td>
<td><p>集中ログサービスコントローラー (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任意</p></td>
<td><p>ディレクター</p></td>
<td><p>集中ログサービスコントローラー (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

