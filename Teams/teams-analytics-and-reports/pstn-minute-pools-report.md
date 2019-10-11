---
title: Microsoft Teams の PSTN 分プールレポート
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Microsoft Teams 管理センターで Teams の PSTN 分プールレポートを使用して、組織内の現在の月に消費された分数を確認する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 900d847b5b0978ca2bfdccd4788a828a32f2ee3b
ms.sourcegitcommit: 3ce40094a58509b69376b941b151c9d1c8538654
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "37428344"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Microsoft Teams の PSTN 分プールレポート

Microsoft Teams 管理センターの Teams PSTN 分数プールレポートは、現在の月に消費された分数を表示して、組織内の電話会議と通話アクティビティの概要を示します。 通話に使用されているライセンス、合計通話時間、使用済みの分数、および場所ごとのライセンス使用状況などのアクティビティの内訳を確認できます。

## <a name="view-the-report"></a>レポートを表示する

Microsoft Teams 管理センターの左のナビゲーションで、[**分析] & [レポート** > の**利用状況レポート**] をクリックします。 [レポートの**表示**] タブの [**レポート**] で、[ **PSTN 分プール**] を選択し、[**レポートの実行**] をクリックします。

(../media/teams-reports-pstn-minute-pools-with-callouts.png "番号付きの吹き出しが含まれる Microsoft teams 管理センターの TEAMS pstn 分プールレポートの")管理センターのスクリーンショット![に含まれる、teams の pstn 分プールレポートのスクリーンショット]

## <a name="interpret-the-report"></a>レポートを解釈する

|コールアウト |説明  |
|--------|-------------|
|**1**   |各レポートには、生成された日付が含まれています。 通常、レポートはアクティビティの時刻から 24 ～ 48 時間の遅延を反映します。 |
|**2**   |機能 (ライセンス) をクリックすると、その機能のアクティビティが表示されます。 |
|**3**   |X 軸は、国または地域です。 Y 軸は分単位の数値です。 <br>グラフの棒の上にマウスポインターを置くと、その使用場所のアクティビティが表示されます。  |
|**4**   |凡例の項目をクリックして、グラフに表示する情報をフィルター処理できます。 たとえば、[**未使用**]、[**国内ユーザー**]、[**データなし**]、[国際] のいずれかをクリックすると、それぞれに関連する情報のみが表示**され**ます。 |
|**5**   |表では、機能と利用場所ごとに、分単位のプールの内訳を示します。 <ul><li>[**国または地域**] は使用場所です。 </li><li>**機能の説明**は、通話に使用されるライセンスの説明です。  このレポートには、次の機能の説明が含まれています。 <ul><li>国内および国際通話プラン (1200 の国内通話プラン)</li><li>国内および国際通話プラン (3000 の国内通話プラン)</li><li>国内および国際通話プラン (600 の国際通話時間)</li></ul></li><br><li>"**合計分数**" は、その月で利用可能な分数の合計数です。</li><li>[**使用時間 (分)** は、毎月使用される分数</li> <li>[**利用可能な時間 (分)** とは、その月の残り分数です。</li><li>[ **機能** ] は通話のために使用されるライセンスです。 次のようなライセンスが表示されることがあります。<ul><li>**Mcopstnpp** -通信クレジット</li><li>**MCOPSTN1** -国内通話プラン (3000 分間/1200 分の EU プラン)</li><li>**MCOPSTN2** -国際通話プラン</li><li>**MCOPSTN5** -国内通話プラン (120 分の通話プラン)</li><li>**MCOPSTN6** -国内通話プラン (240 分の通話プラン)</li><li>**MCOMEETADD** -電話会議</li><li>**MCOMEETACPEA** -1 分あたりの通話料金電話会議</li></ul></li> </ul> 表に希望する情報を表示するには、表に列を追加する必要があります。|
|**6**   |[**列の編集**] を選択して表で列を追加または削除します。|
|**7**   |全画面表示モードでレポートを表示するには、[**全画面**表示] を選択します。|

## <a name="related-topics"></a>関連トピック

- [Teams の分析とレポート](teams-reporting-reference.md)