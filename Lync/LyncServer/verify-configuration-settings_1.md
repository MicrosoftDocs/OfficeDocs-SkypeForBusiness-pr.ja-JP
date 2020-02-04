---
title: 構成の設定の確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4d13f3bdd5af1a2c9b90e190775522ea6f11b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a><span data-ttu-id="79143-102">構成の設定の確認</span><span class="sxs-lookup"><span data-stu-id="79143-102">Verify configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79143-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="79143-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="79143-104">トポロジをマージして、 **CsLegacyConfiguration**コマンドレットを実行した後、Office Communications Server 2007 R2 のポリシーと設定が Lync Server 2013 にインポートされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="79143-104">After you merge the topology and run the **Import-CsLegacyConfiguration** cmdlet, verify that your Office Communications Server 2007 R2 policies and settings were imported to Lync Server 2013.</span></span> <span data-ttu-id="79143-105">次の表に、確認する必要があるポリシーと設定を示します。</span><span class="sxs-lookup"><span data-stu-id="79143-105">The following table lists the policies and settings that you should verify.</span></span>

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a><span data-ttu-id="79143-106">移行後に確認するポリシーと設定</span><span class="sxs-lookup"><span data-stu-id="79143-106">Policies and Settings to Verify after Migration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79143-107">この作業負荷を使用する場合:</span><span class="sxs-lookup"><span data-stu-id="79143-107">If you use this workload:</span></span></th>
<th><span data-ttu-id="79143-108">以下のポリシーと設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="79143-108">Verify these policies and settings:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79143-109">インスタントメッセージング (IM) と会議</span><span class="sxs-lookup"><span data-stu-id="79143-109">Instant messaging (IM) and conferencing</span></span></p></td>
<td><p><span data-ttu-id="79143-110">プレゼンスポリシー</span><span class="sxs-lookup"><span data-stu-id="79143-110">Presence policy</span></span></p>
<p><span data-ttu-id="79143-111">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="79143-111">Conferencing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79143-112">ダイヤルイン会議</span><span class="sxs-lookup"><span data-stu-id="79143-112">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="79143-113">ダイヤルインアクセス番号</span><span class="sxs-lookup"><span data-stu-id="79143-113">Dial-in access numbers</span></span></p>
<p><span data-ttu-id="79143-114">ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="79143-114">Dial plans</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79143-115">エンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="79143-115">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="79143-116">音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="79143-116">Voice policy</span></span></p>
<p><span data-ttu-id="79143-117">音声ルート</span><span class="sxs-lookup"><span data-stu-id="79143-117">Voice routes</span></span></p>
<p><span data-ttu-id="79143-118">ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="79143-118">Dial plans</span></span></p>
<p><span data-ttu-id="79143-119">PSTN 使用状況の設定</span><span class="sxs-lookup"><span data-stu-id="79143-119">PSTN usage settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79143-120">Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="79143-120">Communicator Web Access</span></span></p></td>
<td><p><span data-ttu-id="79143-121">簡易 URL</span><span class="sxs-lookup"><span data-stu-id="79143-121">Simple URLs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79143-122">外部ユーザー</span><span class="sxs-lookup"><span data-stu-id="79143-122">External users</span></span></p></td>
<td><p><span data-ttu-id="79143-123">外部アクセスポリシー</span><span class="sxs-lookup"><span data-stu-id="79143-123">External access policies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79143-124">アーカイブ</span><span class="sxs-lookup"><span data-stu-id="79143-124">Archiving</span></span></p></td>
<td><p><span data-ttu-id="79143-125">アーカイブポリシー</span><span class="sxs-lookup"><span data-stu-id="79143-125">Archiving policy</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a><span data-ttu-id="79143-126">ポリシーと設定を確認するには</span><span class="sxs-lookup"><span data-stu-id="79143-126">To verify policies and settings</span></span>

1.  <span data-ttu-id="79143-127">Office Communications Server 2007 R2 環境で、ダイヤルプラン (以前は位置情報プロファイル)、ダイヤルインアクセス番号 (会議アテンダントアクセス電話番号と地域)、音声ルート、および以下に記載されているポリシーの名前をメモしておきます。Communicator Web Access で使用される Url に加えて、前の表が表示されます。</span><span class="sxs-lookup"><span data-stu-id="79143-127">In your Office Communications Server 2007 R2 environment, make note of the names of dial plans (formerly known as location profiles), dial-in access numbers (Conferencing Attendant access phone numbers and regions), voice routes, and the policies listed in the preceding table, in addition to the URLs used for Communicator Web Access.</span></span>

