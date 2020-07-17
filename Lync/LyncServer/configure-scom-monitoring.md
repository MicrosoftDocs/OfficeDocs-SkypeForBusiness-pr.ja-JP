---
title: SCOM 監視の構成
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95bc54defed596dfa8a8d801908b281abf06ead3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a><span data-ttu-id="313d5-102">SCOM 監視の構成</span><span class="sxs-lookup"><span data-stu-id="313d5-102">Configure SCOM monitoring</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="313d5-103">_**トピックの最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="313d5-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="313d5-104">Microsoft Lync Server 2013 に移行した後で、Lync Server 2013 を System Center Operations Manager と連携するように構成するには、いくつかのタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="313d5-104">After migrating to Microsoft Lync Server 2013, you must complete a few tasks to configure Lync Server 2013 to work with System Center Operations Manager.</span></span>

  - <span data-ttu-id="313d5-105">中央検出ロジックを管理するために選択したサーバーに Lync Server 2010 の更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="313d5-105">Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.</span></span>

  - <span data-ttu-id="313d5-106">中央検出候補サーバーのレジストリ キーを更新する。</span><span class="sxs-lookup"><span data-stu-id="313d5-106">Update the central discovery candidate server registry key.</span></span>

  - <span data-ttu-id="313d5-107">プライマリの System Center Operations Manager 管理サーバーを構成して、[中央探索の候補」ノードを上書きします。</span><span class="sxs-lookup"><span data-stu-id="313d5-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>

<span data-ttu-id="313d5-108">各タスクを実行する手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="313d5-108">Instructions for carrying out each of these tasks are provided below.</span></span>

<span data-ttu-id="313d5-109">**中央検出ロジックを管理するために選択したサーバーに Lync Server 2010 の更新プログラムを適用します。**</span><span class="sxs-lookup"><span data-stu-id="313d5-109">**Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.**</span></span>

1.  <span data-ttu-id="313d5-110">System Center Operations Manager エージェント ファイルがインストールされ、候補検出ノードとして構成されているサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="313d5-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span>

2.  <span data-ttu-id="313d5-111">このサーバーに Lync Server 2010 の更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="313d5-111">Apply Lync Server 2010 updates to this server.</span></span> <span data-ttu-id="313d5-112">「 [Lync Server 2010 の更新プログラムの適用](apply-lync-server-2010-updates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="313d5-112">See the topic [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).</span></span>

<span data-ttu-id="313d5-113">**中央検出候補サーバーのレジストリ キーを更新する。**</span><span class="sxs-lookup"><span data-stu-id="313d5-113">**Update the central discovery candidate server registry key.**</span></span>

1.  <span data-ttu-id="313d5-114">中央検出ロジックを管理することを選択したサーバーで、Windows PowerShell コマンドウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="313d5-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span>

2.  <span data-ttu-id="313d5-115">コマンド ラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="313d5-115">At the command line, type the following:</span></span>
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="313d5-p102">レジストリを編集すると、"レジストリ キーが既に存在する場合はコマンドが失敗する" というエラーが発生することがあります。このエラーは無視しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="313d5-p102">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error.</span></span>

    
    </div>

<span data-ttu-id="313d5-118">**プライマリの System Center Operations Manager 管理サーバーを構成して、[中央探索の候補監視ノードの候補を上書きします。**</span><span class="sxs-lookup"><span data-stu-id="313d5-118">**Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.**</span></span>

1.  <span data-ttu-id="313d5-119">System Center Operations Manager コントロールがインストールされているコンピューターで、[**管理パック オブジェクト**] を展開し、[**オブジェクト検出**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="313d5-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>

2.  <span data-ttu-id="313d5-120">[**スコープの変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="313d5-120">Click **Change Scope...**</span></span>

3.  <span data-ttu-id="313d5-121">[**管理パック オブジェクトのスコープ設定**] ページで、[**LS Discovery Candidate**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="313d5-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>

4.  <span data-ttu-id="313d5-122">前の手順で選択した候補サーバーの名前の [**LS Discovery Candidate Effective Value**] を上書きします。</span><span class="sxs-lookup"><span data-stu-id="313d5-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span>

<span data-ttu-id="313d5-123">最後に、変更を確定するには、System Center Operations Manager のルート管理サーバーで状態サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="313d5-123">Lastly, to finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

