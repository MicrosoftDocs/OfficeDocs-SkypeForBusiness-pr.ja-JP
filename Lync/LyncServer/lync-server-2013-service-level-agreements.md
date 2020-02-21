---
title: 'Lync Server 2013: サービスレベル契約'
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
ms.openlocfilehash: 8f902a946d272ce3a16db5f032b74ec031c7e3a7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="service-level-agreements-in-lync-server-2013"></a><span data-ttu-id="fc77e-102">Lync Server 2013 でのサービスレベル契約</span><span class="sxs-lookup"><span data-stu-id="fc77e-102">Service level agreements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc77e-103">_**トピックの最終更新日:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="fc77e-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="fc77e-104">SLA は、お客様が期待するサービスを定義するドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="fc77e-104">The SLA is a document that defines the services that your customer expects from you.</span></span> <span data-ttu-id="fc77e-105">このドキュメントの複雑さと内容は、お客様が内部 (環境内) であるか、または外部であるかによって大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="fc77e-105">The complexity and content of this document depends largely on whether customers are internal (within your environment) or external.</span></span>

<div>

## <a name="external-customers"></a><span data-ttu-id="fc77e-106">外部のお客様</span><span class="sxs-lookup"><span data-stu-id="fc77e-106">External Customers</span></span>

<span data-ttu-id="fc77e-107">お客様が外部である場合、SLA は、定義されたサービスの範囲内または外部でのパフォーマンスに関する財政的なインセンティブと罰則を受ける法的契約に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="fc77e-107">If your customer is external, the SLA may be part of a legal contract with financial incentives and penalties for performance that falls inside or outside defined levels of service.</span></span> <span data-ttu-id="fc77e-108">これらのサービスレベルを定義することは、コントラクトのネゴシエーション全体に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc77e-108">Defining these levels of service should be part of the overall contract negotiation.</span></span>

<span data-ttu-id="fc77e-109">すべての契約の場合と同様に、両方の当事者が期待を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="fc77e-109">As with all contracts, it’s important that both parties understand expectations.</span></span> <span data-ttu-id="fc77e-110">SLA では、これらの期待値が定義されています。</span><span class="sxs-lookup"><span data-stu-id="fc77e-110">The SLA defines these expectations.</span></span> <span data-ttu-id="fc77e-111">ドキュメントの内容は、お客様と交渉されるため、めったに変更されません。</span><span class="sxs-lookup"><span data-stu-id="fc77e-111">The contents of the document should change infrequently and only because of negotiations with the customer.</span></span>

</div>

<div>

## <a name="internal-customers"></a><span data-ttu-id="fc77e-112">内部のお客様</span><span class="sxs-lookup"><span data-stu-id="fc77e-112">Internal Customers</span></span>

<span data-ttu-id="fc77e-113">お客様が内部の場合でも、運用チームおよび IT システムの予想されるサービスを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc77e-113">If your customer is internal, you may still want to define the services that are expected of operations teams and of IT systems.</span></span> <span data-ttu-id="fc77e-114">SLA は、運用スタッフが作成するものであり、組織内で IT サービスを利用できるようにするための一連の目標として使用することができます。</span><span class="sxs-lookup"><span data-stu-id="fc77e-114">The SLA may be created by the operations staff and intended as a set of goals for the availability of IT services within your organization.</span></span> <span data-ttu-id="fc77e-115">また、パフォーマンスレベルが管理によって設定され、スタッフのパフォーマンスを評価するときにベンチマークとして使用される場合もあります。</span><span class="sxs-lookup"><span data-stu-id="fc77e-115">Or, performance levels may be set by management and used as benchmarks when assessing staff performance.</span></span>

</div>

<div>

## <a name="typical-criteria"></a><span data-ttu-id="fc77e-116">一般的な抽出条件</span><span class="sxs-lookup"><span data-stu-id="fc77e-116">Typical Criteria</span></span>

<span data-ttu-id="fc77e-117">Sla には、可用性、サポート、および容量の最小レベルの条件を定義するセクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fc77e-117">SLAs include sections that define criteria of minimum levels of availability, support, and capacity.</span></span>

  - <span data-ttu-id="fc77e-118">**可用性**   サイトおよびその他の Lync サービスが利用可能になる時間とオペレーティングシステムを定義します。</span><span class="sxs-lookup"><span data-stu-id="fc77e-118">**Availability**   Define the hours and the operating systems on which sites and other Lync services will be available.</span></span> <span data-ttu-id="fc77e-119">サービスの可用性に影響を与える定期的な保守を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc77e-119">Any routine maintenance that affects service availability should be defined.</span></span> <span data-ttu-id="fc77e-120">インターネット接続の損失など、サービスに影響を与える外部要因を定義します。</span><span class="sxs-lookup"><span data-stu-id="fc77e-120">Define external factors that affect service, for example, the loss of Internet connectivity.</span></span>

  - <span data-ttu-id="fc77e-121">**サポート**   システムのサポートが利用可能になる時間を定義します。</span><span class="sxs-lookup"><span data-stu-id="fc77e-121">**Support**   Define the hours when support for a system will be available.</span></span> <span data-ttu-id="fc77e-122">お客様がサポートスタッフに連絡する方法、インシデントをグループ化する方法、インシデントを解決して解決するための目標時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="fc77e-122">Specify methods for customers to contact support staff, how incidents are grouped, and target time to respond and to resolve the incident.</span></span> <span data-ttu-id="fc77e-123">お客様へのフィードバックの頻度と内容を定義します。</span><span class="sxs-lookup"><span data-stu-id="fc77e-123">Define frequency and content of feedback to the customer.</span></span>

  - <span data-ttu-id="fc77e-124">**[容量**   ] Lync サイトの最大許容サイズと、制限を超えた場合に実行する手順を定義します。</span><span class="sxs-lookup"><span data-stu-id="fc77e-124">**Capacity**   Define the maximum enabled size of Lync sites and the steps to take if the limit is exceeded.</span></span> <span data-ttu-id="fc77e-125">ドキュメントライブラリからドキュメントを取得する時間など、標準的なタスクを実行するための最大許容時間を定義します。</span><span class="sxs-lookup"><span data-stu-id="fc77e-125">Define the maximum enabled time to do standard tasks, such as the time to retrieve a document from a document library.</span></span> <span data-ttu-id="fc77e-126">Lync プールごとの最大ユーザー数を定義し、さらにユーザーを追加する場合は処理能力を向上させるためのプロセスに同意します。</span><span class="sxs-lookup"><span data-stu-id="fc77e-126">Define the maximum number of users per Lync pool and agree to a process to increase capacity if more users are added.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

