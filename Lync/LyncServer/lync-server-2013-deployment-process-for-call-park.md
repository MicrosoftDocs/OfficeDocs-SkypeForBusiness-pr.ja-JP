---
title: 'Lync Server 2013: コールパークの展開プロセス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a00c354aa29a3c9a431b18a686105ab16d94c54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a><span data-ttu-id="1b03e-102">Lync Server 2013 でのコールパークの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="1b03e-102">Deployment process for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b03e-103">_**最終更新日:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="1b03e-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="1b03e-104">このセクションでは、コールパークアプリケーションの展開に関連する手順の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b03e-104">This section provides an overview of the steps involved in deploying the Call Park application.</span></span> <span data-ttu-id="1b03e-105">コールパークを構成する前に、enterprise Edition または Standard Edition をエンタープライズボイスと共に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b03e-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Call Park.</span></span> <span data-ttu-id="1b03e-106">エンタープライズ Voip を展開すると、コールパークに必要なコンポーネントがインストールされて有効になります。</span><span class="sxs-lookup"><span data-stu-id="1b03e-106">The components required by Call Park are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="call-park-deployment-process"></a><span data-ttu-id="1b03e-107">コール パーク展開プロセス</span><span class="sxs-lookup"><span data-stu-id="1b03e-107">Call Park Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b03e-108">フェーズ</span><span class="sxs-lookup"><span data-stu-id="1b03e-108">Phase</span></span></th>
<th><span data-ttu-id="1b03e-109">ステップ</span><span class="sxs-lookup"><span data-stu-id="1b03e-109">Steps</span></span></th>
<th><span data-ttu-id="1b03e-110">必要なグループおよび役割</span><span class="sxs-lookup"><span data-stu-id="1b03e-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="1b03e-111">「展開」のドキュメント</span><span class="sxs-lookup"><span data-stu-id="1b03e-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b03e-112">オービット テーブルでコール パーク オービット範囲を構成する</span><span class="sxs-lookup"><span data-stu-id="1b03e-112">Configure the call park orbit ranges in the orbit table</span></span></p></td>
<td><p><span data-ttu-id="1b03e-113">Lync Server コントロールパネルまたは<strong>CSCallParkOrbit</strong>コマンドレットを使用して、呼び出しパークのテーブルに軌道範囲を作成し、それを call パークアプリケーションをホストするアプリケーションサービスと関連付けます。</span><span class="sxs-lookup"><span data-stu-id="1b03e-113">Use Lync Server Control Panel or the <strong>New-CSCallParkOrbit</strong> cmdlet to create the orbit ranges in the call park orbit table and associate them with the Application service that hosts the Call Park application.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="1b03e-p102">既存のダイヤル プランとシームレスに統合するため、一般的にオービット範囲は仮想の内線番号の禁止として構成されます。コール パーク オービット テーブルでオービット番号として Direct Inward Dialing (DID) 番号を指定することは、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1b03e-p102">For seamless integration with existing dial plans, orbit ranges are typically configured as a block of virtual extensions. Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="1b03e-116">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1b03e-116">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="1b03e-117">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="1b03e-117">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="1b03e-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="1b03e-118">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="1b03e-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="1b03e-119">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1b03e-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">通話パークの作成または変更 Lync Server 2013 の範囲の軌道</a></span><span class="sxs-lookup"><span data-stu-id="1b03e-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Create or modify a Call Park orbit range in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b03e-121">コール パーク設定の構成</span><span class="sxs-lookup"><span data-stu-id="1b03e-121">Configure Call Park settings</span></span></p></td>
<td><p><span data-ttu-id="1b03e-122"><strong>CsCpsConfiguration</strong>コマンドレットを使用して、コールパーク設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="1b03e-122">Use the <strong>Set-CsCpsConfiguration</strong> cmdlet to configure Call Park settings.</span></span> <span data-ttu-id="1b03e-123">少なくとも、[ <strong>Ontimeouturi</strong> ] オプションを構成して、保留中の通話がタイムアウトしたときに使うフォールバック先を構成することをお勧めします。次の設定を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="1b03e-123">At a minimum, we recommend that you configure the <strong>OnTimeoutURI</strong> option to configure the fallback destination to use when a parked call times out. You can also configure the following settings:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b03e-124">(オプション) <strong>EnableMusicOnHold</strong> を構成して保留音を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="1b03e-124">(Optional) <strong>EnableMusicOnHold</strong> to enable or disable music on hold.</span></span></p></li>
<li><p><span data-ttu-id="1b03e-125">(オプション) <strong>MaxCallPickupAttempts</strong> を構成して、パークされた通話が、代替 Uniform Resource Identifier (URI) に転送されるまでに、応答した電話にかけ直す回数を決定します。</span><span class="sxs-lookup"><span data-stu-id="1b03e-125">(Optional) <strong>MaxCallPickupAttempts</strong> to determine the number of times a parked call rings back to the answering phone before forwarding the call to the fallback Uniform Resource Identifier (URI).</span></span></p></li>
<li><p><span data-ttu-id="1b03e-126">(オプション) <strong>CallPickupTimeoutThreshold</strong> を構成して、通話がパークされてから、呼び出しに応答した電話にかけ直されるまでの経過時間を決定します。</span><span class="sxs-lookup"><span data-stu-id="1b03e-126">(Optional) <strong>CallPickupTimeoutThreshold</strong> to determine the amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1b03e-127">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1b03e-127">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="1b03e-128">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="1b03e-128">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="1b03e-129">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="1b03e-129">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="1b03e-130">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="1b03e-130">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1b03e-131"><a href="lync-server-2013-configure-call-park-settings.md">Lync Server 2013 でのコールパーク設定の構成</a></span><span class="sxs-lookup"><span data-stu-id="1b03e-131"><a href="lync-server-2013-configure-call-park-settings.md">Configure Call Park settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b03e-132">必要に応じて、保留音をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="1b03e-132">Optionally, customize the music on hold</span></span></p></td>
<td><p><span data-ttu-id="1b03e-133">既定の保留音を使用しない場合は、<strong>Set-CsCallParkServiceMusicOnHoldFile</strong> コマンドを使用して、音声ファイルをカスタマイズおよびアップロードします。</span><span class="sxs-lookup"><span data-stu-id="1b03e-133">Use the <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> cmdlet to customize and upload an audio file, if you don't want to use the default music on hold.</span></span></p></td>
<td><p><span data-ttu-id="1b03e-134">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1b03e-134">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="1b03e-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="1b03e-135">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="1b03e-136">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="1b03e-136">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="1b03e-137">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="1b03e-137">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1b03e-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">通話パークをカスタマイズする Lync Server 2013 の保留中の音楽</a></span><span class="sxs-lookup"><span data-stu-id="1b03e-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Customize Call Park music on hold in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b03e-139">音声ポリシーを構成してユーザーのコールパークを有効にする</span><span class="sxs-lookup"><span data-stu-id="1b03e-139">Configure voice policy to enable Call Park for users</span></span></p></td>
<td><p><span data-ttu-id="1b03e-140">Lync Server コントロールパネルまたは<strong>CSVoicePolicy</strong>コマンドレットを<strong>Enablecallpark</strong>オプションと共に使用して、ボイスポリシーのユーザーに対してコールパークを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1b03e-140">Use Lync Server Control Panel or the <strong>Set-CSVoicePolicy</strong> cmdlet with the <strong>EnableCallPark</strong> option to enable Call Park for users in voice policy.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="1b03e-141">既定では、すべてのユーザーに対して [コールパーク] が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="1b03e-141">By default, Call Park is disabled for all users.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="1b03e-142">複数の音声ポリシーが存在する場合、EnableCallPark プロパティが、既定のポリシーに対してだけでなく、それぞれの音声ポリシーに設定されているのを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1b03e-142">If you have multiple voice policies, make sure the EnableCallPark property is set for each voice policy, not just for the default policy.</span></span>


