---
title: Microsoft Teams使用状況レポートを作成する
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
description: 管理センターでアプリの使用状況Teamsレポートを使用するMicrosoft Teamsします。
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
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams使用状況レポートを作成する

Teams管理センターのアプリ使用状況レポートMicrosoft Teams、ユーザーがアプリで使用しているアプリに関する情報Teams。  

## <a name="view-the-app-usage-report"></a>アプリの使用状況レポートを表示する

1.  管理センターの左側のナビゲーションで、[分析] をクリックし、[ <https://admin.teams.microsoft.com> **利用状況& レポート** \> **を表示します**。 [レポートの **表示] タブの** [レポート] **で、[アプリ** の使用状況] **を選択します**。

     :::image type="content" source="media/app-usage-report1.png" alt-text="[使用状況レポート] メニュー項目のスクリーンショット":::

2.  **[日付の範囲]** の下で、範囲を選択して、**[レポートの実行]** をクリックします。

      :::image type="content" source="media/app-usage-report2.png" alt-text="アプリの使用状況レポートのスクリーンショット":::

## <a name="interpret-the-report"></a>レポートを解釈する

|Callout |説明  |
|--------|-------------|
|**1**   |[Teams アプリの使用状況レポートでは、過去 7 日間、30 日間、または 90 日間の傾向を確認できます。 |
|**2**   |各レポートには、レポートが生成された日付があります。 通常、レポートには、アプリを開いた時刻から 24 時間の待機時間が反映されます。 <br><br>![日付範囲を示すアプリの使用状況レポートのスクリーンショット](media/app-usage-report3.png)|
|**3**    | <ul><li>グラフの X 軸は、特定のレポートに対して選択した日付範囲です。</li><li>Y 軸は、特定の日にグラフ内でポイントされたユーザーの数です。これらのユーザーは少なくとも 1 回アプリを開き、これを行ってアクティブ ユーザーと見なされ、マウス ポインターで表示された合計に対して発生します。</li></ul>|
|**4**   |指定した日付のアプリの使用状況を表すドットにマウス ポインターを合わせると、その日付のアプリの合計アクティブ ユーザー数が表示されます。  |
|**5**   |すべてのアプリが含まれますが、[フィルター] アイコンを選択すると、追加のフィルターを使用できます。  |
|**6**   |この表は、アクティブなユーザーとチームの内訳をアプリ名別に示しています。<br><ul><li>**[アプリ名**] は、アプリで使用されるアプリの表示Teams。</li><li>**アクティブ ユーザー** とは、指定した期間中にアプリを少なくとも 1 回開いたユーザーの数です。</li><li>**アプリの** 種類は、"Microsoft" または "サード パーティ" のいずれかの静的な値です。</li><li>**アクティブな** チームとは、チームの少なくとも 1 人のメンバーが指定した期間中にアプリを開いたチームの数です。</li><li>**Publisher** は、アプリのソフトウェア発行元です。</li><li>**バージョン** は、アプリの発行元から提供される、アプリのソフトウェア バージョンです。</li></ul><b> 注:</b> 現在、"アクティブ ユーザー" と "アクティブ なチーム" は、チャネルでのみ使用されるアプリに対して計算されます。     

<br>![アプリの使用状況レポートのスクリーンショット| | ](media/app-usage-report4.png) **7**  |[列 **の編集] を** 選択して、テーブルの列を追加または削除します。<br><br>![[列の編集] ページのスクリーンショット| | ](media/app-usage-report5.png) **8 |**  レポートを CSV ファイルにエクスポートして、オフライン分析を行います。 **[Excel にエクスポート]** をクリックしてから、**[ダウンロード]** タブの **[ダウンロード]** をクリックして、準備のできたレポートをダウンロードします。<br>![[ダウンロード] ページのスクリーンショット| | ](media/app-usage-report7.png) **9 |** レポートを [ビュー] にExcel、アプリ ID を表す **[ID]** 列も表示されます。 通常、チーム ID は英数字の文字列です。 **[Id] 列** に **\n** と表示されている場合は、ユーザーが自分の情報を削除する要求を行いました。<br>![ダウンロードしたレポートのExcelスクリーンショット](media/app-usage-report8.png)  |

## <a name="related-topics"></a>関連トピック

- [Teams の分析とレポート](teams-reporting-reference.md)