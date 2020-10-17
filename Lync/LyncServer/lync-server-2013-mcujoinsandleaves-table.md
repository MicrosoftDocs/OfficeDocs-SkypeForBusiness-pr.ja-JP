---
title: 'Lync Server 2013: McuJoinsAndLeaves テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves table
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398316(v=OCS.15)
ms:contentKeyID: 48184115
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4aa5fb14ff16d13b1cdff72f15c648f9e353922
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524734"
---
# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a>Lync Server 2013 の McuJoinsAndLeaves テーブル

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

この表の各レコードには、ユーザー参加または電話会議サーバーの1つの組み合わせに関する通話の詳細が含まれています。 たとえば、web 会議と音声ビデオの要素を含む会議にユーザーが参加すると、そのユーザーの web 会議への参加に対して1つのレコードが作成され、そのユーザーの音声/ビデオ会議の参加に対して別のレコードが作成されます。


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>日付型</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>会議インスタンスの時間。 <strong>Sessionidseq</strong>と組み合わせて、電話会議のインスタンスを一意に識別するために使用されます。 詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a> の電話会議の表」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessionidseq と</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>会議インスタンスを識別する ID 番号。 <strong>Sessionidtime</strong>と組み合わせて、電話会議のインスタンスを一意に識別するために使用されます。 詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a> の電話会議の表」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>このユーザーを識別する一意の番号。 詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>ユーザーが複数のコンピューターまたはデバイスで同時にログオンしている場合、McuUserInstance はユーザーとデバイスの組み合わせを一意に識別します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsFromPstn</strong></p></td>
<td><p>若干</p></td>
<td><p> </p></td>
<td><p>ユーザーが PSTN から参加しているかどうかを指定します。</p></td>
</tr>
<tr class="even">
<td><p><strong>McuId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>この会議サーバーを示す一意の番号です。 詳細については、「 <a href="lync-server-2013-mcus-table.md">Lync Server 2013 の mcu テーブル</a> 」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>日付型</p></td>
<td><p>外部</p></td>
<td><p>セッション要求の時刻。 セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>セッションを識別するための ID 番号。 セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>日付型</p></td>
<td><p> </p></td>
<td><p>このユーザーがこの会議サーバーに参加した時刻。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>日付型</p></td>
<td><p> </p></td>
<td><p>このユーザーがこの会議サーバーから退室した時刻。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>電話会議で使用するクライアントソフトウェアのバージョン番号を指定する識別子。 詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions</a> 」の表を参照してください。</p>
<p>このフィールドは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

