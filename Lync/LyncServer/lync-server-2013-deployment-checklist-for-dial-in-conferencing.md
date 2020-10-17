---
title: Lync Server 2013 ダイヤルイン会議の展開チェックリスト
description: Lync Server 2013 ダイヤルイン会議の展開チェックリスト。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 743b5120bf011ab8467679bea9869a46231b0835
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568363"
---
# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="e5f2a-103">Lync Server 2013 でのダイヤルイン会議の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="e5f2a-103">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5f2a-104">_**トピックの最終更新日:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="e5f2a-104">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="e5f2a-105">ダイヤルイン会議に必要なコンポーネントは、会議ワークロードを展開すると展開されます。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-105">The components required for dial-in conferencing are deployed when you deploy the conferencing workload.</span></span> <span data-ttu-id="e5f2a-106">ダイヤルイン会議を構成する前に、エンタープライズ Voip または仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイのどちらかを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-106">Before you can configure dial-in conferencing, you need to deploy either Enterprise Voice or a Mediation Server and a public switched telephone network (PSTN) gateway.</span></span>

<span data-ttu-id="e5f2a-107">ユーザーが PSTN からダイヤルインして音声ビデオ会議に参加するには、次の表のすべての手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-107">All the steps in the following table must be performed before users can dial in from the PSTN to join an audio/video conference.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e5f2a-108">Office Communications Server 2007 R2 から移行する場合は、ダイヤルイン会議を展開する前に、Office Communications Server 2007 R2 環境に最新の更新プログラムを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-108">If you are migrating from Office Communications Server 2007 R2, you must apply the latest updates to your Office Communications Server 2007 R2 environment before deploying dial-in conferencing.</span></span>



</div>

