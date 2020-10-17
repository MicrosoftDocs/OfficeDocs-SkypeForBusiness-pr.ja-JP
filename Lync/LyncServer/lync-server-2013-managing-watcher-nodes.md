---
title: 'Lync Server 2013: 監視ノードの管理'
description: 'Lync Server 2013: 監視ノードの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1795b09bbca73d8157cf796ceeaaeafb9cc2ebc5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556613"
---
# <a name="managing-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="7abfd-103">Lync Server 2013 での監視ノードの管理</span><span class="sxs-lookup"><span data-stu-id="7abfd-103">Managing watcher nodes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7abfd-104">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="7abfd-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="7abfd-105">監視ノードで実行される代理トランザクションの変更に加え、管理者は **Set-CsWatcherNodeConfiguration** コマンドレットを使用して、監視ノードを有効化または無効化すること、およびテストの実行時に内部 URL または外部 URL を使用するように監視ノードを構成すること、という 2 つの重要なタスクも実行できます。</span><span class="sxs-lookup"><span data-stu-id="7abfd-105">In addition to modifying the synthetic transactions that are executed on a watcher node, administrators can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal URLs or external URLs when running its tests.</span></span>

<span data-ttu-id="7abfd-106">既定では、監視ノードは、すべての有効な代理トランザクションを定期的に実行するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="7abfd-106">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="7abfd-107">ただし、これらのトランザクションの中断が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="7abfd-107">Sometimes, however, you may need to suspend those transactions.</span></span> <span data-ttu-id="7abfd-108">たとえば、監視ノードを一時的にネットワークから切り離す場合は、代理トランザクションを実行する理由がありません。</span><span class="sxs-lookup"><span data-stu-id="7abfd-108">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="7abfd-109">ネットワーク接続がなければ、これらのトランザクションは必ず失敗します。</span><span class="sxs-lookup"><span data-stu-id="7abfd-109">Without network connectivity, those transactions are guaranteed to fail.</span></span> <span data-ttu-id="7abfd-110">監視ノードを一時的に無効にする場合は、Lync Server 管理シェルから次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7abfd-110">If you want to temporarily disable a watcher node, run a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

<span data-ttu-id="7abfd-p102">このコマンドは、監視ノード atl-watcher- 001.litwareinc.com での代理トランザクションの実行を無効にします。代理トランザクションの実行を再開するには、Enabled プロパティを True ($True) に戻します。</span><span class="sxs-lookup"><span data-stu-id="7abfd-p102">This command will disable the execution of synthetic transactions on the watcher node atl-watcher- 001.litwareinc.com. To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> <span data-ttu-id="7abfd-113">Enabled プロパティを使用して監視ノードをオンまたはオフにできます。</span><span class="sxs-lookup"><span data-stu-id="7abfd-113">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="7abfd-114">監視ノードを完全に削除する場合は、<STRONG>Remove-CsWatcherNodeConfiguration</STRONG> コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7abfd-114">If you want to permanently delete a watcher node, use the <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> cmdlet:</span></span><BR><span data-ttu-id="7abfd-115">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="7abfd-115">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span></span><BR><span data-ttu-id="7abfd-116">このコマンドは、指定されたコンピューターからすべての監視ノード構成設定を削除します。これにより、コンピューターは代理トランザクションを自動的に実行することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="7abfd-116">That command removes all the watcher node configuration settings from the specified computer, which prevents the computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="7abfd-117">ただし、このコマンドを実行しても、System Center エージェントファイルまたは Lync Server 2013 システムファイルはアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="7abfd-117">However, the command does not uninstall the System Center agent files or the Lync Server 2013 system files.</span></span>



</div>

<span data-ttu-id="7abfd-p105">既定では、監視ノードは、テストを実行するときに組織の外部 URL を使用します。ただし、監視ノードは、組織の内部 URL を使用するように構成することもできます。これにより、管理者は、境界ネットワーク内に配置されたユーザーの URL アクセスを検証できます。監視ノードを外部 URL ではなく内部 URL を使用するように構成するには、UseInternalWebUrls プロパティを True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="7abfd-p105">By default, watcher nodes use an organization's external URLs when conducting their tests. However, watcher nodes can also be configured to use the organization's internal URLs. This enables administrators to verify URL access for users located inside the perimeter network. To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebUrls property to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

<span data-ttu-id="7abfd-122">このプロパティを既定値である False ($False) にリセットすると、監視ノードは外部 URL を使用します。</span><span class="sxs-lookup"><span data-stu-id="7abfd-122">If you reset this property to the default value of False ($False), the watcher will then use the external URLs:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

