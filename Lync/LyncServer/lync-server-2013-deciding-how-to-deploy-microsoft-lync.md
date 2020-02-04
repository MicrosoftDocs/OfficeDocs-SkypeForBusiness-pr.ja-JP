---
title: 'Lync Server 2013: Microsoft Lync 展開方法の決定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aef6ac76b6c0e8a6fb3c0444ab219acf78119ecd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a><span data-ttu-id="af260-102">Lync Server 2013 展開方法の決定</span><span class="sxs-lookup"><span data-stu-id="af260-102">Deciding how to deploy Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af260-103">_**最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="af260-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="af260-104">Lync を計画する場合、最初の主な決定は、Microsoft Lync: Lync Server 2013 を社内に展開する方法、またはクラウドの Microsoft Office 365 で Lync Online を展開する方法です。</span><span class="sxs-lookup"><span data-stu-id="af260-104">When planning for Lync, the first major decision is how to deploy Microsoft Lync: as Lync Server 2013 on premises, or Lync Online with Microsoft Office 365 in the cloud.</span></span>

  - <span data-ttu-id="af260-105">**Lync Server 2013 オンプレミス**: lync のすべての機能セットが提供され、展開の構成、カスタマイズ、および操作に最適な柔軟性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="af260-105">**Lync Server 2013 on-premises** : This choice provides the complete Lync feature set and provides ultimate flexibility in configuring, customizing, and operating your deployment.</span></span> <span data-ttu-id="af260-106">すべてのサーバーがオンサイトにインストールされ、組織によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="af260-106">All servers are installed onsite and maintained by your organization.</span></span> <span data-ttu-id="af260-107">オンプレミスの展開では、Lync Server のさまざまな機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="af260-107">An on-premises deployment provides the full range of Lync Server features.</span></span>

  - <span data-ttu-id="af260-108">**クラウドでの Lync Online**Lync Online は、Lync Server のビジネスクラス機能を犠牲にすることなく、クラウドベースのインスタントメッセージング、プレゼンス、会議のコストとアジリティの向上を希望する組織向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="af260-108">**Lync Online in the cloud** Lync Online is designed for organizations that want the cost and agility benefits of cloud-based instant messaging, presence, and meetings without sacrificing the business-class capabilities of Lync Server.</span></span> <span data-ttu-id="af260-109">Lync Online を使用すると、Microsoft は必要なサーバーインフラストラクチャを展開して管理し、継続的なメンテナンス、パッチ、アップグレードを処理します。</span><span class="sxs-lookup"><span data-stu-id="af260-109">With Lync Online, Microsoft deploys and maintains the required server infrastructure, and handles ongoing maintenance, patches, and upgrades.</span></span> <span data-ttu-id="af260-110">オンプレミスの展開で利用できる機能の一部は、Lync Online では利用できません。</span><span class="sxs-lookup"><span data-stu-id="af260-110">Some features available in an on-premises deployment are not available in Lync Online.</span></span>

<span data-ttu-id="af260-111">どのような種類の展開を使用するかは、展開するワークロードと組織の地理的状態とビジネス状態によって異なります。</span><span class="sxs-lookup"><span data-stu-id="af260-111">Which type of deployment would be best for you depends on the workloads you want to deploy, and your organization’s geographical and business status.</span></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="af260-112">Lync Server</span><span class="sxs-lookup"><span data-stu-id="af260-112">Lync Server</span></span>

