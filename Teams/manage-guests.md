---
title: Microsoft Teams でのゲスト アクセスを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: IT 管理者は、テナントレベルでのゲストの追加、ゲスト ユーザー ポリシーと権限の設定と管理、ゲストを招待できるユーザーの判別、ゲスト ユーザーのアクティビティに関するレポートの取得を行うことができます。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7db3d42a8d4ae44364ee56f6c7f31ce501a34137
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37567620"
---
<a name="manage-guest-access-in-microsoft-teams"></a><span data-ttu-id="c6cba-103">Microsoft Teams でのゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="c6cba-103">Manage guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="c6cba-p101">**ゲスト**は、Microsoft Teams のユーザー/ライセンスの種類の 1 つで、すべての Office 365 Business Premium、Office 365 Enterprise、Office 365 Education のサブスクリプションに含まれていますす。追加の Office 365 ライセンスは必要ありません。Teams のゲスト アクセスはテナント レベルの設定であり、既定では無効になっています。ゲスト アクセスを有効にする方法について、詳しくは「[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c6cba-p101">**Guest** is a user/license type in Microsoft Teams that is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions. No additional Office 365 license is necessary. Teams guest access is a tenant-level setting and is turned off by default. For details about how to enable guest access, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>

<span data-ttu-id="c6cba-108">**ゲスト**ユーザー/ライセンスの種類を有効にした後、「 [microsoft teams の設定を管理](enable-features-office-365.md)する」および「[新しい microsoft teams への移行中にチームを管理する」で説明されているコントロールを使用してゲストの設定を構成することができます。管理センター](manage-teams-skypeforbusiness-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="c6cba-108">After the **Guest** user/license type is turned on, you can configure settings for guests via the controls described in [Manage Microsoft Teams settings for your organization](enable-features-office-365.md) and [Manage Teams during the transition to the new Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md).</span></span>     
    
<span data-ttu-id="c6cba-109">IT 管理者は、テナント レベルでのゲストの追加、ゲスト ユーザー ポリシーと権限の設定と管理、およびゲスト ユーザーのアクティビティに関するレポートの取得を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c6cba-109">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, and pull reports on guest user activity.</span></span> <span data-ttu-id="c6cba-110">これらの制御は、Microsoft Teams 管理センターを介して利用可能です。</span><span class="sxs-lookup"><span data-stu-id="c6cba-110">These controls are available through the Microsoft Teams admin center.</span></span> <span data-ttu-id="c6cba-111">ゲスト ユーザーのコンテンツとアクティビティには、Office 365 の他の部分と同じコンプライアンスと監査保護が適用されます。</span><span class="sxs-lookup"><span data-stu-id="c6cba-111">Guest user content and activities are under the same compliance and auditing protection as the rest of Office 365.</span></span>

<span data-ttu-id="c6cba-112">チーム所有者は、新しいゲストを招待し、既存のディレクトリゲストユーザーをチームに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="c6cba-112">Team owners can invite new guests and add existing directory guest users to their teams.</span></span> <span data-ttu-id="c6cba-113">チーム所有者は、チーム**管理チーム\*\*\*\*でゲスト** > ユーザーを特定し、**組織全体の設定** > を通じてゲストのチャネル関連機能を設定することができます。ゲスト**アクセス**を許可すると、ゲストの作成、更新、および次の図に示すように、チャネルを削除します。</span><span class="sxs-lookup"><span data-stu-id="c6cba-113">Team owners can identify guest users via **Teams** > **Manage teams**, and set channel-related capabilities for guests via **Org-wide settings** > **Guest access**, including allowing guests to create, update, and delete channels, as shown in the following illustration.</span></span>

![Teams でのゲストのアクセス権の設定](media/manage-guest-access-image1.png)
  
<span data-ttu-id="c6cba-115">Azure Active Directory (Azure AD) ポータルを使用して、ゲストと、Office 365 および Teams リソースへのアクセスを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="c6cba-115">You can use the Azure Active Directory (Azure AD) portal to manage guests and their access to Office 365 and Teams resources.</span></span> <span data-ttu-id="c6cba-116">Teams ゲストアクセスでは、id プロパティ、メンバーシップ、多要素認証の設定などのセキュリティ原則情報を保存する基盤として、Azure AD のビジネス間 (B2B) コラボレーション機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="c6cba-116">Teams guest access makes use of Azure AD business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="c6cba-117">Azure AD b2b の詳細については、「 [AZURE AD b2b コラボレーションの](https://go.microsoft.com/fwlink/p/?linkid=853011)概要」と「 [AZURE Active Directory b2b コラボレーション](https://go.microsoft.com/fwlink/p/?linkid=853020)に関する faq」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6cba-117">To learn more about Azure AD B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>

> [!NOTE]
> <span data-ttu-id="c6cba-118">Microsoft Teams では、ゲストユーザーによるテナントへの追加を許可または禁止するために、Azure AD の外部設定を常に使用しています。</span><span class="sxs-lookup"><span data-stu-id="c6cba-118">Microsoft Teams always honors Azure AD external settings to allow or prevent guest user additions to the tenant.</span></span> <span data-ttu-id="c6cba-119">詳細については、「 [Microsoft Teams でゲストアクセスを承認](Teams-dependencies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6cba-119">For more details, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
  
## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="c6cba-120">ゲスト アクセスと外部アクセス (フェデレーション)</span><span class="sxs-lookup"><span data-stu-id="c6cba-120">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="review-guest-access-periodically"></a><span data-ttu-id="c6cba-121">ゲスト アクセスを定期的にレビューする</span><span class="sxs-lookup"><span data-stu-id="c6cba-121">Review guest access periodically</span></span>

<span data-ttu-id="c6cba-122">Teams では、ライセンスを持っている各ユーザーごとに 5 人のゲストを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="c6cba-122">In Teams, you can add 5 guests for each licensed user.</span></span> <span data-ttu-id="c6cba-123">この制限のため、またはテナントを最新の状態に維持する必要があるため、ゲスト アクセスを定期的にレビューして、アクセスする必要がなくなったユーザーを識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6cba-123">Because of this limitation, or because you want to keep your tenant up to date, you should review guest access periodically to identify users who have access that they don't need anymore.</span></span> <span data-ttu-id="c6cba-124">Azure AD を使用して、アプリケーションに割り当てられているグループメンバーまたはユーザーのアクセスレビューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c6cba-124">You can use Azure AD to create an access review for group members or users assigned to an application.</span></span> <span data-ttu-id="c6cba-125">反復的なアクセス レビューを作成することで、時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="c6cba-125">Creating recurring access reviews can save you time.</span></span> <span data-ttu-id="c6cba-126">アプリケーションにアクセスできるユーザー、またはメンバーのグループであるユーザーを定期的にレビューする必要がある場合は、それらのレビューの頻度を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="c6cba-126">If you need to routinely review users who have access to an application or are members of a group, you can define the frequency of those reviews.</span></span> 

<span data-ttu-id="c6cba-127">ゲスト アクセスのレビューを自分自身で実行したり、ゲストにメンバーシップのレビューを求めたり、アプリケーション所有者またはビジネス意思決定者に対してアクセス レビューを実行するよう求めたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="c6cba-127">You can perform a guest access review yourself, ask guests to review their own membership, or ask an application owner or business decision maker to perform the access review.</span></span> <span data-ttu-id="c6cba-128">ゲスト アクセス レビューを実行するために、Azure ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6cba-128">You use the Azure portal to perform guest access reviews.</span></span> <span data-ttu-id="c6cba-129">詳細については、「[Azure AD アクセス レビューでゲスト アクセスを管理する](https://docs.microsoft.com/en-us/azure/active-directory/governance/manage-guest-access-with-access-reviews)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c6cba-129">For more information, see [Manage guest access with Azure AD access reviews](https://docs.microsoft.com/en-us/azure/active-directory/governance/manage-guest-access-with-access-reviews).</span></span>

###  <a name="prerequisites"></a><span data-ttu-id="c6cba-130">前提条件</span><span class="sxs-lookup"><span data-stu-id="c6cba-130">Prerequisites</span></span>

<span data-ttu-id="c6cba-131">アクセス レビューは、Microsoft Enterprise Mobility + Security E5 に含まれている Azure AD の Premium P2 エディションで利用することができます。</span><span class="sxs-lookup"><span data-stu-id="c6cba-131">Access reviews are available with the Premium P2 edition of Azure AD, which is included in Microsoft Enterprise Mobility + Security, E5.</span></span> <span data-ttu-id="c6cba-132">詳細については、「 [Azure Active Directory のエディション](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6cba-132">For more information, see [Azure Active Directory editions](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="c6cba-133">レビューを作成したり、レビューを記入したり、アクセスを承認したりすることでこの機能とやり取りを行う各ユーザーには、ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="c6cba-133">Each user who interacts with this feature by creating a review, filling out a review, or confirming their access, must have a license.</span></span>

<span data-ttu-id="c6cba-134">Teams では追加することができるゲストの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="c6cba-134">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="c6cba-135">ただし、テナントに追加することができるゲストの合計数は、ご利用の AAD ライセンスによって許可されるものに基づきます。</span><span class="sxs-lookup"><span data-stu-id="c6cba-135">However, the total number of guests that can be added to your tenant is based on what your AAD licensing allows.</span></span> <span data-ttu-id="c6cba-136">詳しくは、「[Azure Active Directory B2B コラボレーションのライセンスに関するガイダンス](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c6cba-136">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span></span>

## <a name="guest-access-latencies"></a><span data-ttu-id="c6cba-137">ゲスト アクセスの遅延</span><span class="sxs-lookup"><span data-stu-id="c6cba-137">Guest access latencies</span></span>

<span data-ttu-id="c6cba-138">ゲスト設定は Azure AD で設定されています。</span><span class="sxs-lookup"><span data-stu-id="c6cba-138">The guest settings are set in Azure AD.</span></span> <span data-ttu-id="c6cba-139">その変更が Office 365 組織全体で有効になるまでに 2 時間から 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="c6cba-139">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="c6cba-140">ユーザーがチームにゲストを追加しようとするときに「Contact your administrator (管理者にお問い合わせください)」というメッセージが表示される場合、ゲスト機能が使用できる状態になっていないか、設定が有効になっていないかのいずれかの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c6cba-140">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings aren't effective yet.</span></span>

## <a name="more-information"></a><span data-ttu-id="c6cba-141">詳細情報</span><span class="sxs-lookup"><span data-stu-id="c6cba-141">More information</span></span>

<span data-ttu-id="c6cba-142">ゲスト アクセスを管理するために PowerShell を使用する方法の詳細については、「[PowerShell を使用してチームへのゲスト アクセスを制御する](guest-access-powershell.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c6cba-142">For information about using PowerShell to manage guest access, see [Use PowerShell to control guest access to a team](guest-access-powershell.md).</span></span>


