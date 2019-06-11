---
title: 'Lync Server 2013: 応答グループの障害復旧の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70622364349eb83ecbc171cb3d5bf894ba03d3f9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="7c740-102">Lync Server 2013 での応答グループの障害復旧の計画</span><span class="sxs-lookup"><span data-stu-id="7c740-102">Planning for response group disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c740-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7c740-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7c740-104">このセクションでは、障害回復のための応答グループを準備する方法について説明し、障害回復プロセスの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="7c740-104">This section describes some ways to prepare response groups for disaster recovery and provides an overview of the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a><span data-ttu-id="7c740-105">回答グループの障害回復の準備</span><span class="sxs-lookup"><span data-stu-id="7c740-105">Preparing for Response Group Disaster Recovery</span></span>

<span data-ttu-id="7c740-106">災害回復の手順を準備し、実行する場合は、次の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="7c740-106">Keep the following in mind when you prepare for and carry out disaster recovery procedures.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7c740-107">共存環境では、このドキュメントで説明されているディザスタリカバリの手順については、Lync Server 2013 応答グループのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7c740-107">In a coexistence environment, only the Lync Server 2013 response groups are supported for the disaster recovery procedures described in this document.</span></span>



</div>

  - <span data-ttu-id="7c740-108">キャパシティ計画を行うときの障害回復計画を立てます。</span><span class="sxs-lookup"><span data-stu-id="7c740-108">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="7c740-109">障害回復キャパシティの場合、ペア化されたプール内の各プールは、両方のプールのすべての応答グループのワークロードを処理できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c740-109">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of all the response groups in both pools.</span></span> <span data-ttu-id="7c740-110">回答グループのキャパシティ計画の詳細については、「 [Lync Server 2013 の応答グループのキャパシティ計画](lync-server-2013-capacity-planning-for-response-group.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c740-110">For details about Response Group capacity planning, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span></span>

  - <span data-ttu-id="7c740-111">このドキュメントで説明されているエクスポート手順を使用して、応答グループアプリケーションを展開したすべての [返信グループ] 構成の定期的なバックアップコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="7c740-111">Take regular backup copies of all the response group configurations in all the Front End pools where you deployed the Response Group application by using the export procedure described in this document.</span></span> <span data-ttu-id="7c740-112">詳細については、「 [Lync Server 2013 での応答グループの障害回復の手順](lync-server-2013-response-group-disaster-recovery-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c740-112">For details, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span> <span data-ttu-id="7c740-113">バックアップコピーを安全な場所に保管します。</span><span class="sxs-lookup"><span data-stu-id="7c740-113">Keep the backup copies in a safe location.</span></span>

  - <span data-ttu-id="7c740-114">応答グループアプリケーションに使用した元のすべてのオーディオファイルのバックアップコピーを個別に保存しておきます。レコーディングや音楽の保留ファイルも含めます。</span><span class="sxs-lookup"><span data-stu-id="7c740-114">Keep a separate backup copy of all the original audio files you used for the Response Group application, including any recordings and music-on-hold files.</span></span> <span data-ttu-id="7c740-115">バックアップファイルを安全な場所に保管します。</span><span class="sxs-lookup"><span data-stu-id="7c740-115">Keep the backup files in a safe location.</span></span>

  - <span data-ttu-id="7c740-116">Lync Server 2013 の障害回復の場合、すべての応答グループの設定で、展開時に一意の名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c740-116">For Lync Server 2013 disaster recovery, all Response Group settings must have unique names across your deployment.</span></span> <span data-ttu-id="7c740-117">この要件は、ワークフロー、キュー、エージェントグループ、休日セット、および営業時間に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7c740-117">This requirement applies to workflows, queues, agent groups, holiday sets, and hours of business.</span></span> <span data-ttu-id="7c740-118">プライマリとバックアップのプールがアクティブで、フェールオーバー手順を開始する前に、この要件が満たされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c740-118">You should verify that this requirement is met when the primary and backup pools are still active, and before you need to initiate any failover procedure.</span></span> <span data-ttu-id="7c740-119">応答グループデータをバックアッププールにインポートするときに名前の競合が発生した場合、インポートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="7c740-119">If you encounter name conflicts while importing response group data to the backup pool, the import fails.</span></span> <span data-ttu-id="7c740-120">インポートとフェールオーバーの手順を完了するには、バックアッププール内の応答グループオブジェクトの名前を変更するか、– ResolveNameConflicts パラメーターを指定して**import/CsRgsConfiguration**コマンドレットを使用して、名前の競合を解決する必要があります。応答グループオブジェクトに一意の識別番号を追加して、競合を解決します。</span><span class="sxs-lookup"><span data-stu-id="7c740-120">To complete the import and failover procedure, you need to resolve the name conflicts by renaming the response group object in the backup pool or by using the **Import-CsRgsConfiguration** cmdlet with the –ResolveNameConflicts parameter to automatically resolve the conflict by appending a unique identifying number to the response group object.</span></span>

  - <span data-ttu-id="7c740-121">一般的に、毎日のバックアップを実行することをお勧めしますが、変更の量が多い場合は、より頻繁にバックアップをスケジュールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7c740-121">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="7c740-122">障害が発生した場合に失われる可能性のある情報の量は、バックアップの頻度と、変更の頻度と量によって異なります。</span><span class="sxs-lookup"><span data-stu-id="7c740-122">The amount of information you can lose in the event of a disaster depends on the frequency of your backups, as well as the frequency and volume of changes.</span></span>

  - <span data-ttu-id="7c740-123">ディザスタまたはフェイルオーバー操作が発生する前に、バックアッププールに応答グループをインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="7c740-123">It is possible to import response groups to a backup pool before a disaster or failover operation occurs.</span></span> <span data-ttu-id="7c740-124">返信グループの事前インポートは、通話がバックアッププールにルーティングされるとすぐに、Lync Server 応答グループサービスをバックアッププールで復元できるため、ダウンタイムが短縮されます。</span><span class="sxs-lookup"><span data-stu-id="7c740-124">Importing response groups in advance reduces downtime, because the Lync Server Response Group service can be restored in the backup pool as soon as calls are routed to the backup pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7c740-125">フェールオーバーが完了するまで、応答グループのアプリケーションは、非アクティブなプールに所属しているエージェントに到達できません。</span><span class="sxs-lookup"><span data-stu-id="7c740-125">The Response Group application cannot reach any agents homed in an inactive pool until failover is complete.</span></span> <span data-ttu-id="7c740-126">このとき、応答グループアプリケーションは、それらのエージェントが利用できない場合と同様に呼び出しを処理します。</span><span class="sxs-lookup"><span data-stu-id="7c740-126">During this time, the Response Group application processes calls as if those agents are unavailable.</span></span>

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a><span data-ttu-id="7c740-127">応答グループの障害回復プロセス</span><span class="sxs-lookup"><span data-stu-id="7c740-127">Response Group Disaster Recovery Process</span></span>

<span data-ttu-id="7c740-128">障害が発生した場合は、次のいずれかの回復方法を使用して応答グループを回復できます。</span><span class="sxs-lookup"><span data-stu-id="7c740-128">In the event of a disaster, you can recover response groups by using either of the following recovery approaches:</span></span>

  - <span data-ttu-id="7c740-129">バックアッププールにフェイルオーバーし、元のプールにフェイルバックします。</span><span class="sxs-lookup"><span data-stu-id="7c740-129">Fail over to a backup pool and then fail back to the original pool.</span></span>

  - <span data-ttu-id="7c740-130">バックアッププールにフェールオーバーする場合は、別の完全修飾ドメイン名 (FQDN) を使用して新しいプールを作成し、新しいプールに応答グループをインポートします。</span><span class="sxs-lookup"><span data-stu-id="7c740-130">Fail over to a backup pool, create a new pool with a different fully qualified domain name (FQDN), and then import the response groups to the new pool.</span></span>

<span data-ttu-id="7c740-131">障害回復のフェールオーバーフェーズでは、応答グループは、プライマリプール (使用できない) とバックアッププールの複数のプールに存在します。</span><span class="sxs-lookup"><span data-stu-id="7c740-131">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="7c740-132">両方のプールの応答グループの名前が同じであり、所有者が同じ所有者 (プライマリプール) であるが、それぞれの親が異なっている。</span><span class="sxs-lookup"><span data-stu-id="7c740-132">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span>

<span data-ttu-id="7c740-133">別の FQDN で新しいプールを作成して回復する場合は、新しいプールをインポートするときに、応答グループの所有者として割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c740-133">When you recover by creating a new pool with a different FQDN, you need to assign the new pool as the owner of the response groups when you import them.</span></span> <span data-ttu-id="7c740-134">応答グループの所有権は、**インポート-CsRgsConfiguration**コマンドレットを使用して– OverwriteOwner パラメーターを使って明示的に所有権を再割り当てする場合を除き、元のプールのままになります。</span><span class="sxs-lookup"><span data-stu-id="7c740-134">Ownership of response groups remains with the original pool unless or until you explicitly reassign ownership by using the –OverwriteOwner parameter with the **Import-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7c740-135">また、回復中にプールを再構築した場合 (つまり、応答グループのデータベースが空である場合)、同じ FQDN を使用しているかどうかにかかわらず、– OverwriteOwner パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c740-135">You also need to use the –OverwriteOwner parameter if you rebuilt the pool during the recovery (that is, the Response Group database is empty), whether or not you use the same FQDN.</span></span> <span data-ttu-id="7c740-136">プールをリビルドしていない場合は、– OverwriteOwner パラメーターを使う必要はありませんが、応答グループをプライマリプールにインポートするたびに、このパラメーターを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="7c740-136">You do not need to use the –OverwriteOwner parameter if you did not rebuild the pool, but it is permissible to use this parameter whenever you import response groups back to the primary pool.</span></span>



</div>

<span data-ttu-id="7c740-137">プールごとに1つのアプリケーションレベル応答グループ構成設定のみを定義できます。</span><span class="sxs-lookup"><span data-stu-id="7c740-137">You can define only one set of application-level Response Group configuration settings per pool.</span></span> <span data-ttu-id="7c740-138">これらの設定には、既定の音楽保留の構成、既定の音楽保留中のオーディオファイル、エージェント ringback の猶予期間、通話コンテキストの構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7c740-138">These settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="7c740-139">これらの構成設定を表示するには、 **Get-CsRgsConfiguration**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7c740-139">To view these configuration settings, run the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="7c740-140">**Get-csrgsconfiguration**コマンドレットの詳細については、「 [Get-csrgsconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c740-140">For details about the **Get-CsRgsConfiguration** cmdlet, see [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span></span>

<span data-ttu-id="7c740-141">これらのアプリケーションレベルの設定は、– ReplaceExistingSettings パラメーターを指定して**Import-CsRgsConfiguration**コマンドレットを使用して、1つのプールから別のプールに転送できますが、これにより、移動先のプールの設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="7c740-141">You can transfer these application-level settings from one pool to another by using the **Import-CsRgsConfiguration** cmdlet with the –ReplaceExistingSettings parameter, but doing so overrides the settings in the destination pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7c740-142">他のプールへの設定の転送に関するこの制約は、アプリケーションレベルの設定、および既定の音楽/ホールドオーディオファイルに対してのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="7c740-142">This constraint about transferring settings to another pool is true only for the application-level settings and the default music-on-hold audio file.</span></span> <span data-ttu-id="7c740-143">エージェントグループ、キュー、ワークフロー、業務時間、休日セットには適用されません。</span><span class="sxs-lookup"><span data-stu-id="7c740-143">It does not apply to agent groups, queues, workflows, business hours, and holiday sets.</span></span>



</div>

<span data-ttu-id="7c740-144">障害発生時にバックアッププールのアプリケーションレベルの設定を変更せずに、プライマリプールを復元できない場合、プライマリプールのアプリケーションレベルの設定は失われます。</span><span class="sxs-lookup"><span data-stu-id="7c740-144">If you don't want to replace the application-level settings in the backup pool during a disaster and the primary pool can't be recovered, the application-level settings from the primary pool will be lost.</span></span> <span data-ttu-id="7c740-145">新しいプールを作成して回復中にプライマリプールを置き換える必要がある場合は、同じ FQDN または別の FQDN を使用して、元のアプリケーションレベルの設定を復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="7c740-145">If you need to create a new pool to replace the primary pool during recovery, either with the same FQDN or with a different FQDN, you can't recover the original application-level settings.</span></span> <span data-ttu-id="7c740-146">この場合は、これらの設定を使用して新しいプールを構成し、音楽の保留中のオーディオファイルを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c740-146">In this case, you need to configure the new pool with these settings and include the music-on-hold audio file.</span></span>

<span data-ttu-id="7c740-147">**インポート-CsRgsConfiguration**コマンドレットを使用して、障害が発生したときに、プライマリプールからバックアッププールにアプリケーションレベルの設定を転送することにした場合、回復中にバックアッププールから新しいプールに設定を転送することができます。プライマリプールからバックアッププールに転送された方法。</span><span class="sxs-lookup"><span data-stu-id="7c740-147">If you decide to use the **Import-CsRgsConfiguration** cmdlet to transfer application-level settings from the primary pool to the backup pool during a disaster, you can then transfer the settings from the backup pool to the new pool during recovery in the same way that you transferred them from the primary pool to the backup pool.</span></span>

<span data-ttu-id="7c740-148">次の表では、応答グループの回復に関連する手順の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="7c740-148">The following table is an overview of the steps involved in recovering response groups.</span></span>

<span data-ttu-id="7c740-149">これらの手順の実行について詳しくは、「 [Lync Server 2013 の応答グループの障害回復手順](lync-server-2013-response-group-disaster-recovery-procedures.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7c740-149">For details about performing these steps, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span>

### <a name="response-group-disaster-recovery-steps"></a><span data-ttu-id="7c740-150">応答グループの障害回復手順</span><span class="sxs-lookup"><span data-stu-id="7c740-150">Response Group Disaster Recovery Steps</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c740-151">段階</span><span class="sxs-lookup"><span data-stu-id="7c740-151">Phase</span></span></th>
<th><span data-ttu-id="7c740-152">ステップ</span><span class="sxs-lookup"><span data-stu-id="7c740-152">Steps</span></span></th>
<th><span data-ttu-id="7c740-153">必要なグループおよび役割</span><span class="sxs-lookup"><span data-stu-id="7c740-153">Required groups and roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c740-154">停止前</span><span class="sxs-lookup"><span data-stu-id="7c740-154">Before outage</span></span></p></td>
<td><p><span data-ttu-id="7c740-155">ルーチンベースでは、 <strong>Export-CsRgsConfiguration</strong>コマンドレットを実行して、応答グループアプリケーションが展開されているすべてのフロントエンドプールですべての応答グループの構成のバックアップを作成します。</span><span class="sxs-lookup"><span data-stu-id="7c740-155">On a routine basis, run the <strong>Export-CsRgsConfiguration</strong> cmdlet to create backups of all Response Group configurations in all Front End pools where Response Group application is deployed.</span></span></p></td>
<td><p><span data-ttu-id="7c740-156">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7c740-156">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="7c740-157">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="7c740-157">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c740-158">停止中</span><span class="sxs-lookup"><span data-stu-id="7c740-158">During outage</span></span></p></td>
<td><p><span data-ttu-id="7c740-159"><strong>インポート-CsRgsConfiguration</strong>コマンドレットを実行し、プライマリプールからバックアッププールに、バックアップされた Lync Server 応答グループサービスの構成をインポートします。</span><span class="sxs-lookup"><span data-stu-id="7c740-159">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the backed up Lync Server Response Group service configuration from the primary pool to the backup pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="7c740-160">バックアッププールのアプリケーションレベルの応答グループの設定をプライマリプールの設定で置き換える場合は、– ReplaceExistingSettings パラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="7c740-160">Use the –ReplaceExistingSettings parameter if you want to replace application-level Response Group settings in the backup pool with the settings from the primary pool.</span></span> <span data-ttu-id="7c740-161">アプリケーションレベルの設定をプライマリプールからバックアッププールに転送せず、プライマリプールを復元できない場合、プライマリプールの設定は失われます。</span><span class="sxs-lookup"><span data-stu-id="7c740-161">If you do not transfer the application-level settings from the primary pool to the backup pool, and the primary pool can't be recovered, you will lose the settings from the primary pool.</span></span>


</div></td>
<td><p><span data-ttu-id="7c740-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7c740-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="7c740-163">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="7c740-163">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c740-164">インポート後</span><span class="sxs-lookup"><span data-stu-id="7c740-164">After importing</span></span></p></td>
<td><p><span data-ttu-id="7c740-165">応答グループのコマンドレットを実行するには、– ShowAll パラメーター (すべての応答グループを表示) または– Owner パラメーター (インポートされた応答グループのみを表示) を使用して、すべての応答グループの構成がバックアッププールにインポートされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7c740-165">Run Response Group cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were imported to the backup pool.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="7c740-166">– ShowAll パラメーターまたは– Owner パラメーターのいずれも使用しない場合、バックアッププールにインポートした応答グループは、コマンドレットによって返された結果に一覧表示されません。</span><span class="sxs-lookup"><span data-stu-id="7c740-166">If you do not use either the –ShowAll parameter or the –Owner parameter, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>


</div>
<p><span data-ttu-id="7c740-167">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7c740-167">Run the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="7c740-168"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="7c740-168"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="7c740-169"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="7c740-169"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="7c740-170"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="7c740-170"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="7c740-171"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="7c740-171"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="7c740-172"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="7c740-172"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7c740-173">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7c740-173">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="7c740-174">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="7c740-174">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c740-175">フェールオーバー後</span><span class="sxs-lookup"><span data-stu-id="7c740-175">After failover</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7c740-176">バックアッププールにインポートされた応答グループにテスト通話を発信し、通話が正しく処理されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7c740-176">Place a test call to a response group that was imported to the backup pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="7c740-177">すべての正式なエージェントは、バックアッププールの正式グループにもう一度サインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c740-177">All formal agents must sign in again to their formal groups on backup pool.</span></span></p></li>
<li><p><span data-ttu-id="7c740-178">構成の変更を管理します。</span><span class="sxs-lookup"><span data-stu-id="7c740-178">Manage configuration changes:</span></span></p>
<p><span data-ttu-id="7c740-179">バックアッププール内の応答グループ (バックアッププールにインポートされているかバックアッププールによって所有されているか) は、停止中に通常どおり変更できます。</span><span class="sxs-lookup"><span data-stu-id="7c740-179">Response groups in the backup pool, whether imported to the backup pool or owned by the backup pool, can be modified as usual during the outage.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="7c740-180">バックアッププールにインポートした応答グループを管理するには、Lync Server 管理シェルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c740-180">You must use Lync Server Management Shell to manage the response groups that you imported to the backup pool.</span></span> <span data-ttu-id="7c740-181">Lync Server コントロールパネルを使用して、バックアッププール内の応答グループを管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="7c740-181">You cannot use Lync Server Control Panel to manage these response groups while they are in the backup pool.</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="7c740-182">N/A</span><span class="sxs-lookup"><span data-stu-id="7c740-182">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c740-183">回復後、フェールバック前</span><span class="sxs-lookup"><span data-stu-id="7c740-183">After recovery, before failback</span></span></p></td>
<td><p><span data-ttu-id="7c740-184"><strong>エクスポート-CsRgsConfiguration</strong>コマンドレットを実行して、バックアッププールとして-Source パラメーターを指定し、プライマリプールとして-Owner パラメーターを指定して、バックアッププールからプライマリプールに所有されている応答グループをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="7c740-184">Run the <strong>Export-CsRgsConfiguration</strong> cmdlet specifying the -Source parameter as the backup pool and the –Owner parameter as the primary pool to export the response groups owned by the primary pool from the backup pool.</span></span></p></td>
<td><p><span data-ttu-id="7c740-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7c740-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="7c740-186">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="7c740-186">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c740-187">フェイルバック後</span><span class="sxs-lookup"><span data-stu-id="7c740-187">After failback</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7c740-188"><strong>インポート-CsRgsConfiguration</strong>コマンドレットを実行して、応答グループをプライマリプールにインポートします。</span><span class="sxs-lookup"><span data-stu-id="7c740-188">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the response groups back to the primary pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="7c740-189">プライマリプールを復元できず、新しいプールを展開して置き換える場合は、– ReplaceExistingSettings パラメーターを使用して、アプリケーションレベルの設定をバックアッププールから新しいプールに転送します。</span><span class="sxs-lookup"><span data-stu-id="7c740-189">If the primary pool can't be recovered and you deploy a new pool to replace it, use the –ReplaceExistingSettings parameter to transfer the application-level settings from the backup pool to the new pool.</span></span> <span data-ttu-id="7c740-190">バックアッププールから設定を転送しない場合、新しいプールでは既定の設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7c740-190">If you do not transfer the settings from the backup pool, the new pool will use the default settings.</span></span>


</div></li>
<li><p><span data-ttu-id="7c740-191">次のコマンドレットを実行するには、– ShowAll パラメーター (すべての応答グループを表示) または– Owner パラメーター (インポートされた応答グループのみを表示) を使用して、すべての応答グループの構成が正常にプライマリプールにインポートされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7c740-191">Run the following cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were successfully imported back to the primary pool:</span></span></p>
<ul>
<li><p><span data-ttu-id="7c740-192"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="7c740-192"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="7c740-193"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="7c740-193"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="7c740-194"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="7c740-194"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="7c740-195"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="7c740-195"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="7c740-196"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="7c740-196"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="7c740-197">プライマリプールにインポートされた応答グループにテスト通話を発信し、通話が正しく処理されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7c740-197">Place a test call to a response group that was imported back to the primary pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="7c740-198">必要に応じて、– RemoveExportedConfiguration パラメーターを指定して、バックアッププールに対して<strong>Export-CsRgsConfiguration</strong>コマンドレットを実行し、プライマリプールによって所有されている応答グループをバックアッププールから削除します。</span><span class="sxs-lookup"><span data-stu-id="7c740-198">Optionally, run the <strong>Export-CsRgsConfiguration</strong> cmdlet on the backup pool with the –RemoveExportedConfiguration parameter to remove the response groups owned by the primary pool from the backup pool.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7c740-199">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7c740-199">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="7c740-200">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="7c740-200">CsResponseGroupAdministrator</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

