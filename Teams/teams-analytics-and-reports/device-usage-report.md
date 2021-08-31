---
title: Microsoft Teams のデバイス使用状況レポート
author: cichur
ms.author: v-cichur
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
description: Teams 管理センターで Teams Microsoft Teams デバイスの使用状況レポートを使用して、組織内のユーザーがデバイスに接続する方法を確認する方法についてTeams。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 53aa8d88edd906e13532a452190234decf80d5db
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58730176"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams のデバイス使用状況レポート

Teams管理センターの [Microsoft Teams デバイスの使用状況] レポートには、ユーザーがデバイスに接続する方法に関する情報Teams。 レポートを使用すると、組織内で使用されているデバイスを確認できます。また、移動中にモバイル デバイスから Teams を使用するデバイスの数も表示できます。  

## <a name="view-the-device-usage-report"></a>デバイス使用状況レポートを表示する

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[分析 & レポート]** > **[使用状況レポート]** をクリックします。 [レポート **の表示] タブの**[レポート **] で、[** デバイスTeams **を選択します**。
2. **[日付の範囲]** の下で、範囲を選択して、**[レポートの実行]** をクリックします。

    ![吹き出しTeams付き、Teamsデバイス使用状況レポートのスクリーンショット。](../media/teams-reports-device-usage-with-callouts.png "吹き出しTeams付き、Teamsデバイス使用状況レポートのスクリーンショット")

## <a name="interpret-the-report"></a>レポートを解釈する

|Callout |説明  |
|--------|-------------|
|**1**   |デバイスTeamsレポートでは、過去 7 日間または 30 日間の傾向を確認できます。  |
|**2**   |各レポートには、レポートが生成された日付があります。 レポートには通常、アクティビティの時刻から 24 時間の待機時間が反映されます。 |
|**3**   |<ul><li>グラフ上の X 軸は、Windows、Mac、Linux、iOS、Android **電話、Web)** に接続するために使用されるさまざまなデバイスTeams。 </li><li>Y 軸は、選択した期間にデバイスを使用しているユーザーの数です。</li> </ul>デバイスを表すバーにマウス ポインターを合わせると、デバイスを使用してデバイスに接続しているユーザーの数Teams。|
|**4**   |次の表は、ユーザー別のデバイス使用状況の内訳を示しています。 <ul><li>**ユーザー名** はユーザーの表示名です。 表示名をクリックして、Microsoft Teams 管理センターのユーザーの設定ページに移動することができます。 </li><li>**Windows** ベースのコンピューター上の Teams デスクトップ クライアントでユーザーがアクティブWindows選択されます。</li><li>**macOS** コンピューターのデスクトップ クライアントでユーザーがアクティブTeams Mac が選択されます。 </li> <li>**Linux** コンピューターのデスクトップ クライアントでユーザーがアクティブTeams Linux が選択されます。 </li> <li>**ユーザーが iOS** のモバイル クライアントでアクティブTeams場合は、iOS が選択されます。</li><li>**Android フォン** は、ユーザーが Android のモバイル クライアントでアクティブTeams選択されます。 <li><li>**Web** クライアントでユーザーがアクティブだった場合、Web Teamsされます。 <li>**[最後のアクティビティ]** は、ユーザーが Teams アクティビティに参加した最後の日付 (UTC) を指します。</li> </ul> ユーザー アカウントが Azure AD に存在しなくなった場合は、ユーザー名がテーブルに "--" として表示されます。 <br><br>表に希望する情報を表示するには、表に列を追加する必要があります。 |
|**5**   |[**列の編集**] を選択して表で列を追加または削除します。 |
|**6**   |レポートを CSV ファイルにエクスポートすると、オフラインで分析できます。 **[Excel にエクスポート]** をクリックしてから、**[ダウンロード]** タブの **[ダウンロード]** をクリックして、準備のできたレポートをダウンロードします。<br><br>![エクスポートされたレポートを示す [ダウンロード] タブのスクリーンショット。](../media/teams-reports-export-to-csv.png)|


## <a name="make-the-user-specific-data-anonymous"></a>ユーザー固有のデータを匿名にする

デバイス使用状況レポートTeamsデータを匿名にする場合は、グローバル管理者である必要があります。 これにより、レポートの表示名、電子メール、AAD ID などの識別可能な情報とそのエクスポートが非表示になります。

1. このMicrosoft 365 管理センター、[組織] の[設定] に設定、[サービス] タブで [レポート] を \> 選択 **します**。 
    
2. [ **レポート]** を選択し、[匿名識別子 **を表示する] を選択します**。 この設定は、管理センターだけでなく、Microsoft 365 管理センター使用状況レポートTeams適用されます。
  
3. [変更の **保存] を選択します**。

## <a name="related-topics"></a>関連項目

- [Teams の分析とレポート](teams-reporting-reference.md)
