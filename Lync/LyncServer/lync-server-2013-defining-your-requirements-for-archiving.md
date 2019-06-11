---
title: 'Lync Server 2013: アーカイブ要件の定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for Archiving
ms:assetid: ce0fc0f6-7704-4b80-bf19-a1fa9818fc7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205276(v=OCS.15)
ms:contentKeyID: 48185462
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75ed62d577cc6b382509f83e53088973e16b6827
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-archiving-in-lync-server-2013"></a><span data-ttu-id="08776-102">Lync Server 2013 でのアーカイブ要件の定義</span><span class="sxs-lookup"><span data-stu-id="08776-102">Defining your requirements for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08776-103">_**最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="08776-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="08776-104">組織でコンプライアンスの規則に従う必要がある場合は、アーカイブを展開して、Lync Server 2013 インスタントメッセージング (IM) と会議 (会議) のアーカイブサポートを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="08776-104">If your organization must follow compliance regulations, you can deploy Archiving to enable archiving support for Lync Server 2013 instant messaging (IM) and conferencing (meetings).</span></span> <span data-ttu-id="08776-105">アーカイブ可能なコンテンツの種類の詳細については、計画ドキュメントの「 [Lync Server 2013 でのアーカイブの概要](lync-server-2013-overview-of-archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08776-105">For details about the type of content that can be archived, see [Overview of Archiving in Lync Server 2013](lync-server-2013-overview-of-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="08776-106">アーカイブを実装するには、まず組織のアーカイブ要件を満たす方法を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08776-106">To implement Archiving, you need to first decide how to meet your organization’s requirements for Archiving.</span></span> <span data-ttu-id="08776-107">そのためには、次のことを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08776-107">This requires determining the following:</span></span>

  - <span data-ttu-id="08776-108">**アーカイブを展開するタイミング**。</span><span class="sxs-lookup"><span data-stu-id="08776-108">**When to deploy Archiving**.</span></span> <span data-ttu-id="08776-109">初めての Lync Server 2013 展開の一部としてアーカイブを展開するか、既存の展開に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="08776-109">You can deploy Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="08776-110">トポロジビルダーを使用してアーカイブを展開し、トポロジに追加してから、トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="08776-110">You deploy Archiving by using Topology Builder to add it to your topology, and then publishing the topology.</span></span>

  - <span data-ttu-id="08776-p104">**内部通信または外部通信をアーカイブするかどうか**。内部通信 (つまり、内部ユーザー間の通信)、外部通信 (少なくとも 1 人の内部ネットワーク外のユーザーが含まれる通信)、または両方のアーカイブを有効にできます。これらのオプションは、組織全体に対して指定することも、特定のサイトおよびプールに対して指定することもできます。既定では、どちらのオプションも無効です。</span><span class="sxs-lookup"><span data-stu-id="08776-p104">**Whether to archive internal or external communications**. You can enable archiving for internal communications (communications between internal users), external communications (communications that include at least one user outside your internal network), or both. You can specify these options for your entire organization, or you can specify them for specific sites and pools. By default, neither option is enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="08776-115">Microsoft Exchange の統合機能を使用してアーカイブデータを保存する場合、Exchange の設定によって Lync の通信をアーカイブするかどうかが制御されます。</span><span class="sxs-lookup"><span data-stu-id="08776-115">If you use Microsoft Exchange integration to store archived data, your Exchange settings control whether Lync communications are archived.</span></span> <span data-ttu-id="08776-116">展開に複数のフォレストが含まれている場合は、Lync Server と Exchange の間で設定を同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08776-116">If your deployment includes multiple forests, you must synchronize the settings between Lync Server and Exchange.</span></span> <span data-ttu-id="08776-117">内部または外部の通信のアーカイブの制御は、Lync ポリシーでのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="08776-117">Controlling archiving for internal or external communications is only available for Lync Policy.</span></span> <span data-ttu-id="08776-118">Exchange と統合されたアーカイブでは、両方ともアーカイブされるか、アーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="08776-118">For Exchange-integrated archiving, both of them will be archived or not archived.</span></span>

    
    </div>

  - <span data-ttu-id="08776-119">**アーカイブを有効にする理由**</span><span class="sxs-lookup"><span data-stu-id="08776-119">**Why enable Archiving**.</span></span> <span data-ttu-id="08776-120">展開全体のアーカイブをグローバルレベルで有効または無効にすることができます。また、特定のサイトとユーザーのアーカイブを有効または無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="08776-120">You can enable and disable Archiving for your entire deployment at a global level, and you can enable and disable Archiving for specific sites and users.</span></span> <span data-ttu-id="08776-121">これらの各レベルでは、IM セッションのアーカイブを有効にするか (ピアツーピア)、会議 (会議)、またはその両方を指定します。</span><span class="sxs-lookup"><span data-stu-id="08776-121">At each of these levels, you specify whether to enable archiving of IM sessions (peer-to-peer), conferences (meetings, which are multiparty sessions), or both.</span></span> <span data-ttu-id="08776-122">既定では、アーカイブは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="08776-122">By default, Archiving is disabled.</span></span>

  - <span data-ttu-id="08776-123">**組織内のユーザーにとって重要なアーカイブはどのように**なりますか。</span><span class="sxs-lookup"><span data-stu-id="08776-123">**How critical Archiving is to users in your organization**.</span></span> <span data-ttu-id="08776-124">組織でアーカイブがミッションクリティカルである場合は、Lync Server 2013 がクリティカルモードで実行されるように指定することができます。これにより、アーカイブに失敗した場合に IM と会議セッションがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="08776-124">If archiving is mission-critical in your organization, you can specify that Lync Server 2013 run in critical mode, which blocks IM and conferencing sessions if archiving fails.</span></span> <span data-ttu-id="08776-125">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="08776-125">For example:</span></span>
    
      - <span data-ttu-id="08776-126">アーカイブサービスが、一時的にデータベースキューにメッセージを送信できない場合、またはデータベースにメッセージを挿入できない場合、アーカイブのサポートが復元されるまで、IM と会議の機能は両方とも展開でブロックされます。</span><span class="sxs-lookup"><span data-stu-id="08776-126">If the Archiving service is temporarily unable to send a message to the database queue or insert a message into the database), both IM and conferencing functionality are blocked in the deployment until archiving support is restored.</span></span>
    
      - <span data-ttu-id="08776-127">会議ユーザーがファイルをアップロードしても、ファイルをアーカイブファイルストアにコピーできない場合、会議機能は問題が解決されるまで展開でブロックされますが、IM 機能はブロックされません。</span><span class="sxs-lookup"><span data-stu-id="08776-127">If a conferencing user uploads a file, but the file cannot be copied to the archiving file store, conferencing functionality is blocked in the deployment until the problem is resolved, but IM functionality is not blocked.</span></span>
    
    <span data-ttu-id="08776-128">このオプションは、グローバルレベル、サイトレベル、プールレベルで構成できます。</span><span class="sxs-lookup"><span data-stu-id="08776-128">You can configure this option at the global level, site level, and pool level.</span></span> <span data-ttu-id="08776-129">既定では、[クリティカル] モードは有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="08776-129">By default, critical mode is not enabled.</span></span>

  - <span data-ttu-id="08776-130">**Microsoft Exchange 統合を使用するかどうか**。</span><span class="sxs-lookup"><span data-stu-id="08776-130">**Whether to use Microsoft Exchange integration**.</span></span> <span data-ttu-id="08776-131">このオプションでは、アーカイブストレージと Exchange 2013 ストレージが統合されるため、Lync Server のアーカイブデータと Exchange 2013 アーカイブデータは Exchange に一緒に保存されます。</span><span class="sxs-lookup"><span data-stu-id="08776-131">This option integrates Archiving storage with your Exchange 2013 storage, so that your Lync Server archived data and Exchange 2013 archived data are stored together in Exchange.</span></span> <span data-ttu-id="08776-132">Microsoft Exchange 統合を使用すると、Exchange 2013 を使っているユーザーのメールボックスがインプレース保持されている場合に、そのユーザーのアーカイブデータを保存することができます。</span><span class="sxs-lookup"><span data-stu-id="08776-132">You can use Microsoft Exchange integration for storage of archiving data for users who are homed on Exchange 2013, if their mailboxes have been put on In-Place Hold.</span></span> <span data-ttu-id="08776-133">Exchange 2013 の展開を行っていない場合、または統合しない場合、または Exchange 2013 を使用していない Lync ユーザーがいる場合は、SQL Server を使用して、アーカイブデータを Lync コミュニケーションから保存することで、個別のアーカイブデータベースを展開できます。</span><span class="sxs-lookup"><span data-stu-id="08776-133">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync users who are not homed on Exchange 2013, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="08776-134">Microsoft Exchange 統合オプションは、グローバルレベル、サイトレベル、プールレベルで構成できます。</span><span class="sxs-lookup"><span data-stu-id="08776-134">You can configure the Microsoft Exchange integration option at the global level, site level, and pool level.</span></span> <span data-ttu-id="08776-135">既定では、Microsoft Exchange の統合は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="08776-135">By default, Microsoft Exchange integration is not enabled.</span></span>

  - <span data-ttu-id="08776-136">**アーカイブデータを管理する方法**。</span><span class="sxs-lookup"><span data-stu-id="08776-136">**How archived data is to be managed**.</span></span> <span data-ttu-id="08776-137">アーカイブデータベースは、長期間の保存のためのものではありません。また、Lync Server 2013 はアーカイブデータの電子的な探索 (検索) ソリューションを提供していないため、データを他のストレージに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08776-137">The archiving database is not intended for long-term retention and Lync Server 2013 does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="08776-138">Lync Server には、アーカイブデータをエクスポートするために使用できるセッションエクスポートツールが用意されています。これにより、アーカイブデータの検索可能なトランスクリプトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="08776-138">Lync Server does provide a session export tool that you can use to export archived data, and which creates searchable transcripts of the archived data.</span></span> <span data-ttu-id="08776-139">グローバルポリシーの場合、および作成するサイトとユーザーのポリシーごとに、データの削除を有効にして、次のいずれかのオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="08776-139">For the global policy, and for each site and user policy that you create, you can enable data purging and specify one of the following options:</span></span>
    
      - <span data-ttu-id="08776-140">指定の日数が経過した後に、エクスポートされたアーカイブデータと保存されているアーカイブデータの両方を消去します。</span><span class="sxs-lookup"><span data-stu-id="08776-140">Purge both exported archiving data and stored archiving data after a specific number of days.</span></span> <span data-ttu-id="08776-141">指定できる日数の最小値は1日です。</span><span class="sxs-lookup"><span data-stu-id="08776-141">The minimum number of days that you can specify is one day.</span></span> <span data-ttu-id="08776-142">指定できる最大日数は2562日です。</span><span class="sxs-lookup"><span data-stu-id="08776-142">The maximum number of days that you can specify is 2562 days.</span></span>
    
      - <span data-ttu-id="08776-143">エクスポートされたアーカイブデータのみを消去します。</span><span class="sxs-lookup"><span data-stu-id="08776-143">Purge exported archiving data only.</span></span> <span data-ttu-id="08776-144">このオプションでは、エクスポートされた、またはセッションエクスポートツールによって削除できるとマークされたすべてのレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="08776-144">This option purges all records that have been exported and marked as safe to delete by the session export tool.</span></span>
    
    <span data-ttu-id="08776-145">このオプションは、グローバルレベル、サイトレベル、プールレベルで構成できます。</span><span class="sxs-lookup"><span data-stu-id="08776-145">You can configure this option at the global level, site level, and pool level.</span></span> <span data-ttu-id="08776-146">既定では、削除は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="08776-146">By default, purging is not enabled.</span></span>

