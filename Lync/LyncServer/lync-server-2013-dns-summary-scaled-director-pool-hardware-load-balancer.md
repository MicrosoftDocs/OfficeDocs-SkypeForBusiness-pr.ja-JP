---
title: 'Lync Server 2013: DNS の概要-拡張ディレクタープール、ハードウェアロードバランサー'
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
ms.openlocfilehash: 7ed4a3a810e4f1aa2fc5228e61cd68af163c91f0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>DNS の概要-Lync Server 2013 の拡張ディレクタープール、ハードウェアロードバランサー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-20_

次の表に、ハードウェア負荷分散ディレクターをサポートするために必要な DNS レコードの概要を示します。 ディレクターの役割では、フロントエンドサーバーと同様の DNS レコードが必要です。 必要なレコード数は、ディレクター証明書で必要なサブジェクトの別名に反映されます。 フロントエンドサーバーとは異なり、ディレクタープールはユーザーアカウントをホストしたり、モビリティサービスをホストしたりしません。

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a>ロードバランサー機器と DNS 負荷分散を使用してディレクタープールに必要な DNS レコード

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
<th>マッピング先/コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>ディレクター</p></td>
<td><p>レプリケーションおよびサーバー間通信に使用されるディレクターホストレコード</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>ディレクタープールの HLB VIP</p></td>
<td><p>DNS 負荷分散ディレクタープールのホストレコード</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>ディレクタープールの HLB VIP</p></td>
<td><p>エッジサーバーの内部インターフェイスからの受信セッション開始プロトコル (SIP)</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>ディレクタープールの HLB VIP</p></td>
<td><p>リバースプロキシからのハードウェア負荷分散公開ダイヤルイン web サービス</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>ディレクタープールの HLB VIP</p></td>
<td><p>リバースプロキシからのハードウェア負荷分散公開会議 web サービス</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>ディレクタープールの HLB VIP</p></td>
<td><p>ハードウェア負荷分散が公開され、リバースプロキシによって、ディレクタープールの Web チケット外部 web サービスによって定義されている。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

