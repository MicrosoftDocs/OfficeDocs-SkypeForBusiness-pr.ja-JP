---
title: 'Lync Server 2013: バックアップと復元の計画を立てる'
description: 'Lync Server 2013: バックアップと復元の計画を確立します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration plan
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202183(v=OCS.15)
ms:contentKeyID: 51541499
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06d93c713364bf6b5f230b255b68a2c1dfe1d04a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555053"
---
# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a><span data-ttu-id="d02a0-103">Lync Server 2013 のバックアップと復元の計画を立てる</span><span class="sxs-lookup"><span data-stu-id="d02a0-103">Establishing a backup and restoration plan for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d02a0-104">_**トピックの最終更新日:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="d02a0-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="d02a0-105">バックアップと復元の計画を作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d02a0-105">Creating a backup and restoration plan involves the following steps:</span></span>

  - <span data-ttu-id="d02a0-106">プランを作成します。</span><span class="sxs-lookup"><span data-stu-id="d02a0-106">Developing the plan.</span></span>

  - <span data-ttu-id="d02a0-107">プランを実装します。</span><span class="sxs-lookup"><span data-stu-id="d02a0-107">Implementing the plan.</span></span>

  - <span data-ttu-id="d02a0-108">計画を維持します。</span><span class="sxs-lookup"><span data-stu-id="d02a0-108">Maintaining the plan.</span></span>

<div>

## <a name="developing-a-backup-and-restoration-plan"></a><span data-ttu-id="d02a0-109">バックアップと復元の計画を作成する</span><span class="sxs-lookup"><span data-stu-id="d02a0-109">Developing a Backup and Restoration Plan</span></span>

<span data-ttu-id="d02a0-110">Lync Server のバックアップと復元の戦略を作成したら、それを使用して詳細なバックアップと復元の計画を文書化します。</span><span class="sxs-lookup"><span data-stu-id="d02a0-110">After you develop your backup and restoration strategy for Lync Server, use it to document a detailed backup and restoration plan.</span></span> <span data-ttu-id="d02a0-111">プランでは、データと設定のバックアップに関する優先順位と要件を明確に伝える必要があります。</span><span class="sxs-lookup"><span data-stu-id="d02a0-111">Your plan should clearly convey the priorities and requirements for backing up data and settings.</span></span> <span data-ttu-id="d02a0-112">「Lync server [2013 のバックアップと](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) 復元の戦略の確立」および「 [lync Server 2013 のバックアップと復元](lync-server-2013-backup-and-restoration-worksheets.md) のワークシート」の情報を使用して、戦略のドキュメントを容易に確認できます。</span><span class="sxs-lookup"><span data-stu-id="d02a0-112">You can use the information in [Establishing a backup and restoration strategy for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) and the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) to facilitate the documentation of your strategy.</span></span> <span data-ttu-id="d02a0-113">プランには、サービスをいつどのように復元するかを決定するための基準も含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d02a0-113">Your plan should also contain criteria for deciding when and how to restore service.</span></span>

<span data-ttu-id="d02a0-114">計画を策定する際には、次のことを考慮し、考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d02a0-114">As you develop your plan, you need to consider, and account for, the following:</span></span>

  - <span data-ttu-id="d02a0-115">新しいハードウェア上のサーバーを復元する方法。</span><span class="sxs-lookup"><span data-stu-id="d02a0-115">How you will recover servers on new hardware.</span></span>

  - <span data-ttu-id="d02a0-116">複数のビジネス領域または部署の一部に対するアクションを必要とするサービスをどのように復旧するか。</span><span class="sxs-lookup"><span data-stu-id="d02a0-116">How you will recover services that require action on the part of multiple business areas or departments.</span></span>

  - <span data-ttu-id="d02a0-117">予備サーバーを迅速に取得する方法。</span><span class="sxs-lookup"><span data-stu-id="d02a0-117">How you can acquire spare servers quickly.</span></span>

  - <span data-ttu-id="d02a0-118">戦略を使用して回復するのにかかる時間。</span><span class="sxs-lookup"><span data-stu-id="d02a0-118">The time it takes to recover by using your strategy.</span></span> <span data-ttu-id="d02a0-119">組織の目標復旧時間 (RTO) について検討してください。</span><span class="sxs-lookup"><span data-stu-id="d02a0-119">Consider your organization’s requirements for recovery time objective (RTO).</span></span>

