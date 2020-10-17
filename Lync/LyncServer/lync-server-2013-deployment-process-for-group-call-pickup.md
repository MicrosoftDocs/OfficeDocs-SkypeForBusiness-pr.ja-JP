---
title: 'Lync Server 2013: グループ通話ピックアップの展開プロセス'
description: 'Lync Server 2013: グループ通話ピックアップの展開プロセス。'
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
ms.openlocfilehash: 2a01409b257c685ae71dfdb13074f2d8ea590cd9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552493"
---
# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="95d34-103">Lync Server 2013 でのグループ通話ピックアップの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="95d34-103">Deployment process for Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95d34-104">_**トピックの最終更新日:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="95d34-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="95d34-105">このセクションでは、グループ通話ピックアップの展開に必要な手順の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="95d34-105">This section provides an overview of the steps involved in deploying Group Call Pickup.</span></span> <span data-ttu-id="95d34-106">グループ通話ピックアップを構成する前に、エンタープライズ Voip を使用して Enterprise Edition または Standard Edition を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95d34-106">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Group Call Pickup.</span></span> <span data-ttu-id="95d34-107">グループ通話ピックアップで必要なコンポーネントは、エンタープライズ Voip を展開するときにインストールされて有効にされます。</span><span class="sxs-lookup"><span data-stu-id="95d34-107">The components required by Group Call Pickup are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="group-call-pickup-deployment-process"></a><span data-ttu-id="95d34-108">グループ通話ピックアップの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="95d34-108">Group Call Pickup Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95d34-109">フェーズ</span><span class="sxs-lookup"><span data-stu-id="95d34-109">Phase</span></span></th>
<th><span data-ttu-id="95d34-110">手順</span><span class="sxs-lookup"><span data-stu-id="95d34-110">Steps</span></span></th>
<th><span data-ttu-id="95d34-111">必要なグループおよび役割</span><span class="sxs-lookup"><span data-stu-id="95d34-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="95d34-112">展開のドキュメント</span><span class="sxs-lookup"><span data-stu-id="95d34-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95d34-113">トポロジで SEFAUtil リソースキットツールを有効にする</span><span class="sxs-lookup"><span data-stu-id="95d34-113">Enable the SEFAUtil resource kit tool in the topology</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="95d34-114">新しい信頼されたアプリケーションプールを作成するには、 <strong>「new-cstrustedapplicationpool</strong> コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="95d34-114">Use the <strong>New-CsTrustedApplicationPool</strong> cmdlet to create a new trusted application pool.</span></span></p></li>
<li><p><span data-ttu-id="95d34-115"><strong>「New-cstrustedapplication</strong>コマンドレットを使用して、SEFAUtil ツールを信頼済みアプリケーションとして指定します。</span><span class="sxs-lookup"><span data-stu-id="95d34-115">Use the <strong>New-CsTrustedApplication</strong> cmdlet to specify the SEFAUtil tool as trusted application.</span></span></p></li>
<li><p><span data-ttu-id="95d34-116"><strong>Enable-CsTopology</strong>コマンドレットを実行してトポロジを有効にします。</span><span class="sxs-lookup"><span data-stu-id="95d34-116">Run the <strong>Enable-CsTopology</strong> cmdlet to enable the topology.</span></span></p></li>
<li><p><span data-ttu-id="95d34-117">手順1で作成した信頼されたアプリケーションプールにあるフロントエンドサーバーに、リソースキットツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="95d34-117">Install the resource kit tools on a Front End Server that is in the trusted application pool created in step 1.</span></span></p></li>
<li><p><span data-ttu-id="95d34-118">SEFAUtil を実行して、展開内のユーザーの着信転送設定を表示することによって、正しく動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="95d34-118">Verify that SEFAUtil is running correctly by running it to display the call forwarding settings of a user in the deployment.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="95d34-119">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="95d34-119">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="95d34-120"><a href="lync-server-2013-deploy-the-sefautil-tool.md">SEFAUtil ツールを Lync Server 2013 に展開する</a></span><span class="sxs-lookup"><span data-stu-id="95d34-120"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95d34-121">コールパークオービットテーブルでの通話ピックアップ番号の範囲の構成</span><span class="sxs-lookup"><span data-stu-id="95d34-121">Configure call pickup number ranges in the call park orbit table</span></span></p></td>
<td><p><span data-ttu-id="95d34-122"><strong>Get-cscallparkorbit</strong>コマンドレットを使用して、コールパークオービットテーブルに通話ピックアップ番号の範囲を作成し、通話ピックアップの範囲を [種類] grouppickup に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="95d34-122">Use the <strong>New-CSCallParkOrbit</strong> cmdlet to create call pickup number ranges in the call park orbit table and assign the call pickup ranges the type GroupPickup.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="95d34-123">通話パークオービットテーブルでグループ通話ピックアップ番号の範囲を作成、変更、削除、表示するには、Lync Server 管理シェルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95d34-123">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="95d34-124">グループ通話ピックアップ番号の範囲は、Lync Server コントロールパネルでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="95d34-124">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="95d34-125">既存のダイヤルプランとシームレスに統合するために、通常、番号範囲は仮想内線のブロックとして構成されます。</span><span class="sxs-lookup"><span data-stu-id="95d34-125">For seamless integration with existing dial plans, number ranges are typically configured as a block of virtual extensions.</span></span> <span data-ttu-id="95d34-126">コールパークオービットテーブルで、直接内向きダイヤル (DID) 番号を範囲番号として割り当てることはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="95d34-126">Assigning Direct Inward Dialing (DID) numbers as range numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="95d34-127">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="95d34-127">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="95d34-128">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="95d34-128">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="95d34-129">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="95d34-129">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="95d34-130">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="95d34-130">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="95d34-131"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Lync Server 2013 での通話ピックアップグループ番号の構成</a></span><span class="sxs-lookup"><span data-stu-id="95d34-131"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configure call pickup group numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95d34-132">通話ピックアップ番号をユーザーに割り当て、ユーザーのグループ通話ピックアップを有効にする</span><span class="sxs-lookup"><span data-stu-id="95d34-132">Assign a call pickup number to users, and enable Group Call Pickup for the users</span></span></p></td>
<td><p><span data-ttu-id="95d34-133">グループ通話ピックアップを有効にし、ユーザーの通話ピックアップ番号を割り当てるには、SEFAUtil リソースキットツールの/enablegrouppickup パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="95d34-133">Use the /enablegrouppickup parameter in the SEFAUtil resource kit tool to enable Group Call Pickup and assign a call pickup number for users.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="95d34-134"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Lync Server 2013 のユーザーのグループ通話ピックアップを有効にし、グループ番号を割り当てる</a></span><span class="sxs-lookup"><span data-stu-id="95d34-134"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95d34-135">割り当てられた通話ピックアップ番号およびその他の任意の数のユーザーに通知する</span><span class="sxs-lookup"><span data-stu-id="95d34-135">Notify users of their assigned call pickup number and any other number of interest</span></span></p></td>
<td><p><span data-ttu-id="95d34-136">グループ通話ピックアップユーザーに対して行われた通話はすべてのユーザーが取得できるため、ユーザーは複数のグループを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95d34-136">Because any user can retrieve a call made to a Group Call Pickup user, users may want to monitor more than one group.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="95d34-137"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">グループ通話ピックアップの割り当てを Lync Server 2013 のユーザーに伝達する</a></span><span class="sxs-lookup"><span data-stu-id="95d34-137"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communicate Group Call Pickup assignments to users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95d34-138">グループ通話ピックアップの展開を確認する</span><span class="sxs-lookup"><span data-stu-id="95d34-138">Verify your Group Call Pickup deployment</span></span></p></td>
<td><p><span data-ttu-id="95d34-139">呼び出しを発信および取得して、構成が予想どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="95d34-139">Test placing and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="95d34-140"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">オプションLync Server 2013 でのグループ通話ピックアップの展開の確認</a></span><span class="sxs-lookup"><span data-stu-id="95d34-140"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

