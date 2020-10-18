---
title: 'Lync Server 2013: サービスレベル契約'
description: 'Lync Server 2013: サービスレベル契約。'
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
ms.openlocfilehash: 817aa8e092d9d368dfd8cb920958553ee32e8600
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576473"
---
# <a name="service-level-agreements-in-lync-server-2013"></a><span data-ttu-id="aeb9f-103">Lync Server 2013 でのサービスレベル契約</span><span class="sxs-lookup"><span data-stu-id="aeb9f-103">Service level agreements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aeb9f-104">_**トピックの最終更新日:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="aeb9f-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="aeb9f-105">SLA は、お客様が期待するサービスを定義するドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="aeb9f-105">The SLA is a document that defines the services that your customer expects from you.</span></span> <span data-ttu-id="aeb9f-106">このドキュメントの複雑さと内容は、お客様が内部 (環境内) であるか、または外部であるかによって大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="aeb9f-106">The complexity and content of this document depends largely on whether customers are internal (within your environment) or external.</span></span>

<div>

## <a name="external-customers"></a><span data-ttu-id="aeb9f-107">外部のお客様</span><span class="sxs-lookup"><span data-stu-id="aeb9f-107">External Customers</span></span>

<span data-ttu-id="aeb9f-108">お客様が外部である場合、SLA は、定義されたサービスの範囲内または外部でのパフォーマンスに関する財政的なインセンティブと罰則を受ける法的契約に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="aeb9f-108">If your customer is external, the SLA may be part of a legal contract with financial incentives and penalties for performance that falls inside or outside defined levels of service.</span></span> <span data-ttu-id="aeb9f-109">これらのサービスレベルを定義することは、コントラクトのネゴシエーション全体に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeb9f-109">Defining these levels of service should be part of the overall contract negotiation.</span></span>

<span data-ttu-id="aeb9f-110">すべての契約の場合と同様に、両方の当事者が期待を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="aeb9f-110">As with all contracts, it’s important that both parties understand expectations.</span></span> <span data-ttu-id="aeb9f-111">SLA では、これらの期待値が定義されています。</span><span class="sxs-lookup"><span data-stu-id="aeb9f-111">The SLA defines these expectations.</span></span> <span data-ttu-id="aeb9f-112">ドキュメントの内容は、お客様と交渉されるため、めったに変更されません。</span><span class="sxs-lookup"><span data-stu-id="aeb9f-112">The contents of the document should change infrequently and only because of negotiations with the customer.</span></span>

</div>

<div>

## <a name="internal-customers"></a><span data-ttu-id="aeb9f-113">内部のお客様</span><span class="sxs-lookup"><span data-stu-id="aeb9f-113">Internal Customers</span></span>

<span data-ttu-id="aeb9f-114">お客様が内部の場合でも、運用チームおよび IT システムの予想されるサービスを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeb9f-114">If your customer is internal, you may still want to define the services that are expected of operations teams and of IT systems.</span></span> <span data-ttu-id="aeb9f-115">SLA は、運用スタッフが作成するものであり、組織内で IT サービスを利用できるようにするための一連の目標として使用することができます。</span><span class="sxs-lookup"><span data-stu-id="aeb9f-115">The SLA may be created by the operations staff and intended as a set of goals for the availability of IT services within your organization.</span></span> <span data-ttu-id="aeb9f-116">また、パフォーマンスレベルが管理によって設定され、スタッフのパフォーマンスを評価するときにベンチマークとして使用される場合もあります。</span><span class="sxs-lookup"><span data-stu-id="aeb9f-116">Or, performance levels may be set by management and used as benchmarks when assessing staff performance.</span></span>

</div>

<div>

## <a name="typical-criteria"></a><span data-ttu-id="aeb9f-117">一般的な抽出条件</span><span class="sxs-lookup"><span data-stu-id="aeb9f-117">Typical Criteria</span></span>

<span data-ttu-id="aeb9f-118">Sla には、可用性、サポート、および容量の最小レベルの条件を定義するセクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="aeb9f-118">SLAs include sections that define criteria of minimum levels of availability, support, and capacity.</span></span>

  - <span data-ttu-id="aeb9f-119">**可用性**    サイトおよびその他の Lync services が使用可能になる時間とオペレーティングシステムを定義します。</span><span class="sxs-lookup"><span data-stu-id="aeb9f-119">**Availability**   Define the hours and the operating systems on which sites and other Lync services will be available.</span></span> <span data-ttu-id="aeb9f-120">サービスの可用性に影響を与える定期的な保守を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeb9f-120">Any routine maintenance that affects service availability should be defined.</span></span> <span data-ttu-id="aeb9f-121">インターネット接続の損失など、サービスに影響を与える外部要因を定義します。</span><span class="sxs-lookup"><span data-stu-id="aeb9f-121">Define external factors that affect service, for example, the loss of Internet connectivity.</span></span>

  - <span data-ttu-id="aeb9f-122">**サポート**    システムのサポートが利用可能になる時間を定義します。</span><span class="sxs-lookup"><span data-stu-id="aeb9f-122">**Support**   Define the hours when support for a system will be available.</span></span> <span data-ttu-id="aeb9f-123">お客様がサポートスタッフに連絡する方法、インシデントをグループ化する方法、インシデントを解決して解決するための目標時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="aeb9f-123">Specify methods for customers to contact support staff, how incidents are grouped, and target time to respond and to resolve the incident.</span></span> <span data-ttu-id="aeb9f-124">お客様へのフィードバックの頻度と内容を定義します。</span><span class="sxs-lookup"><span data-stu-id="aeb9f-124">Define frequency and content of feedback to the customer.</span></span>

  - <span data-ttu-id="aeb9f-125">**容量**    Lync サイトの最大有効サイズと、制限を超えた場合に実行する手順を定義します。</span><span class="sxs-lookup"><span data-stu-id="aeb9f-125">**Capacity**   Define the maximum enabled size of Lync sites and the steps to take if the limit is exceeded.</span></span> <span data-ttu-id="aeb9f-126">ドキュメントライブラリからドキュメントを取得する時間など、標準的なタスクを実行するための最大許容時間を定義します。</span><span class="sxs-lookup"><span data-stu-id="aeb9f-126">Define the maximum enabled time to do standard tasks, such as the time to retrieve a document from a document library.</span></span> <span data-ttu-id="aeb9f-127">Lync プールごとの最大ユーザー数を定義し、さらにユーザーを追加する場合は処理能力を向上させるためのプロセスに同意します。</span><span class="sxs-lookup"><span data-stu-id="aeb9f-127">Define the maximum number of users per Lync pool and agree to a process to increase capacity if more users are added.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

