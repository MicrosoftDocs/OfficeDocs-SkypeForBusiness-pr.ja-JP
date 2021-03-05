---
title: Microsoft Teams アプリの使用状況レポート
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-quhur
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Teams 管理センターで Teams アプリの使用状況レポートを使用する方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 29e51e91cdc42000350a48dd0d83225e7791aea6
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460597"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams アプリの使用状況レポート

Microsoft Teams 管理センターの Teams アプリの使用状況レポートには、ユーザーが Teams で使用しているアプリに関する情報が表示されます。  

## <a name="view-the-app-usage-report"></a>アプリの使用状況レポートを表示する

1.  管理センターの左側のナビゲーションで、[利用状況レポート] & <https://admin.teams.microsoft.com> **クリック** \> **します**。 [レポートの **表示] タブの** [レポート **] で、[** アプリの使用状況 **] を選択します**。

     :::image type="content" source="media/app-usage-report1.png" alt-text="[利用状況レポート] メニュー項目のスクリーンショット":::

2.  **[日付の範囲]** の下で、範囲を選択して、**[レポートの実行]** をクリックします。

      :::image type="content" source="media/app-usage-report2.png" alt-text="アプリの使用状況レポートのスクリーンショット":::

## <a name="interpret-the-report"></a>レポートを解釈する

|Callout |説明  |
|--------|-------------|
|**1**   |Teams アプリの使用状況レポートでは、過去 7 日間、30 日間、または 90 日間の傾向を確認できます。 |
|**2**   |各レポートには、レポートが生成された日付が含されます。 通常、レポートには、アプリを開いた時刻から 24 時間の待機時間が反映されます。 <br><br>![日付範囲を示すアプリの使用状況レポートのスクリーンショット](media/app-usage-report3.png)|
|**3**    | <ul><li>グラフの X 軸は、特定のレポートに対して選択した日付範囲です。</li><li>Y 軸は、グラフ内で特定の日をポイントしたユーザーの数です。これらのユーザーは少なくとも 1 回はアプリを開いているので、アクティブ ユーザーと見なされ、マウス ポインターの上に表示される合計に対して計上されます。</li></ul>|
|**4**   |指定した日付にアプリの使用状況を表す点の上にマウス ポインターを置くと、そのアプリのアクティブなユーザーの合計のインスタンス数が、その日付に表示されます。  |
|**5**   |すべてのアプリが含まれますが、[フィルター] アイコンを選択すると、追加のフィルターを使用できます。  |
|**6**   |この表は、アクティブなユーザーとチームの内訳をアプリ名別に示しています。<br><ul><li>**アプリ名** は、Teams で使用されるアプリの表示名です。</li><li>**アクティブユーザー** とは、指定した期間中に少なくとも 1 回はアプリを開いたユーザーの数です。</li><li>**アプリの** 種類は、"Microsoft" または "サード パーティ" のいずれかの静的な値です。</li><li>**アクティブな** チームとは、チームの少なくとも 1 人のメンバーと、指定した期間中にアプリを開いたチームの数です。</li><li>**Publisher** は、アプリのソフトウェア発行元です。</li><li>**バージョン** は、アプリの発行元から提供されるアプリのソフトウェア バージョンです。</li></ul><b> 注:</b> 現在、"アクティブなユーザー" と "アクティブなチーム" は、チャネルでのみ使用されるアプリに対して計算されます。     

<br>![[アプリの使用状況] レポートの ](media/app-usage-report4.png)  | |**7**  |[列 **の編集] を** 選択して、テーブルの列を追加または削除します。<br><br>![[列の編集] ページのスクリーンショット| | ](media/app-usage-report5.png) **8**  |オフラインで分析するために、レポートを CSV ファイルにエクスポートできます。 **[Excel にエクスポート]** をクリックしてから、**[ダウンロード]** タブの **[ダウンロード]** をクリックして、準備のできたレポートをダウンロードします。<br>![[ダウンロード] ページのスクリーンショット| | ](media/app-usage-report7.png) **9**   |Excel でレポートを表示すると、アプリ ID を表す **Id** 列も表示されます。 通常、チーム ID は英数字の文字列です。 Id 列 **に** **\n**** と表示される場合は、ユーザーが情報の削除を要求したという意味です。<br>![ダウンロードした Excel レポートのスクリーンショット](media/app-usage-report8.png)  |

## <a name="related-topics"></a>関連トピック

- [Teams の分析とレポート](teams-reporting-reference.md)