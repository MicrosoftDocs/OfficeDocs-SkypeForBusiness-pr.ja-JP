---
title: 'Lync Server 2013: ダイヤルイン会議の展開チェックリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44591676d69b5fb4ac3d66ce0e18718389a0c189
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="eb06f-102">Lync Server 2013 のダイヤルイン会議の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="eb06f-102">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb06f-103">_**最終更新日:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="eb06f-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="eb06f-104">会議のワークロードを展開すると、ダイヤルイン会議に必要なコンポーネントが展開されます。</span><span class="sxs-lookup"><span data-stu-id="eb06f-104">The components required for dial-in conferencing are deployed when you deploy the conferencing workload.</span></span> <span data-ttu-id="eb06f-105">ダイヤルイン会議を構成する前に、エンタープライズボイスまたは仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb06f-105">Before you can configure dial-in conferencing, you need to deploy either Enterprise Voice or a Mediation Server and a public switched telephone network (PSTN) gateway.</span></span>

<span data-ttu-id="eb06f-106">次の表のすべての手順を実行して、ユーザーが PSTN から電話会議に参加するようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb06f-106">All the steps in the following table must be performed before users can dial in from the PSTN to join an audio/video conference.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eb06f-107">Office Communications Server 2007 R2 から移行する場合は、ダイヤルイン会議を展開する前に、Office Communications Server 2007 R2 の環境に最新の更新プログラムを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb06f-107">If you are migrating from Office Communications Server 2007 R2, you must apply the latest updates to your Office Communications Server 2007 R2 environment before deploying dial-in conferencing.</span></span>



</div>

