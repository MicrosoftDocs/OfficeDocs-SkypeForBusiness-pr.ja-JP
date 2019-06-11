---
title: 'Lync Server 2013: 会議のための場所に基づくルーティングの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 657978ee622713ffd830d4aeb92a05d949287568
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="7dd21-102">Lync Server 2013 での会議のための場所に基づくルーティングの構成</span><span class="sxs-lookup"><span data-stu-id="7dd21-102">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7dd21-103">_**最終更新日:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="7dd21-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="7dd21-104">場所に基づくルーティング会議アプリケーションは、Lync Server 2013 の場所に基づくルーティングの構成に依存します。</span><span class="sxs-lookup"><span data-stu-id="7dd21-104">The Location-Based Routing Conferencing application relies on the configuration of Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="7dd21-105">主な構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7dd21-105">The main configurations are the following:</span></span>

  - <span data-ttu-id="7dd21-106">会議の参加者の場所は、ネットワーク サイトに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="7dd21-106">The location of participants joining a meeting is determined based on their network site.</span></span> <span data-ttu-id="7dd21-107">場所に基づくルーティングを適用するには、ネットワークサイトと関連付けられたネットワークサブネットが Lync Server で定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dd21-107">A network site and its associated network subnets must be defined in Lync Server in order to enforce Location-Based Routing.</span></span>

  - <span data-ttu-id="7dd21-108">会議の位置情報に基づくルーティングを適用するには、場所に基づくルーティングで Lync の出席者を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dd21-108">To enforce Location-Based Routing of meetings, Lync participants must be enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="7dd21-109">会議に参加する PSTN エンドポイントの位置に基づくルーティングを適用するには、PSTN エンドポイントを接続するために使用される SIP トランクが位置情報に基づくルーティング用に構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dd21-109">To enforce Location-Based Routing of PSTN endpoints joining meetings, the SIP trunk used to connect the PSTN endpoints must be configured for Location-Based Routing.</span></span>

<span data-ttu-id="7dd21-110">Lync Server 2013 の位置情報に基づくルーティングの展開と構成の詳細については、「[場所ベースのルーティング](lync-server-2013-configuring-location-based-routing.md)を構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dd21-110">For additional information on deploying and configuring Lync Server 2013 Location-Based Routing, please refer Configuring [Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a><span data-ttu-id="7dd21-111">位置に基づくルーティング会議アプリケーションを有効にする</span><span class="sxs-lookup"><span data-stu-id="7dd21-111">Enabling the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="7dd21-112">場所に基づくルーティング会議アプリケーションは、既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="7dd21-112">The Location-Based Routing Conferencing application is disabled by default.</span></span> <span data-ttu-id="7dd21-113">このアプリケーションを有効にする前に、このアプリケーションに割り当てるのに適した優先順位を決める必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dd21-113">Before enabling this application, you need to determine the right priority to assign for the application.</span></span> <span data-ttu-id="7dd21-114">この優先度を決定するには、Lync Server 管理シェルで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7dd21-114">To determine this priority, run the following cmdlet in Lync Server Management Shell:</span></span>

<span data-ttu-id="7dd21-115">CsServerApplication-Identity Service: レジストラー:\<Pool FQDN\></span><span class="sxs-lookup"><span data-stu-id="7dd21-115">Get-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\></span></span>

<span data-ttu-id="7dd21-116">このコマンドレットで\<は、\>位置情報に基づくルーティング会議アプリケーションを有効にするプールをプールの FQDN として指定します。</span><span class="sxs-lookup"><span data-stu-id="7dd21-116">In this cmdlet, \<Pool FQDN\> is the pool in which the Location-Based Routing Conferencing application is to be enabled.</span></span>

<span data-ttu-id="7dd21-117">このコマンドレットは、Lync Server によってホストされているアプリケーションの一覧とそれぞれの priority の値を返します。</span><span class="sxs-lookup"><span data-stu-id="7dd21-117">This cmdlet will return the list of the applications hosted by Lync Server and the priority value for each of them.</span></span> <span data-ttu-id="7dd21-118">場所に基づくルーティング会議アプリケーションには、"UdcAgent" アプリケーションよりも大きく、"DefaultRouting"、"ExumRouting"、"OutboundRouting" アプリケーションよりも小さい優先度の値を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dd21-118">The Location-Based Routing Conferencing application needs to be assigned a priority value larger than the “UdcAgent” application and smaller than the “DefaultRouting”, “ExumRouting” and “OutboundRouting” applications.</span></span> <span data-ttu-id="7dd21-119">場所に基づくルーティング会議アプリケーションは、"UdcAgent" アプリケーションの優先度値より1ポイント高い優先度の値に割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7dd21-119">We recommend that you assign the Location-Based Routing Conferencing application a priority value that is one point higher than the priority value of the “UdcAgent” application.</span></span>

