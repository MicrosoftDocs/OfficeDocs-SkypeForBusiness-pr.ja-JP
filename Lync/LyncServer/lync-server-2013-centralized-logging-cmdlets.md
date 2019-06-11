---
title: 'Lync Server 2013: 一元的なログコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Centralized Logging cmdlets
ms:assetid: 8ba5bcae-8b99-489c-9355-6e77d4ad9100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205064(v=OCS.15)
ms:contentKeyID: 48184743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01087b335098e34dc3066fbee31c5e6ec7995698
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="centralized-logging-cmdlets-in-lync-server-2013"></a><span data-ttu-id="c3cc9-102">Lync Server 2013 の集中化されたログコマンドレット</span><span class="sxs-lookup"><span data-stu-id="c3cc9-102">Centralized Logging cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3cc9-103">_**最終更新日:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="c3cc9-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="c3cc9-104">集中ログコマンドレットを使用すると、管理者は Microsoft Lync Server 2013 で導入された一元的なログ機能を管理および構成することができます。</span><span class="sxs-lookup"><span data-stu-id="c3cc9-104">The centralized logging cmdlets provide a way for administrators to manage and configure the centralized logging capabilities introduced in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="c3cc9-105">一元管理では、管理者が複数のコンピューターのイベントトレースを同時に有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c3cc9-105">Centralized logging allows administrators to simultaneously enable or disable event tracing on multiple computers.</span></span>

<div>

## <a name="centralized-logging-cmdlets"></a><span data-ttu-id="c3cc9-106">一元的なログコマンドレット</span><span class="sxs-lookup"><span data-stu-id="c3cc9-106">Centralized Logging Cmdlets</span></span>

<span data-ttu-id="c3cc9-107">一元的なログコマンドレットを使用すると、Lync Server 2013 で導入された中央のログサービスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="c3cc9-107">The centralized logging cmdlets enable you to manage the centralized logging service introduced in Lync Server 2013:</span></span>

<span data-ttu-id="c3cc9-108">**一元的なログコマンドレット**</span><span class="sxs-lookup"><span data-stu-id="c3cc9-108">**Centralized Logging Cmdlets**</span></span>

  - <span data-ttu-id="c3cc9-109">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-109">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span></span>

  - <span data-ttu-id="c3cc9-110">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-110">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span></span>

  - <span data-ttu-id="c3cc9-111">[CsClsConfiguration の削除](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-111">[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span></span>

  - <span data-ttu-id="c3cc9-112">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-112">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c3cc9-113">[Search-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-113">[Search-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15))</span></span>

  - <span data-ttu-id="c3cc9-114">[[表示]-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-114">[Show-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15))</span></span>

  - <span data-ttu-id="c3cc9-115">[スタート-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-115">[Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15))</span></span>

  - <span data-ttu-id="c3cc9-116">[は、CsClsLogging の停止](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-116">[Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15))</span></span>

  - <span data-ttu-id="c3cc9-117">[Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-117">[Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15))</span></span>

  - <span data-ttu-id="c3cc9-118">[更新プログラム-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-118">[Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c3cc9-119">[新規の CsClsProvider](https://technet.microsoft.com/en-us/library/JJ619187(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-119">[New-CsClsProvider](https://technet.microsoft.com/en-us/library/JJ619187(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c3cc9-120">[Get-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-120">[Get-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15))</span></span>

  - <span data-ttu-id="c3cc9-121">[新規-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-121">[New-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15))</span></span>

  - <span data-ttu-id="c3cc9-122">[削除-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-122">[Remove-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15))</span></span>

  - <span data-ttu-id="c3cc9-123">[Set-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-123">[Set-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c3cc9-124">[Get-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205091(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-124">[Get-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205091(v=OCS.15))</span></span>

  - <span data-ttu-id="c3cc9-125">[新しい CsClsScenario シナリオ](https://technet.microsoft.com/en-us/library/JJ205022(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-125">[New-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205022(v=OCS.15))</span></span>

  - <span data-ttu-id="c3cc9-126">[削除-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205010(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-126">[Remove-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205010(v=OCS.15))</span></span>

  - <span data-ttu-id="c3cc9-127">[Set-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ204622(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-127">[Set-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ204622(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c3cc9-128">[Get-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-128">[Get-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15))</span></span>

  - <span data-ttu-id="c3cc9-129">[Set-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-129">[Set-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c3cc9-130">[Get-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-130">[Get-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15))</span></span>

  - <span data-ttu-id="c3cc9-131">[新規-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-131">[New-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15))</span></span>

  - <span data-ttu-id="c3cc9-132">[Remove-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-132">[Remove-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15))</span></span>

  - <span data-ttu-id="c3cc9-133">[Set-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3cc9-133">[Set-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

