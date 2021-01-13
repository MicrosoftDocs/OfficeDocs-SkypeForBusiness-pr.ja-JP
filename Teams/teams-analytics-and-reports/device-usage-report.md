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
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Teams 管理センターで Teams デバイス使用状況レポートを使用して、組織内のユーザーが Teams に接続する方法を確認する方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 292632972396f5d4300fa2526f01e69a5555ff45
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815647"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams のデバイス使用状況レポート

Microsoft Teams 管理センターの Teams デバイス使用状況レポートには、ユーザーが Teams に接続する方法に関する情報が表示されます。 レポートを使用して、組織全体で使用されているデバイスを表示できます。また、移動中にモバイル デバイスから Teams を使用するデバイスの数も含めて表示できます。  

## <a name="view-the-device-usage-report"></a>デバイス使用状況レポートを表示する

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[分析 & レポート]** > **[使用状況レポート]** をクリックします。 [レポートの **表示] タブの** [レポート **] で、[Teams** デバイスの **使用状況] を選択します**。
2. **[日付の範囲]** の下で、範囲を選択して、**[レポートの実行]** をクリックします。

    ![吹き出し付き Teams 管理センターの Teams デバイス使用状況レポートのスクリーンショット](../media/teams-reports-device-usage-with-callouts.png "吹き出し付き Teams 管理センターの Teams デバイス使用状況レポートのスクリーンショット")

## <a name="interpret-the-report"></a>レポートを解釈する

|Callout |説明  |
|--------|-------------|
|**1**   |Teams デバイスの使用状況レポートでは、過去 7 日間または 30 日間の傾向を確認できます。  |
|**2**   |各レポートには、レポートが生成された日付が含されます。 通常、レポートはアクティビティの時刻から 24 時間の待機時間を反映します。 |
|**3**   |<ul><li>グラフ上の X 軸は、Teams への接続に使用されるさまざまなデバイス (Windows、Mac、Linux、iOS、Android    **Phone、Web)** を表します。  </li><li>Y 軸は、選択した期間にデバイスを使用しているユーザーの数です。</li> </ul>デバイスを表すバーの上にマウス ポインターを置くと、デバイスを使用して Teams に接続しているユーザーの数が表示されます。|
|**4**   |この表は、ユーザー別のデバイス使用状況の内訳を示しています。 <ul><li>**ユーザー名** はユーザーの表示名です。 表示名をクリックして、Microsoft Teams 管理センターのユーザーの設定ページに移動することができます。 </li><li>**ユーザー** が Windows ベースのコンピューター上の Teams デスクトップ クライアントでアクティブだった場合、Windows が選択されます。</li><li>**ユーザー** が macOS コンピューターの Teams デスクトップ クライアントでアクティブだった場合、Mac が選択されます。 </li> <li>**ユーザー** が Linux コンピューターの Teams デスクトップ クライアントでアクティブだった場合、Linux が選択されます。 </li> <li>**ユーザーが iOS** 用 Teams モバイル クライアントでアクティブだった場合、iOS が選択されます。</li><li>**ユーザーが Android** 用 Teams モバイル クライアントでアクティブだった場合、Android フォンが選択されます。 <li><li>**ユーザー** が Teams Web クライアントでアクティブだった場合、Web が選択されます。 <li>**[最後のアクティビティ]** は、ユーザーが Teams アクティビティに参加した最後の日付 (UTC) を指します。</li> </ul> ユーザー アカウントが Azure AD に存在しなくなった場合は、ユーザー名がテーブルに "--" として表示されます。 <br><br>表に希望する情報を表示するには、表に列を追加する必要があります。 |
|**5**   |[**列の編集**] を選択して表で列を追加または削除します。 |
|**6**   |レポートを CSV ファイルにエクスポートすると、オフラインで分析できます。 **[Excel にエクスポート]** をクリックしてから、**[ダウンロード]** タブの **[ダウンロード]** をクリックして、準備のできたレポートをダウンロードします。<br><br>![エクスポートされたレポートを示す [ダウンロード] タブのスクリーンショット](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>関連項目

- [Teams の分析とレポート](teams-reporting-reference.md)
