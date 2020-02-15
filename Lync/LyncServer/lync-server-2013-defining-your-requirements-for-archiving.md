---
title: 'Lync Server 2013: アーカイブの要件の定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Archiving
ms:assetid: ce0fc0f6-7704-4b80-bf19-a1fa9818fc7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205276(v=OCS.15)
ms:contentKeyID: 48185462
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c90baaafcc2d287c6bfc94784f8c0409d9de96f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-archiving-in-lync-server-2013"></a><span data-ttu-id="2cda2-102">Lync Server 2013 でのアーカイブ要件の定義</span><span class="sxs-lookup"><span data-stu-id="2cda2-102">Defining your requirements for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cda2-103">_**トピックの最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="2cda2-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="2cda2-104">組織が法令遵守規制に従う必要がある場合は、Lync Server 2013 インスタントメッセージング (IM) および電話会議 (会議) のアーカイブサポートを有効にするためのアーカイブを展開できます。</span><span class="sxs-lookup"><span data-stu-id="2cda2-104">If your organization must follow compliance regulations, you can deploy Archiving to enable archiving support for Lync Server 2013 instant messaging (IM) and conferencing (meetings).</span></span> <span data-ttu-id="2cda2-105">アーカイブできるコンテンツの種類の詳細については、「計画」のドキュメントの「 [Lync Server 2013 のアーカイブの概要](lync-server-2013-overview-of-archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cda2-105">For details about the type of content that can be archived, see [Overview of Archiving in Lync Server 2013](lync-server-2013-overview-of-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="2cda2-106">アーカイブ機能を実装するには、最初にアーカイブに対する組織の要件を満たす方法を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cda2-106">To implement Archiving, you need to first decide how to meet your organization’s requirements for Archiving.</span></span> <span data-ttu-id="2cda2-107">次のことを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cda2-107">This requires determining the following:</span></span>

  - <span data-ttu-id="2cda2-108">**アーカイブ機能を展開するタイミング。**</span><span class="sxs-lookup"><span data-stu-id="2cda2-108">**When to deploy Archiving**.</span></span> <span data-ttu-id="2cda2-109">最初の Lync Server 2013 展開の一部としてアーカイブを展開するか、既存の展開にアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="2cda2-109">You can deploy Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="2cda2-110">トポロジビルダーを使用してアーカイブを展開し、トポロジに追加して、トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="2cda2-110">You deploy Archiving by using Topology Builder to add it to your topology, and then publishing the topology.</span></span>

  - <span data-ttu-id="2cda2-p104">**内部通信または外部通信をアーカイブするかどうか。** 内部通信 (つまり、内部ユーザー間の通信)、外部通信 (少なくとも 1 人の内部ネットワーク外のユーザーが含まれる通信)、または両方のアーカイブを有効にできます。これらのオプションは、組織全体に対して指定することも、特定のサイトおよびプールに対して指定することもできます。既定では、どちらのオプションも無効です。</span><span class="sxs-lookup"><span data-stu-id="2cda2-p104">**Whether to archive internal or external communications**. You can enable archiving for internal communications (communications between internal users), external communications (communications that include at least one user outside your internal network), or both. You can specify these options for your entire organization, or you can specify them for specific sites and pools. By default, neither option is enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2cda2-115">Microsoft Exchange 統合を使用してアーカイブされたデータを保存する場合、Exchange の設定によって Lync 通信をアーカイブするかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="2cda2-115">If you use Microsoft Exchange integration to store archived data, your Exchange settings control whether Lync communications are archived.</span></span> <span data-ttu-id="2cda2-116">展開に複数のフォレストが含まれている場合は、Lync Server と Exchange の間で設定を同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cda2-116">If your deployment includes multiple forests, you must synchronize the settings between Lync Server and Exchange.</span></span> <span data-ttu-id="2cda2-117">内部または外部の通信のアーカイブを制御することは、Lync ポリシーに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2cda2-117">Controlling archiving for internal or external communications is only available for Lync Policy.</span></span> <span data-ttu-id="2cda2-118">Exchange 統合アーカイブの場合、どちらもアーカイブされるか、アーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="2cda2-118">For Exchange-integrated archiving, both of them will be archived or not archived.</span></span>

    
    </div>

  - <span data-ttu-id="2cda2-p106">**なぜアーカイブを有効にするのか。** アーカイブの有効または無効の指定は、グローバル レベルで展開全体に対して行うことも、特定のサイトおよびユーザーに対して行うこともできます。これらの各レベルで、IM セッション (ピアツーピア)、会議 (マルチパーティ セッション)、または両方のアーカイブを有効にするかどうかを指定します。既定では、アーカイブ機能は無効です。</span><span class="sxs-lookup"><span data-stu-id="2cda2-p106">**Why enable Archiving**. You can enable and disable Archiving for your entire deployment at a global level, and you can enable and disable Archiving for specific sites and users. At each of these levels, you specify whether to enable archiving of IM sessions (peer-to-peer), conferences (meetings, which are multiparty sessions), or both. By default, Archiving is disabled.</span></span>

  - <span data-ttu-id="2cda2-123">**組織内のユーザーにとって重要なアーカイブの方法**。</span><span class="sxs-lookup"><span data-stu-id="2cda2-123">**How critical Archiving is to users in your organization**.</span></span> <span data-ttu-id="2cda2-124">組織でアーカイブがミッションクリティカルである場合は、Lync Server 2013 を重要モードで実行するように指定できます。これにより、アーカイブが失敗した場合に IM および会議セッションがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="2cda2-124">If archiving is mission-critical in your organization, you can specify that Lync Server 2013 run in critical mode, which blocks IM and conferencing sessions if archiving fails.</span></span> <span data-ttu-id="2cda2-125">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="2cda2-125">For example:</span></span>
    
      - <span data-ttu-id="2cda2-126">アーカイブ サービスが一時的にデータベース キューにメッセージを送信できない、またはデータベースにメッセージを挿入できない場合、アーカイブ サポートが復元されるまで、IM および会議機能の両方が展開内で禁止されます。</span><span class="sxs-lookup"><span data-stu-id="2cda2-126">If the Archiving service is temporarily unable to send a message to the database queue or insert a message into the database), both IM and conferencing functionality are blocked in the deployment until archiving support is restored.</span></span>
    
      - <span data-ttu-id="2cda2-127">会議ユーザーがファイルをアップロードし、そのファイルがアーカイブ ファイル ストアに複製されない場合、問題が解決されるまで展開内の会議機能が禁止されますが、IM 機能は禁止されません。</span><span class="sxs-lookup"><span data-stu-id="2cda2-127">If a conferencing user uploads a file, but the file cannot be copied to the archiving file store, conferencing functionality is blocked in the deployment until the problem is resolved, but IM functionality is not blocked.</span></span>
    
    <span data-ttu-id="2cda2-p108">このオプションは、グローバル、サイト、およびプールのレベルで構成できます。既定では、クリティカル モードは無効です。</span><span class="sxs-lookup"><span data-stu-id="2cda2-p108">You can configure this option at the global level, site level, and pool level. By default, critical mode is not enabled.</span></span>

  - <span data-ttu-id="2cda2-130">**Microsoft Exchange 統合を使用するかどうか**。</span><span class="sxs-lookup"><span data-stu-id="2cda2-130">**Whether to use Microsoft Exchange integration**.</span></span> <span data-ttu-id="2cda2-131">このオプションを使用すると、アーカイブストレージが Exchange 2013 ストレージと統合されるため、Lync Server のアーカイブデータと Exchange 2013 アーカイブデータが Exchange にまとめて格納されます。</span><span class="sxs-lookup"><span data-stu-id="2cda2-131">This option integrates Archiving storage with your Exchange 2013 storage, so that your Lync Server archived data and Exchange 2013 archived data are stored together in Exchange.</span></span> <span data-ttu-id="2cda2-132">メールボックスがインプレース保持されている場合、Exchange 2013 に所属しているユーザーに対して、Microsoft Exchange 統合を使用してアーカイブデータを保存することができます。</span><span class="sxs-lookup"><span data-stu-id="2cda2-132">You can use Microsoft Exchange integration for storage of archiving data for users who are homed on Exchange 2013, if their mailboxes have been put on In-Place Hold.</span></span> <span data-ttu-id="2cda2-133">Exchange 2013 を展開していない場合、または統合しない場合、または Exchange 2013 に所属していない Lync ユーザーがいる場合は、SQL Server を使用して Lync コミュニケーションからアーカイブされたデータを格納することによって、別のアーカイブデータベースを展開できます。</span><span class="sxs-lookup"><span data-stu-id="2cda2-133">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync users who are not homed on Exchange 2013, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="2cda2-134">Microsoft Exchange 統合オプションは、グローバルレベル、サイトレベル、およびプールレベルで構成できます。</span><span class="sxs-lookup"><span data-stu-id="2cda2-134">You can configure the Microsoft Exchange integration option at the global level, site level, and pool level.</span></span> <span data-ttu-id="2cda2-135">既定では、Microsoft Exchange 統合は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="2cda2-135">By default, Microsoft Exchange integration is not enabled.</span></span>

  - <span data-ttu-id="2cda2-136">**アーカイブされたデータの管理方法**。</span><span class="sxs-lookup"><span data-stu-id="2cda2-136">**How archived data is to be managed**.</span></span> <span data-ttu-id="2cda2-137">アーカイブデータベースは、長期間の保存を対象としたものではなく、Lync Server 2013 はアーカイブされたデータに対して電子情報開示 (検索) ソリューションを提供しないため、データを他のストレージに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cda2-137">The archiving database is not intended for long-term retention and Lync Server 2013 does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="2cda2-138">Lync Server は、アーカイブされたデータのエクスポートに使用できるセッションエクスポートツールを提供します。また、アーカイブされたデータの検索可能なトランスクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2cda2-138">Lync Server does provide a session export tool that you can use to export archived data, and which creates searchable transcripts of the archived data.</span></span> <span data-ttu-id="2cda2-139">グローバルポリシーで、作成するサイトおよびユーザーポリシーごとに、データの削除を有効にし、次のいずれかのオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2cda2-139">For the global policy, and for each site and user policy that you create, you can enable data purging and specify one of the following options:</span></span>
    
      - <span data-ttu-id="2cda2-p111">特定の日数後に、エクスポート済みのアーカイブ データおよび保存されているアーカイブ データの両方を削除します。指定できる最小日数は 1 日です。指定できる最大日数は 2562 日です。</span><span class="sxs-lookup"><span data-stu-id="2cda2-p111">Purge both exported archiving data and stored archiving data after a specific number of days. The minimum number of days that you can specify is one day. The maximum number of days that you can specify is 2562 days.</span></span>
    
      - <span data-ttu-id="2cda2-p112">エクスポート済みのアーカイブデータのみを削除します。 このオプションは、すでにエクスポートされ、セッション エクスポート ツールによって削除しても安全だとマークされているすべてのレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="2cda2-p112">Purge exported archiving data only. This option purges all records that have been exported and marked as safe to delete by the session export tool.</span></span>
    
    <span data-ttu-id="2cda2-p113">このオプションは、グローバル、サイト、およびプールのレベルで構成できます。既定では、削除は無効です。</span><span class="sxs-lookup"><span data-stu-id="2cda2-p113">You can configure this option at the global level, site level, and pool level. By default, purging is not enabled.</span></span>

