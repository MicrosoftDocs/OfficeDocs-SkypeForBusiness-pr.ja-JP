---
title: 構成の設定を確認する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e1ad498f25656e01507e55c41d98ff4bb9143b4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508414"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="6ba3c-102">構成の設定を確認する</span><span class="sxs-lookup"><span data-stu-id="6ba3c-102">Verify configuration settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ba3c-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6ba3c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6ba3c-104">トポロジをマージし、 **import-cslegacyconfiguration** コマンドレットを実行した後、Office Communications Server 2007 R2 のポリシーと設定が Lync Server 2013 にインポートされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-104">After you merge the topology and run the **Import-CsLegacyConfiguration** cmdlet, verify that your Office Communications Server 2007 R2 policies and settings were imported to Lync Server 2013.</span></span> <span data-ttu-id="6ba3c-105">次の表に、確認が必要なポリシーと設定を示します。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-105">The following table lists the policies and settings that you should verify.</span></span>

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a><span data-ttu-id="6ba3c-106">移行後に確認が必要なポリシーと設定</span><span class="sxs-lookup"><span data-stu-id="6ba3c-106">Policies and Settings to Verify after Migration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ba3c-107">このワークロードを使用する場合:</span><span class="sxs-lookup"><span data-stu-id="6ba3c-107">If you use this workload:</span></span></th>
<th><span data-ttu-id="6ba3c-108">確認が必要なポリシーと設定:</span><span class="sxs-lookup"><span data-stu-id="6ba3c-108">Verify these policies and settings:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ba3c-109">インスタント メッセージング (IM) および電話会議</span><span class="sxs-lookup"><span data-stu-id="6ba3c-109">Instant messaging (IM) and conferencing</span></span></p></td>
<td><p><span data-ttu-id="6ba3c-110">プレゼンス ポリシー</span><span class="sxs-lookup"><span data-stu-id="6ba3c-110">Presence policy</span></span></p>
<p><span data-ttu-id="6ba3c-111">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="6ba3c-111">Conferencing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ba3c-112">ダイヤルイン会議</span><span class="sxs-lookup"><span data-stu-id="6ba3c-112">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="6ba3c-113">ダイヤルイン アクセス番号</span><span class="sxs-lookup"><span data-stu-id="6ba3c-113">Dial-in access numbers</span></span></p>
<p><span data-ttu-id="6ba3c-114">ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="6ba3c-114">Dial plans</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ba3c-115">エンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="6ba3c-115">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="6ba3c-116">音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="6ba3c-116">Voice policy</span></span></p>
<p><span data-ttu-id="6ba3c-117">音声ルート</span><span class="sxs-lookup"><span data-stu-id="6ba3c-117">Voice routes</span></span></p>
<p><span data-ttu-id="6ba3c-118">ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="6ba3c-118">Dial plans</span></span></p>
<p><span data-ttu-id="6ba3c-119">PSTN 使用法設定</span><span class="sxs-lookup"><span data-stu-id="6ba3c-119">PSTN usage settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ba3c-120">Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="6ba3c-120">Communicator Web Access</span></span></p></td>
<td><p><span data-ttu-id="6ba3c-121">簡易 URL</span><span class="sxs-lookup"><span data-stu-id="6ba3c-121">Simple URLs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ba3c-122">外部ユーザー</span><span class="sxs-lookup"><span data-stu-id="6ba3c-122">External users</span></span></p></td>
<td><p><span data-ttu-id="6ba3c-123">外部アクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="6ba3c-123">External access policies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ba3c-124">アーカイブ</span><span class="sxs-lookup"><span data-stu-id="6ba3c-124">Archiving</span></span></p></td>
<td><p><span data-ttu-id="6ba3c-125">アーカイブ ポリシー</span><span class="sxs-lookup"><span data-stu-id="6ba3c-125">Archiving policy</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a><span data-ttu-id="6ba3c-126">ポリシーと設定を確認するには</span><span class="sxs-lookup"><span data-stu-id="6ba3c-126">To verify policies and settings</span></span>

1.  <span data-ttu-id="6ba3c-127">Office Communications Server 2007 R2 環境で、Communicator Web Access に使用される Url に加えて、ダイヤルプラン (以前の場所のプロファイル)、ダイヤルインアクセス番号 (会議アテンダントアクセスの電話番号と地域)、音声ルート、および上記の表に記載されているポリシーの名前をメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-127">In your Office Communications Server 2007 R2 environment, make note of the names of dial plans (formerly known as location profiles), dial-in access numbers (Conferencing Attendant access phone numbers and regions), voice routes, and the policies listed in the preceding table, in addition to the URLs used for Communicator Web Access.</span></span>

