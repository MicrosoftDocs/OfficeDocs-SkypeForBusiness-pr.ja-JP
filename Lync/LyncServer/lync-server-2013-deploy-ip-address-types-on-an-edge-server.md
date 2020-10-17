---
title: 'Lync Server 2013: エッジサーバーに IP アドレスタイプを展開する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on an Edge Server
ms:assetid: 6e2fe7e8-6e90-4d1a-8fc5-e3be92c46571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204984(v=OCS.15)
ms:contentKeyID: 48184435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 210819547a78905865ebe2dca09d03ab597f33af
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531424"
---
# <a name="deploy-ip-address-types-on-an-edge-server-for-lync-server-2013"></a><span data-ttu-id="db2e6-102">Lync Server 2013 のエッジサーバーに IP アドレスタイプを展開する</span><span class="sxs-lookup"><span data-stu-id="db2e6-102">Deploy IP address types on an Edge Server for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db2e6-103">_**トピックの最終更新日:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="db2e6-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="db2e6-104">トポロジビルダーを使用して、次の手順を実行して、エッジサーバーに IP アドレスの種類を展開します。</span><span class="sxs-lookup"><span data-stu-id="db2e6-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on an Edge Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="db2e6-105">エッジ サーバー上に IP アドレスの種類を展開するには</span><span class="sxs-lookup"><span data-stu-id="db2e6-105">To deploy IP address types on an Edge Server</span></span>

1.  <span data-ttu-id="db2e6-106">[トポロジビルダー] の [ **エッジプール**] で、プール内のサーバーを右クリックし、[ **プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="db2e6-106">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="db2e6-107">または、サーバーを選択し、[**アクション**] メニューの [**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db2e6-107">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2.  <span data-ttu-id="db2e6-p102">[**プロパティの編集**] ウィンドウで、サポートする IP アドレス構成を選択します。次の図に、内部インターフェイスおよび外部インターフェイスのデュアル スタック構成を示します。</span><span class="sxs-lookup"><span data-stu-id="db2e6-p102">In the **Edit Properties** window, select the IP address configuration that you want to support. The following figures show a dual stack configuration for the internal interface and the external interface.</span></span>
    
    <span data-ttu-id="db2e6-110">**デュアル スタック エッジ サーバー内部インターフェイス**</span><span class="sxs-lookup"><span data-stu-id="db2e6-110">**Dual stacked Edge Server internal interface**</span></span>
    
    <span data-ttu-id="db2e6-111">![Lync Server の [全般プロパティ] ページ](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Lync Server の [全般プロパティ] ページ")</span><span class="sxs-lookup"><span data-stu-id="db2e6-111">![Lync Server general properties page](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Lync Server general properties page")</span></span>
    
    <span data-ttu-id="db2e6-112">**デュアル スタック エッジ サーバー外部インターフェイス**</span><span class="sxs-lookup"><span data-stu-id="db2e6-112">**Dual stacked Edge Server external interface**</span></span>
    
    <span data-ttu-id="db2e6-113">![Lync Server の次ホップ/外部構成ページ](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server の次ホップ/外部構成ページ")</span><span class="sxs-lookup"><span data-stu-id="db2e6-113">![Lync Server next hop/external configuration page](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server next hop/external configuration page")</span></span>

3.  <span data-ttu-id="db2e6-114">選択したアドレスの種類のそれぞれで、適切な内部アドレスと外部アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db2e6-114">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

