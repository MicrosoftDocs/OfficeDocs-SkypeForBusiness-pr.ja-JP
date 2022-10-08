---
title: Microsoft Teams アプリの使用状況レポート
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
ms.date: 09/27/2022
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Teams 管理センターで Teams アプリの使用状況レポートを使用する方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9db5378a439061639298b8bc3b48f4d3ef26c50b
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2022
ms.locfileid: "68376965"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams アプリの使用状況レポート

Microsoft Teams 管理センターの Teams アプリの使用状況レポートには、Teams でユーザーが使用しているアプリに関する分析情報が表示されます。 組織内の Teams アプリ アクティビティに関する分析情報を得ることができます。 この記事では、レポートにアクセスし、レポート内のさまざまなメトリックを表示および解釈する方法について説明します。 

## <a name="view-the-app-usage-report"></a>アプリ使用状況レポートを表示する

1. Teams 管理センターの左側のナビゲーションで、[**Analytics & レポート****[使用状況レポート](https://admin.teams.microsoft.com/analytics/reports)** > ] を選択します。

   :::image type="content" source="media/app-usage-report1.png" alt-text="[利用状況レポート] メニュー項目のスクリーンショット。":::

1. [ **レポートの表示** ] タブの [ **レポート**] で、[ **アプリの使用状況**] を選択します。

1. **[日付範囲**] で範囲を選択し、[**レポートの実行**] を選択します。 Teams Apps 使用状況レポートでは、過去 7 日間、30 日、90 日、180 日間の傾向を確認できます。

   :::image type="content" source="media/app-usage-report2-trimmed.png" alt-text="アプリ使用状況レポート インターフェイスのスクリーンショット。" lightbox="media/app-usage-report2.png":::

## <a name="interpret-the-report"></a>レポートを解釈する

:::image type="content" alt-text="Teams 管理センターの Teams アプリ使用状況レポートと吹き出しのスクリーンショット。" source="media/app-usage-report5.png" lightbox="media/app-usage-report5.png":::

各レポートには、レポートが作成された日時を示す日付が左上に表示されます。 通常、レポートには、アプリを開いた時点から 24 時間から 48 時間の待機時間が反映されます。

管理センターには、アクティブなユーザーと日付のグラフが表示されます。 アクティブなユーザーは、選択した期間中に少なくとも 1 回アプリを開いたユーザーの数です。

任意の日付にアプリの使用状況を表すドット (4) にマウス ポインターを合わせると、その日付にアプリのアクティブなユーザーの合計数が表示されます。

他のアプリを選択するには、右上にある **[フィルター** ] アイコン (5) を選択し、新しい条件を選択または入力して、[ **適用**] を選択します。

レポートの下部にある表 (6) には、アクティブなユーザーとチームがアプリ名で表示されます。

   - **アプリ名** は、Teams で使用されるアプリの表示名です。
   - **アクティブなユーザー** は、指定した期間内に少なくとも 1 回アプリを開いたユーザーの数です。
   - **アプリの種類** は、"Microsoft" または "サード パーティ" のいずれかの静的な値です。
   - **アクティブなチーム** とは、チームの少なくとも 1 人のメンバーがアプリを開いたチームの数であり、指定された期間にアプリを開いたチームの数です。
   - **パブリッシャー** は、アプリのソフトウェア開発者です。
   - **バージョン** は、アプリ開発者からのアプリのソフトウェア バージョンです。

   > [!NOTE]
   > **アクティブ ユーザー** と **アクティブ チーム** は、チャネルでのみ使用されるアプリに対して計算されます。

テーブル内の列を追加または削除するには、右上の [ **列の編集]** アイコン (7) を選択し、[ **列の編集** ] タブで新しい条件を選択し、[ **適用**] を選択します。

レポートをオフライン分析用の CSV ファイルにエクスポートするには、右上の **[Excel にエクスポート**] アイコン (8) を選択し、[**状態**] の [**ダウンロード**] タブで [**ダウンロード**] を選択します。

   :::image type="content" alt-text="[ダウンロード] ウィンドウのスクリーンショット。" source="media/app-usage-report7.png" lightbox="media/app-usage-report7.png":::

Microsoft Excel でレポートを表示すると、アプリ ID を表す列 (通常は英数字の文字列) も表示 `Id` されます。 値 `Id` が **\n** の場合は、ユーザーが自分の情報を削除するように求めたことを意味します。

   :::image type="content" source="media/app-usage-report8.png" alt-text="ダウンロードした Excel レポートのスクリーンショット。":::

## <a name="related-articles"></a>関連記事

- [Teams の分析とレポート](teams-reporting-reference.md)
