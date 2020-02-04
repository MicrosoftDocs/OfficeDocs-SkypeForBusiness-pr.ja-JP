---
title: 'Lync Server 2013: SessionDetails テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b68c50fc17199c68a69c5a7c6dd6abc8a5bd1dac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a>Lync Server 2013 の SessionDetails テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-28_

各レコードは、1つのピアツーピアセッションを表します。これは、VoIP の電話通話、2パーティの IM セッション、または他の種類のセッションである可能性があります。 [Lync Server 2013 でメディアテーブル](lync-server-2013-media-table.md)を使用してテーブルを結合して、このセッションに関連する各メディアの詳細を見つけることができます。

IsUser1IntegratedWithDeskPhone と IsUser2IntegratedWithDeskPhone フィールドが、Microsoft Lync Server 2013 で使用されている SessionDetails テーブルから削除されていることに注意してください。


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
<td><p>datetime</p></td>
<td><p>プライマリ、外部</p></td>
<td><p>セッション要求の時刻。 セッションを一意に識別するために<strong>Sessionidseq</strong>と組み合わせて使用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>プライマリ、外部</p></td>
<td><p>セッションを識別する ID 番号。 セッションを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用されます。 * 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CorrelationId</strong></p></td>
<td><p>長さ</p></td>
<td></td>
<td><p>複数のセッションを関連付けるための GUID。</p></td>
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
<td><p><strong>User1Id</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>セッションの1人のユーザーの ID です。 詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2Id</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>セッション内の他のユーザーの ID です。 詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>User1EndpointId</strong></p></td>
<td><p>長さ</p></td>
<td></td>
<td><p>セッションの最初のユーザーによって使用されるエンドポイントを示す GUID。</p>
<p>このフィールドは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2EndpointId</strong></p></td>
<td><p>長さ</p></td>
<td></td>
<td><p>セッション内の2番目のユーザーによって使用されるエンドポイントを識別する GUID。</p>
<p>このフィールドは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>TargetUserId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>SIP 要求の元の To ユーザーの URI。 詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionStartedById</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>セッションを開始したユーザーの ID です。 詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</p></td>
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
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>このセッションで使用するフロントエンドサーバーの ID です。 詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>セッションがキャプチャされたプールの ID です。 詳細については、「 <a href="lync-server-2013-pools-table.md">Lync Server 2013 のプールテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeID</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>セッションで使用されるコンテンツタイプ。 詳細については、「 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 の ContentTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>User1 が使用するクライアントのバージョン。 詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions の表</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>User2ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>User2 が使用するクライアントのバージョン。 詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions の表</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1EdgeServerid</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>User1 で使用されるエッジサーバー。 詳細については、「 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>User2EdgeServerid</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>User2 によって使用されるエッジサーバー。 詳細については、「 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUser1Internal</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>User1 が内部からログオンしているかどうかを示します。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUser2Internal</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>User2 が内部からログオンしているかどうかを示します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>最初の招待要求の時刻。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>最初の招待メッセージに対する応答の時刻。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</p></td>
</tr>
<tr class="odd">
<td><p><strong>返信</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>セッション招待状への SIP 応答コード。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>SIP ヘッダーからキャプチャされた診断 ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallPriority</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話の優先度。 詳細については、「 <a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 の Callpriorities テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>User1MessageCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>セッション中に User1 から送信されたメッセージの数です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2MessageCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>セッション中に User2 から送信されたメッセージの数です。</p></td>
</tr>
<tr class="even">
<td><p><strong>セッション終了時刻</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>セッションの終了時。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaTypes</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>このセッションのメディアの種類を示すビットセット。 表示される型の定義を次に示します。</p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>インスタント メッセージ</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>FILE_TRANSFER</p></td>
<td><p>両面</p></td>
</tr>
<tr class="odd">
<td><p>REMOTE_ASSISTANCE</p></td>
<td><p>4</p></td>
</tr>
<tr class="even">
<td><p>APP_SHARING</p></td>
<td><p>個</p></td>
</tr>
<tr class="odd">
<td><p>オーディオトランジション</p></td>
<td><p>16</p></td>
</tr>
<tr class="even">
<td><p>ビデオ</p></td>
<td><p>32</p></td>
</tr>
<tr class="odd">
<td><p>APP_INVITE</p></td>
<td><p>64</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>User1Flag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>User1 属性を示すビットセット。 次の属性定義が表示されます。</p>
<ul>
<li><p>0x01-デスクトップ電話と統合</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>User2Flag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>User2 の属性を示すビットセット。 次の属性定義が表示されます。</p>
<ul>
<li><p>0x01-デスクトップ電話と統合</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>呼び出し属性を示すビットセット。 次の属性定義が表示されます。</p>
<ul>
<li><p>0x01-再試行セッション</p></li>
<li><p>0x02-応答グループの代理としてエージェントによって発信された通話</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>処理</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>監視サービスで内部的に使用されます。</p>
<p>このフィールドは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>


\*ほとんどのセッションでは、SessionIdSeq の値は1になります。 複数のセッションが同時に開始された場合は、1つのセッションの SessionIdSeq は1、それ以外の場合は2となります。

</div>

<span> </span>

</div>

</div>

</div>

