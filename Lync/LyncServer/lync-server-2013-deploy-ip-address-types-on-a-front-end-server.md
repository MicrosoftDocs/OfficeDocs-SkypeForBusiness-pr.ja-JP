---
title: 'Lync Server 2013: IP アドレスの種類をフロントエンドサーバーに展開する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Front End Server
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205191(v=OCS.15)
ms:contentKeyID: 48185193
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3be24a05cf75adfc999205bb306010ba43fa1d6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-front-end-server-for-lync-server-2013"></a><span data-ttu-id="35221-102">Lync Server 2013 のフロントエンドサーバーに IP アドレスタイプを展開する</span><span class="sxs-lookup"><span data-stu-id="35221-102">Deploy IP address types on a Front End Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35221-103">_**トピックの最終更新日:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="35221-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="35221-104">トポロジビルダーを使用して、次の手順を実行して、IP アドレスの種類をフロントエンドサーバーに展開します。</span><span class="sxs-lookup"><span data-stu-id="35221-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="35221-105">IP アドレス タイプをフロントエンド サーバーに展開するには</span><span class="sxs-lookup"><span data-stu-id="35221-105">To deploy IP address types on a Front End Server</span></span>

1.  <span data-ttu-id="35221-p101">[**Enterprise Edition フロントエンドのプール**] で、プール内のサーバーを右クリックし、[**プロパティの編集**] を選択します (または、サーバーを選択し、[**アクション**] メニューの [**プロパティの編集**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="35221-p101">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2.  <span data-ttu-id="35221-p102">[**プロパティの編集**] ダイアログ ボックスで、構成する IP アドレス タイプを選択します。デュアル スタック構成の場合は、次の図のように、[**IPv4 を有効にする**] および [**IPv6 を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="35221-p102">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="35221-110">**フロントエンド サーバー プールの [プロパティの編集] ダイアログ ボックス**</span><span class="sxs-lookup"><span data-stu-id="35221-110">**Edit Properties dialog box for the Front End Server pool**</span></span>
    
    <span data-ttu-id="35221-111">![フロントエンドサーバーの [プロパティの編集] ダイアログボックス](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "フロントエンドサーバーの [プロパティの編集] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="35221-111">![Front End Server Edit Properties dialog box](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Front End Server Edit Properties dialog box")</span></span>
    
      - <span data-ttu-id="35221-p103">[**すべての構成済み IP アドレスを使用する**]。コンピューター上で定義されているすべての IP アドレスの使用を許可する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="35221-p103">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="35221-114">これは、IP version 6 (IPv6) 構成の推奨オプションです。</span><span class="sxs-lookup"><span data-stu-id="35221-114">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

        
        </div>
    
      - <span data-ttu-id="35221-p104">[**サービスの使用を選択した IP アドレスに限定する**]。新しいサーバーで使用するアドレスを指定するには、このオプションを選択します。このオプションを選択した場合は、[**プライマリ IP アドレス**] に値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35221-p104">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>
    
      - <span data-ttu-id="35221-p105">[**プライマリ IP アドレス**]。公衆交換電話網 (PSTN) 以外のすべての通信でサーバーが使用する IP アドレスを入力します。入力する IP アドレスは、選択されているアドレス タイプの形式に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="35221-p105">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
      - <span data-ttu-id="35221-121">[**PSTN IP アドレス**]。</span><span class="sxs-lookup"><span data-stu-id="35221-121">**PSTN IP address**.</span></span> <span data-ttu-id="35221-122">Lync Server 2013 の PSTN IP アドレス構成をサポートするための追加のネットワークインターフェイスカード (NIC) のインストールは、併置された仲介サーバーの役割ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="35221-122">The installation of additional network interface cards (NIC)s to support the PSTN IP address configuration for Lync Server 2013 is not supported on collocated Mediation Server roles.</span></span> <span data-ttu-id="35221-123">Lync Server 2013 でサポートされている NIC 構成の詳細については、「 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35221-123">For more information about supported NIC configurations for Lync Server 2013, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

