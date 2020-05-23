---
title: Microsoft Teams 管理センターのアクティビティログでポリシーの割り当てを表示する
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Microsoft Teams 管理センターのアクティビティログでポリシーの割り当てアクティビティを表示する方法について説明します。
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a363d934ffd66d04bc3eb778380613e33e460a9
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350081"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>アクティビティログでポリシーの割り当てを表示する

Microsoft Teams 管理センターでユーザーにポリシーを割り当てると、それらのポリシー割り当ての状態をアクティビティログで確認できます。 アクティビティログには、過去30日間の Microsoft Teams 管理センターを通じて、20人を超えるユーザーのバッチに対するポリシーの割り当てが表示されます。 アクティビティログには、Microsoft Teams 管理センターを通じて、または PowerShell を使用したポリシーの割り当てによって、ポリシーパッケージの割り当て、ポリシーの割り当てが表示されないことに注意してください。

![[アクティビティログ] ページのスクリーンショット](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>アクティビティログでポリシーの割り当てアクティビティを表示する

アクティビティログでポリシーの割り当てを表示するには、次の操作を行います。

1. Microsoft Teams 管理センターの左のナビゲーションで、[**ダッシュボード**] に移動し、[**アクティビティログ**] で [**詳細の表示**] を選択します。
2. すべてのポリシーの割り当てを表示したり、状態別にリストにフィルターを適用したりして、**未開始**、**進行中**、または**完了**した割り当てだけを表示することができます。 各課題について次の情報が表示されます。
    - **Name**: ポリシーの割り当ての名前。 詳細を表示するには、リンクをクリックします。 これには、ポリシーが割り当てられたユーザーの数と、完了した、進行中で、まだ開始していない課題の数が含まれます。 また、バッチ内のユーザーの一覧と、各ユーザーの状態と結果も表示されます。 以下は、実行例です。

        ![のスクリーンショット](media/activity-log-policy-assignment-detail.png)

    - [**送信**日時]: ポリシーの割り当てが送信された日時。
    - **完了時刻**: ポリシーの割り当てが完了した日時。
    - **影響度**: バッチ内のユーザーの数。
    - **全般的な状態**: ポリシー割り当ての状態。

> [!NOTE]
> [**ユーザー** ] ページからアクティビティログにアクセスすることもできます。 [**適用**] をクリックして一括ポリシーの割り当てを送信すると、ページの上部にバナーが表示されます。 バナーの [**アクティビティログ**] リンクをクリックします。

## <a name="related-topics"></a>関連トピック

- [ユーザーにポリシーを割り当てる](assign-policies.md)
