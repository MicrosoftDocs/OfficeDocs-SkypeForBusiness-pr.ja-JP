---
title: Microsoft Teams でのゲスト アクセスを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: IT 管理者は、テナントレベルでのゲストの追加、ゲスト ユーザー ポリシーと権限の設定と管理、ゲストを招待できるユーザーの判別、ゲスト ユーザーのアクティビティに関するレポートの取得を行うことができます。
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef091eb926301e6dd9d3ac27d7c62486d93075a1
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834777"
---
<a name="manage-guest-access-in-microsoft-teams"></a><span data-ttu-id="5e51c-103">Microsoft Teams でのゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="5e51c-103">Manage guest access in Microsoft Teams</span></span>
======================================

> [!IMPORTANT]
> <span data-ttu-id="5e51c-104">変更が有効になるまで最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="5e51c-104">You may have to wait up to 24 hours for your changes to take effect.</span></span> 

<span data-ttu-id="5e51c-105">**ゲスト**は、すべての Office 365 Business Premium、Office 365 Enterprise、Office 365 Business Essentials、および Office 365 エデュケーションサブスクリプションに含まれている、Microsoft Teams のユーザーの種類です。</span><span class="sxs-lookup"><span data-stu-id="5e51c-105">**Guest** is a user type in Microsoft Teams that is included with all Office 365 Business Premium, Office 365 Enterprise, Office 365 Business Essentials, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="5e51c-106">追加の Office 365 ライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="5e51c-106">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="5e51c-107">[ゲストアクセスライセンス](#guest-access-licensing-limits)の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e51c-107">Read more about [guest access licensing](#guest-access-licensing-limits) below.</span></span>

<span data-ttu-id="5e51c-108">Teams のゲスト アクセスはテナントレベルの設定であり、既定ではオフになっています。</span><span class="sxs-lookup"><span data-stu-id="5e51c-108">Teams guest access is a tenant-level setting and is turned off by default.</span></span> <span data-ttu-id="5e51c-109">ゲストアクセスを有効にする方法の詳細については、「 [Teams へのゲストアクセスを有効また](set-up-guests.md)は無効にする」を参照するか、[ゲストアクセスのチェックリスト](guest-access-checklist.md)を使用してセットアップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5e51c-109">For details about how to turn on guest access, see [Turn on or turn off guest access to Teams](set-up-guests.md), or use the [Guest access checklist ](guest-access-checklist.md) to walk you through the setup.</span></span>

<span data-ttu-id="5e51c-110">ゲストアクセスを有効にした後、「[組織のチーム設定を管理](enable-features-office-365.md)する」で説明されているコントロールを使用してゲストの設定を構成し、[新しい Microsoft Teams 管理センターへの移行中に teams を管理](manage-teams-skypeforbusiness-admin-center.md)することができます。</span><span class="sxs-lookup"><span data-stu-id="5e51c-110">After guest access is turned on, you can configure settings for guests using the controls described in [Manage Teams settings for your organization](enable-features-office-365.md) and [Manage Teams during the transition to the new Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md).</span></span>     
    
<span data-ttu-id="5e51c-111">IT 管理者は、テナント レベルでのゲストの追加、ゲスト ユーザー ポリシーと権限の設定と管理、およびゲスト ユーザーのアクティビティに関するレポートの取得を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5e51c-111">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, and pull reports on guest user activity.</span></span> <span data-ttu-id="5e51c-112">これらのコントロールは、Teams 管理センターで使用できます。</span><span class="sxs-lookup"><span data-stu-id="5e51c-112">These controls are available in the Teams admin center.</span></span> <span data-ttu-id="5e51c-113">ゲストユーザーのコンテンツとアクティビティは、Office 365 の他の部分と同じコンプライアンスおよび監査保護の対象となります。</span><span class="sxs-lookup"><span data-stu-id="5e51c-113">Guest user content and activities fall under the same compliance and auditing protection as the rest of Office 365.</span></span>

<span data-ttu-id="5e51c-114">チームの所有者は、新しいゲストを招待し、チーム管理センターで既存のディレクトリゲストユーザーを自分のチームに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="5e51c-114">Team owners can invite new guests and add existing directory guest users to their teams in the Teams admin center.</span></span> <span data-ttu-id="5e51c-115">**チーム** > **管理**ページでゲストユーザーを特定し、**組織全体** > の [**ゲストアクセス**の設定] ページでゲストのチャネル関連の機能を設定します。</span><span class="sxs-lookup"><span data-stu-id="5e51c-115">Identify guest users on the **Teams** > **Manage teams** page, and set channel-related capabilities for guests on the  **Org-wide settings** > **Guest access** page.</span></span> <span data-ttu-id="5e51c-116">[設定] には、次の図に示すように、ゲストによるチャネルの作成、更新、削除の許可が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e51c-116">Settings include allowing guests to create, update, and delete channels, as shown in the following illustration.</span></span>

![Teams でのゲストのアクセス権の設定](media/manage-guest-access-image1.png)
  
<span data-ttu-id="5e51c-118">Azure Active Directory (Azure AD) ポータルを使用して、ゲストと、Office 365 および Teams リソースへのアクセスを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="5e51c-118">You can use the Azure Active Directory (Azure AD) portal to manage guests and their access to Office 365 and Teams resources.</span></span> <span data-ttu-id="5e51c-119">Teams ゲストアクセスでは、id プロパティ、メンバーシップ、多要素認証の設定などのセキュリティ原則情報を保存する基盤として、Azure AD のビジネス間 (B2B) コラボレーション機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="5e51c-119">Teams guest access makes use of Azure AD business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="5e51c-120">Azure AD b2b の詳細については、「 [AZURE AD b2b コラボレーションの](https://go.microsoft.com/fwlink/p/?linkid=853011)概要」と「 [AZURE Active Directory b2b コラボレーション](https://go.microsoft.com/fwlink/p/?linkid=853020)に関する faq」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e51c-120">To learn more about Azure AD B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>

> [!NOTE]
> <span data-ttu-id="5e51c-121">Microsoft Teams では、ゲストユーザーによるテナントへの追加を許可または禁止するために、Azure AD の外部設定を常に使用しています。</span><span class="sxs-lookup"><span data-stu-id="5e51c-121">Microsoft Teams always honors Azure AD external settings to allow or prevent guest user additions to the tenant.</span></span> <span data-ttu-id="5e51c-122">詳細については、「 [Microsoft Teams でゲストアクセスを承認](Teams-dependencies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e51c-122">For more details, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>


## <a name="guest-access-licensing-limits"></a><span data-ttu-id="5e51c-123">ゲストアクセスライセンスの制限</span><span class="sxs-lookup"><span data-stu-id="5e51c-123">Guest access licensing limits</span></span>

<span data-ttu-id="5e51c-124">Teams では追加することができるゲストの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="5e51c-124">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="5e51c-125">ただし、テナントに追加することができるゲストの合計数は、ご利用の Azure AD ライセンスによって許可されるものに基づきます。通常はライセンス ユーザーごとに 5 人です。</span><span class="sxs-lookup"><span data-stu-id="5e51c-125">However, the total number of guests that can be added to your tenant is based on what your Azure AD licensing allows - usually 5 guests per licensed user.</span></span> <span data-ttu-id="5e51c-126">詳細については、「[Azure AD B2B コラボレーションのライセンス](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)」に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e51c-126">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>

<span data-ttu-id="5e51c-127">ライセンスの制限があるため (およびテナントを最新の状態に維持するため)、ゲストアクセスを定期的に確認して、必要のないアクセス権を持つユーザーを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e51c-127">Because of these licensing limitations (and to keep your tenant up-to-date), you should review guest access periodically to identify users who have access that they don't need anymore.</span></span> <span data-ttu-id="5e51c-128">Azure AD を使用して、アプリケーションに割り当てられているグループメンバーまたはユーザーのアクセスレビューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5e51c-128">You can use Azure AD to create an access review for group members or users assigned to an application.</span></span> <span data-ttu-id="5e51c-129">反復的なアクセス レビューを作成することで、時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="5e51c-129">Creating recurring access reviews can save you time.</span></span> <span data-ttu-id="5e51c-130">アプリケーションにアクセスできるユーザー、またはメンバーのグループであるユーザーを定期的にレビューする必要がある場合は、それらのレビューの頻度を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="5e51c-130">If you need to routinely review users who have access to an application or are members of a group, you can define the frequency of those reviews.</span></span> 

<span data-ttu-id="5e51c-131">ゲスト アクセスのレビューを自分自身で実行したり、ゲストにメンバーシップのレビューを求めたり、アプリケーション所有者またはビジネス意思決定者に対してアクセス レビューを実行するよう求めたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5e51c-131">You can perform a guest access review yourself, ask guests to review their own membership, or ask an application owner or business decision maker to perform the access review.</span></span> <span data-ttu-id="5e51c-132">Azure portal を使用して、ゲストアクセスレビューを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e51c-132">Use the Azure portal to perform guest access reviews.</span></span> <span data-ttu-id="5e51c-133">詳細については、「[Azure AD アクセス レビューでゲスト アクセスを管理する](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5e51c-133">For more information, see [Manage guest access with Azure AD access reviews](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).</span></span>

###  <a name="prerequisites-for-azure-ad-access-reviews"></a><span data-ttu-id="5e51c-134">Azure AD access レビューの前提条件</span><span class="sxs-lookup"><span data-stu-id="5e51c-134">Prerequisites for Azure AD access reviews</span></span>

<span data-ttu-id="5e51c-135">アクセス レビューは、Microsoft Enterprise Mobility + Security E5 に含まれている Azure AD の Premium P2 エディションで利用することができます。</span><span class="sxs-lookup"><span data-stu-id="5e51c-135">Access reviews are available with the Premium P2 edition of Azure AD, which is included in Microsoft Enterprise Mobility + Security, E5.</span></span> <span data-ttu-id="5e51c-136">詳細については、「 [Azure Active Directory のエディション](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e51c-136">For more information, see [Azure Active Directory editions](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="5e51c-137">レビューを作成したり、レビューを記入したり、アクセスを承認したりすることでこの機能とやり取りを行う各ユーザーには、ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="5e51c-137">Each user who interacts with this feature by creating a review, filling out a review, or confirming their access, must have a license.</span></span>



## <a name="lag-time-for-guest-access-settings-to-take-effect"></a><span data-ttu-id="5e51c-138">ゲストアクセスの設定が有効になるまでのラグタイム</span><span class="sxs-lookup"><span data-stu-id="5e51c-138">Lag time for guest access settings to take effect</span></span>

<span data-ttu-id="5e51c-139">Azure Active Directory のゲストアクセスの設定では、Office 365 組織全体で変更が反映されるまでに、2-24 時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="5e51c-139">For the guest access settings in Azure Active Directory, it takes 2-24 hours for the changes to take effect across your Office 365 organization.</span></span> <span data-ttu-id="5e51c-140">ユーザーがチームにゲストを追加しようとしたときに、"管理者に連絡してください" というメッセージが表示される場合は、ゲスト機能が有効になっていないか、設定がまだ有効になっていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5e51c-140">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been turned on or the settings aren't effective yet.</span></span> <span data-ttu-id="5e51c-141">ゲストアクセスの設定の問題については、「 [Teams でのゲストアクセスのトラブルシューティング](troubleshoot-guest-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e51c-141">For help with problems setting up guest access, read [Troubleshoot guest access in Teams](troubleshoot-guest-access.md).</span></span>

  
## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="5e51c-142">外部アクセス (フェデレーション) とゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="5e51c-142">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="5e51c-143">詳細情報</span><span class="sxs-lookup"><span data-stu-id="5e51c-143">More information</span></span>

<span data-ttu-id="5e51c-144">ゲスト アクセスを管理するために PowerShell を使用する方法の詳細については、「[PowerShell を使用してチームへのゲスト アクセスを制御する](guest-access-powershell.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5e51c-144">For information about using PowerShell to manage guest access, see [Use PowerShell to control guest access to a team](guest-access-powershell.md).</span></span>


