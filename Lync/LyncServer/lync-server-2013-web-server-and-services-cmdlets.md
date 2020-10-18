---
title: 'Lync Server 2013: Web サーバーおよびサービスのコマンドレット'
description: 'Lync Server 2013: Web サーバーおよびサービスのコマンドレット。'
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
ms.openlocfilehash: a5a4aca9d9859a070459b07d731271142d04b603
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576373"
---
# <a name="web-server-and-services-cmdlets-in-lync-server-2013"></a><span data-ttu-id="da7ff-103">Lync Server 2013 の Web サーバーおよびサービスのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="da7ff-103">Web server and services cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da7ff-104">_**トピックの最終更新日:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="da7ff-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="da7ff-105">Microsoft Lync Server 2013 の多くのコンポーネントは web ベースです。これらのコンポーネントは、Web サービスまたは Web ページを使用してタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="da7ff-105">Many Microsoft Lync Server 2013 components are web-based: these components either use Web Services or webpages to carry out their tasks.</span></span> <span data-ttu-id="da7ff-106">Web サーバーと Web サービスのコマンドレットを使用すると、Web サーバーの設定を構成したり、簡単な Url を管理したりするなどの作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="da7ff-106">The Web Server and Web services cmdlets enable you to do such things as configure Web Server settings and to manage simple URLs.</span></span> <span data-ttu-id="da7ff-107">簡易 Url を使用すると、ユーザーが会議や会議に参加しやすくなり、管理者が Lync Server 2013 コントロールパネルに容易にログオンできるようになります。</span><span class="sxs-lookup"><span data-stu-id="da7ff-107">Simple URLs make it easier for users to join meetings and conferences, and make it easier for Administrators to log on to the Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="web-server-and-web-services-cmdlets"></a><span data-ttu-id="da7ff-108">Web サーバーと Web サービスのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="da7ff-108">Web Server and Web Services Cmdlets</span></span>

<span data-ttu-id="da7ff-109">以下に、Web サーバーと Web サービスの管理に直接関連するコマンドレットの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="da7ff-109">The following is a list of cmdlets that relate directly to managing Web Servers and Web Services:</span></span>

<span data-ttu-id="da7ff-110">**Web サーバーとサービス**</span><span class="sxs-lookup"><span data-stu-id="da7ff-110">**Web Servers and Services**</span></span>

  - <span></span>  
    <span data-ttu-id="da7ff-111">[新しい-CsSimpleUrl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da7ff-111">[New-CsSimpleUrl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="da7ff-112">[取得-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da7ff-112">[Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="da7ff-113">[新規-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da7ff-113">[New-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="da7ff-114">[削除-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398515(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da7ff-114">[Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398515(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="da7ff-115">[設定-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da7ff-115">[Set-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="da7ff-116">[新しい-CsSimpleUrlEntry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da7ff-116">[New-CsSimpleUrlEntry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="da7ff-117">[新規-CsWebOrigin](https://technet.microsoft.com/library/JJ950236(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da7ff-117">[New-CsWebOrigin](https://technet.microsoft.com/library/JJ950236(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="da7ff-118">[設定-CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da7ff-118">[Set-CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="da7ff-119">[Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da7ff-119">[Get-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="da7ff-120">[Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da7ff-120">[New-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="da7ff-121">[Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398266(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da7ff-121">[Remove-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398266(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="da7ff-122">[Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da7ff-122">[Set-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="da7ff-123">[New-cswebtrustedcacertificate は](https://technet.microsoft.com/library/Gg412746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da7ff-123">[New-CsWebTrustedCACertificate](https://technet.microsoft.com/library/Gg412746(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="da7ff-124">[New-Csker' Osaccount '](https://technet.microsoft.com/library/Gg398485(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da7ff-124">[New-CsKerberosAccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="da7ff-125">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da7ff-125">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="da7ff-126">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da7ff-126">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="da7ff-127">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da7ff-127">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="da7ff-128">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da7ff-128">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="da7ff-129">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da7ff-129">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="da7ff-130">[Set-Csker' Osaccountpassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da7ff-130">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="da7ff-131">[テスト-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da7ff-131">[Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span></span>

  - <span data-ttu-id="da7ff-132">[Test-cswebappanonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="da7ff-132">[Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="da7ff-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="da7ff-133">See Also</span></span>


[<span data-ttu-id="da7ff-134">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="da7ff-134">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

