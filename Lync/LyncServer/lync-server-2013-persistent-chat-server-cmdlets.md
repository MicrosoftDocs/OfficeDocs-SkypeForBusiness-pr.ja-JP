---
title: 'Lync Server 2013: 常設チャットサーバーのコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server cmdlets
ms:assetid: 5aa59edb-db57-406f-9fbd-54bf1a55d31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204920(v=OCS.15)
ms:contentKeyID: 48184226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73e56e02dbd4b76aaa90a4556f688aad2e4ae37c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524234"
---
# <a name="persistent-chat-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="80d24-102">Lync Server 2013 の常設チャットサーバーのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="80d24-102">Persistent Chat Server cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80d24-103">_**トピックの最終更新日:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="80d24-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="80d24-104">常設チャットコマンドレットを使用すると、Microsoft Lync Server 2013 常設チャットサービス (以前のグループチャットサービス) を管理および構成できます。</span><span class="sxs-lookup"><span data-stu-id="80d24-104">The Persistent Chat cmdlets enable you to manage and configure the Microsoft Lync Server 2013 Persistent Chat service (formerly known as the Group Chat service).</span></span> <span data-ttu-id="80d24-105">常設チャットを使用すると、ユーザーはオンラインインスタントメッセージングセッションに参加できます。</span><span class="sxs-lookup"><span data-stu-id="80d24-105">Persistent Chat enables users to participate in online instant messaging sessions.</span></span> <span data-ttu-id="80d24-106">これらのセッションはリアルタイムで行われますが、各セッションの内容は永続的です。つまり、これらの会話は、いつでもだれでも再開できます。</span><span class="sxs-lookup"><span data-stu-id="80d24-106">Although these sessions can take place in real time, the content of each session is persistent; that means these conversations can be resumed by anyone at any time.</span></span>

<div>

## <a name="persistent-chat-cmdlets"></a><span data-ttu-id="80d24-107">常設チャット コマンドレット</span><span class="sxs-lookup"><span data-stu-id="80d24-107">Persistent Chat Cmdlets</span></span>

<span data-ttu-id="80d24-108">常設チャットコマンドレットを使用すると、Lync Server の常設チャットサービスを管理および構成できます。</span><span class="sxs-lookup"><span data-stu-id="80d24-108">The Persistent Chat cmdlets enable you to manage and configure the Lync Server Persistent Chat service.</span></span>

