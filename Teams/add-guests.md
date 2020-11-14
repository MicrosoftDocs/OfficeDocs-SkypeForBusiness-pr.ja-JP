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
description: 管理者は、Microsoft Teams デスクトップ、Web クライアント、Azure Active Directory B2B コラボレーション ポータルなどのツールで、組織に新しいゲスト ユーザーを追加する方法について学習することができます。
ms.openlocfilehash: 21f8e733a87474888f2b33f8a23a063fa00b4b11
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030813"
---
# <a name="add-a-guest-to-a-team"></a><span data-ttu-id="bce30-103">チームにゲストを追加する</span><span class="sxs-lookup"><span data-stu-id="bce30-103">Add a guest to a team</span></span>

<span data-ttu-id="bce30-104">Outlook、Gmail などの勤務先または通常のメール アカウントを持っているユーザーは、ゲストとして Teams に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="bce30-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="bce30-105">管理者は、新しいゲスト ユーザーを複数の方法で組織に追加できます。</span><span class="sxs-lookup"><span data-stu-id="bce30-105">As an admin, you can add a new guest user to the organization in a couple of ways:</span></span>

- <span data-ttu-id="bce30-106">グローバル管理者または Teams 管理者とチーム所有者は、Teams クライアントまたは Teams 管理センターでチームにゲストを追加できます。</span><span class="sxs-lookup"><span data-stu-id="bce30-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="bce30-107">詳細については、「[ゲストをチームに追加する](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bce30-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="bce30-108">ゲスト アクセスをまだ設定していない場合は、「[チームでゲストと共同で作業する](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)」の手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="bce30-108">If you haven't set up guest access yet, go through the steps in the [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

- <span data-ttu-id="bce30-109">Azure Active Directory (Azure AD) B2B コラボレーションを使用して組織にゲストを追加する。</span><span class="sxs-lookup"><span data-stu-id="bce30-109">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="bce30-110">詳細については、「 [クイックスタート: Azure ポータルのディレクトリにゲストユーザーを追加する」](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bce30-110">For details, check out [Quickstart: Add guest users to your directory in the Azure portal](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

<span data-ttu-id="bce30-111">管理者は、"ゲスト招待元" ロールを割り当てることで、組織内の他のユーザーにゲストを追加する権限を委任することもできます。</span><span class="sxs-lookup"><span data-stu-id="bce30-111">Admins can also delegate permissions to add guests to others in their organization by assigning the Guest Inviter role.</span></span> <span data-ttu-id="bce30-112">詳細については、「[B2B の外部コラボレーションを有効にしてゲストを招待できるユーザー管理する](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bce30-112">For more information, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span>

<span data-ttu-id="bce30-113">Azure AD B2B コラボレーションを使用すると、組織は B2B ユーザーに対して条件付きアクセスと多要素認証 (MFA) ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="bce30-113">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="bce30-114">これらのポリシーは、組織のフルタイムの従業員とメンバーに対して有効にするのと同じ方法で、テナント レベル、アプリ レベル、または個々のユーザー レベルで適用できます。</span><span class="sxs-lookup"><span data-stu-id="bce30-114">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="bce30-115">こうしたポリシーはリソース組織で実施します。</span><span class="sxs-lookup"><span data-stu-id="bce30-115">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="bce30-116">詳細については、「[B2B コラボレーション ユーザーの条件付きアクセス](https://go.microsoft.com/fwlink/?linkid=857454)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bce30-116">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="bce30-117">個別にゲスト ユーザーを拒否することはできません。</span><span class="sxs-lookup"><span data-stu-id="bce30-117">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="bce30-118">Azure AD B2B、Microsoft 365 グループ、または SharePoint を使用して既に追加したゲストユーザーは、準備ができています。</span><span class="sxs-lookup"><span data-stu-id="bce30-118">Guest users you have already added via Azure AD B2B, Microsoft 365 Groups, or SharePoint are ready to go.</span></span> <span data-ttu-id="bce30-119">Microsoft 365 管理者またはチーム所有者は、これらのゲストをそれぞれのチームに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="bce30-119">The Microsoft 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="bce30-120">チームに関連付けられている Microsoft 365 グループにゲストを直接追加した場合、ゲストはチームへのアクセス権を取得しますが、Microsoft 365 グループはゲストに招待メールを生成しないので、チームのメンバーがゲストに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bce30-120">If add a guest directly to the Microsoft 365 group associated with a team, the guest will get access to the team but the Microsoft 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="bce30-121">ゲストにも [ Microsoft 365 または Office 365 ](https://go.microsoft.com/fwlink/p/?linkid=282347) と [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) のサービスの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="bce30-121">Guests are subject to  [Microsoft 365 or Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="bce30-122">ゲストの追加は、Azure AD または Microsoft 365 セキュリティ センターで追跡できます。</span><span class="sxs-lookup"><span data-stu-id="bce30-122">You can track guest additions in Azure AD or the Microsoft 365 security center.</span></span> <span data-ttu-id="bce30-123">Microsoft Teams でのゲストの追加は監査され、「Added member to group (グループにメンバーを追加しました)」という Azure AD グループ管理アクティビティとして記録されます。</span><span class="sxs-lookup"><span data-stu-id="bce30-123">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="bce30-124">詳細については、「 [B2B コラボレーションユーザーを監査および報告する](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) 」と「 [コンプライアンスセンターで監査ログを検索](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bce30-124">For more details, see [Auditing and reporting a B2B collaboration user](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) and [Search the audit log in the compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>


## <a name="related-topics"></a><span data-ttu-id="bce30-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="bce30-125">Related topics</span></span>

[<span data-ttu-id="bce30-126">Microsoft Teams でゲスト アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="bce30-126">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)

[<span data-ttu-id="bce30-127">Microsoft Teams へのゲスト アクセスをオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="bce30-127">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)