<span data-ttu-id="7dd21-120">たとえば、"UdcAgent" アプリケーションの優先度値が "2" の場合、"DefaultRouting" アプリケーションには "8" という優先度の値が設定されています。 "ExumRouting" アプリケーションの優先度値は "9" で、"OutboundRouting" アプリケーションには "10" という優先順位値があります。場所に基づくルーティング会議アプリケーションには、"3" の優先度の値を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dd21-120">For example, if the “UdcAgent” application has a priority value of “2”, the “DefaultRouting” application has a priority value of “8”, the “ExumRouting” application has a priority value of “9” and the “OutboundRouting” application has a priority value of “10” then you should assign the Location-Based Routing Conferencing application a priority value of “3”.</span></span> <span data-ttu-id="7dd21-121">その場合、アプリケーションの優先度は、その他のアプリケーション (優先度: 0 から 1)、"UdcAgent" (優先度: 2)、場所に基づくルーティング会議アプリケーション (優先度: 3)、その他のアプリケーション (優先度: 4 ~ 8)、"DefaultRouting "(優先度: 9)、" ExumRouting "(優先度:10) と" OutboundRouting "(Priority:11)。</span><span class="sxs-lookup"><span data-stu-id="7dd21-121">Doing so would place the priority of the applications in the following order: Other applications (Priorities: 0 to 1), “UdcAgent” (Priority: 2), Location-Based Routing Conferencing application (Priority: 3), other applications (Priorities: 4 to 8), “DefaultRouting” (Priority: 9), “ExumRouting” (Priority: 10) and “OutboundRouting” (Priority: 11).</span></span>

<span data-ttu-id="7dd21-122">場所に基づくルーティング会議アプリケーションの適切な優先度の値を見つけたら、次のコマンドレットを使用して、位置情報に基づくルーティングが有効になっている各フロントエンドプールまたは標準エディションのサーバーに対して、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="7dd21-122">After you find the correct priority value for the Location-Based Routing Conferencing application, type the following cmdlet for each Front-End pool or Standard Edition Server that homes users enabled for Location-Based Routing:</span></span>

<span data-ttu-id="7dd21-123">新しい-CsServerApplication-Identity Service: レジストラー:\<Pool FQDN\>/LBRouting-priority \<アプリケーション優先\> $true-重要な $true Urihttp://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="7dd21-123">New-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\>/LBRouting -Priority \<Application Priority\> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="7dd21-124">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7dd21-124">For example:</span></span>

<span data-ttu-id="7dd21-125">新規の CsServerApplication-Identity Service: レジストラー: Ls2013cu2lbrLBRouting-Priority 3 $true--------------------------------------$truehttp://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="7dd21-125">New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="7dd21-126">このコマンドレットを使用した後、プールまたは場所ベースのルーティング会議アプリケーションが有効になっている Standard Edition サーバーで、すべてのフロントエンドサーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="7dd21-126">After using this cmdlet, restart all Front End servers in the pool or the Standard Edition Servers where the Location-Based Routing Conferencing application has been enabled.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7dd21-127">会議への位置情報に基づくルーティング enforcements は、対象のプールまたは Standard Edition サーバーのすべてのフロントエンドサーバーが再起動されるまでは適用されません。</span><span class="sxs-lookup"><span data-stu-id="7dd21-127">Location-Based Routing enforcements to conferences or consultative transfers won’t be enforced until all the Front End Servers in the applicable pools or the Standard Edition Servers are restarted.</span></span>



</div>

<span data-ttu-id="7dd21-128">位置情報に基づくルーティング会議アプリケーションが正常に有効になり、適用可能なすべての Lync サーバーが再起動されると、PSTN の通話を許可しないように、場所ベースのルーティングが有効になっている Lync ユーザーが開催するすべての会議が監視されます</span><span class="sxs-lookup"><span data-stu-id="7dd21-128">Once the Location-Based Routing Conferencing application has been successfully enabled and all applicable Lync servers have been restarted, all conferences organized by Lync users enabled for Location-Based Routing will be monitored to prevent PSTN toll bypass</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

