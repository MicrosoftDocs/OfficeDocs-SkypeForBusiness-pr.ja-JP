---
title: 一括でマイクロソフトのチームのユーザー設定を編集します。
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
ms.sourcegitcommit: 3000a661ac420eecd825a8285bdac7b744bd25da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "31988974"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a><span data-ttu-id="66607-103">一括でマイクロソフトのチームのユーザー設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="66607-103">Edit Microsoft Teams user settings in bulk</span></span>

<span data-ttu-id="66607-104">管理者としては、マイクロソフトのチームの管理センターでチームのユーザー設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="66607-104">As an admin, you manage Teams user settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="66607-105">[**ユーザー** ] ページでは、アカウントとライセンスの詳細情報を表示し、ポリシーとその他の設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="66607-105">On the **Users** page, you can view information such as account and licensing details and edit policy and other settings.</span></span> <span data-ttu-id="66607-106">同時に個別にまたは複数のユーザーのユーザーの設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="66607-106">You can edit settings for users individually or for multiple users at the same time.</span></span>

## <a name="edit-user-settings-in-bulk"></a><span data-ttu-id="66607-107">一括でユーザー設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="66607-107">Edit user settings in bulk</span></span>

<span data-ttu-id="66607-108">マイクロソフトのチーム管理センターを使用すると、同時に複数のユーザーの設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="66607-108">Use the Microsoft Teams admin center to edit settings for multiple users at a time.</span></span> <span data-ttu-id="66607-109">同時に 20 のユーザーの設定を編集することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="66607-109">We recommend editing settings for 20 users at a time.</span></span> <span data-ttu-id="66607-110">多数のユーザーの設定を編集するには、PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="66607-110">To edit settings for a large number of users, use PowerShell.</span></span> <span data-ttu-id="66607-111">詳細については、[チームの PowerShell の概要](teams-powershell-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66607-111">For more information, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

1. <span data-ttu-id="66607-112">マイクロソフトのチーム管理センターの左側のナビゲーションでは、**ユーザー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="66607-112">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="66607-113">編集または編集するユーザーを表示するビューにフィルターを適用するユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="66607-113">Search for the users you want to edit or filter the view to show the users you want to edit.</span></span>
3. <span data-ttu-id="66607-114">で **& #x 2713 です。**(チェック マーク)] 列で、次のいずれかの方法でユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="66607-114">In the **&#x2713;** (check mark) column, select users by doing one of the following:</span></span>
    - <span data-ttu-id="66607-115">一度に 1 つのユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="66607-115">Select users one at a time.</span></span> <span data-ttu-id="66607-116">選択する各ユーザーの横にある、 **& #x 2713;** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="66607-116">A **&#x2713;** is displayed next to each user you select.</span></span> <span data-ttu-id="66607-117">ブロックされませんが、注意してください場合は、20 以上のユーザーを選択するより多くのユーザーを選択することは、操作は、完了に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="66607-117">If you select more than 20 users, you won't be blocked but keep in mind that the more users you select, the operation will take longer to complete.</span></span>

        ![ユーザーの選択内容を表示するユーザー ページのスクリーン ショット](media/bulk-edit-user-settings-select-users.png)

    - <span data-ttu-id="66607-119">_AMP_ #x 2713; をクリックします。(チェック マーク) (最大で 20 ユーザー)、すべてのユーザーを選択し、[**選択範囲を制限する**] ダイアログ ボックスで] をクリックして**続行を選択すべて**選択を完了するのには、テーブルの上部にあります。</span><span class="sxs-lookup"><span data-stu-id="66607-119">Click the &#x2713; (check mark) at the top of the table to select all users (up to a maximum of 20 users), and then in the **Selection limit** dialog box, click **Continue select all** to complete the selection.</span></span>

        <span data-ttu-id="66607-120">![選択の制限を表示する [ユーザー] ページのスクリーン ショット](media/bulk-edit-user-settings-select-all-limit.png)</span><span class="sxs-lookup"><span data-stu-id="66607-120">![Screen shot of the Users page, showing the selection limit](media/bulk-edit-user-settings-select-all-limit.png)</span></span> <br> <span data-ttu-id="66607-121">選択したユーザーの横にある、 **& #x 2713;** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="66607-121">A **&#x2713;** is displayed next to the selected users.</span></span>

        ![20 ユーザーの選択を表示する [ユーザー] ページのスクリーン ショット](media/bulk-edit-user-settings-select-all.png)
4. <span data-ttu-id="66607-123">**設定の編集**] をクリックして、必要な変更を加えるし、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66607-123">Click **Edit settings**, make the changes that you want, and then click **Save**.</span></span>

    ![設定の編集] ウィンドウのスクリーン ショット](media/bulk-edit-user-settings-edit-settings.png)
