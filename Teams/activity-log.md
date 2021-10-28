---
title: ポリシーの割り当てを管理センターのアクティビティ ログMicrosoft Teams表示する
author: cichur
ms.author: serdars
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: ポリシー割り当てアクティビティを管理センターのアクティビティ ログで表示Microsoft Teamsします。
ms.localizationpriority: medium
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c1ce06f8c74570a7d5da5056b89772d5446562b
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605643"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>アクティビティ ログでポリシーの割り当てを表示する

Microsoft Teams 管理センターでユーザーにポリシーを割り当てると、それらのポリシー割り当ての状態をアクティビティ ログに表示できます。 アクティビティ ログには、過去 30 日間の Microsoft Teams 管理センターを通じて、20 人を超えるユーザーのバッチへのポリシー割り当てが表示されます。 アクティビティ ログには、ポリシー パッケージの割り当て、Microsoft Teams 管理センターを通じて 20 人未満のユーザーのバッチに対するポリシーの割り当て、または PowerShell を使用したポリシー割り当てが表示される点に気を付けます。

![[アクティビティ ログ] ページのスクリーンショット。](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>アクティビティ ログでポリシー割り当てアクティビティを表示する

アクティビティ ログでポリシーの割り当てを表示するには:

1. 管理センターの左側のナビゲーションMicrosoft Teams 、[ホーム] に移動し、[アクティビティ ログ]で [詳細の表示]**を選択します**。
2. すべてのポリシー割り当てを表示したり、状態で一覧をフィルター処理して、[開始していない]、[進行中]、または [完了] の割り当てのみを **表示することができます**。 各課題に関する次の情報が表示されます。
    - **[** 名前]: ポリシー割り当ての名前。 リンクをクリックすると、詳細が表示されます。 これには、ポリシーが割り当てられたユーザーの数と、完了した割り当て、進行中、開始されていない割り当ての数が含まれます。 バッチ内のユーザーの一覧と、各ユーザーの状態と結果も表示されます。 以下は、実行例です。

        ![のスクリーンショット。](media/activity-log-policy-assignment-detail.png)

    - **送信** 済み: ポリシーの割り当てが送信された日付と時刻。
    - **完了時刻**: ポリシーの割り当てが完了した日付と時刻。
    - **影響:** バッチ内のユーザーの数。
    - **全体の状態**: ポリシー割り当ての状態。

> [!NOTE]
> [ユーザー] ページからアクティビティ ログに **アクセス** することもできます。 [適用] **をクリック** して一括ポリシーの割り当てを送信すると、ページの上部にバナーが表示されます。 バナーの **[アクティビティ ログ** ] リンクをクリックします。

## <a name="related-topics"></a>関連トピック

- [ユーザーにポリシーを割り当てる](policy-assignment-overview.md)
