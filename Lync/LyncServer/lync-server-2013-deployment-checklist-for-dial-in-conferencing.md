---
title: Lync Server 2013 ダイヤルイン会議の展開チェックリスト
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
ms.openlocfilehash: dc1cbf5d732cbd30ac7d59e3bcedafadb0759ce2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="ff6f7-102">Lync Server 2013 でのダイヤルイン会議の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="ff6f7-102">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff6f7-103">_**トピックの最終更新日:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="ff6f7-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="ff6f7-104">ダイヤルイン会議に必要なコンポーネントは、会議ワークロードを展開すると展開されます。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-104">The components required for dial-in conferencing are deployed when you deploy the conferencing workload.</span></span> <span data-ttu-id="ff6f7-105">ダイヤルイン会議を構成する前に、エンタープライズ Voip または仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイのどちらかを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-105">Before you can configure dial-in conferencing, you need to deploy either Enterprise Voice or a Mediation Server and a public switched telephone network (PSTN) gateway.</span></span>

<span data-ttu-id="ff6f7-106">ユーザーが PSTN からダイヤルインして音声ビデオ会議に参加するには、次の表のすべての手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-106">All the steps in the following table must be performed before users can dial in from the PSTN to join an audio/video conference.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff6f7-107">Office Communications Server 2007 R2 から移行する場合は、ダイヤルイン会議を展開する前に、Office Communications Server 2007 R2 環境に最新の更新プログラムを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-107">If you are migrating from Office Communications Server 2007 R2, you must apply the latest updates to your Office Communications Server 2007 R2 environment before deploying dial-in conferencing.</span></span>



</div>

