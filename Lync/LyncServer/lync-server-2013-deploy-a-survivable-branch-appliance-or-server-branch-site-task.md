---
title: 存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの展開 - ブランチ サイトのタスク
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy a Survivable Branch Appliance or Server - branch site task
ms:assetid: 7989ba29-0419-46dd-892c-4ad3238afd56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398599(v=OCS.15)
ms:contentKeyID: 48184586
ms.date: 10/29/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2edf70ccbc4817942775d953b7d43313d96e25c7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-a-survivable-branch-appliance-or-server-with-lync-server-2013---branch-site-task"></a><span data-ttu-id="b41b7-102">Lync Server 2013 での存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの展開 - ブランチ サイトのタスク</span><span class="sxs-lookup"><span data-stu-id="b41b7-102">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b41b7-103">_**最終更新日:** 2014-10-28_</span><span class="sxs-lookup"><span data-stu-id="b41b7-103">_**Topic Last Modified:** 2014-10-28_</span></span>

<span data-ttu-id="b41b7-104">[Survivable Branch Appliance または server を Lync Server 2013-セントラルサイトタスクと共に展開する際](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)に、このトピックで説明する2つの手順のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="b41b7-104">Perform one of the two procedures described in this topic at the branch site, after successfully completing the tasks in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md).</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="b41b7-105">この手順を実行するには、RTCUniversalSBATechnicians グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b41b7-105">To perform this procedure, you must be a member of the RTCUniversalSBATechnicians group.</span></span>



</div>

<div>

## <a name="to-deploy-the-survivable-branch-appliance"></a><span data-ttu-id="b41b7-106">Survivable Branch アプライアンスを展開するには</span><span class="sxs-lookup"><span data-stu-id="b41b7-106">To deploy the Survivable Branch Appliance</span></span>

  - <span data-ttu-id="b41b7-107">Survivable Branch Appliance の展開は、web ユーザーインターフェイス (UI) を介して Survivable Branch Appliance ベンダーによって有効にされています。</span><span class="sxs-lookup"><span data-stu-id="b41b7-107">Survivable Branch Appliance deployment is enabled by the Survivable Branch Appliance vendor through a web user interface (UI).</span></span> <span data-ttu-id="b41b7-108">Survivable Branch アプライアンスの展開については、Survivable Branch Appliance のベンダーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b41b7-108">For information about deploying the Survivable Branch Appliance, see your Survivable Branch Appliance vendor documentation.</span></span>

</div>

<div>

## <a name="to-deploy-the-survivable-branch-server"></a><span data-ttu-id="b41b7-109">Survivable Branch Server を展開するには</span><span class="sxs-lookup"><span data-stu-id="b41b7-109">To deploy the Survivable Branch Server</span></span>

  - <span data-ttu-id="b41b7-110">他の Lync Server 2013 サーバーの役割をインストールする場合と同様に、Windows Server 2008 R2、Windows Server 2012、または Windows Server 2012 R2 を実行しているコンピューターに Lync Server 2013 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b41b7-110">Install Lync Server 2013 on a computer running Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2, just as you would install any other Lync Server 2013 server role.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b41b7-111">Lync Server のインストールの詳細については、「展開ドキュメントに<A href="lync-server-2013-deploying-lync-server.md">Lync server 2013 を展開</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b41b7-111">For information about installing Lync Server, see <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="b41b7-112">**次のステップ**: [Lync Server 2013 でブランチサイトの回復用ユーザーを構成する](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="b41b7-112">**Next step**: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b41b7-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="b41b7-113">See Also</span></span>


[<span data-ttu-id="b41b7-114">付録 A: Lync Server 2013 でのコマンドレットを使用した存続可能ブランチ アプライアンスの展開</span><span class="sxs-lookup"><span data-stu-id="b41b7-114">Appendix A: Using cmdlets to deploy a Survivable Branch Appliance in Lync Server 2013</span></span>](lync-server-2013-appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

