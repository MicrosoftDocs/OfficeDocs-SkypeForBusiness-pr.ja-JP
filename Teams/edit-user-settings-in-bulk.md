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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6177a463bee481812323b2334461f20e7021af84
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41832647"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a><span data-ttu-id="db942-103">Microsoft Teams のユーザー設定を一括して編集する</span><span class="sxs-lookup"><span data-stu-id="db942-103">Edit Microsoft Teams user settings in bulk</span></span>

<span data-ttu-id="db942-104">管理者は、Microsoft Teams 管理センターで Teams のユーザー設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="db942-104">As an admin, you manage Teams user settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="db942-105">[**ユーザー** ] ページでは、[アカウント]、[ライセンスの詳細]、[ポリシーとその他の設定の編集] などの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="db942-105">On the **Users** page, you can view information such as account and licensing details and edit policy and other settings.</span></span> <span data-ttu-id="db942-106">ユーザーは、個別に、または複数のユーザーの設定を同時に編集することができます。</span><span class="sxs-lookup"><span data-stu-id="db942-106">You can edit settings for users individually or for multiple users at the same time.</span></span>

## <a name="edit-user-settings-in-bulk"></a><span data-ttu-id="db942-107">ユーザー設定を一括で編集する</span><span class="sxs-lookup"><span data-stu-id="db942-107">Edit user settings in bulk</span></span>

<span data-ttu-id="db942-108">Microsoft Teams 管理センターを使用して、一度に複数のユーザーの設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="db942-108">Use the Microsoft Teams admin center to edit settings for multiple users at a time.</span></span> <span data-ttu-id="db942-109">一度に20人のユーザーの設定を編集することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="db942-109">We recommend editing settings for 20 users at a time.</span></span> <span data-ttu-id="db942-110">多数のユーザーの設定を編集するには、PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="db942-110">To edit settings for a large number of users, use PowerShell.</span></span> <span data-ttu-id="db942-111">詳細については、「 [Teams PowerShell の概要](teams-powershell-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db942-111">For more information, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

1. <span data-ttu-id="db942-112">Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="db942-112">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="db942-113">編集するユーザーを検索するか、ビューをフィルター処理して、編集するユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="db942-113">Search for the users you want to edit or filter the view to show the users you want to edit.</span></span>
3. <span data-ttu-id="db942-114">[ **&#x2713;** (チェックマーク)] 列で、次のいずれかの操作を行って [ユーザー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="db942-114">In the **&#x2713;** (check mark) column, select users by doing one of the following:</span></span>
    - <span data-ttu-id="db942-115">一度に1人のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="db942-115">Select users one at a time.</span></span> <span data-ttu-id="db942-116">選択した各ユーザーの横に **&#x2713;** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="db942-116">A **&#x2713;** is displayed next to each user you select.</span></span> <span data-ttu-id="db942-117">ユーザーが20人を超える場合は、ブロックされることはありませんが、選択したユーザー数が多いほど、操作が完了するまでに長い時間がかかることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="db942-117">If you select more than 20 users, you won't be blocked but keep in mind that the more users you select, the longer the operation will take to complete.</span></span>

        ![ユーザーが選択したことを示す [ユーザー] ページのスクリーンショット](media/bulk-edit-user-settings-select-users.png)

    - <span data-ttu-id="db942-119">表の上部にある [&#x2713; (最大20人)] をクリックし、[**選択範囲**] ダイアログボックスで、[**すべて選択**] をクリックして選択を完了します。</span><span class="sxs-lookup"><span data-stu-id="db942-119">Click the &#x2713; (check mark) at the top of the table to select all users (up to a maximum of 20 users), and then in the **Selection limit** dialog box, click **Continue select all** to complete the selection.</span></span>

        <span data-ttu-id="db942-120">![[ユーザー] ページのスクリーンショット。選択の制限が表示されています。](media/bulk-edit-user-settings-select-all-limit.png)</span><span class="sxs-lookup"><span data-stu-id="db942-120">![Screen shot of the Users page, showing the selection limit](media/bulk-edit-user-settings-select-all-limit.png)</span></span> <br> <span data-ttu-id="db942-121">選択したユーザーの横に **&#x2713;** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="db942-121">A **&#x2713;** is displayed next to the selected users.</span></span>

        ![選択された20人のユーザーを示す [ユーザー] ページのスクリーンショット](media/bulk-edit-user-settings-select-all.png)
4. <span data-ttu-id="db942-123">[**設定の編集**] をクリックし、必要な変更を加えて、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db942-123">Click **Edit settings**, make the changes that you want, and then click **Save**.</span></span>

    ![[設定の編集] ウィンドウのスクリーンショット](media/bulk-edit-user-settings-edit-settings.png)