### <a name="dial-in-conferencing-deployment-process"></a><span data-ttu-id="e5f2a-109">ダイヤルイン会議の展開プロセス</span><span class="sxs-lookup"><span data-stu-id="e5f2a-109">Dial-in Conferencing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5f2a-110">フェーズ</span><span class="sxs-lookup"><span data-stu-id="e5f2a-110">Phase</span></span></th>
<th><span data-ttu-id="e5f2a-111">手順</span><span class="sxs-lookup"><span data-stu-id="e5f2a-111">Steps</span></span></th>
<th><span data-ttu-id="e5f2a-112">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="e5f2a-112">Permissions</span></span></th>
<th><span data-ttu-id="e5f2a-113">展開のドキュメント</span><span class="sxs-lookup"><span data-stu-id="e5f2a-113">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5f2a-114"><strong>仲介サーバーと PSTN ゲートウェイを含む、会議ワークロードを含むトポロジを作成し、フロントエンドプールまたは Standard Edition サーバーを展開します。</strong></span><span class="sxs-lookup"><span data-stu-id="e5f2a-114"><strong>Create a topology that includes the Conferencing workload, including a Mediation Server and PSTN gateway, and deploy the Front End pool or Standard Edition server</strong></span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="e5f2a-115">トポロジビルダーを実行してトポロジを構成します。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-115">Run Topology Builder to configure your topology.</span></span> <span data-ttu-id="e5f2a-116">トポロジの構成時に、ダイヤルイン会議オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-116">While configuring the topology, select the dial-in conferencing option.</span></span></p></li>
<li><p><span data-ttu-id="e5f2a-117">トポロジを公開し、フロントエンドプールまたは Standard Edition サーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-117">Publish the topology and deploy the Front End pool or Standard Edition server.</span></span></p></li>
<li><p><span data-ttu-id="e5f2a-118">必要に応じて、スタンドアロンの仲介サーバーを作成し、PSTN ゲートウェイに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-118">If necessary, create a stand-alone Mediation Server and associate it with a PSTN gateway.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e5f2a-119">この手順は、エンタープライズ Voip を展開せず、仲介サーバーをエンタープライズ EditionFront エンドサーバーまたは Standard Edition サーバーと併置しない場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-119">This step is required only if you do not deploy Enterprise Voice and do not collocate the Mediation Server with the Enterprise EditionFront End Server or Standard Edition server.</span></span> <span data-ttu-id="e5f2a-120">エンタープライズ Voip を展開する場合は、エンタープライズ Voip 展開の一部として、仲介サーバーと PSTN ゲートウェイをインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-120">If you deploy Enterprise Voice, you install and configure Mediation Servers and PSTN gateways as part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="e5f2a-121">仲介サーバーを併置する場合は、仲介サーバーをフロントエンドプールまたは Standard Edition サーバー展開の一部としてインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-121">If you collocate the Mediation Server, you install and configure the Mediation Server as part of the Front End pool or Standard Edition server deployment.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="e5f2a-122">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="e5f2a-122">Domain Admins</span></span></p>
<p><span data-ttu-id="e5f2a-123">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e5f2a-123">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e5f2a-124">管理者</span><span class="sxs-lookup"><span data-stu-id="e5f2a-124">Administrator</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e5f2a-125"><a href="lync-server-2013-deploying-lync-server.md">Lync Server 2013 の展開 </a></span><span class="sxs-lookup"><span data-stu-id="e5f2a-125"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="e5f2a-126">スタンドアロンの仲介サーバープールを作成するには: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">仲介サーバーの展開と Lync server 2013 でのピアの定義</a></span><span class="sxs-lookup"><span data-stu-id="e5f2a-126">To create a stand-alone Mediation Server pool: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5f2a-127"><strong>ダイヤル プランを構成する</strong></span><span class="sxs-lookup"><span data-stu-id="e5f2a-127"><strong>Configure dial plans</strong></span></span></p></td>
<td><p><span data-ttu-id="e5f2a-128">ダイヤルプランとは、電話の承認と通話のルーティングを目的として、特定の場所から1つの標準 (e.164) 形式にダイヤルする電話番号を変換する一連の電話番号正規化ルールのことです。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-128">A dial plan is a set of phone number normalization rules that translate phone numbers dialed from a specific location to a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="e5f2a-129">異なる場所からダイヤルされた同じ電話番号は、それぞれの場所に応じて、それぞれのダイヤルプランに基づいて異なる e.164 番号に解決できます。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-129">The same phone number dialed from different locations can, based on the respective dial plans, resolve to different E.164 numbers, as appropriate to each location.</span></span> <span data-ttu-id="e5f2a-130">エンタープライズ Voip を展開する場合は、ダイヤルプランをその展開の一部として設定し、ダイヤルプランがダイヤルイン会議にも対応していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-130">If you deploy Enterprise Voice, you set up dial plans as part of that deployment, and you need to make sure that the dial plans also accommodate dial-in conferencing.</span></span> <span data-ttu-id="e5f2a-131">エンタープライズ Voip を展開しない場合は、ダイヤルイン会議のダイヤルプランを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-131">If you do not deploy Enterprise Voice, you need to set up dial plans for dial-in conferencing.</span></span></p>
<p><span data-ttu-id="e5f2a-132">Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、ダイヤルプランを次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-132">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial plans as follows:</span></span></p>
<ol>
<li><p><span data-ttu-id="e5f2a-133">ダイヤルイン アクセスの電話番号をルーティングするための、1 つまたは複数のダイヤル プランを作成します。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-133">Create one or more dial plans for routing dial-in access phone numbers.</span></span></p></li>
<li><p><span data-ttu-id="e5f2a-p105">各プールに既定のダイヤル プランを割り当てます。 ダイヤル プランを適用する地理的場所に [<strong>ダイヤルイン会議の地域</strong>] を設定します。 地域がダイヤルイン アクセス番号が設定されたダイヤル プランに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-p105">Assign a default dial plan to each pool. Set the <strong>Dial-in conferencing region</strong> to the geographic location to which the dial plan applies. The region associates the dial plan with dial-in access numbers.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="e5f2a-137">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e5f2a-137">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e5f2a-138">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-138">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="e5f2a-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-139">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="e5f2a-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-140">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-141"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Lync Server 2013 でダイヤルイン会議のダイヤルプランを構成する</a></span><span class="sxs-lookup"><span data-stu-id="e5f2a-141"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configure dial plans for dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5f2a-142"><strong>ダイヤルプランに地域が割り当てられていることを確認する</strong></span><span class="sxs-lookup"><span data-stu-id="e5f2a-142"><strong>Make sure that dial plans are assigned regions</strong></span></span></p></td>
<td><p><span data-ttu-id="e5f2a-143"><strong>Get-csdialplan</strong>および<strong>get-csdialplan</strong>コマンドレットを実行して、すべてのダイヤルプランに地域が割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-143">Run the <strong>Get-CsDialPlan</strong> and <strong>Set-CsDialPlan</strong> cmdlets to make sure that all dial plans have a region assigned.</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-144">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e5f2a-144">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e5f2a-145">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-145">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="e5f2a-146">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-146">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="e5f2a-147">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-147">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-148"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">ダイヤルプラン Lync Server 2013 に地域が割り当てられていることを確認する</a></span><span class="sxs-lookup"><span data-stu-id="e5f2a-148"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Make sure dial plans Lync Server 2013 have assigned regions</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5f2a-149"><strong>(オプション) ユーザーの暗証番号 (PIN) 要件を確認または変更する</strong></span><span class="sxs-lookup"><span data-stu-id="e5f2a-149"><strong>(Optional) Verify or modify user personal identification number (PIN) requirements</strong></span></span></p></td>
<td><p><span data-ttu-id="e5f2a-150">Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、会議 <strong>PIN ポリシー</strong>を表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-150">Use Lync Server 2013 Control Panel or Lync Server Management Shell to view or modify the Conferencing <strong>PIN Policy</strong>.</span></span> <span data-ttu-id="e5f2a-151">最小 PIN サイズ、最大ログオン試行回数、PIN の有効期限、およびよくあるパターンを許可するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-151">You can specify minimum PIN length, maximum number of logon attempts, PIN expiration, and whether common patterns are allowable.</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-152">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e5f2a-152">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e5f2a-153">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-153">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="e5f2a-154">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-154">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-155"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">オプションLync Server 2013 での PIN ポリシー設定の確認</a></span><span class="sxs-lookup"><span data-stu-id="e5f2a-155"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Optional) Verify PIN policy settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5f2a-156"><strong>ダイヤルイン会議をサポートするように会議ポリシーを構成する</strong></span><span class="sxs-lookup"><span data-stu-id="e5f2a-156"><strong>Configure conferencing policy to support dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="e5f2a-157">Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、 <strong>会議ポリシー</strong> の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-157">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure <strong>Conferencing Policy</strong> settings.</span></span> <span data-ttu-id="e5f2a-158">次のことを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-158">Specify whether:</span></span></p>
<ul>
<li><p><span data-ttu-id="e5f2a-159">PSTN 会議ダイヤルインを有効にするかどうか。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-159">PSTN conference dial-in is enabled.</span></span></p></li>
<li><p><span data-ttu-id="e5f2a-160">ユーザーが匿名参加者を招待できるようにするかどうか。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-160">Users can invite anonymous participants.</span></span></p></li>
<li><p><span data-ttu-id="e5f2a-p108">認証されていないユーザーがダイヤルアウト番号を使用して会議に参加できるようにするかどうか。 会議サーバーはダイヤルアウト番号を使用してユーザーを呼び出し、ユーザーはその電話に応答し、会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-p108">Unauthenticated users can join a conference by using dial-out phoning. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e5f2a-163">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e5f2a-163">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e5f2a-164">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-164">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="e5f2a-165">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-165">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-166"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Lync Server 2013 でのダイヤルインの会議ポリシーの構成</a></span><span class="sxs-lookup"><span data-stu-id="e5f2a-166"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configure conferencing policy for dial-in in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5f2a-167"><strong>ダイヤルイン アクセス番号を構成する</strong></span><span class="sxs-lookup"><span data-stu-id="e5f2a-167"><strong>Configure dial-in access numbers</strong></span></span></p></td>
<td><p><span data-ttu-id="e5f2a-168">Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、ユーザーが電話会議にダイヤルインするためにダイヤルインアクセス番号を設定し、アクセス番号を適切なダイヤルプランに関連付ける地域を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-168">Use Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial-in access numbers that users call to dial in to a conference, and specify the regions that associate the access number with the appropriate dial plans.</span></span> <span data-ttu-id="e5f2a-169">開催者のダイヤル プランで指定されている地域の最初の 3 つのアクセス番号が会議開催通知に含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-169">The first three access numbers for the region specified by the organizer's dial plan are included in the conference invitation.</span></span> <span data-ttu-id="e5f2a-170">すべてのアクセス番号は、[ダイヤルイン会議の設定] ページで利用できます。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-170">All access numbers are available on the Dial-in Conferencing Settings page.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e5f2a-171">ダイヤルインアクセス番号を作成した後は、 <STRONG>get-csdialinconferencingaccessnumber</STRONG> コマンドレットを使用して、Active Directory 連絡先オブジェクトの表示名を変更し、ユーザーが正しいアクセス番号を容易に識別できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-171">After you create dial-in access numbers, you can use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name of the Active Directory contact objects so that users can more easily identify the correct access number.</span></span>


