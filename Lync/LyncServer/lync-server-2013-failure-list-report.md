---
title: 'Lync Server 2013: エラーリストレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure List Report
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615446(v=OCS.15)
ms:contentKeyID: 48185194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 010e8314eb7d2cbb33354461bdc2a1eb2c5b2cf1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a>Lync Server 2013 のエラーリストレポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-07-02_

エラー リスト レポートは、エラーが発生したピアツーピア セッションまたは電話会議セッションに参加した個々の参加者に関する情報を提供します。この情報には、問題が発生したユーザーの URI、エラーに関連付けられている SIP 応答コードおよび診断 ID が含まれています。

<div>

## <a name="accessing-the-failure-list-report"></a>エラー リスト レポートへのアクセス

エラーリストレポートにアクセスするには、 [Lync Server 2013 のエラー分布レポート](lync-server-2013-failure-distribution-report.md)で次のいずれかの指標をクリックします。

  - [トップの診断理由] (セッション)

  - [トップ モダリティ] (セッション)

  - [トップ プール] (セッション))

  - [トップ ソース] (セッション))

  - [トップ コンポーネント] (セッション)

  - [トップの発信元ユーザー] (セッション)

  - [トップの発信先ユーザー] (セッション)

  - [送信元ユーザー エージェント] (セッション)

エラーリストレポートでは、ピアツーピアセッションのセッション詳細指標をクリックすることによって、 [Lync Server 2013 のピアツーピアセッション詳細レポート](lync-server-2013-peer-to-peer-session-detail-report.md)にアクセスできます。 また、電話会議の電話会議の指標をクリックすると、会議詳細レポートにもアクセスできます。

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a>エラー リスト レポートの活用

エラー リスト レポートでは、マウス ポインターを値の上に置くだけで、それぞれの応答コードまたは診断 ID の説明を表示することができます。たとえば、診断 ID 7025 の上にマウス ポインターを置くと、次の説明がツールチップに表示されます。

Internal server error creating media for user. (ユーザーのメディアの作成中に内部サーバー エラーが発生しました。)

エラーリストレポートには、少なくとも1つの失敗したセッションに参加したすべてのユーザーの一覧を直接取得する簡単な方法が提供されているわけではないことに注意してください。また、最も多く使用して失敗したユーザーを特定する方法も提供していません。セッション. (1 つは、エラーリストレポートにはフィルター機能がありません)。ただし、データをエクスポートしてからコンマ区切り値ファイルに変換する場合は、Windows PowerShell を使用して、これらの質問に対する答えを見つけることができます。 たとえば、データをに保存するとします。C:\\データ\\エラー\_リスト .csv という名前の csv ファイル。 このコマンドは、そのファイルに保存されているデータに基づいて、少なくとも1つの失敗したセッションに参加したすべてのユーザーを一覧表示します。

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

このコマンドにより、次にような一覧が返されます。

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

これにより、次のようなデータが返されます。

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

なし。エラー リスト レポートはフィルターできません。

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
<td><p>レポートが記録された日時です。</p></td>
</tr>
<tr class="even">
<td><p><strong>要求</strong></p></td>
<td><p>いいえ</p></td>
<td><p>失敗した SIP 要求の種類です (INVITE、BYE など)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>応答コード</strong></p></td>
<td><p>いいえ</p></td>
<td><p>会議にエラーが発生したときに送信された SIP 応答コードです。</p></td>
</tr>
<tr class="even">
<td><p><strong>診断 ID</strong></p></td>
<td><p>いいえ</p></td>
<td><p>エラーのトラブルシューティングに役立つ情報を得られることが多い、SIP メッセージに添付された一意の識別子です (ms-diagnostics ヘッダーの形式)。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>Join cost time (ms)</strong>] (参加に要した時間 (ミリ秒))</p></td>
<td><p>いいえ</p></td>
<td><p>ユーザーが会議に参加するのに要した時間 (ミリ秒)。</p></td>
</tr>
<tr class="even">
<td><p><strong>送信元ユーザー</strong></p></td>
<td><p>いいえ</p></td>
<td><p>呼び出しを開始したユーザーの SIP アドレスです。</p></td>
</tr>
<tr class="odd">
<td><p><strong>送信元ユーザー エージェント</strong></p></td>
<td><p>いいえ</p></td>
<td><p>呼び出しを開始したユーザーのエンドポイントで使用されているソフトウェアです。</p></td>
</tr>
<tr class="even">
<td><p><strong>送信先ユーザー</strong></p></td>
<td><p>いいえ</p></td>
<td><p>呼び出しを受けたユーザーの SIP アドレスです。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

