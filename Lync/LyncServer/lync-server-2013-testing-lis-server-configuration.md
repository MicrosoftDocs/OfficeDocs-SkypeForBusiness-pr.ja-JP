---
title: 'Lync Server 2013: LIS サーバーの構成のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8893964ce1982c67dc97ed93bca9ba19ec2f24e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536020"
---
# <a name="testing-lis-server-configuration-in-lync-server-2013"></a><span data-ttu-id="b3945-102">Lync Server 2013 での LIS サーバーの構成のテスト</span><span class="sxs-lookup"><span data-stu-id="b3945-102">Testing LIS server configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3945-103">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="b3945-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3945-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="b3945-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b3945-105">毎日</span><span class="sxs-lookup"><span data-stu-id="b3945-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3945-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="b3945-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b3945-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3945-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3945-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b3945-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b3945-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3945-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b3945-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsLisConfiguration コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3945-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLisConfiguration cmdlet.</span></span> <span data-ttu-id="b3945-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b3945-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b3945-112">説明</span><span class="sxs-lookup"><span data-stu-id="b3945-112">Description</span></span>

<span data-ttu-id="b3945-113">Test-CsLisConfiguration コマンドレットでは、LIS web サービスに接続できるかどうかを検証します。</span><span class="sxs-lookup"><span data-stu-id="b3945-113">The Test-CsLisConfiguration cmdlet verifies your ability to contact the LIS web service.</span></span> <span data-ttu-id="b3945-114">Web サービスに接続できる場合は、特定の場所が見つからないかどうかに関係なく、テストは成功したと見なされます。</span><span class="sxs-lookup"><span data-stu-id="b3945-114">If the web service can be contacted, then the test will be considered a success, regardless of whether any specific locations can be found.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b3945-115">テストの実行</span><span class="sxs-lookup"><span data-stu-id="b3945-115">Running the test</span></span>

