---
title: PowerShell を使用してチームへのゲスト アクセスを制御する
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/09/17
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: PowerShell を使用して、Microsoft Teams のチームへのゲスト アクセスを許可または拒否できます。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ca05e48d28986a944debe150d5dbf25129ca73c
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2019
ms.locfileid: "33827670"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="84dfb-103">PowerShell を使用してチームへのゲスト アクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="84dfb-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="84dfb-104">Office 365 管理センターと Azure Active Directory ポータルに加え、Windows PowerShell を使用してゲスト アクセスを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="84dfb-104">In addition to using the Office 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="84dfb-105">PowerShell を使用すると、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="84dfb-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="84dfb-106">すべてのチームおよび Office 365 グループへのゲスト アクセスを許可または拒否する</span><span class="sxs-lookup"><span data-stu-id="84dfb-106">Allow or block guest access to all teams and Office 365 groups</span></span>
    
- <span data-ttu-id="84dfb-107">すべてのチームおよび Office 365 グループへのゲストの追加を許可する</span><span class="sxs-lookup"><span data-stu-id="84dfb-107">Allow guests to be added to all teams and Office 365 groups</span></span>
      
- <span data-ttu-id="84dfb-108">特定のチームまたは Office 365 グループのゲスト ユーザーを許可または拒否する</span><span class="sxs-lookup"><span data-stu-id="84dfb-108">Allow or block guest users from a specific team or Office 365 group</span></span>
    
<span data-ttu-id="84dfb-109">詳細については、 [Office 365 のグループでのゲスト アクセス](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell)の管理] タブの「ゲスト アクセスを制御する PowerShell を使用」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="84dfb-109">For details, see the section "Use PowerShell to control guest access" on the Manage tab of [Guest access in Office 365 Groups](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
<span data-ttu-id="84dfb-110">PowerShell を使用して、ドメインに基づいてゲスト ユーザーの許可と拒否を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="84dfb-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="84dfb-111">たとえば、ある企業 (Contoso) が別の企業 (Fabrikam) とパートナーシップを結んでいると仮定します。</span><span class="sxs-lookup"><span data-stu-id="84dfb-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="84dfb-112">Fabrikam 社を [許可] リストに追加すると、Contoso 社のユーザーは Fabrikam のユーザーをゲストとしてグループに追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="84dfb-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="84dfb-113">詳細については、「[Allow/Block guest access to Office 365 groups (Office 365 グループへのゲスト アクセスを許可/拒否する)](https://go.microsoft.com/fwlink/?linkid=854001)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="84dfb-113">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="84dfb-114">チームには、来園者をブロックし、SharePoint サイトにアクセスできるようにする場合は、コマンドレットを使用できます Azure Active Directory Powershell 会社オブジェクトでは、AllowGuestsToAccessGroups パラメーターを無効にする外部の共有がオンの場合SharePoint サイトです。</span><span class="sxs-lookup"><span data-stu-id="84dfb-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure Active Directory Powershell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>   

## <a name="guest-access-vs-external-access"></a><span data-ttu-id="84dfb-115">ゲスト アクセスを外部からのアクセスとの比較</span><span class="sxs-lookup"><span data-stu-id="84dfb-115">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
