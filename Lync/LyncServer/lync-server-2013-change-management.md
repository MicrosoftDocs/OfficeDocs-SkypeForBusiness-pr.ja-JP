---
title: 'Lync Server 2013: 変更管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change management
ms:assetid: 73c774f5-c12f-4c72-be73-e07dc745b994
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720336(v=OCS.15)
ms:contentKeyID: 63969618
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abd6af0af5722d05d7439ac262ff36e62d2b12e1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-management-in-lync-server-2013"></a><span data-ttu-id="477e5-102">Lync Server 2013 での変更管理</span><span class="sxs-lookup"><span data-stu-id="477e5-102">Change management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="477e5-103">_**トピックの最終更新日:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="477e5-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="477e5-104">IT 環境への変更は避けられません。</span><span class="sxs-lookup"><span data-stu-id="477e5-104">Changes to the IT environment are unavoidable.</span></span> <span data-ttu-id="477e5-105">変更には、新しいテクノロジ、システム、アプリケーション、ハードウェア、ツール、プロセス、および役割と責任の変更が含まれます。</span><span class="sxs-lookup"><span data-stu-id="477e5-105">Changes include new technologies, systems, applications, hardware, tools, processes, and changes in roles and responsibilities.</span></span> <span data-ttu-id="477e5-106">効果的な変更管理システムを使用すると、サービスの中断を最小限に抑えながら、迅速に IT 環境に変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="477e5-106">An effective change management system lets you introduce changes to the IT environment quickly and with minimal service disruption.</span></span> <span data-ttu-id="477e5-107">変更管理システムによって、システムの変更に関係する teams が統合されます。</span><span class="sxs-lookup"><span data-stu-id="477e5-107">A change management system brings together the teams involved in changing a system.</span></span> <span data-ttu-id="477e5-108">たとえば、Office Web Apps を利用することを決定します。</span><span class="sxs-lookup"><span data-stu-id="477e5-108">For example, deciding to take advantage of the Office Web Apps.</span></span> <span data-ttu-id="477e5-109">これは、ユーザーがブラウザーでドキュメントを読み取って編集できるようにするための、統合された Lync サービスアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="477e5-109">This is an integrated Lync Service application that enables users to read and edit documents in a browser.</span></span> <span data-ttu-id="477e5-110">運用を終了した後、このサービスを実装するには、いくつかのチームの関与が必要になります。</span><span class="sxs-lookup"><span data-stu-id="477e5-110">The implementation of this service, after you have gone into production, requires the involvement of several teams:</span></span>

  - <span data-ttu-id="477e5-111">**テストチーム**   このチームは、テストサーバー上の Office Web Apps のロードテストを行い、予想される使用パターンおよび運用サーバーの予想されるパフォーマンスに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="477e5-111">**Test Team**   This team load-tests the Office Web Apps on a test server, in the process providing information about the expected usage patterns and expected performance of the production servers.</span></span>

  - <span data-ttu-id="477e5-112">**Lync 管理者**   このチームは、展開戦略を決定し、可能な場合にインストールをスクリプトにします。</span><span class="sxs-lookup"><span data-stu-id="477e5-112">**Lync Administrators**   This team determines the deployment strategy and scripts the installation where it was possible.</span></span> <span data-ttu-id="477e5-113">チームは、変更が運用環境に展開されることを確認し、後で管理することを担当します。</span><span class="sxs-lookup"><span data-stu-id="477e5-113">The team is responsible for making sure that the change is deployed on the production environment, and it is responsible for administration afterward.</span></span> <span data-ttu-id="477e5-114">変更の影響について理解し、変更を運用に移す前に手順に組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="477e5-114">The team must understand the effect of the changes and incorporate them in procedures before the changes are put into production</span></span>

  - <span data-ttu-id="477e5-115">**ネットワークチーム**   このチームは、インターネットから内部の Lync プールサーバーへのアクセスを許可するファイアウォールルールへの変更を担当します。</span><span class="sxs-lookup"><span data-stu-id="477e5-115">**Network Team**   This team is responsible for changes to firewall rules that allow access from the Internet to the internal Lync pool servers.</span></span> <span data-ttu-id="477e5-116">また、チームは、使用可能な帯域幅が追加の負荷をサポートできることを確認するために、Lync 管理者との連携を担当します。</span><span class="sxs-lookup"><span data-stu-id="477e5-116">The team is also responsible in working with the Lync administrators for making sure that the available bandwidth can support the additional load.</span></span>

  - <span data-ttu-id="477e5-117">**セキュリティチーム**   このチームは、セキュリティを評価し、リスクを最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="477e5-117">**Security Team**   This team assesses security and minimizes risks.</span></span> <span data-ttu-id="477e5-118">セキュリティチームは既知の脆弱性を調査する必要があり、セキュリティリスクが最小限になるように支援します。</span><span class="sxs-lookup"><span data-stu-id="477e5-118">The security team must review known vulnerabilities and help ensure that security risks are minimized.</span></span>

  - <span data-ttu-id="477e5-119">**ユーザー受け入れチーム**   このチームは、システムをテストし、改善のためにフィードバックを提供するユーザーで構成されています。</span><span class="sxs-lookup"><span data-stu-id="477e5-119">**User Acceptance Team**   This team is composed of users who are willing to test the system and offer feedback for improvements.</span></span>

