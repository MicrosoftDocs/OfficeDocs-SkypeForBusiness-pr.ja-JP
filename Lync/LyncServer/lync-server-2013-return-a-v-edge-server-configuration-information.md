---
title: 'Lync Server 2013: 音声ビデオエッジサーバーの構成情報を返す'
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
ms.openlocfilehash: 50cfd257e387c48af8446adc43b25d4fd0818ea5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a><span data-ttu-id="8e5a6-102">Lync Server 2013 での音声ビデオエッジサーバーの構成情報の取得</span><span class="sxs-lookup"><span data-stu-id="8e5a6-102">Return A/V Edge Server configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e5a6-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8e5a6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8e5a6-p101">音声ビデオ エッジ サービスにより、内部ユーザー (組織のネットワークにログオンしているユーザー) は、外部ユーザー (組織のネットワークにログオンしていないユーザー) と音声とビデオを共有することができます。音声ビデオ エッジ サービスは、主に音声ビデオ エッジ構成設定を使用して管理されます。音声ビデオ エッジ構成設定は、サイト スコープまたはサービス スコープで (つまり音声ビデオ エッジ サーバーごとに) 設定できます。</span><span class="sxs-lookup"><span data-stu-id="8e5a6-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="8e5a6-106">組織で使用されている音声ビデオエッジ構成設定に関する情報を戻すには、Windows PowerShell と Get-csavedgeconfiguration コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e5a6-106">To return information about the A/V Edge configuration settings in use in your organization, you must use Windows PowerShell and the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="8e5a6-107">詳細については、 [get-csavedgeconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e5a6-107">For more information, see the help topic for the [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) cmdlet.</span></span>

<span data-ttu-id="8e5a6-108">Get-CsAVEdgeConfiguration コマンドレットからは次のような情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="8e5a6-108">Information returned from the Get-CsAVEdgeConfiguration cmdlet will look similar to this:</span></span>

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a><span data-ttu-id="8e5a6-109">すべての音声ビデオエッジ構成設定に関する情報を戻すには</span><span class="sxs-lookup"><span data-stu-id="8e5a6-109">To return information for all your A/V Edge configuration settings</span></span>

  - <span data-ttu-id="8e5a6-110">次のコマンドを実行すると、組織で現在使用中のすべての音声ビデオ エッジ構成設定に関する情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="8e5a6-110">The following command returns information about all the A/V Edge configuration settings currently in use in your organization:</span></span>
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a><span data-ttu-id="8e5a6-111">サイトスコープの音声ビデオエッジ構成設定に関する情報を戻すには</span><span class="sxs-lookup"><span data-stu-id="8e5a6-111">To return information for site-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="8e5a6-p103">音声ビデオ エッジ構成設定の特定のコレクションに関する情報を返すには、Get-CsAVEdgeConfiguration コマンドレットの実行時にそのコレクションの識別子を指定します。たとえば、次のコマンドでは、Redmond サイトに適用されている設定に関する情報のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="8e5a6-p103">To return information about a specific collection of A/V Edge configuration settings, specify the Identity of that collection when running the Get-CsAVEdgeConfiguration cmdlet. For example, this command returns information only for the settings applied to the Redmond site:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a><span data-ttu-id="8e5a6-114">サービススコープの音声ビデオエッジ構成設定に関する情報を戻すには</span><span class="sxs-lookup"><span data-stu-id="8e5a6-114">To return information for service-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="8e5a6-115">次のコマンドでは、特定の音声ビデオ エッジ サーバーに適用された設定に関する情報のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="8e5a6-115">And this command returns information only for settings applied the a specific A/V Edge server:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8e5a6-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e5a6-116">See Also</span></span>


[<span data-ttu-id="8e5a6-117">Lync Server 2013 での音声ビデオエッジサーバー構成設定のコレクションの作成または変更</span><span class="sxs-lookup"><span data-stu-id="8e5a6-117">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[<span data-ttu-id="8e5a6-118">Lync Server 2013 の音声ビデオエッジサーバー構成設定の既存コレクションの削除</span><span class="sxs-lookup"><span data-stu-id="8e5a6-118">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="8e5a6-119">Lync Server 2013 の音声ビデオ (A/V) エッジサーバー</span><span class="sxs-lookup"><span data-stu-id="8e5a6-119">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

