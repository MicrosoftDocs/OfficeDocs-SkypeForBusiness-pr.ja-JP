---
title: 'Lync Server 2013: セッションの詳細ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bd3902fd35679366e905c04e99ff1e72b2ece86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a>Lync Server 2013 のセッション詳細表示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-01_

セッション詳細ビューには、VoIP 電話、2パーティの IM セッション、その他の種類のセッションなど、ピアツーピアセッションに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。


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
<td><p><strong>セッション Id</strong></p></td>
<td><p>datetime</p></td>
<td><p>セッション要求の時刻。 セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 テーブルのダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>セッションを識別する ID 番号。 セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>最初の招待要求の時刻。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>セッションを開始したユーザーの URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>セッションに参加したユーザーの URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションを開始したユーザーの URI の種類。 詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションに参加したユーザーの URI の種類。 詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>セッションを開始したユーザーのテナント。 詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>すべての Ant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションに参加したユーザーのテナント。 詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromEndpointId</strong></p></td>
<td><p>長さ</p></td>
<td><p>セッションを開始したユーザーのエンドポイントを表す一意の識別子です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToEndpointId</strong></p></td>
<td><p>長さ</p></td>
<td><p>セッションに参加したユーザーのエンドポイントを表す一意の識別子です。</p></td>
</tr>
<tr class="even">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>セッションの終了時刻。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMessageCount</strong></p></td>
<td><p>int</p></td>
<td><p>セッションを開始したユーザーによって送信されたメッセージの数です。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMessageCount</strong></p></td>
<td><p>int</p></td>
<td><p>セッションに参加したユーザーによって送信されたメッセージの数です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションを開始したユーザーによって使用されたクライアントのバージョン。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromClientType</strong></p></td>
<td><p>int</p></td>
<td><p>セッションを開始したユーザーによって使用されたクライアント。 詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>セッションを開始したユーザーによって使用されたクライアントのカテゴリの名前です。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションに参加したユーザーによって使用されたクライアントのバージョン</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToClientType</strong></p></td>
<td><p>int</p></td>
<td><p>セッションに参加したユーザーによって使用されたクライアント。 詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>セッションに参加したユーザーによって使用されたクライアントのカテゴリの名前です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>TargetUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>セッションのターゲットユーザーの URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>TargetUriType</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>セッションのターゲットユーザーの URI の種類です。 詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>セッションが開始されたユーザーの URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>OnnnBehalfOfUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションが開始されたユーザーの URI の種類。 詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションを開始したユーザーのテナント。 詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>△この Uri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>セッションを参照したユーザーの URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ベンチャー Redbyuritん</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションを参照したユーザーの URI の種類。 詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>このテナント</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションを参照したユーザーのテナント。 詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>この Id</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>SIP ダイアログ ID。 形式は次のとおりです。</p>
<p>ダイアログ; 開始タグからタグへ</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationId</strong></p></td>
<td><p>長さ</p></td>
<td><p>複数のセッションの関連付けに使用する GUID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Edialogidtime の置き換え</strong></p></td>
<td><p>datetime</p></td>
<td><p>セッションによって置き換えられたダイアログの時間です。 セッションによって置き換えられるダイアログを一意に識別するには、置換 Edialogidseq と組み合わせて使います。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>Edialogidseq の置き換え</strong></p></td>
<td><p>int</p></td>
<td><p>セッションを識別する ID 番号。 セッションによって置き換えられるダイアログを一意に識別するために、交換 Edialogidtime と組み合わせて使います。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>置換の方法 Id</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>SIP ダイアログ ID によってセッションが置き換えられます。 形式は次のとおりです。</p>
<p>ダイアログ; 開始タグからタグへ</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>最初の招待メッセージに対する返信の時刻。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</p></td>
</tr>
<tr class="odd">
<td><p><strong>返信</strong></p></td>
<td><p>int</p></td>
<td><p>セッション招待状への SIP 応答コード。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p>SIP ヘッダーからキャプチャされた診断 ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションのコンテンツの種類です。</p></td>
</tr>
<tr class="even">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションのデータをキャプチャしたフロントエンドサーバーの FQDN。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションのデータをキャプチャしたプールの FQDN。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromEdgeServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションを開始したユーザーによって使用されたエッジサーバーの FQDN。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToEdgeServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションを開始したユーザーによって使用されたエッジサーバーの FQDN</p></td>
</tr>
<tr class="even">
<td><p><strong>IsFromInternal</strong></p></td>
<td><p>bit</p></td>
<td><p>セッションを開始したユーザーが内部ネットワークからログオンしているかどうかを示します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsToInternal</strong></p></td>
<td><p>bit</p></td>
<td><p>セッションに参加したユーザーが内部ネットワークからログオンしているかどうかを示します。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションの通話優先度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUserFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>セッションを開始したユーザーの属性を示します。 次の属性定義を使用できます。</p>
<p>0x01-デスクトップ電話と統合</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUserFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>セッションを開始したユーザーの属性を示します。 次の属性定義を使用できます。</p>
<p>0x01-デスクトップ電話と統合</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>呼び出しの属性を示します。 次の属性定義を使用できます。</p>
<p>0x01-再試行セッション</p>
<p>0x02-応答グループの代理としてエージェントによって発信された通話</p></td>
</tr>
<tr class="even">
<td><p><strong>場所</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>緊急通話の場所。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

