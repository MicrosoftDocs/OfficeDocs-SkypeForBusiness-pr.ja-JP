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
ms.openlocfilehash: af4bd6dd911b43714dffa48c3b21d3329b2aaa01
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a><span data-ttu-id="f0229-102">Lync Server 2013 での UCWA 会議のテスト</span><span class="sxs-lookup"><span data-stu-id="f0229-102">Testing UCWA conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0229-103">_**トピックの最終更新日:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="f0229-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0229-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="f0229-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f0229-105">毎日</span><span class="sxs-lookup"><span data-stu-id="f0229-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0229-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="f0229-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f0229-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0229-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0229-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="f0229-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f0229-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0229-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f0229-110">Windows PowerShell のリモートインスタンスを使用して実行する場合は、 <strong>test-csucwaconference</strong>コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0229-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUcwaConference</strong> cmdlet.</span></span> <span data-ttu-id="f0229-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0229-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f0229-112">説明</span><span class="sxs-lookup"><span data-stu-id="f0229-112">Description</span></span>

<span data-ttu-id="f0229-113">**Test-csucwaconference**コマンドレットは、テストユーザーのペアが、統合コミュニケーション Web API (ucwa) を使用してオンライン会議をスケジュール、参加、および実行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0229-113">The **Test-CsUcwaConference** cmdlet verifies that a pair of test users can schedule, join, and then conduct an online conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="f0229-114">これを行うために、コマンドレットは Lync Server web チケットサービスを使用して2つのテストユーザーを認証し、それらを Lync Server に登録します。</span><span class="sxs-lookup"><span data-stu-id="f0229-114">To do this, the cmdlet uses the Lync Server web ticket service to authenticate the two test users and register them with Lync Server.</span></span> <span data-ttu-id="f0229-115">コマンドレットは、開催者の資格情報を使用して会議を開始し、参加者に会議への参加を依頼します。</span><span class="sxs-lookup"><span data-stu-id="f0229-115">The cmdlet then starts a conference using the organizer credentials and invites the participant to join the meeting.</span></span> <span data-ttu-id="f0229-116">会議が参加した後、 **test-csucwaconference**コマンドレットは、ユーザーが exchange インスタントメッセージやプールの実行などの操作を行うことができることを確認した後、会議を切断し、2つのテストユーザーの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="f0229-116">After the meeting is joined, the **Test-CsUcwaConference** cmdlet verifies that the users can do such things as exchange instant message and conduct pools, then disconnects the conference and unregisters the two test users.</span></span> <span data-ttu-id="f0229-117">スケジュールされた会議は、テストが完了したときにも削除されます。</span><span class="sxs-lookup"><span data-stu-id="f0229-117">The scheduled conference will also be deleted when the test is finished.</span></span>

<span data-ttu-id="f0229-118">匿名ユーザーがオンライン会議に参加できるかどうかを判断するには、 **test-csucwaconference**コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="f0229-118">The **Test-CsUcwaConference** cmdlet can also be used to determine whether anonymous users can join online conferences.</span></span>

<span data-ttu-id="f0229-119">**Test-csucwaconference**コマンドレットは、ucwa がそのプールにインストールされていない限り、Microsoft Lync Server 2010 プールに対して実行しないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="f0229-119">Note that the **Test-CsUcwaConference** cmdlet should not be run against a Microsoft Lync Server 2010 pool unless UCWA was installed on that pool.</span></span> <span data-ttu-id="f0229-120">UCWA がインストールされていない場合は、 **test-csucwaconference**コマンドレットの呼び出しは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f0229-120">If UCWA has not been installed then the call to the **Test-CsUcwaConference** cmdlet will fail.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f0229-121">テストの実行</span><span class="sxs-lookup"><span data-stu-id="f0229-121">Running the test</span></span>

