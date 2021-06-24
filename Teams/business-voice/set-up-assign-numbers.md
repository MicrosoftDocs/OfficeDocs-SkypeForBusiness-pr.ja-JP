---
title: Business Voice の電話番号をユーザーに割り当てる
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 組織内のユーザーに電話番号Microsoft 365 Business Voiceを割り当てる方法について学習します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0792b644c97194867c448ed67fb574bfb7735325
ms.sourcegitcommit: 38fa37d83704200911866cf017566fcb128ea2fe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105159"
---
# <a name="step-5-assign-business-voice-phone-numbers-to-your-users"></a><span data-ttu-id="7fbb5-103">手順 5: Business Voice の電話番号をユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="7fbb5-103">Step 5: Assign Business Voice phone numbers to your users</span></span>

<span data-ttu-id="7fbb5-104">ユーザーが通常の電話回線Teams通話を送受信するには、ユーザーに電話番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fbb5-104">Before users can use Teams to make or receive phone calls to or from regular phone lines, you need to assign phone numbers to them.</span></span> <span data-ttu-id="7fbb5-105">このMicrosoft Teamsユーザーに割り当てる電話番号は、ユーザーが [通話] をクリックするとダイヤル パッドに表示 **されます**。</span><span class="sxs-lookup"><span data-stu-id="7fbb5-105">In Microsoft Teams clients, the phone number that you assign to a user is listed in the dial pad when the user clicks **Calls**.</span></span> <span data-ttu-id="7fbb5-106">電話番号が必要なユーザーごとに、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7fbb5-106">Do the following for each user that needs a phone number.</span></span>

![ユーザーの電話番号が [Teams] に表示されます。](../media/teams-phone-number.png)

> [!NOTE]
> <span data-ttu-id="7fbb5-108">電話番号が表示しない場合は、お待ちください。</span><span class="sxs-lookup"><span data-stu-id="7fbb5-108">If you don't see any phone numbers, please wait.</span></span> <span data-ttu-id="7fbb5-109">新しい電話番号が新しい電話番号で利用可能になるには、数時間かかるTeams。</span><span class="sxs-lookup"><span data-stu-id="7fbb5-109">It may take several hours for your new phone numbers to become available in Teams.</span></span>

<span data-ttu-id="7fbb5-110">次のビデオでは、管理センターでこれらの手順を完了Teams示します。</span><span class="sxs-lookup"><span data-stu-id="7fbb5-110">The following video shows you how to complete these steps in the Teams admin center.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OFYO]

1. <span data-ttu-id="7fbb5-111">Microsoft Teams 管理センターを開き、グローバル管理者であるユーザー (通常は、管理者のサインアップに使用したアカウント) でログインMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="7fbb5-111">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="7fbb5-112">左側のナビゲーション ウィンドウで、[Voice 電話 <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">  >  **に移動します**</a>。</span><span class="sxs-lookup"><span data-stu-id="7fbb5-112">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Voice** > **Phone numbers**</a>.</span></span>
1. <span data-ttu-id="7fbb5-113">[番号 **電話ページで**、一覧で未割り当て番号を選択し、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="7fbb5-113">On the **Phone numbers** page, select an unassigned number in the list, and then click **Edit**.</span></span>  
1. <span data-ttu-id="7fbb5-114">[編集] **ウィンドウの** [割 **り** 当て] で、表示名またはユーザー名でユーザーを検索し、[割り当て] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="7fbb5-114">In the **Edit** pane, under **Assigned to**, search for the user by display name or user name, and then click **Assign**.</span></span>
1. <span data-ttu-id="7fbb5-115">[**緊急対応** の場所] で、[緊急対応の場所の設定][](set-up-emergency-locations.md)手順で追加した緊急対応の場所を選択するか、別のオフィスまたはホーム オフィス用に新しい場所を作成する必要がある場合は、[場所の追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="7fbb5-115">Under **Emergency location**, you can select either the emergency location you added in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
1. <span data-ttu-id="7fbb5-116">電話番号情報が記載されたウェルカム メールをユーザーに送信するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="7fbb5-116">Decide whether to send a welcome email with phone number information to the user.</span></span> <span data-ttu-id="7fbb5-117">以下を希望する場合:</span><span class="sxs-lookup"><span data-stu-id="7fbb5-117">If you want to:</span></span>
    - <span data-ttu-id="7fbb5-118">**既存の電話番号を** Business Voice (電話番号の移植と呼ばれる)に持ち込み、電話番号情報を含むメール ユーザー **の選択を解除します**。</span><span class="sxs-lookup"><span data-stu-id="7fbb5-118">**Bring your existing phone numbers** to Business Voice (called phone number porting), *unselect* **Email user with telephone number information**.</span></span>
    - <span data-ttu-id="7fbb5-119">Business Voice **で選択した新しい** 電話番号を使用し、[電話番号情報を **含むメール ユーザー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7fbb5-119">**Use the new phone numbers** selected by Business Voice, *select* **Email user with telephone number information**.</span></span>
1. <span data-ttu-id="7fbb5-120">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7fbb5-120">Click **Save**.</span></span>
1. <span data-ttu-id="7fbb5-121">電話番号を割り当てる各ユーザーについて、上記の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="7fbb5-121">Repeat the above steps for each user to which you want to assign a phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="7fbb5-122">Microsoft 365 または Office 365 と Teams の間の待機時間のため、ユーザーが有効になるのに最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7fbb5-122">Because of the latency between Microsoft 365 or Office 365 and Teams, it can take up to 24 hours for users to be enabled.</span></span> <span data-ttu-id="7fbb5-123">電話番号が 24 時間後に正しく割り当てられていない場合は、ビジネス製品のサポートに問い [合わせ - 管理者](/microsoft-365/admin/contact-support-for-business-products)向けヘルプ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fbb5-123">If the phone number isn't assigned correctly after 24 hours, [contact support for business products - Admin Help](/microsoft-365/admin/contact-support-for-business-products).</span></span> <span data-ttu-id="7fbb5-124">お手伝いします。</span><span class="sxs-lookup"><span data-stu-id="7fbb5-124">We're here to help!</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7fbb5-125">次の手順: 自動応答を設定する</span><span class="sxs-lookup"><span data-stu-id="7fbb5-125">Next step: Set up an auto attendant</span></span>](set-up-auto-attendant.md?tabs=general-info#steps)
