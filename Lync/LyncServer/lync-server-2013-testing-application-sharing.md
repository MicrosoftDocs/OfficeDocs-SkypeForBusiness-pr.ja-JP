---
title: 'Lync Server 2013: アプリケーション共有のテスト'
description: 'Lync Server 2013: アプリケーション共有のテスト。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f857908e374239b4054985b88951cd12720ed418
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560723"
---
# <a name="testing-application-sharing-in-lync-server-2013"></a><span data-ttu-id="25451-103">Lync Server 2013 でのアプリケーション共有のテスト</span><span class="sxs-lookup"><span data-stu-id="25451-103">Testing application sharing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25451-104">_**トピックの最終更新日:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="25451-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25451-105">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="25451-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="25451-106">毎日</span><span class="sxs-lookup"><span data-stu-id="25451-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25451-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="25451-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="25451-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="25451-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25451-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="25451-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="25451-110">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="25451-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="25451-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsASConference コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="25451-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsASConference cmdlet.</span></span> <span data-ttu-id="25451-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="25451-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="25451-113">説明</span><span class="sxs-lookup"><span data-stu-id="25451-113">Description</span></span>

<span data-ttu-id="25451-114">**Test-CsASConference**コマンドレットは、テストユーザーのペアがアプリケーション共有を含むオンライン会議に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="25451-114">The **Test-CsASConference** cmdlet verifies that a pair of test users can participate in an online conference that includes application sharing.</span></span> <span data-ttu-id="25451-115">これを行うために、コマンドレットは2人のユーザーを Lync Server 2013 に登録し、ユーザーアカウントの1人を使用して、アプリケーション共有を含む新しい会議を作成します。</span><span class="sxs-lookup"><span data-stu-id="25451-115">To do this, the cmdlet registers the two users with Lync Server 2013, and then it uses one of the user accounts to create a new conference that includes applications sharing.</span></span> <span data-ttu-id="25451-116">その後、もう 1 人のユーザーが電話会議に参加できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="25451-116">The cmdlet then verifies that the second user is able to join that conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="25451-117">テストの実行</span><span class="sxs-lookup"><span data-stu-id="25451-117">Running the test</span></span>

<span data-ttu-id="25451-p103">例 1 に示すコマンドは、atl-cs-001.litwareinc.com というプールでアプリケーション共有電話会議を実施できるかどうかを確認します。ここでは、指定するプールに対して 1 組のテスト ユーザーが構成済みであることを前提としています。テスト ユーザーが構成されていない場合、コマンドの実行は失敗します。</span><span class="sxs-lookup"><span data-stu-id="25451-p103">The command shown in Example 1 verifies that an Application Sharing conference can be conducted on the pool atl-cs-001.litwareinc.com. This command assumes that you have configured a pair of test users for the specified pool. If no such test users exist, the command will fail.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="25451-p104">例 2 では、atl-cs-001.litwareinc.com というプールでのアプリケーション共有電話会議に Join Launcher サービスが参加できるかどうかをテストします。このコマンドはサービスのみをテストします。このコマンドを実行するためにモバイル デバイスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="25451-p104">Example 2 tests the ability of the Join Launcher service to participate in an Application Sharing conference on the pool atl-cs-001.litwareinc.com. Note that this command tests only the service itself; you do not need any mobile devices in order to run the command.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

<span data-ttu-id="25451-123">例2のコマンドは、ユーザーのペア (litwareinc \\ pilar と litwareinc \\ kenmyer) が Lync Server 2013 にログオンして、アプリケーション共有会議を開始できるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="25451-123">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct an Application Sharing conference.</span></span> <span data-ttu-id="25451-124">これを行うには、この例の最初のコマンドは Get-Credential コマンドレットを使用して、user Pilar Ackerman の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="25451-124">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="25451-125">(ログオン名 litwareinc \\ pilar がパラメーターとして含まれているため、[Windows PowerShell 資格情報の要求] ダイアログボックスでは、管理者のみが Pilar Ackerman アカウントのパスワードを入力する必要があります)。その後、結果として得られる資格情報オブジェクトは $cred 1 という名前の変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="25451-125">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="25451-126">2番目のコマンドは同じことを行いますが、今度は Ken Myer アカウントの credential オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="25451-126">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="25451-127">資格情報オブジェクトが手元にある場合、3番目のコマンドは、これら2人のユーザーが Lync Server 2013 にログオンして、アプリケーション共有会議を実行できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="25451-127">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct an Application Sharing conference.</span></span> <span data-ttu-id="25451-128">このタスクを実行するために、次のパラメーターと共に、 **Test-CsASConference** コマンドレットが呼び出されます。 targetfqdn (レジストラープールの FQDN)。SenderSipAddress (最初のテストユーザーの SIP アドレス)。SenderCredential (この同じユーザーの資格情報を含む Windows PowerShell オブジェクト)。ReceiverSipAddress (他のテストユーザーの SIP アドレス)。と ReceiverCredential (他のテストユーザーの資格情報を格納している Windows PowerShell オブジェクト)。</span><span class="sxs-lookup"><span data-stu-id="25451-128">To carry out this task, the **Test-CsASConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="25451-129">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="25451-129">Determining success or failure</span></span>

