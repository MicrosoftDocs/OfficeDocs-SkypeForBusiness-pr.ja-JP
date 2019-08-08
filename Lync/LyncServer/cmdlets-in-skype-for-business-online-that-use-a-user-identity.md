---
title: ユーザー id を使用する Skype for Business Online のコマンドレット
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce46e700a65f00625aeebad1032c54a5affeaa19
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233114"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="016ff-102">ユーザー id を使用する Skype for Business Online のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="016ff-102">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="016ff-103">Skype for Business Online には、個々のユーザー Id を参照するさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="016ff-103">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="016ff-104">ユーザーの Active Directory ドメインサービスの表示名を使用します。</span><span class="sxs-lookup"><span data-stu-id="016ff-104">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="016ff-105">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="016ff-105">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="016ff-106">ユーザーの SIP アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="016ff-106">Use the user’s SIP address.</span></span> <span data-ttu-id="016ff-107">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="016ff-107">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="016ff-108">ユーザーの UPN を使用します。</span><span class="sxs-lookup"><span data-stu-id="016ff-108">Use the user’s UPN.</span></span> <span data-ttu-id="016ff-109">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="016ff-109">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="016ff-110">ユーザーの Active Directory ドメインサービスの識別名を使用します。</span><span class="sxs-lookup"><span data-stu-id="016ff-110">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="016ff-111">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="016ff-111">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="016ff-112">次のコマンドレットは、ユーザー Id を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="016ff-112">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="016ff-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="016ff-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="016ff-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="016ff-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="016ff-115">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="016ff-115">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="016ff-116">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="016ff-116">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="016ff-117">[Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="016ff-117">[Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="016ff-118">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="016ff-118">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="016ff-119">[新規-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="016ff-119">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="016ff-120">[削除-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="016ff-120">[Remove-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="016ff-121">[CsUserAcp の削除](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="016ff-121">[Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="016ff-122">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="016ff-122">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="016ff-123">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="016ff-123">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="016ff-124">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="016ff-124">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="016ff-125">**Get Cs**コマンドレットのいずれかを呼び出す場合は、ユーザー id を指定する必要はないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="016ff-125">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="016ff-126">この場合、コマンドレットは指定された項目のすべてのインスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="016ff-126">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="016ff-127">たとえば、次のコマンドは、Skype for Business Online が有効になっているすべてのユーザーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="016ff-127">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="016ff-128">Identity パラメーターが必要になるのは、特定のユーザーに関する情報を返す場合のみです。</span><span class="sxs-lookup"><span data-stu-id="016ff-128">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="016ff-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="016ff-129">See Also</span></span>


[<span data-ttu-id="016ff-130">Skype for Business Online の id、スコープ、テナント</span><span class="sxs-lookup"><span data-stu-id="016ff-130">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="016ff-131">[Lync Online のコマンドレット](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="016ff-131">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

