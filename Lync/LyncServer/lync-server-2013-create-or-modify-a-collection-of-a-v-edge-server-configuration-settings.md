---
title: A/V Edge サーバー構成設定のコレクションを作成または変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c4b45b34b5c52d0eb138fbc16c37e5aaee7262b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="2bff8-102">Lync Server 2013 での A/V Edge サーバー構成設定のコレクションを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="2bff8-102">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bff8-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2bff8-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2bff8-104">A/V Edge サービスは、内部ユーザー (組織のネットワークにログオンしているユーザー) が、外部ユーザー (組織のネットワークにログオンしていないユーザー) とオーディオやビデオを共有できるようにするための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="2bff8-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="2bff8-105">A/V edge サービスは、主に、A/V Edge 構成設定を使用して管理されます。これは、サイトスコープまたはサービスの範囲で構成できます (つまり、個々の A/V Edge サーバー用に構成できます)。</span><span class="sxs-lookup"><span data-stu-id="2bff8-105">The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="2bff8-106">Lync Server をインストールすると、A/V Edge のグローバルコレクションが設定されます。</span><span class="sxs-lookup"><span data-stu-id="2bff8-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="2bff8-107">さらに、Windows PowerShell と CsAVEdgeConfiguration コマンドレットを使用して、サイトのスコープまたはサービスのスコープ (つまり、個別の A/V Edge サーバーの場合) で新しい設定を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2bff8-107">In addition to that, you can use the Windows PowerShell and the New-CsAVEdgeConfiguration cmdlet to create new settings at the site scope or the service scope (that is, for an individual A/V Edge server).</span></span> <span data-ttu-id="2bff8-108">新しい設定を作成する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="2bff8-108">If you create new settings keep in mind that:</span></span>

  - <span data-ttu-id="2bff8-109">サービスの範囲 (つまり個々のサーバー) で構成された設定は、すべてのユーザーに対して優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="2bff8-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="2bff8-110">サイトのスコープで構成された設定は、グローバルスコープで構成されている設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="2bff8-110">Settings configured at the site scope take priority over settings configured at the global scope.</span></span> <span data-ttu-id="2bff8-111">ただし、サービスの範囲設定は、サイトの範囲設定にも優先されます。</span><span class="sxs-lookup"><span data-stu-id="2bff8-111">However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="2bff8-112">グローバルスコープの設定は、個々のサーバーで構成されているサービス設定がなく、そのサーバーが配置されているサイトのサイト設定がない場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="2bff8-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="2bff8-113">設定を変更するには、CsAVEdgeConfiguration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2bff8-113">Any of your settings can then be modified by using the Set-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="2bff8-114">詳細については、 [CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))および[CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bff8-114">For more information, see the help topics for the [New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15)) and the [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15)) cmdlets.</span></span>

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="2bff8-115">新しい A/V Edge の構成設定をサイトのスコープで作成するには</span><span class="sxs-lookup"><span data-stu-id="2bff8-115">To create new A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="2bff8-116">次のコマンドは、Redmond サイトの A/V Edge 構成設定の新しいコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2bff8-116">The following command creates a new collection of A/V Edge configuration settings for the Redmond site:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="2bff8-117">ユーザー設定の A/V Edge の構成設定をサイトのスコープで作成するには</span><span class="sxs-lookup"><span data-stu-id="2bff8-117">To create custom A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="2bff8-118">追加のパラメーターが含まれていないため、これらの新しい設定では、A/V Edge サービスの既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2bff8-118">Because no additional parameters were included, these new settings will use the default values for the A/V Edge service.</span></span> <span data-ttu-id="2bff8-119">または、追加のパラメーターとパラメーター値を追加して、カスタムコレクションを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2bff8-119">Alternatively, you can add additional parameters and parameter values to create a custom collection.</span></span> <span data-ttu-id="2bff8-120">たとえば、次のコマンドは MaxTokenLifetime プロパティを4時間 (04 時間:00 分:00 秒) に設定します。</span><span class="sxs-lookup"><span data-stu-id="2bff8-120">For example, this command sets the MaxTokenLifetime property to 4 hours (04 hours : 00 minutes : 00 seconds):</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a><span data-ttu-id="2bff8-121">カスタムの A/V Edge の構成設定をサービスのスコープで作成するには</span><span class="sxs-lookup"><span data-stu-id="2bff8-121">To create custom A/V Edge configuration settings at the service scope</span></span>

  - <span data-ttu-id="2bff8-122">このコマンドは、A/V Edge サーバー atl-edge-001.litwareinc.com に適用される同様のコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2bff8-122">This command creates a similar collection applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a><span data-ttu-id="2bff8-123">既存の A/V Edge の構成設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="2bff8-123">To modify existing A/V Edge configuration settings</span></span>

  - <span data-ttu-id="2bff8-124">この例では、CsAVEdgeConfiguration コマンドレットを使用して、Redmond サイトの最大トークンの有効期間を12時間に変更します。</span><span class="sxs-lookup"><span data-stu-id="2bff8-124">In this example, the Set-CsAVEdgeConfiguration cmdlet is used to change the maximum token lifetime for the Redmond site to 12 hours:</span></span>
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2bff8-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bff8-125">See Also</span></span>


[<span data-ttu-id="2bff8-126">Lync Server 2013 で A/V Edge サーバーの構成情報を返す</span><span class="sxs-lookup"><span data-stu-id="2bff8-126">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="2bff8-127">Lync Server 2013 での既存の A/V エッジサーバー構成の設定を削除する</span><span class="sxs-lookup"><span data-stu-id="2bff8-127">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="2bff8-128">Lync Server 2013 の音声/ビデオ (A/V) エッジサーバー</span><span class="sxs-lookup"><span data-stu-id="2bff8-128">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="2bff8-129">[新規-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2bff8-129">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span></span>  
<span data-ttu-id="2bff8-130">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2bff8-130">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

