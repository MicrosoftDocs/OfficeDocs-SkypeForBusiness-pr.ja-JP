---
title: 'Lync Server 2013: バックアップと復元の計画を立てる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Establishing a backup and restoration plan
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202183(v=OCS.15)
ms:contentKeyID: 51541499
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b3516e63a7cbada4a89fad3540406e38b299fef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a><span data-ttu-id="eaacb-102">Lync Server 2013 のバックアップと復元の計画を立てる</span><span class="sxs-lookup"><span data-stu-id="eaacb-102">Establishing a backup and restoration plan for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eaacb-103">_**最終更新日:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="eaacb-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="eaacb-104">バックアップと復元の計画を作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="eaacb-104">Creating a backup and restoration plan involves the following steps:</span></span>

  - <span data-ttu-id="eaacb-105">計画の策定。</span><span class="sxs-lookup"><span data-stu-id="eaacb-105">Developing the plan.</span></span>

  - <span data-ttu-id="eaacb-106">プランの実装。</span><span class="sxs-lookup"><span data-stu-id="eaacb-106">Implementing the plan.</span></span>

  - <span data-ttu-id="eaacb-107">計画を管理する。</span><span class="sxs-lookup"><span data-stu-id="eaacb-107">Maintaining the plan.</span></span>

<div>

## <a name="developing-a-backup-and-restoration-plan"></a><span data-ttu-id="eaacb-108">バックアップと復元の計画を作成する</span><span class="sxs-lookup"><span data-stu-id="eaacb-108">Developing a Backup and Restoration Plan</span></span>

<span data-ttu-id="eaacb-109">Lync Server のバックアップと復元戦略を開発したら、それを使用して、詳細なバックアップと復元計画を作成します。</span><span class="sxs-lookup"><span data-stu-id="eaacb-109">After you develop your backup and restoration strategy for Lync Server, use it to document a detailed backup and restoration plan.</span></span> <span data-ttu-id="eaacb-110">プランでは、データと設定をバックアップするための優先度と要件を明確に伝える必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaacb-110">Your plan should clearly convey the priorities and requirements for backing up data and settings.</span></span> <span data-ttu-id="eaacb-111">「 [Lync server 2013 のバックアップと復元の戦略を立てる](lync-server-2013-establishing-a-backup-and-restoration-strategy.md)」および「 [lync Server 2013 のバックアップと復元ワークシート](lync-server-2013-backup-and-restoration-worksheets.md)のワークシートを作成する」の情報を使用して、戦略の文書化を容易にすることができます。</span><span class="sxs-lookup"><span data-stu-id="eaacb-111">You can use the information in [Establishing a backup and restoration strategy for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) and the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) to facilitate the documentation of your strategy.</span></span> <span data-ttu-id="eaacb-112">プランには、サービスを復元するタイミングと方法を決定するための条件も含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaacb-112">Your plan should also contain criteria for deciding when and how to restore service.</span></span>

<span data-ttu-id="eaacb-113">計画を立てるときは、次のことを考慮し、考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaacb-113">As you develop your plan, you need to consider, and account for, the following:</span></span>

  - <span data-ttu-id="eaacb-114">新しいハードウェアでサーバーを回復する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="eaacb-114">How you will recover servers on new hardware.</span></span>

  - <span data-ttu-id="eaacb-115">複数のビジネス領域または部門の一部に対してアクションを必要とするサービスを回復する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="eaacb-115">How you will recover services that require action on the part of multiple business areas or departments.</span></span>

  - <span data-ttu-id="eaacb-116">予備サーバーをすばやく入手する方法をご紹介します。</span><span class="sxs-lookup"><span data-stu-id="eaacb-116">How you can acquire spare servers quickly.</span></span>

  - <span data-ttu-id="eaacb-117">戦略を使用して回復するのにかかる時間。</span><span class="sxs-lookup"><span data-stu-id="eaacb-117">The time it takes to recover by using your strategy.</span></span> <span data-ttu-id="eaacb-118">Rpo (目標復旧時間) に関する組織の要件を検討してください。</span><span class="sxs-lookup"><span data-stu-id="eaacb-118">Consider your organization’s requirements for recovery time objective (RTO).</span></span>