<span data-ttu-id="08776-147">アーカイブを制御するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="08776-147">You control Archiving by using the following methods:</span></span>

  - <span data-ttu-id="08776-148">**アーカイブポリシー**。</span><span class="sxs-lookup"><span data-stu-id="08776-148">**Archiving policies**.</span></span> <span data-ttu-id="08776-149">内部と外部の通信のアーカイブを有効または無効にするには、1つ以上のアーカイブポリシーを使います。</span><span class="sxs-lookup"><span data-stu-id="08776-149">You use one or more Archiving policies to enable and disable archiving of internal and external communications.</span></span> <span data-ttu-id="08776-150">既定では、アーカイブは有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="08776-150">By default, no archiving is enabled.</span></span> <span data-ttu-id="08776-151">既定のグローバルポリシーを使用して、展開で内部通信、外部通信、またはその両方のアーカイブを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="08776-151">You enable or disable Archiving for internal communications, external communications, or both in your deployment by using the default global policy.</span></span> <span data-ttu-id="08776-152">グローバルポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="08776-152">You cannot delete the global policy.</span></span> <span data-ttu-id="08776-153">1つまたは複数のオプションのサイトポリシーを指定して、特定のサイトの内部および外部通信のアーカイブを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="08776-153">You can specify one or more optional site policies to enable or disable Archiving for internal and external communications for specific sites.</span></span> <span data-ttu-id="08776-154">また、1つ以上のユーザーポリシーを指定して、特定のユーザーとユーザーグループのアーカイブを有効または無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="08776-154">You can also specify one or more user policies to enable or disable Archiving for specific users and user groups.</span></span> <span data-ttu-id="08776-155">ユーザーレベルのポリシーは、サイトポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="08776-155">User-level policies override site policies.</span></span> <span data-ttu-id="08776-156">サイトレベルのポリシーはグローバルレベルポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="08776-156">Site-level policies override the global-level policies.</span></span> <span data-ttu-id="08776-157">ユーザーレベルポリシーは、ポリシーを使用するように構成されている特定のユーザーに対してのみ実装されます。</span><span class="sxs-lookup"><span data-stu-id="08776-157">User-level policies are implemented only for the specific users who are configured to use the policy.</span></span> <span data-ttu-id="08776-158">グループのインスタントメッセージと会議は、少なくとも1人の参加者のポリシーがアーカイブを有効にするように構成されている場合にのみアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="08776-158">Group instant messages and conferences are archived only if a policy for at least one of the participants is configured to enable archiving.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="08776-159">Microsoft Exchange との統合を使用している場合、exchange 2013 ポリシーは、Exchange 2013 サーバー上にあるすべてのユーザーに対して Lync Server アーカイブポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="08776-159">If you use Microsoft Exchange integration, Exchange 2013 policies override Lync Server Archiving policies for all users homed on the Exchange 2013 servers.</span></span>

    
    </div>

  - <span data-ttu-id="08776-160">**アーカイブ構成**。</span><span class="sxs-lookup"><span data-stu-id="08776-160">**Archiving configurations**.</span></span> <span data-ttu-id="08776-161">このトピックで説明されているアーカイブオプションのほとんどを指定するには、1つ以上のアーカイブ構成を使用します。内部および外部通信のアーカイブを有効にする (アーカイブポリシーを使用して構成する) ことを除き、前の行頭文字)</span><span class="sxs-lookup"><span data-stu-id="08776-161">You use one or more Archiving configurations to specify most of the Archiving options that are described previously in this topic, except for enabling archiving of internal and external communications (configured using Archiving policies, as described in the previous bullet).</span></span> <span data-ttu-id="08776-162">アーカイブ構成には、既定のグローバル構成、オプションのサイトとプール構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="08776-162">Archiving configurations include the default global configuration and optional site and pool configurations.</span></span> <span data-ttu-id="08776-163">グローバル構成を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="08776-163">You cannot delete the global configuration.</span></span> <span data-ttu-id="08776-164">プールレベルの構成は、サイトレベルの構成よりも優先します。</span><span class="sxs-lookup"><span data-stu-id="08776-164">Pool-level configurations override site-level configurations.</span></span> <span data-ttu-id="08776-165">サイトレベルの構成は、グローバルレベルの構成よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="08776-165">Site-level configurations override the global-level configuration.</span></span>

