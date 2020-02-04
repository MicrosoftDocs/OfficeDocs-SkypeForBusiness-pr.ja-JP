---
title: 'Lync Server 2013: グループ通話のピックアップの展開プロセス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 015aa2817b7d829d1714288182775b42ba2bb1f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="8a758-102">Lync Server 2013 でのグループ通話のピックアップの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="8a758-102">Deployment process for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a758-103">_**最終更新日:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="8a758-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="8a758-104">このセクションでは、グループ通話のピックアップの展開に関連する手順の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="8a758-104">This section provides an overview of the steps involved in deploying Group Call Pickup.</span></span> <span data-ttu-id="8a758-105">グループ通話のピックアップを構成する前に、enterprise Edition または Standard Edition をエンタープライズボイスと共に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a758-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Group Call Pickup.</span></span> <span data-ttu-id="8a758-106">エンタープライズ Voip を展開すると、グループ通話のピックアップに必要なコンポーネントがインストールされて有効になります。</span><span class="sxs-lookup"><span data-stu-id="8a758-106">The components required by Group Call Pickup are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="group-call-pickup-deployment-process"></a><span data-ttu-id="8a758-107">グループ通話ピックアップの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="8a758-107">Group Call Pickup Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a758-108">フェーズ</span><span class="sxs-lookup"><span data-stu-id="8a758-108">Phase</span></span></th>
<th><span data-ttu-id="8a758-109">ステップ</span><span class="sxs-lookup"><span data-stu-id="8a758-109">Steps</span></span></th>
<th><span data-ttu-id="8a758-110">必要なグループおよび役割</span><span class="sxs-lookup"><span data-stu-id="8a758-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="8a758-111">「展開」のドキュメント</span><span class="sxs-lookup"><span data-stu-id="8a758-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a758-112">トポロジで SEFAUtil リソースキットツールを有効にする</span><span class="sxs-lookup"><span data-stu-id="8a758-112">Enable the SEFAUtil resource kit tool in the topology</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="8a758-113"><strong>New-CsTrustedApplicationPool</strong> コマンドレットを使用して、新しい信頼済みアプリケーション プールを作成します。</span><span class="sxs-lookup"><span data-stu-id="8a758-113">Use the <strong>New-CsTrustedApplicationPool</strong> cmdlet to create a new trusted application pool.</span></span></p></li>
<li><p><span data-ttu-id="8a758-114"><strong>New-CsTrustedApplication</strong> コマンドレットを使用して、SEFAUtil ツールを信頼済みアプリケーションとして指定します。</span><span class="sxs-lookup"><span data-stu-id="8a758-114">Use the <strong>New-CsTrustedApplication</strong> cmdlet to specify the SEFAUtil tool as trusted application.</span></span></p></li>
<li><p><span data-ttu-id="8a758-115"><strong>Enable-CsTopology</strong> コマンドレットを実行して、トポロジを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8a758-115">Run the <strong>Enable-CsTopology</strong> cmdlet to enable the topology.</span></span></p></li>
<li><p><span data-ttu-id="8a758-116">手順1で作成した信頼されたアプリケーションプール内のフロントエンドサーバーにリソースキットツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8a758-116">Install the resource kit tools on a Front End Server that is in the trusted application pool created in step 1.</span></span></p></li>
<li><p><span data-ttu-id="8a758-117">SEFAUtil を実行し、展開内のユーザーの着信の転送設定を表示して、SEFAUtil が適切に実行されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a758-117">Verify that SEFAUtil is running correctly by running it to display the call forwarding settings of a user in the deployment.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="8a758-118">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="8a758-118">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="8a758-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8a758-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a758-120">コール パーク オービット テーブルに通話ピックアップの番号範囲を構成する</span><span class="sxs-lookup"><span data-stu-id="8a758-120">Configure call pickup number ranges in the call park orbit table</span></span></p></td>
<td><p><span data-ttu-id="8a758-121"><strong>CSCallParkOrbit</strong>コマンドレットを使用して、通話パークの番号の範囲を作成し、通話のピックアップの範囲を「grouppickup」として割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8a758-121">Use the <strong>New-CSCallParkOrbit</strong> cmdlet to create call pickup number ranges in the call park orbit table and assign the call pickup ranges the type GroupPickup.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="8a758-122">通話パークの軌道の番号範囲を作成、変更、削除、および表示するには、Lync Server 管理シェルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a758-122">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="8a758-123">グループ通話の集配番号の範囲は Lync Server コントロールパネルでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="8a758-123">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="8a758-p103">既存のダイヤル プランとシームレスに統合するため、番号範囲は、通常、仮想の内線番号のブロックとして構成されます。コール パーク オービット テーブルで Direct Inward Dialing (DID) 番号を範囲番号として指定することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8a758-p103">For seamless integration with existing dial plans, number ranges are typically configured as a block of virtual extensions. Assigning Direct Inward Dialing (DID) numbers as range numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="8a758-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="8a758-126">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="8a758-127">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="8a758-127">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="8a758-128">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="8a758-128">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="8a758-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="8a758-129">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="8a758-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Lync Server 2013 での通話ピックアップグループ番号の設定</a></span><span class="sxs-lookup"><span data-stu-id="8a758-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configure call pickup group numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a758-131">通話集配番号をユーザーに割り当てて、ユーザーに対してグループ通話のピックアップを有効にする</span><span class="sxs-lookup"><span data-stu-id="8a758-131">Assign a call pickup number to users, and enable Group Call Pickup for the users</span></span></p></td>
<td><p><span data-ttu-id="8a758-132">SEFAUtil リソースキットツールの/enablegrouppickup パラメーターを使用して、グループ通話のピックアップを有効にし、ユーザーに通話の集配番号を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8a758-132">Use the /enablegrouppickup parameter in the SEFAUtil resource kit tool to enable Group Call Pickup and assign a call pickup number for users.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="8a758-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Lync Server 2013 のユーザーに対してグループ通話のピックアップを有効にし、グループ番号を割り当てる</a></span><span class="sxs-lookup"><span data-stu-id="8a758-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a758-134">割り当てられた通話ピックアップ番号をユーザーに通知し、必要な他の番号があるかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="8a758-134">Notify users of their assigned call pickup number and any other number of interest</span></span></p></td>
<td><p><span data-ttu-id="8a758-135">グループ通話のピックアップユーザーに発信された通話は、ユーザーが取得することができるため、ユーザーは複数のグループを監視する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="8a758-135">Because any user can retrieve a call made to a Group Call Pickup user, users may want to monitor more than one group.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="8a758-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">グループ通話の集配の課題を Lync Server 2013 のユーザーに伝える</a></span><span class="sxs-lookup"><span data-stu-id="8a758-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communicate Group Call Pickup assignments to users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a758-137">グループ通話の集配の展開を確認する</span><span class="sxs-lookup"><span data-stu-id="8a758-137">Verify your Group Call Pickup deployment</span></span></p></td>
<td><p><span data-ttu-id="8a758-138">通話の発信と取得をテストし、構成が予想どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a758-138">Test placing and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="8a758-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">省略Lync Server 2013 でグループ通話のピックアップの展開を確認する</a></span><span class="sxs-lookup"><span data-stu-id="8a758-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