<span data-ttu-id="d02a0-120">このトピックのバックアップと復元の手順を変更し、必要に応じて手順を追加および削除して、展開内のサーバーとコンポーネントを反映します。</span><span class="sxs-lookup"><span data-stu-id="d02a0-120">Modify the backup and restoration procedures in this topic, adding and deleting procedures as appropriate, to reflect the servers and components in your deployment.</span></span> <span data-ttu-id="d02a0-121">また、バックアップスケジュールなどの適切な詳細を適切な手順に追加して、情報が見落とされないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d02a0-121">You can also add appropriate details, such as the backup schedule, to the appropriate procedures to make sure that the information is not overlooked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d02a0-122">手順の品質と再現性を確保するために、可能な限り多くの手順用にスクリプトを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d02a0-122">It is good practice to create scripts for as many steps as possible, to help ensure the quality and reproducibility of procedures.</span></span>



</div>

<span data-ttu-id="d02a0-123">プランでは、計画をレビューする担当者、新しい手順やツールをテストして検証する担当者、および計画および関連する手順に対する変更を承認する必要がある人物を指定します。</span><span class="sxs-lookup"><span data-stu-id="d02a0-123">In your plan, specify who is responsible for reviewing the plan, who is responsible for testing and validating any new procedures or tools, and who must approve any changes to the plan and related procedures.</span></span>

<span data-ttu-id="d02a0-124">バックアップと復元の計画が、定められたすべての目標および優先順位を完全に満たしていることを確認するには、計画を実施する前に、組織内の適切なビジネス意思決定者と技術職意思決定者の承認を得ます。</span><span class="sxs-lookup"><span data-stu-id="d02a0-124">To make sure that your backup and restoration plan fully meets all established goals and priorities, get the approval of the appropriate business decision makers and technical decision makers in your organization before you implement the plan.</span></span>

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a><span data-ttu-id="d02a0-125">バックアップと復元の計画の実装</span><span class="sxs-lookup"><span data-stu-id="d02a0-125">Implementing the Backup and Restoration Plan</span></span>

<span data-ttu-id="d02a0-126">バックアップと復元の計画を実施するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d02a0-126">Implementing a backup and restoration plan requires the following steps:</span></span>

  - <span data-ttu-id="d02a0-127">計画をテストし、検証します。</span><span class="sxs-lookup"><span data-stu-id="d02a0-127">Testing and validating the plan.</span></span>

  - <span data-ttu-id="d02a0-128">プランを連絡する。</span><span class="sxs-lookup"><span data-stu-id="d02a0-128">Communicating the plan.</span></span>

  - <span data-ttu-id="d02a0-129">バックアップと復元の操作を検証します。</span><span class="sxs-lookup"><span data-stu-id="d02a0-129">Validating backup and restoration operations.</span></span>

<div>

## <a name="testing-and-validating-the-plan"></a><span data-ttu-id="d02a0-130">プランのテストと検証</span><span class="sxs-lookup"><span data-stu-id="d02a0-130">Testing and Validating the Plan</span></span>

<span data-ttu-id="d02a0-131">ここで説明する手順は、ラボ環境でテストおよび検証されています。</span><span class="sxs-lookup"><span data-stu-id="d02a0-131">The procedures described here have been tested and validated in a lab environment.</span></span> <span data-ttu-id="d02a0-132">これらの手順またはその他の手順が環境内で動作することを確認するには、実装する各手順をテストして検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d02a0-132">To make sure that these or any other procedures work in your environment, you should test and validate each procedure you intend to implement.</span></span> <span data-ttu-id="d02a0-133">最終的な承認を得るために、計画を提出する前に、テストと検証を完了します。</span><span class="sxs-lookup"><span data-stu-id="d02a0-133">Complete the testing and the validation before you submit your plan for final approval.</span></span>

</div>

<div>

## <a name="communicating-the-plan"></a><span data-ttu-id="d02a0-134">計画を伝える</span><span class="sxs-lookup"><span data-stu-id="d02a0-134">Communicating the Plan</span></span>

