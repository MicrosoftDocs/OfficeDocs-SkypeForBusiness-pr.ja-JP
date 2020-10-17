---
title: Lync Server 2013 のシナリオを構成する
description: Lync Server 2013 のシナリオを構成します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4a5b7bd271191067779ac358807cc54918b16bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555463"
---
# <a name="configure-lync-server-2013-scenarios"></a><span data-ttu-id="d1b8d-103">Lync Server 2013 のシナリオを構成する</span><span class="sxs-lookup"><span data-stu-id="d1b8d-103">Configure Lync Server 2013 Scenarios</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1b8d-104">_**トピックの最終更新日:** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="d1b8d-104">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="d1b8d-105">Lync Server 2013 のストレスおよびパフォーマンスツール (LyncPerfTool) を実行するには、最初に Lync Server 2013 トポロジを、実行するシナリオに対して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1b8d-105">To run the Lync Server 2013 Stress and Performance Tool (LyncPerfTool), the Lync Server 2013 topology must first be configured for the scenarios that will be executed.</span></span> <span data-ttu-id="d1b8d-106">Lync Server 2013 が構成されていない場合や、正しく構成されていない場合は、ほとんどの場合、負荷シミュレーションは失敗します。</span><span class="sxs-lookup"><span data-stu-id="d1b8d-106">If Lync Server 2013 is not configured or is configured incorrectly, load simulation will fail in most cases.</span></span> <span data-ttu-id="d1b8d-107">Lync server 2013 のストレスおよびパフォーマンスツールを使用して、lync server の管理シェルスクリプトと基本的なリソースファイルの例をご用意しました。これは、Lync Server 2013 を構成するための開始点として使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1b8d-107">With the Lync Server 2013 Stress and Performance Tool, we have provided example Lync Server Management Shell scripts and basic resource files that can be used as a starting point for configuring Lync Server 2013.</span></span> <span data-ttu-id="d1b8d-108">このトピックでは、提供されている Windows PowerShell の例について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1b8d-108">This topic describes the Windows PowerShell examples provided.</span></span> <span data-ttu-id="d1b8d-109">このトピックでは、一般に Lync Server 2013 を構成する方法については説明していないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d1b8d-109">Note that it is not the goal of this topic to describe how to configure Lync Server 2013 in general.</span></span> <span data-ttu-id="d1b8d-110">Lync Server 2013 での Windows PowerShell の使用の詳細については、「Lync Server Management Shell」のドキュメントを参照してください <https://technet.microsoft.com/library/gg398474.aspx> 。</span><span class="sxs-lookup"><span data-stu-id="d1b8d-110">For details about working with Windows PowerShell in Lync Server 2013, see the Lync Server Management Shell documentation at <https://technet.microsoft.com/library/gg398474.aspx>.</span></span>

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a><span data-ttu-id="d1b8d-111">Lync Server 管理シェルスクリプトの実行について</span><span class="sxs-lookup"><span data-stu-id="d1b8d-111">About Running Lync Server Management Shell Scripts</span></span>

<span data-ttu-id="d1b8d-112">ここでは、負荷シミュレーションを実行するための準備に使用できる Lync Server 管理シェルスクリプトの例を提供しています。</span><span class="sxs-lookup"><span data-stu-id="d1b8d-112">We have provided example Lync Server Management Shell scripts that may be used in preparation for running load simulation.</span></span> <span data-ttu-id="d1b8d-113">スクリプトは負荷シミュレーションを目的としているため、単純で寛容なものであるため、運用環境には適していない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d1b8d-113">Because the scripts are intended for load simulation, they are simple and permissive, and therefore may not be appropriate for production.</span></span> <span data-ttu-id="d1b8d-114">すべてのスクリプトは例であり、場合によっては、トポロジを反映するように変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1b8d-114">All scripts are examples and must be reviewed, and, in some cases, modified to reflect your topology.</span></span> <span data-ttu-id="d1b8d-115">少なくとも、応答グループサービス (RGS) シナリオは、エージェントグループに割り当てられるエージェントを指定するように変更する必要があると考えられます。</span><span class="sxs-lookup"><span data-stu-id="d1b8d-115">At a minimum, we expect that the Response Group Service (RGS) scenario would need to be modified to specify the agents that are assigned to the agent groups.</span></span> <span data-ttu-id="d1b8d-116">ただし、この負荷をシミュレートするオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="d1b8d-116">However, you have the option to not simulate this load.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="d1b8d-117">提供される例を確認し、理解してください。</span><span class="sxs-lookup"><span data-stu-id="d1b8d-117">Take care in reviewing and understanding the examples provided.</span></span> <span data-ttu-id="d1b8d-118">スクリプトは、トポロジ内の既存の設定を上書きします。</span><span class="sxs-lookup"><span data-stu-id="d1b8d-118">Scripts will overwrite any existing settings in the topology.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d1b8d-119">Windows PowerShell および Lync Server 管理シェルの使用の詳細については、「Lync Server 2013 Windows PowerShell のブログ」を参照してください <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A> 。</span><span class="sxs-lookup"><span data-stu-id="d1b8d-119">For details about using Windows PowerShell and the Lync Server Management Shell, see the Lync Server 2013 Windows PowerShell Blog at <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>.</span></span>



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a><span data-ttu-id="d1b8d-120">ストレスおよびパフォーマンスツールクライアントバージョンモニカー</span><span class="sxs-lookup"><span data-stu-id="d1b8d-120">Stress and Performance Tool Client Version Monikers</span></span>

<span data-ttu-id="d1b8d-121">既定値の設定を変更した場合、クライアントバージョンチェックポリシーを構成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d1b8d-121">You may need to configure the Client Version Check policy if you have changed the settings from the default values.</span></span> <span data-ttu-id="d1b8d-122">詳細については、「」の「サポートされているクライアントバージョンを構成する」を参照してください <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx> 。</span><span class="sxs-lookup"><span data-stu-id="d1b8d-122">For details, see “Configuring supported client versions” at <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx>.</span></span> <span data-ttu-id="d1b8d-123">Lync server 2013 のストレスおよびパフォーマンスツールは、Lync Server 2013 と通信するときに既定で次のユーザーエージェントバージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1b8d-123">The Lync Server 2013 Stress and Performance Tool uses the following User Agent Versions by default when communicating with Lync Server 2013:</span></span>

  - <span data-ttu-id="d1b8d-124">LSPT/15.0.0.0 です (Lync Server 2013 ストレスおよびパフォーマンスツール)</span><span class="sxs-lookup"><span data-stu-id="d1b8d-124">LSPT/15.0.0.0 (Lync Server 2013 Stress and Performance Tool)</span></span>

  - <span data-ttu-id="d1b8d-125">OCPHONE/. 0.522</span><span class="sxs-lookup"><span data-stu-id="d1b8d-125">OCPHONE/.0.522</span></span>

<span data-ttu-id="d1b8d-126">LyncPerfTool のモビリティ (UCWA) クライアントの場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d1b8d-126">These are for the Mobility (UCWA) client in LyncPerfTool:</span></span>

  - <span data-ttu-id="d1b8d-127">Ucwa Perf ツール/Web 会議</span><span class="sxs-lookup"><span data-stu-id="d1b8d-127">Ucwa Perf Tool/Web Conference</span></span>

  - <span data-ttu-id="d1b8d-128">Ucwa Perf ツール/モバイル</span><span class="sxs-lookup"><span data-stu-id="d1b8d-128">Ucwa Perf Tool/Mobile</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

