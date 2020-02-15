---
title: 音声ビデオエッジサーバー構成設定のコレクションを作成または変更する
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
ms.openlocfilehash: 576fcb445eb37b92356ad9fdf36de716581ca6fa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="059cd-102">Lync Server 2013 での音声ビデオエッジサーバー構成設定のコレクションの作成または変更</span><span class="sxs-lookup"><span data-stu-id="059cd-102">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="059cd-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="059cd-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="059cd-p101">音声ビデオ エッジ サービスにより、内部ユーザー (組織のネットワークにログオンしているユーザー) は、外部ユーザー (組織のネットワークにログオンしていないユーザー) と音声とビデオを共有することができます。音声ビデオ エッジ サービスは、主に音声ビデオ エッジ構成設定を使用して管理されます。音声ビデオ エッジ構成設定は、サイト スコープまたはサービス スコープで (つまり音声ビデオ エッジ サーバーごとに) 設定できます。</span><span class="sxs-lookup"><span data-stu-id="059cd-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="059cd-106">Lync Server をインストールすると、音声ビデオエッジ構成設定のグローバルコレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="059cd-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="059cd-107">また、Windows PowerShell と Get-csavedgeconfiguration コマンドレットを使用して、サイトスコープまたはサービススコープ (つまり、個々の音声ビデオエッジサーバーの場合) で新しい設定を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="059cd-107">In addition to that, you can use the Windows PowerShell and the New-CsAVEdgeConfiguration cmdlet to create new settings at the site scope or the service scope (that is, for an individual A/V Edge server).</span></span> <span data-ttu-id="059cd-108">新しい設定を作成する場合は、次のことに留意してください。</span><span class="sxs-lookup"><span data-stu-id="059cd-108">If you create new settings keep in mind that:</span></span>

  - <span data-ttu-id="059cd-109">サービス スコープで (つまり個々のサーバーに) 構成された設定は、すべてに優先されます。</span><span class="sxs-lookup"><span data-stu-id="059cd-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="059cd-p103">サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。ただし、サービス スコープ設定はサイトスコープ設定を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="059cd-p103">Settings configured at the site scope take priority over settings configured at the global scope. However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="059cd-112">個々のサーバーでサービス設定が構成されていない場合、およびサーバーが配置されているサイトにサイト設定が存在しない場合に限り、グローバル スコープの設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="059cd-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="059cd-113">すべての設定は、Set-CsAVEdgeConfiguration コマンドレットを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="059cd-113">Any of your settings can then be modified by using the Set-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="059cd-114">詳細については、 [get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))および[get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="059cd-114">For more information, see the help topics for the [New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) and the [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) cmdlets.</span></span>

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="059cd-115">サイトスコープで新しい音声ビデオエッジ構成設定を作成するには</span><span class="sxs-lookup"><span data-stu-id="059cd-115">To create new A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="059cd-116">以下のコマンドでは、Redmond サイト用の音声ビデオ エッジ構成設定の新しいコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="059cd-116">The following command creates a new collection of A/V Edge configuration settings for the Redmond site:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="059cd-117">サイトスコープでカスタムの音声ビデオエッジ構成設定を作成するには</span><span class="sxs-lookup"><span data-stu-id="059cd-117">To create custom A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="059cd-p105">追加のパラメーターが指定されない場合、これらの新しい設定では、音声ビデオ エッジ サービスに既定値が使用されます。あるいは、追加のパラメーターとパラメーター値を指定してカスタム コレクションを作成できます。たとえばこのコマンドでは、MaxTokenLifetime プロパティを 4 時間 (04 時間 : 00 分 : 00 秒) に設定します。</span><span class="sxs-lookup"><span data-stu-id="059cd-p105">Because no additional parameters were included, these new settings will use the default values for the A/V Edge service. Alternatively, you can add additional parameters and parameter values to create a custom collection. For example, this command sets the MaxTokenLifetime property to 4 hours (04 hours : 00 minutes : 00 seconds):</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a><span data-ttu-id="059cd-121">サービススコープでカスタムの音声ビデオエッジ構成設定を作成するには</span><span class="sxs-lookup"><span data-stu-id="059cd-121">To create custom A/V Edge configuration settings at the service scope</span></span>

  - <span data-ttu-id="059cd-122">このコマンドは、音声ビデオ エッジ サーバー atl-edge-001.litwareinc.com に適用される同様のコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="059cd-122">This command creates a similar collection applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a><span data-ttu-id="059cd-123">既存の音声ビデオエッジ構成設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="059cd-123">To modify existing A/V Edge configuration settings</span></span>

  - <span data-ttu-id="059cd-124">この例では、Redmond サイトの最大トークン存続時間を 12 時間に変更するために、Set-CsAVEdgeConfiguration コマンドレットが使用されます。</span><span class="sxs-lookup"><span data-stu-id="059cd-124">In this example, the Set-CsAVEdgeConfiguration cmdlet is used to change the maximum token lifetime for the Redmond site to 12 hours:</span></span>
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="059cd-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="059cd-125">See Also</span></span>


[<span data-ttu-id="059cd-126">Lync Server 2013 での音声ビデオエッジサーバーの構成情報の取得</span><span class="sxs-lookup"><span data-stu-id="059cd-126">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="059cd-127">Lync Server 2013 の音声ビデオエッジサーバー構成設定の既存コレクションの削除</span><span class="sxs-lookup"><span data-stu-id="059cd-127">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="059cd-128">Lync Server 2013 の音声ビデオ (A/V) エッジサーバー</span><span class="sxs-lookup"><span data-stu-id="059cd-128">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="059cd-129">[Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="059cd-129">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span></span>  
<span data-ttu-id="059cd-130">[Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="059cd-130">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

