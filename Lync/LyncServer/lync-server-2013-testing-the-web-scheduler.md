---
title: 'Lync Server 2013: Web scheduler のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65d7dc70bad90dc4e4c94e2db273f44ed20c50ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-web-scheduler-in-lync-server-2013"></a><span data-ttu-id="9ea66-102">Lync Server 2013 で Web scheduler をテストする</span><span class="sxs-lookup"><span data-stu-id="9ea66-102">Testing the Web scheduler in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ea66-103">_**最終更新日:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="9ea66-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ea66-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="9ea66-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9ea66-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="9ea66-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ea66-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="9ea66-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9ea66-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ea66-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ea66-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="9ea66-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9ea66-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ea66-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9ea66-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、 <strong>CsWebScheduler</strong>コマンドレットを実行するアクセス許可が与えられた RBAC の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ea66-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWebScheduler</strong> cmdlet.</span></span> <span data-ttu-id="9ea66-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9ea66-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9ea66-112">説明</span><span class="sxs-lookup"><span data-stu-id="9ea66-112">Description</span></span>

<span data-ttu-id="9ea66-113">**テスト用の webscheduler**コマンドレットを使用すると、特定のユーザーが Web Scheduler を使って会議をスケジュールできるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="9ea66-113">The **Test-CsWebScheduler** cmdlet enables you to determine whether a specific user can schedule a meeting using the Web Scheduler.</span></span> <span data-ttu-id="9ea66-114">Web Scheduler は、Outlook を実行していないユーザーがオンライン会議をスケジュールすることを可能にします。</span><span class="sxs-lookup"><span data-stu-id="9ea66-114">The Web Scheduler enables users who are not running Outlook to schedule online meetings.</span></span> <span data-ttu-id="9ea66-115">この新機能 (Microsoft Lync Server 2010 リソースキットに含まれていた Web Scheduler ツールに含まれていた機能が組み込まれています) では、ユーザーは次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9ea66-115">Among other things, this new feature (which incorporates the functionality found in the Web Scheduler tool that was included with the Microsoft Lync Server 2010 resource kit) enables users to:</span></span>

  - <span data-ttu-id="9ea66-116">新しいオンライン会議をスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="9ea66-116">Schedule a new online meeting.</span></span>

  - <span data-ttu-id="9ea66-117">自分がスケジュールしたすべての会議を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="9ea66-117">List all meetings that he or she has scheduled.</span></span>

  - <span data-ttu-id="9ea66-118">既存の会議を表示または変更する。</span><span class="sxs-lookup"><span data-stu-id="9ea66-118">View/modify an existing meeting.</span></span>

  - <span data-ttu-id="9ea66-119">既存の会議を削除します。</span><span class="sxs-lookup"><span data-stu-id="9ea66-119">Delete an existing meeting.</span></span>

  - <span data-ttu-id="9ea66-120">事前に構成された SMTP メールサーバーを使用して、会議の出席者にメール招待状を送信します。</span><span class="sxs-lookup"><span data-stu-id="9ea66-120">Send an email invitation to meeting participants by using a preconfigured SMTP mail server.</span></span>

  - <span data-ttu-id="9ea66-121">既存の会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="9ea66-121">Join an existing conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9ea66-122">テストの実行</span><span class="sxs-lookup"><span data-stu-id="9ea66-122">Running the test</span></span>

<span data-ttu-id="9ea66-123">次の例では、プール atl-cs-001.litwareinc.com の Web Scheduler を確認します。</span><span class="sxs-lookup"><span data-stu-id="9ea66-123">The following example verifies the Web Scheduler for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="9ea66-124">このコマンドは、プール atl-cs-001.litwareinc.com に対してテストユーザーが定義されている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="9ea66-124">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="9ea66-125">その場合、コマンドは、最初のテストユーザーが Web Scheduler を使ってオンライン会議をスケジュールできるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="9ea66-125">If they have, then the command will determine whether the first test user can schedule an online meeting using the Web Scheduler.</span></span>