### <a name="dial-in-conferencing-deployment-process"></a><span data-ttu-id="ff6f7-108">ダイヤルイン会議の展開プロセス</span><span class="sxs-lookup"><span data-stu-id="ff6f7-108">Dial-in Conferencing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff6f7-109">フェーズ</span><span class="sxs-lookup"><span data-stu-id="ff6f7-109">Phase</span></span></th>
<th><span data-ttu-id="ff6f7-110">手順</span><span class="sxs-lookup"><span data-stu-id="ff6f7-110">Steps</span></span></th>
<th><span data-ttu-id="ff6f7-111">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ff6f7-111">Permissions</span></span></th>
<th><span data-ttu-id="ff6f7-112">展開のドキュメント</span><span class="sxs-lookup"><span data-stu-id="ff6f7-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff6f7-113"><strong>仲介サーバーと PSTN ゲートウェイを含む、会議ワークロードを含むトポロジを作成し、フロントエンドプールまたは Standard Edition サーバーを展開します。</strong></span><span class="sxs-lookup"><span data-stu-id="ff6f7-113"><strong>Create a topology that includes the Conferencing workload, including a Mediation Server and PSTN gateway, and deploy the Front End pool or Standard Edition server</strong></span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="ff6f7-114">トポロジビルダーを実行してトポロジを構成します。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-114">Run Topology Builder to configure your topology.</span></span> <span data-ttu-id="ff6f7-115">トポロジの構成時に、ダイヤルイン会議オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-115">While configuring the topology, select the dial-in conferencing option.</span></span></p></li>
<li><p><span data-ttu-id="ff6f7-116">トポロジを公開し、フロントエンドプールまたは Standard Edition サーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-116">Publish the topology and deploy the Front End pool or Standard Edition server.</span></span></p></li>
<li><p><span data-ttu-id="ff6f7-117">必要に応じて、スタンドアロンの仲介サーバーを作成し、PSTN ゲートウェイに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-117">If necessary, create a stand-alone Mediation Server and associate it with a PSTN gateway.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="ff6f7-118">この手順は、エンタープライズ Voip を展開せず、仲介サーバーをエンタープライズ EditionFront エンドサーバーまたは Standard Edition サーバーと併置しない場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-118">This step is required only if you do not deploy Enterprise Voice and do not collocate the Mediation Server with the Enterprise EditionFront End Server or Standard Edition server.</span></span> <span data-ttu-id="ff6f7-119">エンタープライズ Voip を展開する場合は、エンタープライズ Voip 展開の一部として、仲介サーバーと PSTN ゲートウェイをインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-119">If you deploy Enterprise Voice, you install and configure Mediation Servers and PSTN gateways as part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="ff6f7-120">仲介サーバーを併置する場合は、仲介サーバーをフロントエンドプールまたは Standard Edition サーバー展開の一部としてインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-120">If you collocate the Mediation Server, you install and configure the Mediation Server as part of the Front End pool or Standard Edition server deployment.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="ff6f7-121">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="ff6f7-121">Domain Admins</span></span></p>
<p><span data-ttu-id="ff6f7-122">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ff6f7-122">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ff6f7-123">管理者</span><span class="sxs-lookup"><span data-stu-id="ff6f7-123">Administrator</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ff6f7-124"><a href="lync-server-2013-deploying-lync-server.md">Lync Server 2013 の展開 </a></span><span class="sxs-lookup"><span data-stu-id="ff6f7-124"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="ff6f7-125">スタンドアロンの仲介サーバープールを作成するには:<a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">仲介サーバーの展開と Lync server 2013 でのピアの定義</a></span><span class="sxs-lookup"><span data-stu-id="ff6f7-125">To create a stand-alone Mediation Server pool: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff6f7-126"><strong>ダイヤル プランを構成する</strong></span><span class="sxs-lookup"><span data-stu-id="ff6f7-126"><strong>Configure dial plans</strong></span></span></p></td>
<td><p><span data-ttu-id="ff6f7-127">ダイヤルプランとは、電話の承認と通話のルーティングを目的として、特定の場所から1つの標準 (e.164) 形式にダイヤルする電話番号を変換する一連の電話番号正規化ルールのことです。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-127">A dial plan is a set of phone number normalization rules that translate phone numbers dialed from a specific location to a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="ff6f7-128">異なる場所からダイヤルされた同じ電話番号は、それぞれの場所に応じて、それぞれのダイヤルプランに基づいて異なる e.164 番号に解決できます。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-128">The same phone number dialed from different locations can, based on the respective dial plans, resolve to different E.164 numbers, as appropriate to each location.</span></span> <span data-ttu-id="ff6f7-129">エンタープライズ Voip を展開する場合は、ダイヤルプランをその展開の一部として設定し、ダイヤルプランがダイヤルイン会議にも対応していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-129">If you deploy Enterprise Voice, you set up dial plans as part of that deployment, and you need to make sure that the dial plans also accommodate dial-in conferencing.</span></span> <span data-ttu-id="ff6f7-130">エンタープライズ Voip を展開しない場合は、ダイヤルイン会議のダイヤルプランを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-130">If you do not deploy Enterprise Voice, you need to set up dial plans for dial-in conferencing.</span></span></p>
<p><span data-ttu-id="ff6f7-131">Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、ダイヤルプランを次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-131">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial plans as follows:</span></span></p>
<ol>
<li><p><span data-ttu-id="ff6f7-132">ダイヤルイン アクセスの電話番号をルーティングするための、1 つまたは複数のダイヤル プランを作成します。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-132">Create one or more dial plans for routing dial-in access phone numbers.</span></span></p></li>
<li><p><span data-ttu-id="ff6f7-p105">各プールに既定のダイヤル プランを割り当てます。 ダイヤル プランを適用する地理的場所に [<strong>ダイヤルイン会議の地域</strong>] を設定します。 地域がダイヤルイン アクセス番号が設定されたダイヤル プランに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-p105">Assign a default dial plan to each pool. Set the <strong>Dial-in conferencing region</strong> to the geographic location to which the dial plan applies. The region associates the dial plan with dial-in access numbers.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="ff6f7-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ff6f7-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ff6f7-137">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-137">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="ff6f7-138">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-138">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="ff6f7-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Lync Server 2013 でダイヤルイン会議のダイヤルプランを構成する</a></span><span class="sxs-lookup"><span data-stu-id="ff6f7-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configure dial plans for dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff6f7-141"><strong>ダイヤルプランに地域が割り当てられていることを確認する</strong></span><span class="sxs-lookup"><span data-stu-id="ff6f7-141"><strong>Make sure that dial plans are assigned regions</strong></span></span></p></td>
<td><p><span data-ttu-id="ff6f7-142"><strong>Get-csdialplan</strong>および<strong>get-csdialplan</strong>コマンドレットを実行して、すべてのダイヤルプランに地域が割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-142">Run the <strong>Get-CsDialPlan</strong> and <strong>Set-CsDialPlan</strong> cmdlets to make sure that all dial plans have a region assigned.</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ff6f7-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ff6f7-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="ff6f7-145">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-145">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="ff6f7-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">ダイヤルプラン Lync Server 2013 に地域が割り当てられていることを確認する</a></span><span class="sxs-lookup"><span data-stu-id="ff6f7-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Make sure dial plans Lync Server 2013 have assigned regions</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff6f7-148"><strong>(オプション) ユーザーの暗証番号 (PIN) 要件を確認または変更する</strong></span><span class="sxs-lookup"><span data-stu-id="ff6f7-148"><strong>(Optional) Verify or modify user personal identification number (PIN) requirements</strong></span></span></p></td>
<td><p><span data-ttu-id="ff6f7-149">Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、会議<strong>PIN ポリシー</strong>を表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-149">Use Lync Server 2013 Control Panel or Lync Server Management Shell to view or modify the Conferencing <strong>PIN Policy</strong>.</span></span> <span data-ttu-id="ff6f7-150">最小 PIN サイズ、最大ログオン試行回数、PIN の有効期限、およびよくあるパターンを許可するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-150">You can specify minimum PIN length, maximum number of logon attempts, PIN expiration, and whether common patterns are allowable.</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-151">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ff6f7-151">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ff6f7-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="ff6f7-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">オプションLync Server 2013 での PIN ポリシー設定の確認</a></span><span class="sxs-lookup"><span data-stu-id="ff6f7-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Optional) Verify PIN policy settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff6f7-155"><strong>ダイヤルイン会議をサポートするように会議ポリシーを構成する</strong></span><span class="sxs-lookup"><span data-stu-id="ff6f7-155"><strong>Configure conferencing policy to support dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="ff6f7-156">Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、<strong>会議ポリシー</strong>の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-156">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure <strong>Conferencing Policy</strong> settings.</span></span> <span data-ttu-id="ff6f7-157">次のことを指定します。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-157">Specify whether:</span></span></p>
<ul>
<li><p><span data-ttu-id="ff6f7-158">PSTN 会議ダイヤルインを有効にするかどうか。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-158">PSTN conference dial-in is enabled.</span></span></p></li>
<li><p><span data-ttu-id="ff6f7-159">ユーザーが匿名参加者を招待できるようにするかどうか。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-159">Users can invite anonymous participants.</span></span></p></li>
<li><p><span data-ttu-id="ff6f7-p108">認証されていないユーザーがダイヤルアウト番号を使用して会議に参加できるようにするかどうか。 会議サーバーはダイヤルアウト番号を使用してユーザーを呼び出し、ユーザーはその電話に応答し、会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-p108">Unauthenticated users can join a conference by using dial-out phoning. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ff6f7-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ff6f7-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ff6f7-163">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-163">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="ff6f7-164">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-164">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Lync Server 2013 でのダイヤルインの会議ポリシーの構成</a></span><span class="sxs-lookup"><span data-stu-id="ff6f7-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configure conferencing policy for dial-in in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff6f7-166"><strong>ダイヤルイン アクセス番号を構成する</strong></span><span class="sxs-lookup"><span data-stu-id="ff6f7-166"><strong>Configure dial-in access numbers</strong></span></span></p></td>
<td><p><span data-ttu-id="ff6f7-167">Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、ユーザーが電話会議にダイヤルインするためにダイヤルインアクセス番号を設定し、アクセス番号を適切なダイヤルプランに関連付ける地域を指定します。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-167">Use Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial-in access numbers that users call to dial in to a conference, and specify the regions that associate the access number with the appropriate dial plans.</span></span> <span data-ttu-id="ff6f7-168">開催者のダイヤル プランで指定されている地域の最初の 3 つのアクセス番号が会議開催通知に含まれます。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-168">The first three access numbers for the region specified by the organizer's dial plan are included in the conference invitation.</span></span> <span data-ttu-id="ff6f7-169">すべてのアクセス番号は、[ダイヤルイン会議の設定] ページで利用できます。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-169">All access numbers are available on the Dial-in Conferencing Settings page.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="ff6f7-170">ダイヤルインアクセス番号を作成した後は、 <STRONG>get-csdialinconferencingaccessnumber</STRONG>コマンドレットを使用して、Active Directory 連絡先オブジェクトの表示名を変更し、ユーザーが正しいアクセス番号を容易に識別できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-170">After you create dial-in access numbers, you can use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name of the Active Directory contact objects so that users can more easily identify the correct access number.</span></span>


