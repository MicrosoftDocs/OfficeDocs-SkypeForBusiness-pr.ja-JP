---
title: 'Lync Server 2013: サードパーティの電話会議のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51f728bfb5617185bdd9a1ef3b5f21b3e12ca61f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503934"
---
# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a><span data-ttu-id="71550-102">Lync Server 2013 でのサードパーティの電話会議のテスト</span><span class="sxs-lookup"><span data-stu-id="71550-102">Testing third-party audio conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71550-103">_**トピックの最終更新日:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="71550-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71550-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="71550-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="71550-105">毎日</span><span class="sxs-lookup"><span data-stu-id="71550-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71550-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="71550-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="71550-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="71550-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71550-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="71550-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="71550-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="71550-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="71550-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsAudioConferencingProvider コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="71550-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAudioConferencingProvider cmdlet.</span></span> <span data-ttu-id="71550-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="71550-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="71550-112">説明</span><span class="sxs-lookup"><span data-stu-id="71550-112">Description</span></span>

<span data-ttu-id="71550-p102">電話会議プロバイダーとは、電話会議サービスを組織に提供するサード パーティの企業です。電話会議プロバイダーの主な機能は、社外にいて企業ネットワークまたはインターネットに接続されていないユーザーが、電話会議または会議のオーディオ部分に参加できるようにすることです。電話会議プロバイダーは多くの場合、リアルタイム通訳、トランスクリプション、オペレーターによる各電話会議のリアルタイム サポートなど、高度なサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="71550-p102">An audio conferencing provider is a third-party company that provides organizations with conferencing services. Among other things, audio conferencing providers enable users located off site, and not connected to the corporate network or the Internet, to participate in the audio portion of a conference or meeting. Audio conferencing providers often provide high-end services such as live translation, transcription, and live per-conference operator assistance.</span></span>

<span data-ttu-id="71550-116">**Test-csaudioconferencingprovider**コマンドレットは、ユーザーが自分の電話会議プロバイダーに接続できることを確認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="71550-116">The **Test-CsAudioConferencingProvider** cmdlet is used to verify that a user is able to make a connection to his or her audio conferencing provider.</span></span> <span data-ttu-id="71550-117">このコマンドレットは、次の2つの方法のどちらかで実行できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="71550-117">Note that this cmdlet can be run in one of two ways.</span></span> <span data-ttu-id="71550-118">多くの管理者は、CsHealthMonitoringConfiguration コマンドレットを使用して、テスト ユーザーを各レジストラー プールに設定します。</span><span class="sxs-lookup"><span data-stu-id="71550-118">Many administrators will use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="71550-119">これらのテストユーザーは、代理トランザクションで使用するために事前に構成されたユーザーアカウントのペアを表します。</span><span class="sxs-lookup"><span data-stu-id="71550-119">These test users represent a pair of user accounts that have been preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="71550-120">(通常、これらはテストアカウントであり、実際のユーザーに属するアカウントではありません)。テストユーザーがプールに対して構成されている場合、管理者は、テストに関係するユーザーアカウント (および資格情報) を指定せずに、そのプールに対して **test-csaudioconferencingprovider** コマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="71550-120">(Typically these are test accounts and not accounts that belong to actual users.) If test users are configured for a pool, administrators can run the **Test-CsAudioConferencingProvider** cmdlet against that pool without having to specify the identity of (and supply the credentials for) the user account involved in the test.</span></span>

<span data-ttu-id="71550-121">または、管理者は実際のユーザーアカウントを使用して **test-csaudioconferencingprovider** コマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="71550-121">Alternatively, administrators can run the **Test-CsAudioConferencingProvider** cmdlet using an actual user account.</span></span> <span data-ttu-id="71550-122">実際のユーザー アカウントを使用してテストを実行する場合は、そのアカウントのログオン名とパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71550-122">If you decide to conduct the test using an actual user account you will need to supply the logon name and password for that account.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="71550-123">テストの実行</span><span class="sxs-lookup"><span data-stu-id="71550-123">Running the test</span></span>

<span data-ttu-id="71550-124">例1では、プール atl-cs-001.litwareinc.com に対して定義されたテストユーザーが自分の電話会議プロバイダーに接続できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="71550-124">Example 1 checks to see if a test user defined for the pool atl-cs-001.litwareinc.com is able to connect to his or her audio conferencing provider.</span></span> <span data-ttu-id="71550-125">このコマンドでは、プールに対して少なくとも1つのテストユーザーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71550-125">This command requires that at least one test user be defined for the pool.</span></span> <span data-ttu-id="71550-126">Atl-cs-001.litwareinc.com に対してテストユーザーが定義されていない場合、コマンドは失敗します。これは、 **test-csaudioconferencingprovider** コマンドレットはテストに使用するユーザーを認識しないためです。</span><span class="sxs-lookup"><span data-stu-id="71550-126">If no test users have been defined for atl-cs-001.litwareinc.com, then the command will fail; that's because the **Test-CsAudioConferencingProvider** cmdlet will not know which user to employ in the test.</span></span> <span data-ttu-id="71550-127">プールに対してテストユーザーが定義されていない場合は、電話会議プロバイダーとの接続を確認するときに、コマンドが使用する必要があるユーザーアカウントの UserSipAddress パラメーターと資格情報を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="71550-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user account that the command should employ when verifying the connection with an audio conferencing provider.</span></span>

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