<span data-ttu-id="f0229-122">例1に示すコマンドを実行すると、テストユーザーのペアが、プール atl-cs-001.litwareinc.com で UCWA 会議に参加できることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="f0229-122">The command shown in Example 1 verifies that a pair of test users can participate in an UCWA conference on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="f0229-123">Atl-cs-001.litwareinc.com の正常性の監視構成テストユーザーのペアが事前に定義されていない場合、このコマンドは失敗することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f0229-123">Note that this command will fail if you have not predefined a pair of health monitoring configuration test users for atl-cs-001.litwareinc.com.</span></span>

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="f0229-124">例2のコマンドは、ユーザーのペア (litwareinc\\pilar と litwareinc\\kenmyer) が ucwa 会議に参加できるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="f0229-124">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to participate in an UCWA conference.</span></span> <span data-ttu-id="f0229-125">これを行うには、例の最初のコマンドは、資格情報コマンドレットを使用して、user Pilar Ackerman の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0229-125">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="f0229-126">(ログオン名 litwareinc\\pilar がパラメーターとして含まれているため、[Windows PowerShell 資格情報の要求] ダイアログボックスでは、管理者のみが Pilar Ackerman アカウントのパスワードを入力する必要があります)。その後、結果の資格情報オブジェクトは $cred 1 という名前の変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="f0229-126">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="f0229-127">2番目のコマンドは同じことを行いますが、今度は Ken Myer アカウントの credential オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="f0229-127">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="f0229-128">2つの資格情報オブジェクトがある場合、この例の3番目のコマンドでは、2人のユーザーが UCWA 会議に参加できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="f0229-128">With the two credential objects in hand, the third command in the example determines whether the two users can participate in an UCWA conference.</span></span> <span data-ttu-id="f0229-129">このタスクを実行するには、 **test-csucwaconference**コマンドレットを次のパラメーターと共に呼び出します。 targetfqdn (レジストラープールの FQDN)。OrganizerSipAddress (会議の開催者の SIP アドレス)。Groupname Ercredential (この同じユーザーの資格情報を含む Windows PowerShell オブジェクト)。ParticipantSipAddress (他のテストユーザーの SIP アドレス)。ParticipantCredential (他のユーザーの資格情報を含む Windows PowerShell コマンドラインインターフェイスオブジェクト)。</span><span class="sxs-lookup"><span data-stu-id="f0229-129">To run this task, the **Test-CsUcwaConference** cmdlet is called, together with the following parameters: TargetFqdn (the FQDN of the Registrar pool); OrganizerSipAddress (the SIP address for the meeting organizer); OrganizerCredential (the Windows PowerShell object that contains the credentials for this same user); ParticipantSipAddress (the SIP address for the other test user); and ParticipantCredential (the Windows PowerShell command-line interface object that contains the credentials for the other user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f0229-130">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="f0229-130">Determining success or failure</span></span>

<span data-ttu-id="f0229-131">会議が正しく構成されている場合は、次のような出力が得られ、Result プロパティは Success としてマークされ**ます。**</span><span class="sxs-lookup"><span data-stu-id="f0229-131">If conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="f0229-132">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f0229-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f0229-133">ターゲット Uri: https://LyncTest-Corp. LyncTest.</span><span class="sxs-lookup"><span data-stu-id="f0229-133">Target Uri : https:// LyncTest-SE.LyncTest.SelfHost.Corp.</span></span>

<span data-ttu-id="f0229-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span><span class="sxs-lookup"><span data-stu-id="f0229-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span></span>

<span data-ttu-id="f0229-135">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="f0229-135">Result : Success</span></span>

<span data-ttu-id="f0229-136">待機時間:00:00: 14.9862716</span><span class="sxs-lookup"><span data-stu-id="f0229-136">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="f0229-137">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="f0229-137">Error Message :</span></span>

<span data-ttu-id="f0229-138">分析</span><span class="sxs-lookup"><span data-stu-id="f0229-138">Diagnosis :</span></span>

