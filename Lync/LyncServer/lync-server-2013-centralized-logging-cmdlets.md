---
title: 'Lync Server 2013: 集中ログのコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Centralized Logging cmdlets
ms:assetid: 8ba5bcae-8b99-489c-9355-6e77d4ad9100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205064(v=OCS.15)
ms:contentKeyID: 48184743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70e9993134c10b2b90193538239022919db80c4a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="centralized-logging-cmdlets-in-lync-server-2013"></a><span data-ttu-id="d8cc7-102">Lync Server 2013 での集中ログのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="d8cc7-102">Centralized Logging cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8cc7-103">_**トピックの最終更新日:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="d8cc7-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="d8cc7-104">集中ログコマンドレットを使用すると、管理者は Microsoft Lync Server 2013 で導入された集中ログ機能を管理および構成することができます。</span><span class="sxs-lookup"><span data-stu-id="d8cc7-104">The centralized logging cmdlets provide a way for administrators to manage and configure the centralized logging capabilities introduced in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="d8cc7-105">管理者は、集中ログを使用して、複数のコンピューター上のイベント トレースを同時に有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="d8cc7-105">Centralized logging allows administrators to simultaneously enable or disable event tracing on multiple computers.</span></span>

<div>

## <a name="centralized-logging-cmdlets"></a><span data-ttu-id="d8cc7-106">集中ログ コマンドレット</span><span class="sxs-lookup"><span data-stu-id="d8cc7-106">Centralized Logging Cmdlets</span></span>

<span data-ttu-id="d8cc7-107">集中ログコマンドレットを使用すると、Lync Server 2013 で導入された集中ログサービスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="d8cc7-107">The centralized logging cmdlets enable you to manage the centralized logging service introduced in Lync Server 2013:</span></span>

<span data-ttu-id="d8cc7-108">**集中ログ コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="d8cc7-108">**Centralized Logging Cmdlets**</span></span>

  - <span data-ttu-id="d8cc7-109">[取得-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-109">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>

  - <span data-ttu-id="d8cc7-110">[新しい-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-110">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>

  - <span data-ttu-id="d8cc7-111">[削除-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-111">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>

  - <span data-ttu-id="d8cc7-112">[設定-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-112">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="d8cc7-113">[検索-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-113">[Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15))</span></span>

  - <span data-ttu-id="d8cc7-114">[Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-114">[Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15))</span></span>

  - <span data-ttu-id="d8cc7-115">[Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-115">[Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15))</span></span>

  - <span data-ttu-id="d8cc7-116">[Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-116">[Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15))</span></span>

  - <span data-ttu-id="d8cc7-117">[Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-117">[Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15))</span></span>

  - <span data-ttu-id="d8cc7-118">[更新-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-118">[Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="d8cc7-119">[新しい-CsClsProvider](https://technet.microsoft.com/library/JJ619187(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-119">[New-CsClsProvider](https://technet.microsoft.com/library/JJ619187(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="d8cc7-120">[取得-CsClsRegion](https://technet.microsoft.com/library/JJ204879(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-120">[Get-CsClsRegion](https://technet.microsoft.com/library/JJ204879(v=OCS.15))</span></span>

  - <span data-ttu-id="d8cc7-121">[新しい-CsClsRegion](https://technet.microsoft.com/library/JJ204658(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-121">[New-CsClsRegion](https://technet.microsoft.com/library/JJ204658(v=OCS.15))</span></span>

  - <span data-ttu-id="d8cc7-122">[削除-CsClsRegion](https://technet.microsoft.com/library/JJ204971(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-122">[Remove-CsClsRegion](https://technet.microsoft.com/library/JJ204971(v=OCS.15))</span></span>

  - <span data-ttu-id="d8cc7-123">[設定-CsClsRegion](https://technet.microsoft.com/library/JJ204746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-123">[Set-CsClsRegion](https://technet.microsoft.com/library/JJ204746(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="d8cc7-124">[取得-CsClsScenario](https://technet.microsoft.com/library/JJ205091(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-124">[Get-CsClsScenario](https://technet.microsoft.com/library/JJ205091(v=OCS.15))</span></span>

  - <span data-ttu-id="d8cc7-125">[新しい-CsClsScenario](https://technet.microsoft.com/library/JJ205022(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-125">[New-CsClsScenario](https://technet.microsoft.com/library/JJ205022(v=OCS.15))</span></span>

  - <span data-ttu-id="d8cc7-126">[削除-CsClsScenario](https://technet.microsoft.com/library/JJ205010(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-126">[Remove-CsClsScenario](https://technet.microsoft.com/library/JJ205010(v=OCS.15))</span></span>

  - <span data-ttu-id="d8cc7-127">[Set-CsClsScenario](https://technet.microsoft.com/library/JJ204622(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-127">[Set-CsClsScenario](https://technet.microsoft.com/library/JJ204622(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="d8cc7-128">[取得-CsClsSearchTerm](https://technet.microsoft.com/library/JJ205061(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-128">[Get-CsClsSearchTerm](https://technet.microsoft.com/library/JJ205061(v=OCS.15))</span></span>

  - <span data-ttu-id="d8cc7-129">[Set-CsClsSearchTerm](https://technet.microsoft.com/library/JJ204911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-129">[Set-CsClsSearchTerm](https://technet.microsoft.com/library/JJ204911(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="d8cc7-130">[New-csclssecuritygroup](https://technet.microsoft.com/library/JJ205285(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-130">[Get-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205285(v=OCS.15))</span></span>

  - <span data-ttu-id="d8cc7-131">[New-csclssecuritygroup](https://technet.microsoft.com/library/JJ205359(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-131">[New-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205359(v=OCS.15))</span></span>

  - <span data-ttu-id="d8cc7-132">[New-csclssecuritygroup](https://technet.microsoft.com/library/JJ204958(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-132">[Remove-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204958(v=OCS.15))</span></span>

  - <span data-ttu-id="d8cc7-133">[New-csclssecuritygroup](https://technet.microsoft.com/library/JJ204700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d8cc7-133">[Set-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204700(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

