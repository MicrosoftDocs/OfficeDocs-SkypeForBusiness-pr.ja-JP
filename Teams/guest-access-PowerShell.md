---
title: PowerShell を使用してチームへのゲスト アクセスを制御する
author: lanachin
ms.author: v-lanac
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
ms.openlocfilehash: 815a35efbce89404b012d5534e257752bef8d53e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886383"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="3223e-103">PowerShell を使用してチームへのゲスト アクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="3223e-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="3223e-104">Microsoft 365 管理センターと Azure Active Directory ポータルに加え、Windows PowerShell を使用してゲスト アクセスを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="3223e-104">In addition to using the Office 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="3223e-105">PowerShell を使用すると、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3223e-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="3223e-106">すべてのチームおよび Office 365 グループへのゲスト アクセスを許可または拒否する</span><span class="sxs-lookup"><span data-stu-id="3223e-106">Allow or block guest access to all teams and Office 365 groups</span></span>
    
- <span data-ttu-id="3223e-107">すべてのチームおよび Office 365 グループへのゲストの追加を許可する</span><span class="sxs-lookup"><span data-stu-id="3223e-107">Allow guests to be added to all teams and Office 365 groups</span></span>
      
- <span data-ttu-id="3223e-108">特定のチームまたは Office 365 グループのゲスト ユーザーを許可または拒否する</span><span class="sxs-lookup"><span data-stu-id="3223e-108">Allow or block guest users from a specific team or Office 365 group</span></span>
    
<span data-ttu-id="3223e-109">詳しくは、「[Office 365 グループのゲスト アクセス](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell)」の [管理] タブの「PowerShell を使用してゲスト アクセスを制御する」のセクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3223e-109">For more details, see the section "Use PowerShell to control guest access" on the Manage tab of [Guest access in Office 365 Groups](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
<span data-ttu-id="3223e-110">PowerShell を使用して、ドメインに基づいてゲスト ユーザーの許可と拒否を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="3223e-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="3223e-111">たとえば、自分の会社 (Contoso) が他の会社 (Fabrikam) とのパートナーシップを持つとします。</span><span class="sxs-lookup"><span data-stu-id="3223e-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="3223e-112">許可リストに Fabrikam を追加し、ユーザーが自分のグループにそれらのゲストを追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3223e-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="3223e-113">詳細については、「[Allow/Block guest access to Office 365 groups (Office 365 グループへのゲスト アクセスを許可/拒否する)](https://go.microsoft.com/fwlink/?linkid=854001)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3223e-113">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="3223e-114">Teamsのゲストを拒否したいがゲストに対して SharePoint サイトへのアクセスを引き続き許可する場合は、SharePoint の外部共有をオンに設定しているという前提の上に、Azure Active Directory Powershell コマンドレットを使用して Company オブジェクトの AllowGuestsToAccessGroups パラメーターを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3223e-114">If you want to block guests in teams and still allow guests to access SharePoint sites, you can use Azure Active Directory Powershell cmdlets to disable the AllowGuestAccessToGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>   

## <a name="guest-access-vs-external-access"></a><span data-ttu-id="3223e-115">ゲスト アクセスと外部アクセス</span><span class="sxs-lookup"><span data-stu-id="3223e-115">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