2.  <span data-ttu-id="6ba3c-128">Lync Server 2013 のフロントエンドサーバーで、[Lync Server コントロールパネル] を開きます。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-128">On the Lync Server 2013 Front End server, open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="6ba3c-129">インポートされた電話会議ポリシーを確認するには、左側のウィンドウで [ **会議**] をクリックし、[ **会議ポリシー**] をクリックして、Office Communications Server 2007 R2 環境のすべての電話会議ポリシーがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-129">To verify imported conferencing policies, in the left pane, click **Conferencing**, click **Conferencing Policy**, and then verify that all the conferencing policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6ba3c-130">以前のバージョンの Office Communications Server からの <STRONG>会議</STRONG> ポリシーは、Lync Server 2013 の会議ポリシーと呼ばれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-130">The <STRONG>Meeting</STRONG> policy from previous versions of Office Communications Server is now known as the conferencing policy in Lync Server 2013.</span></span> <span data-ttu-id="6ba3c-131">さらに、以前のバージョンの Office Communications Server からの <STRONG>匿名</STRONG> の管理設定は、Lync Server 2013 の電話会議ポリシーの設定になっています。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-131">Additionally, the <STRONG>Anonymous Particpants</STRONG> setting from previous versions of Office Communications Server is now a setting in the Lync Server 2013 conferencing policy.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6ba3c-132">Office Communications Server 2007 R2 では、会議ポリシーが <STRONG>ユーザーごとに使用</STRONG>するように設定されていない場合は、グローバルポリシー設定のみがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-132">In Office Communications Server 2007 R2, if the conferencing policy is not set to <STRONG>use per user</STRONG>, only global policy settings are imported.</span></span> <span data-ttu-id="6ba3c-133">この場合、他の会議ポリシーはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-133">No other conference policies are imported in this situation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6ba3c-134"><STRONG>匿名参加者</STRONG>が Office Communications Server 2007 R2 会議ポリシーの<STRONG>ユーザーごとに適用</STRONG>するように設定されている場合は、移行中に2つの会議ポリシーが作成されます。1つは<STRONG>AllowAnonymousParticipantsInMeetings</STRONG>を<STRONG>True</STRONG>に設定し、もう1つは<STRONG>AllowAnonymousParticipantsInMeetings</STRONG>を<STRONG>False</STRONG>に設定します。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-134">If <STRONG>Anonymous Participants</STRONG> is set to <STRONG>Enforce per user</STRONG> in your Office Communications Server 2007 R2 conferencing policy, two conferencing policies are created during migration: one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>True</STRONG> and one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>False</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="6ba3c-135">インポートされたダイヤル プランを確認するには、[**音声のルーティング**] をクリックし、[**ダイヤル プラン**] をクリックして、Office Communicator 2007 R2 環境のダイヤル プランがリストにすべて含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-135">To verify imported dial plans, click **Voice Routing**, click **Dial Plan**, and then verify that all the dial plans in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6ba3c-136">Lync Server 2013 では、 <STRONG>場所のプロファイル</STRONG> が <STRONG>ダイヤルプラン</STRONG>と呼ばれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-136">In Lync Server 2013, <STRONG>location profiles</STRONG> are now referred to as <STRONG>dial-plans</STRONG>.</span></span>

    
    </div>

5.  <span data-ttu-id="6ba3c-137">インポートされた音声ポリシーを確認するには、[**音声のルーティング**] をクリックし、[**音声ポリシー**] をクリックして、 Office Communicator 2007 R2 環境の音声ポリシーがリストにすべて含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-137">To verify imported voice policies, click **Voice Routing**, click **Voice Policy**, and then verify that all the voice policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6ba3c-138">音声ポリシーが Office Communications Server 2007 R2 環境の <STRONG>ユーザーごとに使用</STRONG> するように設定されていない場合は、グローバルポリシー設定のみがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-138">If voice policy is not set to <STRONG>use per user</STRONG> in your Office Communications Server 2007 R2 environment, only global policy settings are imported.</span></span> <span data-ttu-id="6ba3c-139">この場合、音声ポリシーはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-139">No other voice policies are imported in this situation.</span></span>

    
    </div>

6.  <span data-ttu-id="6ba3c-140">インポートされた音声ルートを確認するには、[**音声のルーティング**] をクリックし、[**ルート**] をクリックして、Office Communicator 2007 R2 環境の音声ルートがリストにすべて含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-140">To verify imported voice routes, click **Voice Routing**, click **Route**, and then verify that all the voice routes in your Office Communicator 2007 R2 environment are included in the list.</span></span>

7.  <span data-ttu-id="6ba3c-141">インポートされた PSTN 使用法の設定を確認するには、[**音声のルーティング**] をクリックし、[**PSTN 使用法**] をクリックして、Office Communicator 2007 R2 環境の PSTN 使用法の設定がリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-141">To verify imported PSTN usage settings, click **Voice Routing**, click **PSTN Usage**, and then verify that the PSTN Usage settings from your Office Communicator 2007 R2 environment are included in the list.</span></span>

