---
title: Microsoft Teams の使用状況レポート
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 自分の組織での Teams のアクティビティの概要を把握するために、Microsoft Teams 管理センターにある Teams の使用状況レポートを、どのように使用するかについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7aba4d3e185052d7c4f5399dd9370a05a4a7dc0a
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570974"
---
# <a name="microsoft-teams-usage-report"></a>Microsoft Teams の使用状況レポート

Microsoft Teams 管理センターにある Teams の使用状況レポートは、Teams での使用状況のアクティビティの概要を提供するもので、アクティブなユーザーおよびチャネルの数が含まれており、組織全体で何人のユーザーが通信や共同作業のために Teams を使用しているかをすぐに確認することができます。 各チームのアクティブなユーザー、チャネル、ゲスト、およびメッセージの数など、チームでの使用状況に関する情報を表示することができます。

## <a name="view-the-report"></a>レポートを表示する

1. Microsoft Teams 管理センターの左のナビゲーションで、[**分析] & [レポート** > の**利用状況レポート**] をクリックします。 [**レポートの表示**] タブの [**レポート**] で、[**チームの利用状況**] を選択します。
2. [**日付の範囲**] の下で、範囲を選択して、[**レポートの実行**] をクリックします。

    ![吹き出し付きの Teams 管理センターの Teams 利用状況レポートのスクリーンショット](../media/teams-reports-teams-usage-with-callouts.png "吹き出し付きの Teams 管理センターの Teams 利用状況レポートのスクリーンショット")

## <a name="interpret-the-report"></a>レポートを解釈する

|コールアウト |説明  |
|--------|-------------|
|**1**   |Teams 使用状況アクティビティ レポートでは、過去 7 日間または 28 日間の傾向を確認できます。 |
|**2**   |各レポートには、このレポートが生成された日付が表示されます。通常、レポートはアクティビティの時刻から 24 から 48 時間の遅延を反映します。 |
|**3**   |<ul><li>グラフ上の X 軸はこのレポートで選択した日付範囲です。</li> <li> Y 軸はアクティブな項目またはアクティビティの数です。</li> </ul>特定の日付の項目またはアクティビティを示しているドットの上にマウス カーソルを合わせると、その特定の日付のその項目またはアクティビティのインスタンスの数を見ることができます。|
|**4**   |凡例の項目をクリックして、グラフに表示する情報をフィルター処理できます。 たとえば、[**アクティブなユーザーの合計**]、[**チーム & のアクティブユーザー**]、[**アクティブなチャネル**]、または [**メッセージ**] をクリックして、それぞれに関連する情報のみを表示します。 この選択を変更しても、表内の情報は変わりません。 |
|**5**   |表によって、チームごとの使用状況の内訳が表示されます。 <ul><li>**チーム名**は、チームの表示名です。 チーム名をクリックすると、Microsoft Teams 管理センターのチームの [設定] ページに移動できます。 </li> <li>**プライバシー**では、チームがプライベートなチームであるかパブリックなチームであるかが示されます。</li> <li>**アクティブ ユーザー**は指定された期間でのチーム内のアクティブなユーザーの数です。</li><li>**ゲスト**は指定された期間でのチーム内のゲストの数です。</li> </li> </ul>ユーザーアカウントが Azure AD に存在しなくなった場合は、ユーザー名がテーブルに "--" として表示されることに注意してください。 <br><br>表に希望する情報を表示するには、表に列を追加する必要があります。 |
|**6**   |[**列の編集**] を選択して表で列を追加または削除します。|
|**7**   |レポートを CSV ファイルにエクスポートしてオフラインで分析することができます。 [ **Excel にエクスポート**] をクリックし、[**ダウンロード**] タブの [**ダウンロード**] をクリックして、準備ができたらレポートをダウンロードします。<br><br>![エクスポートされたレポートをダウンロードするための [ダウンロード] タブのスクリーンショット](../media/teams-reports-export-to-csv.png)|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>関連項目

- [Teams の分析とレポート](teams-reporting-reference.md)