<span data-ttu-id="eaacb-119">このトピックのバックアップと復元の手順を変更します。必要に応じて手順を追加および削除して、展開のサーバーとコンポーネントを反映させます。</span><span class="sxs-lookup"><span data-stu-id="eaacb-119">Modify the backup and restoration procedures in this topic, adding and deleting procedures as appropriate, to reflect the servers and components in your deployment.</span></span> <span data-ttu-id="eaacb-120">また、バックアップスケジュールなどの適切な詳細を適切な手順に追加して、情報が見落とされないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="eaacb-120">You can also add appropriate details, such as the backup schedule, to the appropriate procedures to make sure that the information is not overlooked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eaacb-121">手順の品質と再現性を向上させるために、できるだけ多くの手順を実行するようにスクリプトを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="eaacb-121">It is good practice to create scripts for as many steps as possible, to help ensure the quality and reproducibility of procedures.</span></span>



</div>

<span data-ttu-id="eaacb-122">計画で、新しい手順やツールのテストと検証を担当する担当者、および計画および関連する手順への変更を承認する必要があるユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="eaacb-122">In your plan, specify who is responsible for reviewing the plan, who is responsible for testing and validating any new procedures or tools, and who must approve any changes to the plan and related procedures.</span></span>

<span data-ttu-id="eaacb-123">バックアップと復元の計画が、設定されたすべての目標と優先順位を満たしていることを確認するために、計画を実装する前に、組織内の適切なビジネス上の意思決定者と技術上の意思決定者の承認を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaacb-123">To make sure that your backup and restoration plan fully meets all established goals and priorities, get the approval of the appropriate business decision makers and technical decision makers in your organization before you implement the plan.</span></span>

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a><span data-ttu-id="eaacb-124">バックアップと復元の計画の実装</span><span class="sxs-lookup"><span data-stu-id="eaacb-124">Implementing the Backup and Restoration Plan</span></span>

<span data-ttu-id="eaacb-125">バックアップと復元の計画を実装するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaacb-125">Implementing a backup and restoration plan requires the following steps:</span></span>

  - <span data-ttu-id="eaacb-126">プランのテストと検証。</span><span class="sxs-lookup"><span data-stu-id="eaacb-126">Testing and validating the plan.</span></span>

  - <span data-ttu-id="eaacb-127">プランを連絡しています。</span><span class="sxs-lookup"><span data-stu-id="eaacb-127">Communicating the plan.</span></span>

  - <span data-ttu-id="eaacb-128">バックアップと復元の操作を検証する。</span><span class="sxs-lookup"><span data-stu-id="eaacb-128">Validating backup and restoration operations.</span></span>

<div>

## <a name="testing-and-validating-the-plan"></a><span data-ttu-id="eaacb-129">プランのテストと検証</span><span class="sxs-lookup"><span data-stu-id="eaacb-129">Testing and Validating the Plan</span></span>

<span data-ttu-id="eaacb-130">ここで説明する手順は、ラボ環境でテストおよび検証されています。</span><span class="sxs-lookup"><span data-stu-id="eaacb-130">The procedures described here have been tested and validated in a lab environment.</span></span> <span data-ttu-id="eaacb-131">これらの手順またはその他の手順を環境で確実に使用できるようにするには、実装する各プロシージャをテストして検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaacb-131">To make sure that these or any other procedures work in your environment, you should test and validate each procedure you intend to implement.</span></span> <span data-ttu-id="eaacb-132">最終的な承認を得るために、計画を提出する前に、テストと検証を完了します。</span><span class="sxs-lookup"><span data-stu-id="eaacb-132">Complete the testing and the validation before you submit your plan for final approval.</span></span>

</div>

<div>

## <a name="communicating-the-plan"></a><span data-ttu-id="eaacb-133">プランの伝達</span><span class="sxs-lookup"><span data-stu-id="eaacb-133">Communicating the Plan</span></span>

