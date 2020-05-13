---
title: 'Lync Server 2013: Microsoft Lync の展開方法の決定'
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
ms.openlocfilehash: d5f4e622d71175ec393706af39ce470c5030216a
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a><span data-ttu-id="81883-102">Lync Server 2013 の展開方法を決定する</span><span class="sxs-lookup"><span data-stu-id="81883-102">Deciding how to deploy Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81883-103">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="81883-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="81883-104">Lync を計画する場合、最初の主要な決定は、Microsoft Lync の展開方法 (Lync Server 2013 オンプレミス)、またはクラウド内の Lync Online を Microsoft 365 または Office 365 と共に展開することです。</span><span class="sxs-lookup"><span data-stu-id="81883-104">When planning for Lync, the first major decision is how to deploy Microsoft Lync: as Lync Server 2013 on premises, or Lync Online with Microsoft 365 or Office 365 in the cloud.</span></span>

  - <span data-ttu-id="81883-105">**Lync Server 2013 オンプレミス**: これにより、lync のすべての機能セットが提供され、展開の構成、カスタマイズ、および運用を極めて柔軟に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="81883-105">**Lync Server 2013 on-premises** : This choice provides the complete Lync feature set and provides ultimate flexibility in configuring, customizing, and operating your deployment.</span></span> <span data-ttu-id="81883-106">すべてのサーバーはオンサイトでインストールされ、組織によって保守されます。</span><span class="sxs-lookup"><span data-stu-id="81883-106">All servers are installed onsite and maintained by your organization.</span></span> <span data-ttu-id="81883-107">オンプレミスの展開では、Lync Server のすべての機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="81883-107">An on-premises deployment provides the full range of Lync Server features.</span></span>

  - <span data-ttu-id="81883-108">**クラウド内の Lync Online**Lync Online は、Lync Server のビジネスクラス機能を犠牲にせずに、クラウドベースのインスタントメッセージング、プレゼンス、および会議のコストとアジリティのメリットを必要とする組織向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="81883-108">**Lync Online in the cloud** Lync Online is designed for organizations that want the cost and agility benefits of cloud-based instant messaging, presence, and meetings without sacrificing the business-class capabilities of Lync Server.</span></span> <span data-ttu-id="81883-109">Lync Online では、Microsoft によって必要なサーバーインフラストラクチャが展開および維持され、継続的なメンテナンス、パッチ、およびアップグレードが処理されます。</span><span class="sxs-lookup"><span data-stu-id="81883-109">With Lync Online, Microsoft deploys and maintains the required server infrastructure, and handles ongoing maintenance, patches, and upgrades.</span></span> <span data-ttu-id="81883-110">オンプレミスの展開で使用できる一部の機能は、Lync Online では使用できません。</span><span class="sxs-lookup"><span data-stu-id="81883-110">Some features available in an on-premises deployment are not available in Lync Online.</span></span>

<span data-ttu-id="81883-111">どちらの種類の展開が最も適しているかは、展開する負荷と、組織の地理的状況およびビジネスの状況によって異なります。</span><span class="sxs-lookup"><span data-stu-id="81883-111">Which type of deployment would be best for you depends on the workloads you want to deploy, and your organization’s geographical and business status.</span></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="81883-112">Lync Server</span><span class="sxs-lookup"><span data-stu-id="81883-112">Lync Server</span></span>

