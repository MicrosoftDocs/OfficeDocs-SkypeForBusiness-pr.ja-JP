---
title: 仲介サーバーを構成する
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
ms.openlocfilehash: eb9b2c7cf8da1d454f310a8ac999dddbc7d34f68
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a><span data-ttu-id="08e4b-102">仲介サーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="08e4b-102">Configure Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08e4b-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="08e4b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="08e4b-104">この手順では、従来の Office Communications Server 2007 R2 仲介サーバーではなく、lync server 2013 仲介サーバーを使用するように Lync Server 2013 プールを構成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="08e4b-104">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="08e4b-105">トポロジを正常に発行、有効化、または無効にするには、RTCUniversalServerAdmins および Domain Admins グループのメンバーであるユーザーとしてログインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="08e4b-105">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="08e4b-106">また、サーバーの役割を追加するための適切な管理者権限と権限を委任することもできます。</span><span class="sxs-lookup"><span data-stu-id="08e4b-106">It is also possible to delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="08e4b-107">詳細については、「Standard Edition server または Enterprise Edition server 展開ドキュメントの委任セットアップの権限」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08e4b-107">For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="08e4b-108">その他の構成変更については、RTCUniversalServerAdmins グループのメンバーシップのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="08e4b-108">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="08e4b-109">Lync Server 2013 で動作する、限定 PSTN ゲートウェイ、IP Pbx、SIP トランクサービスの検索に関する最新情報については、「Microsoft ユニファイド通信で<A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>の相互運用プログラムのオープン」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08e4b-109">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="08e4b-110">トポロジビルダーを使用して仲介サーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="08e4b-110">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="08e4b-111">トポロジビルダーから既存のトポロジを開きます。</span><span class="sxs-lookup"><span data-stu-id="08e4b-111">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="08e4b-112">左側のウィンドウで、[ **PSTN ゲートウェイ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="08e4b-112">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="08e4b-113">[ **PSTN ゲートウェイ**] を右クリックし、[**新しい IP/PSTN ゲートウェイ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08e4b-113">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="08e4b-114">[**新しい IP/PSTN ゲートウェイの定義**] ページに次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="08e4b-114">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="08e4b-115">ゲートウェイの FQDN または IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="08e4b-115">Enter the gateway FQDN or IP address.</span></span> <span data-ttu-id="08e4b-116">ゲートウェイで TLS プロトコルを使用している場合は、ゲートウェイの FQDN が必要です。</span><span class="sxs-lookup"><span data-stu-id="08e4b-116">The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="08e4b-117">**IP/PSTN ゲートウェイのリスニングポート**の既定値をそのまま使うか、変更された場合は新しいリッスンポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="08e4b-117">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="08e4b-118">**Sip トランスポートプロトコル**を設定します。</span><span class="sxs-lookup"><span data-stu-id="08e4b-118">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="08e4b-119">左側のウィンドウで、 **Enterprise Edition のフロントエンドプール**または**Standard Edition サーバー**に移動します。</span><span class="sxs-lookup"><span data-stu-id="08e4b-119">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="08e4b-120">プールを右クリックし、[プロパティの**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08e4b-120">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="08e4b-121">[**仲介サーバー**] で、**リッスンポート**を設定します。</span><span class="sxs-lookup"><span data-stu-id="08e4b-121">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="08e4b-122">次に、新しく作成した PSTN ゲートウェイを選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08e4b-122">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="08e4b-123">[**トポロジビルダー**] で、トップノードの**Lync Server**を選択します。</span><span class="sxs-lookup"><span data-stu-id="08e4b-123">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="08e4b-124">[**アクション**] メニューで、[**発行トポロジ**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08e4b-124">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="08e4b-125">**発行ウィザード**が完了したら、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="08e4b-125">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="08e4b-126">次のトピック「ボイスルートを変更して、<A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">新しい Lync server 2013 仲介サーバーを使用する</A>」を実行し、ボイスルーティングが正しい仲介サーバーをポイントするようにすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="08e4b-126">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

