---
title: 'Lync Server 2013: 診断レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Diagnostic Report
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48185159
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57d62e5938fd2d3b3d6966410a99e2f2e106325f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="diagnostic-report-in-lync-server-2013"></a>Lync Server 2013 の診断レポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-07_

診断レポートは、エラーが発生したセッションの診断とトラブルシューティングの情報を提供します。 この情報には、診断 ID と、セッションが失敗したときに報告された診断ヘッダーの両方が含まれます。 診断 ID は、SIP メッセージに関連付けられた一意の識別子 (ms diagnostics ヘッダーの形式) ですが、診断ヘッダーは診断 ID に関する説明を提供します。 レポートには、レポートコンポーネントによって知られる重要なトラブルシューティングの詳細が含まれていることもあります。 次に例を示します。

  - エラーを生成した PSTN ゲートウェイによって提供された原因コード。発信通話が PSTN ネットワークで失敗すると、ISDN User Part (ISUP) の原因コードが自動的に生成されます。たとえば、PSTN ゲートウェイは原因コード 34 を送信して、通話を完了するための使用可能な回線またはチャネルが存在しないことを示す場合があります。

  - 接続エラーのピアの FQDN、ポート、および Winsock エラー。

  - DNS 解決エラーで検索されている名前。DNS 解決は、クライアントがネーム サーバーに問い合わせ、指定されたデバイス名に対応する IP アドレスを要求するときにいつでも実行されます。

<div>

## <a name="accessing-the-diagnostic-report"></a>診断レポートへのアクセス

診断レポートには、 [Lync Server 2013 のピアツーピアセッション詳細レポート](lync-server-2013-peer-to-peer-session-detail-report.md)または会議詳細レポートで [診断レポート (詳細)] 指標をクリックするとアクセスできます。

</div>

<div>

## <a name="filters"></a>フィルター

なし。診断レポートにフィルターを適用することはできません。

</div>

<div>

## <a name="metrics"></a>指標

次の表に、診断レポートで提供されるセッションごとの情報を示します。

### <a name="diagnostic-report-metrics"></a>診断レポートの指標

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名前</th>
<th>この項目での並べ替え</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>レポート時刻</strong></p></td>
<td><p>いいえ</p></td>
<td><p>レポートが記録された日時。</p></td>
</tr>
<tr class="even">
<td><p><strong>応答コード</strong></p></td>
<td><p>いいえ</p></td>
<td><p>セッションが失敗したときに送信された SIP 応答コード。</p></td>
</tr>
<tr class="odd">
<td><p><strong>要求の種類</strong></p></td>
<td><p>いいえ</p></td>
<td><p>失敗した SIP 要求の種類 (INVITE、BYE、SERVICE など)。</p></td>
</tr>
<tr class="even">
<td><p><strong>Source</strong></p></td>
<td><p>いいえ</p></td>
<td><p>エラーのソース。</p></td>
</tr>
<tr class="odd">
<td><p><strong>送信元ユーザー URI</strong></p></td>
<td><p>いいえ</p></td>
<td><p>セッションを開始したユーザーの SIP アドレス。</p></td>
</tr>
<tr class="even">
<td><p><strong>送信元ユーザー エージェント</strong></p></td>
<td><p>いいえ</p></td>
<td><p>セッションを開始したユーザーのエンドポイントで使用されているソフトウェア。</p></td>
</tr>
<tr class="odd">
<td><p><strong>診断 ID</strong></p></td>
<td><p>いいえ</p></td>
<td><p>エラーのトラブルシューティングに役立つ情報を得られることが多い、SIP メッセージに添付された一意の識別子です (ms-diagnostics ヘッダーの形式)。</p></td>
</tr>
<tr class="even">
<td><p><strong>コンテンツの種類</strong></p></td>
<td><p>いいえ</p></td>
<td><p>失敗したメディア コンテンツの種類。たとえば、よく使われるコンテンツの種類は Application/sdp です。セッション記述プロトコル (SDP) は、セッションのアナウンス、セッションの招待、その他のマルチメディア セッション開始形式で使われる標準インターネット プロトコルです。</p></td>
</tr>
<tr class="odd">
<td><p><strong>アプリケーション</strong></p></td>
<td><p>いいえ</p></td>
<td><p>エラーに関係するアプリケーション。</p></td>
</tr>
<tr class="even">
<td><p><strong>送信先ユーザー URI</strong></p></td>
<td><p>いいえ</p></td>
<td><p>セッションに招待されたユーザーの SIP アドレス。</p></td>
</tr>
<tr class="odd">
<td><p>会議参加時間 (ミリ秒)</p></td>
<td><p>いいえ</p></td>
<td><p>ユーザーが会議に参加するのにかかった時間 (ミリ秒)。</p></td>
</tr>
<tr class="even">
<td><p><strong>診断ヘッダー</strong></p></td>
<td><p>いいえ</p></td>
<td><p>診断 ID の説明。</p></td>
</tr>
</tbody>
</table>


診断エラーの一覧については、「 [Ms Diagnostics Header」ページ](http://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx)を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

