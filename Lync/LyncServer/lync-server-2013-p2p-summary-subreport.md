---
title: 'Lync Server 2013: P2P Summary サブレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: P2P Summary Subreport
ms:assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205416(v=OCS.15)
ms:contentKeyID: 48185950
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 345a659d3edfe8542391719ed4b90717b45a3c35
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="p2p-summary-subreport-in-lync-server-2013"></a>Lync Server 2013 の P2P 概要サブレポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-21_

P2P 概要サブレポートは、エラーが発生したピアツーピア セッションの総合的な概要を示します。

<div>

## <a name="filters"></a>フィルター

フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。次の表に、P2P 概要サブレポートで使用できるフィルターを示します。

### <a name="p2p-summary-subreport-filters"></a>P2P 概要サブレポートのフィルター

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

次の表に、P2P 概要サブレポートで提供される情報を示します。

### <a name="p2p-summary-subreport-metrics"></a>P2P 概要サブレポートの指標

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
<td><p>[<strong>セッションの合計数</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>セッションの総数です。成功したセッション、失敗したセッション (予期されるエラーと予期しないエラーの両方)、およびどちらにも分類されないセッションを含みます。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>エラー率</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>エラーが発生したピアツーピア セッションの割合です。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>モダリティ別セッション</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>モダリティによってグループ化されたセッションの合計数 (たとえば、インスタント メッセージング)。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>モダリティ別エラー率</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>モダリティによってグループ化された失敗したセッションの合計数 (たとえば、インスタント メッセージング)。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

