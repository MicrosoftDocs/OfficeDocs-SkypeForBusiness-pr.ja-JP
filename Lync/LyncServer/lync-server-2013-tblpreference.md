---
title: 'Lync Server 2013: tblPreference'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48185913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 652312c5ca48a140ee7f17486ef98debb4e08672
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblpreference-in-lync-server-2013"></a>Lync Server 2013 の tblPreference

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-24_

tblPreference には、ユーザーのクライアントの設定が含まれます。 通常、これは Lync 2013 より前のクライアントで使用されます。

### <a name="columns"></a>行

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>型</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prefLabel</p></td>
<td><p>nvarchar (255)、null ではない</p></td>
<td><p>"ユーザー sip uri &lt;&gt;| ユーザー名" のような形式のラベル。&lt;設定&gt;。</p></td>
</tr>
<tr class="even">
<td><p>prefSeqID</p></td>
<td><p>int (null ではない)</p></td>
<td><p>バージョン管理のための連続番号 (ラベルあたり)。</p></td>
</tr>
<tr class="odd">
<td><p>prefContent</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>エンコードされたコンテンツ。</p></td>
</tr>
<tr class="even">
<td><p>最終方法</p></td>
<td><p>int (null ではない)</p></td>
<td><p>設定を更新したプリンシパルの ID です。</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>キー

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;prefLabel, prefSeqID&gt;</p></td>
<td><p>主キー。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

