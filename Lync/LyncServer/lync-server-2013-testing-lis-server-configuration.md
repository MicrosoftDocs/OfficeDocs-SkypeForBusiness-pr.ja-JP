---
title: 'Lync Server 2013: LIS サーバー構成のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e5baed37e4c72da8b8348dab9702b5d22fbbc5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lis-server-configuration-in-lync-server-2013"></a><span data-ttu-id="dab76-102">Lync Server 2013 での LIS サーバーの構成のテスト</span><span class="sxs-lookup"><span data-stu-id="dab76-102">Testing LIS server configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dab76-103">_**最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="dab76-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dab76-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="dab76-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="dab76-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="dab76-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dab76-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="dab76-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="dab76-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dab76-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dab76-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="dab76-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="dab76-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="dab76-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="dab76-110">Windows PowerShell のリモートインスタンスを使って実行する場合は、CsLisConfiguration コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dab76-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLisConfiguration cmdlet.</span></span> <span data-ttu-id="dab76-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dab76-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="dab76-112">説明</span><span class="sxs-lookup"><span data-stu-id="dab76-112">Description</span></span>

<span data-ttu-id="dab76-113">CsLisConfiguration コマンドレットによって、LIS web サービスに連絡する機能が確認されます。</span><span class="sxs-lookup"><span data-stu-id="dab76-113">The Test-CsLisConfiguration cmdlet verifies your ability to contact the LIS web service.</span></span> <span data-ttu-id="dab76-114">Web サービスに連絡できる場合は、特定の場所が見つかるかどうかに関係なく、テストが成功したと見なされます。</span><span class="sxs-lookup"><span data-stu-id="dab76-114">If the web service can be contacted, then the test will be considered a success, regardless of whether any specific locations can be found.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="dab76-115">テストの実行</span><span class="sxs-lookup"><span data-stu-id="dab76-115">Running the test</span></span>

