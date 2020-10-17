---
title: 'Lync Server 2013: グループ拡張を使用するためのテスト能力'
description: 'Lync Server 2013: グループ拡張を使用するためのテスト機能。'
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
ms.openlocfilehash: 6267bc2099fc420c5c57e1ef80f4bf4491334938
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560793"
---
# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a><span data-ttu-id="0b561-103">Lync Server 2013 でグループ拡張を採用するためのテスト能力</span><span class="sxs-lookup"><span data-stu-id="0b561-103">Testing ability to employ group expansion in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b561-104">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="0b561-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b561-105">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="0b561-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0b561-106">毎日</span><span class="sxs-lookup"><span data-stu-id="0b561-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b561-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="0b561-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0b561-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b561-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b561-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0b561-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0b561-110">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b561-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="0b561-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsGroupExpansion コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b561-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupExpansion cmdlet.</span></span> <span data-ttu-id="0b561-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b561-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0b561-113">説明</span><span class="sxs-lookup"><span data-stu-id="0b561-113">Description</span></span>

<span data-ttu-id="0b561-114">Test-CsGroupExpansion コマンドレットを使用すると、グループ拡張が組織内で動作しているかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="0b561-114">The Test-CsGroupExpansion cmdlet lets you determine whether group expansion is working within your organization.</span></span> <span data-ttu-id="0b561-115">グループ拡張が有効になっている場合、ユーザーは配布グループを連絡先として構成します。</span><span class="sxs-lookup"><span data-stu-id="0b561-115">When group expansion is enabled, users configure distribution groups as a contact.</span></span> <span data-ttu-id="0b561-116">つまり、それらのユーザーは、そのグループの個々のメンバーではなく、グループにメッセージをアドレス指定することによって、すべてのグループメンバーに同じインスタントメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="0b561-116">That means that those users can then send the same instant message to all the group members by addressing the message to the group instead of to individual members of that group.</span></span> <span data-ttu-id="0b561-117">グループ拡張を使用すると、すべてのグループメンバーとその現在の状態をすばやく簡単に表示できます。</span><span class="sxs-lookup"><span data-stu-id="0b561-117">Group expansion enables you to quickly and easily view all the group members and their current status.</span></span>

<span data-ttu-id="0b561-118">Test-CsGroupExpansion コマンドレットを使用して、グループの電子メールアドレスを使用して Active Directory 配布グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="0b561-118">With the Test-CsGroupExpansion cmdlet, you specify an Active Directory distribution group by using the group’s email address.</span></span> <span data-ttu-id="0b561-119">次に Test-CsGroupExpansion グループ拡張を使用してグループメンバーシップを取得し、取得したリストを、指定したグループ電子メールアドレスのメンバーシップと比較します。</span><span class="sxs-lookup"><span data-stu-id="0b561-119">Test-CsGroupExpansion then uses group expansion to retrieve the group membership and compare the retrieved list to the membership of the group email address that you supplied.</span></span> <span data-ttu-id="0b561-120">2つのリストが一致する場合は、グループ拡張が正しく機能しています。</span><span class="sxs-lookup"><span data-stu-id="0b561-120">If the two lists match, then group expansion is working correctly.</span></span> <span data-ttu-id="0b561-121">グループ拡張のテストは、サービス自体をテストする方法と、関連付けられた web サービスをテストする方法の2つで確認できます。</span><span class="sxs-lookup"><span data-stu-id="0b561-121">Note that you can test group expansion in two ways: by testing the service itself or by testing the associated web service.</span></span>

