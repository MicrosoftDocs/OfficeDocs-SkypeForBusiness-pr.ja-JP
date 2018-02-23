---
title: "Microsoft Teams へのゲスト アクセスを管理する"
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
ms.reviewer: laal
description: "IT 管理者は、テナントレベルでのゲストの追加、ゲスト ユーザー ポリシーと権限の設定と管理、ゲストを招待できるユーザーの判別、ゲスト ユーザーのアクティビティに関するレポートの取得を行うことができます。"
appliesto:
- Microsoft Teams
ms.openlocfilehash: d665a5a837070eadbbd8d3f7e168da0ad97d642c
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2018
---
<a name="manage-guest-access-to-microsoft-teams"></a><span data-ttu-id="b4e75-103">Microsoft Teams へのゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="b4e75-103">Manage guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="b4e75-104">ゲスト アクセスは、Office 365 Business Premium、Office 365 Enterprise、Office 365 Education のすべてのサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="b4e75-104">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="b4e75-105">追加の Office 365 ライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="b4e75-105">No additional Office 365 license is necessary.</span></span>
  
    
    
<span data-ttu-id="b4e75-106">Teams のゲスト アクセスはテナントレベルの設定であり、既定ではオフになっています。</span><span class="sxs-lookup"><span data-stu-id="b4e75-106">Teams guest access is a tenant-level setting and is turned off by default.</span></span> <span data-ttu-id="b4e75-107">IT 管理者は、テナントレベルでのゲストの追加、ゲスト ユーザー ポリシーと権限の設定と管理、ゲストを招待できるユーザーの判別、ゲスト ユーザーのアクティビティに関するレポートの取得を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b4e75-107">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, determine which users can invite guests, and pull reports on guest user activity.</span></span> <span data-ttu-id="b4e75-108">これらの制御は Office 365 管理センターを介して利用できます。</span><span class="sxs-lookup"><span data-stu-id="b4e75-108">These controls are available through the Office 365 admin center.</span></span> <span data-ttu-id="b4e75-109">ゲスト ユーザーのコンテンツとアクティビティには、Office 365 の他の部分と同じコンプライアンスと監査保護が適用されます。</span><span class="sxs-lookup"><span data-stu-id="b4e75-109">Guest user content and activities are under the same compliance and auditing protection as the rest of Office 365.</span></span>
  
    
    

> [!NOTE]
> <span data-ttu-id="b4e75-110">Teams のゲスト アクセスのテナント設定は、ゲストのサインインのみを拒否します。</span><span class="sxs-lookup"><span data-stu-id="b4e75-110">The Teams guest access tenant setting only prevents guest sign-in.</span></span> <span data-ttu-id="b4e75-111">チーム所有者は、所有するチームに新しいゲストを招待したり、既存のディレクトリ ゲスト ユーザーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="b4e75-111">Team owners will be able to invite new guests and add existing directory guest users to their respective teams.</span></span> <span data-ttu-id="b4e75-112">Teams は、テナントへのゲスト ユーザーの追加の許可または拒否において、常に Azure Active Directory の外部設定を優先します。</span><span class="sxs-lookup"><span data-stu-id="b4e75-112">As a reminder, Teams always honors Azure Active Directory external settings to allow or prevent guest user addition to the tenant.</span></span> 
  
    
    

<span data-ttu-id="b4e75-113">さらに、Azure Active Directory ポータルを使用して、ゲストの管理、Office 365 や Teams のリソースへのゲスト アクセスの管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b4e75-113">In addition, you can use the Azure Active Directory portal to manage guests and their access to Office 365 and Teams resources.</span></span> <span data-ttu-id="b4e75-114">Teams のゲスト アクセスでは、Azure Active Directory ビジネス ツー ビジネス (B2B) コラボレーション機能を基本インフラストラクチャとして活用して、ID プロパティ、メンバーシップ、多要素認証設定といったセキュリティの原則情報を保管します。</span><span class="sxs-lookup"><span data-stu-id="b4e75-114">Teams guest access makes use of Azure Active Directory business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="b4e75-115">Azure Active Directory B2B の詳細については、「[Azure AD B2B コラボレーションとは](https://go.microsoft.com/fwlink/p/?linkid=853011)」と「[Azure Active Directory B2B コラボレーションの FAQ](https://go.microsoft.com/fwlink/p/?linkid=853020)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b4e75-115">To learn more about Azure Active Directory B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>
  