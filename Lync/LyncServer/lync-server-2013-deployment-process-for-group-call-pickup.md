---
title: 'Lync Server 2013: グループ通話ピックアップの展開プロセス'
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
ms.openlocfilehash: 52f7646010e4048d135e11c98d06a651f923d633
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522614"
---
# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="00fbd-102">Lync Server 2013 でのグループ通話ピックアップの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="00fbd-102">Deployment process for Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00fbd-103">_**トピックの最終更新日:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="00fbd-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="00fbd-104">このセクションでは、グループ通話ピックアップの展開に必要な手順の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="00fbd-104">This section provides an overview of the steps involved in deploying Group Call Pickup.</span></span> <span data-ttu-id="00fbd-105">グループ通話ピックアップを構成する前に、エンタープライズ Voip を使用して Enterprise Edition または Standard Edition を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00fbd-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Group Call Pickup.</span></span> <span data-ttu-id="00fbd-106">グループ通話ピックアップで必要なコンポーネントは、エンタープライズ Voip を展開するときにインストールされて有効にされます。</span><span class="sxs-lookup"><span data-stu-id="00fbd-106">The components required by Group Call Pickup are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="group-call-pickup-deployment-process"></a><span data-ttu-id="00fbd-107">グループ通話ピックアップの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="00fbd-107">Group Call Pickup Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00fbd-108">フェーズ</span><span class="sxs-lookup"><span data-stu-id="00fbd-108">Phase</span></span></th>
<th><span data-ttu-id="00fbd-109">手順</span><span class="sxs-lookup"><span data-stu-id="00fbd-109">Steps</span></span></th>
<th><span data-ttu-id="00fbd-110">必要なグループおよび役割</span><span class="sxs-lookup"><span data-stu-id="00fbd-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="00fbd-111">展開のドキュメント</span><span class="sxs-lookup"><span data-stu-id="00fbd-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00fbd-112">トポロジで SEFAUtil リソースキットツールを有効にする</span><span class="sxs-lookup"><span data-stu-id="00fbd-112">Enable the SEFAUtil resource kit tool in the topology</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="00fbd-113">新しい信頼されたアプリケーションプールを作成するには、 <strong>「new-cstrustedapplicationpool</strong> コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="00fbd-113">Use the <strong>New-CsTrustedApplicationPool</strong> cmdlet to create a new trusted application pool.</span></span></p></li>
<li><p><span data-ttu-id="00fbd-114"><strong>「New-cstrustedapplication</strong>コマンドレットを使用して、SEFAUtil ツールを信頼済みアプリケーションとして指定します。</span><span class="sxs-lookup"><span data-stu-id="00fbd-114">Use the <strong>New-CsTrustedApplication</strong> cmdlet to specify the SEFAUtil tool as trusted application.</span></span></p></li>
<li><p><span data-ttu-id="00fbd-115"><strong>Enable-CsTopology</strong>コマンドレットを実行してトポロジを有効にします。</span><span class="sxs-lookup"><span data-stu-id="00fbd-115">Run the <strong>Enable-CsTopology</strong> cmdlet to enable the topology.</span></span></p></li>
<li><p><span data-ttu-id="00fbd-116">手順1で作成した信頼されたアプリケーションプールにあるフロントエンドサーバーに、リソースキットツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="00fbd-116">Install the resource kit tools on a Front End Server that is in the trusted application pool created in step 1.</span></span></p></li>
<li><p><span data-ttu-id="00fbd-117">SEFAUtil を実行して、展開内のユーザーの着信転送設定を表示することによって、正しく動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="00fbd-117">Verify that SEFAUtil is running correctly by running it to display the call forwarding settings of a user in the deployment.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="00fbd-118">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="00fbd-118">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="00fbd-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">SEFAUtil ツールを Lync Server 2013 に展開する</a></span><span class="sxs-lookup"><span data-stu-id="00fbd-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00fbd-120">コールパークオービットテーブルでの通話ピックアップ番号の範囲の構成</span><span class="sxs-lookup"><span data-stu-id="00fbd-120">Configure call pickup number ranges in the call park orbit table</span></span></p></td>
<td><p><span data-ttu-id="00fbd-121"><strong>Get-cscallparkorbit</strong>コマンドレットを使用して、コールパークオービットテーブルに通話ピックアップ番号の範囲を作成し、通話ピックアップの範囲を [種類] grouppickup に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="00fbd-121">Use the <strong>New-CSCallParkOrbit</strong> cmdlet to create call pickup number ranges in the call park orbit table and assign the call pickup ranges the type GroupPickup.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="00fbd-122">通話パークオービットテーブルでグループ通話ピックアップ番号の範囲を作成、変更、削除、表示するには、Lync Server 管理シェルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00fbd-122">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="00fbd-123">グループ通話ピックアップ番号の範囲は、Lync Server コントロールパネルでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="00fbd-123">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="00fbd-124">既存のダイヤルプランとシームレスに統合するために、通常、番号範囲は仮想内線のブロックとして構成されます。</span><span class="sxs-lookup"><span data-stu-id="00fbd-124">For seamless integration with existing dial plans, number ranges are typically configured as a block of virtual extensions.</span></span> <span data-ttu-id="00fbd-125">コールパークオービットテーブルで、直接内向きダイヤル (DID) 番号を範囲番号として割り当てることはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="00fbd-125">Assigning Direct Inward Dialing (DID) numbers as range numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="00fbd-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="00fbd-126">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="00fbd-127">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="00fbd-127">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="00fbd-128">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="00fbd-128">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="00fbd-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="00fbd-129">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="00fbd-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Lync Server 2013 での通話ピックアップグループ番号の構成</a></span><span class="sxs-lookup"><span data-stu-id="00fbd-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configure call pickup group numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00fbd-131">通話ピックアップ番号をユーザーに割り当て、ユーザーのグループ通話ピックアップを有効にする</span><span class="sxs-lookup"><span data-stu-id="00fbd-131">Assign a call pickup number to users, and enable Group Call Pickup for the users</span></span></p></td>
<td><p><span data-ttu-id="00fbd-132">グループ通話ピックアップを有効にし、ユーザーの通話ピックアップ番号を割り当てるには、SEFAUtil リソースキットツールの/enablegrouppickup パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="00fbd-132">Use the /enablegrouppickup parameter in the SEFAUtil resource kit tool to enable Group Call Pickup and assign a call pickup number for users.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="00fbd-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Lync Server 2013 のユーザーのグループ通話ピックアップを有効にし、グループ番号を割り当てる</a></span><span class="sxs-lookup"><span data-stu-id="00fbd-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00fbd-134">割り当てられた通話ピックアップ番号およびその他の任意の数のユーザーに通知する</span><span class="sxs-lookup"><span data-stu-id="00fbd-134">Notify users of their assigned call pickup number and any other number of interest</span></span></p></td>
<td><p><span data-ttu-id="00fbd-135">グループ通話ピックアップユーザーに対して行われた通話はすべてのユーザーが取得できるため、ユーザーは複数のグループを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00fbd-135">Because any user can retrieve a call made to a Group Call Pickup user, users may want to monitor more than one group.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="00fbd-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">グループ通話ピックアップの割り当てを Lync Server 2013 のユーザーに伝達する</a></span><span class="sxs-lookup"><span data-stu-id="00fbd-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communicate Group Call Pickup assignments to users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00fbd-137">グループ通話ピックアップの展開を確認する</span><span class="sxs-lookup"><span data-stu-id="00fbd-137">Verify your Group Call Pickup deployment</span></span></p></td>
<td><p><span data-ttu-id="00fbd-138">呼び出しを発信および取得して、構成が予想どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="00fbd-138">Test placing and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="00fbd-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">オプションLync Server 2013 でのグループ通話ピックアップの展開の確認</a></span><span class="sxs-lookup"><span data-stu-id="00fbd-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