2.  <span data-ttu-id="79143-128">Lync Server 2013 フロントエンドサーバーで、[Lync Server] コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="79143-128">On the Lync Server 2013 Front End server, open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="79143-129">インポートした会議ポリシーを確認するには、左側のウィンドウで [**会議**] をクリックし、[**会議ポリシー**] をクリックして、Office Communications Server 2007 R2 環境のすべての会議ポリシーが一覧に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="79143-129">To verify imported conferencing policies, in the left pane, click **Conferencing**, click **Conferencing Policy**, and then verify that all the conferencing policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="79143-130">以前のバージョンの Office Communications Server の<STRONG>会議</STRONG>ポリシーは、Lync Server 2013 の会議ポリシーと呼ばれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="79143-130">The <STRONG>Meeting</STRONG> policy from previous versions of Office Communications Server is now known as the conferencing policy in Lync Server 2013.</span></span> <span data-ttu-id="79143-131">さらに、以前のバージョンの Office Communications Server からの<STRONG>匿名</STRONG>の管理設定は、Lync Server 2013 会議ポリシーの設定になりました。</span><span class="sxs-lookup"><span data-stu-id="79143-131">Additionally, the <STRONG>Anonymous Particpants</STRONG> setting from previous versions of Office Communications Server is now a setting in the Lync Server 2013 conferencing policy.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="79143-132">Office Communications Server 2007 R2 で、会議ポリシーが<STRONG>ユーザーごとに使用</STRONG>するように設定されていない場合は、グローバルポリシー設定のみがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="79143-132">In Office Communications Server 2007 R2, if the conferencing policy is not set to <STRONG>use per user</STRONG>, only global policy settings are imported.</span></span> <span data-ttu-id="79143-133">この状況では、他の会議ポリシーはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="79143-133">No other conference policies are imported in this situation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="79143-134">Office Communications Server 2007 R2 会議ポリシーで<STRONG>ユーザーごとに適用</STRONG>するように<STRONG>匿名の参加者</STRONG>が設定されている場合、移行中に2つの会議ポリシーが作成されます。1つは、 <STRONG>AllowAnonymousParticipantsInMeetings</STRONG>が<STRONG>True</STRONG>に設定されている場合と、 <STRONG>AllowAnonymousParticipantsInMeetings</STRONG>が<STRONG>False</STRONG>に設定されている場合です。</span><span class="sxs-lookup"><span data-stu-id="79143-134">If <STRONG>Anonymous Participants</STRONG> is set to <STRONG>Enforce per user</STRONG> in your Office Communications Server 2007 R2 conferencing policy, two conferencing policies are created during migration: one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>True</STRONG> and one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>False</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="79143-135">インポートしたダイヤルプランを確認するには、[**音声ルーティング**]、[**ダイヤルプラン**] の順にクリックし、Office Communicator 2007 R2 環境のすべてのダイヤルプランがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="79143-135">To verify imported dial plans, click **Voice Routing**, click **Dial Plan**, and then verify that all the dial plans in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="79143-136">Lync Server 2013 では、<STRONG>位置情報プロファイル</STRONG>は<STRONG>ダイヤルプラン</STRONG>として参照されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="79143-136">In Lync Server 2013, <STRONG>location profiles</STRONG> are now referred to as <STRONG>dial-plans</STRONG>.</span></span>

    
    </div>

5.  <span data-ttu-id="79143-137">インポートした音声ポリシーを確認するには、[**音声ルーティング**]、[**音声ポリシー**] の順にクリックし、Office Communicator 2007 R2 環境のすべての音声ポリシーが一覧に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="79143-137">To verify imported voice policies, click **Voice Routing**, click **Voice Policy**, and then verify that all the voice policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="79143-138">Office Communications Server 2007 R2 環境で<STRONG>ユーザーごとに使用</STRONG>するようにボイスポリシーが設定されていない場合、グローバルポリシー設定のみがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="79143-138">If voice policy is not set to <STRONG>use per user</STRONG> in your Office Communications Server 2007 R2 environment, only global policy settings are imported.</span></span> <span data-ttu-id="79143-139">この状況では、他の音声ポリシーはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="79143-139">No other voice policies are imported in this situation.</span></span>

    
    </div>

6.  <span data-ttu-id="79143-140">インポートした音声ルートを確認するには、[**音声ルーティング**] をクリックし、[**ルーティング**] をクリックして、Office Communicator 2007 R2 環境のすべてのボイスルートがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="79143-140">To verify imported voice routes, click **Voice Routing**, click **Route**, and then verify that all the voice routes in your Office Communicator 2007 R2 environment are included in the list.</span></span>

7.  <span data-ttu-id="79143-141">インポートした PSTN 使用状況の設定を確認するには、[**音声ルーティング**] をクリックし、[ **pstn 使用状況**] をクリックして、Office Communicator 2007 R2 環境からの pstn 使用の設定が一覧に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="79143-141">To verify imported PSTN usage settings, click **Voice Routing**, click **PSTN Usage**, and then verify that the PSTN Usage settings from your Office Communicator 2007 R2 environment are included in the list.</span></span>

8.  <span data-ttu-id="79143-142">インポートされた外部アクセスポリシーを確認するには、[**フェデレーションと外部アクセス**] をクリックし、[**外部アクセスポリシー**] をクリックして、Office Communicator 2007 R2 環境のすべての外部アクセスポリシーがリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="79143-142">To verify imported external access policies, click **Federation and External Access**, click **External Access Policy**, and then verify that all the external access policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>