<span data-ttu-id="80d24-109">**常設チャット コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="80d24-109">**Persistent Chat Cmdlets**</span></span>

  - <span data-ttu-id="80d24-110">[取得-CsAdPrincipal](https://technet.microsoft.com/library/JJ205326(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-110">[Get-CsAdPrincipal](https://technet.microsoft.com/library/JJ205326(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="80d24-111">[Set-cspersistentchatactiveserver](https://technet.microsoft.com/library/JJ205065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-111">[Set-CsPersistentChatActiveServer](https://technet.microsoft.com/library/JJ205065(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="80d24-112">[Get-cspersistentchataddin 戻し](https://technet.microsoft.com/library/JJ204670(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-112">[Get-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204670(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-113">[Get-cspersistentchataddin 戻し](https://technet.microsoft.com/library/JJ204641(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-113">[New-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204641(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-114">[Get-cspersistentchataddin 戻し](https://technet.microsoft.com/library/JJ205350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-114">[Remove-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ205350(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-115">[Get-cspersistentchataddin 戻し](https://technet.microsoft.com/library/JJ204721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-115">[Set-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204721(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="80d24-116">[New-cspersistentchatcategory](https://technet.microsoft.com/library/JJ204771(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-116">[Get-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204771(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-117">[New-cspersistentchatcategory](https://technet.microsoft.com/library/JJ204803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-117">[New-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204803(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-118">[New-cspersistentchatcategory](https://technet.microsoft.com/library/JJ204660(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-118">[Remove-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204660(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-119">[New-cspersistentchatcategory](https://technet.microsoft.com/library/JJ204952(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-119">[Set-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204952(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="80d24-120">[New-cspersistentchatcomplianceconfiguration](https://technet.microsoft.com/library/JJ204625(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-120">[Get-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204625(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-121">[New-cspersistentchatcomplianceconfiguration](https://technet.microsoft.com/library/JJ205163(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-121">[New-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ205163(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-122">[New-cspersistentchatcomplianceconfiguration](https://technet.microsoft.com/library/JJ204767(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-122">[Remove-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204767(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-123">[New-cspersistentchatcomplianceconfiguration](https://technet.microsoft.com/library/JJ204949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-123">[Set-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204949(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="80d24-124">[Get-cspersistentchatconfiguration](https://technet.microsoft.com/library/JJ205140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-124">[Get-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205140(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-125">[Get-cspersistentchatconfiguration](https://technet.microsoft.com/library/JJ205330(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-125">[New-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205330(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-126">[Get-cspersistentchatconfiguration](https://technet.microsoft.com/library/JJ204927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-126">[Remove-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ204927(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-127">[Get-cspersistentchatconfiguration](https://technet.microsoft.com/library/JJ205122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-127">[Set-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205122(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="80d24-128">[Export-cspersistentchatdata](https://technet.microsoft.com/library/JJ205378(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-128">[Export-CsPersistentChatData](https://technet.microsoft.com/library/JJ205378(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-129">[Export-cspersistentchatdata](https://technet.microsoft.com/library/JJ204709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-129">[Import-CsPersistentChatData](https://technet.microsoft.com/library/JJ204709(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="80d24-130">[Get-cspersistentchateligibleprincipal](https://technet.microsoft.com/library/JJ204891(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-130">[Get-CsPersistentChatEligiblePrincipal](https://technet.microsoft.com/library/JJ204891(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="80d24-131">[New-cspersistentchatendpoint](https://technet.microsoft.com/library/JJ204764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-131">[Get-CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204764(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-132">[New-cspersistentchatendpoint](https://technet.microsoft.com/library/JJ204811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-132">[New-CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204811(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-133">[New-cspersistentchatendpoint](https://technet.microsoft.com/library/JJ204626(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-133">[Remove-CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204626(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="80d24-134">[Test-cspersistentchatmessage](https://technet.microsoft.com/library/JJ204668(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-134">[Remove-CsPersistentChatMessage](https://technet.microsoft.com/library/JJ204668(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-135">[Test-cspersistentchatmessage](https://technet.microsoft.com/library/JJ204656(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-135">[Test-CsPersistentChatMessage](https://technet.microsoft.com/library/JJ204656(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="80d24-136">[Get-cspersistentchatpolicy 戻し](https://technet.microsoft.com/library/JJ204673(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-136">[Get-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ204673(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-137">[Get-cspersistentchatpolicy 戻し](https://technet.microsoft.com/library/JJ204907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-137">[Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ204907(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-138">[Get-cspersistentchatpolicy 戻し](https://technet.microsoft.com/library/JJ205396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-138">[New-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205396(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-139">[Get-cspersistentchatpolicy 戻し](https://technet.microsoft.com/library/JJ205301(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-139">[Remove-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205301(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-140">[Get-cspersistentchatpolicy 戻し](https://technet.microsoft.com/library/JJ205192(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-140">[Set-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205192(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="80d24-141">[Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ204976(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-141">[Clear-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204976(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-142">[Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ205123(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-142">[Get-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ205123(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-143">[Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ205166(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-143">[New-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ205166(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-144">[Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ204639(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-144">[Remove-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204639(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-145">[Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ204801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-145">[Set-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204801(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="80d24-146">[Set-cspersistentchatstate](https://technet.microsoft.com/library/JJ204915(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-146">[Get-CsPersistentChatState](https://technet.microsoft.com/library/JJ204915(v=OCS.15))</span></span>

  - <span data-ttu-id="80d24-147">[Set-cspersistentchatstate](https://technet.microsoft.com/library/JJ205109(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="80d24-147">[Set-CsPersistentChatState](https://technet.microsoft.com/library/JJ205109(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

