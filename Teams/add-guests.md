---
title: チームにゲストを追加する
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 01/31/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
description: 組織に新しいゲスト ユーザーを追加するために管理者が利用できる Microsoft Teams デスクトップ、Web クライアント、Azure Active Directory B2B コラボレーション ポータルなどのツールについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 27f1f344313111561c9f1c3a5e57dc1bd0ae20cb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202873"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="f0902-103">チームにゲストを追加する</span><span class="sxs-lookup"><span data-stu-id="f0902-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="f0902-104">ビジネスやコンシューマー電子メール アカウントを Outlook、Gmail、またはその他のユーザーなど、すべてのユーザーは、チームにゲストとして参加できます。</span><span class="sxs-lookup"><span data-stu-id="f0902-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="f0902-105">管理者として、複数の方法で組織に新しいゲスト ユーザーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="f0902-105">As an admin, you can add a new guest user to the organization in a couple ways:</span></span> 
- <span data-ttu-id="f0902-106">チームの所有者であるグローバル管理者は、Microsoft Teams デスクトップまたは Web クライアントのいずれかを使用してチームにゲストを追加できます。</span><span class="sxs-lookup"><span data-stu-id="f0902-106">Global admins who are owners of a team and owners of a team can add a guest to a team through either the Microsoft Teams desktop or the web clients.</span></span> <span data-ttu-id="f0902-107">詳細については、[チームに追加の来園者](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)を確認します。</span><span class="sxs-lookup"><span data-stu-id="f0902-107">For more details, check out [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)</span></span>
- <span data-ttu-id="f0902-108">Azure Active Directory B2B コラボレーションを使用して組織にゲストを追加します。</span><span class="sxs-lookup"><span data-stu-id="f0902-108">Add guests to your organization through Azure Active Directory B2B collaboration.</span></span> <span data-ttu-id="f0902-109">Azure Active Directory B2B コラボレーションを使用すると、グローバル管理者は、2000 行以下のカンマ区切り (CSV) ファイルを B2B コラボレーション ポータルにアップロードすることで、複数の外部ユーザーを招待、承認できます。</span><span class="sxs-lookup"><span data-stu-id="f0902-109">Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="f0902-110">詳細については、「[Azure Active Directory B2B コラボレーション](https://go.microsoft.com/fwlink/p/?linkid=826383)」をご覧ください</span><span class="sxs-lookup"><span data-stu-id="f0902-110">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="f0902-111">Azure Active Directory B2B コラボレーションでは、組織は B2B ユーザーに対して条件付きアクセスと多要素認証 (MFA) ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="f0902-111">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="f0902-112">このポリシーは、フルタイムの従業員や組織のメンバーに対して有効にするのと同じ方法で、テナント レベル、アプリ レベルまたは個々のユーザー レベルで適用できます。</span><span class="sxs-lookup"><span data-stu-id="f0902-112">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="f0902-113">こうしたポリシーはリソース組織で実施します。</span><span class="sxs-lookup"><span data-stu-id="f0902-113">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="f0902-114">詳細については、「[B2B コラボレーション ユーザーの条件付きアクセス](https://go.microsoft.com/fwlink/?linkid=857454)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f0902-114">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="f0902-115">個別にゲスト ユーザーを拒否することはできません。</span><span class="sxs-lookup"><span data-stu-id="f0902-115">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="f0902-116">Azure Active Directory の B2B、Office 365 グループ、または SharePoint Online を使用して追加されているゲスト ユーザーは、移動する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="f0902-116">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups, or SharePoint Online are ready to go.</span></span> <span data-ttu-id="f0902-117">Office 365 管理者またはチーム所有者は所有するチームにこのゲストを追加できます。</span><span class="sxs-lookup"><span data-stu-id="f0902-117">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="f0902-118">チームが Office 365 グループにすでに追加されており、ゲストがそのグループに追加される場合、そのゲストはチームにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f0902-118">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="f0902-119">Office 365 グループを介してゲストを追加すると、そのゲストへの招待状メールは生成されません。そのため、チームの他のユーザーがそのゲストに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0902-119">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="f0902-120">ゲストにも [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) と [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) のサービスの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f0902-120">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="f0902-121">ゲストの追加は、Azure Active Directory または Office 365 セキュリティ &amp; コンプライアンス センターで追跡できます。</span><span class="sxs-lookup"><span data-stu-id="f0902-121">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="f0902-122">Microsoft Teams でのゲストの追加は監査され、「Added member to group (グループにメンバーを追加しました)」という Azure AD グループ管理アクティビティとして記録されます。</span><span class="sxs-lookup"><span data-stu-id="f0902-122">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="f0902-123">詳細については、「[B2B コラボレーション ユーザーの監査およびレポート](https://go.microsoft.com/fwlink/p/?linkid=858884)」と「[Office 365 のセキュリティ センター &amp; コンプライアンス センターで監査ログを検索する](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f0902-123">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="f0902-124">ゲスト アクセスと外部アクセス (フェデレーション)</span><span class="sxs-lookup"><span data-stu-id="f0902-124">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="f0902-125">詳細情報</span><span class="sxs-lookup"><span data-stu-id="f0902-125">More information</span></span>

[<span data-ttu-id="f0902-126">Microsoft Teams でゲスト アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="f0902-126">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="f0902-127">またはマイクロソフトのチームでのゲスト アクセスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f0902-127">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="f0902-128">PowerShell を使用してチームへのゲスト アクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="f0902-128">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)