<span data-ttu-id="2cda2-147">アーカイブ機能を制御するには次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="2cda2-147">You control Archiving by using the following methods:</span></span>

  - <span data-ttu-id="2cda2-p114">**アーカイブ ポリシー。** 1 つ以上のアーカイブ ポリシーを使用して、内部通信および外部通信のアーカイブを有効および無効にします。既定では、アーカイブは無効になっています。既定のグローバル ポリシーを使用して、展開での内部通信、外部通信、またはその両方のアーカイブを有効または無効にします。グローバル ポリシーは削除できません。1 つ以上のオプションのサイト ポリシーを指定して、特定のサイトに対する内部通信および外部通信のアーカイブを有効または無効にできます。また、1 つ以上のユーザー ポリシーを指定して、特定のユーザーおよびユーザー グループのアーカイブを有効または無効にすることもできます。ユーザー レベルのポリシーはサイト ポリシーより優先されます。サイト レベルのポリシーは、グローバル レベルのポリシーより優先されます。ユーザー レベルのポリシーは、ポリシーを使用するように構成されている特定のユーザーに対してのみ実装されます。グループ インスタント メッセージおよび会議は、参加者のうち少なくとも 1 人のポリシーがアーカイブ有効に構成されている場合のみ、アーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="2cda2-p114">**Archiving policies**. You use one or more Archiving policies to enable and disable archiving of internal and external communications. By default, no archiving is enabled. You enable or disable Archiving for internal communications, external communications, or both in your deployment by using the default global policy. You cannot delete the global policy. You can specify one or more optional site policies to enable or disable Archiving for internal and external communications for specific sites. You can also specify one or more user policies to enable or disable Archiving for specific users and user groups. User-level policies override site policies. Site-level policies override the global-level policies. User-level policies are implemented only for the specific users who are configured to use the policy. Group instant messages and conferences are archived only if a policy for at least one of the participants is configured to enable archiving.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2cda2-159">Microsoft Exchange 統合を使用する場合、exchange 2013 ポリシーは、Exchange 2013 サーバーに所属するすべてのユーザーの Lync Server アーカイブポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="2cda2-159">If you use Microsoft Exchange integration, Exchange 2013 policies override Lync Server Archiving policies for all users homed on the Exchange 2013 servers.</span></span>

    
    </div>

  - <span data-ttu-id="2cda2-p115">**アーカイブの構成。** 1 つ以上のアーカイブ構成を使用して、このトピックでこれまでに説明したアーカイブ オプションのほとんどを指定できます。例外は、内部通信および外部通信のアーカイブの有効化の指定です (前の項で説明したように、これはアーカイブ ポリシーを使用して構成します)。アーカイブ構成には、既定のグローバル構成と、オプションのサイトおよびプール構成が含まれます。グローバル構成は削除できません。プール レベルの構成はサイト レベルの構成より優先されます。サイト レベルの構成はグローバル レベルの構成より優先されます。</span><span class="sxs-lookup"><span data-stu-id="2cda2-p115">**Archiving configurations**. You use one or more Archiving configurations to specify most of the Archiving options that are described previously in this topic, except for enabling archiving of internal and external communications (configured using Archiving policies, as described in the previous bullet). Archiving configurations include the default global configuration and optional site and pool configurations. You cannot delete the global configuration. Pool-level configurations override site-level configurations. Site-level configurations override the global-level configuration.</span></span>

