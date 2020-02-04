---
title: 'Lync Server 2013: グループ展開を使用するためのテスト機能'
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
ms.openlocfilehash: d79c5432bc2efca0d3a958d3837793eaf227b251
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a><span data-ttu-id="4c664-102">Lync Server 2013 でグループ展開を使用するためのテスト機能</span><span class="sxs-lookup"><span data-stu-id="4c664-102">Testing ability to employ group expansion in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c664-103">_**最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="4c664-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c664-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="4c664-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="4c664-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="4c664-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c664-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="4c664-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="4c664-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c664-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c664-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="4c664-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="4c664-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c664-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="4c664-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、CsGroupExpansion コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c664-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupExpansion cmdlet.</span></span> <span data-ttu-id="4c664-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4c664-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="4c664-112">説明</span><span class="sxs-lookup"><span data-stu-id="4c664-112">Description</span></span>

<span data-ttu-id="4c664-113">テスト用の CsGroupExpansion コマンドレットを使用すると、グループの展開が組織内で機能しているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4c664-113">The Test-CsGroupExpansion cmdlet lets you determine whether group expansion is working within your organization.</span></span> <span data-ttu-id="4c664-114">グループの拡張が有効になっている場合、ユーザーは配布グループを連絡先として構成します。</span><span class="sxs-lookup"><span data-stu-id="4c664-114">When group expansion is enabled, users configure distribution groups as a contact.</span></span> <span data-ttu-id="4c664-115">つまり、これらのユーザーは、グループの個々のメンバーではなく、グループにメッセージをアドレス指定して、すべてのグループメンバーに同じインスタントメッセージを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="4c664-115">That means that those users can then send the same instant message to all the group members by addressing the message to the group instead of to individual members of that group.</span></span> <span data-ttu-id="4c664-116">グループ展開では、すべてのグループメンバーとその現在の状態をすばやく簡単に表示できます。</span><span class="sxs-lookup"><span data-stu-id="4c664-116">Group expansion enables you to quickly and easily view all the group members and their current status.</span></span>

<span data-ttu-id="4c664-117">テスト用の CsGroupExpansion コマンドレットを使用して、グループのメールアドレスを使って Active Directory 配布グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="4c664-117">With the Test-CsGroupExpansion cmdlet, you specify an Active Directory distribution group by using the group’s email address.</span></span> <span data-ttu-id="4c664-118">テスト-CsGroupExpansion では、グループの展開を使用してグループメンバーシップを取得し、取得したリストと、指定したグループメールアドレスのメンバーシップを比較します。</span><span class="sxs-lookup"><span data-stu-id="4c664-118">Test-CsGroupExpansion then uses group expansion to retrieve the group membership and compare the retrieved list to the membership of the group email address that you supplied.</span></span> <span data-ttu-id="4c664-119">2つのリストが一致する場合、グループの展開は正常に機能しています。</span><span class="sxs-lookup"><span data-stu-id="4c664-119">If the two lists match, then group expansion is working correctly.</span></span> <span data-ttu-id="4c664-120">グループの展開をテストするには、サービス自体をテストするか、関連付けられた web サービスをテストするという2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="4c664-120">Note that you can test group expansion in two ways: by testing the service itself or by testing the associated web service.</span></span>

