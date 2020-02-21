---
title: 'Lync Server 2013: 通話受付管理の展開チェックリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd1de11f9d169babc8a4367f429d9d99559d6aa6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="da1c6-102">Lync Server 2013 の通話受付管理の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="da1c6-102">Call admission control deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da1c6-103">_**トピックの最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="da1c6-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="da1c6-104">次のチェック リストを使用して、通話受付管理サービス (CAC) を展開するために必要なすべての構成タスクを完了したことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="da1c6-104">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy call admission control (CAC).</span></span>

  - <span data-ttu-id="da1c6-p101">1 つまたは複数のエッジ サーバーが展開されている場合には、32 ビット マスクのすべての外部インターフェイス IP アドレスがネットワーク構成設定のサブネット リストに追加されている必要があります。音声ビデオ エッジ サービスが展開されている地理的な場所のネットワーク サイト ID にこのサブネット (IP アドレス) を関連付ける必要もあります。</span><span class="sxs-lookup"><span data-stu-id="da1c6-p101">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32. You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da1c6-107">エッジ サーバーは CAC を実装する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="da1c6-107">Edge servers are not required to implement CAC.</span></span>

    
    </div>

  - <span data-ttu-id="da1c6-108">Lync Server コントロールパネルを使用するか、または「 [Lync server 2013 で通話受付管理を有効にする](lync-server-2013-enable-call-admission-control.md)」で指定されているコマンドレットを実行して、CAC が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="da1c6-108">Make sure that CAC is enabled, either through Lync Server Control Panel or by running the cmdlet as specified in [Enable call admission control in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span></span>

  - <span data-ttu-id="da1c6-109">すべてのセントラル サイトで CAC が有効化されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="da1c6-109">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="da1c6-110">これはトポロジビルダーを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="da1c6-110">This can be done through the Topology Builder.</span></span> <span data-ttu-id="da1c6-111">公開時に警告が生成された場合には、警告を無視しないでください。</span><span class="sxs-lookup"><span data-stu-id="da1c6-111">If a warning is generated when you publish, *do not* ignore it.</span></span>

  - <span data-ttu-id="da1c6-112">エンタープライズ ネットワークで管理されているすべてのサブネットがネットワーク構成設定で構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="da1c6-112">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="da1c6-113">また、「 [Lync Server 2013 でのネットワークサイトへのサブネットの関連付け](lync-server-2013-associate-a-subnet-with-a-network-site.md)」の説明に従って、すべてのサブネットがネットワークサイトに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="da1c6-113">It is also essential that every subnet be associated to a network site, as explained in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

  - <span data-ttu-id="da1c6-114">すべてのフロントエンド サーバー、存続可能ブランチ アプライアンス (SBA)、音声ビデオ会議サーバー (別プールの場合)、および仲介サーバーのサブネットまたは IP アドレスがネットワーク構成設定で構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="da1c6-114">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