8.  <span data-ttu-id="6ba3c-142">インポートされた外部アクセス ポリシーを確認するには、[**フェデレーションと外部アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックして、Office Communicator 2007 R2 環境のすべての外部アクセス ポリシーがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-142">To verify imported external access policies, click **Federation and External Access**, click **External Access Policy**, and then verify that all the external access policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>

9.  <span data-ttu-id="6ba3c-143">アーカイブポリシーを確認するには、[ **監視とアーカイブ**] をクリックし、[ **アーカイブポリシー**] をクリックして、Office Communications Server 2007 R2 環境のすべてのアーカイブポリシーがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-143">To verify archiving policies, click **Monitoring and Archiving**, click **Archiving Policy**, and then verify that all the archiving policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

10. <span data-ttu-id="6ba3c-144">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-144">Open the Lync Server Management Shell.</span></span>

11. <span data-ttu-id="6ba3c-145">プレゼンス ポリシーを確認するには、コマンド ラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-145">To verify presence policies, at the command line, type the following:</span></span>
    
        Get-CsPresencePolicy
    
    <span data-ttu-id="6ba3c-146">**Identity**パラメーターの名前を参照して、Office Communications Server 2007 R2 環境のすべてのプレゼンスポリシーがインポートされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-146">By looking at the name in the **Identity** parameter, verify that all the presence policies in your Office Communications Server 2007 R2 environment were imported.</span></span>

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a><span data-ttu-id="6ba3c-147">コマンドレットを使用してポリシーと設定を確認するには</span><span class="sxs-lookup"><span data-stu-id="6ba3c-147">To verify policies and settings by using cmdlets</span></span>

1.  <span data-ttu-id="6ba3c-148">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-148">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="6ba3c-149">次の表に示すコマンドレットを実行して、ポリシーと設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-149">Run the cmdlets in the following table to verify policies and settings.</span></span>
    
    <span data-ttu-id="6ba3c-150">これらのコマンドレットの構文は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-150">The syntax of these cmdlets is like the following example:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="6ba3c-151">これらのコマンドレットの詳細については、次のように実行してください。</span><span class="sxs-lookup"><span data-stu-id="6ba3c-151">For details about these cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ba3c-152">次のポリシーまたは設定を確認する場合:</span><span class="sxs-lookup"><span data-stu-id="6ba3c-152">For this policy or setting:</span></span></th>
<th><span data-ttu-id="6ba3c-153">使用するコマンドレット:</span><span class="sxs-lookup"><span data-stu-id="6ba3c-153">Use this cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ba3c-154">プレゼンス ポリシー</span><span class="sxs-lookup"><span data-stu-id="6ba3c-154">Presence policy</span></span></p></td>
<td><p><span data-ttu-id="6ba3c-155"><strong>Get-CsPresencePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="6ba3c-155"><strong>Get-CsPresencePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ba3c-156">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="6ba3c-156">Conferencing policy</span></span></p></td>
<td><p><span data-ttu-id="6ba3c-157"><strong>Get-CsConferencingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="6ba3c-157"><strong>Get-CsConferencingPolicy</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ba3c-158">ダイヤルイン アクセス番号</span><span class="sxs-lookup"><span data-stu-id="6ba3c-158">Dial-in access numbers</span></span></p></td>
<td><p><span data-ttu-id="6ba3c-159"><strong>Get-csdialinconferencingaccessnumber</strong></span><span class="sxs-lookup"><span data-stu-id="6ba3c-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ba3c-160">ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="6ba3c-160">Dial plans</span></span></p></td>
<td><p><span data-ttu-id="6ba3c-161"><strong>Get-CsDialPlan</strong></span><span class="sxs-lookup"><span data-stu-id="6ba3c-161"><strong>Get-CsDialPlan</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ba3c-162">音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="6ba3c-162">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="6ba3c-163"><strong>Get-CsVoicePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="6ba3c-163"><strong>Get-CsVoicePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ba3c-164">音声ルート</span><span class="sxs-lookup"><span data-stu-id="6ba3c-164">Voice routes</span></span></p></td>
<td><p><span data-ttu-id="6ba3c-165"><strong>Get-csvoiceroute</strong></span><span class="sxs-lookup"><span data-stu-id="6ba3c-165"><strong>Get-CsVoiceRoute</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ba3c-166">PSTN の使用法</span><span class="sxs-lookup"><span data-stu-id="6ba3c-166">PSTN Usage</span></span></p></td>
<td><p><span data-ttu-id="6ba3c-167"><strong>Get-CsPstnUsage</strong></span><span class="sxs-lookup"><span data-stu-id="6ba3c-167"><strong>Get-CsPstnUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ba3c-168">URL</span><span class="sxs-lookup"><span data-stu-id="6ba3c-168">URLs</span></span></p></td>
<td><p><span data-ttu-id="6ba3c-169"><strong>取得-CsSimpleUrlConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="6ba3c-169"><strong>Get-CsSimpleUrlConfiguration</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ba3c-170">外部アクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="6ba3c-170">External access policies</span></span></p></td>
<td><p><span data-ttu-id="6ba3c-171"><strong>Get-CsExternalAccessPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="6ba3c-171"><strong>Get-CsExternalAccessPolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ba3c-172">アーカイブ ポリシー</span><span class="sxs-lookup"><span data-stu-id="6ba3c-172">Archiving policy</span></span></p></td>
<td><p><span data-ttu-id="6ba3c-173"><strong>Grant-csarchivingpolicy</strong></span><span class="sxs-lookup"><span data-stu-id="6ba3c-173"><strong>Get-CsArchivingPolicy</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

