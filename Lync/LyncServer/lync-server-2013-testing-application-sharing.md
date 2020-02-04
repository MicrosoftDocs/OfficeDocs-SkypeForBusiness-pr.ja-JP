---
title: 'Lync Server 2013: アプリケーション共有のテスト'
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
ms.openlocfilehash: ab428e5bbfb5ffc58fa7b1d092cd7fc04b117226
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-application-sharing-in-lync-server-2013"></a><span data-ttu-id="c9ba1-102">Lync Server 2013 でのアプリケーション共有のテスト</span><span class="sxs-lookup"><span data-stu-id="c9ba1-102">Testing application sharing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9ba1-103">_**最終更新日:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="c9ba1-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9ba1-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="c9ba1-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c9ba1-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="c9ba1-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9ba1-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="c9ba1-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c9ba1-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9ba1-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9ba1-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="c9ba1-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c9ba1-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c9ba1-110">Windows PowerShell のリモートインスタンスを使って実行する場合、ユーザーには、テスト用の CsASConference コマンドレットを実行するアクセス許可が与えられた RBAC の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsASConference cmdlet.</span></span> <span data-ttu-id="c9ba1-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c9ba1-112">説明</span><span class="sxs-lookup"><span data-stu-id="c9ba1-112">Description</span></span>

<span data-ttu-id="c9ba1-113">**CsASConference**コマンドレットを使用すると、アプリケーション共有が含まれるオンライン会議に参加できるテストユーザーが1組であることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-113">The **Test-CsASConference** cmdlet verifies that a pair of test users can participate in an online conference that includes application sharing.</span></span> <span data-ttu-id="c9ba1-114">これを行うには、コマンドレットによって Lync Server 2013 に2人のユーザーが登録され、次にいずれかのユーザーアカウントを使って、アプリケーションの共有を含む新しい会議を作成します。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-114">To do this, the cmdlet registers the two users with Lync Server 2013, and then it uses one of the user accounts to create a new conference that includes applications sharing.</span></span> <span data-ttu-id="c9ba1-115">次に、2番目のユーザーがその会議に参加できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-115">The cmdlet then verifies that the second user is able to join that conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c9ba1-116">テストの実行</span><span class="sxs-lookup"><span data-stu-id="c9ba1-116">Running the test</span></span>

<span data-ttu-id="c9ba1-117">例1に示すコマンドは、アプリ共有会議がプール atl-cs-001.litwareinc.com で実行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-117">The command shown in Example 1 verifies that an Application Sharing conference can be conducted on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="c9ba1-118">このコマンドは、指定されたプールのテストユーザーのペアを構成していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-118">This command assumes that you have configured a pair of test users for the specified pool.</span></span> <span data-ttu-id="c9ba1-119">このようなテストユーザーが存在しない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-119">If no such test users exist, the command will fail.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="c9ba1-120">例2プール atl-cs-001.litwareinc.com でのアプリケーション共有会議に参加するための、Join ランチャーサービスの機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-120">Example 2 tests the ability of the Join Launcher service to participate in an Application Sharing conference on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="c9ba1-121">このコマンドは、サービス自体のみをテストすることに注意してください。コマンドを実行するために、モバイルデバイスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-121">Note that this command tests only the service itself; you do not need any mobile devices in order to run the command.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

<span data-ttu-id="c9ba1-122">例2に示すコマンドは、ユーザーのペア (litwareinc\\pilar と litwareinc\\Kenmyer) が Lync Server 2013 にログオンして、アプリケーション共有会議を開催する機能をテストしています。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-122">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct an Application Sharing conference.</span></span> <span data-ttu-id="c9ba1-123">これを行うには、この例の最初のコマンドでは、Credential コマンドレットを使用して、user Pilar Ackerman の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイス Credential オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-123">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="c9ba1-124">(Logon name、litwareinc\\pilar はパラメーターとして指定されているため、Windows PowerShell 資格情報の要求ダイアログボックスでは、管理者は Pilar Ackerman アカウントのパスワードを入力する必要があります)。結果として得られた資格情報オブジェクトは、$cred 1 という名前の変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-124">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="c9ba1-125">2番目のコマンドでも同じことが実行されますが、今回は Ken Myer アカウントの credential オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-125">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="c9ba1-126">資格情報オブジェクトが手元にある場合、3番目のコマンドは、これら2人のユーザーが Lync Server 2013 にログオンして、アプリケーション共有会議を実行できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-126">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct an Application Sharing conference.</span></span> <span data-ttu-id="c9ba1-127">このタスクを実行するために、次のパラメーターと共に、 **CsASConference**コマンドレットが呼び出されます。 Targetfqdn (レジストラー POOL の FQDN)SenderSipAddress (最初のテストユーザーの SIP アドレス)SenderCredential (同じユーザーの資格情報が含まれている Windows PowerShell オブジェクト)ReceiverSipAddress (他のテストユーザーの SIP アドレス)ReceiverCredential (他のテストユーザーの資格情報を格納する Windows PowerShell オブジェクト)。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-127">To carry out this task, the **Test-CsASConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c9ba1-128">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="c9ba1-128">Determining success or failure</span></span>

