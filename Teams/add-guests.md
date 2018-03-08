---
title: "チームにゲストを追加します。"
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 10/23/2017
ms.topic: article
ms.service: msteams
description: "Microsoft チーム デスクトップと web クライアントと Azure Active Directory B2B コラボレーション ポータルなど、組織に新しいゲスト ユーザーを追加するには、管理者が利用できるツールについて説明します。"
ms.openlocfilehash: 2cff7bade024bf5324d729559a83974ea33681a8
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="8ee6c-103">チームにゲストを追加します。</span><span class="sxs-lookup"><span data-stu-id="8ee6c-103">Add a guest to a team</span></span>
=====================

<span data-ttu-id="8ee6c-104">Azure Active Directory または Office 365 に対応するメール アドレスを持つユーザーのみが動作するか、ゲスト ユーザーとして学校のアカウントを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="8ee6c-104">Only users who have an email address corresponding to an Azure Active Directory or Office 365 work or school account can be added as a guest user.</span></span>


<span data-ttu-id="8ee6c-105">管理者は、いくつかの方法で組織に新しいゲスト ユーザーを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="8ee6c-105">As an admin, you can add a new guest user to the organization in a couple ways:</span></span> 
- <span data-ttu-id="8ee6c-106">チームの所有者およびチームの所有者であるグローバル管理者は、Microsoft チーム デスクトップまたは web クライアントでチームにゲストを追加できます。</span><span class="sxs-lookup"><span data-stu-id="8ee6c-106">Global admins who are owners of a team and owners of a team can add a guest to a team through either the Microsoft Teams desktop or the web clients.</span></span>
- <span data-ttu-id="8ee6c-p101">Azure Active Directory B2B での共同作業を組織には、ゲストを追加します。Azure Active Directory B2B での共同作業には、グローバル管理者招待し、B2B コラボレーション ポータルに以内 2,000 行の値をカンマ区切り (CSV) ファイルをアップロード、外部ユーザーのセットを承認することができます。詳細については、確認[Azure Active Directory B2B での共同作業](https://go.microsoft.com/fwlink/p/?linkid=826383)してください。</span><span class="sxs-lookup"><span data-stu-id="8ee6c-p101">Add guests to your organization through Azure Active Directory B2B collaboration. Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal. For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>



<span data-ttu-id="8ee6c-p102">Azure Active Directory B2B の共同作業の組織は、条件付きのアクセスと B2B ユーザー向けの多要素認証 (MFA) ポリシーを適用できます。これらのポリシーは、フルタイムの従業員、および組織のメンバーが有効なことは、テナント、アプリ、または個々 のユーザー レベルで適用できます。リソースの組織でこのようなポリシーが適用されます。詳細については、[条件付き B2B での共同作業のユーザー アクセス](https://go.microsoft.com/fwlink/?linkid=857454)を参照してください。個々 のゲスト ユーザーがブロックされることはできません。</span><span class="sxs-lookup"><span data-stu-id="8ee6c-p102">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users. These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization. Such policies are enforced at the resource organization. For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454). Individual guest users can't be blocked.</span></span>



<span data-ttu-id="8ee6c-p103">ゲスト ユーザーの Azure Active Directory B2B、Office 365 のグループまたは SharePoint Online で既に追加したは、移動する準備が整いました。Office 365 管理者またはチームの所有者は、それぞれチームにこれらのゲストを追加できます。チームが、Office 365 のグループとは既にゲストがグループに追加される場合は、ゲストはチームへのアクセスを取得します。Office 365 グループを使用してゲストを追加しない生成への招待メールにゲストために、チームのメンバー、ゲストを通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ee6c-p103">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups or SharePoint Online are ready to go. The Office 365 admin or a team owner can add those guests to their respective teams. If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team. Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="8ee6c-119">ゲストは、 [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347)と[Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019)サービスの制限の適用対象はします。</span><span class="sxs-lookup"><span data-stu-id="8ee6c-119">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>



<span data-ttu-id="8ee6c-p104">ゲストの追加の Azure Active Directory または Office 365 のセキュリティを管理できる&amp;コンプライアンス センターします。Microsoft チームでゲストを追加し、監査が、Azure AD グループ管理アクティビティ「追加されたメンバーをグループに」としてログオンします。詳細については、[監査と B2B コラボレーション ユーザーのレポート](https://go.microsoft.com/fwlink/p/?linkid=858884)を参照してくださいと[Office 365 のセキュリティの監査ログを検索&amp;コンプライアンス センター](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)します。</span><span class="sxs-lookup"><span data-stu-id="8ee6c-p104">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center. Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group". For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

