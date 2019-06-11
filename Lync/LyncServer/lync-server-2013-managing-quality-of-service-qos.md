---
title: 'Lync Server 2013: サービスの品質 (QoS) の管理'
ms.reviewer: ''
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
ms.openlocfilehash: 96f25d35f0d96c9e1681c6b4d2c2c3b3079aad34
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a><span data-ttu-id="05ad2-102">Lync Server 2013 での QoS (Quality of Service) の管理</span><span class="sxs-lookup"><span data-stu-id="05ad2-102">Managing Quality of Service (QoS) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05ad2-103">_**最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="05ad2-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="05ad2-104">QoS (Quality of Service) は、音声とビデオの通信に最適なエンドユーザーエクスペリエンスを提供するために、組織内で使用されるネットワークテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="05ad2-104">Quality of Service (QoS) is a networking technology used in some organizations to help provide an optimal end-user experience for audio and video communications.</span></span> <span data-ttu-id="05ad2-105">QoS は、帯域幅が制限されているネットワークで一般的に使用されています。大量のネットワークパケットが、使用可能な帯域幅が比較的少ない場合は、管理者がより高い優先順位をパケットに割り当てる方法を提供します。オーディオデータまたはビデオデータを伝送する。</span><span class="sxs-lookup"><span data-stu-id="05ad2-105">QoS is most-commonly used on networks where bandwidth is limited: with a large number of network packets competing for a relatively small amount of available bandwidth, Quality of Service provides a way for administrators to assign higher priorities to packets carrying audio or video data.</span></span> <span data-ttu-id="05ad2-106">これらのパケットの優先度を高くすることで、音声とビデオによる通信は、ファイル転送、web 閲覧、データベースバックアップなどのネットワークセッションよりもずっと速く、中断される可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="05ad2-106">By giving these packets a higher priority, audio and video communications are likely to complete faster, and with less interruption, than network sessions involving things like file transfers, web browsing, or database backups.</span></span> <span data-ttu-id="05ad2-107">これは、ファイル転送やデータベースバックアップに使用されるネットワークパケットに "最善の努力" の優先度が割り当てられているためです。</span><span class="sxs-lookup"><span data-stu-id="05ad2-107">That's because network packets used for file transfers or database backups are assigned a "best effort" priority.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="05ad2-108">一般的な規則として、サービスの品質は、内部ネットワーク上の通信セッションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="05ad2-108">As a general rule, Quality of Service applies only to communication sessions on your internal network.</span></span> <span data-ttu-id="05ad2-109">QoS を実装するときは、サーバーとルーターがパケットマーキングをサポートするように構成します。ただし、これらのデバイスでは、特定の方法でのパケットマーキングをサポートするように構成します。</span><span class="sxs-lookup"><span data-stu-id="05ad2-109">When you implement QoS, you configure your servers and routers to support packet marking; however, you configure these devices to support packet marking in a particular manner.</span></span> <span data-ttu-id="05ad2-110">サービスの品質は、インターネットやその他のネットワークでサポートされていると想定することはできません。</span><span class="sxs-lookup"><span data-stu-id="05ad2-110">You cannot assume that Quality of Service will be supported on the Internet or on other networks.</span></span> <span data-ttu-id="05ad2-111">サービスが他のネットワークでサポートされている場合でも、ネットワーク上のサービスを構成したときと同じ方法で QoS が構成される保証はありません。</span><span class="sxs-lookup"><span data-stu-id="05ad2-111">Even if Quality if Service is supported on other networks, there is no guarantee that QoS will be configured the same way that you configured the service on your network.</span></span>



</div>

