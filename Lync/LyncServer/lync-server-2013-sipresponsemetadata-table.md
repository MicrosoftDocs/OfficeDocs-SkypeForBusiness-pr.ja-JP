---
title: 'Lync Server 2013: SIPResponseMetaData テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2418851ed66500937dab92f2820c36a8d1afac3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519634"
---
# <a name="sipresponsemetadata-table-in-lync-server-2013"></a>Lync Server 2013 の SIPResponseMetaData テーブル

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

SIPResponseMetaDataTable には、SIP 応答コードと、各コードの分類と定義の一覧が含まれます。これらのコードは SIP デバイスおよび SIP 通信セッションに影響を与えるイベントへの応答して生成されます。たとえば、応答コード 403 は、SIP デバイスが要求を行い、サーバーがその要求の実行を拒否したときに生成されます。

この表は、Microsoft Lync Server 2013 で導入されました。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Column</th>
<th>データ型</th>
<th>キー/インデックス</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>SIP 応答コードを表す数値。</p></td>
</tr>
<tr class="even">
<td><p><strong>Class</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>応答コードの一般的な分類。以下の分類があります。</p>
<ul>
<li><p>1 – 情報応答</p></li>
<li><p>2 – 正常応答</p></li>
<li><p>3 – リダイレクト応答</p></li>
<li><p>4 – クライアント エラー応答</p></li>
<li><p>5--サーバーエラー応答</p></li>
<li><p>6 – グローバル エラー応答</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>説明</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>SIP 応答コードの説明。たとえば、コード 181 には以下の説明があります。</p>
<p>Call Is Being Forwarded (呼び出しを転送中)</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

