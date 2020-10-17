---
title: 'Lync Server 2013: エンタープライズ Voip のコマンドレットのトラブルシューティング'
description: 'Lync Server 2013: エンタープライズ Voip のコマンドレットのトラブルシューティング。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Enterprise Voice cmdlets
ms:assetid: 28ec32d2-6d1e-40e6-b2a8-065803288e8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415638(v=OCS.15)
ms:contentKeyID: 48183697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eeee9792ce635afc5c625394f6594676d0bd4f71
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549033"
---
# <a name="troubleshooting-enterprise-voice-cmdlets-in-lync-server-2013"></a><span data-ttu-id="f8234-103">Lync Server 2013 でのエンタープライズ Voip のコマンドレットのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f8234-103">Troubleshooting Enterprise Voice cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8234-104">_**トピックの最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="f8234-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="f8234-105">Microsoft Lync Server 2013 の実装の一部としてのエンタープライズ Voip の設定には、着信および発信の呼び出しが期待どおりに完了するようにする必要があるルート、ポリシー、およびルールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8234-105">Setting up Enterprise Voice as part of your Microsoft Lync Server 2013 implementation involves creating routes, policies and rules that must all work together to ensure incoming and outgoing calls are completed as expected.</span></span> <span data-ttu-id="f8234-106">Lync Server 管理シェルには、接続とパスのテスト、および実装中に発生する可能性のある問題のトラブルシューティングに使用できるコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f8234-106">Lync Server Management Shell includes cmdlets that can be used to test connections and paths and to troubleshoot issues that may arise during implementation.</span></span>

<div>

## <a name="troubleshooting-enterprise-voice-cmdlets"></a><span data-ttu-id="f8234-107">エンタープライズ VoIP のトラブルシューティングのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="f8234-107">Troubleshooting Enterprise Voice Cmdlets</span></span>

<span data-ttu-id="f8234-108">次のコマンドレットは、エンタープライズ VoIP 接続のテストとトラブルシューティングに使用できます。</span><span class="sxs-lookup"><span data-stu-id="f8234-108">The following cmdlets can be used to test and troubleshoot Enterprise Voice connections.</span></span>

<span data-ttu-id="f8234-109">**エンタープライズ VoIP のトラブルシューティングのコマンドレット**</span><span class="sxs-lookup"><span data-stu-id="f8234-109">**Troubleshooting Enterprise Voice Cmdlets**</span></span>

  - <span></span>  
    <span data-ttu-id="f8234-110">[CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f8234-110">[Get-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f8234-111">[CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f8234-111">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398804(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f8234-112">[CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f8234-112">[Set-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f8234-113">[Test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f8234-113">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f8234-114">[Test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f8234-114">[New-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f8234-115">[Test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg412813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f8234-115">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412813(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f8234-116">[Test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f8234-116">[Set-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f8234-117">[Test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f8234-117">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f8234-118">[Get-csdialplan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f8234-118">[Test-CsDialPlan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f8234-119">[Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f8234-119">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f8234-120">[Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f8234-120">[Test-CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f8234-121">[Get-csvoiceroute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f8234-121">[Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f8234-122">[CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f8234-122">[Test-CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f8234-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8234-123">See Also</span></span>


[<span data-ttu-id="f8234-124">Lync Server 2013 のエンタープライズ Voip のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="f8234-124">Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-cmdlets.md)  


[<span data-ttu-id="f8234-125">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="f8234-125">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

