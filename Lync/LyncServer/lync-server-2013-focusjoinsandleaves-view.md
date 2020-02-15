---
title: 'Lync Server 2013: FocusJoinsAndLeaves ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c5c10cc90064e9ed3237dcd4cd4cbed1021d1b5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a>Lync Server 2013 の FocusJoinsAndLeaves ビュー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

FocusJoinsAndLeaves ビューには、1 つの会議における参加と退出についての情報が格納されます。 各会議は、ユーザーが会議に参加して会議を退出するたびに書き込まれるレコードによってこのビューで表されます。 このビューは Microsoft Lync Server 2013 で導入されました。


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>日付型</p></td>
<td><p>会議インスタンスの時間。 SessionIdSeq と合わせて使用して、会議インスタンスを一意に識別します。 詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a>の電話会議の表」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessionidseq と</strong></p></td>
<td><p>int</p></td>
<td><p>会議インスタンスを識別する ID 番号。 SessionIdTime と合わせて使用して、会議インスタンスを一意に識別します。 詳細については、「 <a href="lync-server-2013-conferences-table.md">Lync Server 2013</a>の電話会議の表」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>会議の参加/退出情報が取得されたユーザーの URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>Useruritoff</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>会議の参加/退出情報が取得されたユーザーの URI の種類。 詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>会議の参加/退出情報が取得されたユーザーのテナント。 詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>識別子</p></td>
<td><p>会議の参加/退出情報が取得されたユーザーの一意の識別子。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>会議の参加/退出情報が取得されたユーザーが使用したクライアントのバージョン。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>会議の参加/退出情報が取得されたユーザーが使用したクライアント。 詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef table</a> 」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>会議の参加/退出情報が取得されたユーザーが使用したクライアントのカテゴリ名。</p></td>
</tr>
<tr class="even">
<td><p><strong>FocusUserInstance</strong></p></td>
<td><p>int</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><strong>IsuserInternal</strong></p></td>
<td><p>若干</p></td>
<td><p>ユーザーが内部ユーザーかどうかを示すビット。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>日付型</p></td>
<td><p>セッション要求の時間。 セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>ユーザーが複数のコンピューターまたはデバイスから同時にログオンしている場合は、UserInstance を使用してユーザーとデバイスの組み合わせを一意に識別します。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>セッションの SIP ダイアログ ID。形式は dialog;from-tag;to-tag です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>日付型</p></td>
<td><p>ユーザーが会議に参加した時刻。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>日付型</p></td>
<td><p>ユーザーが会議を退出した時刻。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserRole</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>会議でのユーザーの役割 (発表者、参加者など)。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