<span data-ttu-id="477e5-120">変更管理プロセスでは、各チームの責任を定義し、実行する作業をスケジュールして、必要な場所でチェックとテストを組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="477e5-120">The change management process defines the responsibilities of each team and schedules the work to be performed, incorporating checks and tests where they are required.</span></span> <span data-ttu-id="477e5-121">変更コントロールは、複雑さと、変化の予想される影響に応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="477e5-121">Change controls will vary depending on the complexity and expected effect of a change.</span></span> <span data-ttu-id="477e5-122">小さな変更の自動承認、レビュー会議の変更、完全なプロジェクトレベルのレビューに対して異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="477e5-122">They can vary from automatic approval of minor changes, to change review meetings, to full project-level reviews.</span></span> <span data-ttu-id="477e5-123">このことを説明するために、変更のグループについてはこのセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="477e5-123">To explain this better, the groups of changes are discussed in this section.</span></span>

  - <span data-ttu-id="477e5-124">**大きな変更**   主な変更は、システムに影響を与え、さまざまなチームからの入力を必要とする場合があります。</span><span class="sxs-lookup"><span data-stu-id="477e5-124">**Major Changes**   Major changes have a global effect on the system and may require input from various teams.</span></span> <span data-ttu-id="477e5-125">この例は、Lync Server 2013 にアップグレードしています。</span><span class="sxs-lookup"><span data-stu-id="477e5-125">An example of this is upgrading to Lync Server 2013.</span></span> <span data-ttu-id="477e5-126">大きな変更は、多くのチームや、おそらく異なるシステムに影響します。</span><span class="sxs-lookup"><span data-stu-id="477e5-126">Major changes affect many teams and perhaps different systems.</span></span> <span data-ttu-id="477e5-127">変更管理プロセスには、変更に関与する、または変更によって影響を受けるチームに通知するために、1つまたは複数の変更レビュー会議が含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="477e5-127">The change management process will probably include one or more change review meetings to inform the teams that will be involved in the change or be affected by the change.</span></span>

  - <span data-ttu-id="477e5-128">**大幅な変更**   大きな変更は、計画、構築、および実装に多大なリソースを必要とします。</span><span class="sxs-lookup"><span data-stu-id="477e5-128">**Significant Changes**   Significant changes require significant resources to plan, build, and implement.</span></span> <span data-ttu-id="477e5-129">変更の影響が理解され、展開手順がテストされて、ロールバックおよび不測の計画が準備されていることを確認するために、適切な変更管理が導入されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="477e5-129">Appropriate change controls should be introduced to help make ensure that the effect of the change is understood, deployment procedures are tested, and the rollback and contingency plans are ready.</span></span> <span data-ttu-id="477e5-130">重要な変更の例として、新しい累積的な更新プログラムが展開されています。</span><span class="sxs-lookup"><span data-stu-id="477e5-130">An example of a significant change is deploying a new cumulative update.</span></span>

  - <span data-ttu-id="477e5-131">**マイナー**   変更小規模な変更は、IT 環境に大きな影響を与えることはありません。たとえば、Microsoft lync Server 2013 コントロールパネルを使用して特定の Lync ポリシーを変更する場合などです。</span><span class="sxs-lookup"><span data-stu-id="477e5-131">**Minor Changes**   Minor changes do not significantly affect the IT environment, for example, changing certain Lync policies via the Microsoft Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="477e5-132">**標準変更**   は定期的に行われ、よく理解され文書化されています。</span><span class="sxs-lookup"><span data-stu-id="477e5-132">**Standard Changes**   Standard changes are performed regularly and are well understood and documented.</span></span> <span data-ttu-id="477e5-133">変更管理プロセスでは、手順に対するすべての変更を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="477e5-133">The change management process should review all changes to the procedures.</span></span> <span data-ttu-id="477e5-134">コンテンツデータベースの作成やユーザーの追加などのルーチンの変更には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="477e5-134">It should not be needed for routine changes like creating a content database or adding a user.</span></span>

