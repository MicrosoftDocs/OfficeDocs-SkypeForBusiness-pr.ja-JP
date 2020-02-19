---
title: 'Lync Server 2013: Web スケジューラのテスト'
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
ms.openlocfilehash: f6cd00192a7e2a9695a078768a6cf6ad9fac5873
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-web-scheduler-in-lync-server-2013"></a><span data-ttu-id="72103-102">Lync Server 2013 での Web スケジューラのテスト</span><span class="sxs-lookup"><span data-stu-id="72103-102">Testing the Web scheduler in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72103-103">_**トピックの最終更新日:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="72103-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72103-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="72103-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="72103-105">毎日</span><span class="sxs-lookup"><span data-stu-id="72103-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72103-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="72103-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="72103-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="72103-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72103-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="72103-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="72103-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="72103-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="72103-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、 <strong>Test-CsWebScheduler</strong>コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="72103-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWebScheduler</strong> cmdlet.</span></span> <span data-ttu-id="72103-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="72103-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="72103-112">説明</span><span class="sxs-lookup"><span data-stu-id="72103-112">Description</span></span>

<span data-ttu-id="72103-113">**Test-CsWebScheduler**コマンドレットを使用すると、特定のユーザーが Web スケジューラを使用して会議をスケジュールできるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="72103-113">The **Test-CsWebScheduler** cmdlet enables you to determine whether a specific user can schedule a meeting using the Web Scheduler.</span></span> <span data-ttu-id="72103-114">Web スケジューラは、Outlook を実行していないユーザーがオンライン会議をスケジュール設定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="72103-114">The Web Scheduler enables users who are not running Outlook to schedule online meetings.</span></span> <span data-ttu-id="72103-115">その他の機能として、この新しい機能 (Microsoft Lync Server 2010 リソースキットに付属していた Web スケジューラツールの機能を組み込む) により、ユーザーは次のことができます。</span><span class="sxs-lookup"><span data-stu-id="72103-115">Among other things, this new feature (which incorporates the functionality found in the Web Scheduler tool that was included with the Microsoft Lync Server 2010 resource kit) enables users to:</span></span>

  - <span data-ttu-id="72103-116">新しいオンライン会議をスケジュール設定します。</span><span class="sxs-lookup"><span data-stu-id="72103-116">Schedule a new online meeting.</span></span>

  - <span data-ttu-id="72103-117">ユーザーがスケジュール設定したすべての会議の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="72103-117">List all meetings that he or she has scheduled.</span></span>

  - <span data-ttu-id="72103-118">既存の会議を表示/変更します。</span><span class="sxs-lookup"><span data-stu-id="72103-118">View/modify an existing meeting.</span></span>

  - <span data-ttu-id="72103-119">既存の会議を削除します。</span><span class="sxs-lookup"><span data-stu-id="72103-119">Delete an existing meeting.</span></span>

  - <span data-ttu-id="72103-120">事前設定された SMTP メール サーバーを使用して会議の参加者に電子メール招待を送信します。</span><span class="sxs-lookup"><span data-stu-id="72103-120">Send an email invitation to meeting participants by using a preconfigured SMTP mail server.</span></span>

  - <span data-ttu-id="72103-121">既存の会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="72103-121">Join an existing conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="72103-122">テストの実行</span><span class="sxs-lookup"><span data-stu-id="72103-122">Running the test</span></span>

<span data-ttu-id="72103-123">次の例では、プール atl-cs-001.litwareinc.com の Web スケジューラを検証します。</span><span class="sxs-lookup"><span data-stu-id="72103-123">The following example verifies the Web Scheduler for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="72103-124">このコマンドは、プール atl-cs-001.litwareinc.com に対してテストユーザーが定義されている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="72103-124">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="72103-125">その場合は、コマンドによって、最初のテストユーザーが Web スケジューラを使用してオンライン会議をスケジュールできるかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="72103-125">If they have, then the command will determine whether the first test user can schedule an online meeting using the Web Scheduler.</span></span>

