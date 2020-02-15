---
title: 'Lync Server 2013: サービスの品質 (QoS) の管理'
ms.reviewer: ''
f1.keywords:
- NOCSH
TOCTitle: Managing Quality of Service (QoS)
author: lanachin
ms.author: v-lanac
ms.manager: serdars
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9b6661bb9e34db11099bc0f1a7526ba23792198
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "41992332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a><span data-ttu-id="69c2c-102">Lync Server 2013 でのサービスの品質 (QoS) の管理</span><span class="sxs-lookup"><span data-stu-id="69c2c-102">Managing Quality of Service (QoS) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69c2c-103">_**トピックの最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="69c2c-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="69c2c-p101">サービスの品質 (QoS) は、一部の組織で使用されているネットワーク テクノロジであり、音声やビデオによる通信で最適なエンドユーザー エクスペリエンスを提供するために役立ちます。QoS は、帯域幅が制限されているネットワークで特によく使用されます。大量のネットワーク パケットが比較的少量の使用可能な帯域幅を取り合うため、サービスの品質によって、管理者が音声またはビデオのデータを伝送するパケットに高い優先順位を割り当てる方法が提供されます。このようなパケットに高い優先順位を付与すると、音声やビデオによる通信は、ファイルの転送、Web 閲覧、またはデータベース バックアップのようなネットワーク セッションよりも迅速かつ少ない中断で完了する可能性が高まります。このため、ファイルの転送またはデータベース バックアップに使用されるネットワーク パケットには "ベスト エフォート型" の優先順位が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="69c2c-p101">Quality of Service (QoS) is a networking technology used in some organizations to help provide an optimal end-user experience for audio and video communications. QoS is most-commonly used on networks where bandwidth is limited: with a large number of network packets competing for a relatively small amount of available bandwidth, Quality of Service provides a way for administrators to assign higher priorities to packets carrying audio or video data. By giving these packets a higher priority, audio and video communications are likely to complete faster, and with less interruption, than network sessions involving things like file transfers, web browsing, or database backups. That's because network packets used for file transfers or database backups are assigned a "best effort" priority.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69c2c-p102">一般に、サービスの品質は、内部ネットワーク上のセッションとの通信にのみ適用されます。QoS を実装する場合は、パケットのマーキングをサポートするようにサーバーおよびルーターを構成します。ただし、これらのデバイスの構成では、特定の方法でパケットのマーキングをサポートするようにします。サービスの品質はインターネットまたはその他のネットワークでサポートされることを前提にしてはいけません。サービスの品質がその他のネットワークでサポートされる場合であっても、ネットワークでサービスを構成した方法と同じ方法で QoS が構成される保証はありません。</span><span class="sxs-lookup"><span data-stu-id="69c2c-p102">As a general rule, Quality of Service applies only to communication sessions on your internal network. When you implement QoS, you configure your servers and routers to support packet marking; however, you configure these devices to support packet marking in a particular manner. You cannot assume that Quality of Service will be supported on the Internet or on other networks. Even if Quality if Service is supported on other networks, there is no guarantee that QoS will be configured the same way that you configured the service on your network.</span></span>



</div>

<span data-ttu-id="69c2c-112">Microsoft Lync Server 2013 は、サービスの品質を必要としません。現在 QoS を使用していない場合は、Lync Server 2013 をインストールする前にサービスをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="69c2c-112">Microsoft Lync Server 2013 does not require Quality of Service; if you do not currently use QoS there is no requirement that you install the service before installing Lync Server 2013.</span></span> <span data-ttu-id="69c2c-113">ネットワークで大量のパケット損失が発生した場合、この問題を緩和するために推奨される方法は、追加の帯域幅を追加することです。</span><span class="sxs-lookup"><span data-stu-id="69c2c-113">If you experience a considerable amount of packet loss on your network the recommended way to alleviate this problem is to add additional bandwidth.</span></span> <span data-ttu-id="69c2c-114">帯域幅を追加できない場合は、代わりにサービスの品質を実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="69c2c-114">If adding more bandwidth is not possible, then you might want to implement Quality of Service instead.</span></span>

