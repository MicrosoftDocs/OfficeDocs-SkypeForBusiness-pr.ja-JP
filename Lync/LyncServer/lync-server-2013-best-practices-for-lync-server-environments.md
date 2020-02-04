---
title: 'Lync Server 2013: Lync Server 環境のベストプラクティス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for Lync Server environments
ms:assetid: b0e45d84-09c8-4d3e-aad0-bc6f34ce233b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720348(v=OCS.15)
ms:contentKeyID: 63969642
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf207f4cd0303330ccb01dc56e28b949c1df22f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-lync-server-2013-environments"></a><span data-ttu-id="cd741-102">Lync Server 2013 環境のベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="cd741-102">Best practices for Lync Server 2013 environments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd741-103">_**最終更新日:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="cd741-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="cd741-104">システムの実行中の操作には、次の一般的な原則を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd741-104">The following general principles should be applied to ongoing operations of your system:</span></span>

  - <span data-ttu-id="cd741-105">**Mof mof を理解して使用**   することは、ベストプラクティス、原則、およびモデルの集まりで、IT 資産の管理について組織の技術ガイダンスを提供します。たとえば、毎日の Lync Server 2013 の操作などです。</span><span class="sxs-lookup"><span data-stu-id="cd741-105">**Understand and utilize MOF**   MOF is a collection of best practices, principles, and models that provide organizations technical guidance about the management of IT assets, such as daily Lync Server 2013 operations.</span></span> <span data-ttu-id="cd741-106">MOF ガイドラインは、次のように、Microsoft 製品のミッションクリティカルな生産システムの信頼性、可用性、サポート性、および管理性を実現するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cd741-106">Following MOF guidelines can help you achieve mission-critical production system reliability, availability, supportability, and manageability for Microsoft products.</span></span> <span data-ttu-id="cd741-107">詳細については、「 [Microsoft Operations Framework 4.0](http://go.microsoft.com/fwlink/p/?linkid=40939)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd741-107">For more information, see [Microsoft Operations Framework 4.0](http://go.microsoft.com/fwlink/p/?linkid=40939).</span></span>

  - <span data-ttu-id="cd741-108">**Lync server 2013**   のベストプラクティスについては、「lync server 2013 を管理するための実用的で実証された手順を実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cd741-108">**Learn about best practices for Lync Server 2013**   We recommend that you implement practical and proven procedures to manage Lync Server 2013.</span></span> <span data-ttu-id="cd741-109">試用、テスト、文書化された操作を管理する方法は、独自のメソッドを開発する場合よりも効率的に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cd741-109">By using tried, tested, and documented methods of managing operations may be more efficient than developing your own methods.</span></span>

  - <span data-ttu-id="cd741-110">**日常的、週単位、月**   単位のプロセスに個別の操作を行うことで、必要な運用タスクを定期的に文書化することができます。</span><span class="sxs-lookup"><span data-stu-id="cd741-110">**Separate operations into daily, weekly, and monthly processes**   Document the required operational tasks that you'll regularly perform.</span></span> <span data-ttu-id="cd741-111">タスクの実行方法を文書化することで、新しいテクノロジが展開された、またはスタッフが変更されたときなど、運用環境に変更があった場合に、情報が確実に保持されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="cd741-111">Documenting how you perform tasks helps make sure that your information is preserved when there is a change in your operational environment such as when new technologies are deployed or staff changes occur.</span></span> <span data-ttu-id="cd741-112">タスクが毎日、毎週、毎月実行される管理可能なワークロードに、運用タスクを分けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cd741-112">We recommend that operational tasks be separated into manageable workloads where tasks are performed daily, weekly, and monthly.</span></span> <span data-ttu-id="cd741-113">日常的な作業では、システムの機能に重点を置いています。また、毎月のタスクでは、システムの長期の正常性を確保することに重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="cd741-113">Daily tasks would focus efforts on the functioning of a system, and monthly tasks would focus more on ensuring the long-term health of a system.</span></span>
    
    <span data-ttu-id="cd741-114">このドキュメントは、エンタープライズ Voip でインスタントメッセージ/プレゼンス (IM/P) コンポーネントまたは IM/P を展開する環境で使用できます。</span><span class="sxs-lookup"><span data-stu-id="cd741-114">This document can be used in environments deploying only instant messaging/presence (IM/P) components or IM/P with Enterprise Voice.</span></span> <span data-ttu-id="cd741-115">タスクまたはチェックリスト項目がエンタープライズ Voip に固有の場合、これが説明されています。また、環境にエンタープライズ Voip が含まれていない場合は、その部分がスキップされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cd741-115">When tasks or checklist items are specific to Enterprise Voice, this is mentioned and if your environment does not include Enterprise Voice the portion may be skipped.</span></span>

  - <span data-ttu-id="cd741-116">**Lync server 2013**   を使用するために必要なツールを展開する多くのツールを利用して、問題のトラブルシューティング、タスクの自動化、lync server 2013 環境の監視と維持に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cd741-116">**Deploy the tools that are required for operating Lync Server 2013**   Many tools are available to help troubleshoot issues, automate tasks, and help monitor and maintain the Lync Server 2013 environment.</span></span> <span data-ttu-id="cd741-117">運営チームによって実行されるタスクを正確かつ効率的に実行し、管理された方法で実行するために、組織用に標準のツールセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="cd741-117">Define a standard set of tools for your organization so the tasks that are performed by the operations team are performed accurately, efficiently, consistently, and in a controlled manner.</span></span> <span data-ttu-id="cd741-118">また、インシデントおよび主要構成の変更を追跡するプロセスも実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd741-118">You should also implement processes to track incidents and major configuration changes.</span></span>

<div>

## <a name="reference"></a><span data-ttu-id="cd741-119">Reference</span><span class="sxs-lookup"><span data-stu-id="cd741-119">Reference</span></span>

<span data-ttu-id="cd741-120">一般的にサーバー管理の基本について理解していない読者のために、ここではサーバー管理のプラクティスの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd741-120">For the benefit of readers not already familiar with the basics of server management in general, we provide an overview of server management practices.</span></span> <span data-ttu-id="cd741-121">既にサーバー管理に慣れている読者は、このセクションをスキップすることができます。</span><span class="sxs-lookup"><span data-stu-id="cd741-121">Readers already familiar with server management may choose to skip this section.</span></span>

<span data-ttu-id="cd741-122">ベストプラクティスとは、IT プロフェッショナルが多くの環境で得た知識と経験に基づいた推奨事項です。</span><span class="sxs-lookup"><span data-stu-id="cd741-122">Best practices are recommendations that are based on the knowledge and experience that IT professionals have gained across many environments.</span></span> <span data-ttu-id="cd741-123">Lync Server の管理者が日常的に実行する必要のある一般的なタスクの標準的な手順と、Lync Server 環境を管理するために使う必要のあるツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cd741-123">They provide standard procedures for typical tasks that your Lync Server administrators must perform daily, and list the tools that they should use to manage a Lync Server environment.</span></span>

<span data-ttu-id="cd741-124">Lync 管理者向けの一般的なタスクには、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="cd741-124">Typical tasks for Lync administrators include the following:</span></span>

  - <span data-ttu-id="cd741-125">**容量と可用性の管理**   によって、将来の容量要件を予測し、システムの容量、信頼性、および可用性に関するレポートを作成する方法と測定方法が定義されます。</span><span class="sxs-lookup"><span data-stu-id="cd741-125">**Capacity and Availability Management**   Define how and what to measure to predict future capacity requirements and to report about the capacity, reliability, and availability of your systems.</span></span> <span data-ttu-id="cd741-126">Lync Server を実行しているサーバーがシステムの負荷を処理するように設定されていること、および予期しないダウンタイムがサービスレベル契約 (SLA) で定義されているレベルの下にあることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd741-126">You must verify that servers that are running Lync Server are sized to handle the load on the system, and that unplanned downtime is kept under the levels defined in the service level agreement (SLA).</span></span> <span data-ttu-id="cd741-127">さらに、定義された要件を引き続き満たすためには、ハードウェアをアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd741-127">Additionally, you'll have to upgrade hardware to continue to meet the defined requirements.</span></span>

  - <span data-ttu-id="cd741-128">**管理と構成の管理**   を変更し、IT システムに加えられた変更を制御します。</span><span class="sxs-lookup"><span data-stu-id="cd741-128">**Change Management and Configuration Management**   Control how changes are made to IT systems.</span></span> <span data-ttu-id="cd741-129">これには、テスト、アプリケーションのフィードバックと不測事態対応の計画、すべての変更の文書化、問題が発生した場合の管理からの承認などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cd741-129">This should include testing, application feedback and contingency plans, documentation of all changes, and approval from management if issues occur.</span></span> <span data-ttu-id="cd741-130">ソフトウェアとハードウェアの資産とその構成を記録しておきます。</span><span class="sxs-lookup"><span data-stu-id="cd741-130">Keep a record of your software and hardware assets and their configurations.</span></span>

  - <span data-ttu-id="cd741-131">**システム管理**   の概要データベース管理、サイト管理などの管理タスクを実行するための標準的な方法。</span><span class="sxs-lookup"><span data-stu-id="cd741-131">**System Administration**   Outline standard methods for doing administrative tasks such as database administration and site administration.</span></span>

  - <span data-ttu-id="cd741-132">**セキュリティ管理**   には、データの機密性、データの整合性、IT インフラストラクチャのデータ可用性を保護するための詳細なポリシーと計画が用意されています。</span><span class="sxs-lookup"><span data-stu-id="cd741-132">**Security Administration**   Have a detailed policy and plan that protects data confidentiality, data integrity, and data availability of the IT infrastructure.</span></span> <span data-ttu-id="cd741-133">これには、IT セキュリティインフラストラクチャの維持と調整に関連する日常的なアクティビティとタスクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cd741-133">This includes day-to-day activities and tasks that are related to maintaining and adjusting the IT security infrastructure.</span></span>

  - <span data-ttu-id="cd741-134">\*\*\*\*   将来の問題を回避するための手順など、予期しない問題を処理するためのシステムのトラブルシューティングのアウトライン方法。</span><span class="sxs-lookup"><span data-stu-id="cd741-134">**System Troubleshooting**   Outline methods for dealing with unexpected issues, including steps to prevent similar issues in the future.</span></span>

  - <span data-ttu-id="cd741-135">**サービスレベル契約**   は、IT システムのパフォーマンスに対する一連の目標を維持し、これらの目標に対するパフォーマンスを定期的に測定します。</span><span class="sxs-lookup"><span data-stu-id="cd741-135">**Service Level Agreements**   Maintain a set of goals for the performance of the IT systems and regularly measure performance against these goals.</span></span>

  - <span data-ttu-id="cd741-136">**ドキュメント**   ドキュメントの標準的な手順 (構成情報や教訓など) と、それを必要とするスタッフメンバーが利用できるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd741-136">**Documentation**   Document standard procedures, such as configuration information and lessons learned, and make them available to the staff members that need them.</span></span> <span data-ttu-id="cd741-137">構成の変更が行われると、それに合わせてドキュメントが更新されます。</span><span class="sxs-lookup"><span data-stu-id="cd741-137">As changes to the configuration are made, update the documentation accordingly.</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="cd741-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd741-138">Related Sections</span></span>

<span data-ttu-id="cd741-139">続行する前に、次のシステム操作に関するトピックを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cd741-139">Review the following topics concerning system operations before proceeding:</span></span>

  - [<span data-ttu-id="cd741-140">Lync Server 2013 での容量と可用性の管理</span><span class="sxs-lookup"><span data-stu-id="cd741-140">Capacity and availability management in Lync Server 2013</span></span>](lync-server-2013-capacity-and-availability-management.md)

  - [<span data-ttu-id="cd741-141">Lync Server 2013 で管理を変更する</span><span class="sxs-lookup"><span data-stu-id="cd741-141">Change management in Lync Server 2013</span></span>](lync-server-2013-change-management.md)

  - [<span data-ttu-id="cd741-142">Lync Server 2013 での構成管理</span><span class="sxs-lookup"><span data-stu-id="cd741-142">Configuration management in Lync Server 2013</span></span>](lync-server-2013-configuration-management.md)

  - [<span data-ttu-id="cd741-143">Lync Server 2013 でのシステム管理</span><span class="sxs-lookup"><span data-stu-id="cd741-143">System administration in Lync Server 2013</span></span>](lync-server-2013-system-administration.md)

  - [<span data-ttu-id="cd741-144">Lync Server 2013 のサービスレベル契約</span><span class="sxs-lookup"><span data-stu-id="cd741-144">Service level agreements in Lync Server 2013</span></span>](lync-server-2013-service-level-agreements.md)

  - [<span data-ttu-id="cd741-145">Lync Server 2013 のドキュメント</span><span class="sxs-lookup"><span data-stu-id="cd741-145">Documentation in Lync Server 2013</span></span>](lync-server-2013-documentation.md)

  - [<span data-ttu-id="cd741-146">Lync Server 2013 の標準手順</span><span class="sxs-lookup"><span data-stu-id="cd741-146">Standard procedures in Lync Server 2013</span></span>](lync-server-2013-standard-procedures.md)

  - [<span data-ttu-id="cd741-147">Lync Server 2013 の緊急対応手順</span><span class="sxs-lookup"><span data-stu-id="cd741-147">Emergency procedures in Lync Server 2013</span></span>](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cd741-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd741-148">See Also</span></span>


[<span data-ttu-id="cd741-149">Microsoft 運用フレームワーク4.0</span><span class="sxs-lookup"><span data-stu-id="cd741-149">Microsoft Operations Framework 4.0</span></span>](http://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

