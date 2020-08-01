---
title: Microsoft Teams のデバイス使用状況レポート
author: LanaChin
ms.author: v-lanac
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
description: Microsoft Teams 管理センターの Teams デバイス使用状況レポートを使用して、組織内のユーザーがどのように Teams に接続しているかを確認する方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dc36ccca5145bdfdd21e5b398954aec79cd12127
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533864"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams のデバイス使用状況レポート

Microsoft Teams 管理センターの Teams デバイス使用状況レポートでは、ユーザーが Teams に接続する方法についての情報が提供されます。 レポートを使用すると、外出先でも、モバイルデバイスで何人のチームを使用しているかなど、組織全体で使用されているデバイスを確認できます。  

## <a name="view-the-device-usage-report"></a>デバイスの使用状況レポートを表示する

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[分析およびレポート]** > **[使用状況レポート]** をクリックします。 [**レポートの表示**] タブの [**レポート**] で、[**チームデバイスの使用状況**] を選択します。
2. **[日付の範囲]** ので範囲を選択し、**[レポートの実行]** をクリックします。

    ![吹き出し付きの Teams 管理センターの Teams デバイスの使用状況レポートのスクリーンショット](../media/teams-reports-device-usage-with-callouts.png "吹き出し付きの Teams 管理センターの Teams デバイスの使用状況レポートのスクリーンショット")

## <a name="interpret-the-report"></a>レポートを解釈する

|Callout |説明  |
|--------|-------------|
|**1**   |[チームデバイスの使用状況] レポートでは、過去7日間または30日間の傾向を確認できます。  |
|**2**   |各レポートには、レポートが生成された日付が含まれています。 通常、レポートには、アクティビティの時間から24時間の待ち時間が反映されます。 |
|**3**   |<ul><li>グラフの X 軸は、Teams に接続するために使用されるさまざまなデバイス (**Windows**、 **Mac**、 **Linux**、 **iOS**、 **Android フォン**、 **Web**) を示しています。 </li><li>Y 軸は、選択した期間中にデバイスを使用したユーザーの数です。</li> </ul>デバイスを表すバーの上にマウスポインターを移動すると、そのデバイスを使用して Teams に接続したユーザーの数が表示されます。|
|**4**   |この表では、ユーザーによるデバイスの使用状況の内訳を示します。 <ul><li>**Username**はユーザーの表示名です。 表示名をクリックして、Microsoft Teams 管理センターのユーザーの設定ページに移動することができます。 </li><li>Windows ベースのコンピューターの Teams デスクトップクライアントでユーザーがアクティブになっていた場合は、 **windows**が選択されます。</li><li>**Mac**は、ユーザーが macOS コンピューターの Teams デスクトップクライアントでアクティブになった場合に選択されます。 </li> <li>ユーザーが Linux コンピューターの Teams デスクトップクライアントでアクティブになった場合、 **linux**が選択されます。 </li> <li>ユーザーが iOS の Teams モバイルクライアントでアクティブになっていた場合、 **ios**が選択されます。</li><li>ユーザーが Android 用の Teams モバイルクライアントでアクティブになっていた場合は、[ **android スマートフォン**を選択します。 <li><li>ユーザーが Teams web クライアントでアクティブになっていた場合は、[ **Web**に選択されています。 <li>**[最後のアクティビティ]** は、ユーザーが Teams アクティビティに参加した最後の日付 (UTC) を指します。</li> </ul> ユーザー アカウントが Azure AD に存在しなくなった場合は、ユーザー名がテーブルに "--" として表示されます。 <br><br>表に希望する情報を表示するには、表に列を追加する必要があります。 |
|**5**   |[**列の編集**] を選択して表で列を追加または削除します。 |
|**6**   |レポートを CSV ファイルにエクスポートすると、オフラインで分析できます。 **[Excel にエクスポート]** をクリックしてから、**[ダウンロード]** タブの **[ダウンロード]** をクリックして、準備のできたレポートをダウンロードします。<br><br>![エクスポートされたレポートが表示されている [ダウンロード] タブのスクリーンショット](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>関連項目

- [Teams の分析とレポート](teams-reporting-reference.md)
