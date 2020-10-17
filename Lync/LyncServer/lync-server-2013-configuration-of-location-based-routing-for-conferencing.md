---
title: 'Lync Server 2013: 会議用の Location-Based ルーティングの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd5ada5e4af1ed4ed43434ddf4d82abc25f4cd5e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507804"
---
# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="5f79f-102">Lync Server 2013 での会議の Location-Based ルーティングの構成</span><span class="sxs-lookup"><span data-stu-id="5f79f-102">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f79f-103">_**トピックの最終更新日:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="5f79f-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="5f79f-104">Location-Based ルーティング会議アプリケーションは、Lync Server 2013 Location-Based ルーティングの構成に依存します。</span><span class="sxs-lookup"><span data-stu-id="5f79f-104">The Location-Based Routing Conferencing application relies on the configuration of Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="5f79f-105">主な構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5f79f-105">The main configurations are the following:</span></span>

  - <span data-ttu-id="5f79f-106">会議に参加する参加者の場所は、ネットワークサイトに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="5f79f-106">The location of participants joining a meeting is determined based on their network site.</span></span> <span data-ttu-id="5f79f-107">Location-Based ルーティングを適用するには、ネットワークサイトとそれに関連付けられたネットワークサブネットが Lync Server で定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f79f-107">A network site and its associated network subnets must be defined in Lync Server in order to enforce Location-Based Routing.</span></span>

  - <span data-ttu-id="5f79f-108">会議の Location-Based ルーティングを適用するには、Location-Based ルーティングに対して Lync の参加者を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f79f-108">To enforce Location-Based Routing of meetings, Lync participants must be enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="5f79f-109">会議に参加する PSTN エンドポイントの Location-Based ルーティングを適用するには、PSTN エンドポイントへの接続に使用される SIP トランクが Location-Based ルーティング用に構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f79f-109">To enforce Location-Based Routing of PSTN endpoints joining meetings, the SIP trunk used to connect the PSTN endpoints must be configured for Location-Based Routing.</span></span>

<span data-ttu-id="5f79f-110">Lync Server 2013 Location-Based ルーティングの展開および構成の詳細については、「 [場所に基づくルーティング](lync-server-2013-configuring-location-based-routing.md)の構成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f79f-110">For additional information on deploying and configuring Lync Server 2013 Location-Based Routing, please refer Configuring [Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a><span data-ttu-id="5f79f-111">Location-Based ルーティング会議アプリケーションを有効にする</span><span class="sxs-lookup"><span data-stu-id="5f79f-111">Enabling the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="5f79f-112">Location-Based ルーティング会議アプリケーションは、既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="5f79f-112">The Location-Based Routing Conferencing application is disabled by default.</span></span> <span data-ttu-id="5f79f-113">このアプリケーションを有効にする前に、アプリケーションに割り当てる適切な優先順位を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f79f-113">Before enabling this application, you need to determine the right priority to assign for the application.</span></span> <span data-ttu-id="5f79f-114">この優先度を確認するには、Lync Server 管理シェルで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5f79f-114">To determine this priority, run the following cmdlet in Lync Server Management Shell:</span></span>

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

<span data-ttu-id="5f79f-115">このコマンドレットで \<Pool FQDN\> は、Location-Based ルーティング会議アプリケーションを有効にするプールを指定します。</span><span class="sxs-lookup"><span data-stu-id="5f79f-115">In this cmdlet, \<Pool FQDN\> is the pool in which the Location-Based Routing Conferencing application is to be enabled.</span></span>

<span data-ttu-id="5f79f-116">このコマンドレットは、Lync Server でホストされているアプリケーションの一覧とそれぞれの優先度の値を返します。</span><span class="sxs-lookup"><span data-stu-id="5f79f-116">This cmdlet will return the list of the applications hosted by Lync Server and the priority value for each of them.</span></span> <span data-ttu-id="5f79f-117">Location-Based ルーティング会議アプリケーションには、"UdcAgent" アプリケーションよりも大きく、"DefaultRouting"、"ExumRouting"、および "OutboundRouting" アプリケーションよりも小さい優先度の値を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f79f-117">The Location-Based Routing Conferencing application needs to be assigned a priority value larger than the “UdcAgent” application and smaller than the “DefaultRouting”, “ExumRouting” and “OutboundRouting” applications.</span></span> <span data-ttu-id="5f79f-118">Location-Based ルーティング会議アプリケーションには、"UdcAgent" アプリケーションの優先度の値よりも1ポイント大きい優先度の値を割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5f79f-118">We recommend that you assign the Location-Based Routing Conferencing application a priority value that is one point higher than the priority value of the “UdcAgent” application.</span></span>

