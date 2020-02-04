---
title: 'Lync Server 2013: ConferenceSessionDetails テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61da586f3ecaf215b3bb636a80141ba8aaa19f18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a>Lync Server 2013 の ConferenceSessionDetails テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-28_

各レコードは1つの会議セッションを表します。これは、フォーカスのあるセッションまたは特定の会議サーバーのセッションのいずれかになります。


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
<td><p><strong>セッション Id</strong></p></td>
<td><p>Datetime</p></td>
<td><p>プライマリ、外部</p></td>
<td><p>セッション要求の時刻。電話会議セッションを一意に識別するために<strong>Sessionidseq</strong>と組み合わせて使用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>プライマリ、外部</p></td>
<td><p>セッションを識別する ID 番号。 電話会議セッションを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使われます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。 *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>このセッションに関連する会議の URI にフォーカスを移動します。 詳細については、「 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a>」を参照してください。 この URI は、フォーカスベースの会議 URI です。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>長さ</p></td>
<td></td>
<td><p>定期的な会議のインスタンスを区別する識別子。 各定期的な会議インスタンスの ConferenceURI は同じですが、異なる ConfInstance 値があります。</p>
<p>このフィールドは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>このセッションに関連する会議サーバーの会議 URI。 詳細については、「 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a>」を参照してください。 この URI は、会議サーバーベースの会議 URI です。 フォーカス会議セッションの場合、この列は null になります。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>会議セッションの1人のユーザーの ID です。 詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>長さ</p></td>
<td></td>
<td><p>エンドポイントのインスタンスを識別するための GUID。 たとえば、あるユーザーが同じアカウントで異なるコンピューターにログオンしている場合、各コンピューターには別のエンドポイント ID があります。</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者が代理としているユーザーの ID を示します。 詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話を参照するユーザーの ID です。 詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>電話会議ユーザーが使用したクライアントバージョン。 詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions の表</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>会議サーバーで使用されるクライアントのバージョンです。 詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions の表</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>Edialogidtime の置き換え</strong></p></td>
<td><p>datetime</p></td>
<td><p>外部</p></td>
<td><p>現在のセッションによって置き換えられたダイアログを識別する ID 番号。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Edialogidseq の置き換え</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>セッションを識別する ID 番号。 このセッションによって置き換えられるセッションを一意に識別するために、<strong>代替の操作と組み合わせ</strong>て使います。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>セッションが会議サーバーによって開始されたかどうかを示します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>会議サーバーによってセッションが終了したかどうかを示します。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>ユーザーが内部からログオンしているかどうか。</p></td>
</tr>
<tr class="odd">
<td><p><strong>返信</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>セッションの招待状へのセッション開始プロトコル (SIP) 応答コード。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>SIP ヘッダーからキャプチャされた診断 ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>このセッションで使用するフロントエンドサーバーの ID です。 詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>セッションがキャプチャされたプールの ID です。 詳細については、「 <a href="lync-server-2013-pools-table.md">Lync Server 2013 のプールテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話が使用している仲介サーバー。 詳細については、「 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の Mediationservers の表</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>GatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話が使用しているゲートウェイ。 詳細については、「 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話が使用しているエッジサーバー。 詳細については、「 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>セッションで使用されるコンテンツタイプ。 詳細については、「 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 の ContentTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>最初の招待要求の時刻。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>最初の SIP 応答の時刻。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</p></td>
</tr>
<tr class="odd">
<td><p><strong>セッション終了時刻</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>セッションが終了した時刻。</p></td>
</tr>
<tr class="even">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>外部</p></td>
<td><p><a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>の MCU URI の種類の値が含まれています。 このフィールドは、クエリのパフォーマンスを向上させるために使用されます。</p>
<p>このフィールドは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>ユーザー属性を示すビットセット。 次の属性定義が表示されます。</p>
<ul>
<li><p>デスクトップ電話と統合-1</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>呼び出し属性を示すビットセット。 次の属性定義が表示されます。</p>
<ul>
<li><p>セッションを再試行しました-1</p></li>
</ul></td>
</tr>
</tbody>
</table>


\*ほとんどのセッションでは、SessionIdSeq の値は1になります。 複数のセッションが同時に開始された場合は、1つのセッションの SessionIdSeq は1、それ以外の場合は2となります。

</div>

<span> </span>

</div>

</div>

</div>

