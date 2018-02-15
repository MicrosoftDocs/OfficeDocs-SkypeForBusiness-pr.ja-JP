---
title: "チームにゲストを追加する"
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 10/23/2017
ms.topic: article
ms.service: msteams
ms.reviewer: laal
description: "組織に新しいゲスト ユーザーを追加するために管理者が利用できる Microsoft Teams デスクトップ、Web クライアント、Azure Active Directory B2B コラボレーション ポータルなどのツールについて説明します。"
appliesto:
- Microsoft Teams
ms.openlocfilehash: 384572ee714d8fbf25f7b7640a4e5e9687324262
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2018
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="32d25-103">チームにゲストを追加する</span><span class="sxs-lookup"><span data-stu-id="32d25-103">Add a guest to a team</span></span>
=====================

<span data-ttu-id="32d25-104">Azure Active Directory に対応する電子メール アドレス、または Office 365 の職場または学校アカウントを持つユーザーのみをゲスト ユーザーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="32d25-104">Only users who have an email address corresponding to an Azure Active Directory or Office 365 work or school account can be added as a guest user.</span></span>


<span data-ttu-id="32d25-105">管理者として、複数の方法で組織に新しいゲスト ユーザーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="32d25-105">As an admin, you can add a new guest user to the organization in a couple ways:</span></span> 
- <span data-ttu-id="32d25-106">チームの所有者であるグローバル管理者は、Microsoft Teams デスクトップまたは Web クライアントのいずれかを使用してチームにゲストを追加できます。</span><span class="sxs-lookup"><span data-stu-id="32d25-106">Global admins who are owners of a team and owners of a team can add a guest to a team through either the Microsoft Teams desktop or the web clients.</span></span>
- <span data-ttu-id="32d25-107">Azure Active Directory B2B コラボレーションを使用して組織にゲストを追加します。</span><span class="sxs-lookup"><span data-stu-id="32d25-107">Add guests to your organization through Azure Active Directory B2B collaboration.</span></span> <span data-ttu-id="32d25-108">Azure Active Directory B2B コラボレーションを使用すると、グローバル管理者は、2000 行以下のカンマ区切り (CSV) ファイルを B2B コラボレーション ポータルにアップロードすることで、複数の外部ユーザーを招待、承認できます。</span><span class="sxs-lookup"><span data-stu-id="32d25-108">Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="32d25-109">詳細については、「[Azure Active Directory B2B コラボレーション](https://go.microsoft.com/fwlink/p/?linkid=826383)」をご覧ください</span><span class="sxs-lookup"><span data-stu-id="32d25-109">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>



<span data-ttu-id="32d25-110">Azure Active Directory B2B コラボレーションでは、組織は B2B ユーザーに対して条件付きアクセスと多要素認証 (MFA) ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="32d25-110">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="32d25-111">このポリシーは、フルタイムの従業員や組織のメンバーに対して有効にするのと同じ方法で、テナント レベル、アプリ レベルまたは個々のユーザー レベルで適用できます。</span><span class="sxs-lookup"><span data-stu-id="32d25-111">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="32d25-112">こうしたポリシーはリソース組織で実施します。</span><span class="sxs-lookup"><span data-stu-id="32d25-112">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="32d25-113">詳細については、「[B2B コラボレーション ユーザーの条件付きアクセス](https://go.microsoft.com/fwlink/?linkid=857454)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="32d25-113">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="32d25-114">個別にゲスト ユーザーを拒否することはできません。</span><span class="sxs-lookup"><span data-stu-id="32d25-114">Individual guest users can't be blocked.</span></span>



<span data-ttu-id="32d25-115">Azure Active Directory B2B、Office 365 グループまたは SharePoint Online を介してすでに追加しているゲスト ユーザーはすぐに利用できます。</span><span class="sxs-lookup"><span data-stu-id="32d25-115">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups or SharePoint Online are ready to go.</span></span> <span data-ttu-id="32d25-116">Office 365 管理者またはチーム所有者は所有するチームにこのゲストを追加できます。</span><span class="sxs-lookup"><span data-stu-id="32d25-116">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="32d25-117">チームが Office 365 グループにすでに追加されており、ゲストがそのグループに追加される場合、そのゲストはチームにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="32d25-117">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="32d25-118">Office 365 グループを介してゲストを追加すると、そのゲストへの招待状メールは生成されません。そのため、チームの他のユーザーがそのゲストに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32d25-118">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="32d25-119">ゲストにも [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) と [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) のサービスの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="32d25-119">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>



<span data-ttu-id="32d25-120">ゲストの追加は、Azure Active Directory または Office 365 セキュリティ &amp; コンプライアンス センターで追跡できます。</span><span class="sxs-lookup"><span data-stu-id="32d25-120">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="32d25-121">Microsoft Teams でのゲストの追加は監査され、「Added member to group (グループにメンバーを追加しました)」という Azure AD グループ管理アクティビティとして記録されます。</span><span class="sxs-lookup"><span data-stu-id="32d25-121">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="32d25-122">詳細については、「[B2B コラボレーション ユーザーの監査およびレポート](https://go.microsoft.com/fwlink/p/?linkid=858884)」と「[Office 365 のセキュリティ センター &amp; コンプライアンス センターで監査ログを検索する](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="32d25-122">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

