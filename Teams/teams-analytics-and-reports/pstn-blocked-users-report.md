---
title: Microsoft Teams PSTN ブロックユーザー レポート
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
description: Microsoft Teams 管理センターで PSTN ブロックされたユーザー レポートを使用して、PSTN 通話をブロックされている組織の Teams ユーザーの概要を取得します。
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
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Microsoft Teams PSTN ブロックユーザー レポート

Microsoft Teams 管理センターの PSTN ブロックユーザー レポートには、組織内の Teams での PSTN 通話の発信がブロックされているユーザーが表示されます。 割り当てられた電話番号や、通話をブロックされた理由など、ブロックされた各ユーザーに関する詳細を表示できます。

## <a name="view-the-pstn-blocked-users-report"></a>PSTN ブロックされたユーザー レポートを表示する

Microsoft Teams 管理センターの左側のナビゲーションで、**[分析 & レポート]** > **[使用状況レポート]** をクリックします。 [レポート **の表示] タブの** [ **レポート]** で **、[PSTN** ブロックされたユーザー] を選び、[レポートの実行] **をクリックします**。

![管理センターの PSTN ブロックユーザー レポート レポートのスクリーンショット](../media/teams-reports-pstn-blocked-users-with-callouts.png "番号付き吹き出しが表示された Microsoft Teams 管理センターの PSTN ブロックユーザー レポートのスクリーンショット")

## <a name="interpret-the-report"></a>レポートを解釈する

|Callout |説明  |
|--------|-------------|
|**1**   |各レポートには、生成された日付が含されます。 通常、レポートはアクティビティの時刻から 24 ～ 48 時間の遅延を反映します。 |
|**2**   |X 軸は日付です。 Y 軸はユーザー数です。 <br>特定の日付のドットの上にマウス ポインターを置くと、その日付にブロックされたユーザーの数が表示されます。 |
|**3**   |この表は、PSTN 通話をブロックされているすべてのユーザーの内訳を示しています。  電話システムまたは電話会議が割り当てられているすべてのユーザーが表示され、各ユーザーに関する詳細が表示されます。 <ul><li>**表示名** はユーザーの表示名です。 表示名をクリックして、Microsoft Teams 管理センターのユーザーの設定ページに移動することができます。 </li> <li>**電話番号** は、ユーザーに割り当てられている番号です。</li> <li>**ブロックされる理由** は、ユーザーが通話をブロックされる理由です。</li><li>**ブロックされるアクション**  は、ユーザーが Teams で PSTN 通話を行うのをブロックまたはブロック解除されているかどうかを示します。</li> <li>**ブロックされた時刻** は、ユーザーが呼び出しをブロックされた日付と時刻 (UTC) です。</li></li> </ul>表に希望する情報を表示するには、表に列を追加する必要があります。 |
|**4**   |[**列の編集**] を選択して表で列を追加または削除します。|
|**5**   |[ **全画面] を** 選び、レポートを全画面モードで表示します。|

## <a name="related-topics"></a>関連項目

- [Teams の分析とレポート](teams-reporting-reference.md)