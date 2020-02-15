---
title: 'Lync Server 2013: SIP/CSTA ゲートウェイの IP アドレスの定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60541799a66365275207ea998fa2d4dd218a7bc3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a><span data-ttu-id="1440d-102">Lync Server 2013 での SIP/CSTA ゲートウェイの IP アドレスの定義</span><span class="sxs-lookup"><span data-stu-id="1440d-102">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1440d-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="1440d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="1440d-104">伝送制御プロトコル (TCP) 接続を使用して、リモート通話コントロール用に展開した SIP/CSTA ゲートウェイに Lync Server が接続する場合は、トポロジビルダーでゲートウェイの IP アドレスを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1440d-104">If Lync Server will connect to the SIP/CSTA gateway that you deployed for remote call control by using a Transmission Control Protocol (TCP) connection, then you must define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="1440d-105">トランスポート層セキュリティ (TLS) 接続をサポートするゲートウェイの場合、このステップは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1440d-105">This step is not necessary for gateways that support Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="1440d-106">TLS 接続をサポートするすべてのゲートウェイについては、この手順を省略して、「 [lync ユーザーのリモート通話コントロールでの Lync Server 2013 の有効化](lync-server-2013-enable-lync-users-for-remote-call-control.md)」の手順に従って、リモート通話コントロールの展開を続行できます。</span><span class="sxs-lookup"><span data-stu-id="1440d-106">For any gateway that supports TLS connections, you can skip this procedure and continue deployment of remote call control by following the steps in [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a><span data-ttu-id="1440d-107">トポロジ ビルダーを使用して SIP/CSTA ゲートウェイの IP アドレスを定義するには</span><span class="sxs-lookup"><span data-stu-id="1440d-107">To define the SIP/CSTA gateway IP address by using Topology Builder</span></span>

1.  <span data-ttu-id="1440d-108">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="1440d-108">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="1440d-109">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1440d-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="1440d-110">既存のトポロジをダウンロードするオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="1440d-110">Choose the option to download an existing topology.</span></span>

4.  <span data-ttu-id="1440d-111">[**信頼されたアプリケーション サーバー**] ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="1440d-111">Expand the **Trusted application servers** node.</span></span>

5.  <span data-ttu-id="1440d-112">「 [Lync Server 2013 のリモート通話コントロールの信頼済みアプリケーションエントリを構成](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)する」の説明に従って、作成した信頼されたアプリケーションプールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1440d-112">Right-click the trusted application pool that you created, as described in [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="1440d-113">[**このプールへの構成データのレプリケーションを有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="1440d-113">Clear the **Enable replication of configuration data to this pool** check box.</span></span>

7.  <span data-ttu-id="1440d-p102">[**サービスの使用を選択した IP アドレスに限定する**] をクリックします。 既定の設定は [**すべての構成済み IP アドレスの使用**] です。</span><span class="sxs-lookup"><span data-stu-id="1440d-p102">Click **Limit service usage to selected IP addresses**. The default setting is **Use all configured IP addresses**.</span></span>

8.  <span data-ttu-id="1440d-116">[**プライマリ IP アドレス**] テキスト ボックスに、SIP/CSTA ゲートウェイの IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1440d-116">In the **Primary IP address** text box, enter the IP address of the SIP/CSTA gateway.</span></span>

9.  <span data-ttu-id="1440d-117">中央管理ストアでトポロジを更新するには、コンソール ツリーの [**Lync Server**] をクリックし、[**操作**] ウィンドウで [**公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1440d-117">To update the topology in the Central Management store, in the console tree, click **Lync Server**, and then, from the **Actions** pane, click **Publish**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1440d-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="1440d-118">See Also</span></span>


[<span data-ttu-id="1440d-119">Lync Server 2013 でリモート通話コントロールの静的ルートを構成する</span><span class="sxs-lookup"><span data-stu-id="1440d-119">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="1440d-120">Lync Server 2013 でのリモート通話コントロールの信頼済みアプリケーションエントリを構成する</span><span class="sxs-lookup"><span data-stu-id="1440d-120">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

