---
title: 仲介サーバーの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 389c6e5c017594bf386109541a379bd5ae2f7e01
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a><span data-ttu-id="2f396-102">仲介サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="2f396-102">Configure Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f396-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="2f396-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2f396-104">この手順では、従来の Office Communications Server 2007 R2 仲介サーバーではなく、lync server 2013 仲介サーバーを使用するように Lync Server 2013 プールを構成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f396-104">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="2f396-p101">サーバーの役割を追加または削除する際に、トポロジを正常に公開したり、有効または無効にするには、RTCUniversalServerAdmins グループおよび Domain Admins グループのメンバーであるユーザーとしてログインしている必要があります。サーバーの役割を追加するための適切な管理者権限およびアクセス許可を委任することもできます。詳細については、Standard Edition サーバーまたは Enterprise Edition サーバーの「展開」のドキュメントの「セットアップのアクセス許可の委任」を参照してください。他の構成変更の場合は、RTCUniversalServerAdmins グループのメンバーシップのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="2f396-p101">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups. It is also possible to delegate the proper administrator rights and permissions for adding server roles. For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation. For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2f396-109">Lync Server 2013 で動作する、認定 PSTN ゲートウェイ、IP-PBX、および SIP トランキングサービスの検索に関する最新情報については、「Microsoft ユニファイドコミュニケーションオープン<A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>相互運用性プログラム」 () を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f396-109">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="2f396-110">トポロジ ビルダーを使用して仲介サーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="2f396-110">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="2f396-111">トポロジ ビルダーで既存のトポロジを開きます。</span><span class="sxs-lookup"><span data-stu-id="2f396-111">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="2f396-112">左ウィンドウで、[**PSTN ゲートウェイ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="2f396-112">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="2f396-113">[**PSTN ゲートウェイ**] を右クリックし、[**新しい IP/PSTN ゲートウェイ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f396-113">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="2f396-114">[**新しい IP/PSTN ゲートウェイの定義**] ページに、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="2f396-114">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="2f396-p102">ゲートウェイの FQDN または IP アドレスを入力します。ゲートウェイが TLS プロトコルを使用する場合は、ゲートウェイの FQDN が必要です。</span><span class="sxs-lookup"><span data-stu-id="2f396-p102">Enter the gateway FQDN or IP address. The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="2f396-117">[**IP/PSTN ゲートウェイのリッスン ポート**] の既定値をそのまま使用するか、変更されている場合は新しいリッスン ポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="2f396-117">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="2f396-118">[**SIP 転送プロトコル**] を設定します。</span><span class="sxs-lookup"><span data-stu-id="2f396-118">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="2f396-119">左ウィンドウで、[**Enterprise Edition フロント エンド プール**] または [**Standard Edition サーバー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="2f396-119">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="2f396-120">プールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f396-120">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="2f396-121">[**仲介サーバー**] で、[**リッスン ポート**] を設定します。</span><span class="sxs-lookup"><span data-stu-id="2f396-121">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="2f396-122">次に、新しく作成した PSTN ゲートウェイを関連付けます。それには、PSTN ゲートウェイを選択し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f396-122">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="2f396-123">**トポロジ ビルダー**で、最上位ノードの [**Lync Server**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2f396-123">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="2f396-124">[**操作**] メニューの [**トポロジの公開**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f396-124">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="2f396-125">**公開ウィザード**の実行が完了したら、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2f396-125">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2f396-126">次のトピック「<A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">新しい Lync server 2013 仲介サーバーを使用するように音声ルートを変更</A>する」を完了して、音声ルートが正しい仲介サーバーを指していることを確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="2f396-126">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

