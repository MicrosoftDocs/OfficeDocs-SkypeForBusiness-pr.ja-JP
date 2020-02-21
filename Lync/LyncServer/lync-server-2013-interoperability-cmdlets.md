---
title: 'Lync Server 2013: 相互運用性のコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability cmdlets
ms:assetid: 18444a0b-7b66-4540-a262-775ea10b3b7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204714(v=OCS.15)
ms:contentKeyID: 48183527
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5857e70d659c200b4bdcd76da7a67f1feaca4f1d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="interoperability-cmdlets-in-lync-server-2013"></a><span data-ttu-id="852c9-102">Lync Server 2013 の相互運用性のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="852c9-102">Interoperability cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="852c9-103">_**トピックの最終更新日:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="852c9-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="852c9-104">相互運用性のコマンドレットは、Microsoft Lync Server 2013 と、Microsoft Exchange Server 2013 などのその他のサーバー製品との間のサーバー間認証と承認を構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="852c9-104">The interoperability cmdlets are used to configure server-to-server authentication and authorization between Microsoft Lync Server 2013 and other server products such as Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="852c9-105">サーバー間認証および承認を使用すると、これらのサーバーがデータをシームレスに交換したり、共有したりできます。</span><span class="sxs-lookup"><span data-stu-id="852c9-105">Server-to-server authentication and authorization enables these servers to seamless exchange and share data.</span></span>

<div>

## <a name="interoperability-cmdlets"></a><span data-ttu-id="852c9-106">相互運用コマンドレット</span><span class="sxs-lookup"><span data-stu-id="852c9-106">Interoperability Cmdlets</span></span>

<span data-ttu-id="852c9-107">Microsoft Lync Server 2013 とその他のサーバー製品との間の相互運用性の構成と管理に直接関連するコマンドレットの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="852c9-107">The following is a list of cmdlets that relate directly to configuring and managing interoperability between Microsoft Lync Server 2013 and other server products:</span></span>

<span data-ttu-id="852c9-108">**相互運用コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="852c9-108">**Interoperability Cmdlets**</span></span>

  - <span data-ttu-id="852c9-109">[取得-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="852c9-109">[Get-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))</span></span>

  - <span data-ttu-id="852c9-110">[Set-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="852c9-110">[Set-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="852c9-111">[取得-CsOAuthServer](https://technet.microsoft.com/library/JJ205238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="852c9-111">[Get-CsOAuthServer](https://technet.microsoft.com/library/JJ205238(v=OCS.15))</span></span>

  - <span data-ttu-id="852c9-112">[新しい-CsOAuthServer](https://technet.microsoft.com/library/JJ205206(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="852c9-112">[New-CsOAuthServer](https://technet.microsoft.com/library/JJ205206(v=OCS.15))</span></span>

  - <span data-ttu-id="852c9-113">[Remove-CsOAuthServer](https://technet.microsoft.com/library/JJ205408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="852c9-113">[Remove-CsOAuthServer](https://technet.microsoft.com/library/JJ205408(v=OCS.15))</span></span>

  - <span data-ttu-id="852c9-114">[Set-CsOAuthServer](https://technet.microsoft.com/library/JJ204896(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="852c9-114">[Set-CsOAuthServer](https://technet.microsoft.com/library/JJ204896(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="852c9-115">[Get-cspartnerapplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="852c9-115">[Get-CsPartnerApplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))</span></span>

  - <span data-ttu-id="852c9-116">[Get-cspartnerapplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="852c9-116">[New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))</span></span>

  - <span data-ttu-id="852c9-117">[Get-cspartnerapplication](https://technet.microsoft.com/library/JJ204820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="852c9-117">[Remove-CsPartnerApplication](https://technet.microsoft.com/library/JJ204820(v=OCS.15))</span></span>

  - <span data-ttu-id="852c9-118">[Get-cspartnerapplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="852c9-118">[Set-CsPartnerApplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

