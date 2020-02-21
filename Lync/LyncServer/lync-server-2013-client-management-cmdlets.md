---
title: 'Lync Server 2013: クライアント管理のコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client management cmdlets
ms:assetid: 0384f8ab-453d-49d6-aaa7-52439e27b7e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398087(v=OCS.15)
ms:contentKeyID: 48183261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61854b9205c2c195d38d0252421357b94104e7e3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="6523e-102">Lync Server 2013 のクライアント管理のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6523e-102">Client management cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6523e-103">_**トピックの最終更新日:** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="6523e-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="6523e-104">クライアント管理は主に、Microsoft Lync 2013 などのクライアントアプリケーションが Lync Server 2013 にログオンし、ログオン後にこれらのクライアントアプリケーションが使用できる機能を決定することを許可するかどうかを判断するために構成されています。</span><span class="sxs-lookup"><span data-stu-id="6523e-104">Client management consists primarily of determining which client applications (such as Microsoft Lync 2013) will be allowed to log on to Lync Server 2013 and determining the capabilities available to those client applications after they have logged on.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6523e-105">コマンドレットの詳細については、Lync&nbsp;Server Windows PowerShell の<A href="https://go.microsoft.com/fwlink/p/?linkid=263432">https://go.microsoft.com/fwlink/p/?linkId=263432</A>ブログを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6523e-105">For additional information about cmdlets, see the Lync Server&nbsp;Windows PowerShell Blog at <A href="https://go.microsoft.com/fwlink/p/?linkid=263432">https://go.microsoft.com/fwlink/p/?linkId=263432</A>.</span></span> <span data-ttu-id="6523e-106">各ブログのコンテンツおよびその URL は予告なしに変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="6523e-106">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<div>

## <a name="client-management-cmdlets"></a><span data-ttu-id="6523e-107">クライアント管理のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6523e-107">Client Management Cmdlets</span></span>

<span data-ttu-id="6523e-108">クライアント管理に適用されるほとんどの管理タスクは、Lync Server 2013 コントロールパネルから実行できます。</span><span class="sxs-lookup"><span data-stu-id="6523e-108">Most management tasks that apply to client management can be performed from the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="6523e-109">これらの同じタスクは、Lync Server 管理シェルまたはスクリプト内からコマンドレットを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="6523e-109">These same tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="6523e-110">スクリプトを使用すると、特定のタスクを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="6523e-110">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="6523e-111">以下は、クライアント管理に直接関連するコマンドレットの一覧です。</span><span class="sxs-lookup"><span data-stu-id="6523e-111">The following is a list of cmdlets that relate directly to client management:</span></span>

  - <span></span>  
    <span data-ttu-id="6523e-112">[Get-CsClientPolicy](https://technet.microsoft.com/library/Gg398830(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6523e-112">[Get-CsClientPolicy](https://technet.microsoft.com/library/Gg398830(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6523e-113">[Grant-CsClientPolicy](https://technet.microsoft.com/library/Gg412942(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6523e-113">[Grant-CsClientPolicy](https://technet.microsoft.com/library/Gg412942(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6523e-114">[新しい-CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6523e-114">[New-CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6523e-115">[-CsClientPolicy を削除する](https://technet.microsoft.com/library/Gg425772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6523e-115">[Remove-CsClientPolicy](https://technet.microsoft.com/library/Gg425772(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6523e-116">[設定-CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6523e-116">[Set-CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6523e-117">[新しい-CsClientPolicyEntry](https://technet.microsoft.com/library/Gg399046(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6523e-117">[New-CsClientPolicyEntry](https://technet.microsoft.com/library/Gg399046(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6523e-118">[-CsClientVersionConfiguration の取得](https://technet.microsoft.com/library/Gg399072(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6523e-118">[Get-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399072(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6523e-119">[新しい-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6523e-119">[New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6523e-120">[-CsClientVersionConfiguration の削除](https://technet.microsoft.com/library/Gg425925(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6523e-120">[Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6523e-121">[-CsClientVersionConfiguration の設定](https://technet.microsoft.com/library/Gg398623(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6523e-121">[Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6523e-122">[-CsClientVersionPolicy の取得](https://technet.microsoft.com/library/Gg398957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6523e-122">[Get-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398957(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6523e-123">[Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg412903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6523e-123">[Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg412903(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6523e-124">[新しい-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6523e-124">[New-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398709(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6523e-125">[-CsClientVersionPolicy の削除](https://technet.microsoft.com/library/Gg425801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6523e-125">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg425801(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6523e-126">[-CsClientVersionPolicy の設定](https://technet.microsoft.com/library/Gg398876(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6523e-126">[Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6523e-127">[-CsClientVersionPolicyRule の取得](https://technet.microsoft.com/library/Gg413048(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6523e-127">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg413048(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6523e-128">[新しい-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398905(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6523e-128">[New-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398905(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6523e-129">[-CsClientVersionPolicyRule の削除](https://technet.microsoft.com/library/Gg398541(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6523e-129">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398541(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6523e-130">[Set-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg425790(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6523e-130">[Set-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg425790(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

