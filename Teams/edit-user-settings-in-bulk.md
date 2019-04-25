---
title: 一括で Microsoft Teams ユーザー設定を編集する
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: マイクロソフトのチームの管理センターで一括でマイクロソフトのチームのユーザー設定を管理する方法について説明します。
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.bulkoperations.edit
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c1dfba0bdaec642b0ea078d7f10ba022c8514da
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245075"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a>一括でマイクロソフトのチームのユーザー設定を編集します。

管理者としては、マイクロソフトのチームの管理センターでチームのユーザー設定を管理します。 [**ユーザー** ] ページでは、アカウントとライセンスの詳細情報を表示し、ポリシーとその他の設定を編集できます。 同時に個別にまたは複数のユーザーのユーザーの設定を編集できます。

## <a name="edit-user-settings-in-bulk"></a>一括でユーザー設定を編集します。

マイクロソフトのチーム管理センターを使用すると、同時に複数のユーザーの設定を編集します。 同時に 20 のユーザーの設定を編集することをお勧めします。 多数のユーザーの設定を編集するには、PowerShell を使用します。 詳細については、[チームの PowerShell の概要](teams-powershell-overview.md)を参照してください。

1. マイクロソフトのチーム管理センターの左側のナビゲーションでは、**ユーザー**を選択します。
2. 編集または編集するユーザーを表示するビューにフィルターを適用するユーザーを検索します。
3. で **& #x 2713 です。**(チェック マーク)] 列で、次のいずれかの方法でユーザーを選択します。
    - 一度に 1 つのユーザーを選択します。 選択する各ユーザーの横にある、 **& #x 2713;** が表示されます。 ブロックされませんが、注意してください場合は、20 以上のユーザーを選択するより多くのユーザーを選択することは、操作は、完了に時間がかかります。

        ![ユーザーの選択内容を表示するユーザー ページのスクリーン ショット](media/bulk-edit-user-settings-select-users.png)

    - _AMP_ #x 2713; をクリックします。(チェック マーク) (最大で 20 ユーザー)、すべてのユーザーを選択し、[**選択範囲を制限する**] ダイアログ ボックスで] をクリックして**続行を選択すべて**選択を完了するのには、テーブルの上部にあります。

        ![選択の制限を表示する [ユーザー] ページのスクリーン ショット](media/bulk-edit-user-settings-select-all-limit.png) <br> 選択したユーザーの横にある、 **& #x 2713;** が表示されます。

        ![20 ユーザーの選択を表示する [ユーザー] ページのスクリーン ショット](media/bulk-edit-user-settings-select-all.png)
4. **設定の編集**] をクリックして、必要な変更を加えるし、[**保存**] をクリックします。

    ![設定の編集] ウィンドウのスクリーン ショット](media/bulk-edit-user-settings-edit-settings.png)
