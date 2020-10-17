---
title: 'Lync Server 2013: ユーザー管理のコマンドレット'
description: 'Lync Server 2013: ユーザー管理のコマンドレット。'
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
ms.openlocfilehash: b94f2b48017fd29fa7a5a814da8a3c80d8f57968
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569783"
---
# <a name="user-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="3bd66-103">Lync Server 2013 でのユーザー管理のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="3bd66-103">User management cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bd66-104">_**トピックの最終更新日:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="3bd66-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="3bd66-105">Microsoft Lync Server 2013 に含まれているユーザー管理コマンドレットを使用すると、Lync Server ユーザーアカウントの有効化、無効化、および変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3bd66-105">The user management cmdlets included in Microsoft Lync Server 2013 allow you to enable, disable, and modify Lync Server user accounts.</span></span>

<div>

## <a name="user-management-cmdlets"></a><span data-ttu-id="3bd66-106">ユーザー管理のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="3bd66-106">User Management Cmdlets</span></span>

<span data-ttu-id="3bd66-107">ユーザーおよびユーザーアカウントに適用されるほとんどの管理タスクは、Lync Server コントロールパネルから実行できます。</span><span class="sxs-lookup"><span data-stu-id="3bd66-107">Most management tasks that apply to users and user accounts can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="3bd66-108">主な例外は、電話会議プロバイダーを操作するコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="3bd66-108">The primary exceptions are the cmdlets that deal with audio conferencing providers.</span></span> <span data-ttu-id="3bd66-109">ユーザー管理タスクは、Lync Server 管理シェルまたはスクリプト内からコマンドレットを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="3bd66-109">User management tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="3bd66-110">スクリプトを使用すると、特定のタスクを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="3bd66-110">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="3bd66-111">以下は、ユーザーとユーザー アカウントの管理に直接関連するコマンドレットの一覧です。</span><span class="sxs-lookup"><span data-stu-id="3bd66-111">The following is a list of cmdlets that relate directly to managing users and user accounts:</span></span>

  - <span></span>  
    [<span data-ttu-id="3bd66-112">取得-CsAdContact</span><span class="sxs-lookup"><span data-stu-id="3bd66-112">Get-CsAdContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdContact)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="3bd66-113">取得-CsAdUser</span><span class="sxs-lookup"><span data-stu-id="3bd66-113">Get-CsAdUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdUser)

<!-- end list -->

  - [<span data-ttu-id="3bd66-114">-CsClientAccessLicense を取得する</span><span class="sxs-lookup"><span data-stu-id="3bd66-114">Get-CsClientAccessLicense</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClientAccessLicense)

<!-- end list -->

  - [<span data-ttu-id="3bd66-115">CsEffectivePolicy</span><span class="sxs-lookup"><span data-stu-id="3bd66-115">Get-CsEffectivePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsEffectivePolicy)

<!-- end list -->

  - [<span data-ttu-id="3bd66-116">Invoke-csucsrollback</span><span class="sxs-lookup"><span data-stu-id="3bd66-116">Invoke-CsUcsRollback</span></span>](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback)

<!-- end list -->

  - [<span data-ttu-id="3bd66-117">Test-csunifiedcontactstore</span><span class="sxs-lookup"><span data-stu-id="3bd66-117">Debug-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Debug-CsUnifiedContactStore)

  - [<span data-ttu-id="3bd66-118">Test-csunifiedcontactstore</span><span class="sxs-lookup"><span data-stu-id="3bd66-118">Test-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="3bd66-119">無効-CsUser</span><span class="sxs-lookup"><span data-stu-id="3bd66-119">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser)

  - <span></span>  
    [<span data-ttu-id="3bd66-120">を有効にする-CsUser</span><span class="sxs-lookup"><span data-stu-id="3bd66-120">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Enable-CsUser)

  - <span></span>  
    [<span data-ttu-id="3bd66-121">取得-CsUser</span><span class="sxs-lookup"><span data-stu-id="3bd66-121">Get-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)

  - <span></span>  
    [<span data-ttu-id="3bd66-122">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="3bd66-122">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)

  - <span></span>  
    [<span data-ttu-id="3bd66-123">設定-CsUser</span><span class="sxs-lookup"><span data-stu-id="3bd66-123">Set-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="3bd66-124">取得-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="3bd66-124">Get-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="3bd66-125">削除-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="3bd66-125">Remove-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="3bd66-126">設定-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="3bd66-126">Set-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="3bd66-127">Test-csaudioconferencingprovider</span><span class="sxs-lookup"><span data-stu-id="3bd66-127">Test-CsAudioConferencingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAudioConferencingProvider)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="3bd66-128">取得-CsUserPoolInfo</span><span class="sxs-lookup"><span data-stu-id="3bd66-128">Get-CsUserPoolInfo</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserPoolInfo)

<!-- end list -->

  - [<span data-ttu-id="3bd66-129">-Csuserサービスポリシーを取得する</span><span class="sxs-lookup"><span data-stu-id="3bd66-129">Get-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserServicesPolicy)

  - [<span data-ttu-id="3bd66-130">Grant-Csuserサービスポリシー</span><span class="sxs-lookup"><span data-stu-id="3bd66-130">Grant-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsUserServicesPolicy)

  - [<span data-ttu-id="3bd66-131">新しい-Csuserサービスポリシー</span><span class="sxs-lookup"><span data-stu-id="3bd66-131">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)

  - [<span data-ttu-id="3bd66-132">削除-Csuserサービスポリシー</span><span class="sxs-lookup"><span data-stu-id="3bd66-132">Remove-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserServicesPolicy)

  - [<span data-ttu-id="3bd66-133">設定-Csuserサービスポリシー</span><span class="sxs-lookup"><span data-stu-id="3bd66-133">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3bd66-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="3bd66-134">See Also</span></span>


[<span data-ttu-id="3bd66-135">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="3bd66-135">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

