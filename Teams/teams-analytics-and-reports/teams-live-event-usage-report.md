---
title: Microsoft Teams ライブ イベントの使用状況レポート
author: CarolynRowe
ms.author: crowe
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Teams 管理センターの Teams ライブ イベント使用状況レポートを使用して、組織内の Teams ライブ イベント アクティビティの概要を確認する方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 29a255c9248f07db00d4295e99d4062116ca4e76
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794095"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Microsoft Teams ライブ イベントの使用状況レポート

Microsoft Teams 管理センターの Teams ライブ イベント使用状況レポートには、組織で開催されているライブ イベントのアクティビティの概要が表示されます。 イベントの状態、開始時刻、ビュー、各イベントの運用の種類など、使用状況情報を表示できます。 使用状況の傾向に関する分析情報を得て、組織内の誰がライブ イベントをスケジュール、プレゼンテーション、および生成したかを確認できます。

## <a name="view-the-live-event-usage-report"></a>ライブ イベント使用状況レポートを表示する

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[分析 & レポート]** > **[使用状況レポート]** をクリックします。 [ **レポートの表示** ] タブの [ **レポート**] で、[ **Teams ライブ イベントの使用状況**] を選択します。
2. **[日付範囲**] で、定義済みの範囲を選択するか、カスタム範囲を設定します。 現在の日付の前後の 1 年、6 か月後にデータを表示するように範囲を設定できます。
3. (省略可能) **[開催者]** で、特定のユーザーが編成したライブ イベントのみを表示するように選択できます。
4. [ **レポートの実行]** をクリックします。  

   :::image type="content" alt-text="Teams 管理センターの Teams ライブ イベント使用状況レポートと吹き出しのスクリーンショット。" source="../media/teams-live-event-usage-report-with-callouts.png" lightbox="../media/teams-live-event-usage-report-with-callouts.png":::

## <a name="interpret-the-report"></a>レポートを解釈する

|Callout |説明  |
|--------|-------------|
|**1**   |Teams ライブ イベント レポートは、過去 7 日間、28 日間、または設定したカスタム日付範囲の傾向を確認できます。 |
|**2**   |各レポートには、生成された日付が含まれます。 レポートは、ページが更新されたときにほぼリアルタイムのアクティビティを反映します。 |
|**3**   |<ul><li>グラフ上の X 軸はこのレポートで選択した日付範囲です。</li> <li> Y 軸は、ビューの合計数です。</li> </ul>特定の日付のドットにマウス ポインターを合わせると、その日付のすべてのライブ イベントのビュー数が表示されます。|
|**4**   |この表では、各ライブ イベントの内訳を示します。 <ul><li>**イベント** は、ライブ イベントの表示名です。 イベント名をクリックすると、イベントの [詳細が表示](#view-event-details) されます。 </li> <li>**開始時刻** は、イベントの開始日と時刻を参照します。</li> <li>**イベントの状態** は、イベントが発生したかどうかを示します。  </li><li>**開催者** は、イベント開催者の名前です。</li> <li>**発表者** は、イベント発表者の名前です。</li><li>**プロデューサー** は、イベント プロデューサーの名前です。</li><li>**ビュー** は、イベントが完了した後の一意のビューの数です。</li><li>**記録** は、記録設定がオンかオフかを示します。</li><li>**運用の種類** は、イベントが Teams で生成されるか、外部アプリケーションまたはデバイスによって生成されるかを示します。</li></li> </ul>ユーザー アカウントが Azure AD に存在しなくなった場合は、ユーザー名がテーブルに "--" として表示されます。 <br><br>表に希望する情報を表示するには、表に列を追加する必要があります。 |
|**5**   |[**列の編集**] を選択して表で列を追加または削除します。|

## <a name="notes"></a>メモ
現在のレポートの条件に一致する最大 100 のライブ イベントが表示されます。 その他のライブ イベントを表示するには、日付フィルターを適用してリスト サイズを小さくします。

匿名発表者はレポートに含まれません。

イベントまたはオンデマンドイベントの記録を視聴した人は、ビュー数に含まれません。 

## <a name="view-event-details"></a>イベントの詳細を表示する

ライブ イベントの詳細ページには、ライブ イベントの詳細の概要が表示され、イベントに関連付けられているトランスクリプトやレコーディングを含むすべてのファイルが一覧表示されます。 ファイル名をクリックして、ファイルを表示またはダウンロードします。

:::image type="content" alt-text="ライブ イベントの詳細を示すスクリーンショット。" source="../media/teams-live-event-usage-report-event-detail.png" lightbox="../media/teams-live-event-usage-report-event-detail.png":::

組織で [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/) eCDN または [Kollective](https://kollective.com) eCDN が有効になっている場合は、パートナー レポートのリンクをクリックすると、出席者分析を追加できます。

## <a name="related-topics"></a>関連項目

- [Teams の分析とレポート](teams-reporting-reference.md)
- [Teams のライブ イベントについて](../teams-live-events/what-are-teams-live-events.md)