</div></td>
<td><p><span data-ttu-id="ff6f7-171">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ff6f7-171">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ff6f7-172">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-172">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="ff6f7-173">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-173">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Lync Server 2013 でのダイヤルイン会議アクセス番号の構成</a></span><span class="sxs-lookup"><span data-stu-id="ff6f7-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configure dial-in conferencing access numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff6f7-175"><strong>(オプション) ダイヤルイン会議の設定の検証</strong></span><span class="sxs-lookup"><span data-stu-id="ff6f7-175"><strong>(Optional) Verify dial-in conferencing settings</strong></span></span></p></td>
<td><p><span data-ttu-id="ff6f7-176"><strong>Get-CsDialinConferencingAccessNumber</strong> コマンドレットを使用して、地域が割り当てられていないすべてのアクセス番号に関して使用されるダイヤルイン会議の地域が設定されたダイヤル プランを検索します。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-176">Use the <strong>Get-CsDialinConferencingAccessNumber</strong> cmdlet to search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have no region assigned.</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-177">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ff6f7-177">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ff6f7-178">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-178">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="ff6f7-179">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-179">CsAdministrator</span></span></p>
<p><span data-ttu-id="ff6f7-180">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-180">CsViewOnlyAdministrator</span></span></p>
<p><span data-ttu-id="ff6f7-181">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="ff6f7-181">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">オプションLync Server 2013 でダイヤルイン会議の設定を確認する</a></span><span class="sxs-lookup"><span data-stu-id="ff6f7-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Optional) Verify dial-in conferencing settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff6f7-183"><strong>(オプション) DTMF コマンドの主要なマッピングを変更する</strong></span><span class="sxs-lookup"><span data-stu-id="ff6f7-183"><strong>(Optional) Modify key mapping of DTMF commands</strong></span></span></p></td>
<td><p><span data-ttu-id="ff6f7-184"><strong>Set-CsDialinConferencingDtmfConfiguration</strong> コマンドレットを使用して、デュアルトーン多重周波数 (DTMF) コマンドで使用される、参加者が会議設定 (ミュートとミュート解除、ロックとロック解除など) を制御するために使用するキーを変更します。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-184">Use the <strong>Set-CsDialinConferencingDtmfConfiguration</strong> cmdlet to modify the keys used for dual-tone multifrequency (DTMF) commands, which participants can use to control conference settings (such as mute and unmute or lock and unlock).</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ff6f7-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ff6f7-186">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-186">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="ff6f7-187">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-187">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">オプションLync Server 2013 での DTMF コマンドのキーマッピングの変更</a></span><span class="sxs-lookup"><span data-stu-id="ff6f7-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff6f7-189"><strong>(オプション) 会議の参加時と退席時のアナウンス動作を変更する</strong></span><span class="sxs-lookup"><span data-stu-id="ff6f7-189"><strong>(Optional) Modify conference join and leave announcement behavior</strong></span></span></p></td>
<td><p><span data-ttu-id="ff6f7-190"><strong>Set-CsDialinConferencingConfiguration</strong> を使用して、参加者が会議に参加および退席する際のアナウンス動作を変更します。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-190">Use the <strong>Set-CsDialinConferencingConfiguration</strong> to change how announcements work when participants join and leave conferences.</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-191">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ff6f7-191">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ff6f7-192">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-192">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="ff6f7-193">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-193">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">オプションLync Server 2013 での会議の参加と脱退のアナウンスを有効または無効にする</a></span><span class="sxs-lookup"><span data-stu-id="ff6f7-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff6f7-195"><strong>(オプション) ダイヤルイン会議の検証</strong></span><span class="sxs-lookup"><span data-stu-id="ff6f7-195"><strong>(Optional) Verify dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="ff6f7-196"><strong>Test-CsDialInConferencing</strong> コマンドレットを使用して、指定のプールのアクセス番号が正しく機能するかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-196">Use the <strong>Test-CsDialInConferencing</strong> cmdlet to test that the access numbers for the specified pool work correctly.</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-197">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ff6f7-197">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ff6f7-198">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-198">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="ff6f7-199">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-199">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">オプションLync Server 2013 でのダイヤルイン会議の確認</a></span><span class="sxs-lookup"><span data-stu-id="ff6f7-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Optional) Verify dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff6f7-201"><strong>Lync 2013 用オンライン ミーティング アドインの展開</strong></span><span class="sxs-lookup"><span data-stu-id="ff6f7-201"><strong>Deploy the Online Meeting Add-in for Lync 2013</strong></span></span></p></td>
<td><p><span data-ttu-id="ff6f7-202">ユーザーがダイヤルイン会議をサポートする会議をスケジュール設定できるように、Lync 2013 用のオンラインミーティングアドインを展開します。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-202">Deploy the Online Meeting Add-in for Lync 2013 so that users can schedule conferences that support dial-in conferencing.</span></span> <span data-ttu-id="ff6f7-203">Lync 2013 をインストールすると、Lync 2013 用のオンラインミーティングアドインが自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-203">The Online Meeting Add-in for Lync 2013 is installed automatically when you install Lync 2013.</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-204">管理者</span><span class="sxs-lookup"><span data-stu-id="ff6f7-204">Administrators</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Lync 2013 用オンライン ミーティング アドインの展開</a></span><span class="sxs-lookup"><span data-stu-id="ff6f7-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Deploy the Online Meeting Add-in for Lync 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff6f7-206"><strong>ユーザー アカウント設定の構成</strong></span><span class="sxs-lookup"><span data-stu-id="ff6f7-206"><strong>Configure user account settings</strong></span></span></p></td>
<td><p><span data-ttu-id="ff6f7-207">Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、テレフォニー<strong>回線 URI</strong>を正規化された一意の電話番号 (たとえば、tel: + 14255550200) として構成します。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-207">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure the telephony <strong>Line URI</strong> as a unique, normalized phone number (for example, tel:+14255550200).</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-208">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ff6f7-208">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ff6f7-209">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-209">CsAdministrator</span></span></p>
<p><span data-ttu-id="ff6f7-210">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="ff6f7-210">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-211"><a href="lync-server-2013-configure-user-account-settings.md">Lync Server 2013 でユーザーアカウント設定を構成する</a></span><span class="sxs-lookup"><span data-stu-id="ff6f7-211"><a href="lync-server-2013-configure-user-account-settings.md">Configure user account settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff6f7-212">勧め会議ディレクトリを構成する</span><span class="sxs-lookup"><span data-stu-id="ff6f7-212">(Recommended) Configure conference directories</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-213"><strong>Get-csconferencedirectory</strong>コマンドレットを使用して、プール内の999ユーザーごとに1つの会議ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-213">Use the <strong>New-CsConferenceDirectory</strong> cmdlet to create one conference directory for every 999 users in the pool.</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-214">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ff6f7-214">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-215"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013 でのダイヤルイン会議の要件</a> <a href="recommended-create-conference-directories.md">(推奨) 電話会議ディレクトリを作成する</a></span><span class="sxs-lookup"><span data-stu-id="ff6f7-215"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(Recommended) Create Conference Directories</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff6f7-216"><strong>(オプション) ユーザーにダイヤルイン会議を案内して最初の PIN を設定する</strong></span><span class="sxs-lookup"><span data-stu-id="ff6f7-216"><strong>(Optional) Welcome users to dial-in conferencing and set the initial PIN</strong></span></span></p></td>
<td><p><span data-ttu-id="ff6f7-217"><strong>Set-cspinsendcawelcomemail</strong>スクリプトを使用して、ユーザーの初期 pin を設定し、初期 Pin およびダイヤルイン会議の設定ページへのリンクを含む開始メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="ff6f7-217">Use the <strong>Set-CsPinSendCAWelcomeMail</strong> script to set users' initial PINs and send a welcome email that contains the initial PIN and a link to the Dial-in Conferencing Settings page.</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-218">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ff6f7-218">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="ff6f7-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">オプションLync Server 2013 でのダイヤルイン会議へのユーザーのようこそ</a></span><span class="sxs-lookup"><span data-stu-id="ff6f7-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

