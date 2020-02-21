---
title: 'Lync Server 2013: グループ拡張を使用するためのテスト能力'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 358d869f212ac3acef91e28ddb8d08322133970f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a><span data-ttu-id="5a924-102">Lync Server 2013 でグループ拡張を採用するためのテスト能力</span><span class="sxs-lookup"><span data-stu-id="5a924-102">Testing ability to employ group expansion in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a924-103">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="5a924-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a924-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="5a924-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5a924-105">毎日</span><span class="sxs-lookup"><span data-stu-id="5a924-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a924-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="5a924-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5a924-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a924-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a924-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="5a924-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5a924-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a924-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5a924-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テスト用の CsGroupExpansion コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a924-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupExpansion cmdlet.</span></span> <span data-ttu-id="5a924-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a924-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5a924-112">説明</span><span class="sxs-lookup"><span data-stu-id="5a924-112">Description</span></span>

<span data-ttu-id="5a924-113">Test-CsGroupExpansion コマンドレットを使用すると、グループ拡張が組織内で動作しているかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="5a924-113">The Test-CsGroupExpansion cmdlet lets you determine whether group expansion is working within your organization.</span></span> <span data-ttu-id="5a924-114">グループ拡張が有効になっている場合、ユーザーは配布グループを連絡先として構成します。</span><span class="sxs-lookup"><span data-stu-id="5a924-114">When group expansion is enabled, users configure distribution groups as a contact.</span></span> <span data-ttu-id="5a924-115">つまり、それらのユーザーは、そのグループの個々のメンバーではなく、グループにメッセージをアドレス指定することによって、すべてのグループメンバーに同じインスタントメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="5a924-115">That means that those users can then send the same instant message to all the group members by addressing the message to the group instead of to individual members of that group.</span></span> <span data-ttu-id="5a924-116">グループ拡張を使用すると、すべてのグループメンバーとその現在の状態をすばやく簡単に表示できます。</span><span class="sxs-lookup"><span data-stu-id="5a924-116">Group expansion enables you to quickly and easily view all the group members and their current status.</span></span>

<span data-ttu-id="5a924-117">Test-CsGroupExpansion コマンドレットを使用して、グループの電子メールアドレスを使用して Active Directory 配布グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="5a924-117">With the Test-CsGroupExpansion cmdlet, you specify an Active Directory distribution group by using the group’s email address.</span></span> <span data-ttu-id="5a924-118">次に、グループ拡張を使用してグループメンバーシップを取得し、取得したリストを、指定したグループ電子メールアドレスのメンバーシップと比較します。</span><span class="sxs-lookup"><span data-stu-id="5a924-118">Test-CsGroupExpansion then uses group expansion to retrieve the group membership and compare the retrieved list to the membership of the group email address that you supplied.</span></span> <span data-ttu-id="5a924-119">2つのリストが一致する場合は、グループ拡張が正しく機能しています。</span><span class="sxs-lookup"><span data-stu-id="5a924-119">If the two lists match, then group expansion is working correctly.</span></span> <span data-ttu-id="5a924-120">グループ拡張のテストは、サービス自体をテストする方法と、関連付けられた web サービスをテストする方法の2つで確認できます。</span><span class="sxs-lookup"><span data-stu-id="5a924-120">Note that you can test group expansion in two ways: by testing the service itself or by testing the associated web service.</span></span>

