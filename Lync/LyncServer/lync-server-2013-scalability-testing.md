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
ms.openlocfilehash: d702b0a197e6e81fbc6833ca58968a10d8dd3fff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a><span data-ttu-id="c8dfe-102">Lync Server 2013 でのスケーラビリティのテスト</span><span class="sxs-lookup"><span data-stu-id="c8dfe-102">Scalability testing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8dfe-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c8dfe-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c8dfe-104">Lync Server 2013 は、インスタントメッセージング (IM) とプレゼンス、会議、エンタープライズ Voip など、すべての Lync Server のリアルタイム通信のサーバーインフラストラクチャを提供します。</span><span class="sxs-lookup"><span data-stu-id="c8dfe-104">Lync Server 2013 provides the server infrastructure for all Lync Server real-time communications, including instant messaging (IM) and presence, conferencing, and Enterprise Voice.</span></span> <span data-ttu-id="c8dfe-105">これには、Lync Server 2013 プールのハードウェアリソースを使用するすべての機能が含まれます。そのため、パフォーマンスと規模が影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="c8dfe-105">This includes any features that use the hardware resources of a Lync Server 2013 pool and, therefore, affect performance and scale.</span></span> <span data-ttu-id="c8dfe-106">すべての組織が同じ機能を使用するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c8dfe-106">All organizations do not use all features equally.</span></span>

<span data-ttu-id="c8dfe-107">たとえば、一部の組織では、会議でビデオを頻繁に使用することもありますが、ビデオの使用量が少ない、またはまったくない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="c8dfe-107">For example, some organizations might use video in conferences very heavily while others might have little or no video usage.</span></span> <span data-ttu-id="c8dfe-108">一部の組織では、PowerPoint スライドの共有をアプリケーション共有に適用していますが、その他の場合は反対のことを好みます。</span><span class="sxs-lookup"><span data-stu-id="c8dfe-108">Some organizations prefer PowerPoint slide sharing to application sharing, while others prefer the opposite.</span></span> <span data-ttu-id="c8dfe-109">エンタープライズボイスを展開する組織では、応答グループアプリケーションが多用されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c8dfe-109">Those organizations that deploy Enterprise Voice might or might not use the Response Group application heavily.</span></span> <span data-ttu-id="c8dfe-110">ほとんどの組織では、監視サーバーを展開していますが、その多くはアーカイブサーバーを展開しています。</span><span class="sxs-lookup"><span data-stu-id="c8dfe-110">Most organizations deploy Monitoring Servers, but not many of them deploy Archiving Servers.</span></span> <span data-ttu-id="c8dfe-111">さらに、組織には、ハードウェアの容量、ネットワークの容量、プールの数、展開されているプールのサイズなど、同じインフラストラクチャが含まれているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c8dfe-111">Additionally, organizations do not all have the same infrastructures, including hardware capacities, network capacities, and the number of pools and size of pools deployed.</span></span> <span data-ttu-id="c8dfe-112">機能とインフラストラクチャの多様性は、スケーラビリティテストの課題となります。機能とインフラストラクチャのすべての可能な組み合わせをシミュレートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c8dfe-112">The diversity of features and infrastructures poses a challenge to scalability testing – it is not possible to simulate all possible combinations of features and infrastructures.</span></span>

<span data-ttu-id="c8dfe-113">Lync Server のスケーラビリティのサポートを判断するには、平均的な利用モデル (ユーザーモデル) に基づいて、すべての Lync Server 機能を同時に使用してテストを実施します。</span><span class="sxs-lookup"><span data-stu-id="c8dfe-113">To determine scalability support for Lync Server, we conduct testing by using all Lync Server features concurrently, based on an average usage model (user model).</span></span> <span data-ttu-id="c8dfe-114">Lync Server のワークロードに適したユーザーモデルを決定するために、Microsoft の社内の IT 部門からのお客様のアンケート、Microsoft カスタマーエクスペリエンス向上プログラムからのフィードバック、Lync Server の使用状況データなど、さまざまなデータを分析します。また、skype Live Meeting サービスからデータを抽出します。</span><span class="sxs-lookup"><span data-stu-id="c8dfe-114">To determine an appropriate user model for Lync Server workloads, we analyze many data points, including customer surveys, feedback from the Microsoft customer experience improvement program, Lync Server usage data from the internal IT department at Microsoft, and data mined from our Live Meeting Service.</span></span> <span data-ttu-id="c8dfe-115">多くの場合、ユーザーモデルは、組織内での使用に適した余白を提供するために、負荷が高くなるようにバイアスしています。</span><span class="sxs-lookup"><span data-stu-id="c8dfe-115">In many cases, the user model has a bias towards heavier loads to provide a comfortable margin for usage within an organization.</span></span>

<span data-ttu-id="c8dfe-116">Skype のスケーラビリティテストでは、Active Directory ドメインサービス、ハードウェアロードバランサー、ファイアウォールなどのインフラストラクチャコンポーネントなど、推奨されるハードウェアとソフトウェア仕様に従って Lync Server 2013 プールをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="c8dfe-116">In our scalability tests, we set up Lync Server 2013 pools according to the recommended hardware and software specifications, including infrastructure components, such as Active Directory Domain Services, hardware load balancers, and firewalls.</span></span> <span data-ttu-id="c8dfe-117">Lync Server 環境は、実際の一般的な環境にできるだけ近づけるようにセットアップしています。</span><span class="sxs-lookup"><span data-stu-id="c8dfe-117">We set up Lync Server environments as closely as possible to typical real-world environments.</span></span> <span data-ttu-id="c8dfe-118">次に、Lync Server 2013 ストレス/パフォーマンスツールを使用して、Lync Server 2013 のロード (ユーザーモデルに基づく) をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="c8dfe-118">We then use the Lync Server 2013 Stress and Performance Tool to simulate Lync Server 2013 loads (based on our user model).</span></span> <span data-ttu-id="c8dfe-119">.</span><span class="sxs-lookup"><span data-stu-id="c8dfe-119">.</span></span>

<span data-ttu-id="c8dfe-120">スケーラビリティテスト (複数の3週間テストの実行を含む) を複数回繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c8dfe-120">We do multiple iterations of scalability tests (including multiple three-week test runs).</span></span> <span data-ttu-id="c8dfe-121">すべてのテストの結果を使用して、パフォーマンスの調整を行い、ユーザーモデルのスケーラビリティ数のサポートを確認します。</span><span class="sxs-lookup"><span data-stu-id="c8dfe-121">We use the results of all tests to help with performance tuning and to verify support for the scalability numbers in our user model.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

