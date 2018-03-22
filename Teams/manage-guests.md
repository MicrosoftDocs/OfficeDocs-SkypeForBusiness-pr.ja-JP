---
title: Microsoft Teams でのゲスト アクセスを管理する
author: LolaJacobsen
ms.author: rramesan
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: IT 管理者は、テナントレベルでのゲストの追加、ゲスト ユーザー ポリシーと権限の設定と管理、ゲストを招待できるユーザーの判別、ゲスト ユーザーのアクティビティに関するレポートの取得を行うことができます。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 02faf85d91657c487c02503b69b08078b81c88de
ms.sourcegitcommit: 70fc5217f588e10ab0edb400f329ea597efaab52
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2018
---
<a name="manage-guest-access-in-microsoft-teams"></a><span data-ttu-id="9c34e-103">Microsoft Teams でのゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="9c34e-103">Manage guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="9c34e-104">**ゲスト**は、Office 365 のビジネス プレミアム、Office 365 の企業、および Office 365 の教育のすべてのサブスクリプションに含まれているマイクロソフトのチームでのユーザーとライセンスの種類です。</span><span class="sxs-lookup"><span data-stu-id="9c34e-104">**Guest** is a user/license type in Microsoft Teams that is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="9c34e-105">追加の Office 365 ライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="9c34e-105">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="9c34e-106">Teams のゲスト アクセスはテナントレベルの設定であり、既定ではオフになっています。</span><span class="sxs-lookup"><span data-stu-id="9c34e-106">Teams guest access is a tenant-level setting and is turned off by default.</span></span> <span data-ttu-id="9c34e-107">ゲスト アクセスを有効にする方法の詳細については、[マイクロソフトのチームへのゲスト アクセスの無効を切り替える](set-up-guests.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c34e-107">For details about how to enable guest access, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>

<span data-ttu-id="9c34e-108">**ゲスト**ユーザーとライセンスの種類をオンにすると、 [Office 365 の組織での Microsoft チームの管理機能](enable-features-office-365.md#settings-by-userlicense-type)で説明されているコントロールを使用して来園者の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="9c34e-108">After the **Guest** user/license type is turned on, you can configure settings for guests via the controls described in [Manage Microsoft Teams features in your Office 365 organization](enable-features-office-365.md#settings-by-userlicense-type).</span></span>     
    
<span data-ttu-id="9c34e-109">IT 管理者は、テナントレベルでのゲストの追加、ゲスト ユーザー ポリシーと権限の設定と管理、ゲストを招待できるユーザーの判別、ゲスト ユーザーのアクティビティに関するレポートの取得を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9c34e-109">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, determine which users can invite guests, and pull reports on guest user activity.</span></span> <span data-ttu-id="9c34e-110">これらの制御は Office 365 管理センターを介して利用できます。</span><span class="sxs-lookup"><span data-stu-id="9c34e-110">These controls are available through the Office 365 admin center.</span></span> <span data-ttu-id="9c34e-111">ゲスト ユーザーのコンテンツとアクティビティには、Office 365 の他の部分と同じコンプライアンスと監査保護が適用されます。</span><span class="sxs-lookup"><span data-stu-id="9c34e-111">Guest user content and activities are under the same compliance and auditing protection as the rest of Office 365.</span></span>

<span data-ttu-id="9c34e-112">チームの所有者では、新規来園者を招待でき、既存のディレクトリのゲスト ユーザーをチームに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="9c34e-112">Team owners can invite new guests and add existing directory guest users to their teams.</span></span> <span data-ttu-id="9c34e-113">チームの所有者が**管理チーム**では、来園者のチャネルに関連する機能を設定するさらに、 > の**ゲスト アクセス許可**を作成するには、来園者が許可されるなどの更新、および次のスクリーン ショットに示すように、チャンネルを削除します。</span><span class="sxs-lookup"><span data-stu-id="9c34e-113">In addition, team owners can set channel-related capabilities for guests via **Manage teams** > **Guest permissions**, including allowing guests to create, update, and delete channels, as shown in the following screenshot:</span></span>

![チームでのゲスト アクセス権の設定です。](media/view-guests-guest-permissions.png)
  

<span data-ttu-id="9c34e-115">さらに、Azure Active Directory ポータルを使用して、ゲストの管理、Office 365 や Teams のリソースへのゲスト アクセスの管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9c34e-115">In addition, you can use the Azure Active Directory portal to manage guests and their access to Office 365 and Teams resources.</span></span> <span data-ttu-id="9c34e-116">Teams のゲスト アクセスでは、Azure Active Directory ビジネス ツー ビジネス (B2B) コラボレーション機能を基本インフラストラクチャとして活用して、ID プロパティ、メンバーシップ、多要素認証設定といったセキュリティの原則情報を保管します。</span><span class="sxs-lookup"><span data-stu-id="9c34e-116">Teams guest access makes use of Azure Active Directory business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="9c34e-117">Azure Active Directory B2B の詳細については、「[Azure AD B2B コラボレーションとは](https://go.microsoft.com/fwlink/p/?linkid=853011)」と「[Azure Active Directory B2B コラボレーションの FAQ](https://go.microsoft.com/fwlink/p/?linkid=853020)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9c34e-117">To learn more about Azure Active Directory B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>
> [!NOTE]
> <span data-ttu-id="9c34e-118">マイクロソフトのチームでは、Azure Active Directory 外部の設定を許可またはテナントのゲスト ユーザーの追加を禁止する常にします。</span><span class="sxs-lookup"><span data-stu-id="9c34e-118">Microsoft Teams always honors Azure Active Directory external settings to allow or prevent guest user addition to the tenant.</span></span> <span data-ttu-id="9c34e-119">詳細については、[マイクロソフトのチームでのゲスト アクセスを許可](Teams-dependencies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c34e-119">For more details, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
  