<span data-ttu-id="f0229-139">指定したユーザーが会議を使用できない場合、結果は**失敗**として表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="f0229-139">If the specified users can't use conferencing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f0229-140">警告: 指定された完全修飾のレジストラーポート番号を読み取ることができませんでした</span><span class="sxs-lookup"><span data-stu-id="f0229-140">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="f0229-141">ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="f0229-141">domain name (FQDN).</span></span> <span data-ttu-id="f0229-142">既定のレジストラーポート番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0229-142">Using default Registrar port number.</span></span> <span data-ttu-id="f0229-143">例外</span><span class="sxs-lookup"><span data-stu-id="f0229-143">Exception:</span></span>

<span data-ttu-id="f0229-144">System.invalidoperationexception: トポロジ内に一致するクラスターが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="f0229-144">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="f0229-145">下部</span><span class="sxs-lookup"><span data-stu-id="f0229-145">at</span></span>

<span data-ttu-id="f0229-146">TryRetri を SipSyntheticTransaction していることを示します。</span><span class="sxs-lookup"><span data-stu-id="f0229-146">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="f0229-147">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="f0229-147">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="f0229-148">Test-csucwaconference: に対してテストユーザーが割り当てられていません</span><span class="sxs-lookup"><span data-stu-id="f0229-148">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="f0229-149">\[LyncTest.SelfHost.Corp.Microsoft.com\]。</span><span class="sxs-lookup"><span data-stu-id="f0229-149">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="f0229-150">テストユーザーの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="f0229-150">Verify test user configuration.</span></span>

<span data-ttu-id="f0229-151">行: 1 char: 1</span><span class="sxs-lookup"><span data-stu-id="f0229-151">At line:1 char:1</span></span>

<span data-ttu-id="f0229-152">\+Test-csucwaconference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="f0229-152">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="f0229-153">\+カテゴリ情報: ResourceUnavailable 不可: (:)\[Test-csucwaconference\]</span><span class="sxs-lookup"><span data-stu-id="f0229-153">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="f0229-154">、System.invalidoperationexception</span><span class="sxs-lookup"><span data-stu-id="f0229-154">, InvalidOperationException</span></span>

<span data-ttu-id="f0229-155">\+FullyQualifiedErrorId: Notていない Testusers、Microsoft Rtc.</span><span class="sxs-lookup"><span data-stu-id="f0229-155">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="f0229-156">TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="f0229-156">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f0229-157">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="f0229-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="f0229-158">**Test-csucwaconference**が失敗する可能性のある一般的な原因を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f0229-158">Here are some common reasons why **Test-CsUcwaConference** might fail:</span></span>

  - <span data-ttu-id="f0229-159">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="f0229-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="f0229-160">省略可能なパラメーターが使用されている場合、オプションのパラメーターが正しく構成されている必要があります。テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f0229-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="f0229-161">オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0229-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="f0229-162">会議を開催できるかどうかは、会議を開催したユーザー ( **test-csucwaconference**コマンドレットの場合は "sender") に割り当てられている会議ポリシーによって決まります。</span><span class="sxs-lookup"><span data-stu-id="f0229-162">The ability to conduct a conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsUcwaConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="f0229-163">開催者が会議に共同作業のアクティビティを含めることが許可されていない場合 (たとえば、その会議ポリシーで EnableDataCollaboration プロパティが False に設定されている場合)、 **test-csucwaconference**コマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f0229-163">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsUcwaConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="f0229-164">エッジサーバーの構成が正しくないか、まだ展開されていない場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f0229-164">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f0229-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0229-165">See Also</span></span>


[<span data-ttu-id="f0229-166">テスト-CsASConference</span><span class="sxs-lookup"><span data-stu-id="f0229-166">Test-CsASConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[<span data-ttu-id="f0229-167">Test-csdataconference</span><span class="sxs-lookup"><span data-stu-id="f0229-167">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[<span data-ttu-id="f0229-168">テスト-CsAVConference 会議</span><span class="sxs-lookup"><span data-stu-id="f0229-168">Test-CsAVConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