<span data-ttu-id="eaacb-134">バックアップと復元の計画では、手順を実装する担当者と手順を実行するための詳しい手順について明確に説明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaacb-134">Your backup and restoration plan should clearly describe who implements procedures and step-by-step instructions for carrying out the procedures.</span></span> <span data-ttu-id="eaacb-135">バックアップと復元について責任を持つすべてのユーザーが、計画、実装方法、およびロールの意味を理解していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaacb-135">You should make sure that everyone responsible for any aspect of backup and restoration understands the plan, how it is to be implemented, and what their role is.</span></span> <span data-ttu-id="eaacb-136">これには、次のようなすべての実装要件が含まれます。</span><span class="sxs-lookup"><span data-stu-id="eaacb-136">This includes all implementation requirements for the following:</span></span>

  - <span data-ttu-id="eaacb-137">プールとサーバのバックアップ。</span><span class="sxs-lookup"><span data-stu-id="eaacb-137">Pool and server backup.</span></span>

  - <span data-ttu-id="eaacb-138">サービスの復元。</span><span class="sxs-lookup"><span data-stu-id="eaacb-138">Restoration of service.</span></span>

<span data-ttu-id="eaacb-139">**プールとサーバーのバックアップ**</span><span class="sxs-lookup"><span data-stu-id="eaacb-139">**Pool and server backup**</span></span>

<span data-ttu-id="eaacb-140">バックアップと復元の計画には、進捗状況に応じてバックアップ手順を完了するために必要なすべての情報を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaacb-140">The backup and restoration plan should include all information required to complete backup procedures on an ongoing basis.</span></span> <span data-ttu-id="eaacb-141">責任のあるチームメンバーに伝達されるプライマリ情報には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="eaacb-141">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="eaacb-142">各サーバーのバックアップを担当する (個人または役割として指定された) チームまたは人物。</span><span class="sxs-lookup"><span data-stu-id="eaacb-142">Team or person (specified as an individual or role) responsible for backing up each server.</span></span>

  - <span data-ttu-id="eaacb-143">各サーバーをバックアップするための特定のスケジュール。</span><span class="sxs-lookup"><span data-stu-id="eaacb-143">Specific schedules for backing up each server.</span></span>

  - <span data-ttu-id="eaacb-144">データの種類 (設定、データベース、ファイル共有) ごとにバックアップ場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="eaacb-144">Backup locations for each type of data (settings, database, and file shares).</span></span>

  - <span data-ttu-id="eaacb-145">使用するバックアップ手順。各手順を完了するために必要なツールも含まれます。</span><span class="sxs-lookup"><span data-stu-id="eaacb-145">Backup procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="eaacb-146">バックアップの完了に必要な情報。 [Lync Server 2013 のバックアップと復元ワークシート](lync-server-2013-backup-and-restoration-worksheets.md)に記載されています。</span><span class="sxs-lookup"><span data-stu-id="eaacb-146">Information required to complete backups, as covered in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="eaacb-147">データと設定が適切にバックアップされ、復元のために使用できるようにするために使用される検証方法。定期的な監査とテスト用復元を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="eaacb-147">Validation methods to be used to help ensure that data and settings are appropriately backed up and available for restoration, which can include periodic audits and test restorations.</span></span>

<span data-ttu-id="eaacb-148">**サービスの復元**</span><span class="sxs-lookup"><span data-stu-id="eaacb-148">**Restoration of service**</span></span>

