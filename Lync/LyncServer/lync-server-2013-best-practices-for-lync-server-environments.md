---
title: 'Lync Server 2013: Lync Server 環境のベストプラクティス'
description: 'Lync Server 2013: Lync Server 環境のベストプラクティス'
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
ms.openlocfilehash: ae6c02621bd6506d2a1d379aeaf92b20ce3f7ae1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552213"
---
# <a name="best-practices-for-lync-server-2013-environments"></a><span data-ttu-id="3c6f8-103">Lync Server 2013 環境のベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="3c6f8-103">Best practices for Lync Server 2013 environments</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c6f8-104">_**トピックの最終更新日:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="3c6f8-104">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="3c6f8-105">システムの実行中の操作には、次の一般的な原則を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-105">The following general principles should be applied to ongoing operations of your system:</span></span>

  - <span data-ttu-id="3c6f8-106">MOF を理解**して活用**     するMOF は、ベストプラクティス、原則、およびモデルの集合であり、毎日の Lync Server 2013 操作などの IT 資産の管理に関する技術的なガイダンスを組織に提供します。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-106">**Understand and utilize MOF**   MOF is a collection of best practices, principles, and models that provide organizations technical guidance about the management of IT assets, such as daily Lync Server 2013 operations.</span></span> <span data-ttu-id="3c6f8-107">MOF の次のガイドラインは、Microsoft 製品のミッションクリティカルな運用システムの信頼性、可用性、サポート性、および管理性を実現するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-107">Following MOF guidelines can help you achieve mission-critical production system reliability, availability, supportability, and manageability for Microsoft products.</span></span> <span data-ttu-id="3c6f8-108">詳細については、「 [Microsoft Operations Framework 4.0](https://go.microsoft.com/fwlink/p/?linkid=40939)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-108">For more information, see [Microsoft Operations Framework 4.0](https://go.microsoft.com/fwlink/p/?linkid=40939).</span></span>

  - <span data-ttu-id="3c6f8-109">**Lync Server 2013 のベストプラクティスについて説明**     します。Lync Server 2013 を管理するための実用的かつ実証済みの手順を実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-109">**Learn about best practices for Lync Server 2013**   We recommend that you implement practical and proven procedures to manage Lync Server 2013.</span></span> <span data-ttu-id="3c6f8-110">「試行」、「テスト済み」、およびドキュメントで文書化された操作を管理する方法は、独自の方法を開発するよりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-110">By using tried, tested, and documented methods of managing operations may be more efficient than developing your own methods.</span></span>

  - <span data-ttu-id="3c6f8-111">**個別の操作を日単位、週単位、および月単位のプロセス**     に分けます。定期的に実行する必要な運用タスクを文書化します。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-111">**Separate operations into daily, weekly, and monthly processes**   Document the required operational tasks that you'll regularly perform.</span></span> <span data-ttu-id="3c6f8-112">タスクの実行方法を文書化することで、新しいテクノロジが展開されたときや、スタッフの変更が発生したときなど、運用環境に変更があった場合に、情報が確実に保持されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-112">Documenting how you perform tasks helps make sure that your information is preserved when there is a change in your operational environment such as when new technologies are deployed or staff changes occur.</span></span> <span data-ttu-id="3c6f8-113">タスクが毎日、毎週、毎月実行される管理可能なワークロードには、運用タスクを分離することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-113">We recommend that operational tasks be separated into manageable workloads where tasks are performed daily, weekly, and monthly.</span></span> <span data-ttu-id="3c6f8-114">日常のタスクでは、システムの機能に焦点を当てることができます。また、月単位のタスクでは、システムの長期的な正常性を確保することに重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-114">Daily tasks would focus efforts on the functioning of a system, and monthly tasks would focus more on ensuring the long-term health of a system.</span></span>
    
    <span data-ttu-id="3c6f8-115">このドキュメントは、エンタープライズ Voip を使用したインスタントメッセージング/プレゼンス (IM/P) コンポーネントまたは IM/P のみを展開する環境で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-115">This document can be used in environments deploying only instant messaging/presence (IM/P) components or IM/P with Enterprise Voice.</span></span> <span data-ttu-id="3c6f8-116">タスクまたはチェックリストのアイテムがエンタープライズ Voip に固有のものである場合は、このことが説明されています。環境にエンタープライズ Voip が含まれていない場合は、部分をスキップすることができます。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-116">When tasks or checklist items are specific to Enterprise Voice, this is mentioned and if your environment does not include Enterprise Voice the portion may be skipped.</span></span>

  - <span data-ttu-id="3c6f8-117">**Lync Server 2013**     の運用に必要なツールを展開するさまざまなツールを使用して、問題のトラブルシューティングを行ったり、タスクを自動化したり、Lync Server 2013 環境の監視および保守に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-117">**Deploy the tools that are required for operating Lync Server 2013**   Many tools are available to help troubleshoot issues, automate tasks, and help monitor and maintain the Lync Server 2013 environment.</span></span> <span data-ttu-id="3c6f8-118">組織に対して標準のツールセットを定義することで、運用チームによって実行されるタスクが正確かつ効率的に、一貫して、制御された方法で実行されるようになります。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-118">Define a standard set of tools for your organization so the tasks that are performed by the operations team are performed accurately, efficiently, consistently, and in a controlled manner.</span></span> <span data-ttu-id="3c6f8-119">また、インシデントおよび主要な構成の変更を追跡するためのプロセスも実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-119">You should also implement processes to track incidents and major configuration changes.</span></span>

<div>

## <a name="reference"></a><span data-ttu-id="3c6f8-120">リファレンス</span><span class="sxs-lookup"><span data-stu-id="3c6f8-120">Reference</span></span>

<span data-ttu-id="3c6f8-121">一般にサーバーの管理の基本事項を理解していない読者のために、サーバーの管理方法の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-121">For the benefit of readers not already familiar with the basics of server management in general, we provide an overview of server management practices.</span></span> <span data-ttu-id="3c6f8-122">サーバー管理に精通している読者は、このセクションをスキップすることを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-122">Readers already familiar with server management may choose to skip this section.</span></span>

<span data-ttu-id="3c6f8-123">ベストプラクティスは、IT 担当者が多くの環境で得た知識と経験に基づく推奨事項です。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-123">Best practices are recommendations that are based on the knowledge and experience that IT professionals have gained across many environments.</span></span> <span data-ttu-id="3c6f8-124">これらは、Lync Server 管理者が毎日実行する必要のある一般的なタスクの標準的な手順を提供し、Lync Server 環境の管理に使用する必要があるツールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-124">They provide standard procedures for typical tasks that your Lync Server administrators must perform daily, and list the tools that they should use to manage a Lync Server environment.</span></span>

<span data-ttu-id="3c6f8-125">Lync 管理者の一般的なタスクには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-125">Typical tasks for Lync administrators include the following:</span></span>

  - <span data-ttu-id="3c6f8-126">**容量と可用性の管理**    今後の容量要件を予測し、システムの容量、信頼性、および可用性に関するレポートを作成するために、測定する方法と内容を定義します。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-126">**Capacity and Availability Management**   Define how and what to measure to predict future capacity requirements and to report about the capacity, reliability, and availability of your systems.</span></span> <span data-ttu-id="3c6f8-127">Lync Server を実行しているサーバーがシステムの負荷を処理するように設定されていること、および予定外のダウンタイムがサービスレベル契約 (SLA) で定義されているレベルの下に保持されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-127">You must verify that servers that are running Lync Server are sized to handle the load on the system, and that unplanned downtime is kept under the levels defined in the service level agreement (SLA).</span></span> <span data-ttu-id="3c6f8-128">さらに、定義された要件を引き続き満たすようにハードウェアをアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-128">Additionally, you'll have to upgrade hardware to continue to meet the defined requirements.</span></span>

  - <span data-ttu-id="3c6f8-129">**変更管理および構成管理**    IT システムに加えられた変更を制御します。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-129">**Change Management and Configuration Management**   Control how changes are made to IT systems.</span></span> <span data-ttu-id="3c6f8-130">これには、テスト、アプリケーションのフィードバックとコンティンジェンシー計画、すべての変更のドキュメント、および問題が発生した場合の管理からの承認を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-130">This should include testing, application feedback and contingency plans, documentation of all changes, and approval from management if issues occur.</span></span> <span data-ttu-id="3c6f8-131">ソフトウェアおよびハードウェアアセットとその構成の記録を保持します。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-131">Keep a record of your software and hardware assets and their configurations.</span></span>

  - <span data-ttu-id="3c6f8-132">**システム管理**    データベース管理、サイト管理などの管理タスクを実行するための標準的な方法の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-132">**System Administration**   Outline standard methods for doing administrative tasks such as database administration and site administration.</span></span>

  - <span data-ttu-id="3c6f8-133">**セキュリティ管理**    データの機密性、データの整合性、および IT インフラストラクチャのデータ可用性を保護するための詳細なポリシーと計画を立てます。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-133">**Security Administration**   Have a detailed policy and plan that protects data confidentiality, data integrity, and data availability of the IT infrastructure.</span></span> <span data-ttu-id="3c6f8-134">これには、IT セキュリティインフラストラクチャのメンテナンスと調整に関連する日常業務とタスクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-134">This includes day-to-day activities and tasks that are related to maintaining and adjusting the IT security infrastructure.</span></span>

  - <span data-ttu-id="3c6f8-135">**システムのトラブルシューティング**    今後同様の問題が発生しないようにするための手順を含む、予期しない問題を処理するためのアウトライン方法。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-135">**System Troubleshooting**   Outline methods for dealing with unexpected issues, including steps to prevent similar issues in the future.</span></span>

  - <span data-ttu-id="3c6f8-136">**サービスレベル契約**    IT システムのパフォーマンスに関する一連の目標を維持し、これらの目標に対するパフォーマンスを定期的に測定します。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-136">**Service Level Agreements**   Maintain a set of goals for the performance of the IT systems and regularly measure performance against these goals.</span></span>

  - <span data-ttu-id="3c6f8-137">**ドキュメント**    構成情報や教訓など、標準的な手順をドキュメント化し、それらを必要とするスタッフメンバーが使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-137">**Documentation**   Document standard procedures, such as configuration information and lessons learned, and make them available to the staff members that need them.</span></span> <span data-ttu-id="3c6f8-138">構成の変更が行われた後、ドキュメントを更新します。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-138">As changes to the configuration are made, update the documentation accordingly.</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="3c6f8-139">関連情報</span><span class="sxs-lookup"><span data-stu-id="3c6f8-139">Related Sections</span></span>

<span data-ttu-id="3c6f8-140">続行する前に、次のシステム操作に関するトピックを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3c6f8-140">Review the following topics concerning system operations before proceeding:</span></span>

  - [<span data-ttu-id="3c6f8-141">Lync Server 2013 での容量と可用性の管理</span><span class="sxs-lookup"><span data-stu-id="3c6f8-141">Capacity and availability management in Lync Server 2013</span></span>](lync-server-2013-capacity-and-availability-management.md)

  - [<span data-ttu-id="3c6f8-142">Lync Server 2013 での変更管理</span><span class="sxs-lookup"><span data-stu-id="3c6f8-142">Change management in Lync Server 2013</span></span>](lync-server-2013-change-management.md)

  - [<span data-ttu-id="3c6f8-143">Lync Server 2013 での構成管理</span><span class="sxs-lookup"><span data-stu-id="3c6f8-143">Configuration management in Lync Server 2013</span></span>](lync-server-2013-configuration-management.md)

  - [<span data-ttu-id="3c6f8-144">Lync Server 2013 のシステム管理</span><span class="sxs-lookup"><span data-stu-id="3c6f8-144">System administration in Lync Server 2013</span></span>](lync-server-2013-system-administration.md)

  - [<span data-ttu-id="3c6f8-145">Lync Server 2013 でのサービスレベル契約</span><span class="sxs-lookup"><span data-stu-id="3c6f8-145">Service level agreements in Lync Server 2013</span></span>](lync-server-2013-service-level-agreements.md)

  - [<span data-ttu-id="3c6f8-146">Lync Server 2013 のドキュメント</span><span class="sxs-lookup"><span data-stu-id="3c6f8-146">Documentation in Lync Server 2013</span></span>](lync-server-2013-documentation.md)

  - [<span data-ttu-id="3c6f8-147">Lync Server 2013 の標準手順</span><span class="sxs-lookup"><span data-stu-id="3c6f8-147">Standard procedures in Lync Server 2013</span></span>](lync-server-2013-standard-procedures.md)

  - [<span data-ttu-id="3c6f8-148">Lync Server 2013 の緊急時の手順</span><span class="sxs-lookup"><span data-stu-id="3c6f8-148">Emergency procedures in Lync Server 2013</span></span>](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3c6f8-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c6f8-149">See Also</span></span>


[<span data-ttu-id="3c6f8-150">Microsoft Operations Framework 4.0</span><span class="sxs-lookup"><span data-stu-id="3c6f8-150">Microsoft Operations Framework 4.0</span></span>](https://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

