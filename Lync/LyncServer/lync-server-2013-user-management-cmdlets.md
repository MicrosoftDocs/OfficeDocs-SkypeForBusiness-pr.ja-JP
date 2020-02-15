---
title: 'Lync Server 2013: ユーザー管理のコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User management cmdlets
ms:assetid: 85312f3f-28e8-421c-b94c-e6ead1f5f755
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398677(v=OCS.15)
ms:contentKeyID: 48184702
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a672eea92c820970b3cc4cc1c112c15fcffd641
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="4ada5-102">Lync Server 2013 でのユーザー管理のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="4ada5-102">User management cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ada5-103">_**トピックの最終更新日:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="4ada5-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="4ada5-104">Microsoft Lync Server 2013 に含まれているユーザー管理コマンドレットを使用すると、Lync Server ユーザーアカウントの有効化、無効化、および変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4ada5-104">The user management cmdlets included in Microsoft Lync Server 2013 allow you to enable, disable, and modify Lync Server user accounts.</span></span>

<div>

## <a name="user-management-cmdlets"></a><span data-ttu-id="4ada5-105">ユーザー管理のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="4ada5-105">User Management Cmdlets</span></span>

<span data-ttu-id="4ada5-106">ユーザーおよびユーザーアカウントに適用されるほとんどの管理タスクは、Lync Server コントロールパネルから実行できます。</span><span class="sxs-lookup"><span data-stu-id="4ada5-106">Most management tasks that apply to users and user accounts can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="4ada5-107">主な例外は、電話会議プロバイダーを操作するコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="4ada5-107">The primary exceptions are the cmdlets that deal with audio conferencing providers.</span></span> <span data-ttu-id="4ada5-108">ユーザー管理タスクは、Lync Server 管理シェルまたはスクリプト内からコマンドレットを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="4ada5-108">User management tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="4ada5-109">スクリプトを使用すると、特定のタスクを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="4ada5-109">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="4ada5-110">以下は、ユーザーとユーザー アカウントの管理に直接関連するコマンドレットの一覧です。</span><span class="sxs-lookup"><span data-stu-id="4ada5-110">The following is a list of cmdlets that relate directly to managing users and user accounts:</span></span>

  - <span></span>  
    [<span data-ttu-id="4ada5-111">取得-CsAdContact</span><span class="sxs-lookup"><span data-stu-id="4ada5-111">Get-CsAdContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdContact)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="4ada5-112">取得-CsAdUser</span><span class="sxs-lookup"><span data-stu-id="4ada5-112">Get-CsAdUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdUser)

<!-- end list -->

  - [<span data-ttu-id="4ada5-113">-CsClientAccessLicense を取得する</span><span class="sxs-lookup"><span data-stu-id="4ada5-113">Get-CsClientAccessLicense</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClientAccessLicense)

<!-- end list -->

  - [<span data-ttu-id="4ada5-114">CsEffectivePolicy</span><span class="sxs-lookup"><span data-stu-id="4ada5-114">Get-CsEffectivePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsEffectivePolicy)

<!-- end list -->

  - [<span data-ttu-id="4ada5-115">Invoke-csucsrollback</span><span class="sxs-lookup"><span data-stu-id="4ada5-115">Invoke-CsUcsRollback</span></span>](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback)

<!-- end list -->

  - [<span data-ttu-id="4ada5-116">Test-csunifiedcontactstore</span><span class="sxs-lookup"><span data-stu-id="4ada5-116">Debug-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Debug-CsUnifiedContactStore)

  - [<span data-ttu-id="4ada5-117">Test-csunifiedcontactstore</span><span class="sxs-lookup"><span data-stu-id="4ada5-117">Test-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="4ada5-118">無効-CsUser</span><span class="sxs-lookup"><span data-stu-id="4ada5-118">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser)

  - <span></span>  
    [<span data-ttu-id="4ada5-119">を有効にする-CsUser</span><span class="sxs-lookup"><span data-stu-id="4ada5-119">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Enable-CsUser)

  - <span></span>  
    [<span data-ttu-id="4ada5-120">取得-CsUser</span><span class="sxs-lookup"><span data-stu-id="4ada5-120">Get-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)

  - <span></span>  
    [<span data-ttu-id="4ada5-121">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="4ada5-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)

  - <span></span>  
    [<span data-ttu-id="4ada5-122">設定-CsUser</span><span class="sxs-lookup"><span data-stu-id="4ada5-122">Set-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="4ada5-123">取得-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="4ada5-123">Get-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="4ada5-124">削除-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="4ada5-124">Remove-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="4ada5-125">設定-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="4ada5-125">Set-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="4ada5-126">Test-csaudioconferencingprovider</span><span class="sxs-lookup"><span data-stu-id="4ada5-126">Test-CsAudioConferencingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAudioConferencingProvider)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="4ada5-127">取得-CsUserPoolInfo</span><span class="sxs-lookup"><span data-stu-id="4ada5-127">Get-CsUserPoolInfo</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserPoolInfo)

<!-- end list -->

  - [<span data-ttu-id="4ada5-128">-Csuserサービスポリシーを取得する</span><span class="sxs-lookup"><span data-stu-id="4ada5-128">Get-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserServicesPolicy)

  - [<span data-ttu-id="4ada5-129">Grant-Csuserサービスポリシー</span><span class="sxs-lookup"><span data-stu-id="4ada5-129">Grant-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsUserServicesPolicy)

  - [<span data-ttu-id="4ada5-130">新しい-Csuserサービスポリシー</span><span class="sxs-lookup"><span data-stu-id="4ada5-130">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)

  - [<span data-ttu-id="4ada5-131">削除-Csuserサービスポリシー</span><span class="sxs-lookup"><span data-stu-id="4ada5-131">Remove-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserServicesPolicy)

  - [<span data-ttu-id="4ada5-132">設定-Csuserサービスポリシー</span><span class="sxs-lookup"><span data-stu-id="4ada5-132">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4ada5-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ada5-133">See Also</span></span>


[<span data-ttu-id="4ada5-134">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="4ada5-134">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

