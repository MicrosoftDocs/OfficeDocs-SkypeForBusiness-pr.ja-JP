---
title: "PowerShell を使用してチームへのゲスト アクセスを制御する"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "PowerShell を使用して、Microsoft Teams のチームへのゲスト アクセスを許可または拒否できます。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: fd9844d0a72932cb28dca97d8bb8c1c05d0ddfe5
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="6cc5f-103">PowerShell を使用してチームへのゲスト アクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="6cc5f-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="6cc5f-104">Office 365 管理センターと Azure Active Directory ポータルに加え、Windows PowerShell を使用してゲスト アクセスを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="6cc5f-104">In addition to using the Office 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="6cc5f-105">PowerShell を使用すると、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6cc5f-105">With PowerShell, you can do the following:</span></span>
  
  
   

- <span data-ttu-id="6cc5f-106">すべてのチームおよび Office 365 グループへのゲスト アクセスを許可または拒否する</span><span class="sxs-lookup"><span data-stu-id="6cc5f-106">Allow or block guest access to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="6cc5f-107">すべてのチームおよび Office 365 グループへのゲストの追加を許可する</span><span class="sxs-lookup"><span data-stu-id="6cc5f-107">Allow guests to be added to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="6cc5f-108">特定のチームまたは Office 365 グループのゲスト ユーザーを許可または拒否する</span><span class="sxs-lookup"><span data-stu-id="6cc5f-108">Allow or block guest users from a specific team or Office 365 group</span></span>
    
  
<span data-ttu-id="6cc5f-109">詳しくは、「[PowerShell を使用してゲスト アクセスを制御する](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6cc5f-109">For more details, see [Use PowerShell to control guest access](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
    
    
<span data-ttu-id="6cc5f-110">PowerShell を使用して、ドメインに基づいてゲスト ユーザーの許可と拒否を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="6cc5f-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="6cc5f-111">たとえば、ある企業 (Contoso) が別の企業 (Fabrikam) とパートナーシップを結んでいると仮定します。</span><span class="sxs-lookup"><span data-stu-id="6cc5f-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="6cc5f-112">Fabrikam 社を [許可] リストに追加すると、Contoso 社のユーザーは Fabrikam のユーザーをゲストとしてグループに追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6cc5f-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="6cc5f-113">詳細については、「[Allow/Block guest access to Office 365 groups (Office 365 グループへのゲスト アクセスを許可/拒否する)](https://go.microsoft.com/fwlink/?linkid=854001)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6cc5f-113">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
 
<span data-ttu-id="6cc5f-114">チームのゲストを拒否したいがゲストに対して SharePoint サイトへのアクセスを引き続き許可する場合は、SharePoint の外部共有をオンに設定しているという前提の上に、Azure Active Directory Powershell コマンドレットを使用して Company オブジェクトの AllowGuestAccessToGroups パラメーターを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6cc5f-114">If you want to block guests in teams and still allow guests to access SharePoint sites, you can use Azure Active Directory Powershell cmdlets to disable the AllowGuestAccessToGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>   