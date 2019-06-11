---
title: 'Lync Server 2013: ConferenceSessionDetails view'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0432606a49766f7ea6755f5f234343ac70ca6c0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a>Lync Server 2013 での ConferenceSessionDetails の表示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-12_

ConferenceSessionDetails ビューには、マルチパーティセッションに関する情報が格納されます。 各レコードは1つの会議セッションを表します。これは、フォーカスのあるセッションまたは特定の会議サーバーのセッションのいずれかになります。 このビューは、Microsoft Lync Server 2013 で導入されました。


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
<td><p>セッション要求の時刻。 セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>セッションを識別する ID 番号。 セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>最初の招待要求の時刻。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>会議の URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>電話会議 URI の種類。 詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>長さ</p></td>
<td><p>定期的な会議のインスタンスを区別する識別子。 各定期的な会議インスタンスの ConferenceURI は同じですが、異なる ConfInstance 値があります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>会議サーバーの URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>McuConferenceUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>会議サーバーの URI の種類。 詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>セッションに関連するユーザーの URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションの一部だったユーザーの URI の種類。 詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションの一部だったユーザーのテナント。 詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>長さ</p></td>
<td><p>セッションの一部だったユーザーの一意の識別子。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>セッションの終了時刻。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>会議サーバーのバージョン。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceClientType</strong></p></td>
<td><p>int</p></td>
<td><p>会議サーバーの種類。 詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>会議サーバーのカテゴリ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションに参加したユーザーによって使用されたクライアントのバージョン。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>セッションに参加したユーザーによって使用されたクライアント。 詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>セッションの一部だったユーザーによって使用されたクライアントのカテゴリの名前です。</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>セッションが開始されたユーザーの URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションが開始されたユーザーの URI の種類。 詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションを開始したユーザーのテナント。 詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>△この Uri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>セッションを参照したユーザーの URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>ベンチャー Redbyuritん</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションを参照したユーザーの URI の種類。 詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>、Uritbyuritenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションを参照したユーザーのテナント。 詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>この Id</strong></p></td>
<td><p>varstring (775)</p></td>
<td><p>SIP ダイアログ ID。 書式は</p>
<p>:d ialog; from タグ; to タグ</p></td>
</tr>
<tr class="odd">
<td><p><strong>Edialogidtime の置き換え</strong></p></td>
<td><p>datetime</p></td>
<td><p>現在のセッションによって置き換えられたダイアログを識別する ID 番号。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>Edialogidseq の置き換え</strong></p></td>
<td><p>int</p></td>
<td><p>セッションを識別する ID 番号。 このセッションによって置き換えられるセッションを一意に識別するには、置換 Edialogidtime と組み合わせて使います。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>置換の方法 Id</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>SIP ダイアログ ID によってセッションが置き換えられます。 の形式は次のとおりです。</p>
<p>ダイアログ; 開始タグからタグへ</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td><p>セッションが会議サーバーによって開始されたかどうかを示します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td><p>会議サーバーによってセッションが終了したかどうかを示します。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bit</p></td>
<td><p>ユーザーが内部ネットワークからログオンしているかどうかを示します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>最初の招待メッセージに対する返信の時刻。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</p></td>
</tr>
<tr class="even">
<td><p><strong>返信</strong></p></td>
<td><p>int</p></td>
<td><p>セッション招待状への SIP 応答コード。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p>セッション SIP ヘッダーからキャプチャされた診断 ID。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションのコンテンツタイプ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションのデータをキャプチャしたフロントエンドサーバーの FQDN。</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションのデータをキャプチャしたプールの FQDN。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションに参加したユーザーによって使用される仲介サーバー。</p></td>
</tr>
<tr class="even">
<td><p><strong>ゲートウェイ</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションに参加したユーザーが使用したゲートウェイ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションに参加したユーザーによって使用されたエッジサーバーの FQDN。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>セッションに参加したユーザーの属性を示します。 次の属性定義を使用できます。</p>
<p>0x01-デスクトップ電話と統合</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>呼び出しの属性を示します。 次の属性定義を使用できます。</p>
<p>0x01-再試行 Session0</p>
<p>x02-応答グループの代理としてエージェントによって発信された通話</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

