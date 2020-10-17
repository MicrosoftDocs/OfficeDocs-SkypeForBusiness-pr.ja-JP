---
title: 'Lync Server 2013: 証明書および認証のコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate and authentication cmdlets
ms:assetid: ebb51778-3558-49d2-8343-d83e7a731559
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415680(v=OCS.15)
ms:contentKeyID: 48185711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a60f91891f0dc3ef51840994eb16d06483104b46
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508034"
---
# <a name="certificate-and-authentication-cmdlets-in-lync-server-2013"></a><span data-ttu-id="60306-102">Lync Server 2013 の証明書と認証のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="60306-102">Certificate and authentication cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60306-103">_**トピックの最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="60306-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="60306-104">証明書と認証のコマンドレットは、さまざまな範囲のタスクに使用できます。たとえば、サーバーおよびクライアント証明書の管理、ユーザーの PIN (暗証番号) の管理、インターネット インフォメーション サービスで使用する SIP ドメインと Kerberos アカウントの管理などです。</span><span class="sxs-lookup"><span data-stu-id="60306-104">The certificate and authentication cmdlets cover a wide range of tasks, including the management of server and client certificates; the management of user PINs (personal identification numbers); and the management of both SIP domains and the Kerberos accounts used with Internet Information Services.</span></span>

<div>

## <a name="certificate-and-authentication-cmdlets"></a><span data-ttu-id="60306-105">証明書および認証のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="60306-105">Certificate and Authentication Cmdlets</span></span>

<span data-ttu-id="60306-106">以下は、証明書と認証の管理に直接関連するコマンドレットの一覧です。</span><span class="sxs-lookup"><span data-stu-id="60306-106">The following is a list of cmdlets that relate directly to managing certificates and authentication:</span></span>

<span data-ttu-id="60306-107">**証明書と認証**</span><span class="sxs-lookup"><span data-stu-id="60306-107">**Certificates and Authentication**</span></span>

  - <span></span>  
    <span data-ttu-id="60306-108">[-CsCertificate の取得](https://technet.microsoft.com/library/Gg398227(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-108">[Get-CsCertificate](https://technet.microsoft.com/library/Gg398227(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60306-109">[インポート-CsCertificate](https://technet.microsoft.com/library/Gg398688(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-109">[Import-CsCertificate](https://technet.microsoft.com/library/Gg398688(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60306-110">[削除-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-110">[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60306-111">[要求-CsCertificate](https://technet.microsoft.com/library/Gg425723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-111">[Request-CsCertificate](https://technet.microsoft.com/library/Gg425723(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60306-112">[設定-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-112">[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="60306-113">[Test-Cs/Test](https://technet.microsoft.com/library/Gg398647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-113">[Test-CsCertificateConfiguration](https://technet.microsoft.com/library/Gg398647(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="60306-114">[Revoke-csclientcertificate](https://technet.microsoft.com/library/Gg398143(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-114">[Get-CsClientCertificate](https://technet.microsoft.com/library/Gg398143(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60306-115">[Revoke-csclientcertificate](https://technet.microsoft.com/library/Gg425748(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-115">[Revoke-CsClientCertificate](https://technet.microsoft.com/library/Gg425748(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="60306-116">[ロック-CsClientPin](https://technet.microsoft.com/library/Gg398650(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-116">[Lock-CsClientPin](https://technet.microsoft.com/library/Gg398650(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60306-117">[-CsClientPin の設定](https://technet.microsoft.com/library/Gg398929(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-117">[Set-CsClientPin](https://technet.microsoft.com/library/Gg398929(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60306-118">[ロック解除-CsClientPin](unhttps://technet.microsoft.com/library/Gg398650(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-118">[Unlock-CsClientPin](unhttps://technet.microsoft.com/library/Gg398650(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="60306-119">[-CsClientPinInfo を取得する](https://technet.microsoft.com/library/Gg425947(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-119">[Get-CsClientPinInfo](https://technet.microsoft.com/library/Gg425947(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="60306-120">[New-Csker' Osaccount '](https://technet.microsoft.com/library/Gg398485(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-120">[New-CsKerberosAccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="60306-121">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-121">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60306-122">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-122">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60306-123">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-123">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60306-124">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-124">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60306-125">[Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-125">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="60306-126">[Set-Csker' Osaccountpassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-126">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="60306-127">[Get-cspinpolicy](https://technet.microsoft.com/library/Gg398262(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-127">[Get-CsPinPolicy](https://technet.microsoft.com/library/Gg398262(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60306-128">[Get-cspinpolicy](https://technet.microsoft.com/library/Gg398871(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-128">[Grant-CsPinPolicy](https://technet.microsoft.com/library/Gg398871(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60306-129">[Get-cspinpolicy](https://technet.microsoft.com/library/Gg398935(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-129">[New-CsPinPolicy](https://technet.microsoft.com/library/Gg398935(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60306-130">[Get-cspinpolicy](https://technet.microsoft.com/library/Gg398431(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-130">[Remove-CsPinPolicy](https://technet.microsoft.com/library/Gg398431(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60306-131">[Get-cspinpolicy](https://technet.microsoft.com/library/Gg412997(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-131">[Set-CsPinPolicy](https://technet.microsoft.com/library/Gg412997(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="60306-132">[-CsProxyConfiguration の取得](https://technet.microsoft.com/library/Gg399011(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-132">[Get-CsProxyConfiguration](https://technet.microsoft.com/library/Gg399011(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60306-133">[新しい-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398335(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-133">[New-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398335(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60306-134">[-CsProxyConfiguration を削除する](https://technet.microsoft.com/library/Gg398553(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-134">[Remove-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398553(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60306-135">[設定-CsProxyConfiguration](https://technet.microsoft.com/library/Gg425796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-135">[Set-CsProxyConfiguration](https://technet.microsoft.com/library/Gg425796(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="60306-136">[New-cssipdomain](https://technet.microsoft.com/library/Gg398701(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-136">[Get-CsSipDomain](https://technet.microsoft.com/library/Gg398701(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60306-137">[New-cssipdomain](https://technet.microsoft.com/library/Gg425857(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-137">[New-CsSipDomain](https://technet.microsoft.com/library/Gg425857(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60306-138">[New-cssipdomain](https://technet.microsoft.com/library/Gg398865(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-138">[Remove-CsSipDomain](https://technet.microsoft.com/library/Gg398865(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="60306-139">[New-cssipdomain](https://technet.microsoft.com/library/Gg412949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="60306-139">[Set-CsSipDomain](https://technet.microsoft.com/library/Gg412949(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="60306-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="60306-140">See Also</span></span>


[<span data-ttu-id="60306-141">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="60306-141">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

