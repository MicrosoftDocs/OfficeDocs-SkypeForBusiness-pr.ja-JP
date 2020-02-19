---
title: 'Lync Server 2013: DNS の概要-単一ディレクター'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76fe7663e0af8eeeb049ca80f1dd92a7cc882b98
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a>DNS の概要-Lync Server 2013 の単一ディレクター

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-20_

次の表に、単一ディレクターのサポートに必要な DNS レコードの概要を示します。 ディレクターの役割では、フロントエンドサーバーと同様の DNS レコードが必要です。 必要なレコード数は、ディレクター証明書で必要なサブジェクトの別名に反映されます。 フロントエンドサーバーとは異なり、ディレクターはユーザーアカウントをホストしたり、モビリティサービスをホストしたりしません。

### <a name="dns-records-required-for-the-director"></a>ディレクターに必要な DNS レコード

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
<td><p>レプリケーションおよびサーバー間で使用されるディレクターホストレコード</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>ディレクター</p></td>
<td><p>エッジサーバーの内部エッジインターフェイスからの受信セッション開始プロトコル (SIP)</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>ディレクター</p></td>
<td><p>リバース プロキシからの公開済みダイヤルイン Web サービス</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>ディレクター</p></td>
<td><p>リバース プロキシからの公開済みミーティング Web サービス</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>ディレクター</p></td>
<td><p>リバースプロキシの Web チケット外部 web サービスによって発行され、ディレクター用に定義される</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

