---
title: Microsoft Teams管理センターのアクティビティ ログでポリシーの割り当てを表示する
author: SerdarSoysal
ms.author: serdars
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Microsoft Teams管理センターのアクティビティ ログでポリシーの割り当てアクティビティを表示する方法について説明します。
ms.localizationpriority: medium
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ed7903e0018d30882fa27c63941b5d03a27fdaf3
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393529"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>アクティビティ ログでポリシーの割り当てを表示する

Microsoft Teams管理センターのユーザーにポリシーを割り当てると、それらのポリシー割り当ての状態をアクティビティ ログに表示できます。 アクティビティ ログには、過去 30 日間の Microsoft Teams 管理センターを通じて、20 人を超えるユーザーのバッチへのポリシー割り当てが表示されます。 アクティビティ ログには、ポリシー パッケージの割り当て、Microsoft Teams管理センターを介した 20 未満のユーザーのバッチへのポリシーの割り当て、または PowerShell によるポリシーの割り当ては表示されないことに注意してください。

![[アクティビティ ログ] ページのスクリーンショット。](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>アクティビティ ログでポリシーの割り当てアクティビティを表示する

アクティビティ ログでポリシーの割り当てを表示するには:

1. Microsoft Teams管理センターの左側のナビゲーションで、[**ホーム**] に移動し、[**アクティビティ ログ**] で [**詳細の表示**] を選択します。
2. すべてのポリシーの割り当てを表示するか、状態で一覧をフィルター処理して、 **未開始**、 **進行中**、または **完了** の割り当てのみを表示できます。 各割り当てに関する次の情報が表示されます。
    - **名前**: ポリシーの割り当ての名前。 リンクをクリックすると、詳細が表示されます。 これには、ポリシーが割り当てられたユーザーの数と、完了、進行中、未開始の割り当ての数が含まれます。 バッチ内のユーザーの一覧と、各ユーザーの状態と結果も表示されます。 以下は、実行例です。

        ![のスクリーンショット。](media/activity-log-policy-assignment-detail.png)

    - **送信済み**: ポリシーの割り当てが送信された日時。
    - **完了時刻**: ポリシーの割り当てが完了した日時。
    - **影響**: バッチ内のユーザーの数。
    - **全体的な状態**: ポリシーの割り当ての状態。

> [!NOTE]
> [ **ユーザー]** ページからアクティビティ ログにアクセスすることもできます。 [ **適用]** をクリックして一括ポリシーの割り当てを送信すると、ページの上部にバナーが表示されます。 バナーの **[アクティビティ ログ** ] リンクをクリックします。

## <a name="related-topics"></a>関連項目

- [ユーザーにポリシーを割り当てる](policy-assignment-overview.md)