<span data-ttu-id="af260-113">オンプレミスの Lync Server 展開は、次のシナリオに適しています。</span><span class="sxs-lookup"><span data-stu-id="af260-113">An on-premises Lync Server deployment is best for the following scenarios:</span></span>

  - <span data-ttu-id="af260-114">**完全なエンタープライズ音声機能**   PBX の代わりとして、または高度な通話機能を使用する完全なエンタープライズボイスソリューションを展開する予定がある場合は、オンプレミスの Lync Server を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af260-114">**Full Enterprise Voice Capabilities**   If you plan to deploy a full Enterprise Voice solution to replace your PBX or which uses advanced calling features, an on-premises Lync Server deployment is required.</span></span> <span data-ttu-id="af260-115">オンプレミスは、PBX システムと trunks との直接接続、および応答グループやコールパークなどの高度な電話機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="af260-115">On-premises supports direct connectivity with PBX systems and trunks, and advanced phone features such as response groups and call park.</span></span> <span data-ttu-id="af260-116">現時点では、Lync Online はこれらの機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="af260-116">Lync Online does not currently support these features.</span></span>

  - <span data-ttu-id="af260-117">**メディア品質コントロール**   通話受付制御 (CAC) 機能やサービス品質 (QoS) 機能など、さまざまな種類のメディア品質保証機能が必要な場合は、オンプレミスの展開が必要になります。</span><span class="sxs-lookup"><span data-stu-id="af260-117">**Media Quality Controls**   If you want the full range of media quality assurance features, such as Call Admission Control (CAC) and Quality of Service (QoS) features, you will want an on-premises deployment .</span></span>

  - <span data-ttu-id="af260-118">**常設チャット**   組織に常設チャットを展開する必要がある場合は、オンプレミスの展開を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af260-118">**Persistent Chat**   If you need to deploy Persistent chat for your organization, you must choose an on-premises deployment.</span></span>

  - <span data-ttu-id="af260-119">**サードパーティのサーバーアプリケーション**   では、オンプレミスの展開のみが、Microsoft ユニファイドコミュニケーションマネージ API を使う信頼されたサードパーティアプリケーションと連携できます (ucma)。</span><span class="sxs-lookup"><span data-stu-id="af260-119">**3rd-Party Server Applications**   Only on-premises deployments can work with trusted 3rd-party applications that use the Microsoft Unified Communications Managed API (UCMA).</span></span>

  - <span data-ttu-id="af260-120">**地域のサポート**   が必要な複数地域の企業、複数の国または地域のデータセンターがあり、各地域にサーバーを展開して管理する必要がある場合は、オンプレミスの展開をお勧めします。この種類の地域管理機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="af260-120">**Multi-National/Multi-Regional Companies Needing Regional Support**   If you have datacenters in multiple countries or regions and need servers to be deployed and managed on a regional basis, an on-premises deployment is best, as it provides this type of regional management capabilities.</span></span>

  - <span data-ttu-id="af260-121">\*\*\*\*   オンプレミスの Lync Server 展開でポリシー、レポート、アップグレードを管理することで、サーバーとクライアントのすべてのポリシー、監視およびその他のレポート、アップグレードのタイミングにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="af260-121">**Complete control over policies, reports, and upgrades**   With an on premises Lync Server deployment, you have access to the full set of server and client policies, Monitoring and other reports, and timing of upgrades.</span></span> <span data-ttu-id="af260-122">Lync Online には、ポリシー設定とレポートのサブセットが用意されています。このウィンドウには、アップグレードを承認するための重要なウィンドウが含まれています。</span><span class="sxs-lookup"><span data-stu-id="af260-122">Lync Online provides a subset of policy setting and reports, and provides a limited, though significant, window for accepting upgrades.</span></span>

</div>

<div>

## <a name="lync-online"></a><span data-ttu-id="af260-123">Lync Online</span><span class="sxs-lookup"><span data-stu-id="af260-123">Lync Online</span></span>

<span data-ttu-id="af260-124">上に挙げた要因が自分にとって重要ではない場合は、[Lync Online] を選んで、展開と管理性をさらに向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="af260-124">If none of the factors in the preceding list are critical for you, you may want to choose Lync Online, for simpler deployment and manageability.</span></span> <span data-ttu-id="af260-125">Lync Online は、強力な IM、プレゼンス、会議機能のセットを提供します。また、組織内のユーザー間での音声通話とビデオ通話も可能になります。</span><span class="sxs-lookup"><span data-stu-id="af260-125">Lync Online provides a robust IM, presence and conferencing feature set, and also enables voice and video calls over IP between users in your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