<span data-ttu-id="5a924-121">詳細については、「 [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a924-121">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5a924-122">テストの実行</span><span class="sxs-lookup"><span data-stu-id="5a924-122">Running the test</span></span>

<span data-ttu-id="5a924-123">Test-CsGroupExpansion コマンドレットは、事前構成されたテストアカウント (「Lync Server テストを実行するためのテストアカウントの設定」を参照)、または Lync Server が有効になっているユーザーのアカウントのいずれかを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="5a924-123">The Test-CsGroupExpansion cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who was enabled for Lync Server.</span></span> <span data-ttu-id="5a924-124">このチェックをテストアカウントを使用して実行するには、テスト対象の Lync Server プールの FQDN と、有効な配布グループの電子メールアドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a924-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the email address for a valid distribution group.</span></span> <span data-ttu-id="5a924-125">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5a924-125">For example:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

<span data-ttu-id="5a924-126">実際のユーザーアカウントを使用してこのチェックを実行するには、まず、アカウント名とパスワードを含む Lync Server credentials オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a924-126">To run this check using an actual user account, you must first create a Lync Server credentials object that contains the account name and password.</span></span> <span data-ttu-id="5a924-127">次に、システムが Test-CsGroupExpansion を呼び出すときに、その資格情報オブジェクトと、そのアカウントに割り当てられた SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a924-127">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsGroupExpansion:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="5a924-128">詳細については、「 [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a924-128">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5a924-129">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="5a924-129">Determining success or failure</span></span>

<span data-ttu-id="5a924-130">指定したユーザーがグループ拡張を使用できる場合は、次のような出力が得られ、Result プロパティは Success としてマークされ**ます。**</span><span class="sxs-lookup"><span data-stu-id="5a924-130">If the specified user can use group expansion, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="5a924-131">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="5a924-131">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="5a924-132">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5a924-132">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5a924-133">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="5a924-133">Result : Success</span></span>

<span data-ttu-id="5a924-134">待機時間:00:00: 01.1234976</span><span class="sxs-lookup"><span data-stu-id="5a924-134">Latency : 00:00:01.1234976</span></span>

<span data-ttu-id="5a924-135">エラー</span><span class="sxs-lookup"><span data-stu-id="5a924-135">Error :</span></span>

<span data-ttu-id="5a924-136">分析</span><span class="sxs-lookup"><span data-stu-id="5a924-136">Diagnosis :</span></span>

<span data-ttu-id="5a924-137">指定したユーザーがグループ拡張を使用できない場合、結果は失敗として表示され、追加情報が Error および診断プロパティに記録されます。</span><span class="sxs-lookup"><span data-stu-id="5a924-137">If the specified user can't use group expansion, then the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="5a924-138">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="5a924-138">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="5a924-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5a924-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5a924-140">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="5a924-140">Result : Failure</span></span>

<span data-ttu-id="5a924-141">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="5a924-141">Latency : 00:00:00</span></span>

<span data-ttu-id="5a924-142">エラー</span><span class="sxs-lookup"><span data-stu-id="5a924-142">Error :</span></span>

<span data-ttu-id="5a924-143">分析</span><span class="sxs-lookup"><span data-stu-id="5a924-143">Diagnosis :</span></span>

<span data-ttu-id="5a924-144">テスト-CsGroupExpansion: エンドポイントを登録できませんでした。</span><span class="sxs-lookup"><span data-stu-id="5a924-144">Test-CsGroupExpansion : The endpoint was unable to register.</span></span> <span data-ttu-id="5a924-145">具体的な理由については、「ErrorCode」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a924-145">See the ErrorCode for specific reason.</span></span>

<span data-ttu-id="5a924-146">前の出力には、指定したユーザーが Lync Server に登録できなかったためにテストが失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="5a924-146">The previous output states that the test failed because the specified user was unable to register with Lync Server.</span></span> <span data-ttu-id="5a924-147">これは通常、テストアカウントが存在しないか、Lync Server に対して有効になっていない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="5a924-147">This will typically occur if the test account does not exist or has not enabled for Lync Server.</span></span> <span data-ttu-id="5a924-148">アカウントが存在するかどうかを確認し、次のようなコマンドを実行することによって、そのアカウントが有効になっているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5a924-148">You can verify that the account exists, and determine whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to the following:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="5a924-149">Test-CsGroupExpansion に失敗した場合は、次のように詳細なパラメーターを含めて、テストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5a924-149">If Test-CsGroupExpansion fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

<span data-ttu-id="5a924-150">Verbose パラメーターが指定されている場合は、指定したユーザーが Lync Server にログオンできるかどうかを確認したときに実行された各操作のステップごとのアカウントが返されます。</span><span class="sxs-lookup"><span data-stu-id="5a924-150">When the Verbose parameter is included Test-CsGroupExpansion will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="5a924-151">たとえば、次の出力は、指定された配布グループが見つからなかったことを示しています。</span><span class="sxs-lookup"><span data-stu-id="5a924-151">For example, this output indicates that the specified distribution group couldn't be found:</span></span>

<span data-ttu-id="5a924-152">Web チケットを取得しようとしています。</span><span class="sxs-lookup"><span data-stu-id="5a924-152">Trying to get web ticket.</span></span>

<span data-ttu-id="5a924-153">Web サービス url:https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="5a924-153">Web Service url : https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="5a924-154">NTLM/Kerb 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a924-154">Using NTLM/Kerb auth.</span></span>

<span data-ttu-id="5a924-155">GetWebTicketActivity が完了しました。</span><span class="sxs-lookup"><span data-stu-id="5a924-155">GetWebTicketActivity completed.</span></span>

<span data-ttu-id="5a924-156">' VerifyDistributionList ' アクティビティが開始されました。</span><span class="sxs-lookup"><span data-stu-id="5a924-156">'VerifyDistributionList' activity started.</span></span>

<span data-ttu-id="5a924-157">DLX Web サービス応答ステータスは: NotFound です。</span><span class="sxs-lookup"><span data-stu-id="5a924-157">DLX Web Service Response Status is: NotFound.</span></span>

<span data-ttu-id="5a924-158">' VerifyDistributionList ' アクティビティは、' 0.2597923 ' 秒で完了しました。</span><span class="sxs-lookup"><span data-stu-id="5a924-158">'VerifyDistributionList' activity completed in '0.2597923' secs.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5a924-159">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="5a924-159">Reasons why the test might have failed</span></span>

<span data-ttu-id="5a924-160">次に、Test-CsGroupExpansion が失敗する主な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="5a924-160">Here are some common reasons why Test-CsGroupExpansion might fail:</span></span>

  - <span data-ttu-id="5a924-161">無効なユーザーアカウントが指定されています。</span><span class="sxs-lookup"><span data-stu-id="5a924-161">You specified an invalid user account.</span></span> <span data-ttu-id="5a924-162">ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a924-162">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="5a924-163">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="5a924-163">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="5a924-164">ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a924-164">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="5a924-165">Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server に対して有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="5a924-165">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="5a924-166">グループの拡張が無効になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5a924-166">Group expansion might be disabled.</span></span> <span data-ttu-id="5a924-167">グループ拡張を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5a924-167">It is possible to turn off group expansion.</span></span> <span data-ttu-id="5a924-168">グループ拡張が無効になっている場合、Test-CsGroupExpansion コマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="5a924-168">If group expansion was disabled then the Test-CsGroupExpansion cmdlet will fail.</span></span> <span data-ttu-id="5a924-169">グループ拡張が有効になっているかどうかを判断するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5a924-169">To determine whether group expansion is enabled, use a command similar to this:</span></span>
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

