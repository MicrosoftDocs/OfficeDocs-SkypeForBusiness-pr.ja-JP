---
title: System Center discovery に参加するためのウォッチャーノードの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66be6bd0336471626f2ca4e41a89c3a45b073f05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a><span data-ttu-id="84ba2-102">Lync Server 2013 で監視ノードを構成して System Center discovery に参加する</span><span class="sxs-lookup"><span data-stu-id="84ba2-102">Configuring a watcher node in Lync Server 2013 to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84ba2-103">_**最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="84ba2-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="84ba2-104">Watcher ノードが System Center Operations Manager の検出プロセスに参加していることを確認するには、System Center Operations Manager コンソールがインストールされているコンピューターで、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84ba2-104">To make sure that your watcher node participates in the discovery process for System Center Operations Manager, you must complete the following procedure on a computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="84ba2-105">[**管理**] タブで、[**エージェントで管理**します] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84ba2-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="84ba2-106">ウォッチャーノードのコンピューターの名前を右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84ba2-106">Right-click the name of the watcher node computer, and then click **Properties**.</span></span> <span data-ttu-id="84ba2-107">[**プロパティ**] ダイアログボックスの [**セキュリティ**] タブで、[**このエージェントがプロキシとして機能することを許可し、他のコンピューター上の管理オブジェクトを検出**します] をクリックし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84ba2-107">In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="84ba2-108">プロキシとして動作するようにウォッチャーノードを構成したら、ウォッチャーノードのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="84ba2-108">After configuring the watcher node to act as a proxy, reboot the watcher node computer.</span></span> <span data-ttu-id="84ba2-109">コンピューターが再起動したら、そのコンピューターの Operations Manager イベントログにエラーイベントが記録されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="84ba2-109">After the computer has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span> <span data-ttu-id="84ba2-110">コンピューターが15分以上実行されている場合は、Operations Manager コンソールを使用して、lync Server コンピューターが**lync**カテゴリの下に表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="84ba2-110">After the computer has been running for 15 minutes or so, use the Operations Manager console to verify that your Lync Server computers are listed under the **Lync** category.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