</div></td>
<td><p><span data-ttu-id="1b03e-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1b03e-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="1b03e-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="1b03e-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="1b03e-145">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="1b03e-145">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="1b03e-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="1b03e-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1b03e-147"><a href="lync-server-2013-enable-call-park-for-users.md">Lync Server 2013 のユーザーに対してコールパークを有効にする</a></span><span class="sxs-lookup"><span data-stu-id="1b03e-147"><a href="lync-server-2013-enable-call-park-for-users.md">Enable Call Park for users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b03e-148">コール パーク正規化ルールの確認</span><span class="sxs-lookup"><span data-stu-id="1b03e-148">Verify normalization rules for Call Park</span></span></p></td>
<td><p><span data-ttu-id="1b03e-p104">コール パーク オービットを正規化することはできません。正規化ルールにオービット範囲が含まれていないのを確認します。必要に応じて、オービットが正規化されるのを防ぐため、追加の正規化ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="1b03e-p104">Call park orbits must not be normalized. Verify that your normalization rules do not include any of your orbit ranges. If necessary, create additional normalization rules to prevent orbits being normalized.</span></span></p></td>
<td><p><span data-ttu-id="1b03e-152">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1b03e-152">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="1b03e-153">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="1b03e-153">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="1b03e-154">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="1b03e-154">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="1b03e-155">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="1b03e-155">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1b03e-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Lync Server 2013 でのコールパークの正規化ルールを確認する</a></span><span class="sxs-lookup"><span data-stu-id="1b03e-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Verify normalization rules for Call Park in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b03e-157">コールパークの展開を確認する</span><span class="sxs-lookup"><span data-stu-id="1b03e-157">Verify your Call Park deployment</span></span></p></td>
<td><p><span data-ttu-id="1b03e-158">通話の保留と取得をテストし、構成が予想どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="1b03e-158">Test parking and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="1b03e-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">省略Lync Server 2013 でのコールパークの展開を確認する</a></span><span class="sxs-lookup"><span data-stu-id="1b03e-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">(Optional) Verify Call Park deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

