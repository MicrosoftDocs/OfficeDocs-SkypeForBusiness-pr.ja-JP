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
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 管理センターでアプリの使用状況Teamsレポートを使用するMicrosoft Teamsを確認します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7679652f0cb93e445e72af80307803b1e3197992
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2021
ms.locfileid: "60596214"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams使用状況レポートを作成する

Teams 管理センターのアプリ使用状況レポートMicrosoft Teams、ユーザーがアプリで使用しているアプリに関する情報Teams。  

## <a name="view-the-app-usage-report"></a>アプリの使用状況レポートを表示する

1. 管理センターの左側のナビゲーションで、[分析] をクリックし、[ <https://admin.teams.microsoft.com> **利用状況& レポート**  >  **を表示します**。<br><br>![[使用状況レポート] メニュー項目のスクリーンショット。](media/app-usage-report1.png "[使用状況レポート] メニュー項目のスクリーンショット。")
2. [レポートの **表示] タブの** [レポート] **で、[アプリ** の使用状況] **を選択します**。

3. **[日付の範囲]** の下で、範囲を選択して、**[レポートの実行]** をクリックします。 [Teams アプリの使用状況レポートでは、過去 7 日間、30 日間、または 90 日間の傾向を確認できます。<br><br>![アプリの使用状況レポートのスクリーンショット。](media/app-usage-report2.png "アプリの使用状況レポートのスクリーンショット。")


## <a name="interpret-the-report"></a>レポートを解釈する

:::image type="content" alt-text="吹き出しTeams付き、Teamsアプリ使用状況レポートのスクリーンショット。" source="media/app-usage-report5.png" lightbox="media/app-usage-report5.png":::

1. 各レポートには、レポートが作成された日時を示す日付が左上に表示されます。 通常、レポートには、アプリを開いた時刻から 24 時間の待機時間が反映されます。

2. グラフの Y 軸は、グラフの上にマウス ポインターを合わせると選択した日付に対して、少なくとも 1 回はアプリを開いているため、アクティブ ユーザーと見なされるユーザーの数です。

3. グラフの X 軸は、レポートに選択した日付範囲です。

4. 任意の日付にアプリの使用状況を表すドットにマウス ポインターを合わせると、その日付のアプリのアクティブ ユーザーの総数が表示されます。

5. 他のアプリを選択するには、右上にある [フィルター  ] アイコンをクリックし、新しい条件を選択または入力して、[適用] を **クリックします**。

6. レポートの下部にあるテーブルには、アクティブなユーザーとチームがアプリ名で表示されます。

   - **[アプリ** 名] は、アプリで使用されるアプリの表示名Teams。
   - **アクティブ ユーザー** とは、指定した期間中にアプリを少なくとも 1 回開いたユーザーの数です。
   - **アプリの** 種類は、"Microsoft" または "サード パーティ" のいずれかの静的な値です。
   - **アクティブな** チームとは、チームの少なくとも 1 人のメンバーが指定した期間中にアプリを開いたチームの数です。
   - **Publisher** は、アプリのソフトウェア発行元です。
   - **バージョン** は、アプリの発行元から提供される、アプリのソフトウェア バージョンです。

   > [!NOTE]
   > **アクティブ ユーザーと****アクティブ チームは**、チャネルでのみ使用されるアプリに対して計算されます。

7. テーブルの列を追加または削除するには、右上にある [列の編集] アイコンをクリックし、[列の編集] タブで新しい条件を選択し、[適用] をクリック **します**。

8. レポートを CSV ファイルにエクスポートしてオフライン分析するには、右上にある **[Excel** にエクスポート] アイコンを選択し、[状態]の [ダウンロード] タブで [ダウンロード] を **クリックします**。

   :::image type="content" alt-text="[ダウンロード] ウィンドウのスクリーンショット。" source="media/app-usage-report7.png" lightbox="media/app-usage-report7.png":::

9. レポートを Excel表示すると、アプリ ID (通常は英数字の文字列) を表す **Id** 列も表示されます。 ID が **の** 場合 **\n、** ユーザーは情報の削除を求めるメッセージが表示されます。

   ![ダウンロードしたレポートExcelスクリーンショット。](media/app-usage-report8.png "ダウンロードしたレポートExcelスクリーンショット。")

## <a name="related-topics"></a>関連項目

- [Teams の分析とレポート](teams-reporting-reference.md)
