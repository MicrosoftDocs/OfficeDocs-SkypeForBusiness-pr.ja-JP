---
title: 存続可能ブランチアプライアンスまたはサーバー-ブランチサイトタスクを展開する
description: 存続可能ブランチアプライアンスまたはサーバー-ブランチサイトタスクを展開します。
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
ms.openlocfilehash: 6b84f603f185bd507111d4767a22e9009fc0e8b3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545303"
---
# <a name="deploy-a-survivable-branch-appliance-or-server-with-lync-server-2013---branch-site-task"></a><span data-ttu-id="c78bd-103">Lync Server 2013-ブランチサイトタスクを使用して存続可能ブランチアプライアンスまたはサーバーを展開する</span><span class="sxs-lookup"><span data-stu-id="c78bd-103">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c78bd-104">_**トピックの最終更新日:** 2014-10-28_</span><span class="sxs-lookup"><span data-stu-id="c78bd-104">_**Topic Last Modified:** 2014-10-28_</span></span>

<span data-ttu-id="c78bd-105">このトピックで説明する2つの手順のうちの1つは、「 [Lync Server 2013-中央サイトのタスクを使用した存続可能ブランチアプライアンスまたはサーバーの展開](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)」のタスクを正常に完了した後に、ブランチサイトで実行します。</span><span class="sxs-lookup"><span data-stu-id="c78bd-105">Perform one of the two procedures described in this topic at the branch site, after successfully completing the tasks in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md).</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="c78bd-106">この手順を実行するには、RTCUniversalSBATechnicians グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c78bd-106">To perform this procedure, you must be a member of the RTCUniversalSBATechnicians group.</span></span>



</div>

<div>

## <a name="to-deploy-the-survivable-branch-appliance"></a><span data-ttu-id="c78bd-107">存続可能ブランチ アプライアンスを展開するには</span><span class="sxs-lookup"><span data-stu-id="c78bd-107">To deploy the Survivable Branch Appliance</span></span>

  - <span data-ttu-id="c78bd-108">存続可能 Branch Appliance の展開は、web ユーザーインターフェイス (UI) を介して存続可能 Branch Appliance ベンダーによって有効にされます。</span><span class="sxs-lookup"><span data-stu-id="c78bd-108">Survivable Branch Appliance deployment is enabled by the Survivable Branch Appliance vendor through a web user interface (UI).</span></span> <span data-ttu-id="c78bd-109">存続可能ブランチアプライアンスの展開の詳細については、存続可能 Branch Appliance ベンダーのマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c78bd-109">For information about deploying the Survivable Branch Appliance, see your Survivable Branch Appliance vendor documentation.</span></span>

</div>

<div>

## <a name="to-deploy-the-survivable-branch-server"></a><span data-ttu-id="c78bd-110">存続可能ブランチ サーバーを展開するには</span><span class="sxs-lookup"><span data-stu-id="c78bd-110">To deploy the Survivable Branch Server</span></span>

  - <span data-ttu-id="c78bd-111">他の Lync 2013 Server のサーバーの役割をインストールする場合と同じように、Windows Server 2008 R2、Windows Server 2012、または Windows Server 2012 R2 を実行しているコンピューターに Lync Server 2013 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c78bd-111">Install Lync Server 2013 on a computer running Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2, just as you would install any other Lync Server 2013 server role.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="c78bd-112">Lync Server のインストールの詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-deploying-lync-server.md">展開 Lync server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c78bd-112">For information about installing Lync Server, see <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="c78bd-113">**次のステップ**: [Lync Server 2013 でのブランチサイトの復元のユーザーの構成](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="c78bd-113">**Next step**: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c78bd-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="c78bd-114">See Also</span></span>


[<span data-ttu-id="c78bd-115">付録 A: コマンドレットを使用して Lync Server 2013 で存続可能ブランチアプライアンスを展開する</span><span class="sxs-lookup"><span data-stu-id="c78bd-115">Appendix A: Using cmdlets to deploy a Survivable Branch Appliance in Lync Server 2013</span></span>](lync-server-2013-appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

