---
title: チームにゲストを追加する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
ms.reviewer: rafarhi
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: 管理者は、Microsoft Teams デスクトップと Web クライアントおよび Azure Active Directory B2B コラボレーション ポータルで組織に新しいゲストを追加する方法について説明します。
ms.openlocfilehash: 1d44aff9b62a5ba6de7c22499f5a20f187d7781b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109083"
---
# <a name="add-a-guest-to-a-team"></a><span data-ttu-id="1dbfa-103">チームにゲストを追加する</span><span class="sxs-lookup"><span data-stu-id="1dbfa-103">Add a guest to a team</span></span>

<span data-ttu-id="1dbfa-104">Outlook、Gmail などの勤務先または通常のメール アカウントを持っているユーザーは、ゲストとして Teams に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="1dbfa-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="1dbfa-105">管理者は、次の 2 つの方法で新しいゲストを組織に追加できます。</span><span class="sxs-lookup"><span data-stu-id="1dbfa-105">As an admin, you can add a new guest to the organization in a couple of ways:</span></span>

- <span data-ttu-id="1dbfa-106">グローバル管理者または Teams 管理者とチーム所有者は、Teams クライアントまたは Teams 管理センターでチームにゲストを追加できます。</span><span class="sxs-lookup"><span data-stu-id="1dbfa-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="1dbfa-107">詳細については、「[ゲストをチームに追加する](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dbfa-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="1dbfa-108">ゲスト アクセスをまだ設定していない場合は、「[チームでゲストと共同で作業する](/microsoft-365/solutions/collaborate-as-team)」の手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="1dbfa-108">If you haven't set up guest access yet, go through the steps in the [Collaborate with guests in a team](/microsoft-365/solutions/collaborate-as-team).</span></span>

- <span data-ttu-id="1dbfa-109">Azure Active Directory (Azure AD) B2B コラボレーションを使用して組織にゲストを追加する。</span><span class="sxs-lookup"><span data-stu-id="1dbfa-109">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="1dbfa-110">詳細については、「クイック スタート: Azure Portal のディレクトリにゲスト [を追加する」を参照してください](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)。</span><span class="sxs-lookup"><span data-stu-id="1dbfa-110">For details, check out [Quickstart: Add guests to your directory in the Azure portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

<span data-ttu-id="1dbfa-111">管理者は、"ゲスト招待元" ロールを割り当てることで、組織内の他のユーザーにゲストを追加する権限を委任することもできます。</span><span class="sxs-lookup"><span data-stu-id="1dbfa-111">Admins can also delegate permissions to add guests to others in their organization by assigning the Guest Inviter role.</span></span> <span data-ttu-id="1dbfa-112">詳細については、「[B2B の外部コラボレーションを有効にしてゲストを招待できるユーザー管理する](/azure/active-directory/external-identities/delegate-invitations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dbfa-112">For more information, see [Enable B2B external collaboration and manage who can invite guests](/azure/active-directory/external-identities/delegate-invitations).</span></span>

<span data-ttu-id="1dbfa-113">Azure AD B2B コラボレーションを使用すると、組織は B2B ユーザーに対して条件付きアクセスと多要素認証 (MFA) ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="1dbfa-113">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="1dbfa-114">これらのポリシーは、組織のフルタイムの従業員とメンバーに対して有効にするのと同じ方法で、テナント レベル、アプリ レベル、または個々のユーザー レベルで適用できます。</span><span class="sxs-lookup"><span data-stu-id="1dbfa-114">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="1dbfa-115">こうしたポリシーはリソース組織で実施します。</span><span class="sxs-lookup"><span data-stu-id="1dbfa-115">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="1dbfa-116">詳細については、「[B2B コラボレーション ユーザーの条件付きアクセス](/azure/active-directory/external-identities/conditional-access)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1dbfa-116">For more information, see  [Conditional access for B2B collaboration users](/azure/active-directory/external-identities/conditional-access).</span></span> <span data-ttu-id="1dbfa-117">個々のゲストをブロックできない。</span><span class="sxs-lookup"><span data-stu-id="1dbfa-117">Individual guests can't be blocked.</span></span>

<span data-ttu-id="1dbfa-118">Azure AD B2B、Microsoft 365 グループ、または SharePoint を介して追加したゲストは準備完了です。</span><span class="sxs-lookup"><span data-stu-id="1dbfa-118">Guests you have already added via Azure AD B2B, Microsoft 365 Groups, or SharePoint are ready to go.</span></span> <span data-ttu-id="1dbfa-119">Microsoft 365 管理者またはチーム所有者は、それらのゲストをそれぞれのチームに追加できます。</span><span class="sxs-lookup"><span data-stu-id="1dbfa-119">The Microsoft 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="1dbfa-120">チームに関連付けられている Microsoft 365 グループにゲストを直接追加すると、ゲストはチームにアクセスできますが、Microsoft 365 グループはゲストへの招待メールを生成しないので、チームの誰かがゲストに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1dbfa-120">If you add a guest directly to the Microsoft 365 group associated with a team, the guest will get access to the team but the Microsoft 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="1dbfa-121">ゲストにも [ Microsoft 365 または Office 365 ](/office365/servicedescriptions/office-365-service-descriptions-technet-library) と [Azure Active Directory](/azure/active-directory/external-identities/current-limitations) のサービスの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="1dbfa-121">Guests are subject to  [Microsoft 365 or Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library) and [Azure Active Directory](/azure/active-directory/external-identities/current-limitations) service limits.</span></span>

<span data-ttu-id="1dbfa-122">ゲストの追加は、Azure AD または Microsoft 365 セキュリティ センターで追跡できます。</span><span class="sxs-lookup"><span data-stu-id="1dbfa-122">You can track guest additions in Azure AD or the Microsoft 365 security center.</span></span> <span data-ttu-id="1dbfa-123">Microsoft Teams でのゲストの追加は監査され、「Added member to group (グループにメンバーを追加しました)」という Azure AD グループ管理アクティビティとして記録されます。</span><span class="sxs-lookup"><span data-stu-id="1dbfa-123">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="1dbfa-124">詳細については [、「B2B コラボレーション](/azure/active-directory/external-identities/auditing-and-reporting) ユーザーの監査とレポート」と「コンプライアンス センターで監査ログ [を検索する」を参照してください](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。</span><span class="sxs-lookup"><span data-stu-id="1dbfa-124">For more details, see [Auditing and reporting a B2B collaboration user](/azure/active-directory/external-identities/auditing-and-reporting) and [Search the audit log in the compliance Center](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>


## <a name="related-topics"></a><span data-ttu-id="1dbfa-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="1dbfa-125">Related topics</span></span>

[<span data-ttu-id="1dbfa-126">Microsoft Teams でゲスト アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="1dbfa-126">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)

[<span data-ttu-id="1dbfa-127">Microsoft Teams へのゲスト アクセスをオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="1dbfa-127">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)