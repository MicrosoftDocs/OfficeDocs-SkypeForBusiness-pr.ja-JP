---
title: SCOM 監視の構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e114d3f18e482c11a8e83c9d4308f3c5712932c
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a><span data-ttu-id="8189b-102">SCOM 監視の構成</span><span class="sxs-lookup"><span data-stu-id="8189b-102">Configure SCOM monitoring</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8189b-103">_**最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="8189b-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="8189b-104">Microsoft Lync Server 2013 に移行した後、いくつかのタスクを実行して、Lync Server 2013 が System Center Operations Manager と連携するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8189b-104">After migrating to Microsoft Lync Server 2013, you must complete a few tasks to configure Lync Server 2013 to work with System Center Operations Manager.</span></span>

  - <span data-ttu-id="8189b-105">サーバーに Lync Server 2010 更新プログラムを適用して、セントラル検出ロジックを管理します。</span><span class="sxs-lookup"><span data-stu-id="8189b-105">Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.</span></span>

  - <span data-ttu-id="8189b-106">セントラル探索候補サーバーのレジストリキーを更新します。</span><span class="sxs-lookup"><span data-stu-id="8189b-106">Update the central discovery candidate server registry key.</span></span>

  - <span data-ttu-id="8189b-107">"候補" セントラル探索ノードを上書きするように、プライマリ System Center Operations Manager management サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="8189b-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>

<span data-ttu-id="8189b-108">これらの各タスクを実行する手順については、以下で説明します。</span><span class="sxs-lookup"><span data-stu-id="8189b-108">Instructions for carrying out each of these tasks are provided below.</span></span>

<span data-ttu-id="8189b-109">**サーバーに Lync Server 2010 更新プログラムを適用して、セントラル検出ロジックを管理します。**</span><span class="sxs-lookup"><span data-stu-id="8189b-109">**Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.**</span></span>

1.  <span data-ttu-id="8189b-110">System Center Operations Manager エージェントファイルがインストールされ、候補探索ノードとして構成されているサーバーを選びます。</span><span class="sxs-lookup"><span data-stu-id="8189b-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span>

2.  <span data-ttu-id="8189b-111">このサーバーに Lync Server 2010 の更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="8189b-111">Apply Lync Server 2010 updates to this server.</span></span> <span data-ttu-id="8189b-112">「 [Lync Server 2010 更新プログラムの適用](apply-lync-server-2010-updates.md)」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8189b-112">See the topic [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).</span></span>

<span data-ttu-id="8189b-113">**セントラル探索候補サーバーのレジストリキーを更新します。**</span><span class="sxs-lookup"><span data-stu-id="8189b-113">**Update the central discovery candidate server registry key.**</span></span>

1.  <span data-ttu-id="8189b-114">サーバー上でセントラル検出ロジックを管理することを選択した場合は、Windows PowerShell コマンドウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="8189b-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span>

2.  <span data-ttu-id="8189b-115">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8189b-115">At the command line, type the following:</span></span>
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="8189b-116">レジストリを編集すると、レジストリキーが既に存在する場合に、コマンドが失敗するというエラーが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="8189b-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="8189b-117">この問題が発生した場合は、エラーを無視しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="8189b-117">If you experience this, you can safely ignore the error.</span></span>

    
    </div>

<span data-ttu-id="8189b-118">**主要な System Center Operations Manager management server を構成して、[セントラル探索の候補となるサービスの管理者ノードを上書きする。**</span><span class="sxs-lookup"><span data-stu-id="8189b-118">**Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.**</span></span>

1.  <span data-ttu-id="8189b-119">System Center Operations Manager コンソールがインストールされているコンピューターで、[**管理パックのオブジェクト**] を展開し、[**オブジェクト**検出] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8189b-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>

2.  <span data-ttu-id="8189b-120">[**範囲の変更] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="8189b-120">Click **Change Scope...**</span></span>

3.  <span data-ttu-id="8189b-121">[**スコープ管理パックのオブジェクト**] ページで、[ **LS 検出候補**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8189b-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>

4.  <span data-ttu-id="8189b-122">**LS 検出候補の有効値**を、前の手順で選択した候補サーバーの名前に上書きします。</span><span class="sxs-lookup"><span data-stu-id="8189b-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span>

<span data-ttu-id="8189b-123">最後に、変更内容を確定するには、System Center Operations Manager ルート管理サーバーで正常性サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="8189b-123">Lastly, to finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