9.  <span data-ttu-id="79143-143">アーカイブポリシーを確認するには、[**監視およびアーカイブ**] をクリックし、[**アーカイブポリシー**] をクリックして、Office Communications Server 2007 R2 環境のすべてのアーカイブポリシーが一覧に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="79143-143">To verify archiving policies, click **Monitoring and Archiving**, click **Archiving Policy**, and then verify that all the archiving policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

10. <span data-ttu-id="79143-144">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="79143-144">Open the Lync Server Management Shell.</span></span>

11. <span data-ttu-id="79143-145">プレゼンスポリシーを確認するには、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="79143-145">To verify presence policies, at the command line, type the following:</span></span>
    
        Get-CsPresencePolicy
    
    <span data-ttu-id="79143-146">**Identity**パラメーターの名前を確認して、Office Communications Server 2007 R2 環境のすべてのプレゼンスポリシーがインポートされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="79143-146">By looking at the name in the **Identity** parameter, verify that all the presence policies in your Office Communications Server 2007 R2 environment were imported.</span></span>

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a><span data-ttu-id="79143-147">コマンドレットを使用してポリシーと設定を確認するには</span><span class="sxs-lookup"><span data-stu-id="79143-147">To verify policies and settings by using cmdlets</span></span>

1.  <span data-ttu-id="79143-148">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="79143-148">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="79143-149">ポリシーと設定を確認するには、次の表のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="79143-149">Run the cmdlets in the following table to verify policies and settings.</span></span>
    
    <span data-ttu-id="79143-150">これらのコマンドレットの構文は、次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="79143-150">The syntax of these cmdlets is like the following example:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="79143-151">これらのコマンドレットの詳細については、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="79143-151">For details about these cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79143-152">このポリシーまたは設定:</span><span class="sxs-lookup"><span data-stu-id="79143-152">For this policy or setting:</span></span></th>
<th><span data-ttu-id="79143-153">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="79143-153">Use this cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79143-154">プレゼンスポリシー</span><span class="sxs-lookup"><span data-stu-id="79143-154">Presence policy</span></span></p></td>
<td><p><span data-ttu-id="79143-155"><strong>Get-CsPresencePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="79143-155"><strong>Get-CsPresencePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79143-156">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="79143-156">Conferencing policy</span></span></p></td>
<td><p><span data-ttu-id="79143-157"><strong>Get-CsConferencingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="79143-157"><strong>Get-CsConferencingPolicy</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79143-158">ダイヤルインアクセス番号</span><span class="sxs-lookup"><span data-stu-id="79143-158">Dial-in access numbers</span></span></p></td>
<td><p><span data-ttu-id="79143-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span><span class="sxs-lookup"><span data-stu-id="79143-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79143-160">ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="79143-160">Dial plans</span></span></p></td>
<td><p><span data-ttu-id="79143-161"><strong>Get-CsDialPlan</strong></span><span class="sxs-lookup"><span data-stu-id="79143-161"><strong>Get-CsDialPlan</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79143-162">音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="79143-162">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="79143-163"><strong>Get-CsVoicePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="79143-163"><strong>Get-CsVoicePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79143-164">音声ルート</span><span class="sxs-lookup"><span data-stu-id="79143-164">Voice routes</span></span></p></td>
<td><p><span data-ttu-id="79143-165"><strong>Get-CsVoiceRoute</strong></span><span class="sxs-lookup"><span data-stu-id="79143-165"><strong>Get-CsVoiceRoute</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79143-166">PSTN 使用法</span><span class="sxs-lookup"><span data-stu-id="79143-166">PSTN Usage</span></span></p></td>
<td><p><span data-ttu-id="79143-167"><strong>Get-CsPstnUsage</strong></span><span class="sxs-lookup"><span data-stu-id="79143-167"><strong>Get-CsPstnUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79143-168">Url</span><span class="sxs-lookup"><span data-stu-id="79143-168">URLs</span></span></p></td>
<td><p><span data-ttu-id="79143-169"><strong>CsSimpleUrlConfiguration の入手</strong></span><span class="sxs-lookup"><span data-stu-id="79143-169"><strong>Get-CsSimpleUrlConfiguration</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79143-170">外部アクセスポリシー</span><span class="sxs-lookup"><span data-stu-id="79143-170">External access policies</span></span></p></td>
<td><p><span data-ttu-id="79143-171"><strong>Get-CsExternalAccessPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="79143-171"><strong>Get-CsExternalAccessPolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79143-172">アーカイブポリシー</span><span class="sxs-lookup"><span data-stu-id="79143-172">Archiving policy</span></span></p></td>
<td><p><span data-ttu-id="79143-173"><strong>Get-CsArchivingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="79143-173"><strong>Get-CsArchivingPolicy</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

