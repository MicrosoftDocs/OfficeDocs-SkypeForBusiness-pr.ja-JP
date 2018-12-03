---
title: 仲介サーバーを構成します。
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 143d98cebc151473b790246bc78d75e6e2f4185a
ms.sourcegitcommit: a599bdd5057c4fc38e14b4f14961e1a6bf08ee8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2018
ms.locfileid: "27128170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a><span data-ttu-id="ffb21-102">仲介サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="ffb21-102">Configure Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="ffb21-103">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="ffb21-103"></span></span>

<span data-ttu-id="ffb21-104">_**トピックは最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ffb21-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ffb21-105">この手順では、Lync Server 2013 の仲介サーバーを使用して、レガシ Office 通信サーバー 2007 R2 仲介サーバーではなく、Lync Server 2013 プールを構成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="ffb21-105">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="ffb21-106">正常に発行を有効にするなどを追加するか、サーバーの役割を削除すると、トポロジを無効にする、RTCUniversalServerAdmins グループおよび Domain Admins グループのメンバーであるユーザーとしてに記録される必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffb21-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="ffb21-107">適切な管理者権限およびサーバーの役割を追加するためのアクセス許可を委任することもできます。</span><span class="sxs-lookup"><span data-stu-id="ffb21-107">It is also possible to delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="ffb21-108">詳細については、Standard Edition サーバーまたは Enterprise Edition サーバーの展開に関するドキュメントのアクセス許可の委任の設定を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffb21-108">For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="ffb21-109">その他の構成の変更、RTCUniversalServerAdmins グループのメンバーシップのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="ffb21-109">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ffb21-110">修飾の PSTN ゲートウェイ、IP Pbx には、Lync Server 2013 を使用する SIP トランキング サービスを探すことに最新の情報を参照してくださいマイクロソフト ユニファイド コミュニケーション オープン相互運用性プログラム」に<A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>。</span><span class="sxs-lookup"><span data-stu-id="ffb21-110">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="ffb21-111">仲介サーバーを使用するトポロジのビルダーを構成するのには</span><span class="sxs-lookup"><span data-stu-id="ffb21-111">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="ffb21-112">トポロジ ビルダーでは、既存のトポロジを開きます。</span><span class="sxs-lookup"><span data-stu-id="ffb21-112">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="ffb21-113">左側のウィンドウでは、 **PSTN ゲートウェイ**に移動します。</span><span class="sxs-lookup"><span data-stu-id="ffb21-113">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="ffb21-114">**PSTN ゲートウェイ**を右クリックし、**新規の IP ネットワーク アドレス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffb21-114">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="ffb21-115">次の情報が**新しい IP または PSTN ゲートウェイの定義**] ページを完了します。</span><span class="sxs-lookup"><span data-stu-id="ffb21-115">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="ffb21-116">ゲートウェイの FQDN または IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="ffb21-116">Enter the gateway FQDN or IP address.</span></span> <span data-ttu-id="ffb21-117">ゲートウェイが TLS プロトコルを使用している場合、ゲートウェイの FQDN が必要です。</span><span class="sxs-lookup"><span data-stu-id="ffb21-117">The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="ffb21-118">**IP ネットワーク アドレスのリッスンするポート**の既定値を受け入れるか、変更された場合は、新しいリッスン ポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="ffb21-118">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="ffb21-119">の**Sip トランスポート プロトコル**を設定します。</span><span class="sxs-lookup"><span data-stu-id="ffb21-119">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="ffb21-120">左側のウィンドウでは、**エンタープライズ エディションのフロント エンド プール**または**Standard Edition Server**に移動します。</span><span class="sxs-lookup"><span data-stu-id="ffb21-120">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="ffb21-121">プールを右クリックし、 **[プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffb21-121">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="ffb21-122">**仲介サーバー**] の下には、**リッスンするポート**を設定します。</span><span class="sxs-lookup"><span data-stu-id="ffb21-122">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="ffb21-123">次を選択し、[**追加**] をクリックして新しく作成した PSTN ゲートウェイを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="ffb21-123">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="ffb21-124">**トポロジ ビルダー**では、 **Lync Server**の最上位ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="ffb21-124">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="ffb21-125">**[操作**] メニューから**公開トポロジ**を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffb21-125">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="ffb21-126">**発行ウィザード**を完了すると、ウィザードを終了するのには**完了**ををクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffb21-126">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ffb21-127">次のトピックでは、ボイス ルートは、適切な仲介サーバーを指していることを確認するのには<A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">新しい Lync Server 2013 の仲介サーバーを使用するボイス ルートの変更</A>を完了することが重要です。</span><span class="sxs-lookup"><span data-stu-id="ffb21-127">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



<span data-ttu-id="ffb21-128"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="ffb21-128"></span></span></div>

