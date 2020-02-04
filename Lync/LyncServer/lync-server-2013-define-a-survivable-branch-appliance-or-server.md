---
title: 'Lync Server 2013: 存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの定義'
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
ms.openlocfilehash: df5577ff0211afd005feb8fea4788598a03d536e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="4d03b-102">Lync Server 2013 での存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの定義</span><span class="sxs-lookup"><span data-stu-id="4d03b-102">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d03b-103">_**最終更新日:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="4d03b-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="4d03b-104">トポロジに Survivable Branch アプライアンスまたはサーバーを追加したときに定義していない場合は、セントラルサイトでこの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4d03b-104">Perform this procedure at the central site if you did not define the Survivable Branch Appliance or Server when you added it to your topology.</span></span>

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="4d03b-105">Survivable Branch Appliance または Survivable Branch Server を定義するには</span><span class="sxs-lookup"><span data-stu-id="4d03b-105">To define a Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="4d03b-106">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d03b-106">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="4d03b-107">コンソールツリーで、[セントラルサイト]、[**ブランチサイト**] の順に展開して、Survivable branch Appliance または Survivable branch Server の展開を計画しているブランチサイトの名前を展開します。</span><span class="sxs-lookup"><span data-stu-id="4d03b-107">In the console tree, expand the central site, expand **Branch sites**, and then expand the name of the branch site where you plan to deploy the Survivable Branch Appliance or Survivable Branch Server.</span></span>

3.  <span data-ttu-id="4d03b-108">**Survivable Branch**Appliance を右クリックし、[ **New Survivable branch Appliance**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d03b-108">Right-click **Survivable Branch Appliances**, and then click **New Survivable Branch Appliance**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4d03b-109"><STRONG>Survivable Branch アプライアンス</STRONG>では、Survivable branch Servers と Survivable branch アプライアンスを定義しています。</span><span class="sxs-lookup"><span data-stu-id="4d03b-109"><STRONG>Survivable Branch Appliances</STRONG> is where you define Survivable Branch Servers and Survivable Branch Appliances.</span></span>

    
    </div>

4.  <span data-ttu-id="4d03b-110">[ **Survivable Branch appliance の定義**] ダイアログボックスで、[ **fqdn**] をクリックし、このブランチサイトで展開する Survivable Branch Appliance または Survivable branch Server の完全修飾ドメイン名 (FQDN) を入力して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d03b-110">In the **Define Survivable Branch Appliance** dialog box, click **FQDN**, type the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server you will deploy at this branch site, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4d03b-111">Survivable Branch Appliance を定義する場合、 <STRONG>FQDN</STRONG>で入力する名前は、 <STRONG>servicePrincipalName</STRONG>属性に割り当てた Survivable Branch Appliance FQDN と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d03b-111">If you are defining a Survivable Branch Appliance, the name you enter in <STRONG>FQDN</STRONG> must be the same as the Survivable Branch Appliance FQDN you assigned to the <STRONG>servicePrincipalName</STRONG> attribute.</span></span> <span data-ttu-id="4d03b-112">詳細については、「 <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Lync Server 2013 の Active Directory に Survivable Branch Appliance を追加する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d03b-112">For details, see <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</A>.</span></span>

    
    </div>

5.  <span data-ttu-id="4d03b-113">[**フロントエンドプール**] をクリックし、この Survivable branch server が接続するセントラルサイトのフロントエンドサーバー (ユーザーサービスプール) をクリックして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d03b-113">Click **Front End pool**, click the Front End Server (User Services pool) at the central site that this Survivable Branch Appliance or Survivable Branch Server will connect to, and then click **Next**.</span></span>

6.  <span data-ttu-id="4d03b-114">[ **Edge server**] をクリックし、この Survivable branch Appliance または Survivable branch Server が接続するエッジプールをクリックして、ブランチサイトのリモートユーザーに PSTN 接続を提供してから、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d03b-114">Click **Edge Server**, click the Edge pool that this Survivable Branch Appliance or Survivable Branch Server will connect to provide PSTN connectivity to remote users of the branch site, and then click **Next**.</span></span>

7.  <span data-ttu-id="4d03b-115">[**ゲートウェイの fqdn または Ip アドレス**] をクリックして、着信または発信の PSTN 通話をルーティングするために、Survivable branch Appliance または Survivable ブランチサーバーが関連付けられているゲートウェイピアの FQDN または ip アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="4d03b-115">Click **Gateway FQDN or IP Address**, and then type the FQDN or IP address of the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound or outbound PSTN calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4d03b-116">Survivable Branch Appliance を定義している場合、これは、Survivable Branch アプライアンス内の仲介サーバーが PSTN 接続用に接続するゲートウェイです。</span><span class="sxs-lookup"><span data-stu-id="4d03b-116">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span>

    
    </div>

8.  <span data-ttu-id="4d03b-117">[ **IP/PSTN ゲートウェイのリスニングポート**] をクリックし、既定のポートを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="4d03b-117">Click **Listening Port for IP/PSTN Gateway**, and then accept the default port.</span></span>

9.  <span data-ttu-id="4d03b-118">[ **Sip トランスポートプロトコル**] で、Survivable branch Appliance または Survivable branch Server で使用するトランスポートプロトコルをクリックし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d03b-118">In **Sip Transport Protocol**, click the transport protocol the Survivable Branch Appliance or Survivable Branch Server will use, and then click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4d03b-119">セキュリティ上の理由から、トランスポート層セキュリティ (TLS) を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4d03b-119">For security reasons, we strongly recommend that you use Transport Layer Security (TLS).</span></span> <span data-ttu-id="4d03b-120">Survivable Branch appliance を定義する場合は、Survivable Branch Appliance のベンダーのドキュメントを参照して、Survivable Branch Appliance が TLS プロトコルをサポートしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4d03b-120">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>

    
    </div>

10. <span data-ttu-id="4d03b-121">コンソールツリーで、新しい Survivable ブランチアプライアンスまたはサーバーを右クリックし、[**トポロジ**] をクリックして、[**発行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d03b-121">In the console tree, right-click the new Survivable Branch Appliance or Server, click **Topology**, and then click **Publish**.</span></span>

<span data-ttu-id="4d03b-122">**次のステップ**: [Lync Server 2013-ブランチサイトタスクを使用して Survivable Branch Appliance または server を展開する](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span><span class="sxs-lookup"><span data-stu-id="4d03b-122">**Next step**: [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

