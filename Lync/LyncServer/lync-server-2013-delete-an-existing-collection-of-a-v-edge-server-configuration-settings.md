---
title: 音声ビデオエッジサーバー構成設定の既存コレクションの削除
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7043b2ce5fd35e36615b7b92d1561d725a86cc92
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="2dd17-102">Lync Server 2013 の音声ビデオエッジサーバー構成設定の既存コレクションの削除</span><span class="sxs-lookup"><span data-stu-id="2dd17-102">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2dd17-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2dd17-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2dd17-p101">音声ビデオ エッジ サービスにより、内部ユーザー (組織のネットワークにログオンしているユーザー) は、外部ユーザー (組織のネットワークにログオンしていないユーザー) と音声とビデオを共有することができます。音声ビデオ エッジ サービスは、主に音声ビデオ エッジ構成設定を使用して管理されます。音声ビデオ エッジ構成設定は、サイト スコープまたはサービス スコープで (つまり音声ビデオ エッジ サーバーごとに) 設定できます。</span><span class="sxs-lookup"><span data-stu-id="2dd17-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="2dd17-106">Lync Server をインストールすると、音声ビデオエッジ構成設定のグローバルコレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2dd17-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="2dd17-107">このグローバルコレクションは削除できません。</span><span class="sxs-lookup"><span data-stu-id="2dd17-107">This global collection cannot be deleted.</span></span> <span data-ttu-id="2dd17-108">ただし、Windows PowerShell と Get-csavedgeconfiguration コマンドレットを使用して、グローバルコレクションを "リセット" することができます。これは単に、グローバルコレクション内のすべてのプロパティ値が既定値にリセットされることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2dd17-108">However, you can use the Windows PowerShell and the Remove-CsAVEdgeConfiguration cmdlet to "reset" the global collection; that simply means that all the property values in the global collection will be reset to their default value.</span></span> <span data-ttu-id="2dd17-109">たとえば、MaxTokenLifetime プロパティを16時間に設定した場合、そのプロパティは既定値の8時間にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="2dd17-109">For example, if you have set the MaxTokenLifetime property for 16 hours, that property will be reset to its default value of 8 hours.</span></span>

<span data-ttu-id="2dd17-p103">ただし、サイト スコープまたはサービス スコープのどちらかで作成したカスタム設定コレクションは、Remove-CsDiagnosticHeaderConfiguration コマンドレットを使用して削除できます。サイト設定を削除すると、そのサイト内の音声ビデオ エッジ サーバーはグローバル設定によって管理されます。サービス スコープの設定を削除すると、サーバーは、サイト設定が存在する場合はサイト設定によって、サイト設定が使用できない場合はグローバル設定によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="2dd17-p103">However, custom settings collections that you have created at either the site scope or the service scope can be deleted by using the Remove-CsAVEdgeConfiguration cmdlet. If you delete site settings then A/V Edge servers in that site will be managed by the global settings. If you delete service-scope settings,, that server will then be managed by its site settings, if they exist, or by the global settings if no site settings are available.</span></span>

<span data-ttu-id="2dd17-113">詳細については、 [get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dd17-113">For more information, see the help topic for the [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) cmdlet.</span></span>

<div>

## <a name="to-reset-the-global-collection"></a><span data-ttu-id="2dd17-114">グローバルコレクションをリセットするには</span><span class="sxs-lookup"><span data-stu-id="2dd17-114">To reset the global collection</span></span>

  - <span data-ttu-id="2dd17-115">次のコマンドは、音声ビデオ エッジ構成設定のグローバル コレクションをリセットします。</span><span class="sxs-lookup"><span data-stu-id="2dd17-115">The following command resets the global collection of A/V Edge configuration settings:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a><span data-ttu-id="2dd17-116">サイトスコープからコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="2dd17-116">To remove a collection from the site scope</span></span>

  - <span data-ttu-id="2dd17-117">次のコマンドは、Redmond サイトに適用される音声ビデオ エッジ構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="2dd17-117">This command removes the A/V Edge configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a><span data-ttu-id="2dd17-118">サービススコープからコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="2dd17-118">To remove a collection from the service scope</span></span>

  - <span data-ttu-id="2dd17-119">次のコマンドは、音声ビデオ エッジ サーバー atl-edge-001.litwareinc.com に適用される設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="2dd17-119">This command removes the settings applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2dd17-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="2dd17-120">See Also</span></span>


[<span data-ttu-id="2dd17-121">Lync Server 2013 での音声ビデオエッジサーバーの構成情報の取得</span><span class="sxs-lookup"><span data-stu-id="2dd17-121">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="2dd17-122">Lync Server 2013 での音声ビデオエッジサーバー構成設定のコレクションの作成または変更</span><span class="sxs-lookup"><span data-stu-id="2dd17-122">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="2dd17-123">Lync Server 2013 の音声ビデオ (A/V) エッジサーバー</span><span class="sxs-lookup"><span data-stu-id="2dd17-123">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="2dd17-124">[Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2dd17-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

