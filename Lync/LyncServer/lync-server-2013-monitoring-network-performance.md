---
title: 'Lync Server 2013: ネットワークパフォーマンスの監視'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc6941f612fdf18f081cb52e55e2c7f7201e64b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a><span data-ttu-id="1b201-102">Lync Server 2013 でのネットワークパフォーマンスの監視</span><span class="sxs-lookup"><span data-stu-id="1b201-102">Monitoring network performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b201-103">_**トピックの最終更新日:** 2016-04-27_</span><span class="sxs-lookup"><span data-stu-id="1b201-103">_**Topic Last Modified:** 2016-04-27_</span></span>

<span data-ttu-id="1b201-104">Lync Server 2013 は、ネットワークに大きく依存して、インスタントメッセージング (IM)、音声通話、またはビデオ通信によってユーザー間の通信を可能にするリアルタイム通信テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="1b201-104">Lync Server 2013 is a real-time communications technology that relies heavily on the network to enable communication between users—either through instant messaging (IM), voice calls, or video communication.</span></span> <span data-ttu-id="1b201-105">そのため、ネットワークパフォーマンスを継続的に監視して、ユーザーが選択した通信モダリティが最適な環境を提供することを保証することが重要です。</span><span class="sxs-lookup"><span data-stu-id="1b201-105">It is therefore important to monitor the network performance continuously to help guarantee that a user’s chosen communication modality provides the best possible experience.</span></span>

<span data-ttu-id="1b201-106">ネットワークのパフォーマンスは、次の2つのレベルで測定できます。</span><span class="sxs-lookup"><span data-stu-id="1b201-106">Network performance can be measured at two levels:</span></span>

  - <span data-ttu-id="1b201-107">**ネットワークの全体的なパフォーマンス**   このレベルのパフォーマンス測定を使用すると、組織はネットワークの "大きな画像" 表示を作成し、通常はサードパーティのネットワーク監視システムを使用して実装します。</span><span class="sxs-lookup"><span data-stu-id="1b201-107">**Overall network performance**   This level of performance measurement will allow an organization to create a "big-picture" view of their network and is usually implemented through third-party network monitoring systems.</span></span> <span data-ttu-id="1b201-108">これらのシステムは、パフォーマンスと容量のデータをルーターなどのリモートネットワークデバイスから受け取り、ネットワークを介して切り替えることによって、管理者が任意の時間帯に特定のネットワークコンポーネントの正常性を判断できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1b201-108">These systems will receive performance and capacity data from remote network devices such as routers and switched throughout the network to allow administrators to determine the health of any given network component at any time of day.</span></span>

  - <span data-ttu-id="1b201-109">**個々のサーバーのパフォーマンス**   このレベルのパフォーマンス測定値は特定のサーバーに限定され、特定のパフォーマンスの問題のトラブルシューティングや、容量計画プロセスの一環として、特定の期間における個々のサーバーのパフォーマンスを測定するために、特定のサーバーのネットワークパフォーマンスを gauging する管理者に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1b201-109">**Individual server performance**   This level of performance measurement is limited to a specific server and will help administrators with gauging the network performance of a specific server to either help with troubleshooting a specific performance issue or to gauge the respective server’s performance over a given period as part of a capacity planning process.</span></span>

<span data-ttu-id="1b201-110">次のセクションで説明するツールを使用して、ネットワークを監視できます。</span><span class="sxs-lookup"><span data-stu-id="1b201-110">You can monitor the network by using the tools described in the following sections.</span></span>

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a><span data-ttu-id="1b201-111">ネットワークパフォーマンスの全体的な監視用のツール</span><span class="sxs-lookup"><span data-stu-id="1b201-111">Tools for Overall Network Performance Monitoring</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="1b201-112">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="1b201-112">System Center Operations Manager 2012</span></span>

