---
title: 'Lync Server 2013: 統合連絡先ストアのアクセスのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6022d7651a99c2165961ed8cb8852048c10779ff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a><span data-ttu-id="adc16-102">Lync Server 2013 での統合連絡先ストアアクセスのテスト</span><span class="sxs-lookup"><span data-stu-id="adc16-102">Testing Unified Contact Store access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="adc16-103">_**トピックの最終更新日:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="adc16-103">_**Topic Last Modified:** 2015-05-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="adc16-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="adc16-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="adc16-105">毎日</span><span class="sxs-lookup"><span data-stu-id="adc16-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adc16-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="adc16-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="adc16-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="adc16-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adc16-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="adc16-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="adc16-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="adc16-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="adc16-110">Windows PowerShell のリモートインスタンスを使用して実行する場合は、 <strong>test-csunifiedcontactstore</strong>コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="adc16-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUnifiedContactStore</strong> cmdlet.</span></span> <span data-ttu-id="adc16-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="adc16-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="adc16-112">説明</span><span class="sxs-lookup"><span data-stu-id="adc16-112">Description</span></span>

<span data-ttu-id="adc16-113">Lync Server 2013 で導入された統合連絡先ストアによって、管理者は、ユーザーの連絡先を Lync Server ではなく Microsoft Exchange Server 2013 に保存するオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="adc16-113">The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server.</span></span> <span data-ttu-id="adc16-114">これにより、ユーザーは Lync 2013 に加えて、Outlook Web Access 内の同じ連絡先セットにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="adc16-114">This allows the user to access the same set of contacts in Outlook Web Access in addition to Lync 2013.</span></span> <span data-ttu-id="adc16-115">(または、引き続き Lync Server に連絡先を保存することができます。</span><span class="sxs-lookup"><span data-stu-id="adc16-115">(Or, you can continue to store contacts in Lync Server.</span></span> <span data-ttu-id="adc16-116">その場合、ユーザーは2つの別々の連絡先セットを保持する必要があります。1つは Outlook と Outlook Web Access で使用し、もう1つは Lync 2013 で使用するためです。</span><span class="sxs-lookup"><span data-stu-id="adc16-116">In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)</span></span>

<span data-ttu-id="adc16-117">**Test-csunifiedcontactstore**コマンドレットを実行して、ユーザーの連絡先が統合連絡先ストアに移動されたかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="adc16-117">You can determine whether or not a user's contacts were moved to the unified contact store by running the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="adc16-118">**Test-csunifiedcontactstore**コマンドレットは、指定されたユーザーアカウントを取得し、統合連絡先ストアに接続して、ユーザーの連絡先を取得しようとします。</span><span class="sxs-lookup"><span data-stu-id="adc16-118">The **Test-CsUnifiedContactStore** cmdlet will take the specified user account, connect to the unified contact store, and attempt to retrieve a contact for the user.</span></span> <span data-ttu-id="adc16-119">連絡先を取得できない場合、コマンドは "ユーザーの連絡先は受信されていません" というメッセージと共に失敗します。</span><span class="sxs-lookup"><span data-stu-id="adc16-119">If no contacts can be retrieved then the command will fail together with the message "No contacts were received for the user.</span></span> <span data-ttu-id="adc16-120">ユーザーの連絡先が存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="adc16-120">Verify that contacts exist for the user."</span></span>

<span data-ttu-id="adc16-121">ユーザーが統合連絡先ストアに正常に移行されたが、連絡先リストに連絡先が存在しない場合、 **test-csunifiedcontactstore**コマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="adc16-121">Note that the **Test-CsUnifiedContactStore** cmdlet will fail if the user has successfully migrated to the unified contact store but has no contacts on his or her Contacts list.</span></span> <span data-ttu-id="adc16-122">**Test-csunifiedcontactstore**コマンドレットを正常に完了するには、指定されたユーザーが少なくとも1つの連絡先を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="adc16-122">The specified user must have at least one contact for the **Test-CsUnifiedContactStore** cmdlet to complete successfully.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="adc16-123">テストの実行</span><span class="sxs-lookup"><span data-stu-id="adc16-123">Running the test</span></span>

<span data-ttu-id="adc16-124">次の例に示すコマンドは、ユーザー litwareinc\\kenmyer の連絡先が統合連絡先ストアにあるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="adc16-124">The commands shown in the following example determine whether contacts for the user litwareinc\\kenmyer can be found in the unified contact store.</span></span> <span data-ttu-id="adc16-125">これを行うには、この例の最初のコマンド**は、litwareinc コマンドレットを**使用して、user\\kenmyer の Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="adc16-125">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="adc16-126">有効な資格情報オブジェクトを作成し、 **test-csunifiedcontactstore**コマンドレットでチェックを実行できることを確認するには、このアカウントのパスワードを指定する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="adc16-126">Note that you must supply the password for this account to create a valid credentials object and to make sure that the **Test-CsUnifiedContactStore** cmdlet can run its check.</span></span>

<span data-ttu-id="adc16-127">この例の2番目のコマンドでは、指定された credentials オブジェクト ($x) とユーザー\\litwareinc KENMYER の SIP アドレスを使用して、その連絡先が統合連絡先ストアに存在するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="adc16-127">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether his contacts can be found in the unified contact store.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="adc16-128">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="adc16-128">Determining success or failure</span></span>

<span data-ttu-id="adc16-129">連絡先ストアへのアクセスが正しく構成されている場合は、次のような出力が得られ、Result プロパティは Success としてマークされ**ます。**</span><span class="sxs-lookup"><span data-stu-id="adc16-129">If access to the contact store is configured correctly, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="adc16-130">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="adc16-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="adc16-131">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="adc16-131">Result : Success</span></span>

<span data-ttu-id="adc16-132">待機時間:00:00: 14.9862716</span><span class="sxs-lookup"><span data-stu-id="adc16-132">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="adc16-133">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="adc16-133">Error Message :</span></span>

<span data-ttu-id="adc16-134">分析</span><span class="sxs-lookup"><span data-stu-id="adc16-134">Diagnosis :</span></span>

<span data-ttu-id="adc16-135">連絡先ストアへのアクセスが正しく構成されていない場合、結果は**失敗**として表示され、追加情報が Error および診断プロパティに記録されます。</span><span class="sxs-lookup"><span data-stu-id="adc16-135">If access to the contact store is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="adc16-136">警告: 指定された完全修飾のレジストラーポート番号を読み取ることができませんでした</span><span class="sxs-lookup"><span data-stu-id="adc16-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="adc16-137">ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="adc16-137">domain name (FQDN).</span></span> <span data-ttu-id="adc16-138">既定のレジストラーポート番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="adc16-138">Using default Registrar port number.</span></span> <span data-ttu-id="adc16-139">例外</span><span class="sxs-lookup"><span data-stu-id="adc16-139">Exception:</span></span>

<span data-ttu-id="adc16-140">System.invalidoperationexception: トポロジ内に一致するクラスターが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="adc16-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="adc16-141">下部</span><span class="sxs-lookup"><span data-stu-id="adc16-141">at</span></span>

<span data-ttu-id="adc16-142">TryRetri を SipSyntheticTransaction していることを示します。</span><span class="sxs-lookup"><span data-stu-id="adc16-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="adc16-143">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="adc16-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="adc16-144">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="adc16-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="adc16-145">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="adc16-145">Result : Failure</span></span>

<span data-ttu-id="adc16-146">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="adc16-146">Latency : 00:00:00</span></span>

<span data-ttu-id="adc16-147">エラーメッセージ: 10060。接続しているパーティが原因で接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="adc16-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="adc16-148">一定期間後に正しく応答しなかったか、または</span><span class="sxs-lookup"><span data-stu-id="adc16-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="adc16-149">接続されたホストの接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="adc16-149">established connection failed because connected host has</span></span>

<span data-ttu-id="adc16-150">10.188.116.96: 5061 に応答できませんでした</span><span class="sxs-lookup"><span data-stu-id="adc16-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="adc16-151">内部例外: 接続の試行が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="adc16-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="adc16-152">接続されたパーティは、一定期間の後に正しく応答しませんでした</span><span class="sxs-lookup"><span data-stu-id="adc16-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="adc16-153">接続されているホストが原因で、接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="adc16-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="adc16-154">10.188.116.96: 5061 に応答できませんでした</span><span class="sxs-lookup"><span data-stu-id="adc16-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="adc16-155">分析</span><span class="sxs-lookup"><span data-stu-id="adc16-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="adc16-156">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="adc16-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="adc16-157">**Test-csunifiedcontactstore**が失敗する可能性のある一般的な原因を次に示します。</span><span class="sxs-lookup"><span data-stu-id="adc16-157">Here are some common reasons why **Test-CsUnifiedContactStore** might fail:</span></span>

  - <span data-ttu-id="adc16-158">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="adc16-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="adc16-159">省略可能なパラメーターが使用されている場合、オプションのパラメーターが正しく構成されている必要があります。テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="adc16-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="adc16-160">オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="adc16-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="adc16-161">統合連絡先ストアに接続できませんでした。ユーザーの連絡先を取得しようとしましたができませんでした。</span><span class="sxs-lookup"><span data-stu-id="adc16-161">Connect to the unified contact store failed, and the attempt to retrieve a contact for the user was not possible.</span></span> <span data-ttu-id="adc16-162">ネットワーク接続の問題が発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="adc16-162">There may be network connectivity issues.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="adc16-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="adc16-163">See Also</span></span>


[<span data-ttu-id="adc16-164">新しい-Csuserサービスポリシー</span><span class="sxs-lookup"><span data-stu-id="adc16-164">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[<span data-ttu-id="adc16-165">設定-Csuserサービスポリシー</span><span class="sxs-lookup"><span data-stu-id="adc16-165">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