<span data-ttu-id="72103-126">テストユーザーが定義されていない場合は、どのユーザーがどのユーザーとしてログオンするかがわからないため、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="72103-126">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="72103-127">プールに対してテストユーザーが定義されていない場合は、UserSipAddress パラメーターと、コマンドがログオンを試行するときに使用するユーザーの資格情報を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="72103-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user the command should use when trying to log on.</span></span>

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="72103-128">次の例に示すコマンドは、特定のユーザー (litwareinc\\kenmeyer) が Web スケジューラを使用してオンライン会議をスケジュールする機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="72103-128">The commands shown in the next example test the ability of a specific user (litwareinc\\kenmeyer) to schedule an online meeting using the Web scheduler.</span></span> <span data-ttu-id="72103-129">これを行うには、例の最初のコマンドは、**資格情報**コマンドレットを使用して、ユーザー Ken Meyer の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="72103-129">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Ken Meyer.</span></span> <span data-ttu-id="72103-130">(ログオン名 litwareinc\\kenmeyer がパラメーターとして含まれているため、Windows PowerShell の [資格情報の要求] ダイアログボックスでは、管理者のみが Ken Meyer アカウントのパスワードを入力する必要があります。)その後、結果として得られる資格情報オブジェクトは $cred 1 という名前の変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="72103-130">(Because the logon name litwareinc\\kenmeyer is included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Meyer account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="72103-131">2番目のコマンドは、このユーザーがプール atl-cs-001.litwareinc.com にログオンし、オンライン会議をスケジュールすることができるかどうかをチェックします。</span><span class="sxs-lookup"><span data-stu-id="72103-131">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and schedule an online meeting.</span></span> <span data-ttu-id="72103-132">このタスクを実行するには、次の3つのパラメーターと共に、 **Test-CsWebScheduler**コマンドレットを呼び出します。 Targetfqdn (レジストラープールの FQDN)。UserCredential (Pilar Ackerman のユーザー資格情報を含む Windows PowerShell オブジェクト)。UserSipAddress (指定されたユーザー資格情報に対応する SIP アドレス)。</span><span class="sxs-lookup"><span data-stu-id="72103-132">To run this task, the **Test-CsWebScheduler** cmdlet is called, together with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="72103-133">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="72103-133">Determining success or failure</span></span>

<span data-ttu-id="72103-134">Web スケジューラが正しく構成されている場合は、次のような出力が得られ、Result プロパティは**Success**とマークされます。</span><span class="sxs-lookup"><span data-stu-id="72103-134">If the web scheduler is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="72103-135">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="72103-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="72103-136">ターゲット Uri: https://atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="72103-136">Target Uri : https:// atl-cs-001.litwareinc.com.</span></span>

<span data-ttu-id="72103-137">litwareinc.com:443/Scheduler</span><span class="sxs-lookup"><span data-stu-id="72103-137">litwareinc.com:443/Scheduler</span></span>

<span data-ttu-id="72103-138">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="72103-138">Result : Success</span></span>

<span data-ttu-id="72103-139">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="72103-139">Latency : 00:00:00</span></span>

<span data-ttu-id="72103-140">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="72103-140">Error Message :</span></span>

<span data-ttu-id="72103-141">分析</span><span class="sxs-lookup"><span data-stu-id="72103-141">Diagnosis :</span></span>

<span data-ttu-id="72103-142">Web スケジューラが正しく構成されていない場合は、結果が**エラーとして**表示され、追加情報が Error および診断プロパティに記録されます。</span><span class="sxs-lookup"><span data-stu-id="72103-142">If the web scheduler is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="72103-143">警告: 指定された完全修飾のレジストラーポート番号を読み取ることができませんでした</span><span class="sxs-lookup"><span data-stu-id="72103-143">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="72103-144">ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="72103-144">domain name (FQDN).</span></span> <span data-ttu-id="72103-145">既定のレジストラーポート番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="72103-145">Using default Registrar port number.</span></span> <span data-ttu-id="72103-146">例外</span><span class="sxs-lookup"><span data-stu-id="72103-146">Exception:</span></span>

<span data-ttu-id="72103-147">System.invalidoperationexception: トポロジ内に一致するクラスターが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="72103-147">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="72103-148">下部</span><span class="sxs-lookup"><span data-stu-id="72103-148">at</span></span>

<span data-ttu-id="72103-149">TryRetri を SipSyntheticTransaction していることを示します。</span><span class="sxs-lookup"><span data-stu-id="72103-149">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="72103-150">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="72103-150">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="72103-151">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="72103-151">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="72103-152">ターゲット Uri:</span><span class="sxs-lookup"><span data-stu-id="72103-152">Target Uri :</span></span>

<span data-ttu-id="72103-153">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="72103-153">Result : Failure</span></span>

<span data-ttu-id="72103-154">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="72103-154">Latency : 00:00:00</span></span>

<span data-ttu-id="72103-155">エラーメッセージ: トポロジ内に一致するクラスターが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="72103-155">Error Message : No matching cluster found in topology.</span></span>

<span data-ttu-id="72103-156">分析</span><span class="sxs-lookup"><span data-stu-id="72103-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="72103-157">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="72103-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="72103-158">次に **、Test-CsWebScheduler**が失敗する可能性のある一般的な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="72103-158">Here are some common reasons why **Test-CsWebScheduler** might fail:</span></span>

  - <span data-ttu-id="72103-159">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="72103-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="72103-160">省略可能なパラメーターが使用されている場合、オプションのパラメーターが正しく構成されている必要があります。テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="72103-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="72103-161">オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="72103-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="72103-162">Web スケジューラが正しく構成されていないか、まだ展開されていない場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="72103-162">This command will fail if the Web Scheduler is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="72103-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="72103-163">See Also</span></span>


[<span data-ttu-id="72103-164">設定-CsWebServer</span><span class="sxs-lookup"><span data-stu-id="72103-164">Set-CsWebServer</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

