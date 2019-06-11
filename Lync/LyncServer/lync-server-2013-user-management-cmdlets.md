---
title: 'Lync Server 2013: ユーザー管理コマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User management cmdlets
ms:assetid: 85312f3f-28e8-421c-b94c-e6ead1f5f755
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398677(v=OCS.15)
ms:contentKeyID: 48184702
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a841daae6a811b6668c61ac1befca045fb73b03f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="30ed9-102">Lync Server 2013 のユーザー管理コマンドレット</span><span class="sxs-lookup"><span data-stu-id="30ed9-102">User management cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30ed9-103">_**最終更新日:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="30ed9-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="30ed9-104">Microsoft Lync Server 2013 に含まれているユーザー管理コマンドレットを使用すると、Lync Server のユーザーアカウントを有効にしたり、無効にしたり、変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="30ed9-104">The user management cmdlets included in Microsoft Lync Server 2013 allow you to enable, disable, and modify Lync Server user accounts.</span></span>

<div>

## <a name="user-management-cmdlets"></a><span data-ttu-id="30ed9-105">ユーザー管理コマンドレット</span><span class="sxs-lookup"><span data-stu-id="30ed9-105">User Management Cmdlets</span></span>

<span data-ttu-id="30ed9-106">ユーザーとユーザーアカウントに適用されるほとんどの管理タスクは、Lync Server コントロールパネルから実行できます。</span><span class="sxs-lookup"><span data-stu-id="30ed9-106">Most management tasks that apply to users and user accounts can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="30ed9-107">主な例外として、電話会議プロバイダーを扱うコマンドレットがあります。</span><span class="sxs-lookup"><span data-stu-id="30ed9-107">The primary exceptions are the cmdlets that deal with audio conferencing providers.</span></span> <span data-ttu-id="30ed9-108">ユーザー管理タスクは、Lync Server 管理シェルまたはスクリプト内からコマンドレットを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="30ed9-108">User management tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="30ed9-109">スクリプトを使用することで、特定のタスクを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="30ed9-109">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="30ed9-110">ユーザーとユーザーアカウントの管理に直接関連するコマンドレットの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="30ed9-110">The following is a list of cmdlets that relate directly to managing users and user accounts:</span></span>

  - <span></span>  
    [<span data-ttu-id="30ed9-111">お問い合わせ</span><span class="sxs-lookup"><span data-stu-id="30ed9-111">Get-CsAdContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdContact)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="30ed9-112">CsAdUser</span><span class="sxs-lookup"><span data-stu-id="30ed9-112">Get-CsAdUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdUser)

<!-- end list -->

  - [<span data-ttu-id="30ed9-113">Get-CsClientAccessLicense</span><span class="sxs-lookup"><span data-stu-id="30ed9-113">Get-CsClientAccessLicense</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClientAccessLicense)

<!-- end list -->

  - [<span data-ttu-id="30ed9-114">Get-CsEffectivePolicy</span><span class="sxs-lookup"><span data-stu-id="30ed9-114">Get-CsEffectivePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsEffectivePolicy)

<!-- end list -->

  - [<span data-ttu-id="30ed9-115">CsUcsRollback</span><span class="sxs-lookup"><span data-stu-id="30ed9-115">Invoke-CsUcsRollback</span></span>](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback)

<!-- end list -->

  - [<span data-ttu-id="30ed9-116">Debug-CsUnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="30ed9-116">Debug-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Debug-CsUnifiedContactStore)

  - [<span data-ttu-id="30ed9-117">Test-CsUnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="30ed9-117">Test-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="30ed9-118">無効-CsUser</span><span class="sxs-lookup"><span data-stu-id="30ed9-118">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser)

  - <span></span>  
    [<span data-ttu-id="30ed9-119">(CsUser) を有効にする</span><span class="sxs-lookup"><span data-stu-id="30ed9-119">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Enable-CsUser)

  - <span></span>  
    [<span data-ttu-id="30ed9-120">ユーザーを取得する</span><span class="sxs-lookup"><span data-stu-id="30ed9-120">Get-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)

  - <span></span>  
    [<span data-ttu-id="30ed9-121">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="30ed9-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)

  - <span></span>  
    [<span data-ttu-id="30ed9-122">Set-CsUser</span><span class="sxs-lookup"><span data-stu-id="30ed9-122">Set-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="30ed9-123">Get-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="30ed9-123">Get-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="30ed9-124">CsUserAcp の削除</span><span class="sxs-lookup"><span data-stu-id="30ed9-124">Remove-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="30ed9-125">Set-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="30ed9-125">Set-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="30ed9-126">Test-CsAudioConferencingProvider</span><span class="sxs-lookup"><span data-stu-id="30ed9-126">Test-CsAudioConferencingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAudioConferencingProvider)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="30ed9-127">Get-CsUserPoolInfo</span><span class="sxs-lookup"><span data-stu-id="30ed9-127">Get-CsUserPoolInfo</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserPoolInfo)

<!-- end list -->

  - [<span data-ttu-id="30ed9-128">Get-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="30ed9-128">Get-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserServicesPolicy)

  - [<span data-ttu-id="30ed9-129">Grant-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="30ed9-129">Grant-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsUserServicesPolicy)

  - [<span data-ttu-id="30ed9-130">New-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="30ed9-130">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)

  - [<span data-ttu-id="30ed9-131">Csuserサービスポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="30ed9-131">Remove-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserServicesPolicy)

  - [<span data-ttu-id="30ed9-132">Set-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="30ed9-132">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="30ed9-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="30ed9-133">See Also</span></span>


[<span data-ttu-id="30ed9-134">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="30ed9-134">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

