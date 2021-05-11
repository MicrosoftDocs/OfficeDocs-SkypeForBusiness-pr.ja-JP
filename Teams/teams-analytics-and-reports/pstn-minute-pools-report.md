---
title: Microsoft TeamsPSTN 分プール レポート
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
description: Microsoft Teams 管理センターで Teams PSTN 分プール レポートを使用して、当月の組織内で消費された分数を表示する方法。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4d28e33ae820407ffe8c9561cae8c79863532417
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305991"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Microsoft TeamsPSTN 分プール レポート

Microsoft Teams 管理センターの Teams PSTN ミニデータ プール レポートでは、組織内の電話会議と通話アクティビティの概要を示します。このレポートには、当月に消費された分数が表示されます。 通話に使用されるライセンス、利用可能な合計分数、使用分数、場所別のライセンス使用量など、アクティビティの内訳を確認できます。

## <a name="view-the-pstn-minute-pools-report"></a>PSTN 分プール レポートを表示する

Microsoft Teams 管理センターの左側のナビゲーションで、**[分析 & レポート]** > **[使用状況レポート]** をクリックします。 [レポート **の表示] タブの** [レポート] **で**、[PSTN 分プール] **を選択し**、[レポートの実行] **をクリックします**。

![管理センター Teams PSTN 分プール レポートのスクリーンショット](../media/teams-reports-pstn-minute-pools-with-callouts.png "番号付き吹き出しTeams付き、Microsoft Teams PSTN 分プール レポートのスクリーンショット")

## <a name="interpret-the-report"></a>レポートを解釈する

|Callout |説明  |
|--------|-------------|
|**1**   |各レポートには、生成された日付があります。 通常、レポートはアクティビティの時刻から 24 ～ 48 時間の遅延を反映します。 |
|**2**   |機能 (ライセンス) をクリックして、その機能のアクティビティを表示します。 |
|**3**   |X 軸は国または地域です。 Y 軸は分数です。 <br>グラフ上の棒にマウス ポインターを合わせると、その使用状況の場所のアクティビティが表示されます。  |
|**4**   |凡例の項目をクリックして、グラフに表示する情報をフィルター処理できます。 たとえば、[未使用 **]、** 国内ユーザー 、**データ** なし、または [国際] をクリックして、それぞれに関連する情報のみを表示します。 |
|**5**   |この表は、機能と使用場所別の分プールの内訳を示しています。 <ul><li>**国または地域** は使用場所です。 </li><li>**機能の** 説明は、呼び出しに使用されるライセンスの説明です。  このレポートに表示される機能の説明は次のとおりです。 <ul><li>国内通話プランと国際通話プラン (国内通話 1,200 分)</li><li>国内通話プランと国際通話プラン (国内通話 3,000 分)</li><li>国内通話プランと国際通話プラン (600 分の国際通話)</li></ul></li><br><li>**[合計分** 数] は、その月に使用できる合計分数です。</li><li>**[分数** ] は、毎月使用される分数です。</li> <li>**[分]** は、その月の残り時間 (分) です。</li><li>[ **機能** ] は通話のために使用されるライセンスです。 表示される可能性があるライセンスは次のとおりです。<ul><li>**MCOPSTN1** - 国内通話プラン (米国 3000 分/ EU 1200 分プラン)</li><li>**MCOPSTN2** - 国際通話プラン</li><li>**MCOPSTN5** - 国内通話プラン (120 分の通話プラン)</li><li>**MCOPSTN6** - 国内通話プラン (240 分の通話プラン)</li><li>**MCOMEETADD** - 電話会議</li></ul></li> </ul> 表に希望する情報を表示するには、表に列を追加する必要があります。|
|**6**   |[**列の編集**] を選択して表で列を追加または削除します。|
|**7**   |[ **全画面] を** 選択して、レポートを全画面モードで表示します。|

## <a name="related-topics"></a>関連トピック

- [Teams の分析とレポート](teams-reporting-reference.md)