<span data-ttu-id="1b201-113">System Center Operations Manager は、IT 環境全体のサービスレベルを向上させるために、簡単にカスタマイズおよび拡張できる、エンドツーエンドのサービス管理を提供します。</span><span class="sxs-lookup"><span data-stu-id="1b201-113">System Center Operations Manager provides end-to-end service management that is easy to customize and extend for improved service levels across an IT environment.</span></span> <span data-ttu-id="1b201-114">これにより、運用および IT 管理チームは、分散 IT サービスの正常性に影響する問題を特定して解決することができます。</span><span class="sxs-lookup"><span data-stu-id="1b201-114">This enables Operations and IT Management teams to identify, and resolve issues affecting the health of distributed IT services.</span></span> <span data-ttu-id="1b201-115">エンドツーエンドのサービス管理は、Microsoft ベースの環境に制限されていません。</span><span class="sxs-lookup"><span data-stu-id="1b201-115">End-to-end service management is not restricted to Microsoft-based environments.</span></span> <span data-ttu-id="1b201-116">Web サービス (WS-MANAGEMENT)、簡易ネットワーク管理プロトコル (SNMP)、およびパートナーソリューションのサポートにより、Microsoft オペレーティングシステムとハードウェアを実行していないシステムを、システムセンター内のサービス監視に含めることができます。Operations Manager 2012。</span><span class="sxs-lookup"><span data-stu-id="1b201-116">Support for Web Services for Management (WS-Management), Simple Network Management Protocol (SNMP), and partner solutions allow for systems that do not run Microsoft operating systems and hardware to be included in service monitoring within System Center Operations Manager 2012.</span></span>

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a><span data-ttu-id="1b201-117">System Center Operations Manager 2012 およびサードパーティ製のネットワーク管理ソリューション</span><span class="sxs-lookup"><span data-stu-id="1b201-117">System Center Operations Manager 2012 and Third-Party Network Management Solutions</span></span>

<span data-ttu-id="1b201-118">**Emc Smarts**   Operations Manager 向け emc ソリューションは、サービスレベルに影響する問題を迅速に解決するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1b201-118">**EMC Smarts**   EMC Solutions for Operations Manager help you quickly resolve issues affecting service levels throughout.</span></span> <span data-ttu-id="1b201-119">Operations Manager 用 EMC ソリューションを使用すると、統合された1つの自動ソリューションで IT サービスチェーン全体を管理および監視できます。</span><span class="sxs-lookup"><span data-stu-id="1b201-119">By using EMC Solutions for Operations Manager, you can manage and monitor your whole IT service chain with one integrated, automated solution.</span></span> <span data-ttu-id="1b201-120">パフォーマンスと可用性の問題の根本原因を簡単に特定し、それらを解決することで、影響とコストを軽減できます。</span><span class="sxs-lookup"><span data-stu-id="1b201-120">You'll easily identify the root causes of performance and availability issues, and resolve them faster which reduces effects and costs.</span></span> <span data-ttu-id="1b201-121">主な利点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b201-121">Key benefits include the following:</span></span>

  - <span data-ttu-id="1b201-122">高度で使いやすい管理を使用して、手動での並べ替えやフィルター処理を混同せずに、戦略的なビジネス価値を提供することに重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="1b201-122">Advanced, easy-to-use management   Focus on delivering strategic business value instead of manually sorting and filtering confusing alerts.</span></span>

  - <span data-ttu-id="1b201-123">**より迅速に解決**   することで、IT 上の問題を解決し、ビジネスニーズに迅速に対応して、影響とコストを軽減します。</span><span class="sxs-lookup"><span data-stu-id="1b201-123">**Faster resolution**   Solve IT issues and respond to business needs faster, reducing effect and cost.</span></span>

  - <span data-ttu-id="1b201-124">**合理化**   された操作では、複数の管理ツール、アプリケーション、およびターミナルを組み合わせることによって、IT の複雑さを回避します。</span><span class="sxs-lookup"><span data-stu-id="1b201-124">**Streamlined operations**   Avoid IT complexity by combining multiple management tools, applications, and terminals.</span></span>

<span data-ttu-id="1b201-125">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b201-125">More information can be found here:</span></span>

