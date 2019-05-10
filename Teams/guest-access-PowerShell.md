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
ms.openlocfilehash: 0efb3a8054008d179b9d2e7e674b3482fe62a32c
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865091"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="cf86e-103">PowerShell を使用してチームへのゲスト アクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="cf86e-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="cf86e-104">Microsoft 365 管理センターでは、Active Directory の Azure ポータルを使用する以外は、ゲスト アクセスを制御するのに Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf86e-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="cf86e-105">PowerShell を使用すると、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cf86e-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="cf86e-106">すべてのチームおよび Office 365 グループへのゲスト アクセスを許可または拒否する</span><span class="sxs-lookup"><span data-stu-id="cf86e-106">Allow or block guest access to all teams and Office 365 groups</span></span>
    
- <span data-ttu-id="cf86e-107">すべてのチームおよび Office 365 グループへのゲストの追加を許可する</span><span class="sxs-lookup"><span data-stu-id="cf86e-107">Allow guests to be added to all teams and Office 365 groups</span></span>
      
- <span data-ttu-id="cf86e-108">特定のチームまたは Office 365 グループのゲスト ユーザーを許可または拒否する</span><span class="sxs-lookup"><span data-stu-id="cf86e-108">Allow or block guest users from a specific team or Office 365 group</span></span>
    
<span data-ttu-id="cf86e-109">詳細については、 [Office 365 のグループでのゲスト アクセス](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell)の管理] タブの「ゲスト アクセスを制御する PowerShell を使用」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf86e-109">For details, see the section "Use PowerShell to control guest access" on the Manage tab of [Guest access in Office 365 Groups](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
<span data-ttu-id="cf86e-110">PowerShell を使用して、ドメインに基づいてゲスト ユーザーの許可と拒否を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="cf86e-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="cf86e-111">たとえば、ある企業 (Contoso) が別の企業 (Fabrikam) とパートナーシップを結んでいると仮定します。</span><span class="sxs-lookup"><span data-stu-id="cf86e-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="cf86e-112">Fabrikam 社を [許可] リストに追加すると、Contoso 社のユーザーは Fabrikam のユーザーをゲストとしてグループに追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="cf86e-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="cf86e-113">詳細については、「[Allow/Block guest access to Office 365 groups (Office 365 グループへのゲスト アクセスを許可/拒否する)](https://go.microsoft.com/fwlink/?linkid=854001)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cf86e-113">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="cf86e-114">チームには、来園者をブロックし、SharePoint サイトにアクセスできるようにする場合は、コマンドレットを使用できます Azure Active Directory Powershell 会社オブジェクトでは、AllowGuestsToAccessGroups パラメーターを無効にする外部の共有がオンの場合SharePoint サイトです。</span><span class="sxs-lookup"><span data-stu-id="cf86e-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure Active Directory Powershell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>   

## <a name="guest-access-vs-external-access"></a><span data-ttu-id="cf86e-115">ゲスト アクセスを外部からのアクセスとの比較</span><span class="sxs-lookup"><span data-stu-id="cf86e-115">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
