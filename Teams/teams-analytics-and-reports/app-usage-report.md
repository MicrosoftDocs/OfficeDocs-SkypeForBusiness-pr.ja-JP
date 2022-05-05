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
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Teams管理センターでTeamsアプリの使用状況レポートを使用する方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a8ef86a0387c3966b795c323d1c28d0e1ca788e1
ms.sourcegitcommit: e102d72e67ab1c440c29ae6a048fc2cf8545fe01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2022
ms.locfileid: "65217951"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams アプリの使用状況レポート

Microsoft Teams管理センターのTeamsアプリ使用状況レポートには、Teamsで使用しているアプリユーザーに関する情報が表示されます。  

## <a name="view-the-app-usage-report"></a>アプリ使用状況レポートを表示する

1. 管理センターの左側のナビゲーションで<https://admin.teams.microsoft.com>、[**Analytics &** **reportsUsage** >  reports] をクリックします。<br><br>![[利用状況レポート] メニュー項目のスクリーンショット。](media/app-usage-report1.png "[利用状況レポート] メニュー項目のスクリーンショット。")
2. [ **レポートの表示** ] タブの [ **レポート**] で、[ **アプリの使用状況**] を選択します。

3. **[日付の範囲]** の下で、範囲を選択して、**[レポートの実行]** をクリックします。 Teams アプリの使用状況レポートは、過去 7 日間、30 日間、または 90 日間の傾向を確認できます。<br><br>![アプリの使用状況レポートのスクリーンショット。](media/app-usage-report2.png "アプリの使用状況レポートのスクリーンショット。")


## <a name="interpret-the-report"></a>レポートを解釈する

:::image type="content" alt-text="Teams管理センターのTeams アプリ使用状況レポートのスクリーンショット。吹き出しが表示されています。" source="media/app-usage-report5.png" lightbox="media/app-usage-report5.png":::

各レポートには、レポートが作成された日時を示す日付が左上に表示されます。 通常、レポートには、アプリを開いた時点から 24 時間の待機時間が反映されます。

グラフの Y 軸は、グラフの上にマウス ポインターを置いて選択した日付に対して、アプリを少なくとも 1 回開いたため、アクティブユーザーと見なされるユーザーの数です。

グラフの X 軸は、レポートに選択した日付範囲です。

任意の日付にアプリの使用状況を表すドット (4) にマウス ポインターを合わせると、その日付にアプリのアクティブなユーザーの合計数が表示されます。

他のアプリを選択するには、右上の **[フィルター** ] アイコン (5) をクリックし、新しい条件を選択または入力して、[ **適用**] をクリックします。

レポートの下部にある表 (6) には、アクティブなユーザーとチームがアプリ名で表示されます。

   - **アプリ名** は、Teamsで使用されるアプリの表示名です。
   - **アクティブなユーザー** は、指定した期間内に少なくとも 1 回アプリを開いたユーザーの数です。
   - **アプリの種類** は、"Microsoft" または "サード パーティ" のいずれかの静的な値です。
   - **アクティブなチーム** とは、チームの少なくとも 1 人のメンバーがアプリを開いたチームの数であり、指定された期間にアプリを開いたチームの数です。
   - **Publisher** は、アプリのソフトウェア発行元です。
   - **バージョン** は、アプリ発行元からのアプリのソフトウェア バージョンです。

   > [!NOTE]
   > **アクティブ ユーザー** と **アクティブ チーム** は、チャネルでのみ使用されるアプリに対して計算されます。

テーブル内の列を追加または削除するには、右上の [ **列の編集]** アイコン (7) をクリックし、[ **列の編集** ] タブで新しい条件を選択し、[ **適用**] をクリックします。

オフライン分析のためにレポートを CSV ファイルにエクスポートするには、右上の [**Excelにエクスポート**] アイコン (8) を選択し、[**状態**] の [**ダウンロード**] タブで [**ダウンロード**] をクリックします。

   :::image type="content" alt-text="[ダウンロード] ウィンドウのスクリーンショット。" source="media/app-usage-report7.png" lightbox="media/app-usage-report7.png":::

Excelでレポートを表示すると、アプリ ID を表す **Id** 列 (通常は英数字の文字列) も表示されます。 **ID が** **\n** の場合は、ユーザーが自分の情報を削除するように求められたことを意味します。

   ![ダウンロードしたExcel レポートのスクリーンショット。](media/app-usage-report8.png "ダウンロードしたExcel レポートのスクリーンショット。")

## <a name="related-topics"></a>関連項目

- [Teams の分析とレポート](teams-reporting-reference.md)
