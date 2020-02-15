---
title: ユーザー id を使用する Skype for Business Online のコマンドレット
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8310d5e25b5fc3dd3ada43fcf3c8f899f60e5a7e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001262"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="3d81c-102">ユーザー id を使用する Skype for Business Online のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="3d81c-102">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="3d81c-103">Skype for Business Online では、個別のユーザー Id を参照するさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="3d81c-103">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="3d81c-104">ユーザーの Active Directory ドメインサービスの表示名を使用します。</span><span class="sxs-lookup"><span data-stu-id="3d81c-104">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="3d81c-105">例:</span><span class="sxs-lookup"><span data-stu-id="3d81c-105">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="3d81c-106">ユーザーの SIP アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="3d81c-106">Use the user’s SIP address.</span></span> <span data-ttu-id="3d81c-107">例:</span><span class="sxs-lookup"><span data-stu-id="3d81c-107">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="3d81c-108">ユーザーの UPN を使用します。</span><span class="sxs-lookup"><span data-stu-id="3d81c-108">Use the user’s UPN.</span></span> <span data-ttu-id="3d81c-109">例:</span><span class="sxs-lookup"><span data-stu-id="3d81c-109">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="3d81c-110">ユーザーの Active Directory ドメインサービスの識別名を使用します。</span><span class="sxs-lookup"><span data-stu-id="3d81c-110">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="3d81c-111">例:</span><span class="sxs-lookup"><span data-stu-id="3d81c-111">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="3d81c-112">次のコマンドレットは、ユーザー Id を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="3d81c-112">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="3d81c-113">[無効化-Csの会議室](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3d81c-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3d81c-114">[Enable-Csの会議室](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3d81c-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3d81c-115">[取得-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3d81c-115">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3d81c-116">[取得-Cs会議室](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3d81c-116">[Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3d81c-117">[取得-Csonline ユーザー](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3d81c-117">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3d81c-118">[取得-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3d81c-118">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3d81c-119">[新規-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3d81c-119">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3d81c-120">[削除-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3d81c-120">[Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3d81c-121">[削除-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3d81c-121">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3d81c-122">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3d81c-122">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3d81c-123">[セットアップ-Csの会議室](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3d81c-123">[Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3d81c-124">[設定-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3d81c-124">[Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="3d81c-125">なお、この**Get Cs**コマンドレットのいずれかを呼び出す場合は、ユーザー id を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3d81c-125">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="3d81c-126">この例では、コマンドレットは指定されたアイテムのすべてのインスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="3d81c-126">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="3d81c-127">たとえば、次のコマンドを実行すると、Skype for Business Online が有効になっているすべてのユーザーに関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="3d81c-127">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="3d81c-128">Identity パラメーターは、特定のユーザーについての情報を取得する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="3d81c-128">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="3d81c-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d81c-129">See Also</span></span>


[<span data-ttu-id="3d81c-130">Skype for Business Online の id、スコープ、およびテナント</span><span class="sxs-lookup"><span data-stu-id="3d81c-130">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="3d81c-131">[Skype for Business Online のコマンドレット](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3d81c-131">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

