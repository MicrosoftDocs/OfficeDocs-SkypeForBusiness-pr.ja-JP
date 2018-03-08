---
title: "PowerShell を使用してチームにゲスト アクセスを制御するには"
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "許可または Microsoft チームでチームにゲスト アクセスをブロックするには、PowerShell を使用します。"
ms.openlocfilehash: d75bbbce689b5b0799c7d2ec806977f6d23ee906
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="a2f90-103">PowerShell を使用してチームにゲスト アクセスを制御するには</span><span class="sxs-lookup"><span data-stu-id="a2f90-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="a2f90-p101">に加えて、Office 365 管理センターと Azure Active Directory ポータルを使用して、ゲスト アクセスを制御するのに Windows PowerShell を使用することができます。PowerShell] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a2f90-p101">In addition to using the Office 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access. With PowerShell, you can do the following:</span></span>
  
  
   

- <span data-ttu-id="a2f90-106">許可またはすべてのチームと Office 365 グループへのゲスト アクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="a2f90-106">Allow or block guest access to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="a2f90-107">すべてのチームと Office 365 のグループに追加するゲストを許可します。</span><span class="sxs-lookup"><span data-stu-id="a2f90-107">Allow guests to be added to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="a2f90-108">許可または特定のチーム サイトまたは Office 365 グループからゲスト ユーザーをブロックします。</span><span class="sxs-lookup"><span data-stu-id="a2f90-108">Allow or block guest users from a specific team or Office 365 group</span></span>
    
  
<span data-ttu-id="a2f90-109">詳細については、[ [Office 365 のグループ内のゲスト アクセス許可](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell)の管理] タブの「ゲスト アクセスを制御する PowerShell を使用する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2f90-109">For more details, see the section "Use PowerShell to control guest access" on the Manage tab of [Guest access in Office 365 Groups](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
    
    
<span data-ttu-id="a2f90-p102">許可または自分のドメインに基づくゲスト ユーザーをブロックする PowerShell を使用することもできます。たとえば、別のビジネス (Fabrikam) のパートナーシップをビジネス (Contoso) があるとします。許可リストに Fabrikam を追加するには、ユーザーのグループにこれらのゲストを追加できるようにします。詳細については、 [Office 365 のグループへのゲスト アクセスの許可/禁止](https://go.microsoft.com/fwlink/?linkid=854001)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2f90-p102">You can also use PowerShell to allow or block a guest user based on their domain. For example, let's say your business (Contoso) has a partnership with another business (Fabrikam). You can add Fabrikam to your Allow list so your users can add those guests to their groups. For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
 
<span data-ttu-id="a2f90-114">チームのゲストをブロックし、ながら、ゲスト SharePoint サイトにアクセスする場合は、コマンドレットを使用できます Powershell Azure Active Directory、会社のオブジェクトに AllowGuestAccessToGroups パラメーターを無効にする外部共有を有効になっているものとしてSharePoint サイトです。</span><span class="sxs-lookup"><span data-stu-id="a2f90-114">If you want to block guests in teams and still allow guests to access SharePoint sites, you can use Azure Active Directory Powershell cmdlets to disable the AllowGuestAccessToGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>   