<span data-ttu-id="2cda2-p116">要件分析の一環として、グローバル アーカイブ構成およびグローバル アーカイブ ポリシーの構成方法を決定する必要があります。さらに、サイト レベルのアーカイブ構成、プール レベルのアーカイブ構成、サイト レベルのアーカイブ ポリシー、ユーザー レベルのアーカイブ ポリシーに対する要件も決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cda2-p116">As part of your requirements analysis, you need to determine how to configure the global Archiving configuration and global Archiving policy. You also need to determine your requirements for any site-level Archiving configurations, pool-level Archiving configurations, site-level Archiving policies, and user-level Archiving policies.</span></span>

<span data-ttu-id="2cda2-p117">1 つのフロントエンド プールまたは Standard Edition サーバーにアーカイブ機能を展開する場合は、展開内の他のすべてのフロントエンド プールおよび Standard Edition サーバーに対してアーカイブを有効にすることを推奨します。これが必要なのは、通信のアーカイブが必要なユーザーが、異なるプールでホストされるグループ IM 会話や会議に招待される可能性があるためです。会話や会議がホストされているプールでアーカイブが有効になっていなければ、会議データを完全にアーカイブすることはできません。アーカイブが有効にされているユーザーについてのアーカイブは機能しますが、会議のコンテンツやイベントはアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="2cda2-p117">If you deploy Archiving for one Front End pool or Standard Edition server, you should then enable it for all other Front End pools and Standard Edition servers in your deployment. You need to do this because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool. If archiving is not enabled on the pool where the conversation or meeting is hosted, all conference data may not be archived. Archiving will still work for archiving enabled users and all IM messages, but conferencing content and events may not be archived.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2cda2-172">組織のセキュリティ標準を維持しながら管理タスクの委任を有効にするため&nbsp;に、Lync Server 2013 は役割ベースのアクセス制御 (RBAC) を使用します。</span><span class="sxs-lookup"><span data-stu-id="2cda2-172">To enable delegation of administrative tasks while maintaining your organization's security standards, Lync Server 2013&nbsp;uses role-based access control (RBAC).</span></span> <span data-ttu-id="2cda2-173">RBAC を使用すると、定義済みの管理者の役割にユーザーを割り当てることにより、管理者特権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="2cda2-173">With RBAC, administrative privilege is granted by assigning users to predefined administrative roles.</span></span> <span data-ttu-id="2cda2-174">Lync のアーカイブ ポリシーおよびアーカイブ構成を構成するには、ユーザーを CsArchivingAdministrator の役割に割り当てる必要があります (別のコンピューターからのリモートではなく、アーカイブ機能が展開されるサーバー上で構成を直接行うのでない限り)。</span><span class="sxs-lookup"><span data-stu-id="2cda2-174">To configure Lync Archiving policies and Archiving configurations, the user must be assigned to the CsArchivingAdministrator role (unless the configuration is done directly on the server where Archiving is deployed, instead of remotely from another computer).</span></span> <span data-ttu-id="2cda2-175">RBAC の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cda2-175">For details about RBAC, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="2cda2-176">アーカイブ展開に必要なユーザー権限、アクセス許可、および役割の一覧については、「計画」のドキュメントと「展開」のドキュメントの両方で利用できる「 <A href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 のアーカイブの展開チェックリスト</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cda2-176">For a list of the user rights, permissions, and roles required for archiving deployment, see <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</A>, which is available in both the Planning documentation and the Deployment documentation.</span></span><BR><span data-ttu-id="2cda2-177">Microsoft Exchange 統合を使用する場合、Exchange ポリシーを構成するには、適切な管理者権限とアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="2cda2-177">If you use Microsoft Exchange integration, configuration of Exchange policies requires appropriate administrator rights and permissions.</span></span> <span data-ttu-id="2cda2-178">詳細については、Exchange 2013 のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cda2-178">For details, see the Exchange 2013 documentation.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