### <a name="dial-in-conferencing-deployment-process"></a><span data-ttu-id="eb06f-108">ダイヤルイン会議の展開プロセス</span><span class="sxs-lookup"><span data-stu-id="eb06f-108">Dial-in Conferencing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb06f-109">段階</span><span class="sxs-lookup"><span data-stu-id="eb06f-109">Phase</span></span></th>
<th><span data-ttu-id="eb06f-110">ステップ</span><span class="sxs-lookup"><span data-stu-id="eb06f-110">Steps</span></span></th>
<th><span data-ttu-id="eb06f-111">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="eb06f-111">Permissions</span></span></th>
<th><span data-ttu-id="eb06f-112">「展開」のドキュメント</span><span class="sxs-lookup"><span data-stu-id="eb06f-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb06f-113"><strong>仲介サーバーと PSTN ゲートウェイなどの会議のワークロードを含むトポロジを作成して、フロントエンドプールまたは Standard Edition サーバーを展開する</strong></span><span class="sxs-lookup"><span data-stu-id="eb06f-113"><strong>Create a topology that includes the Conferencing workload, including a Mediation Server and PSTN gateway, and deploy the Front End pool or Standard Edition server</strong></span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="eb06f-114">トポロジビルダーを実行してトポロジを構成します。</span><span class="sxs-lookup"><span data-stu-id="eb06f-114">Run Topology Builder to configure your topology.</span></span> <span data-ttu-id="eb06f-115">トポロジの構成時に、ダイヤルイン会議オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="eb06f-115">While configuring the topology, select the dial-in conferencing option.</span></span></p></li>
<li><p><span data-ttu-id="eb06f-116">トポロジを公開し、フロントエンドプールまたは Standard Edition サーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="eb06f-116">Publish the topology and deploy the Front End pool or Standard Edition server.</span></span></p></li>
<li><p><span data-ttu-id="eb06f-117">必要に応じて、スタンドアロンの仲介サーバーを作成して、PSTN ゲートウェイに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="eb06f-117">If necessary, create a stand-alone Mediation Server and associate it with a PSTN gateway.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="eb06f-118">この手順が必要になるのは、エンタープライズボイスを展開せず、エンタープライズ EditionFront エンドサーバーまたは Standard Edition サーバーで仲介サーバーを検索しない場合のみです。</span><span class="sxs-lookup"><span data-stu-id="eb06f-118">This step is required only if you do not deploy Enterprise Voice and do not collocate the Mediation Server with the Enterprise EditionFront End Server or Standard Edition server.</span></span> <span data-ttu-id="eb06f-119">エンタープライズ Voip を展開する場合は、エンタープライズ Voip 展開の一部として、仲介サーバーと PSTN ゲートウェイをインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="eb06f-119">If you deploy Enterprise Voice, you install and configure Mediation Servers and PSTN gateways as part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="eb06f-120">仲介サーバーを検索する場合は、フロントエンドプールまたは Standard Edition サーバーの展開の一部として、仲介サーバーをインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="eb06f-120">If you collocate the Mediation Server, you install and configure the Mediation Server as part of the Front End pool or Standard Edition server deployment.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="eb06f-121">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="eb06f-121">Domain Admins</span></span></p>
<p><span data-ttu-id="eb06f-122">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="eb06f-122">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="eb06f-123">Administrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-123">Administrator</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="eb06f-124"><a href="lync-server-2013-deploying-lync-server.md">Lync Server 2013 の展開</a></span><span class="sxs-lookup"><span data-stu-id="eb06f-124"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="eb06f-125">スタンドアロンの仲介サーバープールを作成するには、「 <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Lync server 2013 での仲介サーバーの展開とピアの定義」</a>をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="eb06f-125">To create a stand-alone Mediation Server pool: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb06f-126"><strong>Configure dial plans</strong></span><span class="sxs-lookup"><span data-stu-id="eb06f-126"><strong>Configure dial plans</strong></span></span></p></td>
<td><p><span data-ttu-id="eb06f-127">ダイヤルプランとは、特定の場所からダイヤルされた電話番号を、電話の認証と通話ルーティングの目的に合わせて1つの標準 (E.i) 形式に変換する、一連の電話番号の正規化ルールです。</span><span class="sxs-lookup"><span data-stu-id="eb06f-127">A dial plan is a set of phone number normalization rules that translate phone numbers dialed from a specific location to a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="eb06f-128">異なる場所からダイヤルされた同じ電話番号は、それぞれのダイヤルプランに基づいて、それぞれの場所に応じて異なる E.i 番号に解決することができます。</span><span class="sxs-lookup"><span data-stu-id="eb06f-128">The same phone number dialed from different locations can, based on the respective dial plans, resolve to different E.164 numbers, as appropriate to each location.</span></span> <span data-ttu-id="eb06f-129">エンタープライズ Voip を展開する場合は、その展開の一環としてダイヤルプランを設定する必要があります。また、ダイヤルプランがダイヤルイン会議にも対応していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb06f-129">If you deploy Enterprise Voice, you set up dial plans as part of that deployment, and you need to make sure that the dial plans also accommodate dial-in conferencing.</span></span> <span data-ttu-id="eb06f-130">エンタープライズ Voip を展開しない場合は、ダイヤルイン会議のダイヤルプランをセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb06f-130">If you do not deploy Enterprise Voice, you need to set up dial plans for dial-in conferencing.</span></span></p>
<p><span data-ttu-id="eb06f-131">Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、次のようにダイヤルプランを設定します。</span><span class="sxs-lookup"><span data-stu-id="eb06f-131">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial plans as follows:</span></span></p>
<ol>
<li><p><span data-ttu-id="eb06f-132">ダイヤルイン アクセスの電話番号をルーティングするための、1 つまたは複数のダイヤル プランを作成します。</span><span class="sxs-lookup"><span data-stu-id="eb06f-132">Create one or more dial plans for routing dial-in access phone numbers.</span></span></p></li>
<li><p><span data-ttu-id="eb06f-p105">各プールに既定のダイヤル プランを割り当てます。ダイヤル プランを適用する地理的場所に [<strong>ダイヤルイン会議の地域</strong>] を設定します。地域がダイヤルイン アクセス番号が設定されたダイヤル プランに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="eb06f-p105">Assign a default dial plan to each pool. Set the <strong>Dial-in conferencing region</strong> to the geographic location to which the dial plan applies. The region associates the dial plan with dial-in access numbers.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="eb06f-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="eb06f-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="eb06f-137">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-137">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="eb06f-138">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-138">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="eb06f-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="eb06f-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Lync Server 2013 でのダイヤルイン会議のダイヤル プランの構成</a></span><span class="sxs-lookup"><span data-stu-id="eb06f-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configure dial plans for dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb06f-141"><strong>ダイヤル プランが地域に割り当てられていることを確認する</strong></span><span class="sxs-lookup"><span data-stu-id="eb06f-141"><strong>Make sure that dial plans are assigned regions</strong></span></span></p></td>
<td><p><span data-ttu-id="eb06f-142"><strong>Get-CsDialPlan</strong> コマンドレットと <strong>Set-CsDialPlan</strong> コマンドレットを実行して、すべてのダイヤル プランに地域が割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="eb06f-142">Run the <strong>Get-CsDialPlan</strong> and <strong>Set-CsDialPlan</strong> cmdlets to make sure that all dial plans have a region assigned.</span></span></p></td>
<td><p><span data-ttu-id="eb06f-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="eb06f-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="eb06f-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="eb06f-145">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-145">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="eb06f-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="eb06f-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">「ダイヤルプラン Lync Server 2013 に地域が割り当てられていることを確認する」</a></span><span class="sxs-lookup"><span data-stu-id="eb06f-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Make sure dial plans Lync Server 2013 have assigned regions</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb06f-148"><strong>(オプション) ユーザーの暗証番号 (PIN) 要件を確認または変更する</strong></span><span class="sxs-lookup"><span data-stu-id="eb06f-148"><strong>(Optional) Verify or modify user personal identification number (PIN) requirements</strong></span></span></p></td>
<td><p><span data-ttu-id="eb06f-149">Lync Server 2013 コントロールパネルまたは Lync Server 管理シェルを使用して、会議<strong>ピンポリシー</strong>を表示または変更します。</span><span class="sxs-lookup"><span data-stu-id="eb06f-149">Use Lync Server 2013 Control Panel or Lync Server Management Shell to view or modify the Conferencing <strong>PIN Policy</strong>.</span></span> <span data-ttu-id="eb06f-150">最小 PIN サイズ、最大ログオン試行回数、PIN の有効期限、およびよくあるパターンを許可するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="eb06f-150">You can specify minimum PIN length, maximum number of logon attempts, PIN expiration, and whether common patterns are allowable.</span></span></p></td>
<td><p><span data-ttu-id="eb06f-151">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="eb06f-151">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="eb06f-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="eb06f-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="eb06f-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(オプション) Lync Server 2013 での PIN ポリシー設定の確認</a></span><span class="sxs-lookup"><span data-stu-id="eb06f-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Optional) Verify PIN policy settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb06f-155"><strong>ダイヤルイン会議をサポートするように会議ポリシーを構成する</strong></span><span class="sxs-lookup"><span data-stu-id="eb06f-155"><strong>Configure conferencing policy to support dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="eb06f-156">Lync Server 2013 コントロールパネルまたは Lync Server Management Shell を使って、<strong>会議のポリシー</strong>設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="eb06f-156">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure <strong>Conferencing Policy</strong> settings.</span></span> <span data-ttu-id="eb06f-157">次のことを指定します。</span><span class="sxs-lookup"><span data-stu-id="eb06f-157">Specify whether:</span></span></p>
<ul>
<li><p><span data-ttu-id="eb06f-158">PSTN 会議ダイヤルインを有効にするかどうか。</span><span class="sxs-lookup"><span data-stu-id="eb06f-158">PSTN conference dial-in is enabled.</span></span></p></li>
<li><p><span data-ttu-id="eb06f-159">ユーザーが匿名参加者を招待できるようにするかどうか。</span><span class="sxs-lookup"><span data-stu-id="eb06f-159">Users can invite anonymous participants.</span></span></p></li>
<li><p><span data-ttu-id="eb06f-p108">認証されていないユーザーがダイヤルアウト番号を使用して会議に参加できるようにするかどうか。会議サーバーはダイヤルアウト番号を使用してユーザーを呼び出し、ユーザーはその電話に応答し、会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="eb06f-p108">Unauthenticated users can join a conference by using dial-out phoning. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="eb06f-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="eb06f-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="eb06f-163">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-163">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="eb06f-164">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-164">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="eb06f-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Lync Server 2013 でダイヤルインの会議ポリシーを構成する</a></span><span class="sxs-lookup"><span data-stu-id="eb06f-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configure conferencing policy for dial-in in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb06f-166"><strong>Configure dial-in access numbers</strong></span><span class="sxs-lookup"><span data-stu-id="eb06f-166"><strong>Configure dial-in access numbers</strong></span></span></p></td>
<td><p><span data-ttu-id="eb06f-167">Lync Server 2013 コントロールパネルまたは Lync Server Management Shell を使用して、ユーザーが電話会議にダイヤルインするためにダイヤルインアクセス番号を設定し、アクセス番号を適切なダイヤルプランに関連付ける地域を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb06f-167">Use Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial-in access numbers that users call to dial in to a conference, and specify the regions that associate the access number with the appropriate dial plans.</span></span> <span data-ttu-id="eb06f-168">開催者のダイヤル プランで指定されている地域の最初の 3 つのアクセス番号が会議開催通知に含まれます。</span><span class="sxs-lookup"><span data-stu-id="eb06f-168">The first three access numbers for the region specified by the organizer's dial plan are included in the conference invitation.</span></span> <span data-ttu-id="eb06f-169">[ダイヤルイン会議の設定] ページでは、すべてのアクセス番号を利用できます。</span><span class="sxs-lookup"><span data-stu-id="eb06f-169">All access numbers are available on the Dial-in Conferencing Settings page.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="eb06f-170">ダイヤルインアクセス番号を作成したら、 <STRONG>CsDialInConferencingAccessNumber</STRONG>コマンドレットを使用して Active Directory の連絡先オブジェクトの表示名を変更し、ユーザーが正しいアクセス番号を簡単に識別できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="eb06f-170">After you create dial-in access numbers, you can use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name of the Active Directory contact objects so that users can more easily identify the correct access number.</span></span>