<span data-ttu-id="477e5-135">次の変更管理の例では、さまざまなチームがどのように連携し、新しいサービスパックが展開されたときに実行されるアクションを検証します。</span><span class="sxs-lookup"><span data-stu-id="477e5-135">The following example of change management examines how different teams interact and the actions that are performed when a new service pack is deployed.</span></span> <span data-ttu-id="477e5-136">これらのアクションは、変更管理プロセスによって編成および管理されます。</span><span class="sxs-lookup"><span data-stu-id="477e5-136">These actions are organized and managed by the change management process.</span></span>

  - <span data-ttu-id="477e5-137">**変更要求**   を発生させるセキュリティチームは最新のサービスパックを評価し、運用システムに存在する可能性のある脆弱性を解決することを確認しました。</span><span class="sxs-lookup"><span data-stu-id="477e5-137">**Raise a change request**   The security team has assessed the latest service pack and confirmed that it resolves a possible vulnerability in the production system.</span></span> <span data-ttu-id="477e5-138">チームは、Lync Server を実行しているすべてのサーバーに対して新しい累積更新プログラムを適用するための変更要求を発生させます。</span><span class="sxs-lookup"><span data-stu-id="477e5-138">The team raises a change request to have the new cumulative update applied to all servers that are running Lync Server.</span></span>

  - <span data-ttu-id="477e5-139">**Service pack のリリースノートのレビュー**   Lync 管理チームは、サービスパックのリリースノートを見直して、システムへの影響を特定します。</span><span class="sxs-lookup"><span data-stu-id="477e5-139">**Service pack release notes review**   The Lync administrator team reviews the service pack release notes to identify the effect on the system.</span></span>

  - <span data-ttu-id="477e5-140">**一連のラボテストが実行**   されます。 Lync 管理チームは、インストールされているアプリケーションおよびサーバーシステムに影響を与えることなく、service pack を正常に適用できるかどうかを判断するために、テスト環境のサーバーでテスト更新を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="477e5-140">**A series of lab tests is performed**   The Lync administrator team must perform test updates on a server in a test environment to decide whether the service pack can be applied successfully without affecting any of the installed applications and server systems.</span></span> <span data-ttu-id="477e5-141">運用環境で Lync Server とインターフェイスを使用して、サードパーティまたは内部で作成されたアプリケーションがある場合は、これらもテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="477e5-141">If there are third-party or internally created applications that interface with Lync Server in a production environment, these should be also tested.</span></span> <span data-ttu-id="477e5-142">これらのテストは、アップグレードを実行するために必要な時間を見積もるためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="477e5-142">These tests can also be used to estimate the time that is required to perform the upgrades.</span></span>

  - <span data-ttu-id="477e5-143">**ユーザーに**   は、Lync 管理者チーム、コミュニケーションチーム、またはユーザーヘルプデスクが、計画された保守サイクルおよびサービスを利用できない期間について、影響を受けるすべてのユーザーに通知されます。</span><span class="sxs-lookup"><span data-stu-id="477e5-143">**Users are informed of the outage**   The Lync administrator team, communications team, or user help desk informs all affected users about the planned maintenance cycle and how long the service will be unavailable.</span></span>

  - <span data-ttu-id="477e5-144">**Lync の完全バックアップ**   は、アップグレードの前に実行されます。 lync 管理チームは、service pack のインストールが失敗した場合に元のシステム状態に戻すために使用できる有効なバックアップがあるかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="477e5-144">**A full backup of Lync is performed before the upgrade**   The Lync administrator team must verify that there is a valid backup that can be used to revert to the original system state if the service pack installation fails.</span></span> <span data-ttu-id="477e5-145">問題がある場合にこのシステムをすぐに使用できるようにするには、スタンバイサーバーにバックアップを復元することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="477e5-145">We recommend that the backup be restored to a standby server to have this system readily available if there are issues.</span></span>

  - <span data-ttu-id="477e5-146">**累積的な更新プログラムが展開**   されています。 Lync 管理チームは、計画されたメンテナンスサイクル中にインストールを実行します。</span><span class="sxs-lookup"><span data-stu-id="477e5-146">**The cumulative update is deployed**   The Lync administrator team does the installation during the planned maintenance cycle.</span></span>

