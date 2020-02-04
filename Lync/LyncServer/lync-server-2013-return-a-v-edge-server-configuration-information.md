---
title: 'Lync Server 2013: A/V Edge サーバー構成情報を返す'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea7d7ed1ef74c092dac60ecfb2f009219564455
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a><span data-ttu-id="aa951-102">Lync Server 2013 で A/V Edge サーバーの構成情報を返す</span><span class="sxs-lookup"><span data-stu-id="aa951-102">Return A/V Edge Server configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa951-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="aa951-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="aa951-104">A/V Edge サービスは、内部ユーザー (組織のネットワークにログオンしているユーザー) が、外部ユーザー (組織のネットワークにログオンしていないユーザー) とオーディオやビデオを共有できるようにするための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="aa951-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="aa951-105">A/V edge サービスは、主に、A/V Edge 構成設定を使用して管理されます。これは、サイトスコープまたはサービスの範囲で構成できます (つまり、個々の A/V Edge サーバー用に構成できます)。</span><span class="sxs-lookup"><span data-stu-id="aa951-105">The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="aa951-106">組織で使用されている A/V Edge 構成の設定に関する情報を返すには、Windows PowerShell と CsAVEdgeConfiguration コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa951-106">To return information about the A/V Edge configuration settings in use in your organization, you must use Windows PowerShell and the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="aa951-107">詳細については、 [CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa951-107">For more information, see the help topic for the [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) cmdlet.</span></span>

<span data-ttu-id="aa951-108">CsAVEdgeConfiguration コマンドレットから返される情報は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="aa951-108">Information returned from the Get-CsAVEdgeConfiguration cmdlet will look similar to this:</span></span>

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a><span data-ttu-id="aa951-109">すべての A/V Edge の構成設定に関する情報を返すには</span><span class="sxs-lookup"><span data-stu-id="aa951-109">To return information for all your A/V Edge configuration settings</span></span>

  - <span data-ttu-id="aa951-110">次のコマンドは、組織で現在使用されているすべての A/V Edge の構成設定に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="aa951-110">The following command returns information about all the A/V Edge configuration settings currently in use in your organization:</span></span>
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a><span data-ttu-id="aa951-111">サイトスコープの A/V Edge の構成設定に関する情報を返すには</span><span class="sxs-lookup"><span data-stu-id="aa951-111">To return information for site-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="aa951-112">A/V Edge の構成設定の特定のコレクションに関する情報を返すには、CsAVEdgeConfiguration コマンドレットを実行するときにそのコレクションの Id を指定します。</span><span class="sxs-lookup"><span data-stu-id="aa951-112">To return information about a specific collection of A/V Edge configuration settings, specify the Identity of that collection when running the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="aa951-113">たとえば、次のコマンドは、Redmond サイトに適用されている設定についてのみ情報を返します。</span><span class="sxs-lookup"><span data-stu-id="aa951-113">For example, this command returns information only for the settings applied to the Redmond site:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a><span data-ttu-id="aa951-114">サービススコープの A/V Edge の構成設定に関する情報を返すには</span><span class="sxs-lookup"><span data-stu-id="aa951-114">To return information for service-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="aa951-115">このコマンドは、特定の A/V エッジサーバーに適用された設定についてのみ情報を返します。</span><span class="sxs-lookup"><span data-stu-id="aa951-115">And this command returns information only for settings applied the a specific A/V Edge server:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aa951-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa951-116">See Also</span></span>


[<span data-ttu-id="aa951-117">Lync Server 2013 での A/V Edge サーバー構成設定のコレクションを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="aa951-117">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[<span data-ttu-id="aa951-118">Lync Server 2013 での既存の A/V エッジサーバー構成の設定を削除する</span><span class="sxs-lookup"><span data-stu-id="aa951-118">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="aa951-119">Lync Server 2013 の音声/ビデオ (A/V) エッジサーバー</span><span class="sxs-lookup"><span data-stu-id="aa951-119">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

