---
title: 'Lync Server 2013: 会議での共有のテスト'
description: 'Lync Server 2013: 会議での共有のテスト。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e569a97d102664b64c201af9b60061813df69ef5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556243"
---
# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a><span data-ttu-id="fe44a-103">Lync Server 2013 での会議での共有のテスト</span><span class="sxs-lookup"><span data-stu-id="fe44a-103">Testing sharing in conferences in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe44a-104">_**トピックの最終更新日:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="fe44a-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe44a-105">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="fe44a-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="fe44a-106">毎日</span><span class="sxs-lookup"><span data-stu-id="fe44a-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe44a-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="fe44a-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="fe44a-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe44a-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe44a-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fe44a-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="fe44a-110">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe44a-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="fe44a-111">Windows PowerShell のリモートインスタンスを使用して実行する場合は、 <strong>test-csdataconference</strong> コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe44a-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDataConference</strong> cmdlet.</span></span> <span data-ttu-id="fe44a-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fe44a-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="fe44a-113">説明</span><span class="sxs-lookup"><span data-stu-id="fe44a-113">Description</span></span>

<span data-ttu-id="fe44a-114">Lync Server 2013 のデータ会議とは、ホワイトボードや注釈などのコラボレーションアクティビティを使用する会議のことです。</span><span class="sxs-lookup"><span data-stu-id="fe44a-114">In Lync Server 2013, a data conference is any conference where collaborative activities such as whiteboarding or annotations are used.</span></span> <span data-ttu-id="fe44a-115">**Test-csdataconference**コマンドレットを使用すると、ユーザーのペアがデータ会議に参加できることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="fe44a-115">The **Test-CsDataConference** cmdlet enables you to verify that a pair of users are able to take part in a data conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="fe44a-116">テストの実行</span><span class="sxs-lookup"><span data-stu-id="fe44a-116">Running the test</span></span>

<span data-ttu-id="fe44a-p103">例 1 に示すコマンドは、atl-cs-001.litwareinc.com というプールでデータ電話会議を実施できるかどうかを確認します。ここでは、指定するプールに対して 1 組のテスト ユーザーが構成済みであることを前提としています。テスト ユーザーが構成されていない場合、コマンドの実行は失敗します。</span><span class="sxs-lookup"><span data-stu-id="fe44a-p103">The command shown in Example 1 verifies that a data conference can be conducted on the pool atl-cs-001.litwareinc.com. This command assumes that you have configured a pair of test users for the specified pool. If no such test users exist, the command will fail.</span></span>

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="fe44a-120">例2のコマンドは、ユーザーのペア (litwareinc \\ pilar と litwareinc \\ kenmyer) が Lync Server 2013 にログオンし、データ会議を行うことができるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="fe44a-120">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct a data conference.</span></span> <span data-ttu-id="fe44a-121">これを行うために、この例の最初のコマンドは、 **資格情報** コマンドレットを使用して、User Pilar Ackerman の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="fe44a-121">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="fe44a-122">(ログオン名 litwareinc \\ pilar がパラメーターとして含まれているため、[Windows PowerShell 資格情報の要求] ダイアログボックスでは、管理者のみが Pilar Ackerman アカウントのパスワードを入力する必要があります)。その後、結果として得られる資格情報オブジェクトは $cred 1 という名前の変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="fe44a-122">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="fe44a-123">2番目のコマンドは同じことを行いますが、今度は Ken Myer アカウントの credential オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="fe44a-123">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="fe44a-124">資格情報オブジェクトが手元にある場合、3番目のコマンドは、これら2人のユーザーが Lync Server 2013 にログオンしてデータ会議を実行できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="fe44a-124">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct a data conference.</span></span> <span data-ttu-id="fe44a-125">このタスクを実行するために、 **test-csdataconference** コマンドレットを次のパラメーターと共に呼び出します。 targetfqdn (レジストラープールの FQDN)。SenderSipAddress (最初のテストユーザーの SIP アドレス)。SenderCredential (この同じユーザーの資格情報を含む Windows PowerShell オブジェクト)。ReceiverSipAddress (他のテストユーザーの SIP アドレス)。と ReceiverCredential (他のテストユーザーの資格情報を格納している Windows PowerShell オブジェクト)。</span><span class="sxs-lookup"><span data-stu-id="fe44a-125">To carry out this task, the **Test-CsDataConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fe44a-126">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="fe44a-126">Determining success or failure</span></span>