</div></td>
<td><p><span data-ttu-id="eb06f-171">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="eb06f-171">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="eb06f-172">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-172">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="eb06f-173">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-173">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="eb06f-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Lync Server 2013 でのダイヤルイン会議アクセス番号の構成</a></span><span class="sxs-lookup"><span data-stu-id="eb06f-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configure dial-in conferencing access numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb06f-175"><strong>(オプション) ダイヤルイン会議の設定の検証</strong></span><span class="sxs-lookup"><span data-stu-id="eb06f-175"><strong>(Optional) Verify dial-in conferencing settings</strong></span></span></p></td>
<td><p><span data-ttu-id="eb06f-176"><strong>Get-CsDialinConferencingAccessNumber</strong> コマンドレットを使用して、どのアクセス番号でも使用されていないダイヤルイン会議の地域が設定されたダイヤル プランと、どの地域も割り当てられていないアクセス番号を検索します。</span><span class="sxs-lookup"><span data-stu-id="eb06f-176">Use the <strong>Get-CsDialinConferencingAccessNumber</strong> cmdlet to search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have no region assigned.</span></span></p></td>
<td><p><span data-ttu-id="eb06f-177">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="eb06f-177">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="eb06f-178">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-178">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="eb06f-179">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-179">CsAdministrator</span></span></p>
<p><span data-ttu-id="eb06f-180">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-180">CsViewOnlyAdministrator</span></span></p>
<p><span data-ttu-id="eb06f-181">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="eb06f-181">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="eb06f-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(オプション) Lync Server 2013 でのダイヤルイン会議の設定の検証</a></span><span class="sxs-lookup"><span data-stu-id="eb06f-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Optional) Verify dial-in conferencing settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb06f-183"><strong>(オプション) DTMF コマンドの主要なマッピングを変更する</strong></span><span class="sxs-lookup"><span data-stu-id="eb06f-183"><strong>(Optional) Modify key mapping of DTMF commands</strong></span></span></p></td>
<td><p><span data-ttu-id="eb06f-184"><strong>CsDialinConferencingDtmfConfiguration</strong>コマンドレットを使用して、2トーン (DTMF) コマンドで使用されるキーを変更します。参加者は、会議の設定 (ミュート、ミュート解除、ロックとロック解除など) を制御するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="eb06f-184">Use the <strong>Set-CsDialinConferencingDtmfConfiguration</strong> cmdlet to modify the keys used for dual-tone multifrequency (DTMF) commands, which participants can use to control conference settings (such as mute and unmute or lock and unlock).</span></span></p></td>
<td><p><span data-ttu-id="eb06f-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="eb06f-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="eb06f-186">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-186">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="eb06f-187">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-187">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="eb06f-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(オプション) Lync Server 2013 で DTMF コマンドの主要なマッピングを変更する</a></span><span class="sxs-lookup"><span data-stu-id="eb06f-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb06f-189"><strong>(オプション) 電話会議の参加時と退席時のアナウンス動作を変更する</strong></span><span class="sxs-lookup"><span data-stu-id="eb06f-189"><strong>(Optional) Modify conference join and leave announcement behavior</strong></span></span></p></td>
<td><p><span data-ttu-id="eb06f-190"><strong>Set-CsDialinConferencingConfiguration</strong> を使用して、参加者が電話会議に参加および退席する際のアナウンス動作を変更します。</span><span class="sxs-lookup"><span data-stu-id="eb06f-190">Use the <strong>Set-CsDialinConferencingConfiguration</strong> to change how announcements work when participants join and leave conferences.</span></span></p></td>
<td><p><span data-ttu-id="eb06f-191">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="eb06f-191">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="eb06f-192">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-192">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="eb06f-193">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-193">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="eb06f-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(オプション) Lync Server 2013 での会議への入退出のアナウンスの有効化および無効化</a></span><span class="sxs-lookup"><span data-stu-id="eb06f-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb06f-195"><strong>(オプション) ダイヤルイン会議の検証</strong></span><span class="sxs-lookup"><span data-stu-id="eb06f-195"><strong>(Optional) Verify dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="eb06f-196"><strong>Test-CsDialInConferencing</strong> コマンドレットを使用して、指定のプールのアクセス番号が正しく機能するかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="eb06f-196">Use the <strong>Test-CsDialInConferencing</strong> cmdlet to test that the access numbers for the specified pool work correctly.</span></span></p></td>
<td><p><span data-ttu-id="eb06f-197">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="eb06f-197">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="eb06f-198">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-198">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="eb06f-199">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-199">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="eb06f-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(オプション) Lync Server 2013 でのダイヤルイン会議の検証</a></span><span class="sxs-lookup"><span data-stu-id="eb06f-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Optional) Verify dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb06f-201"><strong>Lync 2013 用オンライン会議アドインの展開</strong></span><span class="sxs-lookup"><span data-stu-id="eb06f-201"><strong>Deploy the Online Meeting Add-in for Lync 2013</strong></span></span></p></td>
<td><p><span data-ttu-id="eb06f-202">Lync 2013 用のオンライン会議アドインを展開して、ユーザーがダイヤルイン会議をサポートする会議をスケジュールできるようにします。</span><span class="sxs-lookup"><span data-stu-id="eb06f-202">Deploy the Online Meeting Add-in for Lync 2013 so that users can schedule conferences that support dial-in conferencing.</span></span> <span data-ttu-id="eb06f-203">Lync 2013 をインストールすると、Lync 2013 用のオンライン会議アドインが自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="eb06f-203">The Online Meeting Add-in for Lync 2013 is installed automatically when you install Lync 2013.</span></span></p></td>
<td><p><span data-ttu-id="eb06f-204">管理者</span><span class="sxs-lookup"><span data-stu-id="eb06f-204">Administrators</span></span></p></td>
<td><p><span data-ttu-id="eb06f-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Lync 2013 用オンライン会議アドインの展開</a></span><span class="sxs-lookup"><span data-stu-id="eb06f-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Deploy the Online Meeting Add-in for Lync 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb06f-206"><strong>ユーザー アカウント設定の構成</strong></span><span class="sxs-lookup"><span data-stu-id="eb06f-206"><strong>Configure user account settings</strong></span></span></p></td>
<td><p><span data-ttu-id="eb06f-207">Lync Server 2013 コントロールパネルまたは Lync Server Management Shell を使って、一意の正規化された電話番号としてテレフォニーの<strong>ライン URI</strong>を構成します (たとえば、tel: + 14255550200)。</span><span class="sxs-lookup"><span data-stu-id="eb06f-207">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure the telephony <strong>Line URI</strong> as a unique, normalized phone number (for example, tel:+14255550200).</span></span></p></td>
<td><p><span data-ttu-id="eb06f-208">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="eb06f-208">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="eb06f-209">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-209">CsAdministrator</span></span></p>
<p><span data-ttu-id="eb06f-210">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="eb06f-210">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="eb06f-211"><a href="lync-server-2013-configure-user-account-settings.md">Lync Server 2013 でのユーザー アカウント設定の構成</a></span><span class="sxs-lookup"><span data-stu-id="eb06f-211"><a href="lync-server-2013-configure-user-account-settings.md">Configure user account settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb06f-212">(推奨) 電話会議ディレクトリを構成する</span><span class="sxs-lookup"><span data-stu-id="eb06f-212">(Recommended) Configure conference directories</span></span></p></td>
<td><p><span data-ttu-id="eb06f-213"><strong>New-CsConferenceDirectory</strong> コマンドレットを使用して、プールに含まれる 999 ユーザーごとに電話会議ディレクトリを 1 つ作成します。</span><span class="sxs-lookup"><span data-stu-id="eb06f-213">Use the <strong>New-CsConferenceDirectory</strong> cmdlet to create one conference directory for every 999 users in the pool.</span></span></p></td>
<td><p><span data-ttu-id="eb06f-214">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="eb06f-214">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="eb06f-215"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013 でのダイヤルイン会議の要件</a><a href="recommended-create-conference-directories.md">(推奨) 会議ディレクトリを作成する</a></span><span class="sxs-lookup"><span data-stu-id="eb06f-215"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(Recommended) Create Conference Directories</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb06f-216"><strong>(オプション) ユーザーにダイヤルイン会議を案内して最初の PIN を設定する</strong></span><span class="sxs-lookup"><span data-stu-id="eb06f-216"><strong>(Optional) Welcome users to dial-in conferencing and set the initial PIN</strong></span></span></p></td>
<td><p><span data-ttu-id="eb06f-217"><strong>CsPinSendCAWelcomeMail</strong>スクリプトを使用して、ユーザーの初期 pin を設定し、初期 Pin とダイヤルイン会議の設定ページへのリンクを含むようこそメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="eb06f-217">Use the <strong>Set-CsPinSendCAWelcomeMail</strong> script to set users' initial PINs and send a welcome email that contains the initial PIN and a link to the Dial-in Conferencing Settings page.</span></span></p></td>
<td><p><span data-ttu-id="eb06f-218">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="eb06f-218">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="eb06f-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(オプション) Lync Server 2013 でのダイヤルイン会議へのユーザーの受け入れ</a></span><span class="sxs-lookup"><span data-stu-id="eb06f-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

