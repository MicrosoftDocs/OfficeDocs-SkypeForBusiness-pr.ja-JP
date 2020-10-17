---
title: 'Lync Server 2013: サーバーの役割およびサービスのコマンドレットのトラブルシューティング'
description: 'Lync Server 2013: サーバーの役割およびサービスのコマンドレットのトラブルシューティング。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting server roles and services cmdlets
ms:assetid: 03be4cae-bf35-40b2-8e02-477b64afa4c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415628(v=OCS.15)
ms:contentKeyID: 48183268
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c524ca800445e6b23175ba13621b52c71bc4335f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548913"
---
# <a name="troubleshooting-server-roles-and-services-cmdlets-in-lync-server-2013"></a><span data-ttu-id="8a3eb-103">Lync Server 2013 のサーバーの役割およびサービスのコマンドレットのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="8a3eb-103">Troubleshooting server roles and services cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a3eb-104">_**トピックの最終更新日:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="8a3eb-104">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="8a3eb-105">トラブルシューティングのコマンドレットを使用すると、Microsoft Lync Server 2013 が期待どおりに動作していることを確認する方法が異なります。</span><span class="sxs-lookup"><span data-stu-id="8a3eb-105">The troubleshooting cmdlets provide different ways to verify that Microsoft Lync Server 2013 is working as expected.</span></span> <span data-ttu-id="8a3eb-106">たとえば、CsHealthMonitoringConfiguration コマンドレットを使用して、レジストラー プールとディレクター プールのテスト アカウントを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8a3eb-106">For example, the CsHealthMonitoringConfiguration cmdlets enable you to set up test accounts for Registrar and Director pools.</span></span> <span data-ttu-id="8a3eb-107">また、それらのテスト アカウントを使用して、一般的なタスク (システムへのログオン、インスタント メッセージの交換、公衆交換電話網 (PSTN) の電話への発信など) をユーザーが正常に完了できることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8a3eb-107">In turn, you can then use those test accounts to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="8a3eb-108">コマンドレットの詳細については、Lync Server Windows PowerShell のブログを参照してください &nbsp; <A href="https://go.microsoft.com/fwlink/p/?linkid=263432">https://go.microsoft.com/fwlink/p/?linkId=263432</A> 。</span><span class="sxs-lookup"><span data-stu-id="8a3eb-108">For additional information about cmdlets, see the Lync Server&nbsp;Windows PowerShell Blog at <A href="https://go.microsoft.com/fwlink/p/?linkid=263432">https://go.microsoft.com/fwlink/p/?linkId=263432</A>.</span></span> <span data-ttu-id="8a3eb-109">各ブログのコンテンツおよびその URL は予告なしに変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="8a3eb-109">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<div>

## <a name="server-roles-and-services-cmdlets"></a><span data-ttu-id="8a3eb-110">サーバーの役割およびサービスのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="8a3eb-110">Server Roles and Services Cmdlets</span></span>

<span data-ttu-id="8a3eb-111">以下は、サーバーの役割およびサービスのトラブルシューティングに直接関連するコマンドレットの一覧です。</span><span class="sxs-lookup"><span data-stu-id="8a3eb-111">The following is a list of cmdlets that relate directly to troubleshooting server roles and services:</span></span>

<span data-ttu-id="8a3eb-112">**サーバーの役割およびサービスのトラブルシューティング**</span><span class="sxs-lookup"><span data-stu-id="8a3eb-112">**Troubleshooting Server Roles and Services**</span></span>

  - <span></span>  
    <span data-ttu-id="8a3eb-113">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8a3eb-113">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8a3eb-114">[Set-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8a3eb-114">[Set-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8a3eb-115">[Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8a3eb-115">[Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8a3eb-116">[Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8a3eb-116">[New-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8a3eb-117">[Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg425794(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8a3eb-117">[Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425794(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8a3eb-118">[Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8a3eb-118">[Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8a3eb-119">[Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8a3eb-119">[Get-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8a3eb-120">[Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8a3eb-120">[New-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8a3eb-121">[Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg412853(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8a3eb-121">[Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg412853(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8a3eb-122">[Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8a3eb-122">[Set-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8a3eb-123">[New-csdiagnosticsfilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8a3eb-123">[New-CsDiagnosticsFilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8a3eb-124">[Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8a3eb-124">[Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8a3eb-125">[Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8a3eb-125">[New-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8a3eb-126">[Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg398941(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8a3eb-126">[Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398941(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8a3eb-127">[Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8a3eb-127">[Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