<span data-ttu-id="9ea66-126">テストユーザーが定義されていない場合は、どのユーザーとしてログオンするかがわからないため、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="9ea66-126">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="9ea66-127">プールのテストユーザーを定義していない場合は、UserSipAddress パラメーターと、ログオンしようとしたときにコマンドによって使用されるユーザーの資格情報を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ea66-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user the command should use when trying to log on.</span></span>

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="9ea66-128">次の例に示すコマンドは、Web scheduler を使ってオンライン会議を\\スケジュールするために、特定のユーザー (litwareinc kenmeyer) の機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="9ea66-128">The commands shown in the next example test the ability of a specific user (litwareinc\\kenmeyer) to schedule an online meeting using the Web scheduler.</span></span> <span data-ttu-id="9ea66-129">これを行うには、この例の最初のコマンドでは、 **Credential**コマンドレットを使用して、ユーザー Ken Meyer の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイスの資格情報オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="9ea66-129">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Ken Meyer.</span></span> <span data-ttu-id="9ea66-130">(Logon name litwareinc\\kenmeyer はパラメーターとして含まれているため、Windows PowerShell 資格情報の要求ダイアログボックスでは、管理者が Ken Meyer account のパスワードを入力するだけであることになります。)結果として得られた資格情報オブジェクトは、$cred 1 という名前の変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="9ea66-130">(Because the logon name litwareinc\\kenmeyer is included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Meyer account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="9ea66-131">2番目のコマンドは、このユーザーがプール atl-cs-001.litwareinc.com にログオンしてオンライン会議をスケジュールできるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="9ea66-131">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and schedule an online meeting.</span></span> <span data-ttu-id="9ea66-132">このタスクを実行するために、**テスト用の Webscheduler**コマンドレットが呼び出され、次の3つのパラメーター (レジストラープールの FQDN) が使用されます。UserCredential (Pilar Ackerman のユーザー資格情報を格納する Windows PowerShell オブジェクト)UserSipAddress (提供されているユーザー資格情報に対応する SIP アドレス) を選びます。</span><span class="sxs-lookup"><span data-stu-id="9ea66-132">To run this task, the **Test-CsWebScheduler** cmdlet is called, together with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9ea66-133">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="9ea66-133">Determining success or failure</span></span>

<span data-ttu-id="9ea66-134">Web scheduler が適切に構成されている場合は、次のような結果が返され、Result プロパティは**Success**とマークされます。</span><span class="sxs-lookup"><span data-stu-id="9ea66-134">If the web scheduler is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="9ea66-135">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9ea66-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9ea66-136">ターゲット Uri: https://atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="9ea66-136">Target Uri : https:// atl-cs-001.litwareinc.com.</span></span>

<span data-ttu-id="9ea66-137">litwareinc.com:443/Scheduler</span><span class="sxs-lookup"><span data-stu-id="9ea66-137">litwareinc.com:443/Scheduler</span></span>

<span data-ttu-id="9ea66-138">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="9ea66-138">Result : Success</span></span>

<span data-ttu-id="9ea66-139">待ち時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9ea66-139">Latency : 00:00:00</span></span>

<span data-ttu-id="9ea66-140">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="9ea66-140">Error Message :</span></span>

<span data-ttu-id="9ea66-141">診断</span><span class="sxs-lookup"><span data-stu-id="9ea66-141">Diagnosis :</span></span>

<span data-ttu-id="9ea66-142">Web scheduler が正しく構成されていない場合は、結果が**失敗**として表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="9ea66-142">If the web scheduler is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="9ea66-143">警告: 指定した完全修飾のレジストラーポート番号の読み取りに失敗しました</span><span class="sxs-lookup"><span data-stu-id="9ea66-143">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="9ea66-144">ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="9ea66-144">domain name (FQDN).</span></span> <span data-ttu-id="9ea66-145">既定のレジストラーポート番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="9ea66-145">Using default Registrar port number.</span></span> <span data-ttu-id="9ea66-146">エラー</span><span class="sxs-lookup"><span data-stu-id="9ea66-146">Exception:</span></span>

<span data-ttu-id="9ea66-147">InvalidOperationException: トポロジで一致するクラスターが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="9ea66-147">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="9ea66-148">自宅</span><span class="sxs-lookup"><span data-stu-id="9ea66-148">at</span></span>

<span data-ttu-id="9ea66-149">SipSyntheticTransaction-TryRetri の同期を行います。</span><span class="sxs-lookup"><span data-stu-id="9ea66-149">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="9ea66-150">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="9ea66-150">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="9ea66-151">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9ea66-151">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9ea66-152">ターゲット Uri:</span><span class="sxs-lookup"><span data-stu-id="9ea66-152">Target Uri :</span></span>

<span data-ttu-id="9ea66-153">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="9ea66-153">Result : Failure</span></span>

<span data-ttu-id="9ea66-154">待ち時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9ea66-154">Latency : 00:00:00</span></span>

<span data-ttu-id="9ea66-155">エラーメッセージ: 一致するクラスターがトポロジに見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="9ea66-155">Error Message : No matching cluster found in topology.</span></span>

<span data-ttu-id="9ea66-156">診断</span><span class="sxs-lookup"><span data-stu-id="9ea66-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9ea66-157">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="9ea66-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="9ea66-158">次に **、テスト用の Webscheduler スケジューラ**が機能しない場合の一般的な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="9ea66-158">Here are some common reasons why **Test-CsWebScheduler** might fail:</span></span>

  - <span data-ttu-id="9ea66-159">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="9ea66-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="9ea66-160">使用する場合は、オプションのパラメーターが正しく構成されている必要があります。または、テストが失敗します。</span><span class="sxs-lookup"><span data-stu-id="9ea66-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="9ea66-161">省略可能なパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="9ea66-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="9ea66-162">Web Scheduler が正しく構成されていない場合、またはまだ展開されていない場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="9ea66-162">This command will fail if the Web Scheduler is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9ea66-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ea66-163">See Also</span></span>


[<span data-ttu-id="9ea66-164">Set-CsWebServer</span><span class="sxs-lookup"><span data-stu-id="9ea66-164">Set-CsWebServer</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

