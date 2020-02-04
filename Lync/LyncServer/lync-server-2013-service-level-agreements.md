---
title: 'Lync Server 2013: サービスレベルアグリーメント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Service level agreements
ms:assetid: 10899bad-e8b0-422d-83c9-1599fb3a7d17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720321(v=OCS.15)
ms:contentKeyID: 63969580
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8c4b827cf2b82eb315ec166bcabb2452e7d8bdc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="service-level-agreements-in-lync-server-2013"></a><span data-ttu-id="d3530-102">Lync Server 2013 のサービスレベル契約</span><span class="sxs-lookup"><span data-stu-id="d3530-102">Service level agreements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3530-103">_**最終更新日:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="d3530-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="d3530-104">SLA は、顧客が期待しているサービスを定義するドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="d3530-104">The SLA is a document that defines the services that your customer expects from you.</span></span> <span data-ttu-id="d3530-105">このドキュメントの複雑さと内容は、ユーザーが内部 (環境内) と外部のどちらであるかによって大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="d3530-105">The complexity and content of this document depends largely on whether customers are internal (within your environment) or external.</span></span>

<div>

## <a name="external-customers"></a><span data-ttu-id="d3530-106">外部のお客様</span><span class="sxs-lookup"><span data-stu-id="d3530-106">External Customers</span></span>

<span data-ttu-id="d3530-107">顧客が外部の場合、SLA は、定義されたサービスレベルの内部または外部のパフォーマンスに関する財務インセンティブと罰則の対象となります。</span><span class="sxs-lookup"><span data-stu-id="d3530-107">If your customer is external, the SLA may be part of a legal contract with financial incentives and penalties for performance that falls inside or outside defined levels of service.</span></span> <span data-ttu-id="d3530-108">これらのレベルのサービスを定義することは、コントラクトのネゴシエーション全体に含まれます。</span><span class="sxs-lookup"><span data-stu-id="d3530-108">Defining these levels of service should be part of the overall contract negotiation.</span></span>

<span data-ttu-id="d3530-109">すべての契約の場合と同様に、両方の当事者が期待を理解していることが重要です。</span><span class="sxs-lookup"><span data-stu-id="d3530-109">As with all contracts, it’s important that both parties understand expectations.</span></span> <span data-ttu-id="d3530-110">SLA では、これらの期待値を定義しています。</span><span class="sxs-lookup"><span data-stu-id="d3530-110">The SLA defines these expectations.</span></span> <span data-ttu-id="d3530-111">ドキュメントの内容が変更されるのは、顧客との交渉のためだけであるためです。</span><span class="sxs-lookup"><span data-stu-id="d3530-111">The contents of the document should change infrequently and only because of negotiations with the customer.</span></span>

</div>

<div>

## <a name="internal-customers"></a><span data-ttu-id="d3530-112">社内のお客様</span><span class="sxs-lookup"><span data-stu-id="d3530-112">Internal Customers</span></span>

<span data-ttu-id="d3530-113">お客様が社内の場合は、運用チームと IT システムの期待されるサービスを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="d3530-113">If your customer is internal, you may still want to define the services that are expected of operations teams and of IT systems.</span></span> <span data-ttu-id="d3530-114">SLA は、運営スタッフによって作成され、組織内の IT サービスの利用が可能な目標のセットとして作られる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d3530-114">The SLA may be created by the operations staff and intended as a set of goals for the availability of IT services within your organization.</span></span> <span data-ttu-id="d3530-115">または、管理者によってパフォーマンスレベルが設定され、スタッフのパフォーマンスを評価するときにベンチマークとして使用されることがあります。</span><span class="sxs-lookup"><span data-stu-id="d3530-115">Or, performance levels may be set by management and used as benchmarks when assessing staff performance.</span></span>

</div>

<div>

## <a name="typical-criteria"></a><span data-ttu-id="d3530-116">一般的な抽出条件</span><span class="sxs-lookup"><span data-stu-id="d3530-116">Typical Criteria</span></span>

<span data-ttu-id="d3530-117">Sla には、可用性、サポート、および容量の最小レベルの条件を定義するセクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d3530-117">SLAs include sections that define criteria of minimum levels of availability, support, and capacity.</span></span>

  - <span data-ttu-id="d3530-118">**[可用性**   ] サイトや他の Lync サービスを利用できる時間とオペレーティングシステムを定義します。</span><span class="sxs-lookup"><span data-stu-id="d3530-118">**Availability**   Define the hours and the operating systems on which sites and other Lync services will be available.</span></span> <span data-ttu-id="d3530-119">サービスの可用性に影響を与える日常的なメンテナンスは、定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3530-119">Any routine maintenance that affects service availability should be defined.</span></span> <span data-ttu-id="d3530-120">インターネット接続の損失など、サービスに影響を与える外部要因を定義します。</span><span class="sxs-lookup"><span data-stu-id="d3530-120">Define external factors that affect service, for example, the loss of Internet connectivity.</span></span>

  - <span data-ttu-id="d3530-121">**サポート**   システムのサポートが利用できるようになるまでの時間を定義します。</span><span class="sxs-lookup"><span data-stu-id="d3530-121">**Support**   Define the hours when support for a system will be available.</span></span> <span data-ttu-id="d3530-122">顧客がサポートスタッフに連絡する方法、インシデントをグループ化する方法、インシデントを解決するための目標時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="d3530-122">Specify methods for customers to contact support staff, how incidents are grouped, and target time to respond and to resolve the incident.</span></span> <span data-ttu-id="d3530-123">顧客へのフィードバックの頻度とコンテンツを定義します。</span><span class="sxs-lookup"><span data-stu-id="d3530-123">Define frequency and content of feedback to the customer.</span></span>

  - <span data-ttu-id="d3530-124">**[キャパシティ**   ] は、Lync サイトの最大有効サイズと、制限を超えた場合に実行する手順を定義します。</span><span class="sxs-lookup"><span data-stu-id="d3530-124">**Capacity**   Define the maximum enabled size of Lync sites and the steps to take if the limit is exceeded.</span></span> <span data-ttu-id="d3530-125">ドキュメントライブラリからドキュメントを取得する時間など、標準のタスクを実行するための最大有効時間を定義します。</span><span class="sxs-lookup"><span data-stu-id="d3530-125">Define the maximum enabled time to do standard tasks, such as the time to retrieve a document from a document library.</span></span> <span data-ttu-id="d3530-126">Lync プールあたりの最大ユーザー数を定義し、さらに多くのユーザーが追加された場合に、容量を増やすためのプロセスに同意します。</span><span class="sxs-lookup"><span data-stu-id="d3530-126">Define the maximum number of users per Lync pool and agree to a process to increase capacity if more users are added.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

