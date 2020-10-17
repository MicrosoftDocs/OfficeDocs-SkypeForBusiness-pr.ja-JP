---
title: 'Lync Server 2013: 電話会議の概要サブレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Subreport
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204779(v=OCS.15)
ms:contentKeyID: 48183742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ddbbe3fc546010e78ee7df6aa8afb083e594ea14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502324"
---
# <a name="conference-summary-subreport-in-lync-server-2013"></a>Lync Server 2013 の電話会議の概要サブレポート

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-06_

電話会議の概要サブレポートには、エラーが発生した電話会議セッションの概要が表示されます。これらのエラーが発生したセッションは、フォーカス セッションと MCU セッションというセッションの種類によって分類されます。

<div>

## <a name="filters"></a>フィルター

フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。次の表に、電話会議の概要サブレポートで使用できるフィルターを示します。

### <a name="conference-summary-subreport-filters"></a>電話会議の概要サブレポートのフィルター

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名前</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong></p></td>
<td><p>時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</p>
<p>7/7/2012 1:00 PM</p>
<p>開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</p>
<p>7/7/2012</p>
<p>週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</p>
<p>7/3/2012</p>
<p>週は、常に日曜日から土曜日までです。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</p>
<p>7/7/2012 1:00 PM</p>
<p>終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</p>
<p>7/7/2012</p>
<p>週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</p>
<p>7/3/2012</p>
<p>週は、常に日曜日から土曜日までです。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>レジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN)。個別のプールを選択するか、[<strong>すべて</strong>] をクリックしてすべてのプールのデータを表示できます。このドロップダウン リストは、データベース内のレコードに基づいて自動的に設定されます。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

次の表に、電話会議の概要サブレポートに表示される情報を示します。

### <a name="conference-summary-subreport-metrics"></a>電話会議の概要サブレポートの指標

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
<td><p>[<strong>電話会議の合計数</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>開催された電話会議の合計数です。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>電話会議セッションの合計数</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>電話会議セッションの合計数です。1 つの電話会議に複数のセッションが存在する場合があります。たとえば、1 つの電話会議にフォーカス セッションと MCU セッションの両方が含まれる場合があります。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>全体的なセッション エラー率</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>エラーが発生したすべての電話会議の割合です。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>フォーカス セッション</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>フォーカス セッションの合計数です。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>フォーカス エラー率</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>エラーが発生したフォーカス セッションの割合です。</p></td>
</tr>
<tr class="even">
<td><p>[MCU セッション]</p></td>
<td><p>いいえ</p></td>
<td><p>MCU セッションの合計数です。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>MCU エラー率</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>エラーが発生した MCU セッションの割合です。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>MCU セッション (モダリティ別)</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>モダリティ (IM 電話会議など) ごとにグループ化した、MCU セッションの合計数です。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>エラー率 (モダリティ別)</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>モダリティ (IM 電話会議など) ごとにグループ化した、エラーが発生した MCU セッションの割合です。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