</div></td>
<td><p><span data-ttu-id="e5f2a-172">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e5f2a-172">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e5f2a-173">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-173">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="e5f2a-174">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-174">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-175"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Lync Server 2013 でのダイヤルイン会議アクセス番号の構成</a></span><span class="sxs-lookup"><span data-stu-id="e5f2a-175"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configure dial-in conferencing access numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5f2a-176"><strong>(オプション) ダイヤルイン会議の設定の検証</strong></span><span class="sxs-lookup"><span data-stu-id="e5f2a-176"><strong>(Optional) Verify dial-in conferencing settings</strong></span></span></p></td>
<td><p><span data-ttu-id="e5f2a-177"><strong>Get-CsDialinConferencingAccessNumber</strong> コマンドレットを使用して、地域が割り当てられていないすべてのアクセス番号に関して使用されるダイヤルイン会議の地域が設定されたダイヤル プランを検索します。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-177">Use the <strong>Get-CsDialinConferencingAccessNumber</strong> cmdlet to search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have no region assigned.</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-178">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e5f2a-178">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e5f2a-179">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-179">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="e5f2a-180">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-180">CsAdministrator</span></span></p>
<p><span data-ttu-id="e5f2a-181">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-181">CsViewOnlyAdministrator</span></span></p>
<p><span data-ttu-id="e5f2a-182">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="e5f2a-182">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-183"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">オプションLync Server 2013 でダイヤルイン会議の設定を確認する</a></span><span class="sxs-lookup"><span data-stu-id="e5f2a-183"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Optional) Verify dial-in conferencing settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5f2a-184"><strong>(オプション) DTMF コマンドの主要なマッピングを変更する</strong></span><span class="sxs-lookup"><span data-stu-id="e5f2a-184"><strong>(Optional) Modify key mapping of DTMF commands</strong></span></span></p></td>
<td><p><span data-ttu-id="e5f2a-185"><strong>Set-CsDialinConferencingDtmfConfiguration</strong> コマンドレットを使用して、デュアルトーン多重周波数 (DTMF) コマンドで使用される、参加者が会議設定 (ミュートとミュート解除、ロックとロック解除など) を制御するために使用するキーを変更します。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-185">Use the <strong>Set-CsDialinConferencingDtmfConfiguration</strong> cmdlet to modify the keys used for dual-tone multifrequency (DTMF) commands, which participants can use to control conference settings (such as mute and unmute or lock and unlock).</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-186">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e5f2a-186">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e5f2a-187">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-187">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="e5f2a-188">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-188">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-189"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">オプションLync Server 2013 での DTMF コマンドのキーマッピングの変更</a></span><span class="sxs-lookup"><span data-stu-id="e5f2a-189"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5f2a-190"><strong>(オプション) 会議の参加時と退席時のアナウンス動作を変更する</strong></span><span class="sxs-lookup"><span data-stu-id="e5f2a-190"><strong>(Optional) Modify conference join and leave announcement behavior</strong></span></span></p></td>
<td><p><span data-ttu-id="e5f2a-191"><strong>Set-CsDialinConferencingConfiguration</strong> を使用して、参加者が会議に参加および退席する際のアナウンス動作を変更します。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-191">Use the <strong>Set-CsDialinConferencingConfiguration</strong> to change how announcements work when participants join and leave conferences.</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-192">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e5f2a-192">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e5f2a-193">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-193">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="e5f2a-194">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-194">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-195"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">オプションLync Server 2013 での会議の参加と脱退のアナウンスを有効または無効にする</a></span><span class="sxs-lookup"><span data-stu-id="e5f2a-195"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5f2a-196"><strong>(オプション) ダイヤルイン会議の検証</strong></span><span class="sxs-lookup"><span data-stu-id="e5f2a-196"><strong>(Optional) Verify dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="e5f2a-197"><strong>Test-CsDialInConferencing</strong> コマンドレットを使用して、指定のプールのアクセス番号が正しく機能するかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-197">Use the <strong>Test-CsDialInConferencing</strong> cmdlet to test that the access numbers for the specified pool work correctly.</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-198">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e5f2a-198">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e5f2a-199">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-199">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="e5f2a-200">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-200">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-201"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">オプションLync Server 2013 でのダイヤルイン会議の確認</a></span><span class="sxs-lookup"><span data-stu-id="e5f2a-201"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Optional) Verify dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5f2a-202"><strong>Lync 2013 用オンライン ミーティング アドインの展開</strong></span><span class="sxs-lookup"><span data-stu-id="e5f2a-202"><strong>Deploy the Online Meeting Add-in for Lync 2013</strong></span></span></p></td>
<td><p><span data-ttu-id="e5f2a-203">ユーザーがダイヤルイン会議をサポートする会議をスケジュール設定できるように、Lync 2013 用のオンラインミーティングアドインを展開します。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-203">Deploy the Online Meeting Add-in for Lync 2013 so that users can schedule conferences that support dial-in conferencing.</span></span> <span data-ttu-id="e5f2a-204">Lync 2013 をインストールすると、Lync 2013 用のオンラインミーティングアドインが自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-204">The Online Meeting Add-in for Lync 2013 is installed automatically when you install Lync 2013.</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-205">管理者</span><span class="sxs-lookup"><span data-stu-id="e5f2a-205">Administrators</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-206"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Lync 2013 用オンライン ミーティング アドインの展開</a></span><span class="sxs-lookup"><span data-stu-id="e5f2a-206"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Deploy the Online Meeting Add-in for Lync 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5f2a-207"><strong>ユーザー アカウント設定の構成</strong></span><span class="sxs-lookup"><span data-stu-id="e5f2a-207"><strong>Configure user account settings</strong></span></span></p></td>
<td><p><span data-ttu-id="e5f2a-208">Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、テレフォニー <strong>回線 URI</strong> を正規化された一意の電話番号 (たとえば、tel: + 14255550200) として構成します。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-208">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure the telephony <strong>Line URI</strong> as a unique, normalized phone number (for example, tel:+14255550200).</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-209">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e5f2a-209">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e5f2a-210">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-210">CsAdministrator</span></span></p>
<p><span data-ttu-id="e5f2a-211">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="e5f2a-211">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-212"><a href="lync-server-2013-configure-user-account-settings.md">Lync Server 2013 でユーザーアカウント設定を構成する</a></span><span class="sxs-lookup"><span data-stu-id="e5f2a-212"><a href="lync-server-2013-configure-user-account-settings.md">Configure user account settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5f2a-213">勧め会議ディレクトリを構成する</span><span class="sxs-lookup"><span data-stu-id="e5f2a-213">(Recommended) Configure conference directories</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-214"><strong>Get-csconferencedirectory</strong>コマンドレットを使用して、プール内の999ユーザーごとに1つの会議ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-214">Use the <strong>New-CsConferenceDirectory</strong> cmdlet to create one conference directory for every 999 users in the pool.</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-215">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e5f2a-215">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-216"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013 でのダイヤルイン会議の要件</a> <a href="recommended-create-conference-directories.md">(推奨) 電話会議ディレクトリを作成する</a></span><span class="sxs-lookup"><span data-stu-id="e5f2a-216"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(Recommended) Create Conference Directories</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5f2a-217"><strong>(オプション) ユーザーにダイヤルイン会議を案内して最初の PIN を設定する</strong></span><span class="sxs-lookup"><span data-stu-id="e5f2a-217"><strong>(Optional) Welcome users to dial-in conferencing and set the initial PIN</strong></span></span></p></td>
<td><p><span data-ttu-id="e5f2a-218"><strong>Set-cspinsendcawelcomemail</strong>スクリプトを使用して、ユーザーの初期 pin を設定し、初期 Pin およびダイヤルイン会議の設定ページへのリンクを含む開始メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="e5f2a-218">Use the <strong>Set-CsPinSendCAWelcomeMail</strong> script to set users' initial PINs and send a welcome email that contains the initial PIN and a link to the Dial-in Conferencing Settings page.</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-219">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e5f2a-219">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="e5f2a-220"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">オプションLync Server 2013 でのダイヤルイン会議へのユーザーのようこそ</a></span><span class="sxs-lookup"><span data-stu-id="e5f2a-220"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

