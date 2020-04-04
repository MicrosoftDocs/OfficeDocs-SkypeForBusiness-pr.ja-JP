---
title: Microsoft Teams PSTN ブロックユーザーレポート
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Microsoft Teams 管理センターの PSTN ブロックユーザーレポートを使用して、PSTN 通話の発信をブロックされている組織の Teams ユーザーの概要を把握します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e6055533138f08bafbdc9c39b03350612075840f
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140688"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Microsoft Teams PSTN ブロックユーザーレポート

Microsoft Teams 管理センターの PSTN ブロックユーザーレポートには、Teams で PSTN 通話の発信をブロックされている組織内のユーザーが表示されます。 ブロックされたユーザーについての詳細を表示できます。割り当てられた電話番号や、着信がブロックされた理由などです。

## <a name="view-the-report"></a>レポートを表示する

Microsoft Teams 管理センターの左のナビゲーションで、[**分析] & [レポート** > の**利用状況レポート**] をクリックします。 [レポートの**表示**] タブの [**レポート**] で、[ **PSTN ブロックユーザー**] を選択し、[**レポートの実行**] をクリックします。

![管理センターの PSTN ブロックユーザーレポートレポートのスクリーンショット](../media/teams-reports-pstn-blocked-users-with-callouts.png "番号付き吹き出しが含まれる Microsoft Teams 管理センターの PSTN ブロックユーザーレポートのスクリーンショット")

## <a name="interpret-the-report"></a>レポートを解釈する

|コールアウト |説明  |
|--------|-------------|
|**1**   |各レポートには、生成された日付が含まれています。 通常、レポートはアクティビティの時刻から 24 ～ 48 時間の遅延を反映します。 |
|**2**   |X 軸は日付です。 Y 軸はユーザーの数です。 <br>特定の日付のドットの上にマウスポインターを移動すると、その日付でブロックされたユーザーの数が表示されます。 |
|**3**   |この表は、PSTN 通話の発信をブロックされているすべてのユーザーの内訳を示しています。  電話システムまたは電話会議が割り当てられているすべてのユーザーが表示され、各ユーザーについての情報が提供されます。 <ul><li>[**表示名**はユーザーの表示名です。 表示名をクリックすると、Microsoft Teams 管理センターのユーザーの設定ページに移動できます。 </li> <li>[**電話**番号」は、ユーザーに割り当てられている番号です。</li> <li>**ブロック**された理由は、ユーザーが通話を発信できない理由です。</li><li>**ブロック**されたアクションは、チームで PSTN 通話を発信またはブロック解除するかどうかを示します。</li> <li>[ブロックされた**時間**] は、ユーザーが発信をブロックされた日付と時刻 (UTC) です。</li></li> </ul>表に希望する情報を表示するには、表に列を追加する必要があります。 |
|**4**   |[**列の編集**] を選択して表で列を追加または削除します。|
|**5**   |全画面表示モードでレポートを表示するには、[**全画面**表示] を選択します。|

## <a name="related-topics"></a>関連項目

- [Teams の分析とレポート](teams-reporting-reference.md)