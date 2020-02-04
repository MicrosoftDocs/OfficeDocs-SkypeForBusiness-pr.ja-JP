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
ms.openlocfilehash: 1fcd6cb462bd64f6fdcdbae93cfb733de0639898
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a>Lync Server 2013 の SIPResponseMetaData テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-28_

SIPResponseMetaDataTable には、SIP 応答コードの一覧と、各コードの分類と定義が含まれています。 これらのコードは、SIP デバイスと SIP コミュニケーションセッションに影響を与えるイベントに対応して生成されます。たとえば、応答コード403は、SIP デバイスが要求を行ったときに、サーバーがその要求を受け入れることを拒否したときに生成されます。

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
<th>列</th>
<th>データ型</th>
<th>キー/インデックス</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>返信</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>SIP 応答コードを表す数値。</p></td>
</tr>
<tr class="even">
<td><p><strong>クラス</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>応答コードの一般的な分類。 分類には以下が含まれます。</p>
<ul>
<li><p>1–情報の返信</p></li>
<li><p>2–成功応答</p></li>
<li><p>3–リダイレクション応答</p></li>
<li><p>4–クライアントエラー応答</p></li>
<li><p>5--サーバー障害への応答</p></li>
<li><p>6–グローバルエラー応答</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>説明</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>SIP 応答コードの説明。 たとえば、応答コード181には次の説明があります。</p>
<p>通話が転送されています</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

