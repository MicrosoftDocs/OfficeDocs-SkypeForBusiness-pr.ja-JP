---
title: Lync Server コンピューターをシステムセンターの検出に参加するように構成する
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
ms.openlocfilehash: 5f5c313bab7c307a0dbc1a8e78269a94663d9c67
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="cfd84-102">Lync Server 2013 コンピューターを System Center discovery に参加するように構成する</span><span class="sxs-lookup"><span data-stu-id="cfd84-102">Configuring the Lync Server 2013 computer to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfd84-103">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="cfd84-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="cfd84-104">System Center operations Manager の検出プロセスに新しい Lync Server エージェントが参加するようにするには、System Center Operations Manager コンソールがインストールされている各コンピューターで次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfd84-104">To make sure that your new Lync Server agent participates in discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="cfd84-105">[**管理**] タブで、[**管理対象のエージェント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfd84-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="cfd84-p101">コンピューターの名前を右クリックし、[**プロパティ**] をクリックします。[**プロパティ**] ダイアログ ボックスの [**セキュリティ**] タブで、[**このエージェントをプロキシとして動作させ、他のコンピューター上の管理オブジェクトを検出する**] を選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfd84-p101">Right-click the name of the computer, and then click **Properties**. In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="cfd84-p102">手順 2. が完了したら、正常性エージェント サービスを再起動します (サービスを再起動すると、強制的に新しいコンピューターの検出が実行されます。サービスを再起動しないと、System Center Operations Manager によって新しいコンピューターが検出されるまでに 4 時間かかる場合があります)。サービスを再起動した後、そのコンピューター上の Operations Manager のイベント ログに、エラー イベントが記録されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="cfd84-p102">After completing step 2, reboot the Health Agent service. (Rebooting the service will “force” discovery of the new machine. If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.). After the service has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