[<span data-ttu-id="1b201-126">Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="1b201-126">Microsoft System Center Operations Manager</span></span>](https://go.microsoft.com/fwlink/p/?linkid=243651)

[<span data-ttu-id="1b201-127">Microsoft System Center Operations Manager のソリューション</span><span class="sxs-lookup"><span data-stu-id="1b201-127">Solutions for Microsoft System Center Operations Manager</span></span>](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a><span data-ttu-id="1b201-128">サードパーティ製のソリューション</span><span class="sxs-lookup"><span data-stu-id="1b201-128">Third-Party Solutions</span></span>

<span data-ttu-id="1b201-129">Hp ネットワーク管理**センター (旧称 Hp OpenView)**   [Hp ネットワーク管理センター](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__)では、ネットワークの可用性とパフォーマンスを向上するために、統合された障害およびパフォーマンス管理を提供しています。</span><span class="sxs-lookup"><span data-stu-id="1b201-129">**HP Network Management Center (previously known as HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) provides integrated fault and performance management to improve network availability and performance.</span></span> <span data-ttu-id="1b201-130">ネットワーク管理センターは、障害、パフォーマンス、構成、および変更管理を統合する HP 自動ネットワーク管理ソリューションの一部です。</span><span class="sxs-lookup"><span data-stu-id="1b201-130">Network Management Center is part of the HP automated network management solution that unifies fault, performance, configuration, and change management.</span></span>

<span data-ttu-id="1b201-131">**Cisco 社の cisco ネットワーク管理と自動化製品**   には、ciscoworks LAN 管理ソリューションと cisco ネットワーク分析モジュールを含むいくつかの管理製品があります。これにより、運用効率を向上させ、ネットワークのダウンタイムを削減できます。</span><span class="sxs-lookup"><span data-stu-id="1b201-131">**Cisco Network Management and Automation products**   For the Enterprise, Cisco has several management products available including CiscoWorks LAN Management Solution and Cisco Network Analysis Module, to help improve operational efficiency and reduce network downtime.</span></span> <span data-ttu-id="1b201-132">これらの製品の追加データについては、Cisco web [https://www.cisco.com/en/US/products/sw/netmgtsw/index.html](https://www.cisco.com/en/us/products/sw/netmgtsw/index.html)サイト () を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b201-132">For additional data on these products, refer to the Cisco website at [https://www.cisco.com/en/US/products/sw/netmgtsw/index.html](https://www.cisco.com/en/us/products/sw/netmgtsw/index.html).</span></span>

<span data-ttu-id="1b201-133">簡易ネットワーク管理プロトコル (SNMP) 簡易ネットワーク管理プロトコル (SNMP) は、TCP/IP ネットワークを管理する戦略を定義するネットワーク管理の標準です。</span><span class="sxs-lookup"><span data-stu-id="1b201-133">Simple Network Management Protocol (SNMP)   Simple Network Management Protocol (SNMP) is a network management standard that defines a strategy for managing TCP/IP networks.</span></span> <span data-ttu-id="1b201-134">SNMP を使用すると、ネットワークに関する構成および状態に関する情報を取得し、指定されたコンピューターにイベント監視用に情報を送信することができます。</span><span class="sxs-lookup"><span data-stu-id="1b201-134">SNMP enables you to capture configuration and status information about the network, and send the information to a designated computer for event monitoring.</span></span> <span data-ttu-id="1b201-135">この標準ベースのネットワーク管理プロトコルは、次のものを含む分散アーキテクチャを使用します。</span><span class="sxs-lookup"><span data-stu-id="1b201-135">This standards based network management protocol uses a distributed architecture that includes the following:</span></span>

  - <span data-ttu-id="1b201-136">複数の管理ノード。それぞれがエージェントと呼ばれる SNMP エンティティを使用して、管理インストルメンテーションへのリモートアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="1b201-136">Multiple managed nodes, each with an SNMP entity called an agent which provides remote access to management instrumentation.</span></span>

  - <span data-ttu-id="1b201-137">管理要素を監視および制御するために管理アプリケーションを実行する、マネージャーとして知られている少なくとも1つの SNMP エンティティ。</span><span class="sxs-lookup"><span data-stu-id="1b201-137">At least one SNMP entity known as a manager which runs management applications to monitor and control managed elements.</span></span> <span data-ttu-id="1b201-138">管理要素は、ホスト、ルーターなどのデバイスです。</span><span class="sxs-lookup"><span data-stu-id="1b201-138">Managed elements are devices such as hosts, routers, and so on.</span></span> <span data-ttu-id="1b201-139">管理情報にアクセスすることによって監視および制御されます。</span><span class="sxs-lookup"><span data-stu-id="1b201-139">They are monitored and controlled by accessing their management information.</span></span>

  - <span data-ttu-id="1b201-140">管理プロトコル (SNMP) は、管理ステーションとエージェント間で管理情報を通信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1b201-140">A management protocol, SNMP, is used to communicate management information between the management stations and agents.</span></span> <span data-ttu-id="1b201-141">管理情報は、管理情報ベース (MIB) と呼ばれる仮想情報ストア内に存在する管理対象オブジェクトのコレクションを参照します。</span><span class="sxs-lookup"><span data-stu-id="1b201-141">Management information refers to a collection of managed objects that live in a virtual information store called a Management Information Base (MIB).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1b201-142">サードパーティ製のネットワーク監視ソリューションの例については、前述の説明を参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="1b201-142">Examples of third-party network monitoring solutions are provided above.</span></span> <span data-ttu-id="1b201-143">この一覧は明確ではありません。また、Microsoft は特定のベンダーソリューションを優先していません。</span><span class="sxs-lookup"><span data-stu-id="1b201-143">This list is not definitive and Microsoft does not favor any specific vendor solution.</span></span> <span data-ttu-id="1b201-144">ネットワークサービスプロバイダーまたは各テクノロジプロバイダーと相談して、組織に最適なネットワーク監視ソリューションを決定してください。</span><span class="sxs-lookup"><span data-stu-id="1b201-144">Consult with a network service provider and or your respective technology provider to determine the best network monitoring solution for your organization.</span></span>



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a><span data-ttu-id="1b201-145">個々のサーバーネットワークのパフォーマンスを監視するためのツール</span><span class="sxs-lookup"><span data-stu-id="1b201-145">Tools for Monitoring Individual Server Network Performance</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="1b201-146">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="1b201-146">System Center Operations Manager 2012</span></span>

<span data-ttu-id="1b201-147">System Center Operations Manager 2012 では、管理者が Windows Server 2012 管理パックを使用して個々のサーバーのネットワークパフォーマンスを表示することができます。 Windows Server オペレーティングシステム管理パックには、"パフォーマンス" 管理パックが含まれています。これにより、管理者はネットワークアダプターのパフォーマンスとアダプターの正常性を監視できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1b201-147">System Center Operations Manager 2012 would allow administrators to view network performance of individual servers through the Windows Server 2012 Management Pack: The Windows Server operating system management pack includes a "Performance" management pack that would allow administrators to monitor Network Adapter performance and adapter health.</span></span>

</div>

<div>

## <a name="windows-network-monitor"></a><span data-ttu-id="1b201-148">Windows ネットワークモニター</span><span class="sxs-lookup"><span data-stu-id="1b201-148">Windows Network Monitor</span></span>

<span data-ttu-id="1b201-149">サーバー上のリソース使用量を収集、表示、分析し、ネットワークトラフィックを測定します。</span><span class="sxs-lookup"><span data-stu-id="1b201-149">Collects, displays, analyzes resource usage on a server, and measures network traffic.</span></span> <span data-ttu-id="1b201-150">ネットワークモニターは、ネットワークアクティビティを排他的に監視します。</span><span class="sxs-lookup"><span data-stu-id="1b201-150">Network Monitor exclusively monitors network activity.</span></span> <span data-ttu-id="1b201-151">ネットワークデータを収集して分析し、このデータをパフォーマンスログで使用することで、ネットワークの使用状況を判断し、ネットワークの問題を特定し、今後のネットワークのニーズを予測することができます。</span><span class="sxs-lookup"><span data-stu-id="1b201-151">By capturing and analyzing network data, and using this data with performance logs, you can determine the network usage, identify network issues, and forecast future network needs.</span></span>

<span data-ttu-id="1b201-152">ネットワークモニター3.4 の詳細と、ネットワークモニターのインストールおよび構成方法と、データのキャプチャおよび分析方法については、このセッションを参照してください。ネットワークモニター3.3 の概要。</span><span class="sxs-lookup"><span data-stu-id="1b201-152">For more information about Network Monitor 3.4, and to learn how to install and configure Network Monitor and capture and analyze data, review this session: Network Monitor 3.3 Overview.</span></span> <span data-ttu-id="1b201-153">また、[ネットワークモニターのブログ](https://blogs.technet.com/b/netmon/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b201-153">Also, review the [Network Monitor blog](https://blogs.technet.com/b/netmon/).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

