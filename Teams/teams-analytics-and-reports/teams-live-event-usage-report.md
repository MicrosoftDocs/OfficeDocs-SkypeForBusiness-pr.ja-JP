---
title: Microsoft Teams のライブイベントの使用状況レポート
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Teams 管理センターで Teams live イベントの利用状況レポートを使用して、組織内の Teams live イベントアクティビティの概要を確認する方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f9b25fa7c476c9dd3fe347af26fc13742b41d009
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583766"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Microsoft Teams のライブイベントの使用状況レポート

Microsoft Teams 管理センターの [チームライブイベントの利用状況] レポートには、組織内で保持されているライブイベントのアクティビティの概要が表示されます。 イベントの状態、開始時刻、ビュー、および各イベントの生産タイプなどの使用状況情報を表示できます。 利用状況の傾向を把握して、組織内のユーザーがスケジュール、表示、ライブイベントを行うことができます。

## <a name="view-the-live-event-usage-report"></a>ライブイベントの利用状況レポートを表示する

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[分析およびレポート]** > **[使用状況レポート]** をクリックします。 [**レポートの表示**] タブの [**レポート**] で、[**チームライブイベントの利用状況**] を選択します。
2. [**日付範囲**] で、定義済みの範囲を選ぶか、ユーザー設定の範囲を設定します。 日付の範囲を設定して、現在の日付の前と後の6か月前までのデータを表示することができます。
3. 省略[**構成内容**変更] で、特定のユーザーによって開催されるライブイベントのみを表示するように選択できます。
4. [**レポートの実行**] をクリックします。  

    ![吹き出しが含まれる Teams 管理センターのチームライブイベントの使用状況レポートのスクリーンショット](../media/teams-live-event-usage-report-with-callouts.png "吹き出しが含まれる Teams 管理センターのチームライブイベントの使用状況レポートのスクリーンショット")

## <a name="interpret-the-report"></a>レポートを解釈する

|Callout |説明  |
|--------|-------------|
|**1**   |[チームライブ] イベントレポートでは、過去7日間、28日間、または設定したユーザー設定の日付範囲の傾向を確認できます。 |
|**2**   |各レポートには、生成された日付が含まれています。 レポートには、ページが更新されると、ほぼリアルタイムのアクティビティが反映されます。 |
|**3**   |<ul><li>グラフ上の X 軸はこのレポートで選択した日付範囲です。</li> <li> Y 軸は、ビューの合計数です。</li> </ul>特定の日付のドットの上にマウスポインターを移動すると、その日付のすべてのライブイベントのビュー数が表示されます。|
|**4**   |表を使用すると、各ライブイベントの内訳が示されます。 <ul><li>**イベント**は、ライブイベントの表示名です。 イベント名をクリックすると、イベントの[詳細が表示](#view-event-details)されます。 </li> <li>[**開始時刻**] は、イベントの開始日時を指します。</li> <li>**イベントの状態**は、イベントが発生したかどうかを示します。  </li><li>[**開催者**名は、イベントの開催者の名前です。</li> <li>**プレゼンター**は、イベントプレゼンターの名前です。</li><li>**プロデューサー**は、イベントプロデューサーの名前です。</li><li>**ビュー**には、固有のビューの数が表示されます。</li><li>[**レコーディング**] レコーディングの設定がオンになっているかオフになっているかを表示します。</li><li>[**生産の種類**の場合、イベントがチームで生成されるか、外部アプリケーションまたはデバイスによって生成されるかが示されます。</li></li> </ul>ユーザー アカウントが Azure AD に存在しなくなった場合は、ユーザー名がテーブルに "--" として表示されます。 <br><br>表に希望する情報を表示するには、表に列を追加する必要があります。 |
|**5**   |[**列の編集**] を選択して表で列を追加または削除します。|

## <a name="notes"></a>メモ
現在のレポートの条件に一致する最大100のライブイベントを表示します。 他のライブイベントを表示するには、日付フィルターを適用して、リストのサイズを小さくします。

## <a name="view-event-details"></a>イベントの詳細を表示する

[ライブイベントの詳細] ページには、ライブイベントの詳細情報の概要が表示され、イベントに関連付けられた議事録とレコーディングを含むすべてのファイルが一覧表示されます。 ファイル名をクリックして、ファイルを表示またはダウンロードします。

![ライブイベントの詳細を示すスクリーンショット](../media/teams-live-event-usage-report-event-detail.png)

組織で[Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/) ecdn または[Kollective](https://kollective.com) ecdn が有効になっている場合は、パートナーレポートのリンクをクリックして、追加の出席者の分析を取得できます。

## <a name="related-topics"></a>関連トピック

- [Teams の分析とレポート](teams-reporting-reference.md)
- [Teams のライブ イベントについて](../teams-live-events/what-are-teams-live-events.md)
