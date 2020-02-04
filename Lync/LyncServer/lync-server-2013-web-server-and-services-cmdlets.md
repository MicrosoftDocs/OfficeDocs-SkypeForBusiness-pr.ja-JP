---
title: 'Lync Server 2013: Web サーバーとサービスのコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web server and services cmdlets
ms:assetid: 07ce7fd4-4068-4957-9cb9-fd121b43858c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415631(v=OCS.15)
ms:contentKeyID: 48183326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffd517f46d6d1793ad1f947f56b1d7e423bfb269
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="web-server-and-services-cmdlets-in-lync-server-2013"></a><span data-ttu-id="e4a20-102">Lync Server 2013 の Web サーバーとサービスのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="e4a20-102">Web server and services cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4a20-103">_**最終更新日:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="e4a20-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="e4a20-104">Microsoft Lync Server 2013 の多くのコンポーネントは web ベースです。これらのコンポーネントは、Web サービスまたは Web ページを使ってタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="e4a20-104">Many Microsoft Lync Server 2013 components are web-based: these components either use Web Services or webpages to carry out their tasks.</span></span> <span data-ttu-id="e4a20-105">Web サーバーと Web サービスのコマンドレットを使用すると、Web サーバーの設定の構成や簡単な Url の管理などの操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e4a20-105">The Web Server and Web services cmdlets enable you to do such things as configure Web Server settings and to manage simple URLs.</span></span> <span data-ttu-id="e4a20-106">単純な Url を使用すると、ユーザーは会議や会議に簡単に参加できるようになり、管理者は Lync Server 2013 コントロールパネルに簡単にログオンできます。</span><span class="sxs-lookup"><span data-stu-id="e4a20-106">Simple URLs make it easier for users to join meetings and conferences, and make it easier for Administrators to log on to the Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="web-server-and-web-services-cmdlets"></a><span data-ttu-id="e4a20-107">Web サーバーと Web サービスのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="e4a20-107">Web Server and Web Services Cmdlets</span></span>

<span data-ttu-id="e4a20-108">Web サーバーと Web サービスの管理に直接関連するコマンドレットの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e4a20-108">The following is a list of cmdlets that relate directly to managing Web Servers and Web Services:</span></span>

<span data-ttu-id="e4a20-109">**Web サーバーとサービス**</span><span class="sxs-lookup"><span data-stu-id="e4a20-109">**Web Servers and Services**</span></span>

  - <span></span>  
    <span data-ttu-id="e4a20-110">[New-CsSimpleUrl](https://technet.microsoft.com/en-us/library/Gg398180(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4a20-110">[New-CsSimpleUrl](https://technet.microsoft.com/en-us/library/Gg398180(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e4a20-111">[CsSimpleUrlConfiguration の入手](https://technet.microsoft.com/en-us/library/Gg398392(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4a20-111">[Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398392(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e4a20-112">[New-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg425813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4a20-112">[New-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg425813(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e4a20-113">[Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398515(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4a20-113">[Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398515(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e4a20-114">[Set-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg412991(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4a20-114">[Set-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg412991(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e4a20-115">[New-CsSimpleUrlEntry](https://technet.microsoft.com/en-us/library/Gg425902(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4a20-115">[New-CsSimpleUrlEntry](https://technet.microsoft.com/en-us/library/Gg425902(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e4a20-116">[新しい CsWebOrigin](https://technet.microsoft.com/en-us/library/JJ950236(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4a20-116">[New-CsWebOrigin](https://technet.microsoft.com/en-us/library/JJ950236(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e4a20-117">[Set-CsWebServer](https://technet.microsoft.com/en-us/library/Gg398759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4a20-117">[Set-CsWebServer](https://technet.microsoft.com/en-us/library/Gg398759(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e4a20-118">[Get-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg425751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4a20-118">[Get-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg425751(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e4a20-119">[New-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398440(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4a20-119">[New-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398440(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e4a20-120">[Remove-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398266(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4a20-120">[Remove-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398266(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e4a20-121">[Set-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4a20-121">[Set-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398396(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e4a20-122">[新規-CsWebTrustedCACertificate](https://technet.microsoft.com/en-us/library/Gg412746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4a20-122">[New-CsWebTrustedCACertificate](https://technet.microsoft.com/en-us/library/Gg412746(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e4a20-123">[新しい-Csker"@ @" アカウント](https://technet.microsoft.com/en-us/library/Gg398485(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4a20-123">[New-CsKerberosAccount](https://technet.microsoft.com/en-us/library/Gg398485(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e4a20-124">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398526(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4a20-124">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398526(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e4a20-125">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398074(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4a20-125">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398074(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e4a20-126">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg413052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4a20-126">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg413052(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e4a20-127">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4a20-127">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398232(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e4a20-128">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4a20-128">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e4a20-129">[Set-Csker\ "Osaccountpassword"](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4a20-129">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e4a20-130">[Test-CsWebApp](https://technet.microsoft.com/en-us/library/Hh689989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4a20-130">[Test-CsWebApp](https://technet.microsoft.com/en-us/library/Hh689989(v=OCS.15))</span></span>

  - <span data-ttu-id="e4a20-131">[Test-CsWebAppAnonymous](https://technet.microsoft.com/en-us/library/Hh690041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4a20-131">[Test-CsWebAppAnonymous](https://technet.microsoft.com/en-us/library/Hh690041(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e4a20-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4a20-132">See Also</span></span>


[<span data-ttu-id="e4a20-133">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="e4a20-133">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

