---
title: 'Lync Server 2013: 応答グループの障害復旧の計画'
description: 'Lync Server 2013: 応答グループの障害復旧の計画。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5294ddf7dbd42d95c5eb17acd6be6a5abc7a5917
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549263"
---
# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="d462e-103">Lync Server 2013 での応答グループの障害復旧の計画</span><span class="sxs-lookup"><span data-stu-id="d462e-103">Planning for response group disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d462e-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d462e-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d462e-105">このセクションでは、応答グループの障害復旧を準備する方法について説明し、障害復旧プロセスの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="d462e-105">This section describes some ways to prepare response groups for disaster recovery and provides an overview of the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a><span data-ttu-id="d462e-106">応答グループの障害復旧の準備</span><span class="sxs-lookup"><span data-stu-id="d462e-106">Preparing for Response Group Disaster Recovery</span></span>

<span data-ttu-id="d462e-107">障害復旧手順を準備および実施する場合、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="d462e-107">Keep the following in mind when you prepare for and carry out disaster recovery procedures.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d462e-108">共存環境では、このドキュメントで説明されている障害回復手順で Lync Server 2013 応答グループのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d462e-108">In a coexistence environment, only the Lync Server 2013 response groups are supported for the disaster recovery procedures described in this document.</span></span>



</div>

  - <span data-ttu-id="d462e-109">障害復旧の計画は、処理能力の計画時に行います。</span><span class="sxs-lookup"><span data-stu-id="d462e-109">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="d462e-110">障害復旧の処理能力については、ペアにしたプールのそれぞれのプールで、両方のプールのすべての応答グループの負荷を処理できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d462e-110">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of all the response groups in both pools.</span></span> <span data-ttu-id="d462e-111">応答グループの容量計画の詳細については、「 [capacity planning For Response group In Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d462e-111">For details about Response Group capacity planning, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span></span>

  - <span data-ttu-id="d462e-112">このドキュメントで説明されているエクスポート手順を使用して、応答グループアプリケーションを展開したすべてのフロントエンドプールで、すべての応答グループ構成のバックアップコピーを定期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="d462e-112">Take regular backup copies of all the response group configurations in all the Front End pools where you deployed the Response Group application by using the export procedure described in this document.</span></span> <span data-ttu-id="d462e-113">詳細については、「 [Lync Server 2013 の応答グループの障害復旧手順](lync-server-2013-response-group-disaster-recovery-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d462e-113">For details, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span> <span data-ttu-id="d462e-114">そのバックアップは安全な場所に保管します。</span><span class="sxs-lookup"><span data-stu-id="d462e-114">Keep the backup copies in a safe location.</span></span>

  - <span data-ttu-id="d462e-115">応答グループアプリケーションで使用したすべての元のオーディオファイル (レコーディングファイルや音楽オンリストファイルを含む) の個別のバックアップコピーを保持します。</span><span class="sxs-lookup"><span data-stu-id="d462e-115">Keep a separate backup copy of all the original audio files you used for the Response Group application, including any recordings and music-on-hold files.</span></span> <span data-ttu-id="d462e-116">そのバックアップ ファイルは安全な場所に保管します。</span><span class="sxs-lookup"><span data-stu-id="d462e-116">Keep the backup files in a safe location.</span></span>

  - <span data-ttu-id="d462e-117">Lync Server 2013 の障害復旧の場合、すべての応答グループの設定には、展開全体で一意の名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d462e-117">For Lync Server 2013 disaster recovery, all Response Group settings must have unique names across your deployment.</span></span> <span data-ttu-id="d462e-118">この要件は、ワークフロー、キュー、エージェント グループ、休日セット、および営業時間に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d462e-118">This requirement applies to workflows, queues, agent groups, holiday sets, and hours of business.</span></span> <span data-ttu-id="d462e-119">プライマリ プールとバックアップ プールがまだアクティブで、フェールオーバー手順の開始が必要になる前に、この要件が満たされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d462e-119">You should verify that this requirement is met when the primary and backup pools are still active, and before you need to initiate any failover procedure.</span></span> <span data-ttu-id="d462e-120">バックアップ プールに応答グループ データをインポートするときに名前の競合が発生するとインポートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="d462e-120">If you encounter name conflicts while importing response group data to the backup pool, the import fails.</span></span> <span data-ttu-id="d462e-121">インポートとフェールオーバー手順を完了するには、バックアップ プールの応答グループ オブジェクトの名前を変更して名前の競合を解決するか、**Import-CsRgsConfiguration** コマンドレットに -ResolveNameConflicts パラメーターを使用することによって応答グループ オブジェクトに一意の識別番号を追加する方法で競合を自動解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d462e-121">To complete the import and failover procedure, you need to resolve the name conflicts by renaming the response group object in the backup pool or by using the **Import-CsRgsConfiguration** cmdlet with the –ResolveNameConflicts parameter to automatically resolve the conflict by appending a unique identifying number to the response group object.</span></span>

  - <span data-ttu-id="d462e-p105">一般に、毎日バックアップを行うことをお勧めしますが、変更が多い場合は、より頻度の高いバックアップのスケジュールが必要になることもあります。障害発生時に失われる情報の量は、バックアップの頻度および変更の頻度と量に左右されます。</span><span class="sxs-lookup"><span data-stu-id="d462e-p105">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups. The amount of information you can lose in the event of a disaster depends on the frequency of your backups, as well as the frequency and volume of changes.</span></span>

  - <span data-ttu-id="d462e-124">障害またはフェールオーバー処理が発生する前に、応答グループをバックアップ プールにインポートしておくことができます。</span><span class="sxs-lookup"><span data-stu-id="d462e-124">It is possible to import response groups to a backup pool before a disaster or failover operation occurs.</span></span> <span data-ttu-id="d462e-125">応答グループを事前にインポートすると、通話がバックアッププールにルーティングされると直ちに Lync Server Response Group service がバックアッププールに復元されるため、ダウンタイムが減少します。</span><span class="sxs-lookup"><span data-stu-id="d462e-125">Importing response groups in advance reduces downtime, because the Lync Server Response Group service can be restored in the backup pool as soon as calls are routed to the backup pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d462e-126">応答グループアプリケーションは、フェールオーバーが完了するまで非アクティブなプールに所属するエージェントに到達できません。</span><span class="sxs-lookup"><span data-stu-id="d462e-126">The Response Group application cannot reach any agents homed in an inactive pool until failover is complete.</span></span> <span data-ttu-id="d462e-127">この間、応答グループアプリケーションは、それらのエージェントが利用できない場合と同じように通話を処理します。</span><span class="sxs-lookup"><span data-stu-id="d462e-127">During this time, the Response Group application processes calls as if those agents are unavailable.</span></span>

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a><span data-ttu-id="d462e-128">応答グループの障害復旧プロセス</span><span class="sxs-lookup"><span data-stu-id="d462e-128">Response Group Disaster Recovery Process</span></span>

<span data-ttu-id="d462e-129">障害が発生した場合、次の回復アプローチで応答グループを回復できます。</span><span class="sxs-lookup"><span data-stu-id="d462e-129">In the event of a disaster, you can recover response groups by using either of the following recovery approaches:</span></span>

  - <span data-ttu-id="d462e-130">バックアップ プールにフェールオーバーし、次に元のプールにフェールバックします。</span><span class="sxs-lookup"><span data-stu-id="d462e-130">Fail over to a backup pool and then fail back to the original pool.</span></span>

  - <span data-ttu-id="d462e-131">バックアップ プールにフェールオーバーし、異なる完全修飾ドメイン名 (FQDN) を持つ新しいプールを作成し、その新しいプールに応答グループをインポートします。</span><span class="sxs-lookup"><span data-stu-id="d462e-131">Fail over to a backup pool, create a new pool with a different fully qualified domain name (FQDN), and then import the response groups to the new pool.</span></span>

<span data-ttu-id="d462e-p108">障害復旧のフェールオーバー フェーズ中、応答グループは (使用できない) プライマリ プールとバックアップ プールという複数のプールに存在します。どちらのプールでも応答グループの名前と所有者 (プライマリ プール) は同じですが、その親は異なります。</span><span class="sxs-lookup"><span data-stu-id="d462e-p108">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool. The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span>

<span data-ttu-id="d462e-134">異なる FQDN を持つ新しいプールを作成して回復する場合、応答グループをインポートするときにその所有者として新しいプールを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d462e-134">When you recover by creating a new pool with a different FQDN, you need to assign the new pool as the owner of the response groups when you import them.</span></span> <span data-ttu-id="d462e-135">**Import-CsRgsConfiguration** コマンドレットに -OverwriteOwner パラメーターを指定して所有権を明示的に割り当て直さない限り、応答グループの所有権は引き続き元のプールにあります。</span><span class="sxs-lookup"><span data-stu-id="d462e-135">Ownership of response groups remains with the original pool unless or until you explicitly reassign ownership by using the –OverwriteOwner parameter with the **Import-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d462e-136">また、同じ FQDN を使用するかどうかにかかわらず、回復中にプールを再構築した場合 (つまり、応答グループデータベースが空の場合) は、– OverwriteOwner パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d462e-136">You also need to use the –OverwriteOwner parameter if you rebuilt the pool during the recovery (that is, the Response Group database is empty), whether or not you use the same FQDN.</span></span> <span data-ttu-id="d462e-137">プールを構築し直さなかった場合には -OverwriteOwner パラメーターを使用する必要はありませんが、応答グループをプライマリ プールにインポートして戻す場合はこのパラメーターを使用することが許容されます。</span><span class="sxs-lookup"><span data-stu-id="d462e-137">You do not need to use the –OverwriteOwner parameter if you did not rebuild the pool, but it is permissible to use this parameter whenever you import response groups back to the primary pool.</span></span>



</div>

<span data-ttu-id="d462e-138">プールごとに定義できるアプリケーションレベルの応答グループ構成設定は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="d462e-138">You can define only one set of application-level Response Group configuration settings per pool.</span></span> <span data-ttu-id="d462e-139">このような設定として、既定の保留音の構成、既定の保留音オーディオ ファイル、エージェントかけ直し猶予期間、呼び出しコンテキストの構成があります。</span><span class="sxs-lookup"><span data-stu-id="d462e-139">These settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="d462e-140">これらの構成設定を表示するには、**Get-CsRgsConfiguration** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="d462e-140">To view these configuration settings, run the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="d462e-141">**Get-help**コマンドレットの詳細については、「 [get-help](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d462e-141">For details about the **Get-CsRgsConfiguration** cmdlet, see [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span></span>

<span data-ttu-id="d462e-142">これらのアプリケーション レベル設定は、**Import-CsRgsConfiguration** コマンドレットに -ReplaceExistingSettings パラメーターを指定するとプールから別のプールへ転送できますが、それによって転送先プールの設定はオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="d462e-142">You can transfer these application-level settings from one pool to another by using the **Import-CsRgsConfiguration** cmdlet with the –ReplaceExistingSettings parameter, but doing so overrides the settings in the destination pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d462e-p112">設定を別のプールへ転送する場合のこの制約は、アプリケーション レベル設定と既定の保留音オーディオ ファイルのみに適用されます。エージェント グループ、キュー、ワークフロー、営業時間、および休日セットには適用されません。</span><span class="sxs-lookup"><span data-stu-id="d462e-p112">This constraint about transferring settings to another pool is true only for the application-level settings and the default music-on-hold audio file. It does not apply to agent groups, queues, workflows, business hours, and holiday sets.</span></span>



</div>

<span data-ttu-id="d462e-p113">障害時にバックアップ プールのアプリケーション レベル設定を置き換えないようにすると、プライマリ プールを回復できない場合にプライマリ プールのアプリケーション レベル設定は失われます。回復時にプライマリ プールを置き換えるために新しいプールを作成する必要がある場合、それが同じ FQDN を持つか異なる FQDN を持つかに関係なく、元のアプリケーション レベル設定は回復できません。この場合、新しいプールにこれらの設定を構成し、保留音オーディオ ファイルを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d462e-p113">If you don't want to replace the application-level settings in the backup pool during a disaster and the primary pool can't be recovered, the application-level settings from the primary pool will be lost. If you need to create a new pool to replace the primary pool during recovery, either with the same FQDN or with a different FQDN, you can't recover the original application-level settings. In this case, you need to configure the new pool with these settings and include the music-on-hold audio file.</span></span>

<span data-ttu-id="d462e-148">障害時に **Import-CsRgsConfiguration** コマンドレットを使用してプライマリ プールからバックアップ プールにアプリケーション レベル設定を転送する場合は、その後の回復時に、プライマリ プールからバックアップ プールに転送したときと同じ方法でバックアップ プールから新しいプールに設定を転送できます。</span><span class="sxs-lookup"><span data-stu-id="d462e-148">If you decide to use the **Import-CsRgsConfiguration** cmdlet to transfer application-level settings from the primary pool to the backup pool during a disaster, you can then transfer the settings from the backup pool to the new pool during recovery in the same way that you transferred them from the primary pool to the backup pool.</span></span>

<span data-ttu-id="d462e-149">応答グループを回復するステップの概要を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="d462e-149">The following table is an overview of the steps involved in recovering response groups.</span></span>

<span data-ttu-id="d462e-150">これらの手順の実行の詳細については、「 [Lync Server 2013 の応答グループの障害復旧手順](lync-server-2013-response-group-disaster-recovery-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d462e-150">For details about performing these steps, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span>

### <a name="response-group-disaster-recovery-steps"></a><span data-ttu-id="d462e-151">応答グループの障害復旧ステップ</span><span class="sxs-lookup"><span data-stu-id="d462e-151">Response Group Disaster Recovery Steps</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d462e-152">フェーズ</span><span class="sxs-lookup"><span data-stu-id="d462e-152">Phase</span></span></th>
<th><span data-ttu-id="d462e-153">手順</span><span class="sxs-lookup"><span data-stu-id="d462e-153">Steps</span></span></th>
<th><span data-ttu-id="d462e-154">必要なグループおよび役割</span><span class="sxs-lookup"><span data-stu-id="d462e-154">Required groups and roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d462e-155">停止前</span><span class="sxs-lookup"><span data-stu-id="d462e-155">Before outage</span></span></p></td>
<td><p><span data-ttu-id="d462e-156">定期的に、 <strong>Export-CsRgsConfiguration</strong> コマンドレットを実行して、応答グループアプリケーションが展開されているすべてのフロントエンドプールですべての応答グループ構成のバックアップを作成します。</span><span class="sxs-lookup"><span data-stu-id="d462e-156">On a routine basis, run the <strong>Export-CsRgsConfiguration</strong> cmdlet to create backups of all Response Group configurations in all Front End pools where Response Group application is deployed.</span></span></p></td>
<td><p><span data-ttu-id="d462e-157">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d462e-157">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="d462e-158">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="d462e-158">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d462e-159">停止中</span><span class="sxs-lookup"><span data-stu-id="d462e-159">During outage</span></span></p></td>
<td><p><span data-ttu-id="d462e-160"><strong>Import-CsRgsConfiguration</strong>コマンドレットを実行して、バックアップされた Lync Server 応答グループサービスの構成をプライマリプールからバックアッププールにインポートします。</span><span class="sxs-lookup"><span data-stu-id="d462e-160">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the backed up Lync Server Response Group service configuration from the primary pool to the backup pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d462e-161">バックアッププールのアプリケーションレベルの応答グループの設定をプライマリプールの設定と置き換える場合は、-ReplaceExistingSettings パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d462e-161">Use the –ReplaceExistingSettings parameter if you want to replace application-level Response Group settings in the backup pool with the settings from the primary pool.</span></span> <span data-ttu-id="d462e-162">プライマリ プールのアプリケーション レベル設定をバックアップ プールに転送しないと、プライマリ プールを回復できない場合にプライマリ プールの設定は失われます。</span><span class="sxs-lookup"><span data-stu-id="d462e-162">If you do not transfer the application-level settings from the primary pool to the backup pool, and the primary pool can't be recovered, you will lose the settings from the primary pool.</span></span>


</div></td>
<td><p><span data-ttu-id="d462e-163">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d462e-163">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="d462e-164">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="d462e-164">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d462e-165">インポート後</span><span class="sxs-lookup"><span data-stu-id="d462e-165">After importing</span></span></p></td>
<td><p><span data-ttu-id="d462e-166">-ShowAll パラメーター (すべての応答グループを表示する場合) または-Owner パラメーター (インポートされた応答グループのみを表示する場合) のいずれかを使用して応答グループのコマンドレットを実行し、すべての応答グループの構成がバックアッププールにインポートされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d462e-166">Run Response Group cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were imported to the backup pool.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="d462e-167">-ShowAll パラメーターも -Owner パラメーターも指定しない場合、バックアップ プールにインポートされた応答グループは、コマンドレットから返される結果に表示されません。</span><span class="sxs-lookup"><span data-stu-id="d462e-167">If you do not use either the –ShowAll parameter or the –Owner parameter, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>


</div>
<p><span data-ttu-id="d462e-168">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="d462e-168">Run the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="d462e-169"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="d462e-169"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="d462e-170"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="d462e-170"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="d462e-171"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="d462e-171"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="d462e-172"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="d462e-172"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="d462e-173"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="d462e-173"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d462e-174">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d462e-174">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="d462e-175">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="d462e-175">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d462e-176">フェールオーバー後</span><span class="sxs-lookup"><span data-stu-id="d462e-176">After failover</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d462e-177">バックアップ プールにインポートした応答グループへテスト通話を行い、通話が適切に処理されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d462e-177">Place a test call to a response group that was imported to the backup pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="d462e-178">すべての公式エージェントは、バックアップ プール上の公式グループに再度サインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d462e-178">All formal agents must sign in again to their formal groups on backup pool.</span></span></p></li>
<li><p><span data-ttu-id="d462e-179">構成の変更を管理します。</span><span class="sxs-lookup"><span data-stu-id="d462e-179">Manage configuration changes:</span></span></p>
<p><span data-ttu-id="d462e-180">バックアップ プールにインポートされるかバックアップ プールに所有されているためにバックアップ プールに含まれる応答グループは、障害時にも通常どおりに変更できます。</span><span class="sxs-lookup"><span data-stu-id="d462e-180">Response groups in the backup pool, whether imported to the backup pool or owned by the backup pool, can be modified as usual during the outage.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="d462e-181">バックアッププールにインポートした応答グループを管理するには、Lync Server 管理シェルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d462e-181">You must use Lync Server Management Shell to manage the response groups that you imported to the backup pool.</span></span> <span data-ttu-id="d462e-182">Lync Server コントロールパネルを使用して、バックアッププールにあるときにこれらの応答グループを管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="d462e-182">You cannot use Lync Server Control Panel to manage these response groups while they are in the backup pool.</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="d462e-183">該当なし</span><span class="sxs-lookup"><span data-stu-id="d462e-183">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d462e-184">回復後、フェールバック前</span><span class="sxs-lookup"><span data-stu-id="d462e-184">After recovery, before failback</span></span></p></td>
<td><p><span data-ttu-id="d462e-185">-Source パラメーターにバックアップ プール、-Owner パラメーターにプライマリ プールを指定して <strong>Export-CsRgsConfiguration</strong> コマンドレットを実行し、プライマリ プールに所有される応答グループをバックアップ プールからエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d462e-185">Run the <strong>Export-CsRgsConfiguration</strong> cmdlet specifying the -Source parameter as the backup pool and the –Owner parameter as the primary pool to export the response groups owned by the primary pool from the backup pool.</span></span></p></td>
<td><p><span data-ttu-id="d462e-186">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d462e-186">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="d462e-187">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="d462e-187">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d462e-188">フェールバック後</span><span class="sxs-lookup"><span data-stu-id="d462e-188">After failback</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d462e-189"><strong>Import-CsRgsConfiguration</strong> コマンドレットを実行して、応答グループをプライマリ プールにインポートして戻します。</span><span class="sxs-lookup"><span data-stu-id="d462e-189">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the response groups back to the primary pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d462e-p116">プライマリ プールを回復できない場合に新しいプールを展開してそれを置き換えるには、-ReplaceExistingSettings パラメーターを使用してバックアップ プールのアプリケーション レベル設定を新しいプールに転送します。バックアップ プールから設定を転送しないと、新しいプールでは既定の設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d462e-p116">If the primary pool can't be recovered and you deploy a new pool to replace it, use the –ReplaceExistingSettings parameter to transfer the application-level settings from the backup pool to the new pool. If you do not transfer the settings from the backup pool, the new pool will use the default settings.</span></span>


</div></li>
<li><p><span data-ttu-id="d462e-192">次のコマンドレットに -ShowAll パラメーター (すべての応答グループを表示する場合) または -Owner パラメーター (インポートされた応答グループのみを表示する場合) を指定して実行し、すべての応答グループ構成がプライマリ プールに正常にインポートして戻されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d462e-192">Run the following cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were successfully imported back to the primary pool:</span></span></p>
<ul>
<li><p><span data-ttu-id="d462e-193"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="d462e-193"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="d462e-194"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="d462e-194"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="d462e-195"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="d462e-195"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="d462e-196"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="d462e-196"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="d462e-197"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="d462e-197"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="d462e-198">プライマリ プールにインポートして戻した応答グループへテスト通話を行い、通話が適切に処理されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d462e-198">Place a test call to a response group that was imported back to the primary pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="d462e-199">必要に応じて、バックアップ プールで -RemoveExportedConfiguration パラメーターを指定して <strong>Export-CsRgsConfiguration</strong> コマンドレットを実行して、プライマリ プールに所有されている応答グループをバックアップ プールから削除します。</span><span class="sxs-lookup"><span data-stu-id="d462e-199">Optionally, run the <strong>Export-CsRgsConfiguration</strong> cmdlet on the backup pool with the –RemoveExportedConfiguration parameter to remove the response groups owned by the primary pool from the backup pool.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d462e-200">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d462e-200">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="d462e-201">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="d462e-201">CsResponseGroupAdministrator</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

