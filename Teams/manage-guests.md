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
description: 初めてのチームとチャネルを作成する方法、早期導入企業、使用状況とフィードバックを監視する方法、組織全体のロールアウトを計画するためのリソースを取得する方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4751f274e4bc7a874c1469041787d7d145c11bb8
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637666"
---
<a name="manage-guest-access-in-microsoft-teams"></a><span data-ttu-id="0b196-103">Microsoft Teams でのゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="0b196-103">Manage guest access in Microsoft Teams</span></span>
======================================

> [!IMPORTANT]
> <span data-ttu-id="0b196-104">変更が反映されるまでに数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0b196-104">You may have to wait a few hours for your changes to take effect.</span></span> 

<span data-ttu-id="0b196-105">**ゲスト**は、microsoft Teams で、すべての Microsoft 365 ビジネス標準、Office 365 Enterprise、Microsoft 365 Business Basic、Office 365 エデュケーションサブスクリプションに含まれているユーザーの種類です。</span><span class="sxs-lookup"><span data-stu-id="0b196-105">**Guest** is a user type in Microsoft Teams that is included with all Microsoft 365 Business Standard, Office 365 Enterprise, Microsoft 365 Business Basic, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="0b196-106">追加の Microsoft 365 または Office 365 のライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="0b196-106">No additional Microsoft 365 or Office 365 license is necessary.</span></span> <span data-ttu-id="0b196-107">[ゲスト アクセス ライセンス](#guest-access-licensing-limits)の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b196-107">Read more about [guest access licensing](#guest-access-licensing-limits) below.</span></span>

<span data-ttu-id="0b196-108">Teams のゲスト アクセスはテナント レベルの設定であり、既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="0b196-108">Teams guest access is a tenant-level setting and is turned off by default.</span></span> <span data-ttu-id="0b196-109">ゲスト アクセスをオンにする方法の詳細については、「[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)」を参照するか、[ゲスト アクセスのチェックリスト](guest-access-checklist.md)を使用してセットアップの手順をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="0b196-109">For details about how to turn on guest access, see [Turn on or turn off guest access to Teams](set-up-guests.md), or use the [Guest access checklist ](guest-access-checklist.md) to walk you through the setup.</span></span>

<span data-ttu-id="0b196-110">ゲスト アクセスをオンにした後、「[組織の Microsoft Teams の設定を管理する](enable-features-office-365.md)」および「[新しい Microsoft Teams 管理センターへの移行中に Teams を管理する](manage-teams-skypeforbusiness-admin-center.md)」に記載されている制御を介してゲストの設定を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="0b196-110">After guest access is turned on, you can configure settings for guests using the controls described in [Manage Teams settings for your organization](enable-features-office-365.md) and [Manage Teams during the transition to the new Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md).</span></span>     
    
<span data-ttu-id="0b196-111">IT 管理者は、テナント レベルでのゲストの追加、ゲスト ユーザー ポリシーと権限の設定と管理、およびゲスト ユーザーのアクティビティに関するレポートの取得を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0b196-111">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, and pull reports on guest user activity.</span></span> <span data-ttu-id="0b196-112">これらの制御は、Teams 管理センターで利用可能です。</span><span class="sxs-lookup"><span data-stu-id="0b196-112">These controls are available in the Teams admin center.</span></span> <span data-ttu-id="0b196-113">ゲストユーザーのコンテンツとアクティビティは、Microsoft 365 または Office 365 の他の部分と同じコンプライアンスおよび監査保護の対象となります。</span><span class="sxs-lookup"><span data-stu-id="0b196-113">Guest user content and activities fall under the same compliance and auditing protection as the rest of Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="0b196-114">チーム所有者は、Teams 管理センターで自分が所有するチームに新しいゲストを招待したり、既存のディレクトリ ゲスト ユーザーを追加したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="0b196-114">Team owners can invite new guests and add existing directory guest users to their teams in the Teams admin center.</span></span> <span data-ttu-id="0b196-115">**[Teams]**  >  **[チームの管理]** ページでゲスト ユーザーを特定し、**[組織全体の設定]**  >  **[ゲスト アクセス]** ページでゲストに対してチャネル関連の機能を設定します。</span><span class="sxs-lookup"><span data-stu-id="0b196-115">Identify guest users on the **Teams** > **Manage teams** page, and set channel-related capabilities for guests on the  **Org-wide settings** > **Guest access** page.</span></span> <span data-ttu-id="0b196-116">次の図に示すように、設定には、ゲストにチャネルを作成、更新、削除することを許可することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0b196-116">Settings include allowing guests to create, update, and delete channels, as shown in the following illustration.</span></span>

![Teams でのゲストのアクセス権の設定](media/manage-guest-access-image1.png)
  
<span data-ttu-id="0b196-118">Azure Active Directory (Azure AD) ポータルを使用して、ゲストと Microsoft 365 または Office 365 および Teams のリソースへのアクセスを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="0b196-118">You can use the Azure Active Directory (Azure AD) portal to manage guests and their access to Microsoft 365 or Office 365 and Teams resources.</span></span> <span data-ttu-id="0b196-119">Teams のゲスト アクセスでは、Azure AD ビジネス ツー ビジネス (B2B) コラボレーション機能を基本インフラストラクチャとして活用して、ID プロパティ、メンバーシップ、多要素認証設定といったセキュリティの原則情報を保管します。</span><span class="sxs-lookup"><span data-stu-id="0b196-119">Teams guest access makes use of Azure AD business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="0b196-120">Azure AD B2B の詳細については、「[Azure AD B2B コラボレーションとは](https://go.microsoft.com/fwlink/p/?linkid=853011)」と「[Azure Active Directory B2B コラボレーションの FAQ](https://go.microsoft.com/fwlink/p/?linkid=853020)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0b196-120">To learn more about Azure AD B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>

> [!NOTE]
> <span data-ttu-id="0b196-121">Microsoft Teams は、テナントへのゲスト ユーザーの追加を許可または禁止するために、常に Azure AD の外部設定を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="0b196-121">Microsoft Teams always honors Azure AD external settings to allow or prevent guest user additions to the tenant.</span></span> <span data-ttu-id="0b196-122">詳細については、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0b196-122">For more details, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>


## <a name="guest-access-licensing-limits"></a><span data-ttu-id="0b196-123">ゲスト アクセス ライセンスの制限</span><span class="sxs-lookup"><span data-stu-id="0b196-123">Guest access licensing limits</span></span>

<span data-ttu-id="0b196-124">Teams では追加することができるゲストの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="0b196-124">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="0b196-125">ただし、テナントに追加することができるゲストの合計数は、ご利用の Azure AD ライセンスによって許可されるものに基づきます。通常はライセンス ユーザーごとに 5 人です。</span><span class="sxs-lookup"><span data-stu-id="0b196-125">However, the total number of guests that can be added to your tenant is based on what your Azure AD licensing allows - usually 5 guests per licensed user.</span></span> <span data-ttu-id="0b196-126">詳細については、「[Azure AD B2B コラボレーションのライセンス](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)」に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b196-126">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>

<span data-ttu-id="0b196-127">これらのライセンスの制限のため (およびテナントを最新の状態に維持する必要があるため)、ゲスト アクセスを定期的にレビューして、アクセスする必要がなくなったユーザーを識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b196-127">Because of these licensing limitations (and to keep your tenant up-to-date), you should review guest access periodically to identify users who have access that they don't need anymore.</span></span> <span data-ttu-id="0b196-128">Azure AD を使用してアプリケーションに割り当てられたグループ メンバーまたはユーザーに対するアクセス レビューを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="0b196-128">You can use Azure AD to create an access review for group members or users assigned to an application.</span></span> <span data-ttu-id="0b196-129">反復的なアクセス レビューを作成することで、時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="0b196-129">Creating recurring access reviews can save you time.</span></span> <span data-ttu-id="0b196-130">アプリケーションにアクセスできるユーザー、またはメンバーのグループであるユーザーを定期的にレビューする必要がある場合は、それらのレビューの頻度を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="0b196-130">If you need to routinely review users who have access to an application or are members of a group, you can define the frequency of those reviews.</span></span> 

<span data-ttu-id="0b196-131">ゲスト アクセスのレビューを自分自身で実行したり、ゲストにメンバーシップのレビューを求めたり、アプリケーション所有者またはビジネス意思決定者に対してアクセス レビューを実行するよう求めたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="0b196-131">You can perform a guest access review yourself, ask guests to review their own membership, or ask an application owner or business decision maker to perform the access review.</span></span> <span data-ttu-id="0b196-132">ゲスト アクセス レビューを実行するために、Azure ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b196-132">Use the Azure portal to perform guest access reviews.</span></span> <span data-ttu-id="0b196-133">詳細については、「[Azure AD アクセス レビューでゲスト アクセスを管理する](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0b196-133">For more information, see [Manage guest access with Azure AD access reviews](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).</span></span>

###  <a name="prerequisites-for-azure-ad-access-reviews"></a><span data-ttu-id="0b196-134">Azure AD アクセス レビューの前提条件</span><span class="sxs-lookup"><span data-stu-id="0b196-134">Prerequisites for Azure AD access reviews</span></span>

<span data-ttu-id="0b196-135">アクセス レビューは、Microsoft Enterprise Mobility + Security E5 に含まれている Azure AD の Premium P2 エディションで利用することができます。</span><span class="sxs-lookup"><span data-stu-id="0b196-135">Access reviews are available with the Premium P2 edition of Azure AD, which is included in Microsoft Enterprise Mobility + Security, E5.</span></span> <span data-ttu-id="0b196-136">詳細については、「[Azure Active Directory のエディション](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b196-136">For more information, see [Azure Active Directory editions](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="0b196-137">レビューを作成したり、レビューを記入したり、アクセスを承認したりすることでこの機能とやり取りを行う各ユーザーには、ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="0b196-137">Each user who interacts with this feature by creating a review, filling out a review, or confirming their access, must have a license.</span></span>



## <a name="lag-time-for-guest-access-settings-to-take-effect"></a><span data-ttu-id="0b196-138">ゲスト アクセス設定が有効になるまでのラグ タイム</span><span class="sxs-lookup"><span data-stu-id="0b196-138">Lag time for guest access settings to take effect</span></span>

<span data-ttu-id="0b196-139">Azure Active Directory のゲストアクセス設定の場合、変更が Microsoft 365 または Office 365 全体で有効になるまでに数時間かかります。</span><span class="sxs-lookup"><span data-stu-id="0b196-139">For the guest access settings in Azure Active Directory, it takes a few hours for the changes to take effect across Microsoft 365 or Office 365.</span></span> <span data-ttu-id="0b196-140">ユーザーがチームにゲストを追加しようとするときに「Contact your administrator (管理者にお問い合わせください)」というメッセージが表示される場合、ゲスト機能がオンになっていないか、設定が有効になっていないかのいずれかの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0b196-140">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been turned on or the settings aren't effective yet.</span></span> <span data-ttu-id="0b196-141">ゲスト アクセスの設定の問題に関するヘルプについては、「[Teams でのゲスト アクセスのトラブルシューティング](troubleshoot-guest-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b196-141">For help with problems setting up guest access, read [Troubleshoot guest access in Teams](troubleshoot-guest-access.md).</span></span>

  
## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="0b196-142">外部アクセス (フェデレーション) とゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="0b196-142">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="0b196-143">詳細情報</span><span class="sxs-lookup"><span data-stu-id="0b196-143">More information</span></span>

<span data-ttu-id="0b196-144">ゲスト アクセスを管理するために PowerShell を使用する方法の詳細については、「[PowerShell を使用してチームへのゲスト アクセスを制御する](guest-access-powershell.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0b196-144">For information about using PowerShell to manage guest access, see [Use PowerShell to control guest access to a team](guest-access-powershell.md).</span></span>


