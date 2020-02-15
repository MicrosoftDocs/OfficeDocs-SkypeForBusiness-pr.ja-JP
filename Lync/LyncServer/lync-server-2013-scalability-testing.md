---
title: Lync Server 2013 のスケーラビリティテスト
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b23bd731e123c8dba78c3919f9f2a1ff1a6fd1cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a><span data-ttu-id="2b600-102">Lync Server 2013 のスケーラビリティテスト</span><span class="sxs-lookup"><span data-stu-id="2b600-102">Scalability testing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b600-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="2b600-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="2b600-104">Lync Server 2013 には、インスタントメッセージング (IM) とプレゼンス、会議、エンタープライズ Voip など、すべての Lync Server のリアルタイム通信のサーバーインフラストラクチャが用意されています。</span><span class="sxs-lookup"><span data-stu-id="2b600-104">Lync Server 2013 provides the server infrastructure for all Lync Server real-time communications, including instant messaging (IM) and presence, conferencing, and Enterprise Voice.</span></span> <span data-ttu-id="2b600-105">これには、Lync Server 2013 プールのハードウェアリソースを使用するすべての機能が含まれるため、パフォーマンスと規模に影響します。</span><span class="sxs-lookup"><span data-stu-id="2b600-105">This includes any features that use the hardware resources of a Lync Server 2013 pool and, therefore, affect performance and scale.</span></span> <span data-ttu-id="2b600-106">すべての組織がすべての機能を同じように使用するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="2b600-106">All organizations do not use all features equally.</span></span>

<span data-ttu-id="2b600-107">たとえば、組織によっては、会議で非常に頻繁にビデオを使用している場合がありますが、ビデオの使用状況が少ない、またはまったくない場合があります。</span><span class="sxs-lookup"><span data-stu-id="2b600-107">For example, some organizations might use video in conferences very heavily while others might have little or no video usage.</span></span> <span data-ttu-id="2b600-108">一部の組織では、アプリケーション共有に PowerPoint スライドの共有を優先していますが、反対のものを好むこともあります。</span><span class="sxs-lookup"><span data-stu-id="2b600-108">Some organizations prefer PowerPoint slide sharing to application sharing, while others prefer the opposite.</span></span> <span data-ttu-id="2b600-109">エンタープライズ Voip を展開する組織では、応答グループアプリケーションが頻繁に使用されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="2b600-109">Those organizations that deploy Enterprise Voice might or might not use the Response Group application heavily.</span></span> <span data-ttu-id="2b600-110">ほとんどの組織では、監視サーバーを展開していますが、その多くはアーカイブサーバーを展開していません。</span><span class="sxs-lookup"><span data-stu-id="2b600-110">Most organizations deploy Monitoring Servers, but not many of them deploy Archiving Servers.</span></span> <span data-ttu-id="2b600-111">さらに、組織によって、ハードウェアの容量、ネットワークの容量、プールの数と展開されたプールの数を含む、同じインフラストラクチャが存在するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="2b600-111">Additionally, organizations do not all have the same infrastructures, including hardware capacities, network capacities, and the number of pools and size of pools deployed.</span></span> <span data-ttu-id="2b600-112">機能とインフラストラクチャの多様性は、スケーラビリティのテストにおいて課題となり、機能とインフラストラクチャのすべての可能な組み合わせをシミュレートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2b600-112">The diversity of features and infrastructures poses a challenge to scalability testing – it is not possible to simulate all possible combinations of features and infrastructures.</span></span>

<span data-ttu-id="2b600-113">Lync Server のスケーラビリティのサポートを決定するには、平均利用モデル (ユーザーモデル) に基づいて、すべての Lync Server 機能を同時に使用してテストを行います。</span><span class="sxs-lookup"><span data-stu-id="2b600-113">To determine scalability support for Lync Server, we conduct testing by using all Lync Server features concurrently, based on an average usage model (user model).</span></span> <span data-ttu-id="2b600-114">Lync Server ワークロードに適したユーザーモデルを決定するために、お客様の調査、Microsoft カスタマーエクスペリエンス向上プログラムからのフィードバック、Microsoft の内部 IT 部門からの Lync Server の使用状況データなど、多くのデータポイントを分析します。およびデータは、Live Meeting サービスからマイニングされます。</span><span class="sxs-lookup"><span data-stu-id="2b600-114">To determine an appropriate user model for Lync Server workloads, we analyze many data points, including customer surveys, feedback from the Microsoft customer experience improvement program, Lync Server usage data from the internal IT department at Microsoft, and data mined from our Live Meeting Service.</span></span> <span data-ttu-id="2b600-115">多くの場合、組織内の使用に関して十分な余裕を持たせるために、ユーザー モデルは負荷が高い方向に偏っています。</span><span class="sxs-lookup"><span data-stu-id="2b600-115">In many cases, the user model has a bias towards heavier loads to provide a comfortable margin for usage within an organization.</span></span>

<span data-ttu-id="2b600-116">スケーラビリティテストでは、Active Directory ドメインサービス、ハードウェアロードバランサー、ファイアウォールなどのインフラストラクチャコンポーネントを含む、推奨されるハードウェアおよびソフトウェア仕様に従って Lync Server 2013 プールを設定します。</span><span class="sxs-lookup"><span data-stu-id="2b600-116">In our scalability tests, we set up Lync Server 2013 pools according to the recommended hardware and software specifications, including infrastructure components, such as Active Directory Domain Services, hardware load balancers, and firewalls.</span></span> <span data-ttu-id="2b600-117">Lync Server 環境は、一般的な実際の環境にできるだけ近づけるようにセットアップされています。</span><span class="sxs-lookup"><span data-stu-id="2b600-117">We set up Lync Server environments as closely as possible to typical real-world environments.</span></span> <span data-ttu-id="2b600-118">次に、Lync server 2013 ストレスおよびパフォーマンスツールを使用して、Lync Server 2013 の負荷 (ユーザーモデルに基づいて) をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="2b600-118">We then use the Lync Server 2013 Stress and Performance Tool to simulate Lync Server 2013 loads (based on our user model).</span></span> <span data-ttu-id="2b600-119">.</span><span class="sxs-lookup"><span data-stu-id="2b600-119">.</span></span>

<span data-ttu-id="2b600-p105">スケーラビリティ テストは複数回繰り返します (3 週間にわたるテストの複数回の実行を含みます)。すべてのテスト結果を使用して、パフォーマンス チューニングに役立てるとともに、ユーザー モデルでのスケーラビリティの数値がサポートされることを検証します。</span><span class="sxs-lookup"><span data-stu-id="2b600-p105">We do multiple iterations of scalability tests (including multiple three-week test runs). We use the results of all tests to help with performance tuning and to verify support for the scalability numbers in our user model.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

