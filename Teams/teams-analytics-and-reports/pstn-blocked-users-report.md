---
title: MICROSOFT TEAMS PSTN ブロックされたユーザー レポート
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
MS.collection:
- M365-voice
description: Microsoft Teams管理センターの PSTN ブロックユーザー レポートを使用して、PSTN 通話をブロックされている組織のTeams ユーザーの概要を確認します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e648bb8a9158df4fac655324dee4e9365b51fefc
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62419350"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>MICROSOFT TEAMS PSTN ブロックされたユーザー レポート

Microsoft Teams管理センターの PSTN ブロックされたユーザー レポートには、組織内でTeamsで PSTN 通話をブロックされているユーザーが表示されます。 割り当てられた電話番号や通話をブロックした理由など、ブロックされた各ユーザーに関する詳細情報を表示できます。

## <a name="view-the-pstn-blocked-users-report"></a>PSTN ブロックされたユーザー レポートを表示する

Microsoft Teams 管理センターの左側のナビゲーションで、**[分析 & レポート]** > **[使用状況レポート]** をクリックします。 [ **レポートの表示** ] タブの [ **レポート**] で、[ **PSTN でブロックされたユーザー**] を選択し、[ **レポートの実行**] をクリックします。

![管理センターの PSTN ブロックされたユーザー レポート レポートのスクリーンショット。](../media/teams-reports-pstn-blocked-users-with-callouts.png "Microsoft Teams管理センターの PSTN ブロックされたユーザー レポートのスクリーンショット(番号付き吹き出しあり)")

## <a name="interpret-the-report"></a>レポートを解釈する

|Callout |説明  |
|--------|-------------|
|**1**   |各レポートには、それが生成された日付が表示されます。通常、レポートはアクティビティの時刻から 24 から 48 時間の遅延を反映します。 |
|**2**   |X 軸は日付です。 Y 軸はユーザーの数です。 <br>特定の日付のドットにマウス ポインターを合わせると、その日付にブロックされたユーザーの数が表示されます。 |
|**3**   |この表では、PSTN 通話をブロックされているすべてのユーザーの内訳を示します。  電話システムまたは電話会議が割り当てられているすべてのユーザーが表示され、各ユーザーに関する詳細情報が表示されます。 <ul><li>**表示名** はユーザーの表示名です。 表示名をクリックして、Microsoft Teams 管理センターのユーザーの設定ページに移動することができます。 </li> <li>**電話** は、ユーザーに割り当てられている番号です。</li> <li>**ブロックされた理由** は、ユーザーが通話をブロックされている理由です。</li><li>**ブロックされたアクション** は、ユーザーがTeamsで PSTN 通話を行うのをブロックされているかブロック解除されているかを示します。</li> <li>**ブロックされた時刻** は、ユーザーが通話をブロックされた日時 (UTC) です。</li></li> </ul>表に希望する情報を表示するには、表に列を追加する必要があります。 |
|**4**   |[**列の編集**] を選択して表で列を追加または削除します。|
|**5**   |[**全画面**] を選択すると、レポートが全画面モードで表示されます。|

## <a name="related-topics"></a>関連項目

- [Teams の分析とレポート](teams-reporting-reference.md)