<span data-ttu-id="fe44a-127">データ会議が正しく構成されている場合は、次のような出力が得られ、Result プロパティは Success とマークされ **ます。**</span><span class="sxs-lookup"><span data-stu-id="fe44a-127">If data conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="fe44a-128">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fe44a-128">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fe44a-129">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="fe44a-129">Result : Success</span></span>

<span data-ttu-id="fe44a-130">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="fe44a-130">Latency : 00:00:00</span></span>

<span data-ttu-id="fe44a-131">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="fe44a-131">Error Message :</span></span>

<span data-ttu-id="fe44a-132">分析</span><span class="sxs-lookup"><span data-stu-id="fe44a-132">Diagnosis :</span></span>

<span data-ttu-id="fe44a-133">指定したユーザーがデータ共有を使用できない場合は、結果 **がエラーとして**表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="fe44a-133">If the specified users can't use data sharing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="fe44a-134">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fe44a-134">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fe44a-135">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="fe44a-135">Result : Failure</span></span>

<span data-ttu-id="fe44a-136">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="fe44a-136">Latency : 00:00:00</span></span>

<span data-ttu-id="fe44a-137">エラーメッセージ: 10060。接続しているパーティが原因で接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="fe44a-137">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="fe44a-138">一定期間後に正しく応答しなかったか、または</span><span class="sxs-lookup"><span data-stu-id="fe44a-138">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="fe44a-139">接続されたホストの接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="fe44a-139">established connection failed because connected host has</span></span>

<span data-ttu-id="fe44a-140">2001年に応答できませんでした \[ : 4898: e8: f39e: 5c9a: ad83: 81b3: 9944 \] : 5061</span><span class="sxs-lookup"><span data-stu-id="fe44a-140">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="fe44a-141">内部例外: 接続の試行が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="fe44a-141">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="fe44a-142">接続されたパーティは、一定期間の後に正しく応答しませんでした</span><span class="sxs-lookup"><span data-stu-id="fe44a-142">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="fe44a-143">接続されているホストが原因で、接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="fe44a-143">time, or established connection failed because connected host</span></span>

<span data-ttu-id="fe44a-144">応答に失敗した</span><span class="sxs-lookup"><span data-stu-id="fe44a-144">has failed to respond</span></span>

<span data-ttu-id="fe44a-145">\[2001年: 4898: e8: f39e: 5c9a: ad83: 81b3: 9944 \] : 5061</span><span class="sxs-lookup"><span data-stu-id="fe44a-145">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="fe44a-146">分析</span><span class="sxs-lookup"><span data-stu-id="fe44a-146">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fe44a-147">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="fe44a-147">Reasons why the test might have failed</span></span>

<span data-ttu-id="fe44a-148">**Test-csdataconference**が失敗する可能性のある一般的な原因を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fe44a-148">Here are some common reasons why **Test-CsDataConference** might fail:</span></span>

  - <span data-ttu-id="fe44a-149">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="fe44a-149">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="fe44a-150">省略可能なパラメーターが使用されている場合、オプションのパラメーターが正しく構成されている必要があります。テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="fe44a-150">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="fe44a-151">オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="fe44a-151">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="fe44a-152">データ会議を開催できるかどうかは、会議を開催したユーザー ( **test-csdataconference** コマンドレットの場合は "sender") に割り当てられている会議ポリシーによって決まります。</span><span class="sxs-lookup"><span data-stu-id="fe44a-152">The ability to conduct a data conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsDataConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="fe44a-153">開催者が会議に共同作業のアクティビティを含めることが許可されていない場合 (たとえば、その会議ポリシーで EnableDataCollaboration プロパティが False に設定されている場合)、 **test-csdataconference** コマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="fe44a-153">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsDataConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="fe44a-154">エッジサーバーの構成が正しくないか、まだ展開されていない場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="fe44a-154">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