<span data-ttu-id="71550-128">例2に示すコマンドは、特定のユーザー (litwareinc \\ kenmyer) が自分の電話会議プロバイダーに接続できるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="71550-128">The commands shown in Example 2 test the ability of a specific user (litwareinc\\kenmyer) to connect to his audio conferencing provider.</span></span> <span data-ttu-id="71550-129">これを行うには、例の最初のコマンドは Get-Credential コマンドレットを使用して、ユーザー Ken Myer の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="71550-129">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credentials object containing the name and password of the user Ken Myer.</span></span> <span data-ttu-id="71550-130">(ログオン名 litwareinc \\ kenmyer がパラメーターとして含まれているため、Windows PowerShell の [資格情報の要求] ダイアログボックスでは、管理者のみが Ken Myer アカウントのパスワードを入力する必要があります)。結果の資格情報オブジェクトは、$credential という名前の変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="71550-130">(Because the logon name litwareinc\\kenmyer has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Myer account.) The resulting credentials object is stored in a variable named $credential.</span></span>

<span data-ttu-id="71550-131">次に、2 番目のコマンドでは、このユーザーが電話会議プロバイダーに接続できるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="71550-131">The second command then checks to see if this user can connect to his audio conferencing provider.</span></span> <span data-ttu-id="71550-132">このタスクを実行するために、Test-CsAudioConferencingProvider コマンドレットと共に、TargetFqdn (レジストラープールの FQDN) という3つのパラメーターを呼び出します。UserCredential (Ken Myer のユーザー資格情報を含む Windows PowerShell オブジェクト)。UserSipAddress (指定されたユーザー資格情報に対応する SIP アドレス)。</span><span class="sxs-lookup"><span data-stu-id="71550-132">To carry out this task, the Test-CsAudioConferencingProvider cmdlet is called, along with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object containing Ken Myer's user credentials); and UserSipAddress (the SIP address corresponding to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="71550-133">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="71550-133">Determining success or failure</span></span>

<span data-ttu-id="71550-134">電話会議プロバイダーが正しく構成されている場合は、次のような出力が得られ、Result プロパティは Success としてマークされ **ます。**</span><span class="sxs-lookup"><span data-stu-id="71550-134">If the audio conferencing provider is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="71550-135">ターゲット Fqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="71550-135">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="71550-136">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="71550-136">Result : Success</span></span>

<span data-ttu-id="71550-137">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="71550-137">Latency : 00:00:00</span></span>

<span data-ttu-id="71550-138">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="71550-138">Error Message :</span></span>

<span data-ttu-id="71550-139">分析</span><span class="sxs-lookup"><span data-stu-id="71550-139">Diagnosis :</span></span>

<span data-ttu-id="71550-140">指定したユーザーがログオンまたはログオフできない場合は、結果 **がエラーと**して表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="71550-140">If the specified user can't log on or log off, the Result will be shown as a **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="71550-141">ターゲット Fqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="71550-141">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="71550-142">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="71550-142">Result : Failure</span></span>

<span data-ttu-id="71550-143">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="71550-143">Latency : 00:00:00</span></span>

<span data-ttu-id="71550-144">エラーメッセージ: 10060。接続しているパーティが原因で接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="71550-144">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="71550-145">一定期間後に正しく応答しなかったか、または</span><span class="sxs-lookup"><span data-stu-id="71550-145">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="71550-146">接続されたホストの接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="71550-146">established connection failed because connected host has</span></span>

<span data-ttu-id="71550-147">2001年に応答できませんでした \[ : 4898: e8: f39e: 5c9a: ad83: 81b3: 9944 \] : 5061</span><span class="sxs-lookup"><span data-stu-id="71550-147">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="71550-148">内部例外: 接続の試行が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="71550-148">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="71550-149">接続されたパーティは、一定期間の後に正しく応答しませんでした</span><span class="sxs-lookup"><span data-stu-id="71550-149">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="71550-150">接続されているホストが原因で、接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="71550-150">time, or established connection failed because connected host</span></span>

<span data-ttu-id="71550-151">応答に失敗した</span><span class="sxs-lookup"><span data-stu-id="71550-151">has failed to respond</span></span>

<span data-ttu-id="71550-152">\[2001年: 4898: e8: f39e: 5c9a: ad83: 81b3: 9944 \] : 5061</span><span class="sxs-lookup"><span data-stu-id="71550-152">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="71550-153">分析</span><span class="sxs-lookup"><span data-stu-id="71550-153">Diagnosis :</span></span>

<span data-ttu-id="71550-154">たとえば、前述の出力には、通常、エッジサーバーに問題があることを示す「接続されたパーティは正しく応答しませんでした」というメモが含まれています。</span><span class="sxs-lookup"><span data-stu-id="71550-154">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="71550-155">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="71550-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="71550-156">**Test-csaudioconferencingprovider**が失敗する可能性のある一般的な原因を次に示します。</span><span class="sxs-lookup"><span data-stu-id="71550-156">Here are some common reasons why **Test-CsAudioConferencingProvider** might fail:</span></span>

  - <span data-ttu-id="71550-157">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="71550-157">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="71550-158">前の例で示されているように、オプションのパラメーターが正しく構成されている必要があります。または、テストが失敗します。</span><span class="sxs-lookup"><span data-stu-id="71550-158">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="71550-159">オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="71550-159">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="71550-160">**Test-csaudioconferencingprovider**コマンドレットによって使用されているユーザーに電話会議プロバイダーが割り当てられていない場合は、テストが失敗することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="71550-160">Note that the test will fail if the user employed by the **Test-CsAudioConferencingProvider** cmdlet has not been assigned an audio conferencing provider.</span></span>

  - <span data-ttu-id="71550-161">エッジサーバーの構成が正しくないか、まだ展開されていない場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="71550-161">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

