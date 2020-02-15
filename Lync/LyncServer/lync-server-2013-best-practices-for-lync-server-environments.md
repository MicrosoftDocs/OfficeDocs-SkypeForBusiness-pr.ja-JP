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
ms.openlocfilehash: d02d9ed669cf9404b1bf8d07db32c9d331769ec9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-lync-server-2013-environments"></a><span data-ttu-id="c0d2d-102">Lync Server 2013 環境のベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="c0d2d-102">Best practices for Lync Server 2013 environments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0d2d-103">_**トピックの最終更新日:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="c0d2d-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="c0d2d-104">システムの実行中の操作には、次の一般的な原則を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-104">The following general principles should be applied to ongoing operations of your system:</span></span>

  - <span data-ttu-id="c0d2d-105">**Mof mof を理解して活用**   することは、ベストプラクティス、原則、およびモデルの集合であり、毎日の Lync Server 2013 操作などの IT 資産の管理に関する技術的なガイダンスを組織に提供します。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-105">**Understand and utilize MOF**   MOF is a collection of best practices, principles, and models that provide organizations technical guidance about the management of IT assets, such as daily Lync Server 2013 operations.</span></span> <span data-ttu-id="c0d2d-106">MOF の次のガイドラインは、Microsoft 製品のミッションクリティカルな運用システムの信頼性、可用性、サポート性、および管理性を実現するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-106">Following MOF guidelines can help you achieve mission-critical production system reliability, availability, supportability, and manageability for Microsoft products.</span></span> <span data-ttu-id="c0d2d-107">詳細については、「 [Microsoft Operations Framework 4.0](http://go.microsoft.com/fwlink/p/?linkid=40939)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-107">For more information, see [Microsoft Operations Framework 4.0](http://go.microsoft.com/fwlink/p/?linkid=40939).</span></span>

  - <span data-ttu-id="c0d2d-108">**Lync server 2013**   のベストプラクティスについて学習する lync server 2013 を管理するための実用的かつ実証済みの手順を実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-108">**Learn about best practices for Lync Server 2013**   We recommend that you implement practical and proven procedures to manage Lync Server 2013.</span></span> <span data-ttu-id="c0d2d-109">「試行」、「テスト済み」、およびドキュメントで文書化された操作を管理する方法は、独自の方法を開発するよりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-109">By using tried, tested, and documented methods of managing operations may be more efficient than developing your own methods.</span></span>

  - <span data-ttu-id="c0d2d-110">**毎日、毎週、および毎月のプロセス**   への個別の操作によって、定期的に実行する必要な運用タスクが文書化されます。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-110">**Separate operations into daily, weekly, and monthly processes**   Document the required operational tasks that you'll regularly perform.</span></span> <span data-ttu-id="c0d2d-111">タスクの実行方法を文書化することで、新しいテクノロジが展開されたときや、スタッフの変更が発生したときなど、運用環境に変更があった場合に、情報が確実に保持されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-111">Documenting how you perform tasks helps make sure that your information is preserved when there is a change in your operational environment such as when new technologies are deployed or staff changes occur.</span></span> <span data-ttu-id="c0d2d-112">タスクが毎日、毎週、毎月実行される管理可能なワークロードには、運用タスクを分離することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-112">We recommend that operational tasks be separated into manageable workloads where tasks are performed daily, weekly, and monthly.</span></span> <span data-ttu-id="c0d2d-113">日常のタスクでは、システムの機能に焦点を当てることができます。また、月単位のタスクでは、システムの長期的な正常性を確保することに重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-113">Daily tasks would focus efforts on the functioning of a system, and monthly tasks would focus more on ensuring the long-term health of a system.</span></span>
    
    <span data-ttu-id="c0d2d-114">このドキュメントは、エンタープライズ Voip を使用したインスタントメッセージング/プレゼンス (IM/P) コンポーネントまたは IM/P のみを展開する環境で使用できます。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-114">This document can be used in environments deploying only instant messaging/presence (IM/P) components or IM/P with Enterprise Voice.</span></span> <span data-ttu-id="c0d2d-115">タスクまたはチェックリストのアイテムがエンタープライズ Voip に固有のものである場合は、このことが説明されています。環境にエンタープライズ Voip が含まれていない場合は、部分をスキップすることができます。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-115">When tasks or checklist items are specific to Enterprise Voice, this is mentioned and if your environment does not include Enterprise Voice the portion may be skipped.</span></span>

  - <span data-ttu-id="c0d2d-116">**運用 lync server 2013**   に必要なツールを展開します。問題のトラブルシューティング、タスクの自動化、lync server 2013 環境の監視と管理に役立つツールが多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-116">**Deploy the tools that are required for operating Lync Server 2013**   Many tools are available to help troubleshoot issues, automate tasks, and help monitor and maintain the Lync Server 2013 environment.</span></span> <span data-ttu-id="c0d2d-117">組織に対して標準のツールセットを定義することで、運用チームによって実行されるタスクが正確かつ効率的に、一貫して、制御された方法で実行されるようになります。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-117">Define a standard set of tools for your organization so the tasks that are performed by the operations team are performed accurately, efficiently, consistently, and in a controlled manner.</span></span> <span data-ttu-id="c0d2d-118">また、インシデントおよび主要な構成の変更を追跡するためのプロセスも実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-118">You should also implement processes to track incidents and major configuration changes.</span></span>

<div>

## <a name="reference"></a><span data-ttu-id="c0d2d-119">リファレンス</span><span class="sxs-lookup"><span data-stu-id="c0d2d-119">Reference</span></span>

<span data-ttu-id="c0d2d-120">一般にサーバーの管理の基本事項を理解していない読者のために、サーバーの管理方法の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-120">For the benefit of readers not already familiar with the basics of server management in general, we provide an overview of server management practices.</span></span> <span data-ttu-id="c0d2d-121">サーバー管理に精通している読者は、このセクションをスキップすることを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-121">Readers already familiar with server management may choose to skip this section.</span></span>

<span data-ttu-id="c0d2d-122">ベストプラクティスは、IT 担当者が多くの環境で得た知識と経験に基づく推奨事項です。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-122">Best practices are recommendations that are based on the knowledge and experience that IT professionals have gained across many environments.</span></span> <span data-ttu-id="c0d2d-123">これらは、Lync Server 管理者が毎日実行する必要のある一般的なタスクの標準的な手順を提供し、Lync Server 環境の管理に使用する必要があるツールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-123">They provide standard procedures for typical tasks that your Lync Server administrators must perform daily, and list the tools that they should use to manage a Lync Server environment.</span></span>

<span data-ttu-id="c0d2d-124">Lync 管理者の一般的なタスクには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-124">Typical tasks for Lync administrators include the following:</span></span>

  - <span data-ttu-id="c0d2d-125">**キャパシティ/可用性管理**   は、今後の容量要件を予測し、システムの容量、信頼性、および可用性に関するレポートを作成するために、測定する方法と内容を定義します。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-125">**Capacity and Availability Management**   Define how and what to measure to predict future capacity requirements and to report about the capacity, reliability, and availability of your systems.</span></span> <span data-ttu-id="c0d2d-126">Lync Server を実行しているサーバーがシステムの負荷を処理するように設定されていること、および予定外のダウンタイムがサービスレベル契約 (SLA) で定義されているレベルの下に保持されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-126">You must verify that servers that are running Lync Server are sized to handle the load on the system, and that unplanned downtime is kept under the levels defined in the service level agreement (SLA).</span></span> <span data-ttu-id="c0d2d-127">さらに、定義された要件を引き続き満たすようにハードウェアをアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-127">Additionally, you'll have to upgrade hardware to continue to meet the defined requirements.</span></span>

  - <span data-ttu-id="c0d2d-128">**変更管理および構成管理**   によって、IT システムに加えられた変更の方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-128">**Change Management and Configuration Management**   Control how changes are made to IT systems.</span></span> <span data-ttu-id="c0d2d-129">これには、テスト、アプリケーションのフィードバックとコンティンジェンシー計画、すべての変更のドキュメント、および問題が発生した場合の管理からの承認を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-129">This should include testing, application feedback and contingency plans, documentation of all changes, and approval from management if issues occur.</span></span> <span data-ttu-id="c0d2d-130">ソフトウェアおよびハードウェアアセットとその構成の記録を保持します。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-130">Keep a record of your software and hardware assets and their configurations.</span></span>

  - <span data-ttu-id="c0d2d-131">**システム管理**   には、データベース管理、サイト管理などの管理タスクを実行するための標準的な方法があります。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-131">**System Administration**   Outline standard methods for doing administrative tasks such as database administration and site administration.</span></span>

  - <span data-ttu-id="c0d2d-132">**セキュリティ管理**   には、データの機密性、データの整合性、および IT インフラストラクチャのデータ可用性を保護するための詳細なポリシーと計画が用意されています。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-132">**Security Administration**   Have a detailed policy and plan that protects data confidentiality, data integrity, and data availability of the IT infrastructure.</span></span> <span data-ttu-id="c0d2d-133">これには、IT セキュリティインフラストラクチャのメンテナンスと調整に関連する日常業務とタスクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-133">This includes day-to-day activities and tasks that are related to maintaining and adjusting the IT security infrastructure.</span></span>

  - <span data-ttu-id="c0d2d-134">\*\*\*\*   将来的な問題を回避するための手順を含め、予期しない問題を処理するためのシステムトラブルシューティングのアウトライン方法。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-134">**System Troubleshooting**   Outline methods for dealing with unexpected issues, including steps to prevent similar issues in the future.</span></span>

  - <span data-ttu-id="c0d2d-135">**サービスレベルアグリーメント**   IT システムのパフォーマンスに関する一連の目標を維持し、これらの目標に対するパフォーマンスを定期的に測定します。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-135">**Service Level Agreements**   Maintain a set of goals for the performance of the IT systems and regularly measure performance against these goals.</span></span>

  - <span data-ttu-id="c0d2d-136">**ドキュメントドキュメントの**   標準的な手順 (構成情報や授業の教訓など) を参照し、それらを必要とするスタッフメンバーが使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-136">**Documentation**   Document standard procedures, such as configuration information and lessons learned, and make them available to the staff members that need them.</span></span> <span data-ttu-id="c0d2d-137">構成の変更が行われた後、ドキュメントを更新します。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-137">As changes to the configuration are made, update the documentation accordingly.</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="c0d2d-138">関連情報</span><span class="sxs-lookup"><span data-stu-id="c0d2d-138">Related Sections</span></span>

<span data-ttu-id="c0d2d-139">続行する前に、次のシステム操作に関するトピックを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c0d2d-139">Review the following topics concerning system operations before proceeding:</span></span>

  - [<span data-ttu-id="c0d2d-140">Lync Server 2013 での容量と可用性の管理</span><span class="sxs-lookup"><span data-stu-id="c0d2d-140">Capacity and availability management in Lync Server 2013</span></span>](lync-server-2013-capacity-and-availability-management.md)

  - [<span data-ttu-id="c0d2d-141">Lync Server 2013 での変更管理</span><span class="sxs-lookup"><span data-stu-id="c0d2d-141">Change management in Lync Server 2013</span></span>](lync-server-2013-change-management.md)

  - [<span data-ttu-id="c0d2d-142">Lync Server 2013 での構成管理</span><span class="sxs-lookup"><span data-stu-id="c0d2d-142">Configuration management in Lync Server 2013</span></span>](lync-server-2013-configuration-management.md)

  - [<span data-ttu-id="c0d2d-143">Lync Server 2013 のシステム管理</span><span class="sxs-lookup"><span data-stu-id="c0d2d-143">System administration in Lync Server 2013</span></span>](lync-server-2013-system-administration.md)

  - [<span data-ttu-id="c0d2d-144">Lync Server 2013 でのサービスレベル契約</span><span class="sxs-lookup"><span data-stu-id="c0d2d-144">Service level agreements in Lync Server 2013</span></span>](lync-server-2013-service-level-agreements.md)

  - [<span data-ttu-id="c0d2d-145">Lync Server 2013 のドキュメント</span><span class="sxs-lookup"><span data-stu-id="c0d2d-145">Documentation in Lync Server 2013</span></span>](lync-server-2013-documentation.md)

  - [<span data-ttu-id="c0d2d-146">Lync Server 2013 の標準手順</span><span class="sxs-lookup"><span data-stu-id="c0d2d-146">Standard procedures in Lync Server 2013</span></span>](lync-server-2013-standard-procedures.md)

  - [<span data-ttu-id="c0d2d-147">Lync Server 2013 の緊急時の手順</span><span class="sxs-lookup"><span data-stu-id="c0d2d-147">Emergency procedures in Lync Server 2013</span></span>](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c0d2d-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0d2d-148">See Also</span></span>


[<span data-ttu-id="c0d2d-149">Microsoft Operations Framework 4.0</span><span class="sxs-lookup"><span data-stu-id="c0d2d-149">Microsoft Operations Framework 4.0</span></span>](http://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