<div>

## <a name="managing-the-timing-of-changes"></a><span data-ttu-id="477e5-147">変更のタイミングを管理する</span><span class="sxs-lookup"><span data-stu-id="477e5-147">Managing the timing of changes</span></span>

<span data-ttu-id="477e5-148">変更をスケジュール設定するための手順を実施して、作業の重複した部分の混乱を回避することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="477e5-148">We recommend that you implement a procedure for scheduling changes to avoid disruptions in overlapping sections of your work.</span></span> <span data-ttu-id="477e5-149">たとえば、2つのチームがシステムへの小さな変更を計画している場合があります。</span><span class="sxs-lookup"><span data-stu-id="477e5-149">For example, two teams may both be planning a minor change to a system.</span></span> <span data-ttu-id="477e5-150">他のチームが従来のユーザーをそのプールに移行している間に、1つのチームで累積的な更新プログラムをプールに適用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="477e5-150">One team may be applying a cumulative update on a pool while another team is migrating legacy users into that pool.</span></span> <span data-ttu-id="477e5-151">他のチームが計画している変更の影響を受けることはありません。また、チームごとに、他のチームが計画している変更について把握していない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="477e5-151">Neither team is affected by the changes that the other team is planning, and each team may not necessarily know about changes that the other team is planning.</span></span> <span data-ttu-id="477e5-152">両方の変更が同時に発生した場合は、変更を実装するときに問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="477e5-152">If both changes occurred at the same time, there might be issues implementing the changes.</span></span> <span data-ttu-id="477e5-153">また、ユーザーの移行が失敗した場合など、変更が適用された後に問題が発生した場合は、どの変更をロールバックする必要があるかを判断するのが困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="477e5-153">Also, if there are issues after the changes were applied, for example, if the user migration fails, it may be difficult to decide which change should be rolled back.</span></span> <span data-ttu-id="477e5-154">変更をテストして同意するには、定期的な保守期間を設定し、管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="477e5-154">There should be regular maintenance periods set up between IT and management to test the changes and accept them.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

