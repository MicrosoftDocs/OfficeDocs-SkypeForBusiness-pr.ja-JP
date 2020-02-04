---
title: System Center discovery に参加するように Lync Server コンピューターを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cec18903f1621d5a616debbbdd16f3c834ac21c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="0ca66-102">System Center discovery に参加するように Lync Server 2013 コンピューターを構成する</span><span class="sxs-lookup"><span data-stu-id="0ca66-102">Configuring the Lync Server 2013 computer to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ca66-103">_**最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="0ca66-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="0ca66-104">新しい Lync Server エージェントが System Center Operations Manager の検出プロセスに参加するようにするには、System Center Operations Manager コンソールがインストールされている各コンピューターで、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ca66-104">To make sure that your new Lync Server agent participates in discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="0ca66-105">[**管理**] タブで、[**エージェントで管理**します] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ca66-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="0ca66-106">コンピューターの名前を右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ca66-106">Right-click the name of the computer, and then click **Properties**.</span></span> <span data-ttu-id="0ca66-107">[**プロパティ**] ダイアログボックスの [**セキュリティ**] タブで、[**このエージェントがプロキシとして機能することを許可し、他のコンピューター上の管理オブジェクトを検出**します] をクリックし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ca66-107">In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="0ca66-108">手順2を完了したら、正常性エージェントサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="0ca66-108">After completing step 2, reboot the Health Agent service.</span></span> <span data-ttu-id="0ca66-109">(サービスを再起動すると、新しいコンピューターの検出が強制されます。</span><span class="sxs-lookup"><span data-stu-id="0ca66-109">(Rebooting the service will “force” discovery of the new machine.</span></span> <span data-ttu-id="0ca66-110">サービスを再起動しない場合は、新しいコンピューターが System Center Operations Manager によって検出されるまでに4時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="0ca66-110">If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.).</span></span> <span data-ttu-id="0ca66-111">サービスが再起動したら、そのコンピューターの Operations Manager イベントログにエラーイベントが記録されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="0ca66-111">After the service has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