<span data-ttu-id="25451-130">アプリケーション共有が正しく構成されている場合は、次のような出力が得られ、Result プロパティは Success としてマークされ **ます。**</span><span class="sxs-lookup"><span data-stu-id="25451-130">If application sharing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="25451-131">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="25451-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="25451-132">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="25451-132">Result : Success</span></span>

<span data-ttu-id="25451-133">待機時間: 00:00:01</span><span class="sxs-lookup"><span data-stu-id="25451-133">Latency : 00:00:01</span></span>

<span data-ttu-id="25451-134">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="25451-134">Error Message :</span></span>

<span data-ttu-id="25451-135">分析</span><span class="sxs-lookup"><span data-stu-id="25451-135">Diagnosis :</span></span>

<span data-ttu-id="25451-136">指定したユーザーがアプリケーションを共有できない場合、結果は失敗として表示され、追加情報が Error および診断プロパティに記録されます。</span><span class="sxs-lookup"><span data-stu-id="25451-136">If the specified users can't share applications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="25451-137">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="25451-137">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="25451-138">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="25451-138">Result : Failure</span></span>

<span data-ttu-id="25451-139">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="25451-139">Latency : 00:00:00</span></span>

<span data-ttu-id="25451-140">エラーメッセージ: 10060。接続しているパーティが原因で接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="25451-140">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="25451-141">一定期間後に正しく応答しなかったか、または</span><span class="sxs-lookup"><span data-stu-id="25451-141">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="25451-142">接続されたホストの接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="25451-142">established connection failed because connected host has</span></span>

<span data-ttu-id="25451-143">10.188.116.96: 5061 に応答できませんでした</span><span class="sxs-lookup"><span data-stu-id="25451-143">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="25451-144">内部例外: 接続の試行が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="25451-144">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="25451-145">接続されたパーティは、一定期間の後に正しく応答しませんでした</span><span class="sxs-lookup"><span data-stu-id="25451-145">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="25451-146">接続されているホストが原因で、接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="25451-146">time, or established connection failed because connected host</span></span>

<span data-ttu-id="25451-147">10.188.116.96: 5061 に応答できませんでした</span><span class="sxs-lookup"><span data-stu-id="25451-147">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="25451-148">分析</span><span class="sxs-lookup"><span data-stu-id="25451-148">Diagnosis :</span></span>

<span data-ttu-id="25451-149">たとえば、前述の出力には、通常、エッジサーバーに問題があることを示す「接続されたパーティは正しく応答しませんでした」というメモが含まれています。</span><span class="sxs-lookup"><span data-stu-id="25451-149">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="25451-150">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="25451-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="25451-151">次に **、Test-CsASConference** が失敗する主な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="25451-151">Here are some common reasons why **Test-CsASConference** might fail:</span></span>

  - <span data-ttu-id="25451-152">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="25451-152">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="25451-153">省略可能なパラメーターが使用されている場合、オプションのパラメーターが正しく構成されている必要があります。テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="25451-153">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="25451-154">オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="25451-154">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="25451-155">テストユーザーにアプリケーション共有の使用を禁止する電話会議ポリシーが割り当てられている場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="25451-155">This command will fail if the test users were assigned a conferencing policy that prevents them from using application sharing.</span></span>

  - <span data-ttu-id="25451-156">エッジサーバーの構成が正しくないか、まだ展開されていない場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="25451-156">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="25451-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="25451-157">See Also</span></span>


[<span data-ttu-id="25451-158">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="25451-158">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[<span data-ttu-id="25451-159">Test-csdataconference</span><span class="sxs-lookup"><span data-stu-id="25451-159">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

