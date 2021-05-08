---
title: Microsoft TeamsPSTN ブロックユーザー レポート
author: cichur
ms.author: v-cichur
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
description: Microsoft Teams 管理センターで PSTN ブロックユーザー レポートを使用して、PSTN 通話がブロックされている組織のユーザー Teamsの概要を確認します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ed775c3796e40a775b3be2b78f22e162a047bf78
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809337"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Microsoft TeamsPSTN ブロックユーザー レポート

Microsoft Teams 管理センターの PSTN ブロックユーザー レポートには、組織内のユーザーが、TEAMS で PSTN 通話を行うのをブロックされているユーザーが表示されます。 割り当てられた電話番号や、通話がブロックされた理由など、ブロックされている各ユーザーの詳細を表示できます。

## <a name="view-the-pstn-blocked-users-report"></a>PSTN ブロックユーザー レポートを表示する

Microsoft Teams 管理センターの左側のナビゲーションで、**[分析 & レポート]** > **[使用状況レポート]** をクリックします。 [レポート **の表示] タブの** [レポート] **で**、[PSTN ブロックユーザー] を **選択し**、[レポートの実行] **をクリックします**。

![管理センターの PSTN ブロックユーザー レポート レポートのスクリーンショット](../media/teams-reports-pstn-blocked-users-with-callouts.png "番号付き吹き出しが表示された Microsoft Teams PSTN ブロック ユーザー レポートのスクリーンショット")

## <a name="interpret-the-report"></a>レポートを解釈する

|Callout |説明  |
|--------|-------------|
|**1**   |各レポートには、生成された日付があります。 通常、レポートはアクティビティの時刻から 24 ～ 48 時間の遅延を反映します。 |
|**2**   |X 軸は日付です。 Y 軸はユーザー数です。 <br>特定の日付のドットにマウス ポインターを合わせると、その日付にブロックされたユーザーの数が表示されます。 |
|**3**   |この表は、PSTN 通話をブロックしているすべてのユーザーの内訳を示しています。  このページには、電話会議または電話電話システム割り当てられているすべてのユーザーが表示され、各ユーザーに関する詳細が表示されます。 <ul><li>**表示名** はユーザーの表示名です。 表示名をクリックして、Microsoft Teams 管理センターのユーザーの設定ページに移動することができます。 </li> <li>**電話** は、ユーザーに割り当てられている番号です。</li> <li>**ブロックされる理由** は、ユーザーが呼び出しを行うのをブロックされる理由です。</li><li>**[ブロック] アクション** は、ユーザーが PSTN 通話を行うのをブロックまたはブロック解除されているかどうかを示Teams。</li> <li>**[ブロックされた時刻** ] は、ユーザーが呼び出しを行うのをブロックされた日時 (UTC) です。</li></li> </ul>表に希望する情報を表示するには、表に列を追加する必要があります。 |
|**4**   |[**列の編集**] を選択して表で列を追加または削除します。|
|**5**   |[ **全画面] を** 選択して、レポートを全画面モードで表示します。|

## <a name="related-topics"></a>関連トピック

- [Teams の分析とレポート](teams-reporting-reference.md)