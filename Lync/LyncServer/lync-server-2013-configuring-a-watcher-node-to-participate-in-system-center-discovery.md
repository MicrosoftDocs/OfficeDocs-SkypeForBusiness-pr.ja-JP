---
title: システムセンターの検出に参加する監視ノードの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a90f07b445da792e0bc3b22967e41d8cd8d2fcc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a><span data-ttu-id="fef6c-102">Lync Server 2013 の監視ノードを構成して System Center discovery に参加する</span><span class="sxs-lookup"><span data-stu-id="fef6c-102">Configuring a watcher node in Lync Server 2013 to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fef6c-103">_**トピックの最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="fef6c-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="fef6c-104">System center operations manager の検出プロセスに監視ノードが参加していることを確認するには、System Center Operations Manager コンソールがインストールされているコンピューターで次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fef6c-104">To make sure that your watcher node participates in the discovery process for System Center Operations Manager, you must complete the following procedure on a computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="fef6c-105">[**管理**] タブで、[**管理対象のエージェント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fef6c-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="fef6c-p101">ウォッチャー ノード コンピューターの名前を右クリックし、[**プロパティ**] をクリックします。[**プロパティ**] ダイアログ ボックスの [**セキュリティ**] タブで、[**このエージェントをプロキシとして動作させ、他のコンピューター上の管理オブジェクトを検出する**] をオンにして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fef6c-p101">Right-click the name of the watcher node computer, and then click **Properties**. In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="fef6c-108">ウォッチャー ノードがプロキシとして動作するように構成した後、ウォッチャー ノード コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="fef6c-108">After configuring the watcher node to act as a proxy, reboot the watcher node computer.</span></span> <span data-ttu-id="fef6c-109">コンピューターが再起動したら、そのコンピューターの Operations Manager イベントログにエラーイベントが記録されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="fef6c-109">After the computer has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span> <span data-ttu-id="fef6c-110">コンピューターを15分間実行した後、Operations Manager コンソールを使用して、lync Server コンピューターが**lync**カテゴリの下に一覧表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fef6c-110">After the computer has been running for 15 minutes or so, use the Operations Manager console to verify that your Lync Server computers are listed under the **Lync** category.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