<span data-ttu-id="dab76-116">CsLisConfguration コマンドレットを実行するには、事前に定義されたテストアカウント (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照) を使用するか、Lync Server を有効にしているユーザーのアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="dab76-116">The Test-CsLisConfguration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="dab76-117">テストアカウントを使用してこのチェックを実行するには、テスト対象の Lync Server プールの FQDN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dab76-117">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="dab76-118">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="dab76-118">For example:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="dab76-119">実際のユーザーアカウントを使用してこのチェックを実行するには、最初に、アカウント名とパスワードを含む Windows PowerShell 資格情報オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dab76-119">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="dab76-120">次に、CsLisConfiguration を呼び出したときに、アカウントに割り当てられている資格情報オブジェクトと SIP アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dab76-120">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLisConfiguration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="dab76-121">詳細については、「 [CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dab76-121">For more information, see the Help documentation for the [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="dab76-122">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="dab76-122">Determining success or failure</span></span>

<span data-ttu-id="dab76-123">LIS が適切に構成されている場合は、次のような結果が返され、Result プロパティは Success とマークされ**ます。**</span><span class="sxs-lookup"><span data-stu-id="dab76-123">If the LIS is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="dab76-124">TargetUri :https://atl-cs-001.litwareinc.com:443/locationinformation/</span><span class="sxs-lookup"><span data-stu-id="dab76-124">TargetUri : https://atl-cs-001.litwareinc.com:443/locationinformation/</span></span>

<span data-ttu-id="dab76-125">liservice .svc</span><span class="sxs-lookup"><span data-stu-id="dab76-125">liservice.svc</span></span>

<span data-ttu-id="dab76-126">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="dab76-126">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="dab76-127">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="dab76-127">Result : Success</span></span>

<span data-ttu-id="dab76-128">待ち時間:00:00: 06.1616913</span><span class="sxs-lookup"><span data-stu-id="dab76-128">Latency : 00:00:06.1616913</span></span>

<span data-ttu-id="dab76-129">誤差</span><span class="sxs-lookup"><span data-stu-id="dab76-129">Error :</span></span>

<span data-ttu-id="dab76-130">診断</span><span class="sxs-lookup"><span data-stu-id="dab76-130">Diagnosis :</span></span>

<span data-ttu-id="dab76-131">指定したユーザーがログオンまたはログオフできない場合は、結果がエラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="dab76-131">If the specified user can't log on or log off, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="dab76-132">TargetUri :</span><span class="sxs-lookup"><span data-stu-id="dab76-132">TargetUri :</span></span>

<span data-ttu-id="dab76-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="dab76-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="dab76-134">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="dab76-134">Result : Failure</span></span>

<span data-ttu-id="dab76-135">待ち時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="dab76-135">Latency : 00:00:00</span></span>

<span data-ttu-id="dab76-136">エラー: 11004、要求された名前は有効ですが、要求されたデータがありません</span><span class="sxs-lookup"><span data-stu-id="dab76-136">Error : 11004, The requested name is valid but no data of the requested</span></span>

<span data-ttu-id="dab76-137">種類が見つかりました</span><span class="sxs-lookup"><span data-stu-id="dab76-137">type was found</span></span>

<span data-ttu-id="dab76-138">診断</span><span class="sxs-lookup"><span data-stu-id="dab76-138">Diagnosis :</span></span>

<span data-ttu-id="dab76-139">CsLisConfiguration: トポロジで一致するクラスターが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="dab76-139">Test-CsLisConfiguration : No matching cluster found in topology.</span></span>

<span data-ttu-id="dab76-140">たとえば、前の出力には "一致するクラスターがトポロジで見つかりませんでした" というメモが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dab76-140">For example, the previous output includes the note “No matching cluster found in topology.”</span></span> <span data-ttu-id="dab76-141">これは通常、エッジサーバーに問題があることを示します。これは、サービスプロバイダに接続してアドレスを検証するためにエッジサーバーを使用している LIS。</span><span class="sxs-lookup"><span data-stu-id="dab76-141">That typically indicates a problem with the Edge Server: the LIS using the Edge Server to connect to the service provider and validate addresses.</span></span>

<span data-ttu-id="dab76-142">テスト-CsLisConfiguration が失敗した場合は、Verbose パラメーターも含めて、テストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dab76-142">If Test-CsLisConfiguration fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="dab76-143">Verbose パラメーターが含まれている場合、CsLisConfiguration は、指定されたユーザーが Lync Server にログオンする機能を確認したときに実行された各操作のステップバイステップのアカウントを返します。</span><span class="sxs-lookup"><span data-stu-id="dab76-143">When the Verbose parameter is included, Test-CsLisConfiguration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="dab76-144">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="dab76-144">For example:</span></span>

<span data-ttu-id="dab76-145">位置情報サービスを呼び出しています。</span><span class="sxs-lookup"><span data-stu-id="dab76-145">Calling Location Information Service.</span></span>

<span data-ttu-id="dab76-146">サービスパス =https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="dab76-146">Service Path = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span></span>

<span data-ttu-id="dab76-147">Subnet =</span><span class="sxs-lookup"><span data-stu-id="dab76-147">Subnet =</span></span>

<span data-ttu-id="dab76-148">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="dab76-148">BssId = 5</span></span>

<span data-ttu-id="dab76-149">Chいい Sid =</span><span class="sxs-lookup"><span data-stu-id="dab76-149">ChassisId =</span></span>

<span data-ttu-id="dab76-150">PortId =</span><span class="sxs-lookup"><span data-stu-id="dab76-150">PortId =</span></span>

<span data-ttu-id="dab76-151">PortIdSubType = 未定義の型</span><span class="sxs-lookup"><span data-stu-id="dab76-151">PortIdSubType = Undefined Type</span></span>

<span data-ttu-id="dab76-152">Mac</span><span class="sxs-lookup"><span data-stu-id="dab76-152">Mac</span></span>

<span data-ttu-id="dab76-153">"位置情報の Web サービス要求" の例外は、応答コード Item400 で失敗しました。 '</span><span class="sxs-lookup"><span data-stu-id="dab76-153">An exception 'Location Information Web Service request has failed with a response code Item400.'</span></span> <span data-ttu-id="dab76-154">STLisConfigurationWorkflow の実行中に発生したワークフローのことです。.</span><span class="sxs-lookup"><span data-stu-id="dab76-154">occurred during Workflow Microsoft.Rtc.SyntheticTrsnactions.Workflows.STLisConfigurationWorkflow execution.</span></span>

<span data-ttu-id="dab76-155">前の出力をよく確認すると、位置情報サービスを呼び出した後にコマンドレットが失敗したことがわかります。</span><span class="sxs-lookup"><span data-stu-id="dab76-155">If you examine the previous output closely, you’ll see that the cmdlet failed after it tried to call the Location Information Service.</span></span> <span data-ttu-id="dab76-156">この呼び出しで使用されたパラメーターの1つは、次のようになりました。</span><span class="sxs-lookup"><span data-stu-id="dab76-156">One of the parameters that were used in that call was this:</span></span>

<span data-ttu-id="dab76-157">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="dab76-157">BssId = 5</span></span>

<span data-ttu-id="dab76-158">これは、基本サービスセット識別子 (BssID) の有効な値ではありません。</span><span class="sxs-lookup"><span data-stu-id="dab76-158">That’s not a valid value for the Basic Service Set Identifier (BssID).</span></span> <span data-ttu-id="dab76-159">代わりに、BssID は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="dab76-159">Instead, a BssID should resemble this:</span></span>

<span data-ttu-id="dab76-160">12-34-56-78-90-ab</span><span class="sxs-lookup"><span data-stu-id="dab76-160">12-34-56-78-90-ab</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="dab76-161">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="dab76-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="dab76-162">次に、テスト-CsLisConfiguration が失敗する可能性がある一般的な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="dab76-162">Here are some common reasons why Test-CsLisConfiguration might fail:</span></span>

  - <span data-ttu-id="dab76-163">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="dab76-163">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="dab76-164">上の例で示したように、オプションのパラメーターは正しく構成されている必要があります。また、テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="dab76-164">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="dab76-165">省略可能なパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="dab76-165">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

