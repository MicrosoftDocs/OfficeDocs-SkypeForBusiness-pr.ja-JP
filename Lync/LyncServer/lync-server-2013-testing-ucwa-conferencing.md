---
title: 'Lync Server 2013: UCWA 会議のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9496b2a860f0a8272d6eb98df6a2c897aa245ec9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a><span data-ttu-id="e27e8-102">Lync Server 2013 での UCWA 会議のテスト</span><span class="sxs-lookup"><span data-stu-id="e27e8-102">Testing UCWA conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e27e8-103">_**最終更新日:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="e27e8-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e27e8-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="e27e8-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e27e8-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="e27e8-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e27e8-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="e27e8-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e27e8-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e27e8-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e27e8-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e27e8-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e27e8-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e27e8-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e27e8-110">Windows PowerShell のリモートインスタンスを使って実行する場合は、 <strong>CsUcwaConference</strong>コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e27e8-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUcwaConference</strong> cmdlet.</span></span> <span data-ttu-id="e27e8-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e27e8-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e27e8-112">説明</span><span class="sxs-lookup"><span data-stu-id="e27e8-112">Description</span></span>

<span data-ttu-id="e27e8-113">**CsUcwaConference**コマンドレットは、1組のテストユーザーがユニファイドコミュニケーション Web API (ucwa) を使用してオンライン会議をスケジュール、参加、実施できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e27e8-113">The **Test-CsUcwaConference** cmdlet verifies that a pair of test users can schedule, join, and then conduct an online conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="e27e8-114">これを行うには、コマンドレットは Lync Server web ticket サービスを使って2つのテストユーザーを認証し、Lync Server に登録します。</span><span class="sxs-lookup"><span data-stu-id="e27e8-114">To do this, the cmdlet uses the Lync Server web ticket service to authenticate the two test users and register them with Lync Server.</span></span> <span data-ttu-id="e27e8-115">次に、このコマンドレットは開催者の資格情報を使用して会議を開始し、参加者を会議に参加するように招待します。</span><span class="sxs-lookup"><span data-stu-id="e27e8-115">The cmdlet then starts a conference using the organizer credentials and invites the participant to join the meeting.</span></span> <span data-ttu-id="e27e8-116">会議が参加した後、 **CsUcwaConference**コマンドレットは、ユーザーが exchange インスタントメッセージやプールの実施などの操作を実行できることを確認した後、会議を切断し、2つのテストユーザーの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="e27e8-116">After the meeting is joined, the **Test-CsUcwaConference** cmdlet verifies that the users can do such things as exchange instant message and conduct pools, then disconnects the conference and unregisters the two test users.</span></span> <span data-ttu-id="e27e8-117">スケジュールされた会議も、テストが完了したときに削除されます。</span><span class="sxs-lookup"><span data-stu-id="e27e8-117">The scheduled conference will also be deleted when the test is finished.</span></span>

<span data-ttu-id="e27e8-118">**CsUcwaConference**コマンドレットを使用して、匿名ユーザーがオンライン会議に参加できるかどうかを判断することもできます。</span><span class="sxs-lookup"><span data-stu-id="e27e8-118">The **Test-CsUcwaConference** cmdlet can also be used to determine whether anonymous users can join online conferences.</span></span>

<span data-ttu-id="e27e8-119">UCWA がそのプールにインストールされていない場合は、 **CsUcwaConference**コマンドレットを Microsoft Lync Server 2010 プールに対して実行しないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="e27e8-119">Note that the **Test-CsUcwaConference** cmdlet should not be run against a Microsoft Lync Server 2010 pool unless UCWA was installed on that pool.</span></span> <span data-ttu-id="e27e8-120">UCWA がインストールされていない場合は、 **CsUcwaConference**コマンドレットの呼び出しが失敗します。</span><span class="sxs-lookup"><span data-stu-id="e27e8-120">If UCWA has not been installed then the call to the **Test-CsUcwaConference** cmdlet will fail.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e27e8-121">テストの実行</span><span class="sxs-lookup"><span data-stu-id="e27e8-121">Running the test</span></span>

