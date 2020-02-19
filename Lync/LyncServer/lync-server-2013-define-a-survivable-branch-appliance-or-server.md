---
title: 'Lync Server 2013: 存続可能ブランチアプライアンスまたはサーバーの定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68cb4f7d7d64fdd7291fecbd0b0eea470beed08c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="73d1e-102">Lync Server 2013 での存続可能ブランチアプライアンスまたはサーバーの定義</span><span class="sxs-lookup"><span data-stu-id="73d1e-102">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73d1e-103">_**トピックの最終更新日:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="73d1e-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="73d1e-104">存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーをトポロジに追加した際にこれを定義しなかった場合は、この手順をセントラル サイトで実行します。</span><span class="sxs-lookup"><span data-stu-id="73d1e-104">Perform this procedure at the central site if you did not define the Survivable Branch Appliance or Server when you added it to your topology.</span></span>

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="73d1e-105">存続可能 Branch Appliance または存続可能ブランチサーバーを定義するには</span><span class="sxs-lookup"><span data-stu-id="73d1e-105">To define a Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="73d1e-106">[**スタート**]、[**すべてのプログラム**]、[ **Microsoft lync Server 2013**]、[ **lync server トポロジビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="73d1e-106">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="73d1e-107">コンソールツリーでセントラルサイトを展開し、[**ブランチサイト**] を展開して、存続可能 branch Appliance または存続可能 branch Server の展開を計画しているブランチサイトの名前を展開します。</span><span class="sxs-lookup"><span data-stu-id="73d1e-107">In the console tree, expand the central site, expand **Branch sites**, and then expand the name of the branch site where you plan to deploy the Survivable Branch Appliance or Survivable Branch Server.</span></span>

3.  <span data-ttu-id="73d1e-108">[**存続可能 Branch**Appliance] を右クリックし、[ **New 存続可能 branch Appliance**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="73d1e-108">Right-click **Survivable Branch Appliances**, and then click **New Survivable Branch Appliance**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="73d1e-109"><STRONG>存続可能 Branch アプライアンス</STRONG>では、存続可能ブランチサーバーと存続可能ブランチアプライアンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="73d1e-109"><STRONG>Survivable Branch Appliances</STRONG> is where you define Survivable Branch Servers and Survivable Branch Appliances.</span></span>

    
    </div>

4.  <span data-ttu-id="73d1e-110">[**存続可能ブランチアプライアンスの定義**] ダイアログボックスで、[ **fqdn**] をクリックし、このブランチサイトで展開する存続可能 Branch Appliance または存続可能ブランチサーバーの完全修飾ドメイン名 (fqdn) を入力して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="73d1e-110">In the **Define Survivable Branch Appliance** dialog box, click **FQDN**, type the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server you will deploy at this branch site, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="73d1e-111">存続可能ブランチアプライアンスを定義している場合は、[ <STRONG>FQDN</STRONG> ] に入力する名前は、 <STRONG>servicePrincipalName</STRONG>属性に割り当てた存続可能 Branch Appliance FQDN と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="73d1e-111">If you are defining a Survivable Branch Appliance, the name you enter in <STRONG>FQDN</STRONG> must be the same as the Survivable Branch Appliance FQDN you assigned to the <STRONG>servicePrincipalName</STRONG> attribute.</span></span> <span data-ttu-id="73d1e-112">詳細については、「 <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a 存続可能 Branch Appliance To Active Directory In Lync Server 2013</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73d1e-112">For details, see <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</A>.</span></span>

    
    </div>

5.  <span data-ttu-id="73d1e-113">[**フロントエンドプール**] をクリックし、この存続可能 branch Appliance または存続可能 branch server が接続するセントラルサイトのフロントエンドサーバー (ユーザーサービスプール) をクリックして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="73d1e-113">Click **Front End pool**, click the Front End Server (User Services pool) at the central site that this Survivable Branch Appliance or Survivable Branch Server will connect to, and then click **Next**.</span></span>

6.  <span data-ttu-id="73d1e-114">[**エッジサーバー**] をクリックし、この存続可能 branch Appliance または存続可能ブランチサーバーが接続するエッジプールをクリックして、ブランチサイトのリモートユーザーに PSTN 接続を提供し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="73d1e-114">Click **Edge Server**, click the Edge pool that this Survivable Branch Appliance or Survivable Branch Server will connect to provide PSTN connectivity to remote users of the branch site, and then click **Next**.</span></span>

7.  <span data-ttu-id="73d1e-115">[**ゲートウェイの fqdn または Ip アドレス**] をクリックし、着信または発信の PSTN 通話をルーティングするために、存続可能 branch Appliance または存続可能ブランチサーバーが関連付けられているゲートウェイピアの fqdn または ip アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="73d1e-115">Click **Gateway FQDN or IP Address**, and then type the FQDN or IP address of the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound or outbound PSTN calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="73d1e-116">存続可能ブランチ アプライアンスを定義すると、このアプライアンスは、PSTN 接続で存続可能ブランチ アプライアンス内部の仲介サーバーが接続するゲートウェイとなります。</span><span class="sxs-lookup"><span data-stu-id="73d1e-116">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span>

    
    </div>

8.  <span data-ttu-id="73d1e-117">[**IP/PSTN ゲートウェイのリッスン ポート**] をクリックし、既定のポートに設定します。</span><span class="sxs-lookup"><span data-stu-id="73d1e-117">Click **Listening Port for IP/PSTN Gateway**, and then accept the default port.</span></span>

9.  <span data-ttu-id="73d1e-118">[ **Sip トランスポートプロトコル**] で、存続可能ブランチアプライアンスまたは存続可能ブランチサーバーが使用するトランスポートプロトコルをクリックし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="73d1e-118">In **Sip Transport Protocol**, click the transport protocol the Survivable Branch Appliance or Survivable Branch Server will use, and then click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="73d1e-119">セキュリティ上の理由により、トランスポート層セキュリティ (TLS) を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="73d1e-119">For security reasons, we strongly recommend that you use Transport Layer Security (TLS).</span></span> <span data-ttu-id="73d1e-120">存続可能ブランチ アプライアンスを定義する場合は、存続可能ブランチ アプライアンスのベンダー ドキュメントを参照して、その存続可能ブランチ アプライアンスが TLS プロトコルをサポートすることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="73d1e-120">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>

    
    </div>

10. <span data-ttu-id="73d1e-121">コンソール ツリーで新しい存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーを右クリックし、[**トポロジ**] をクリックしてから [**公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="73d1e-121">In the console tree, right-click the new Survivable Branch Appliance or Server, click **Topology**, and then click **Publish**.</span></span>

<span data-ttu-id="73d1e-122">**次のステップ**: [Lync Server 2013-ブランチサイトタスクを使用した存続可能ブランチアプライアンスまたはサーバーの展開](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span><span class="sxs-lookup"><span data-stu-id="73d1e-122">**Next step**: [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

