---
title: 一括で Microsoft Teams ユーザー設定を編集する
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Microsoft Teams 管理センターで Microsoft Teams のユーザー設定をまとめて管理する方法について説明します。
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: c57ae4978e0cfacf69c9e68fb47d3f28ad5c4f4d
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483750"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a>Microsoft Teams のユーザー設定を一括して編集する

管理者は、Microsoft Teams 管理センターで Teams のユーザー設定を管理します。 [**ユーザー** ] ページでは、[アカウント]、[ライセンスの詳細]、[ポリシーとその他の設定の編集] などの情報を表示できます。 ユーザーは、個別に、または複数のユーザーの設定を同時に編集することができます。

## <a name="edit-user-settings-in-bulk"></a>ユーザー設定を一括で編集する

Microsoft Teams 管理センターを使用して、一度に複数のユーザーの設定を編集します。 一度に20人のユーザーの設定を編集することをお勧めします。 多数のユーザーの設定を編集するには、PowerShell を使用します。 詳細については、「 [Teams PowerShell の概要](teams-powershell-overview.md)」を参照してください。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] を選択します。
2. 編集するユーザーを検索するか、ビューをフィルター処理して、編集するユーザーを表示します。
3. [ **&#x2713;** (チェックマーク)] 列で、次のいずれかの操作を行って [ユーザー] を選択します。
    - 一度に1人のユーザーを選択します。 選択した各ユーザーの横に **&#x2713;** が表示されます。 ユーザーが20人を超える場合は、ブロックされることはありませんが、選択したユーザー数が多いほど、操作が完了するまでに長い時間がかかることに注意してください。

        ![ユーザーが選択したことを示す [ユーザー] ページのスクリーンショット](media/bulk-edit-user-settings-select-users.png)

    - 表の上部にある [&#x2713; (最大20人)] をクリックし、[**選択範囲**] ダイアログボックスで、[**すべて選択**] をクリックして選択を完了します。

        ![[ユーザー] ページのスクリーンショット。選択の制限が表示されています。](media/bulk-edit-user-settings-select-all-limit.png) <br> 選択したユーザーの横に **&#x2713;** が表示されます。

        ![選択された20人のユーザーを示す [ユーザー] ページのスクリーンショット](media/bulk-edit-user-settings-select-all.png)
4. [**設定の編集**] をクリックし、必要な変更を加えて、[**保存**] をクリックします。

    ![[設定の編集] ウィンドウのスクリーンショット](media/bulk-edit-user-settings-edit-settings.png)