<span data-ttu-id="69c2c-115">Lync Server 2013 ではサービスの品質を完全にサポートしています。これは、既に QoS を使用している組織が Lync Server を既存のネットワークインフラストラクチャに統合することを容易にすることを意味します。</span><span class="sxs-lookup"><span data-stu-id="69c2c-115">Lync Server 2013 offers full support for Quality of Service: that means that organizations that are already using QoS can easily integrate Lync Server into their existing network infrastructure.</span></span> <span data-ttu-id="69c2c-116">そのためには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69c2c-116">In order to do this you must perform the following tasks:</span></span>

  - <span data-ttu-id="69c2c-117">[Windows に基づかないデバイスに対して Lync Server 2013 で QoS を有効にする](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md)。</span><span class="sxs-lookup"><span data-stu-id="69c2c-117">[Enabling QoS in Lync Server 2013 for devices that are not based on Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span></span> <span data-ttu-id="69c2c-118">既定では、その他のオペレーティング システムを実行するコンピューターおよびその他のデバイス (iPhone など) では QoS は無効です。</span><span class="sxs-lookup"><span data-stu-id="69c2c-118">By default, QoS is disabled for computers and other devices (such as iPhones) that run other operating systems.</span></span> <span data-ttu-id="69c2c-119">Lync Server を使用してデバイスのサービスの品質を有効または無効にすることはできますが、通常、製品を使用してこれらのデバイスで使用される DSCP コードを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="69c2c-119">Although you can use Lync Server to enable and disable Quality of Service for devices, you typically cannot use the product to modify the DSCP codes used by these devices.</span></span>

  - <span data-ttu-id="69c2c-120">[Lync Server 2013 での会議、アプリケーション、仲介サーバー用のポート範囲の構成](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="69c2c-120">[Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="69c2c-121">音声とビデオなどの異なるパケットの種類に対して独自のポート セットを予約する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69c2c-121">You must reserve a unique set of ports for different packet types, such as audio and video.</span></span> <span data-ttu-id="69c2c-122">Lync Server 2013 を使用すると、サービスの品質を有効または無効にすることはできません。たとえば、プロパティ値を True または False に設定します。</span><span class="sxs-lookup"><span data-stu-id="69c2c-122">With Lync Server 2013 you do not enable or disable Quality of Service by, say, setting a property value to True or to False.</span></span> <span data-ttu-id="69c2c-123">そうではなく、ポート範囲を構成してからグループ ポリシーを作成および適用することによってサービスの品質を有効にします。</span><span class="sxs-lookup"><span data-stu-id="69c2c-123">Instead, you enable Quality of Service by configuring port ranges and then creating and applying Group Policy.</span></span> <span data-ttu-id="69c2c-124">後で QoS を使用しないことにする場合は、単に該当するグループ ポリシー オブジェクトを削除することによってサービスの品質を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="69c2c-124">If you later decide not to use QoS you can “disable” Quality of Service simply by removing the appropriate Group Policy objects.</span></span>

  - <span data-ttu-id="69c2c-125">[Lync Server 2013 でのエッジサーバーのポート範囲の構成](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="69c2c-125">[Configuring port ranges for your Edge Servers in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span></span> <span data-ttu-id="69c2c-126">必須ではありませんが、その他のサーバーと同じポート範囲を使用するようにエッジ サーバーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="69c2c-126">Although not required, you can configure your Edge servers to use the same port ranges as your other servers.</span></span>

  - <span data-ttu-id="69c2c-127">[Lync Server 2013 での Microsoft lync クライアントのポート範囲の構成](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="69c2c-127">[Configuring port ranges for your Microsoft Lync clients in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span></span> <span data-ttu-id="69c2c-128">これらのポート範囲はクライアント コンピューターにのみ適用され、通常、サーバーで構成されたポート範囲とは異なります。</span><span class="sxs-lookup"><span data-stu-id="69c2c-128">These port ranges apply only to client computers and are typically not the same as the port ranges configured on your servers.</span></span>

  - <span data-ttu-id="69c2c-129">[Lync Server 2013 での会議、アプリケーション、仲介サーバー用のサービス品質ポリシーの構成](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="69c2c-129">[Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="69c2c-130">これらのポリシーでは、異なるパケットの種類に適用される DSCP コードを決定します。</span><span class="sxs-lookup"><span data-stu-id="69c2c-130">These policies determine the DSCP codes that are applied to different packet types.</span></span>

  - <span data-ttu-id="69c2c-131">[Lync Server 2013 での音声ビデオエッジサーバーの qos (Quality Of Service) ポリシーの構成](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="69c2c-131">[Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span></span> <span data-ttu-id="69c2c-132">これは、エッジ サーバーの内側でのみ行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="69c2c-132">This should only be done for the internal side of your Edge servers.</span></span> <span data-ttu-id="69c2c-133">サービスの品質はインターネットではなく内部ネットワークで使用するために設計されているためです。</span><span class="sxs-lookup"><span data-stu-id="69c2c-133">That's because Quality of Service is designed for use on your internal network and not on the Internet.</span></span>

  - <span data-ttu-id="69c2c-134">[Windows 7 または windows 8 で実行しているクライアントの Lync Server 2013 でのサービスの品質ポリシーの構成](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md)。</span><span class="sxs-lookup"><span data-stu-id="69c2c-134">[Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span></span> <span data-ttu-id="69c2c-135">Microsoft Lync Server 2013 は、Windows Vista や Windows XP などの他の Windows オペレーティングシステムでは QoS をサポートしていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="69c2c-135">Note that Microsoft Lync Server 2013 does not support QoS for other Windows operating systems, such as Windows Vista or Windows XP.</span></span>

  - <span data-ttu-id="69c2c-136">[Lync Server 2013 の Microsoft Lync Phone Edition デバイスでサービスの品質を構成する](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="69c2c-136">[Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span></span> <span data-ttu-id="69c2c-137">既定では、Lync Phone Edition デバイスでは QoS が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="69c2c-137">By default, QoS is enabled for Lync Phone Edition devices.</span></span> <span data-ttu-id="69c2c-138">ただし、組織内のすべての音声パケットが同じ DSCP コードを使用するようにするために、既定の DSCP 値を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="69c2c-138">However, you might want to change the default DSCP value in order to ensure that all audio packets in your organization use the same DSCP code.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69c2c-139">Microsoft Windows Server 2012 または Windows Server 2012 R2 を使用している場合は、そのプラットフォームでサービスの品質を管理するために使用できる Windows PowerShell コマンドレットの新しいセットに関心があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="69c2c-139">If you are using Microsoft Windows Server 2012 or Windows Server 2012 R2 you might be interested in the new set of Windows PowerShell cmdlets available for managing Quality of Service on that platform.</span></span> <span data-ttu-id="69c2c-140">詳細については、「Windows PowerShell のネットワーク品質サービスの[https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69c2c-140">For more information, see Network Quality of Service Cmdlets in Windows PowerShell at [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

