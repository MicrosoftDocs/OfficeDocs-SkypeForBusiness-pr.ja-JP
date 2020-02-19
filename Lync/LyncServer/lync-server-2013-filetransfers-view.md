---
title: 'Lync Server 2013: FileTransfers ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b1704c3496d8c5971af7830462d17fc48042e57
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a>Lync Server 2013 の FileTransfers ビュー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

FileTransfer view は、ピアツーピアのファイル転送セッションに関する情報を格納します。 このビューは Microsoft Lync Server 2013 で導入されました。

<div>


> [!NOTE]  
> FileTransfers ビューには、以下の列に加えて、 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 の Sessiondetails ビュー</A>のすべての列が含まれています。



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>データ型</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>FileName</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>送信されたファイルの名前です。</p></td>
</tr>
<tr class="even">
<td><p><strong>クッキー</strong></p></td>
<td><p>nvarchar(128</p></td>
<td><p>すべてのフォローアップ メッセージをこれに関連付けられたものとして識別するために使用します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>識別子</p></td>
<td><p>同じファイル名が使用されているファイル送信を区別するための一意の識別子です。</p></td>
</tr>
<tr class="even">
<td><p><strong>Accept</strong></p></td>
<td><p>若干</p></td>
<td><p>TRUE または NULL。TRUE の場合は、Reject と Cancel が NULL になります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>拒否する</strong></p></td>
<td><p>若干</p></td>
<td><p>TRUE または NULL。TRUE の場合は、Accept と Cancel が NULL になります。</p></td>
</tr>
<tr class="even">
<td><p><strong>Cancel</strong></p></td>
<td><p>若干</p></td>
<td><p>TRUE または NULL。TRUE の場合は、Accept と Reject が NULL になります。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