<span data-ttu-id="4c664-121">詳細については、「 [CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c664-121">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="4c664-122">テストの実行</span><span class="sxs-lookup"><span data-stu-id="4c664-122">Running the test</span></span>

<span data-ttu-id="4c664-123">テスト用の CsGroupExpansion コマンドレットを実行するには、事前に定義されたテストアカウント (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照) または Lync Server を有効にしたユーザーのアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c664-123">The Test-CsGroupExpansion cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who was enabled for Lync Server.</span></span> <span data-ttu-id="4c664-124">テストアカウントを使用してこのチェックを実行するには、テスト対象の Lync Server プールの FQDN と、有効な配布グループのメールアドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c664-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the email address for a valid distribution group.</span></span> <span data-ttu-id="4c664-125">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4c664-125">For example:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

<span data-ttu-id="4c664-126">実際のユーザーアカウントを使用してこのチェックを実行するには、まず、アカウント名とパスワードを含む Lync Server 資格情報オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c664-126">To run this check using an actual user account, you must first create a Lync Server credentials object that contains the account name and password.</span></span> <span data-ttu-id="4c664-127">次に、資格情報オブジェクトと、システムによってテスト CsGroupExpansion が呼び出されたときにアカウントに割り当てられる SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c664-127">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsGroupExpansion:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="4c664-128">詳細については、「 [CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c664-128">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="4c664-129">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="4c664-129">Determining success or failure</span></span>

<span data-ttu-id="4c664-130">指定したユーザーがグループ拡張を使用できる場合は、次のような結果として、Success とマークされた Result プロパティが表示され**ます。**</span><span class="sxs-lookup"><span data-stu-id="4c664-130">If the specified user can use group expansion, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="4c664-131">TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="4c664-131">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="4c664-132">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4c664-132">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4c664-133">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="4c664-133">Result : Success</span></span>

<span data-ttu-id="4c664-134">待ち時間:00:00: 01.1234976</span><span class="sxs-lookup"><span data-stu-id="4c664-134">Latency : 00:00:01.1234976</span></span>

<span data-ttu-id="4c664-135">誤差</span><span class="sxs-lookup"><span data-stu-id="4c664-135">Error :</span></span>

<span data-ttu-id="4c664-136">診断</span><span class="sxs-lookup"><span data-stu-id="4c664-136">Diagnosis :</span></span>

<span data-ttu-id="4c664-137">指定したユーザーがグループの展開を使用できない場合は、結果がエラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="4c664-137">If the specified user can't use group expansion, then the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="4c664-138">TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="4c664-138">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="4c664-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4c664-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4c664-140">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="4c664-140">Result : Failure</span></span>

<span data-ttu-id="4c664-141">待ち時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="4c664-141">Latency : 00:00:00</span></span>

<span data-ttu-id="4c664-142">誤差</span><span class="sxs-lookup"><span data-stu-id="4c664-142">Error :</span></span>

<span data-ttu-id="4c664-143">診断</span><span class="sxs-lookup"><span data-stu-id="4c664-143">Diagnosis :</span></span>

<span data-ttu-id="4c664-144">テスト-CsGroupExpansion: エンドポイントは登録できませんでした。</span><span class="sxs-lookup"><span data-stu-id="4c664-144">Test-CsGroupExpansion : The endpoint was unable to register.</span></span> <span data-ttu-id="4c664-145">具体的な理由については、「エラーコード」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4c664-145">See the ErrorCode for specific reason.</span></span>

<span data-ttu-id="4c664-146">以前の出力では、指定されたユーザーが Lync Server に登録できなかったため、テストが失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="4c664-146">The previous output states that the test failed because the specified user was unable to register with Lync Server.</span></span> <span data-ttu-id="4c664-147">これは通常、テストアカウントが存在しないか、Lync Server に対して有効になっていない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="4c664-147">This will typically occur if the test account does not exist or has not enabled for Lync Server.</span></span> <span data-ttu-id="4c664-148">アカウントが存在するかどうかを確認し、次のようなコマンドを実行して、nm-ocs-14-3 のアカウントが有効になっているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4c664-148">You can verify that the account exists, and determine whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to the following:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="4c664-149">テスト用の CsGroupExpansion 展開に失敗した場合は、Verbose パラメーターも含めて、テストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4c664-149">If Test-CsGroupExpansion fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

<span data-ttu-id="4c664-150">Verbose パラメーターが含まれている場合は、指定したユーザーが Lync Server にログオンする機能を確認したときに実行される各操作のステップバイステップのアカウントが返されます。</span><span class="sxs-lookup"><span data-stu-id="4c664-150">When the Verbose parameter is included Test-CsGroupExpansion will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="4c664-151">たとえば、次の出力は、指定された配布グループが見つからなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="4c664-151">For example, this output indicates that the specified distribution group couldn't be found:</span></span>

<span data-ttu-id="4c664-152">Web チケットを取得しようとしています。</span><span class="sxs-lookup"><span data-stu-id="4c664-152">Trying to get web ticket.</span></span>

<span data-ttu-id="4c664-153">Web サービスの url:https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="4c664-153">Web Service url : https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="4c664-154">NTLM/Kerb auth を使用しています。</span><span class="sxs-lookup"><span data-stu-id="4c664-154">Using NTLM/Kerb auth.</span></span>

<span data-ttu-id="4c664-155">GetWebTicketActivity が完了しました。</span><span class="sxs-lookup"><span data-stu-id="4c664-155">GetWebTicketActivity completed.</span></span>

<span data-ttu-id="4c664-156">' VerifyDistributionList ' アクティビティが開始されました。</span><span class="sxs-lookup"><span data-stu-id="4c664-156">'VerifyDistributionList' activity started.</span></span>

<span data-ttu-id="4c664-157">DLX Web サービスの応答状態: NotFound。</span><span class="sxs-lookup"><span data-stu-id="4c664-157">DLX Web Service Response Status is: NotFound.</span></span>

<span data-ttu-id="4c664-158">' VerifyDistributionList ' アクティビティは "0.2597923" 秒で完了しました。</span><span class="sxs-lookup"><span data-stu-id="4c664-158">'VerifyDistributionList' activity completed in '0.2597923' secs.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="4c664-159">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="4c664-159">Reasons why the test might have failed</span></span>

<span data-ttu-id="4c664-160">次に、テスト用の CsGroupExpansion 展開が失敗する可能性がある一般的な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="4c664-160">Here are some common reasons why Test-CsGroupExpansion might fail:</span></span>

  - <span data-ttu-id="4c664-161">無効なユーザアカウントを指定しました。</span><span class="sxs-lookup"><span data-stu-id="4c664-161">You specified an invalid user account.</span></span> <span data-ttu-id="4c664-162">次のようなコマンドを実行すると、ユーザーアカウントが存在するかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4c664-162">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="4c664-163">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="4c664-163">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="4c664-164">ユーザーアカウントが Lync Server 用に有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4c664-164">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="4c664-165">Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server を有効にしていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="4c664-165">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="4c664-166">グループの拡張が無効になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4c664-166">Group expansion might be disabled.</span></span> <span data-ttu-id="4c664-167">グループの拡張機能をオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4c664-167">It is possible to turn off group expansion.</span></span> <span data-ttu-id="4c664-168">グループの拡張が無効になっている場合、テスト用の CsGroupExpansion コマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="4c664-168">If group expansion was disabled then the Test-CsGroupExpansion cmdlet will fail.</span></span> <span data-ttu-id="4c664-169">グループの展開が有効であるかどうかを判断するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c664-169">To determine whether group expansion is enabled, use a command similar to this:</span></span>
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