<span data-ttu-id="e27e8-122">例1に示すコマンドは、テストユーザーのペアが、プール atl-cs-001.litwareinc.com の UCWA 会議に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e27e8-122">The command shown in Example 1 verifies that a pair of test users can participate in an UCWA conference on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="e27e8-123">Atl-cs-001.litwareinc.com の正常性監視構成テストユーザーのペアを定義していない場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="e27e8-123">Note that this command will fail if you have not predefined a pair of health monitoring configuration test users for atl-cs-001.litwareinc.com.</span></span>

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="e27e8-124">例2に示すコマンドは、UCWA 会議に参加するユーザーのペア\\(litwareinc pilar\\と litwareinc kenmyer) の機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="e27e8-124">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to participate in an UCWA conference.</span></span> <span data-ttu-id="e27e8-125">これを行うには、この例の最初のコマンドでは、Credential コマンドレットを使用して、user Pilar Ackerman の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e27e8-125">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="e27e8-126">(Logon name、litwareinc\\pilar はパラメーターとして指定されているため、Windows PowerShell 資格情報の要求ダイアログボックスでは、管理者は Pilar Ackerman アカウントのパスワードを入力する必要があります)。結果として得られた資格情報オブジェクトは、$cred 1 という名前の変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="e27e8-126">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="e27e8-127">2番目のコマンドでも同じことが実行されますが、今回は Ken Myer アカウントの credential オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="e27e8-127">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="e27e8-128">2つの資格情報オブジェクトを使うと、この例の3番目のコマンドは、2人のユーザーが UCWA 会議に参加できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e27e8-128">With the two credential objects in hand, the third command in the example determines whether the two users can participate in an UCWA conference.</span></span> <span data-ttu-id="e27e8-129">このタスクを実行するために、 **CsUcwaConference**コマンドレットが呼び出され、次のパラメーターが使用されます。 targetfqdn (レジストラープールの FQDN)OrganizerSipAddress (会議の開催者の SIP アドレス)組織の資格情報 (同じユーザーの資格情報を格納する Windows PowerShell オブジェクト)ParticipantSipAddress (他のテストユーザーの SIP アドレス)ParticipantCredential (他のユーザーの資格情報が含まれている Windows PowerShell コマンドラインインターフェイスオブジェクト) を選びます。</span><span class="sxs-lookup"><span data-stu-id="e27e8-129">To run this task, the **Test-CsUcwaConference** cmdlet is called, together with the following parameters: TargetFqdn (the FQDN of the Registrar pool); OrganizerSipAddress (the SIP address for the meeting organizer); OrganizerCredential (the Windows PowerShell object that contains the credentials for this same user); ParticipantSipAddress (the SIP address for the other test user); and ParticipantCredential (the Windows PowerShell command-line interface object that contains the credentials for the other user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e27e8-130">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="e27e8-130">Determining success or failure</span></span>

<span data-ttu-id="e27e8-131">会議が適切に構成されている場合は、次のような結果が返され**ます。** これには、Result プロパティが Success とマークされています。</span><span class="sxs-lookup"><span data-stu-id="e27e8-131">If conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="e27e8-132">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e27e8-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e27e8-133">ターゲット Uri: https://LyncTest-SE. LyncTest.</span><span class="sxs-lookup"><span data-stu-id="e27e8-133">Target Uri : https:// LyncTest-SE.LyncTest.SelfHost.Corp.</span></span>

<span data-ttu-id="e27e8-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span><span class="sxs-lookup"><span data-stu-id="e27e8-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span></span>

<span data-ttu-id="e27e8-135">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="e27e8-135">Result : Success</span></span>

<span data-ttu-id="e27e8-136">待ち時間:00:00: 14.9862716</span><span class="sxs-lookup"><span data-stu-id="e27e8-136">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="e27e8-137">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="e27e8-137">Error Message :</span></span>

<span data-ttu-id="e27e8-138">診断</span><span class="sxs-lookup"><span data-stu-id="e27e8-138">Diagnosis :</span></span>

<span data-ttu-id="e27e8-139">指定されたユーザーが会議を使用できない場合は、結果**がエラーとして**表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="e27e8-139">If the specified users can't use conferencing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="e27e8-140">警告: 指定した完全修飾のレジストラーポート番号の読み取りに失敗しました</span><span class="sxs-lookup"><span data-stu-id="e27e8-140">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="e27e8-141">ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="e27e8-141">domain name (FQDN).</span></span> <span data-ttu-id="e27e8-142">既定のレジストラーポート番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="e27e8-142">Using default Registrar port number.</span></span> <span data-ttu-id="e27e8-143">エラー</span><span class="sxs-lookup"><span data-stu-id="e27e8-143">Exception:</span></span>

<span data-ttu-id="e27e8-144">InvalidOperationException: トポロジで一致するクラスターが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="e27e8-144">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="e27e8-145">自宅</span><span class="sxs-lookup"><span data-stu-id="e27e8-145">at</span></span>

<span data-ttu-id="e27e8-146">SipSyntheticTransaction-TryRetri の同期を行います。</span><span class="sxs-lookup"><span data-stu-id="e27e8-146">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="e27e8-147">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="e27e8-147">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="e27e8-148">CsUcwaConference: のテストユーザーが割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="e27e8-148">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="e27e8-149">\[LyncTest.SelfHost.Corp.Microsoft.com\]。</span><span class="sxs-lookup"><span data-stu-id="e27e8-149">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="e27e8-150">テストユーザー構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="e27e8-150">Verify test user configuration.</span></span>

<span data-ttu-id="e27e8-151">行: 1 char: 1</span><span class="sxs-lookup"><span data-stu-id="e27e8-151">At line:1 char:1</span></span>

<span data-ttu-id="e27e8-152">\+CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="e27e8-152">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="e27e8-153">\+カテゴリ情報: ResourceUnavailable 使用できません: (:)\[テスト-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="e27e8-153">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="e27e8-154">、InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="e27e8-154">, InvalidOperationException</span></span>

<span data-ttu-id="e27e8-155">\+FullyQualifiedErrorId: Notん Testusers、Microsoft Rtc。</span><span class="sxs-lookup"><span data-stu-id="e27e8-155">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="e27e8-156">TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="e27e8-156">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e27e8-157">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="e27e8-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="e27e8-158">次に **、テスト-CsUcwaConference**が失敗する可能性がある一般的な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="e27e8-158">Here are some common reasons why **Test-CsUcwaConference** might fail:</span></span>

  - <span data-ttu-id="e27e8-159">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="e27e8-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="e27e8-160">使用する場合は、オプションのパラメーターが正しく構成されている必要があります。または、テストが失敗します。</span><span class="sxs-lookup"><span data-stu-id="e27e8-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="e27e8-161">省略可能なパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="e27e8-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="e27e8-162">会議を開催する機能は、会議を開催したユーザーに割り当てられている会議ポリシー ( **CsUcwaConference**コマンドレットの場合は "送信者") によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e27e8-162">The ability to conduct a conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsUcwaConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="e27e8-163">開催者が、会議に共同作業のアクティビティを含めることを許可していない場合 (たとえば、自分の会議ポリシーの EnableDataCollaboration プロパティが False に設定されている場合など)、 **CsUcwaConference**コマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="e27e8-163">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsUcwaConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="e27e8-164">エッジサーバーが正しく構成されていないか、まだ展開されていない場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="e27e8-164">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e27e8-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="e27e8-165">See Also</span></span>


[<span data-ttu-id="e27e8-166">Test-CsASConference</span><span class="sxs-lookup"><span data-stu-id="e27e8-166">Test-CsASConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[<span data-ttu-id="e27e8-167">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="e27e8-167">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[<span data-ttu-id="e27e8-168">Test-CsAVConference</span><span class="sxs-lookup"><span data-stu-id="e27e8-168">Test-CsAVConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