<span data-ttu-id="05ad2-112">Microsoft Lync Server 2013 では、サービスの品質は必要ありません。現在 QoS を使用していない場合は、Lync Server 2013 をインストールする前に、サービスをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="05ad2-112">Microsoft Lync Server 2013 does not require Quality of Service; if you do not currently use QoS there is no requirement that you install the service before installing Lync Server 2013.</span></span> <span data-ttu-id="05ad2-113">ネットワークで大量のパケット損失が発生する場合は、この問題を解決するために推奨される方法は、帯域幅を追加することです。</span><span class="sxs-lookup"><span data-stu-id="05ad2-113">If you experience a considerable amount of packet loss on your network the recommended way to alleviate this problem is to add additional bandwidth.</span></span> <span data-ttu-id="05ad2-114">帯域幅を追加できない場合は、代わりにサービスの品質を実現することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="05ad2-114">If adding more bandwidth is not possible, then you might want to implement Quality of Service instead.</span></span>

<span data-ttu-id="05ad2-115">Lync Server 2013 は、サービスの品質を完全にサポートします。これは、既に QoS を使用している組織では、Lync Server を既存のネットワークインフラストラクチャに簡単に統合できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="05ad2-115">Lync Server 2013 offers full support for Quality of Service: that means that organizations that are already using QoS can easily integrate Lync Server into their existing network infrastructure.</span></span> <span data-ttu-id="05ad2-116">そのためには、次の作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="05ad2-116">In order to do this you must perform the following tasks:</span></span>

  - <span data-ttu-id="05ad2-117">[Windows をベースにしていないデバイスの Lync Server 2013 で QoS を有効に](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md)します。</span><span class="sxs-lookup"><span data-stu-id="05ad2-117">[Enabling QoS in Lync Server 2013 for devices that are not based on Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span></span> <span data-ttu-id="05ad2-118">既定では、その他のオペレーティング システムを実行するコンピューターおよびその他のデバイス (iPhone など) では QoS は無効です。</span><span class="sxs-lookup"><span data-stu-id="05ad2-118">By default, QoS is disabled for computers and other devices (such as iPhones) that run other operating systems.</span></span> <span data-ttu-id="05ad2-119">Lync Server を使用して、デバイスのサービス品質を有効または無効にすることはできますが、通常は製品を使用して、これらのデバイスで使用される DSCP コードを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="05ad2-119">Although you can use Lync Server to enable and disable Quality of Service for devices, you typically cannot use the product to modify the DSCP codes used by these devices.</span></span>

  - <span data-ttu-id="05ad2-120">[Lync Server 2013 での、会議、アプリケーション、および仲介サーバー用のポート範囲の構成](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="05ad2-120">[Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="05ad2-121">オーディオやビデオなどのさまざまな種類のパケットに対して、専用のポートセットを予約する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05ad2-121">You must reserve a unique set of ports for different packet types, such as audio and video.</span></span> <span data-ttu-id="05ad2-122">Lync Server 2013 では、プロパティ値を True または False に設定して、サービスの品質を有効または無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="05ad2-122">With Lync Server 2013 you do not enable or disable Quality of Service by, say, setting a property value to True or to False.</span></span> <span data-ttu-id="05ad2-123">代わりに、ポート範囲を構成し、グループポリシーを作成して適用することで、サービスの品質を有効にします。</span><span class="sxs-lookup"><span data-stu-id="05ad2-123">Instead, you enable Quality of Service by configuring port ranges and then creating and applying Group Policy.</span></span> <span data-ttu-id="05ad2-124">後で QoS を使用しないことにした場合は、適切なグループポリシーオブジェクトを削除することで、"サービスの品質" を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="05ad2-124">If you later decide not to use QoS you can “disable” Quality of Service simply by removing the appropriate Group Policy objects.</span></span>

  - <span data-ttu-id="05ad2-125">[Lync Server 2013 でエッジサーバーのポート範囲を構成](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md)します。</span><span class="sxs-lookup"><span data-stu-id="05ad2-125">[Configuring port ranges for your Edge Servers in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span></span> <span data-ttu-id="05ad2-126">必須ではありませんが、その他のサーバーと同じポート範囲を使用するようにエッジ サーバーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="05ad2-126">Although not required, you can configure your Edge servers to use the same port ranges as your other servers.</span></span>

  - <span data-ttu-id="05ad2-127">[Lync Server 2013 で Microsoft Lync クライアントのポート範囲を構成](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md)します。</span><span class="sxs-lookup"><span data-stu-id="05ad2-127">[Configuring port ranges for your Microsoft Lync clients in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span></span> <span data-ttu-id="05ad2-128">これらのポート範囲はクライアントコンピューターにのみ適用され、通常は、サーバーに構成されているポート範囲とは異なります。</span><span class="sxs-lookup"><span data-stu-id="05ad2-128">These port ranges apply only to client computers and are typically not the same as the port ranges configured on your servers.</span></span>

  - <span data-ttu-id="05ad2-129">[Lync Server 2013 で会議、アプリケーション、および仲介サーバー用のサービス品質ポリシーを構成](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md)します。</span><span class="sxs-lookup"><span data-stu-id="05ad2-129">[Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="05ad2-130">これらのポリシーは、さまざまなパケットの種類に適用される DSCP コードを決定します。</span><span class="sxs-lookup"><span data-stu-id="05ad2-130">These policies determine the DSCP codes that are applied to different packet types.</span></span>

  - <span data-ttu-id="05ad2-131">[Lync Server 2013 で、a/V エッジサーバーのサービス品質ポリシーを構成](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md)します。</span><span class="sxs-lookup"><span data-stu-id="05ad2-131">[Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span></span> <span data-ttu-id="05ad2-132">これは、エッジ サーバーの内側でのみ行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="05ad2-132">This should only be done for the internal side of your Edge servers.</span></span> <span data-ttu-id="05ad2-133">サービスの品質は、インターネット上ではなく、内部ネットワークでの使用を目的として設計されているためです。</span><span class="sxs-lookup"><span data-stu-id="05ad2-133">That's because Quality of Service is designed for use on your internal network and not on the Internet.</span></span>

  - <span data-ttu-id="05ad2-134">[Windows 7 または windows 8 で実行されているクライアントのために、Lync Server 2013 でサービスの品質ポリシーを構成](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md)します。</span><span class="sxs-lookup"><span data-stu-id="05ad2-134">[Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span></span> <span data-ttu-id="05ad2-135">Microsoft Lync Server 2013 は、Windows Vista や Windows XP などの他の Windows オペレーティングシステムでは QoS をサポートしていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="05ad2-135">Note that Microsoft Lync Server 2013 does not support QoS for other Windows operating systems, such as Windows Vista or Windows XP.</span></span>

  - <span data-ttu-id="05ad2-136">[Lync Server 2013 の Microsoft Lync Phone Edition デバイスでのサービス品質の構成](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="05ad2-136">[Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span></span> <span data-ttu-id="05ad2-137">既定では、Lync Phone Edition デバイスでは QoS が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="05ad2-137">By default, QoS is enabled for Lync Phone Edition devices.</span></span> <span data-ttu-id="05ad2-138">ただし、組織内のすべてのオーディオパケットで同じ DSCP コードを使用するために、既定の DSCP 値を変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="05ad2-138">However, you might want to change the default DSCP value in order to ensure that all audio packets in your organization use the same DSCP code.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="05ad2-139">Microsoft Windows Server 2012 または Windows Server 2012 R2 を使用している場合は、そのプラットフォームのサービスの品質を管理するために、新しい Windows PowerShell コマンドレットを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="05ad2-139">If you are using Microsoft Windows Server 2012 or Windows Server 2012 R2 you might be interested in the new set of Windows PowerShell cmdlets available for managing Quality of Service on that platform.</span></span> <span data-ttu-id="05ad2-140">詳細については、「Windows PowerShell でのネットワーク品質の[https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)サービスコマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05ad2-140">For more information, see Network Quality of Service Cmdlets in Windows PowerShell at [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