<span data-ttu-id="d02a0-135">バックアップと復元の計画では、手順を実装する担当者と手順を実行するためのステップごとの指示を明確に説明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d02a0-135">Your backup and restoration plan should clearly describe who implements procedures and step-by-step instructions for carrying out the procedures.</span></span> <span data-ttu-id="d02a0-136">バックアップと復元のあらゆる側面に責任を持つすべてのユーザーが、計画、実装方法、およびその役割について理解していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d02a0-136">You should make sure that everyone responsible for any aspect of backup and restoration understands the plan, how it is to be implemented, and what their role is.</span></span> <span data-ttu-id="d02a0-137">これには、以下のすべての実装要件が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d02a0-137">This includes all implementation requirements for the following:</span></span>

  - <span data-ttu-id="d02a0-138">プールとサーバーのバックアップ。</span><span class="sxs-lookup"><span data-stu-id="d02a0-138">Pool and server backup.</span></span>

  - <span data-ttu-id="d02a0-139">サービスの復元。</span><span class="sxs-lookup"><span data-stu-id="d02a0-139">Restoration of service.</span></span>

<span data-ttu-id="d02a0-140">**プールとサーバーのバックアップ**</span><span class="sxs-lookup"><span data-stu-id="d02a0-140">**Pool and server backup**</span></span>

<span data-ttu-id="d02a0-141">バックアップと復元の計画には、バックアップ手順を継続的に完了するために必要なすべての情報を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d02a0-141">The backup and restoration plan should include all information required to complete backup procedures on an ongoing basis.</span></span> <span data-ttu-id="d02a0-142">チームのメンバーに伝達される主要な情報には、以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d02a0-142">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="d02a0-143">各サーバーのバックアップを担当するチームまたは担当者 (個人または役割として指定)。</span><span class="sxs-lookup"><span data-stu-id="d02a0-143">Team or person (specified as an individual or role) responsible for backing up each server.</span></span>

  - <span data-ttu-id="d02a0-144">各サーバーをバックアップするための特定のスケジュール。</span><span class="sxs-lookup"><span data-stu-id="d02a0-144">Specific schedules for backing up each server.</span></span>

  - <span data-ttu-id="d02a0-145">データの種類 (設定、データベース、およびファイル共有) ごとのバックアップ場所。</span><span class="sxs-lookup"><span data-stu-id="d02a0-145">Backup locations for each type of data (settings, database, and file shares).</span></span>

  - <span data-ttu-id="d02a0-146">使用するバックアップ手順。各手順を完了するために必要なツールを含みます。</span><span class="sxs-lookup"><span data-stu-id="d02a0-146">Backup procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="d02a0-147">[Lync Server 2013 のバックアップと復元のワークシート](lync-server-2013-backup-and-restoration-worksheets.md)で説明されているように、バックアップを完了するために必要な情報。</span><span class="sxs-lookup"><span data-stu-id="d02a0-147">Information required to complete backups, as covered in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="d02a0-148">データおよび設定が適切にバックアップされ、復元に使用できるようにするために使用される検証方法。定期的な監査とテストの復元を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d02a0-148">Validation methods to be used to help ensure that data and settings are appropriately backed up and available for restoration, which can include periodic audits and test restorations.</span></span>

<span data-ttu-id="d02a0-149">**サービスの復元**</span><span class="sxs-lookup"><span data-stu-id="d02a0-149">**Restoration of service**</span></span>

