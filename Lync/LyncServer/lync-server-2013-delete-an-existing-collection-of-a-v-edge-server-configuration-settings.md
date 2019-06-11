---
title: 既存の A/V Edge サーバー構成設定のコレクションを削除する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6af42c338cb7032231ce562ac2227ff4089729ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="a1d75-102">Lync Server 2013 での既存の A/V エッジサーバー構成の設定を削除する</span><span class="sxs-lookup"><span data-stu-id="a1d75-102">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1d75-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a1d75-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a1d75-104">A/V Edge サービスは、内部ユーザー (組織のネットワークにログオンしているユーザー) が、外部ユーザー (組織のネットワークにログオンしていないユーザー) とオーディオやビデオを共有できるようにするための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="a1d75-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="a1d75-105">A/V edge サービスは、主に、A/V Edge 構成設定を使用して管理されます。これは、サイトスコープまたはサービスの範囲で構成できます (つまり、個々の A/V Edge サーバー用に構成できます)。</span><span class="sxs-lookup"><span data-stu-id="a1d75-105">The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="a1d75-106">Lync Server をインストールすると、A/V Edge のグローバルコレクションが設定されます。</span><span class="sxs-lookup"><span data-stu-id="a1d75-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="a1d75-107">このグローバルコレクションは削除できません。</span><span class="sxs-lookup"><span data-stu-id="a1d75-107">This global collection cannot be deleted.</span></span> <span data-ttu-id="a1d75-108">ただし、Windows PowerShell と CsAVEdgeConfiguration コマンドレットを使用して、グローバルコレクションを "リセット" することができます。つまり、グローバルコレクションのすべてのプロパティ値が既定値にリセットされるということです。</span><span class="sxs-lookup"><span data-stu-id="a1d75-108">However, you can use the Windows PowerShell and the Remove-CsAVEdgeConfiguration cmdlet to "reset" the global collection; that simply means that all the property values in the global collection will be reset to their default value.</span></span> <span data-ttu-id="a1d75-109">たとえば、MaxTokenLifetime プロパティを16時間として設定した場合、そのプロパティは既定値の8時間にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="a1d75-109">For example, if you have set the MaxTokenLifetime property for 16 hours, that property will be reset to its default value of 8 hours.</span></span>

<span data-ttu-id="a1d75-110">ただし、サイトスコープまたはサービスのスコープで作成したカスタム設定コレクションは、CsAVEdgeConfiguration コマンドレットを使用して削除できます。</span><span class="sxs-lookup"><span data-stu-id="a1d75-110">However, custom settings collections that you have created at either the site scope or the service scope can be deleted by using the Remove-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="a1d75-111">サイトの設定を削除すると、そのサイトの A/V エッジサーバーはグローバル設定によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="a1d75-111">If you delete site settings then A/V Edge servers in that site will be managed by the global settings.</span></span> <span data-ttu-id="a1d75-112">サービス範囲の設定を削除すると、そのサーバーはそのサイトの設定 (存在する場合)、またはサイトの設定がない場合はグローバル設定によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="a1d75-112">If you delete service-scope settings,, that server will then be managed by its site settings, if they exist, or by the global settings if no site settings are available.</span></span>

<span data-ttu-id="a1d75-113">詳細については、 [CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1d75-113">For more information, see the help topic for the [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15)) cmdlet.</span></span>

<div>

## <a name="to-reset-the-global-collection"></a><span data-ttu-id="a1d75-114">グローバルコレクションをリセットするには</span><span class="sxs-lookup"><span data-stu-id="a1d75-114">To reset the global collection</span></span>

  - <span data-ttu-id="a1d75-115">次のコマンドを実行すると、A/V Edge の構成設定のグローバルコレクションがリセットされます。</span><span class="sxs-lookup"><span data-stu-id="a1d75-115">The following command resets the global collection of A/V Edge configuration settings:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a><span data-ttu-id="a1d75-116">サイトのスコープからコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="a1d75-116">To remove a collection from the site scope</span></span>

  - <span data-ttu-id="a1d75-117">このコマンドは、Redmond サイトに適用されている A/V Edge 構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="a1d75-117">This command removes the A/V Edge configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a><span data-ttu-id="a1d75-118">サービスのスコープからコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="a1d75-118">To remove a collection from the service scope</span></span>

  - <span data-ttu-id="a1d75-119">このコマンドは、A/V Edge サーバー atl-edge-001.litwareinc.com に適用されている設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="a1d75-119">This command removes the settings applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a1d75-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1d75-120">See Also</span></span>


[<span data-ttu-id="a1d75-121">Lync Server 2013 で A/V Edge サーバーの構成情報を返す</span><span class="sxs-lookup"><span data-stu-id="a1d75-121">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="a1d75-122">Lync Server 2013 での A/V Edge サーバー構成設定のコレクションを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="a1d75-122">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="a1d75-123">Lync Server 2013 の音声/ビデオ (A/V) エッジサーバー</span><span class="sxs-lookup"><span data-stu-id="a1d75-123">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="a1d75-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a1d75-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

