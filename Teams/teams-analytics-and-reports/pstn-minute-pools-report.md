---
title: Microsoft Teams PSTN ミニデータ プール レポート
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
description: Microsoft Teams 管理センターで Teams PSTN ミニデータ プール レポートを使用して、現在の月に組織内で使用される分数を表示する方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8df0c1201f963a1c00742532f80089b523ca79aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809347"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Microsoft Teams PSTN ミニデータ プール レポート

Microsoft Teams 管理センターの Teams PSTN ミニサイト プール レポートでは、今月の電話会議と通話アクティビティの概要を示します。このレポートには、今月の通話分数が表示されます。 通話に使用されるライセンス、利用可能な合計通話分数、使用分数、場所別のライセンスの使用状況など、アクティビティの内訳を確認できます。

## <a name="view-the-pstn-minute-pools-report"></a>PSTN ミニ分間プール レポートを表示する

Microsoft Teams 管理センターの左側のナビゲーションで、**[分析 & レポート]** > **[使用状況レポート]** をクリックします。 [レポート **の表示] タブの** [ **レポート]** で **、[PSTN** 分プール] を選び、[レポートの実行] **をクリックします**。

![管理センターの Teams PSTN ミニデータ プール レポートのスクリーンショット](../media/teams-reports-pstn-minute-pools-with-callouts.png "番号付き吹き出し付き Microsoft Teams 管理センターの Teams PSTN ミニデータ プール レポートのスクリーンショット")

## <a name="interpret-the-report"></a>レポートを解釈する

|Callout |説明  |
|--------|-------------|
|**1**   |各レポートには、生成された日付が含されます。 通常、レポートはアクティビティの時刻から 24 ～ 48 時間の遅延を反映します。 |
|**2**   |機能 (ライセンス) をクリックして、その機能のアクティビティを表示します。 |
|**3**   |X 軸は国または地域です。 Y 軸は分数です。 <br>グラフ上のバーにマウス ポインターを置くと、その使用状況の場所のアクティビティが表示されます。  |
|**4**   |凡例の項目をクリックして、グラフに表示する情報をフィルター処理できます。 たとえば、[未使用 **]、[国内ユーザー]、** または [データなし]、または [国際] をクリックして、それぞれに関連する情報のみを表示します。   |
|**5**   |この表は、機能と使用場所別の分プールの内訳を示しています。 <ul><li>**国または地域** が使用場所です。 </li><li>**機能の** 説明は、通話に使用されるライセンスの説明です。  このレポートに表示される機能の説明は次のとおりです。 <ul><li>国内通話と国際通話プラン (国内通話 1200 分)</li><li>国内通話と国際通話プラン (国内通話 3,000 分)</li><li>国内通話と国際通話プラン (600 分の国際通話)</li></ul></li><br><li>**合計分** 数は、その月に利用できる合計分数です。</li><li>**使用分数** は、毎月使用される分数です。</li> <li>**利用可能な** 分数は、その月の残りの分数です。</li><li>[ **機能** ] は通話のために使用されるライセンスです。 表示されるライセンスは次のとおりです。<ul><li>**MCOPSTNPP** - コミュニケーション クレジット</li><li>**MCOPSTN1** - 国内通話プラン (米国 3000 分/ EU 1200 分プラン)</li><li>**MCOPSTN2** - 国際通話プラン</li><li>**MCOPSTN5** - 国内通話プラン (120 分通話プラン)</li><li>**MCOPSTN6** - 国内通話プラン (240 分通話プラン)</li><li>**MCOMEETADD** - 電話会議</li><li>**MCOMEETACPEA** - 分単位の電話会議の支払い</li></ul></li> </ul> 表に希望する情報を表示するには、表に列を追加する必要があります。|
|**6**   |[**列の編集**] を選択して表で列を追加または削除します。|
|**7**   |[ **全画面] を** 選び、レポートを全画面モードで表示します。|

## <a name="related-topics"></a>関連項目

- [Teams の分析とレポート](teams-reporting-reference.md)