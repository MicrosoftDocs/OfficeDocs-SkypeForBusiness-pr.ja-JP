---
title: 'Lync Server 2013: 信頼できるアプリケーションのコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Trusted applications cmdlets
ms:assetid: 4d6ae0dc-e3e0-4519-8b74-9e941dea21e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415652(v=OCS.15)
ms:contentKeyID: 48184071
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 878ce959b10c6868f415ec86d717de590b9c8c29
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="trusted-applications-cmdlets-in-lync-server-2013"></a><span data-ttu-id="cbf2e-102">Lync Server 2013 の信頼済みアプリケーションコマンドレット</span><span class="sxs-lookup"><span data-stu-id="cbf2e-102">Trusted applications cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbf2e-103">_**最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="cbf2e-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="cbf2e-104">信頼されたアプリケーションは、サードパーティによって開発されたアプリケーションで、Microsoft Lync Server 2013 の一部として実行される信頼された状態で、製品の組み込みの部分ではありません。</span><span class="sxs-lookup"><span data-stu-id="cbf2e-104">A trusted application is an application developed by a third party that is given trusted status to run as part of Microsoft Lync Server 2013 but that is not a built-in part of the product.</span></span> <span data-ttu-id="cbf2e-105">Lync Server 2013 には、信頼済みアプリケーションの構成と管理に使うことができるコマンドレットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="cbf2e-105">Lync Server 2013 provides cmdlets that can be used to configure and managed trusted applications.</span></span>

<div>

## <a name="trusted-applications-cmdlets"></a><span data-ttu-id="cbf2e-106">信頼できるアプリケーションのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="cbf2e-106">Trusted Applications Cmdlets</span></span>

<span data-ttu-id="cbf2e-107">信頼できるアプリケーションを管理するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="cbf2e-107">Use the following cmdlets to manage trusted applications.</span></span>

<span data-ttu-id="cbf2e-108">**信頼済みアプリケーション**</span><span class="sxs-lookup"><span data-stu-id="cbf2e-108">**Trusted Applications**</span></span>

  - <span></span>  
    <span data-ttu-id="cbf2e-109">[Get-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg399025(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cbf2e-109">[Get-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg399025(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cbf2e-110">[新規-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398259(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cbf2e-110">[New-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398259(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cbf2e-111">[Remove-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398176(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cbf2e-111">[Remove-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398176(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cbf2e-112">[Set-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg425840(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cbf2e-112">[Set-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg425840(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cbf2e-113">[Get-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg425843(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cbf2e-113">[Get-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg425843(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cbf2e-114">[新規-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398405(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cbf2e-114">[New-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398405(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cbf2e-115">[Remove-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398838(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cbf2e-115">[Remove-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398838(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cbf2e-116">[Get-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg413035(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cbf2e-116">[Get-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg413035(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cbf2e-117">[New-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398594(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cbf2e-117">[New-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398594(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cbf2e-118">[Remove-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cbf2e-118">[Remove-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398837(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cbf2e-119">[Set-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398509(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cbf2e-119">[Set-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398509(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cbf2e-120">[Get-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg413055(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cbf2e-120">[Get-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg413055(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cbf2e-121">[新規-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg425804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cbf2e-121">[New-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg425804(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cbf2e-122">[Remove-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398750(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cbf2e-122">[Remove-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398750(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cbf2e-123">[Set-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398187(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cbf2e-123">[Set-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398187(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cbf2e-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbf2e-124">See Also</span></span>


[<span data-ttu-id="cbf2e-125">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="cbf2e-125">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

