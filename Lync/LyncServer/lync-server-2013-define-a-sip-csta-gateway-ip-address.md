---
title: 'Lync Server 2013: SIP/CSTA ゲートウェイの IP アドレスの定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6143b4b92c8927375dcaa772360e0b3f870dae25
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a><span data-ttu-id="de071-102">Lync Server 2013 での SIP/CSTA ゲートウェイの IP アドレスの定義</span><span class="sxs-lookup"><span data-stu-id="de071-102">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de071-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="de071-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="de071-104">Lync Server が伝送制御プロトコル (TCP) 接続を使ってリモート通話コントロール用に展開した SIP/CSTA ゲートウェイに接続する場合は、トポロジビルダーでゲートウェイの IP アドレスを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de071-104">If Lync Server will connect to the SIP/CSTA gateway that you deployed for remote call control by using a Transmission Control Protocol (TCP) connection, then you must define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="de071-105">トランスポート層セキュリティ (TLS) 接続をサポートするゲートウェイの場合、この手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="de071-105">This step is not necessary for gateways that support Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="de071-106">TLS 接続をサポートしているすべてのゲートウェイについては、この手順をスキップして、「lync[ユーザーが Lync Server 2013 のリモート通話制御を有効にする](lync-server-2013-enable-lync-users-for-remote-call-control.md)」の手順に従って、リモート通話コントロールの展開を継続できます。</span><span class="sxs-lookup"><span data-stu-id="de071-106">For any gateway that supports TLS connections, you can skip this procedure and continue deployment of remote call control by following the steps in [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a><span data-ttu-id="de071-107">Topology Builder を使用して SIP/CSTA ゲートウェイの IP アドレスを定義するには</span><span class="sxs-lookup"><span data-stu-id="de071-107">To define the SIP/CSTA gateway IP address by using Topology Builder</span></span>

1.  <span data-ttu-id="de071-108">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="de071-108">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="de071-109">トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="de071-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="de071-110">既存のトポロジをダウンロードするためのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="de071-110">Choose the option to download an existing topology.</span></span>

4.  <span data-ttu-id="de071-111">[信頼されている**アプリケーションサーバー** ] ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="de071-111">Expand the **Trusted application servers** node.</span></span>

5.  <span data-ttu-id="de071-112">「 [Lync Server 2013 のリモート通話コントロールに対して信頼されているアプリケーションエントリを構成](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)する」の説明に従って、作成した信頼できるアプリケーションプールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de071-112">Right-click the trusted application pool that you created, as described in [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="de071-113">[**このプールへの構成データのレプリケーションを有効に**する] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="de071-113">Clear the **Enable replication of configuration data to this pool** check box.</span></span>

7.  <span data-ttu-id="de071-114">[**サービスの利用制限を選択した IP アドレスに制限] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="de071-114">Click **Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="de071-115">既定の設定では、[構成され**た IP アドレスをすべて使用する**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="de071-115">The default setting is **Use all configured IP addresses**.</span></span>

8.  <span data-ttu-id="de071-116">[**プライマリ IP アドレス**] テキストボックスに、SIP/csta ゲートウェイの IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="de071-116">In the **Primary IP address** text box, enter the IP address of the SIP/CSTA gateway.</span></span>

9.  <span data-ttu-id="de071-117">サーバーの全体管理ストアでトポロジを更新するには、コンソールツリーで [ **Lync Server**] をクリックし、[**操作**] ウィンドウで [**発行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de071-117">To update the topology in the Central Management store, in the console tree, click **Lync Server**, and then, from the **Actions** pane, click **Publish**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="de071-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="de071-118">See Also</span></span>


[<span data-ttu-id="de071-119">Lync Server 2013 でのリモート通話コントロールの静的ルートの構成</span><span class="sxs-lookup"><span data-stu-id="de071-119">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="de071-120">Lync Server 2013 でリモート通話コントロールの信頼済みアプリケーション エントリを構成する</span><span class="sxs-lookup"><span data-stu-id="de071-120">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

