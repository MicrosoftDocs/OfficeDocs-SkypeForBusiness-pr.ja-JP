---
title: チームにゲストを追加する
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
audience: ITPro
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
localization_priority: Priority
description: 組織に新しいゲスト ユーザーを追加するために管理者が利用できる Microsoft Teams デスクトップ、Web クライアント、Azure Active Directory B2B コラボレーション ポータルなどのツールについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: acf62fe23a5b22f2cbe07e94e073037e1f95b041
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236322"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="bd4e2-103">チームにゲストを追加する</span><span class="sxs-lookup"><span data-stu-id="bd4e2-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="bd4e2-104">Outlook、Gmail などの勤務先または通常のメール アカウントを持っているユーザーは、ゲストとして Teams に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="bd4e2-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="bd4e2-105">管理者は、新しいゲスト ユーザーを複数の方法で組織に追加できます。</span><span class="sxs-lookup"><span data-stu-id="bd4e2-105">As an admin, you can add a new guest user to the organization in a couple ways:</span></span>
- <span data-ttu-id="bd4e2-106">チームの所有者であるグローバル管理者は、Microsoft Teams デスクトップまたは Web クライアントのいずれかを使用してチームにゲストを追加できます。</span><span class="sxs-lookup"><span data-stu-id="bd4e2-106">Global admins who are owners of a team and owners of a team can add a guest to a team through either the Microsoft Teams desktop or the web clients.</span></span> <span data-ttu-id="bd4e2-107">詳細については、「[ゲストをチームに追加する](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd4e2-107">For more details, check out [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)</span></span>

> [!NOTE] 
> <span data-ttu-id="bd4e2-108">[**管理者と、ゲストの招待元ロールのユーザーのみが招待できる**] が有効な場合には、これは適用されません。</span><span class="sxs-lookup"><span data-stu-id="bd4e2-108">This does not apply when **Admins and users in the guest inviter role can invite** is enabled.</span></span> <span data-ttu-id="bd4e2-109">ゲストの招待元ロールは Teams ではサポートされていないためです。</span><span class="sxs-lookup"><span data-stu-id="bd4e2-109">This is because the guest invitor role isn't supported in Teams.</span></span>

- <span data-ttu-id="bd4e2-110">Azure Active Directory (Azure AD) B2B コラボレーションを使用して組織にゲストを追加する。</span><span class="sxs-lookup"><span data-stu-id="bd4e2-110">Add guests to your organization through Azure Active Directory B2B collaboration.</span></span> <span data-ttu-id="bd4e2-111">Azure AD B2B コラボレーションを使用すると、グローバル管理者は、2,000 行以下のカンマ区切り (CSV) ファイルを B2B コラボレーション ポータルにアップロードすることで、複数の外部ユーザーを招待、承認できます。</span><span class="sxs-lookup"><span data-stu-id="bd4e2-111">Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="bd4e2-112">詳細については、「[Azure Active Directory B2B コラボレーション](https://go.microsoft.com/fwlink/p/?linkid=826383)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd4e2-112">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="bd4e2-113">Azure AD B2B コラボレーションを使用すると、組織は B2B ユーザーに対して条件付きアクセスと多要素認証 (MFA) ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="bd4e2-113">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="bd4e2-114">これらのポリシーは、組織のフルタイムの従業員とメンバーに対して有効にするのと同じ方法で、テナント レベル、アプリ レベル、または個々のユーザー レベルで適用できます。</span><span class="sxs-lookup"><span data-stu-id="bd4e2-114">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="bd4e2-115">こうしたポリシーはリソース組織で実施します。</span><span class="sxs-lookup"><span data-stu-id="bd4e2-115">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="bd4e2-116">詳細については、「[B2B コラボレーション ユーザーの条件付きアクセス](https://go.microsoft.com/fwlink/?linkid=857454)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd4e2-116">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="bd4e2-117">個別にゲスト ユーザーを拒否することはできません。</span><span class="sxs-lookup"><span data-stu-id="bd4e2-117">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="bd4e2-118">Azure AD B2B、Office 365 グループまたは SharePoint Online 経由ですでに追加されたゲスト ユーザーは、すぐに利用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="bd4e2-118">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups or SharePoint Online are ready to go.</span></span> <span data-ttu-id="bd4e2-119">Office 365 管理者またはチーム所有者は所有するチームにこのゲストを追加できます。</span><span class="sxs-lookup"><span data-stu-id="bd4e2-119">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="bd4e2-120">チームが Office 365 グループにすでに追加されており、ゲストがそのグループに追加される場合、そのゲストはチームにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="bd4e2-120">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="bd4e2-121">Office 365 グループを介してゲストを追加すると、そのゲストへの招待状メールは生成されません。そのため、チームの他のユーザーがそのゲストに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd4e2-121">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="bd4e2-122">ゲストにも [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) と [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) のサービスの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="bd4e2-122">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="bd4e2-123">ゲストの追加は、Azure AD または Office 365 セキュリティ &amp; コンプライアンス センターで追跡できます。</span><span class="sxs-lookup"><span data-stu-id="bd4e2-123">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="bd4e2-124">Microsoft Teams でのゲストの追加は監査され、「Added member to group (グループにメンバーを追加しました)」という Azure AD グループ管理アクティビティとして記録されます。</span><span class="sxs-lookup"><span data-stu-id="bd4e2-124">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="bd4e2-125">詳細については、「[B2B コラボレーション ユーザーの監査およびレポート](https://go.microsoft.com/fwlink/p/?linkid=858884)」と「[Office 365 のセキュリティ センター &amp; コンプライアンス センターで監査ログを検索する](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd4e2-125">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="bd4e2-126">ゲスト アクセスと外部アクセス (フェデレーション)</span><span class="sxs-lookup"><span data-stu-id="bd4e2-126">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="bd4e2-127">詳細情報</span><span class="sxs-lookup"><span data-stu-id="bd4e2-127">More information</span></span>

[<span data-ttu-id="bd4e2-128">Microsoft Teams でゲスト アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="bd4e2-128">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
<span data-ttu-id="bd4e2-129">[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)</span><span class="sxs-lookup"><span data-stu-id="bd4e2-129">For more information, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span></br>
[<span data-ttu-id="bd4e2-130">PowerShell を使用してチームへのゲスト アクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="bd4e2-130">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)