<span data-ttu-id="c9ba1-129">アプリケーション共有が適切に構成されている場合は、次のような結果が返され、Result プロパティは Success とマークされ**ます。**</span><span class="sxs-lookup"><span data-stu-id="c9ba1-129">If application sharing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="c9ba1-130">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c9ba1-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c9ba1-131">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="c9ba1-131">Result : Success</span></span>

<span data-ttu-id="c9ba1-132">待ち時間: 00:00:01</span><span class="sxs-lookup"><span data-stu-id="c9ba1-132">Latency : 00:00:01</span></span>

<span data-ttu-id="c9ba1-133">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="c9ba1-133">Error Message :</span></span>

<span data-ttu-id="c9ba1-134">診断</span><span class="sxs-lookup"><span data-stu-id="c9ba1-134">Diagnosis :</span></span>

<span data-ttu-id="c9ba1-135">指定したユーザーがアプリケーションを共有できない場合、結果はエラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-135">If the specified users can't share applications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="c9ba1-136">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c9ba1-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c9ba1-137">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="c9ba1-137">Result : Failure</span></span>

<span data-ttu-id="c9ba1-138">待ち時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c9ba1-138">Latency : 00:00:00</span></span>

<span data-ttu-id="c9ba1-139">エラーメッセージ: 10060、接続されているパーティのため、接続に失敗しました</span><span class="sxs-lookup"><span data-stu-id="c9ba1-139">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="c9ba1-140">一定の期間が経過した後に正しく応答しなかった場合、または</span><span class="sxs-lookup"><span data-stu-id="c9ba1-140">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="c9ba1-141">接続されているホストに、接続に失敗しました</span><span class="sxs-lookup"><span data-stu-id="c9ba1-141">established connection failed because connected host has</span></span>

<span data-ttu-id="c9ba1-142">10.188.116.96 に応答できませんでした: 5061</span><span class="sxs-lookup"><span data-stu-id="c9ba1-142">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="c9ba1-143">内部例外: 接続の試行が失敗したため、接続できませんでした。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-143">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="c9ba1-144">しばらくしても、接続されているパーティが正しく応答しませんでした</span><span class="sxs-lookup"><span data-stu-id="c9ba1-144">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="c9ba1-145">接続されているホストが原因で、時刻、または接続に失敗しました</span><span class="sxs-lookup"><span data-stu-id="c9ba1-145">time, or established connection failed because connected host</span></span>

<span data-ttu-id="c9ba1-146">さんが10.188.116.96 に応答できませんでした: 5061</span><span class="sxs-lookup"><span data-stu-id="c9ba1-146">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="c9ba1-147">診断</span><span class="sxs-lookup"><span data-stu-id="c9ba1-147">Diagnosis :</span></span>

<span data-ttu-id="c9ba1-148">たとえば、前回の出力には、"接続されているパーティは正しく応答しませんでした" というメモが含まれています。通常、エッジサーバーに問題があることを示します。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-148">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c9ba1-149">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="c9ba1-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="c9ba1-150">次に **、テスト用の CsASConference**が失敗する一般的な理由をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-150">Here are some common reasons why **Test-CsASConference** might fail:</span></span>

  - <span data-ttu-id="c9ba1-151">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-151">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="c9ba1-152">使用する場合は、オプションのパラメーターが正しく構成されている必要があります。または、テストが失敗します。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-152">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="c9ba1-153">省略可能なパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-153">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="c9ba1-154">テストユーザーに会議ポリシーが割り当てられていて、それらのユーザーがアプリケーション共有を使用できない場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-154">This command will fail if the test users were assigned a conferencing policy that prevents them from using application sharing.</span></span>

  - <span data-ttu-id="c9ba1-155">エッジサーバーが正しく構成されていないか、まだ展開されていない場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="c9ba1-155">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c9ba1-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9ba1-156">See Also</span></span>


[<span data-ttu-id="c9ba1-157">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="c9ba1-157">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[<span data-ttu-id="c9ba1-158">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="c9ba1-158">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