<span data-ttu-id="eaacb-149">バックアップと復元の計画には、サービスを復元するために必要なすべての情報が含まれている必要があります。1つまたは複数のサーバーでサービスを利用できないという損失が発生する場合。</span><span class="sxs-lookup"><span data-stu-id="eaacb-149">The backup and restoration plan should include all information required to restore service, in case one or more servers experience a loss that makes service unavailable.</span></span> <span data-ttu-id="eaacb-150">責任のあるチームメンバーに伝達されるプライマリ情報には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="eaacb-150">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="eaacb-151">サービスの復元が必要であるかどうかを判断する責任を負うチームまたは人物 (個人または役割として指定) と、サービスの復元に使用する手順、およびそれぞれの手順の実装を担当するチームまたはユーザー復元シナリオ。</span><span class="sxs-lookup"><span data-stu-id="eaacb-151">Team or person (specified as an individual or a role) that is responsible for determining when restoration of service is required and the procedures to be used to restore service, and also the team or person responsible for implementing procedures for each restoration scenario.</span></span>

  - <span data-ttu-id="eaacb-152">特定の状況に最も適した復元手順を決定するための条件。</span><span class="sxs-lookup"><span data-stu-id="eaacb-152">Criteria for determining which restoration procedures are most appropriate for a specific situation.</span></span>

  - <span data-ttu-id="eaacb-153">各復元シナリオのサービスと復元時間の目標 (RTO) を復元する時間の見積もり。</span><span class="sxs-lookup"><span data-stu-id="eaacb-153">Time estimates for restoration of service and recovery time objective (RTO) in each restoration scenario.</span></span>

  - <span data-ttu-id="eaacb-154">使用する復元手順。各手順を完了するために必要なツールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="eaacb-154">Restoration procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="eaacb-155">データと設定を復元するために必要な情報。</span><span class="sxs-lookup"><span data-stu-id="eaacb-155">Information required to restore data and settings.</span></span> <span data-ttu-id="eaacb-156">ワークシートは[、Lync Server 2013 のバックアップと復元ワークシート](lync-server-2013-backup-and-restoration-worksheets.md)に用意されています。</span><span class="sxs-lookup"><span data-stu-id="eaacb-156">Worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a><span data-ttu-id="eaacb-157">バックアップと復元の操作を検証する</span><span class="sxs-lookup"><span data-stu-id="eaacb-157">Validating Backup and Restoration Operations</span></span>

<span data-ttu-id="eaacb-158">実稼働環境での最初のバックアップ作業を完了した後、指定した間隔 (バックアップと復元計画に記載) を行った後、次のことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaacb-158">After completing initial backup efforts in your production environment and at specified intervals (as covered in your backup and restoration plan), you should verify the following:</span></span>

  - <span data-ttu-id="eaacb-159">必要に応じてバックアップが行われます。</span><span class="sxs-lookup"><span data-stu-id="eaacb-159">Backups are occurring as required.</span></span>

  - <span data-ttu-id="eaacb-160">バックアップされたデータと設定にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="eaacb-160">Backed-up data and settings are accessible.</span></span>

  - <span data-ttu-id="eaacb-161">復元手順は、バックアップと復元計画で指定された RTO (目標復旧時間) 内で実行でき、結果はすべてのビジネス要件を満たしています。</span><span class="sxs-lookup"><span data-stu-id="eaacb-161">Restoration procedures can be performed within the recovery time objective (RTO) times specified in the backup and restoration plan, and the results meet all business requirements.</span></span>

  - <span data-ttu-id="eaacb-162">バックアップワークシートが完成し、確認され、安全な場所に保存されている。</span><span class="sxs-lookup"><span data-stu-id="eaacb-162">Backup worksheets have been completed and verified, and they are stored in a secure location.</span></span> <span data-ttu-id="eaacb-163">以下のワークシートは[、Lync Server 2013 のバックアップと復元ワークシート](lync-server-2013-backup-and-restoration-worksheets.md)に用意されています。</span><span class="sxs-lookup"><span data-stu-id="eaacb-163">These worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="eaacb-164">復元手順は、バックアップと復元計画で指定されているように、予想どおりに動作することがテストされています。</span><span class="sxs-lookup"><span data-stu-id="eaacb-164">Restoration procedures have been tested and verified to work as expected, as specified in your backup and restoration plan.</span></span>

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a><span data-ttu-id="eaacb-165">バックアップと復元の計画の管理</span><span class="sxs-lookup"><span data-stu-id="eaacb-165">Maintaining the Backup and Restoration Plan</span></span>

<span data-ttu-id="eaacb-166">Lync Server トポロジは、組織によって変化する動的な環境です。</span><span class="sxs-lookup"><span data-stu-id="eaacb-166">A Lync Server topology is a dynamic environment that changes with your organization.</span></span> <span data-ttu-id="eaacb-167">組織の変更に応じてバックアップと復元の計画を再評価し、定期的にレビューして、ビジネスニーズを確実に満たすことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="eaacb-167">Reassess your backup and restoration plan as your organization changes, and review it periodically to make sure that it continues to meet the needs of your business.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

