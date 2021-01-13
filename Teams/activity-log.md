---
title: Microsoft Teams 管理センターのアクティビティ ログにポリシーの割り当てを表示する
author: cichur
ms.author: v-cichur
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Microsoft Teams 管理センターのアクティビティ ログでポリシー割り当てアクティビティを表示する方法について説明します。
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a8d1d49d187808b768b4a92c64c4e667ca0ea8f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821317"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>アクティビティ ログでポリシー割り当てを表示する

Microsoft Teams 管理センターでユーザーにポリシーを割り当てると、アクティビティ ログでそれらのポリシー割り当ての状態を表示できます。 アクティビティ ログには、過去 30 日間の Microsoft Teams 管理センターを通じて、20 人を超えるユーザーのバッチへのポリシー割り当てが表示されます。 アクティビティ ログには、ポリシー パッケージの割り当て、Microsoft Teams 管理センターを介した 20 人未満のユーザーのバッチへのポリシー割り当て、または PowerShell によるポリシー割り当ては表示されます。

![[アクティビティ ログ] ページのスクリーンショット](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>アクティビティ ログでポリシー割り当てアクティビティを表示する

アクティビティ ログにポリシー割り当てを表示するには、次の方法を実行します。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[ダッシュボード] に移動し、[アクティビティ ログ] の [詳細の表示] を **選択します**。
2. すべてのポリシー割り当てを表示したり、状態でリストをフィルター処理して、[開始していない]、[進行中]、または [完了] の割り当てのみを **表示することができます**。  各課題に関する次の情報が表示されます。
    - **名前**: ポリシー割り当ての名前。 詳細を表示するには、リンクをクリックします。 これには、ポリシーが割り当てられたユーザーの数、完了済み、進行中、開始されていない割り当ての数が含まれます。 バッチ内のユーザーの一覧と、各ユーザーの状態と結果も表示されます。 以下は、実行例です。

        ![[](media/activity-log-policy-assignment-detail.png)

    - **送信** 日時: ポリシー割り当てが送信された日付と時刻。
    - **完了時刻**: ポリシー割り当てが完了した日付と時刻。
    - **影響:** バッチ内のユーザー数。
    - **全体の状態**: ポリシー割り当ての状態。

> [!NOTE]
> [ユーザー] ページからアクティビティ ログに **アクセス** することもできます。 [適用] **をクリック** して一括ポリシーの割り当てを送信すると、ページの上部にバナーが表示されます。 バナーの **[アクティビティ ログ** ] リンクをクリックします。

## <a name="related-topics"></a>関連項目

- [ユーザーにポリシーを割り当てる](assign-policies.md)
