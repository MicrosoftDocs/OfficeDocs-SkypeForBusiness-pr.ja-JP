---
title: 'Lync Server 2013: VoIPDetails ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9553be13dcd73f89ba8d6ab051602d378bf353da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-view-in-lync-server-2013"></a>Lync Server 2013 の VoIPDetails ビュー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-18_

VoIPDetails ビューには、ピアツーピアセッションに関する情報が格納されます。これは、少なくとも1人のユーザーが VoIP ユーザーである場合です。 このビューは、Microsoft Lync Server 2013 で導入されました。

<div>


> [!NOTE]  
> VoIPDetails ビューには、 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 の Sessiondetails ビュー</A>のすべての列に加えて、以下の列も含まれています。



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
<td><p><strong>FromPhone</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>セッションを開始したユーザーの電話の URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>電話番号</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>セッションに参加したユーザーの電話の URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>セッションを切断したユーザーの URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>Uritん</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションを切断したユーザーの URI の種類。 詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>テナント</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションを切断したユーザーのテナント。</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByPhone</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>セッションを切断したユーザーの電話の URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションを開始したユーザーによって使用された仲介サーバー。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションに参加したユーザーが使用した仲介サーバー。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGateway</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションを開始したユーザーによって使用されたゲートウェイ。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGateway</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションに参加したユーザーが使用したゲートウェイ。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