<span data-ttu-id="81883-113">内部設置型の Lync Server 展開は、次のようなシナリオに最適です。</span><span class="sxs-lookup"><span data-stu-id="81883-113">An on-premises Lync Server deployment is best for the following scenarios:</span></span>

  - <span data-ttu-id="81883-114">**完全なエンタープライズ Voip 機能**    PBX を交換するために完全なエンタープライズ Voip ソリューションを展開したり、高度な通話機能を使用したりする予定の場合は、社内の Lync Server の展開が必要です。</span><span class="sxs-lookup"><span data-stu-id="81883-114">**Full Enterprise Voice Capabilities**   If you plan to deploy a full Enterprise Voice solution to replace your PBX or which uses advanced calling features, an on-premises Lync Server deployment is required.</span></span> <span data-ttu-id="81883-115">オンプレミスは、PBX システムとトランクとの直接接続、および応答グループやコールパークなどの高度な電話機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="81883-115">On-premises supports direct connectivity with PBX systems and trunks, and advanced phone features such as response groups and call park.</span></span> <span data-ttu-id="81883-116">Lync Online は現在これらの機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="81883-116">Lync Online does not currently support these features.</span></span>

  - <span data-ttu-id="81883-117">**メディア品質管理**    通話受付管理 (CAC) 機能やサービスの品質 (QoS) 機能などのメディア品質保証機能の全範囲が必要な場合は、オンプレミス展開を使用します。</span><span class="sxs-lookup"><span data-stu-id="81883-117">**Media Quality Controls**   If you want the full range of media quality assurance features, such as Call Admission Control (CAC) and Quality of Service (QoS) features, you will want an on-premises deployment .</span></span>

  - <span data-ttu-id="81883-118">**常設チャット**    組織の常設チャットを展開する必要がある場合は、オンプレミスの展開を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81883-118">**Persistent Chat**   If you need to deploy Persistent chat for your organization, you must choose an on-premises deployment.</span></span>

  - <span data-ttu-id="81883-119">**サードパーティのサーバーアプリケーション**    Microsoft ユニファイドコミュニケーションマネージ API (UCMA) を使用する信頼されたサードパーティアプリケーションと連携できるのは、社内展開のみです。</span><span class="sxs-lookup"><span data-stu-id="81883-119">**3rd-Party Server Applications**   Only on-premises deployments can work with trusted 3rd-party applications that use the Microsoft Unified Communications Managed API (UCMA).</span></span>

  - <span data-ttu-id="81883-120">**地域のサポート**     を必要とする多国籍/複数地域の企業複数の国または地域にデータセンターがあり、地域ベースでサーバーを展開および管理する必要がある場合は、この種類の地域管理機能を提供するため、オンプレミスの展開が最適です。</span><span class="sxs-lookup"><span data-stu-id="81883-120">**Multi-National/Multi-Regional Companies Needing Regional Support**   If you have datacenters in multiple countries or regions and need servers to be deployed and managed on a regional basis, an on-premises deployment is best, as it provides this type of regional management capabilities.</span></span>

  - <span data-ttu-id="81883-121">**ポリシー、レポート、アップグレード**     を完全に制御するオンプレミスの Lync Server 展開を使用すると、サーバーとクライアントのポリシーの完全なセット、監視やその他のレポート、アップグレードのタイミングにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="81883-121">**Complete control over policies, reports, and upgrades**   With an on premises Lync Server deployment, you have access to the full set of server and client policies, Monitoring and other reports, and timing of upgrades.</span></span> <span data-ttu-id="81883-122">Lync Online では、ポリシー設定とレポートのサブセットが提供されており、アップグレードを受け入れるために非常に限定的なウィンドウが提供されます。</span><span class="sxs-lookup"><span data-stu-id="81883-122">Lync Online provides a subset of policy setting and reports, and provides a limited, though significant, window for accepting upgrades.</span></span>

</div>

<div>

## <a name="lync-online"></a><span data-ttu-id="81883-123">Lync Online</span><span class="sxs-lookup"><span data-stu-id="81883-123">Lync Online</span></span>

<span data-ttu-id="81883-124">上記のどの要素も重要でない場合は、より展開が簡単で管理しやすい Lync Online を選択できます。</span><span class="sxs-lookup"><span data-stu-id="81883-124">If none of the factors in the preceding list are critical for you, you may want to choose Lync Online, for simpler deployment and manageability.</span></span> <span data-ttu-id="81883-125">Lync Online は、堅牢な IM、プレゼンス、会議機能セットを提供し、組織内のユーザー間で IP 経由で音声およびビデオ通話を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="81883-125">Lync Online provides a robust IM, presence and conferencing feature set, and also enables voice and video calls over IP between users in your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
