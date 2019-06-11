---
title: 'Lync Server 2013: エラー一覧レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failure List Report
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615446(v=OCS.15)
ms:contentKeyID: 48185194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32c1c9c15b1f539aa1a5213989674dfea268a684
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a>Lync Server 2013 のエラーリストレポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-07-02_

エラー リスト レポートは、エラーが発生したピアツーピア セッションまたは電話会議セッションに参加した個々の参加者に関する情報を提供します。この情報には、問題が発生したユーザーの URI、エラーに関連付けられている SIP 応答コードおよび診断 ID が含まれています。

<div>

## <a name="accessing-the-failure-list-report"></a>エラー リスト レポートへのアクセス

[エラー一覧] レポートにアクセスするには、「 [Lync Server 2013 のエラー配布レポート](lync-server-2013-failure-distribution-report.md)で、次のいずれかの指標をクリックします。

  - トップの診断理由 (セッション)

  - トップのモダリティ (セッション)

  - トップのプール (セッション)

  - トップのソース (セッション)

  - トップのコンポーネント (セッション)

  - トップの発信元ユーザー (セッション)

  - トップの発信先ユーザー (セッション)

  - トップの発信元ユーザー エージェント (セッション)

[エラー一覧] レポートから、Lync Server 2013 のピアツーピア[セッション詳細レポート](lync-server-2013-peer-to-peer-session-detail-report.md)にアクセスできます。これには、ピアツーピアセッションのセッション詳細メトリックをクリックします。 また、電話会議の [電話会議] の指標をクリックすると、会議詳細レポートにもアクセスできます。

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a>エラー リスト レポートの活用

エラー リスト レポートでは、マウス ポインターを値の上に置くだけで、それぞれの応答コードまたは診断 ID の説明を表示できます。たとえば、診断 ID 7025 の上にマウス ポインターを置くと、次のような説明がヒントに表示されます。

ユーザーのメディアの作成中に内部サーバー エラーが発生しました。

障害リストレポートでは、1つ以上のセッションに参加しているすべてのユーザーの一覧を直接取得する方法はありません。また、どのユーザーが失敗したかを判断する方法も提供されていない点に注意してください。セッション. (1 つの問題については、エラーリストレポートにはフィルター機能はありません)。ただし、データをエクスポートして、コンマ区切り値ファイルに変換した場合は、Windows PowerShell を使用して、そのような質問に対する回答を見つけることができます。 たとえば、データをに保存するとします。CSV ファイル名 C:\\データ\\エラー\_リスト .csv。 このコマンドは、そのファイルに保存されているデータに基づいて、1つ以上の失敗したセッションに参加していたすべてのユーザーを一覧表示します。

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

このコマンドを実行すると、次のような一覧が返されます。

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

次の 2 つのコマンドは、各ユーザーが参加した、エラーが発生したセッションの総数についてレポートします。

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

この結果、次のようなデータが返されます。

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a>フィルター

なし。エラー リスト レポートにフィルターを適用することはできません。

</div>

<div>

## <a name="metrics"></a>指標

次の表に、失敗した呼び出しごとにエラー リスト レポートで提供される情報を示します。

### <a name="failure-list-report-metrics"></a>エラー リスト レポートの指標

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
<td><p><strong>レポートされた時刻</strong></p></td>
<td><p>いいえ</p></td>
<td><p>レポートが記録された日時。</p></td>
</tr>
<tr class="even">
<td><p><strong>要求</strong></p></td>
<td><p>いいえ</p></td>
<td><p>失敗した SIP 要求の種類 (INVITE、BYE など)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>応答コード</strong></p></td>
<td><p>いいえ</p></td>
<td><p>会議にエラーが発生したときに送信された SIP 応答コード。</p></td>
</tr>
<tr class="even">
<td><p><strong>診断 ID</strong></p></td>
<td><p>いいえ</p></td>
<td><p>SIP メッセージに (ms-diagnostics ヘッダーの形で) 添付された一意の識別子。多くの場合、この情報はトラブルシューティングに役立ちます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>参加コスト時間 (ミリ秒)</strong></p></td>
<td><p>いいえ</p></td>
<td><p>ユーザーが会議に参加するのに要した時間 (ミリ秒)。</p></td>
</tr>
<tr class="even">
<td><p><strong>移動元ユーザー</strong></p></td>
<td><p>いいえ</p></td>
<td><p>呼び出しを開始したユーザーの SIP アドレス。</p></td>
</tr>
<tr class="odd">
<td><p><strong>送信元ユーザー エージェント</strong></p></td>
<td><p>いいえ</p></td>
<td><p>呼び出しを開始したユーザーのエンドポイントで使用されているソフトウェア。</p></td>
</tr>
<tr class="even">
<td><p><strong>対象ユーザー</strong></p></td>
<td><p>不可</p></td>
<td><p>呼び出しを受けたユーザーの SIP アドレス。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

