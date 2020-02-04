---
title: 'Lync Server 2013: DNS の概要 - 拡張ディレクター プール、ハードウェア ロード バランサー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled Director pool, hardware load balancer
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48183340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 891b69339416c81d81e72e43edf5f09bbf9da3e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>DNS の概要 - Lync Server 2013 の拡張ディレクター プール、ハードウェア ロード バランサー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-20_

次の表には、ハードウェア負荷分散ダイレクタをサポートするために必要な DNS レコードの概要が記載されています。 ディレクターの役割には、フロントエンドサーバーと同様の DNS レコードが必要です。 必要なレコードの数は、ディレクター証明書に必要なサブジェクトの代替名に反映されます。 フロントエンドサーバーとは異なり、ディレクタープールでは、ユーザーアカウントをホストしたり、モビリティサービスをホストしたりすることはありません。

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a>ハードウェアロードバランサーと DNS の負荷分散を使用して、ディレクタープールに必要な DNS レコード

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>場所/種類/ポート</th>
<th>FQDN/DNS レコード</th>
<th>IP アドレス/FQDN</th>
<th>マップ先/コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>ディレクター</p></td>
<td><p>レプリケーションとサーバー間通信に使用されるディレクターホストレコード</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>ディレクタープール HLB VIP</p></td>
<td><p>DNS 負荷分散ダイレクタプールのホストレコード</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>ディレクタープール HLB VIP</p></td>
<td><p>エッジサーバーの内部インターフェイスからの受信セッション開始プロトコル (SIP)</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>ディレクタープール HLB VIP</p></td>
<td><p>リバースプロキシから発行されたハードウェア負荷分散の web サービス</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>ディレクタープール HLB VIP</p></td>
<td><p>リバースプロキシの web サービスによって発行されるハードウェア負荷分散</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>ディレクタープール HLB VIP</p></td>
<td><p>ハードウェアの負荷分散が発行され、そのリバースプロキシ Web チケットによって定義されます。ディレクタープールの外部 web サービス</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