<span data-ttu-id="08776-166">要件分析の一環として、グローバルアーカイブ構成とグローバルアーカイブポリシーの構成方法を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08776-166">As part of your requirements analysis, you need to determine how to configure the global Archiving configuration and global Archiving policy.</span></span> <span data-ttu-id="08776-167">また、サイトレベルのアーカイブ構成、プールレベルのアーカイブ構成、サイトレベルのアーカイブポリシー、ユーザーレベルのアーカイブポリシーの要件を特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08776-167">You also need to determine your requirements for any site-level Archiving configurations, pool-level Archiving configurations, site-level Archiving policies, and user-level Archiving policies.</span></span>

<span data-ttu-id="08776-168">1つのフロントエンドプールまたは Standard Edition サーバーのアーカイブを展開する場合は、その他のすべてのフロントエンドプールと Standard Edition サーバーに対して、展開で有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="08776-168">If you deploy Archiving for one Front End pool or Standard Edition server, you should then enable it for all other Front End pools and Standard Edition servers in your deployment.</span></span> <span data-ttu-id="08776-169">この操作を行う必要があるのは、通信がアーカイブされる必要のあるユーザーが、グループ IM 会話または別のプールでホストされている会議に参加できるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="08776-169">You need to do this because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool.</span></span> <span data-ttu-id="08776-170">会話または会議がホストされているプールでアーカイブが有効になっていない場合、すべての会議データがアーカイブされない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="08776-170">If archiving is not enabled on the pool where the conversation or meeting is hosted, all conference data may not be archived.</span></span> <span data-ttu-id="08776-171">アーカイブが有効になっているユーザーとすべての IM メッセージに対してアーカイブは機能しますが、会議のコンテンツやイベントはアーカイブされない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="08776-171">Archiving will still work for archiving enabled users and all IM messages, but conferencing content and events may not be archived.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="08776-172">組織のセキュリティ基準を維持しながら管理タスクの委任を有効にするため&nbsp;に、Lync Server 2013 は役割ベースのアクセス制御 (RBAC) を使用します。</span><span class="sxs-lookup"><span data-stu-id="08776-172">To enable delegation of administrative tasks while maintaining your organization's security standards, Lync Server 2013&nbsp;uses role-based access control (RBAC).</span></span> <span data-ttu-id="08776-173">RBAC を使用すると、定義済みの管理者の役割にユーザーを割り当てることにより、管理者特権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="08776-173">With RBAC, administrative privilege is granted by assigning users to predefined administrative roles.</span></span> <span data-ttu-id="08776-174">Lync のアーカイブポリシーとアーカイブ構成を構成するには、ユーザーが CsArchivingAdministrator の役割に割り当てられている必要があります (ただし、(別のコンピューターからのリモートではなく、アーカイブが展開されているサーバーで直接構成が行われている場合を除きます)。</span><span class="sxs-lookup"><span data-stu-id="08776-174">To configure Lync Archiving policies and Archiving configurations, the user must be assigned to the CsArchivingAdministrator role (unless the configuration is done directly on the server where Archiving is deployed, instead of remotely from another computer).</span></span> <span data-ttu-id="08776-175">RBAC の詳細については、計画ドキュメントの「 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08776-175">For details about RBAC, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="08776-176">アーカイブ展開に必要なユーザー権限、権限、役割のリストについては、「 <A href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 でアーカイブするための展開チェックリスト</A>」を参照してください。これは、計画ドキュメントと展開ドキュメントの両方で利用できます。</span><span class="sxs-lookup"><span data-stu-id="08776-176">For a list of the user rights, permissions, and roles required for archiving deployment, see <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</A>, which is available in both the Planning documentation and the Deployment documentation.</span></span><BR><span data-ttu-id="08776-177">Microsoft Exchange の統合を使用している場合、Exchange ポリシーを構成するには、適切な管理者権限と権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="08776-177">If you use Microsoft Exchange integration, configuration of Exchange policies requires appropriate administrator rights and permissions.</span></span> <span data-ttu-id="08776-178">詳細については、「Exchange 2013 のドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08776-178">For details, see the Exchange 2013 documentation.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