<span data-ttu-id="5f79f-119">たとえば、"UdcAgent" アプリケーションの優先度の値が "2" の場合は、"DefaultRouting" アプリケーションの優先度値は "8" で、"ExumRouting" アプリケーションの優先度値は "9" で、"OutboundRouting" アプリケーションの優先度は "10" に設定されています。その場合は、Location-Based ルーティング会議アプリケーションに優先度の値 "3" を割り当ててください。</span><span class="sxs-lookup"><span data-stu-id="5f79f-119">For example, if the “UdcAgent” application has a priority value of “2”, the “DefaultRouting” application has a priority value of “8”, the “ExumRouting” application has a priority value of “9” and the “OutboundRouting” application has a priority value of “10” then you should assign the Location-Based Routing Conferencing application a priority value of “3”.</span></span> <span data-ttu-id="5f79f-120">これにより、アプリケーションの優先度は次の順序で設定されます。その他のアプリケーション (優先度: 0 から 1)、"UdcAgent" (優先度: 2)、Location-Based ルーティング会議アプリケーション (優先度: 3)、その他のアプリケーション (優先度: 4 ~ 8)、"DefaultRouting" (優先度:10)、"OutboundRouting" (優先度:11)。</span><span class="sxs-lookup"><span data-stu-id="5f79f-120">Doing so would place the priority of the applications in the following order: Other applications (Priorities: 0 to 1), “UdcAgent” (Priority: 2), Location-Based Routing Conferencing application (Priority: 3), other applications (Priorities: 4 to 8), “DefaultRouting” (Priority: 9), “ExumRouting” (Priority: 10) and “OutboundRouting” (Priority: 11).</span></span>

<span data-ttu-id="5f79f-121">Location-Based ルーティング会議アプリケーションの正しい優先度値を確認した後、Location-Based ルーティングに対してユーザーを有効にした各 Front-End プールまたは Standard Edition サーバーに対して次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="5f79f-121">After you find the correct priority value for the Location-Based Routing Conferencing application, type the following cmdlet for each Front-End pool or Standard Edition Server that homes users enabled for Location-Based Routing:</span></span>

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

<span data-ttu-id="5f79f-122">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5f79f-122">For example:</span></span>

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

<span data-ttu-id="5f79f-123">このコマンドレットを使用した後、プール内のすべてのフロントエンドサーバー、または Location-Based ルーティング会議アプリケーションが有効になっている Standard Edition サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="5f79f-123">After using this cmdlet, restart all Front End servers in the pool or the Standard Edition Servers where the Location-Based Routing Conferencing application has been enabled.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5f79f-124">強制を電話会議またはコンサルティング転送にルーティングする Location-Based は、該当するプールまたは Standard Edition サーバーのすべてのフロントエンドサーバーが再起動されるまで適用されません。</span><span class="sxs-lookup"><span data-stu-id="5f79f-124">Location-Based Routing enforcements to conferences or consultative transfers won’t be enforced until all the Front End Servers in the applicable pools or the Standard Edition Servers are restarted.</span></span>



</div>

<span data-ttu-id="5f79f-125">Location-Based ルーティング会議アプリケーションが正常に有効になり、適用可能なすべての Lync サーバーが再起動されると、Location-Based ルーティングを有効にした Lync ユーザーが開催したすべての会議が監視され、PSTN 有料電話のバイパスが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="5f79f-125">Once the Location-Based Routing Conferencing application has been successfully enabled and all applicable Lync servers have been restarted, all conferences organized by Lync users enabled for Location-Based Routing will be monitored to prevent PSTN toll bypass</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

