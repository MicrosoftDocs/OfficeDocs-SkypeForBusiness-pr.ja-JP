---
title: MICROSOFT TEAMS PSTN 分プール レポート
author: serdarsoysal
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
description: Microsoft Teams管理センターの Teams PSTN 分プール レポートを使用して、現在の月に組織内で消費された分数を表示する方法。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ef2e207352bf4ad7ee3d0f6c8fae674c4022e0b0
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2021
ms.locfileid: "60045993"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>MICROSOFT TEAMS PSTN 分プール レポート

Microsoft Teams管理センターの Teams PSTN 分プール レポートでは、組織内の電話会議と通話アクティビティの概要を確認できます。このレポートには、現在の月に消費された分数が表示されます。 通話に使用されるライセンス、使用可能な合計分数、使用済み分数、場所別のライセンス使用量など、アクティビティの内訳を確認できます。

## <a name="view-the-pstn-minute-pools-report"></a>PSTN 分プール レポートを表示する

Microsoft Teams 管理センターの左側のナビゲーションで、**[分析 & レポート]** > **[使用状況レポート]** をクリックします。 [ **レポートの表示** ] タブの [ **レポート**] で、[ **PSTN 分プールと SMS(プレビュー)] プール** を選択し、[ **レポートの実行**] をクリックします。

![管理センターのTeams PSTN 分プール レポートのスクリーンショット。](../media/teams-reports-pstn-minute-pools-with-callouts.png "Microsoft Teams管理センターのTeams PSTN 分プール レポートのスクリーンショット(番号付き吹き出しあり)")

## <a name="interpret-the-report"></a>レポートを解釈する

|Callout |説明  |
|--------|-------------|
|**1**   |各レポートには、それが生成された日付が表示されます。通常、レポートはアクティビティの時刻から 24 から 48 時間の遅延を反映します。 |
|**2**   |機能 (ライセンス) をクリックして、その機能のアクティビティを表示します。 |
|**3**   |X 軸は国または地域です。 Y 軸は分数です。 <br>グラフ上のバーにカーソルを合わせると、その利用状況の場所のアクティビティが表示されます。  |
|**4**   |凡例の項目をクリックして、グラフに表示する情報をフィルター処理できます。 たとえば、[ **未使用**]、[ **国内ユーザー**]、[ **データなし**]、または **[国際]** をクリックして、それぞれに関連する情報のみを表示します。 |
|**5**   |この表では、機能と使用状況の場所別に分のプールの内訳を示します。 <ul><li>**国または地域** は使用する場所です。 </li><li>**機能の説明** は、呼び出しに使用されるライセンスの説明です。  このレポートに表示される機能の説明は次のとおりです。 <ul><li>国内および国際通話プラン (1200 国内分)</li><li>国内および国際通話プラン (3,000 国内分)</li><li>国内通話と国際通話プラン (600 国際分)</li></ul></li><br><li>**合計分** 数は、その月に使用できる合計分数です。</li><li>**使用される分** 数は、毎月使用される分数です。</li> <li>**使用可能な分** 数は、その月の残りの分数です。</li><li>**機能** は、通話のために使用されるライセンスです。 表示されるライセンスは次のとおりです。<ul><li>**MCOPSTN1** - 国内通話プラン (米国では 3000 分 / EU では 1200 分のプラン)</li><li>**MCOPSTN2** - 国際通話プラン</li><li>**MCOPSTN5** - 国内通話プラン (120 分通話プラン)</li><li>**MCOPSTN6** - 国内通話プラン (240 分通話プラン)</li><li>**MCOMEETADD** - 電話会議</li></ul></li> </ul> 表に希望する情報を表示するには、表に列を追加する必要があります。|
|**6**   |[**列の編集**] を選択して表で列を追加または削除します。|
|**7**   |[**全画面**] を選択すると、レポートが全画面モードで表示されます。|

## <a name="related-topics"></a>関連項目

- [Teams の分析とレポート](teams-reporting-reference.md)