<span data-ttu-id="b3945-116">Test-CsLisConfguration コマンドレットを実行するには、事前に構成されたテストアカウントを使用するか (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照)、Lync Server が有効になっているすべてのユーザーのアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="b3945-116">The Test-CsLisConfguration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="b3945-117">テストアカウントを使用してこのチェックを実行するには、テストする Lync Server プールの FQDN を指定するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="b3945-117">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="b3945-118">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b3945-118">For example:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="b3945-119">実際のユーザーアカウントを使用してこのチェックを実行するには、まず、アカウント名とパスワードを含む Windows PowerShell credentials オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3945-119">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="b3945-120">その資格情報オブジェクトと、Export-cslisconfiguration を呼び出すときにアカウントに割り当てられた SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3945-120">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLisConfiguration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="b3945-121">詳細については、 [export-cslisconfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3945-121">For more information, see the Help documentation for the [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b3945-122">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="b3945-122">Determining success or failure</span></span>

<span data-ttu-id="b3945-123">LIS が正しく構成されている場合は、次のような出力が得られ、Result プロパティは Success としてマークされ **ます。**</span><span class="sxs-lookup"><span data-stu-id="b3945-123">If the LIS is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="b3945-124">TargetUri https://atl-cs-001.litwareinc.com:443/locationinformation/</span><span class="sxs-lookup"><span data-stu-id="b3945-124">TargetUri : https://atl-cs-001.litwareinc.com:443/locationinformation/</span></span>

<span data-ttu-id="b3945-125">liservice svc</span><span class="sxs-lookup"><span data-stu-id="b3945-125">liservice.svc</span></span>

<span data-ttu-id="b3945-126">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b3945-126">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b3945-127">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="b3945-127">Result : Success</span></span>

<span data-ttu-id="b3945-128">待機時間:00:00: 06.1616913</span><span class="sxs-lookup"><span data-stu-id="b3945-128">Latency : 00:00:06.1616913</span></span>

<span data-ttu-id="b3945-129">エラー</span><span class="sxs-lookup"><span data-stu-id="b3945-129">Error :</span></span>

<span data-ttu-id="b3945-130">分析</span><span class="sxs-lookup"><span data-stu-id="b3945-130">Diagnosis :</span></span>

<span data-ttu-id="b3945-131">指定したユーザーがログオンまたはログオフできない場合は、結果がエラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="b3945-131">If the specified user can't log on or log off, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="b3945-132">TargetUri</span><span class="sxs-lookup"><span data-stu-id="b3945-132">TargetUri :</span></span>

<span data-ttu-id="b3945-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b3945-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b3945-134">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="b3945-134">Result : Failure</span></span>

<span data-ttu-id="b3945-135">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="b3945-135">Latency : 00:00:00</span></span>

<span data-ttu-id="b3945-136">エラー: 11004、要求された名前は有効ですが、要求されたデータがありません</span><span class="sxs-lookup"><span data-stu-id="b3945-136">Error : 11004, The requested name is valid but no data of the requested</span></span>

<span data-ttu-id="b3945-137">種類が見つかりました</span><span class="sxs-lookup"><span data-stu-id="b3945-137">type was found</span></span>

<span data-ttu-id="b3945-138">分析</span><span class="sxs-lookup"><span data-stu-id="b3945-138">Diagnosis :</span></span>

<span data-ttu-id="b3945-139">Test-CsLisConfiguration: トポロジ内に一致するクラスターが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="b3945-139">Test-CsLisConfiguration : No matching cluster found in topology.</span></span>

<span data-ttu-id="b3945-140">たとえば、前の出力には「トポロジ内に一致するクラスターが見つかりません」というメモが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b3945-140">For example, the previous output includes the note “No matching cluster found in topology.”</span></span> <span data-ttu-id="b3945-141">これは通常、エッジサーバーに問題があることを示しています: LIS は、サービスプロバイダーに接続し、アドレスを検証します。</span><span class="sxs-lookup"><span data-stu-id="b3945-141">That typically indicates a problem with the Edge Server: the LIS using the Edge Server to connect to the service provider and validate addresses.</span></span>

<span data-ttu-id="b3945-142">Test-CsLisConfiguration が失敗した場合は、次のように詳細パラメーターを含めて、テストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b3945-142">If Test-CsLisConfiguration fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="b3945-143">Verbose パラメーターが含まれている場合、Test-CsLisConfiguration は、指定されたユーザーが Lync Server にログオンできるかどうかを確認したときに実行された各アクションのステップバイステップのアカウントを返します。</span><span class="sxs-lookup"><span data-stu-id="b3945-143">When the Verbose parameter is included, Test-CsLisConfiguration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="b3945-144">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b3945-144">For example:</span></span>

<span data-ttu-id="b3945-145">場所情報サービスを呼び出しています。</span><span class="sxs-lookup"><span data-stu-id="b3945-145">Calling Location Information Service.</span></span>

<span data-ttu-id="b3945-146">サービスパス = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="b3945-146">Service Path = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span></span>

<span data-ttu-id="b3945-147">Subnet =</span><span class="sxs-lookup"><span data-stu-id="b3945-147">Subnet =</span></span>

<span data-ttu-id="b3945-148">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="b3945-148">BssId = 5</span></span>

<span data-ttu-id="b3945-149">Ch/Sid =</span><span class="sxs-lookup"><span data-stu-id="b3945-149">ChassisId =</span></span>

<span data-ttu-id="b3945-150">PortId =</span><span class="sxs-lookup"><span data-stu-id="b3945-150">PortId =</span></span>

<span data-ttu-id="b3945-151">PortIdSubType = 未定義の種類</span><span class="sxs-lookup"><span data-stu-id="b3945-151">PortIdSubType = Undefined Type</span></span>

<span data-ttu-id="b3945-152">Mac</span><span class="sxs-lookup"><span data-stu-id="b3945-152">Mac</span></span>

<span data-ttu-id="b3945-153">例外 ' 場所情報 Web サービス要求が応答コード Item400 で失敗しました。 '</span><span class="sxs-lookup"><span data-stu-id="b3945-153">An exception 'Location Information Web Service request has failed with a response code Item400.'</span></span> <span data-ttu-id="b3945-154">ワークフローの STLisConfigurationWorkflow の実行中に発生しました。この操作は、ワークフローの実行中に発生します。</span><span class="sxs-lookup"><span data-stu-id="b3945-154">occurred during Workflow Microsoft.Rtc.SyntheticTrsnactions.Workflows.STLisConfigurationWorkflow execution.</span></span>

<span data-ttu-id="b3945-155">以前の出力を詳しく調べると、場所情報サービスを呼び出した後にコマンドレットが失敗したことがわかります。</span><span class="sxs-lookup"><span data-stu-id="b3945-155">If you examine the previous output closely, you’ll see that the cmdlet failed after it tried to call the Location Information Service.</span></span> <span data-ttu-id="b3945-156">その呼び出しで使用されたパラメーターの1つは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b3945-156">One of the parameters that were used in that call was this:</span></span>

<span data-ttu-id="b3945-157">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="b3945-157">BssId = 5</span></span>

<span data-ttu-id="b3945-158">これは、基本サービスセット識別子 (BssID) の有効な値ではありません。</span><span class="sxs-lookup"><span data-stu-id="b3945-158">That’s not a valid value for the Basic Service Set Identifier (BssID).</span></span> <span data-ttu-id="b3945-159">代わりに、BssID は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b3945-159">Instead, a BssID should resemble this:</span></span>

<span data-ttu-id="b3945-160">12-34-56-78-90-ab</span><span class="sxs-lookup"><span data-stu-id="b3945-160">12-34-56-78-90-ab</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b3945-161">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="b3945-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="b3945-162">Test-CsLisConfiguration が失敗する可能性のある一般的な理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b3945-162">Here are some common reasons why Test-CsLisConfiguration might fail:</span></span>

  - <span data-ttu-id="b3945-163">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="b3945-163">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="b3945-164">前の例で示されているように、オプションのパラメーターが正しく構成されている必要があります。または、テストが失敗します。</span><span class="sxs-lookup"><span data-stu-id="b3945-164">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="b3945-165">オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b3945-165">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

