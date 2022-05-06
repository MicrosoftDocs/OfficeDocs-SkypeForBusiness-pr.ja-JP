---
title: Microsoft Teams のデバイス使用状況レポート
author: SerdarSoysal
ms.author: serdars
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
description: Microsoft Teams管理センターでTeamsデバイス使用状況レポートを使用して、組織内のユーザーがTeamsに接続する方法を確認する方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f3d7960f0543c3c15733b4c1a77179fc4571a0f2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62418330"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams のデバイス使用状況レポート

Microsoft Teams管理センターのTeamsデバイス使用状況レポートには、ユーザーがTeamsに接続する方法に関する情報が表示されます。 レポートを使用すると、外出先でモバイル デバイスから使用Teamsの数など、組織全体で使用されているデバイスを確認できます。  

## <a name="view-the-device-usage-report"></a>デバイス使用状況レポートを表示する

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[分析 & レポート]** > **[使用状況レポート]** をクリックします。 [**レポートの表示**] タブの [**レポート**] で、**デバイスの使用状況Teams** 選択します。
2. **[日付の範囲]** の下で、範囲を選択して、**[レポートの実行]** をクリックします。

    ![Teams管理センターのTeamsデバイス使用状況レポートと吹き出しのスクリーンショット。](../media/teams-reports-device-usage-with-callouts.png "Teams管理センターのTeamsデバイス使用状況レポートのスクリーンショット(吹き出しあり)")

## <a name="interpret-the-report"></a>レポートを解釈する

|Callout |説明  |
|--------|-------------|
|**1**   |Teamsデバイス使用状況レポートは、過去 7 日間または 30 日間の傾向を確認できます。  |
|**2**   |各レポートには、レポートが生成された日付があります。 通常、レポートにはアクティビティの時点から 24 時間の待機時間が反映されます。 |
|**3**   |<ul><li>グラフの X 軸は、Teamsに接続するために使用されるさまざまなデバイス (**Windows**、**Mac**、**Linux**、**iOS**、**Android 電話**、**Web**) を表します。 </li><li>Y 軸は、選択した期間にデバイスを使用しているユーザーの数です。</li> </ul>デバイスを表すバーにマウス ポインターを合わせると、デバイスを使用してTeamsに接続するユーザーの数が表示されます。|
|**4**   |この表では、ユーザー別のデバイス使用量の内訳を示します。 <ul><li>**ユーザー名** はユーザーの表示名です。 表示名をクリックして、Microsoft Teams 管理センターのユーザーの設定ページに移動することができます。 </li><li>**Windows** は、ユーザーがWindows ベースのコンピューター上のTeams デスクトップ クライアントでアクティブであった場合に選択されます。</li><li>**macOS** コンピューター上のTeams デスクトップ クライアントでユーザーがアクティブであった場合、Mac が選択されます。 </li> <li>**Linux** コンピューター上のTeams デスクトップ クライアントでユーザーがアクティブであった場合、Linux が選択されます。 </li> <li>**ユーザーが iOS** 用のモバイル クライアントTeamsでアクティブであった場合、iOS が選択されます。</li><li>**Android 用** のモバイル クライアントTeamsユーザーがアクティブな場合、Android スマートフォンが選択されます。 <li><li>**ユーザーがTeams** Web クライアントでアクティブであった場合、Web が選択されます。 <li>**[最後のアクティビティ]** は、ユーザーが Teams アクティビティに参加した最後の日付 (UTC) を指します。</li> </ul> ユーザー アカウントが Azure AD に存在しなくなった場合は、ユーザー名がテーブルに "--" として表示されます。 <br><br>表に希望する情報を表示するには、表に列を追加する必要があります。 |
|**5**   |[**列の編集**] を選択して表で列を追加または削除します。 |
|**6**   |レポートを CSV ファイルにエクスポートすると、オフラインで分析できます。 **[Excel にエクスポート]** をクリックしてから、**[ダウンロード]** タブの **[ダウンロード]** をクリックして、準備のできたレポートをダウンロードします。<br><br>![エクスポートされたレポートを示す [ダウンロード] タブのスクリーンショット。](../media/teams-reports-export-to-csv.png)|


## <a name="make-the-user-specific-data-anonymous"></a>ユーザー固有のデータを匿名にする

デバイス使用状況レポートのデータTeams匿名にするには、グローバル管理者である必要があります。 これにより、レポート内の表示名、電子メール、AAD ID、エクスポートなどの識別可能な情報が非表示になります。

1. Microsoft 365 管理センターで、**設定****組織設定**\>に移動し、[**サービス**] タブで [レポート] を選択 **します**。
    
2. [ **レポート**] を選択し、[ **匿名識別子の表示**] を選択します。 この設定は、Microsoft 365 管理センターの使用状況レポートと管理センター Teams両方に適用されます。
  
3. [ **変更の保存] を選択します**。

## <a name="related-topics"></a>関連項目

- [Teams の分析とレポート](teams-reporting-reference.md)