<span data-ttu-id="0b561-122">詳細については、「 [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b561-122">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0b561-123">テストの実行</span><span class="sxs-lookup"><span data-stu-id="0b561-123">Running the test</span></span>

<span data-ttu-id="0b561-124">Test-CsGroupExpansion コマンドレットを実行するには、事前に構成されたテストアカウントを使用するか (「Lync Server テストを実行するためのテストアカウントの設定」を参照してください)、Lync Server が有効になっているユーザーのアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b561-124">The Test-CsGroupExpansion cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who was enabled for Lync Server.</span></span> <span data-ttu-id="0b561-125">このチェックをテストアカウントを使用して実行するには、テスト対象の Lync Server プールの FQDN と、有効な配布グループの電子メールアドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b561-125">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the email address for a valid distribution group.</span></span> <span data-ttu-id="0b561-126">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0b561-126">For example:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

<span data-ttu-id="0b561-127">実際のユーザーアカウントを使用してこのチェックを実行するには、まず、アカウント名とパスワードを含む Lync Server credentials オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b561-127">To run this check using an actual user account, you must first create a Lync Server credentials object that contains the account name and password.</span></span> <span data-ttu-id="0b561-128">次に、システムが Test-CsGroupExpansion を呼び出すときに、その資格情報オブジェクトと、そのアカウントに割り当てられた SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b561-128">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsGroupExpansion:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="0b561-129">詳細については、「 [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b561-129">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0b561-130">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="0b561-130">Determining success or failure</span></span>

<span data-ttu-id="0b561-131">指定したユーザーがグループ拡張を使用できる場合は、次のような出力が得られ、Result プロパティは Success としてマークされ **ます。**</span><span class="sxs-lookup"><span data-stu-id="0b561-131">If the specified user can use group expansion, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="0b561-132">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="0b561-132">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="0b561-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0b561-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0b561-134">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="0b561-134">Result : Success</span></span>

<span data-ttu-id="0b561-135">待機時間:00:00: 01.1234976</span><span class="sxs-lookup"><span data-stu-id="0b561-135">Latency : 00:00:01.1234976</span></span>

<span data-ttu-id="0b561-136">エラー</span><span class="sxs-lookup"><span data-stu-id="0b561-136">Error :</span></span>

<span data-ttu-id="0b561-137">分析</span><span class="sxs-lookup"><span data-stu-id="0b561-137">Diagnosis :</span></span>

<span data-ttu-id="0b561-138">指定したユーザーがグループ拡張を使用できない場合、結果は失敗として表示され、追加情報が Error および診断プロパティに記録されます。</span><span class="sxs-lookup"><span data-stu-id="0b561-138">If the specified user can't use group expansion, then the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="0b561-139">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="0b561-139">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="0b561-140">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0b561-140">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0b561-141">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="0b561-141">Result : Failure</span></span>

<span data-ttu-id="0b561-142">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="0b561-142">Latency : 00:00:00</span></span>

<span data-ttu-id="0b561-143">エラー</span><span class="sxs-lookup"><span data-stu-id="0b561-143">Error :</span></span>

<span data-ttu-id="0b561-144">分析</span><span class="sxs-lookup"><span data-stu-id="0b561-144">Diagnosis :</span></span>

<span data-ttu-id="0b561-145">Test-CsGroupExpansion: エンドポイントを登録できませんでした。</span><span class="sxs-lookup"><span data-stu-id="0b561-145">Test-CsGroupExpansion : The endpoint was unable to register.</span></span> <span data-ttu-id="0b561-146">具体的な理由については、「ErrorCode」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b561-146">See the ErrorCode for specific reason.</span></span>

<span data-ttu-id="0b561-147">前の出力には、指定したユーザーが Lync Server に登録できなかったためにテストが失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="0b561-147">The previous output states that the test failed because the specified user was unable to register with Lync Server.</span></span> <span data-ttu-id="0b561-148">これは通常、テストアカウントが存在しないか、Lync Server に対して有効になっていない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="0b561-148">This will typically occur if the test account does not exist or has not enabled for Lync Server.</span></span> <span data-ttu-id="0b561-149">アカウントが存在するかどうかを確認し、次のようなコマンドを実行することによって、そのアカウントが有効になっているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="0b561-149">You can verify that the account exists, and determine whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to the following:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="0b561-150">Test-CsGroupExpansion が失敗した場合は、次のようにして、Verbose パラメーターを含むテストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0b561-150">If Test-CsGroupExpansion fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

<span data-ttu-id="0b561-151">Verbose パラメーターが含まれている場合 Test-CsGroupExpansion は、指定されたユーザーが Lync Server にログオンできるかどうかを確認したときに実行された各アクションのステップバイステップのアカウントを返します。</span><span class="sxs-lookup"><span data-stu-id="0b561-151">When the Verbose parameter is included Test-CsGroupExpansion will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="0b561-152">たとえば、次の出力は、指定された配布グループが見つからなかったことを示しています。</span><span class="sxs-lookup"><span data-stu-id="0b561-152">For example, this output indicates that the specified distribution group couldn't be found:</span></span>

<span data-ttu-id="0b561-153">Web チケットを取得しようとしています。</span><span class="sxs-lookup"><span data-stu-id="0b561-153">Trying to get web ticket.</span></span>

<span data-ttu-id="0b561-154">Web サービス url: https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="0b561-154">Web Service url : https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="0b561-155">NTLM/Kerb 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b561-155">Using NTLM/Kerb auth.</span></span>

<span data-ttu-id="0b561-156">GetWebTicketActivity が完了しました。</span><span class="sxs-lookup"><span data-stu-id="0b561-156">GetWebTicketActivity completed.</span></span>

<span data-ttu-id="0b561-157">' VerifyDistributionList ' アクティビティが開始されました。</span><span class="sxs-lookup"><span data-stu-id="0b561-157">'VerifyDistributionList' activity started.</span></span>

<span data-ttu-id="0b561-158">DLX Web サービス応答ステータスは: NotFound です。</span><span class="sxs-lookup"><span data-stu-id="0b561-158">DLX Web Service Response Status is: NotFound.</span></span>

<span data-ttu-id="0b561-159">' VerifyDistributionList ' アクティビティは、' 0.2597923 ' 秒で完了しました。</span><span class="sxs-lookup"><span data-stu-id="0b561-159">'VerifyDistributionList' activity completed in '0.2597923' secs.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0b561-160">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="0b561-160">Reasons why the test might have failed</span></span>

<span data-ttu-id="0b561-161">Test-CsGroupExpansion が失敗する可能性のある一般的な理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0b561-161">Here are some common reasons why Test-CsGroupExpansion might fail:</span></span>

  - <span data-ttu-id="0b561-162">無効なユーザーアカウントが指定されています。</span><span class="sxs-lookup"><span data-stu-id="0b561-162">You specified an invalid user account.</span></span> <span data-ttu-id="0b561-163">ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b561-163">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="0b561-164">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="0b561-164">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="0b561-165">ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b561-165">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="0b561-166">Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server に対して有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="0b561-166">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="0b561-167">グループの拡張が無効になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0b561-167">Group expansion might be disabled.</span></span> <span data-ttu-id="0b561-168">グループ拡張を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0b561-168">It is possible to turn off group expansion.</span></span> <span data-ttu-id="0b561-169">グループ拡張が無効になっている場合、Test-CsGroupExpansion コマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="0b561-169">If group expansion was disabled then the Test-CsGroupExpansion cmdlet will fail.</span></span> <span data-ttu-id="0b561-170">グループ拡張が有効になっているかどうかを判断するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b561-170">To determine whether group expansion is enabled, use a command similar to this:</span></span>
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

