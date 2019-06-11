---
title: 'Lync Server 2013: 移行と共存のコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration and coexistence cmdlets
ms:assetid: ff1a56e0-e883-473d-92fe-ca77ea4eb63b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415682(v=OCS.15)
ms:contentKeyID: 48185968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21b78bea6bee197444e275403f8a2abcf7d06634
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-cmdlets-in-lync-server-2013"></a><span data-ttu-id="87e51-102">Lync Server 2013 での移行と共存のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="87e51-102">Migration and coexistence cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87e51-103">_**最終更新日:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="87e51-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="87e51-104">[CsLegacyUser](https://technet.microsoft.com/en-us/library/Gg413025(v=OCS.15))コマンドレットを使用すると、Office Communications server 2007 または Microsoft lync server 2010 から Microsoft lync server 2013 にユーザーアカウントを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="87e51-104">The [Move-CsLegacyUser](https://technet.microsoft.com/en-us/library/Gg413025(v=OCS.15)) cmdlet provides a way for you to move user accounts from Office Communications Server 2007 or Microsoft Lync Server 2010 to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="87e51-105">"戻る" (たとえば、Microsoft Lync Server 2013 から Microsoft Lync Server 2010 に) ユーザーアカウントを移動する必要がある場合は、 [move-CsUser](https://technet.microsoft.com/en-us/library/Gg398528(v=OCS.15))コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="87e51-105">If you need to move a user account "backward" (for example, from Microsoft Lync Server 2013 to Microsoft Lync Server 2010) use the [Move-CsUser](https://technet.microsoft.com/en-us/library/Gg398528(v=OCS.15)) cmdlet.</span></span>

  - <span></span>  
    <span data-ttu-id="87e51-106">[Import-CsLegacyConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg398418(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="87e51-106">[Import-CsLegacyConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg398418(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="87e51-107">[インポート-CsLegacyConfiguration](https://technet.microsoft.com/en-us/library/Gg412923(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="87e51-107">[Import-CsLegacyConfiguration](https://technet.microsoft.com/en-us/library/Gg412923(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="87e51-108">[マージ-CsLegacyTopology](https://technet.microsoft.com/en-us/library/Gg425870(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="87e51-108">[Merge-CsLegacyTopology](https://technet.microsoft.com/en-us/library/Gg425870(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="87e51-109">[Move-CsApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398188(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="87e51-109">[Move-CsApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398188(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="87e51-110">[CsLegacyUser の移動](https://technet.microsoft.com/en-us/library/Gg413025(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="87e51-110">[Move-CsLegacyUser](https://technet.microsoft.com/en-us/library/Gg413025(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="87e51-111">[Convert-CsUserData](https://technet.microsoft.com/en-us/library/JJ205337(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="87e51-111">[Convert-CsUserData](https://technet.microsoft.com/en-us/library/JJ205337(v=OCS.15))</span></span>

  - <span data-ttu-id="87e51-112">[Export-CsUserData](https://technet.microsoft.com/en-us/library/JJ204897(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="87e51-112">[Export-CsUserData](https://technet.microsoft.com/en-us/library/JJ204897(v=OCS.15))</span></span>

  - <span data-ttu-id="87e51-113">[インポート-CsUserData](https://technet.microsoft.com/en-us/library/JJ205373(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="87e51-113">[Import-CsUserData](https://technet.microsoft.com/en-us/library/JJ205373(v=OCS.15))</span></span>

  - <span data-ttu-id="87e51-114">[Update-CsUserData](https://technet.microsoft.com/en-us/library/JJ205358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="87e51-114">[Update-CsUserData](https://technet.microsoft.com/en-us/library/JJ205358(v=OCS.15))</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="87e51-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="87e51-115">See Also</span></span>


[<span data-ttu-id="87e51-116">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="87e51-116">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

