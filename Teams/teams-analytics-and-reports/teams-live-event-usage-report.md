---
title: Microsoft Teams のライブ イベント使用状況レポート
author: cichur
ms.author: v-cichur
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
description: Microsoft Teams 管理センターで Teams ライブ イベント使用状況レポートを使用して、組織内の Teams ライブ イベント アクティビティの概要を取得する方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 971e9bc846ad1a7134c1877a1716fc535ae65e4d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809287"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Microsoft Teams のライブ イベント使用状況レポート

Microsoft Teams 管理センターの Teams ライブ イベント使用状況レポートには、組織内で開催されたライブ イベントのアクティビティの概要が表示されます。 各イベントの利用状況情報 (イベントの状態、開始時刻、ビュー、実稼働の種類など) を表示できます。 使用状況の傾向を把握し、組織内の誰がライブ イベントのスケジュール、発表、作成を行うのか確認できます。

## <a name="view-the-live-event-usage-report"></a>ライブ イベントの使用状況レポートを表示する

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[分析 & レポート]** > **[使用状況レポート]** をクリックします。 [レポート **の表示] タブの** [ **レポート] で、[Teams** ライブ **イベントの使用状況] を選択します**。
2. [ **日付範囲] で**、定義済みの範囲を選択するか、ユーザー設定の範囲を設定します。 範囲を設定して、現在の日付の 6 か月前と後に最大 1 年のデータを表示できます。
3. (省略可能)[ **開催者**] で、特定のユーザーが開催したライブ イベントのみを表示することができます。
4. [レポートの **実行] をクリックします**。  

    ![吹き出し付き Teams 管理センターの Teams ライブ イベント使用状況レポートのスクリーンショット](../media/teams-live-event-usage-report-with-callouts.png "吹き出し付き Teams 管理センターの Teams ライブ イベント使用状況レポートのスクリーンショット")

## <a name="interpret-the-report"></a>レポートを解釈する

|Callout |説明  |
|--------|-------------|
|**1**   |Teams のライブ イベント レポートでは、過去 7 日間、28 日間、または設定したユーザー設定の日付範囲の傾向を確認できます。 |
|**2**   |各レポートには、生成された日付が含されます。 レポートには、ページが更新された場合のほぼリアルタイムのアクティビティが反映されます。 |
|**3**   |<ul><li>グラフ上の X 軸はこのレポートで選択した日付範囲です。</li> <li> Y 軸は、ビューの総数です。</li> </ul>特定の日付のドットの上にマウス ポインターを置くと、その日付のすべてのライブ イベントのビュー数が表示されます。|
|**4**   |この表は、各ライブ イベントの内訳を示しています。 <ul><li>**イベント** はライブ イベントの表示名です。 イベント名をクリックすると、 [イベントの詳細](#view-event-details) が表示されます。 </li> <li>**[開始時刻** ] は、イベントの開始日と時刻を参照します。</li> <li>**イベントの状態** は、イベントが発生したかどうかを示します。  </li><li>**開催** 者は、イベント 開催者の名前です。</li> <li>**発表者** は、イベントの発表者の名前です。</li><li>**プロデューサーは** 、イベント プロデューサーの名前です。</li><li>**ビュー** は、イベントが完了した後の一意のビューの数です。</li><li>**記録** は、記録設定がオンかオフかを示します。</li><li>**実稼働の** 種類は、イベントが Teams で生成されたのか、外部アプリケーションまたはデバイスによって生成されたのかを示します。</li></li> </ul>ユーザー アカウントが Azure AD に存在しなくなった場合は、ユーザー名がテーブルに "--" として表示されます。 <br><br>表に希望する情報を表示するには、表に列を追加する必要があります。 |
|**5**   |[**列の編集**] を選択して表で列を追加または削除します。|

## <a name="notes"></a>備考
現在のレポートの条件に一致する最大 100 のライブ イベントが表示されます。 その他のライブ イベントを表示するには、日付フィルターを適用してリスト サイズを小さくします。

## <a name="view-event-details"></a>イベントの詳細を表示する

ライブ イベントの詳細ページには、ライブ イベントの詳細の概要が表示され、イベントに関連付けられているトランスクリプトやレコーディングを含むすべてのファイルが一覧表示されます。 ファイル名をクリックして、ファイルを表示またはダウンロードします。

![ライブ イベントの詳細を示すスクリーンショット](../media/teams-live-event-usage-report-event-detail.png)

組織で [ハイ](https://www.hivestreaming.com/partners/integration-partners/microsoft/) ブ eCDN または [Kollective](https://kollective.com) eCDN が有効になっている場合は、パートナー レポートのリンクをクリックして、追加の出席者分析を取得できます。

## <a name="related-topics"></a>関連項目

- [Teams の分析とレポート](teams-reporting-reference.md)
- [Teams のライブ イベントについて](../teams-live-events/what-are-teams-live-events.md)