<span data-ttu-id="d02a0-150">バックアップと復元の計画には、サービスの復元に必要なすべての情報を含める必要があります。1つまたは複数のサーバーで障害が発生し、サービスを利用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d02a0-150">The backup and restoration plan should include all information required to restore service, in case one or more servers experience a loss that makes service unavailable.</span></span> <span data-ttu-id="d02a0-151">チームのメンバーに伝達される主要な情報には、以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d02a0-151">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="d02a0-152">サービスの復元が必要かどうかを決定するチームまたは担当者 (個人または役割として指定されたもの) と、サービスの復元に使用する手順、および各復元シナリオの手順を実装するチームまたは担当者。</span><span class="sxs-lookup"><span data-stu-id="d02a0-152">Team or person (specified as an individual or a role) that is responsible for determining when restoration of service is required and the procedures to be used to restore service, and also the team or person responsible for implementing procedures for each restoration scenario.</span></span>

  - <span data-ttu-id="d02a0-153">特定の状況に最も適した復元手順を決定するための条件です。</span><span class="sxs-lookup"><span data-stu-id="d02a0-153">Criteria for determining which restoration procedures are most appropriate for a specific situation.</span></span>

  - <span data-ttu-id="d02a0-154">各復元シナリオでのサービスと RTO (目標復旧時間) の復元にかかる時間を予測します。</span><span class="sxs-lookup"><span data-stu-id="d02a0-154">Time estimates for restoration of service and recovery time objective (RTO) in each restoration scenario.</span></span>

  - <span data-ttu-id="d02a0-155">使用する復元手順 (各手順を完了するために必要なツールを含む)。</span><span class="sxs-lookup"><span data-stu-id="d02a0-155">Restoration procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="d02a0-156">データと設定を復元するために必要な情報。</span><span class="sxs-lookup"><span data-stu-id="d02a0-156">Information required to restore data and settings.</span></span> <span data-ttu-id="d02a0-157">ワークシートについては [、「Lync Server 2013 のバックアップと復元のワークシート](lync-server-2013-backup-and-restoration-worksheets.md)」をご用意しています。</span><span class="sxs-lookup"><span data-stu-id="d02a0-157">Worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a><span data-ttu-id="d02a0-158">バックアップと復元の操作を検証する</span><span class="sxs-lookup"><span data-stu-id="d02a0-158">Validating Backup and Restoration Operations</span></span>

<span data-ttu-id="d02a0-159">運用環境で最初のバックアップ作業を行い、指定した間隔 (バックアップと復元の計画に従って) を実行した後、次の点を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d02a0-159">After completing initial backup efforts in your production environment and at specified intervals (as covered in your backup and restoration plan), you should verify the following:</span></span>

  - <span data-ttu-id="d02a0-160">バックアップは必要に応じて発生します。</span><span class="sxs-lookup"><span data-stu-id="d02a0-160">Backups are occurring as required.</span></span>

  - <span data-ttu-id="d02a0-161">バックアップされたデータと設定にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d02a0-161">Backed-up data and settings are accessible.</span></span>

  - <span data-ttu-id="d02a0-162">復元手順は、バックアップと復元の計画で指定された RTO (目標復旧時間) の期間内に実行でき、結果はすべてのビジネス要件を満たします。</span><span class="sxs-lookup"><span data-stu-id="d02a0-162">Restoration procedures can be performed within the recovery time objective (RTO) times specified in the backup and restoration plan, and the results meet all business requirements.</span></span>

  - <span data-ttu-id="d02a0-163">バックアップワークシートが完成し、確認されており、安全な場所に格納されています。</span><span class="sxs-lookup"><span data-stu-id="d02a0-163">Backup worksheets have been completed and verified, and they are stored in a secure location.</span></span> <span data-ttu-id="d02a0-164">これらのワークシートは [、Lync Server 2013 のバックアップと復元のワークシート](lync-server-2013-backup-and-restoration-worksheets.md)に用意されています。</span><span class="sxs-lookup"><span data-stu-id="d02a0-164">These worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="d02a0-165">バックアップと復元の計画で指定されているように、復元手順はテスト済みで、予想どおりに動作することが確認されています。</span><span class="sxs-lookup"><span data-stu-id="d02a0-165">Restoration procedures have been tested and verified to work as expected, as specified in your backup and restoration plan.</span></span>

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a><span data-ttu-id="d02a0-166">バックアップと復元の計画を維持する</span><span class="sxs-lookup"><span data-stu-id="d02a0-166">Maintaining the Backup and Restoration Plan</span></span>

<span data-ttu-id="d02a0-167">Lync Server トポロジは、組織によって変更される動的な環境です。</span><span class="sxs-lookup"><span data-stu-id="d02a0-167">A Lync Server topology is a dynamic environment that changes with your organization.</span></span> <span data-ttu-id="d02a0-168">組織の変更に合わせてバックアップと復元の計画を再評価し、定期的に確認して、ビジネスのニーズを引き続き確認してください。</span><span class="sxs-lookup"><span data-stu-id="d02a0-168">Reassess your backup and restoration plan as your organization changes, and review it periodically to make sure that it continues to meet the needs of your business.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

