---
title: 'Lync Server 2013: ユニファイド連絡先ストアへのアクセスのテスト'
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
ms.openlocfilehash: 47d5d216a1d7a389f20bf2c59f94baf54636d409
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a><span data-ttu-id="3930a-102">Lync Server 2013 での統合連絡先ストアへのアクセスのテスト</span><span class="sxs-lookup"><span data-stu-id="3930a-102">Testing Unified Contact Store access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3930a-103">_**最終更新日:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="3930a-103">_**Topic Last Modified:** 2015-05-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3930a-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="3930a-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3930a-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="3930a-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3930a-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="3930a-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3930a-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3930a-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3930a-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="3930a-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3930a-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3930a-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3930a-110">Windows PowerShell のリモートインスタンスを使って実行する場合は、 <strong>CsUnifiedContactStore</strong>コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3930a-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUnifiedContactStore</strong> cmdlet.</span></span> <span data-ttu-id="3930a-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3930a-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3930a-112">説明</span><span class="sxs-lookup"><span data-stu-id="3930a-112">Description</span></span>

<span data-ttu-id="3930a-113">Lync Server 2013 で導入された統合連絡先ストアでは、管理者はユーザーの連絡先を Lync Server ではなく Microsoft Exchange Server 2013 に保存するオプションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="3930a-113">The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server.</span></span> <span data-ttu-id="3930a-114">これにより、ユーザーは Lync 2013 だけでなく、Outlook Web Access でも同じ連絡先のセットにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="3930a-114">This allows the user to access the same set of contacts in Outlook Web Access in addition to Lync 2013.</span></span> <span data-ttu-id="3930a-115">(または、引き続き Lync Server に連絡先を保存することができます。</span><span class="sxs-lookup"><span data-stu-id="3930a-115">(Or, you can continue to store contacts in Lync Server.</span></span> <span data-ttu-id="3930a-116">この場合、ユーザーは、Outlook と Outlook Web Access で使用するためと Lync 2013 で使用するために、2つの別々の連絡先を管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3930a-116">In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)</span></span>

<span data-ttu-id="3930a-117">**CsUnifiedContactStore**コマンドレットを実行することで、ユーザーの連絡先がユニファイド連絡先ストアに移動されたかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3930a-117">You can determine whether or not a user's contacts were moved to the unified contact store by running the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="3930a-118">**CsUnifiedContactStore**コマンドレットは、指定されたユーザーアカウントを受け取り、ユニファイド連絡先ストアに接続して、ユーザーの連絡先を取得しようとします。</span><span class="sxs-lookup"><span data-stu-id="3930a-118">The **Test-CsUnifiedContactStore** cmdlet will take the specified user account, connect to the unified contact store, and attempt to retrieve a contact for the user.</span></span> <span data-ttu-id="3930a-119">連絡先を取得できない場合、コマンドは "ユーザーの連絡先は受信されませんでした" というメッセージと共に失敗します。</span><span class="sxs-lookup"><span data-stu-id="3930a-119">If no contacts can be retrieved then the command will fail together with the message "No contacts were received for the user.</span></span> <span data-ttu-id="3930a-120">ユーザーに対して連絡先が存在することを確認します。 "</span><span class="sxs-lookup"><span data-stu-id="3930a-120">Verify that contacts exist for the user."</span></span>

<span data-ttu-id="3930a-121">ユーザーが統合された連絡先ストアに正常に移行したが、連絡先リストに連絡先がない場合は、 **CsUnifiedContactStore**コマンドレットが失敗します。</span><span class="sxs-lookup"><span data-stu-id="3930a-121">Note that the **Test-CsUnifiedContactStore** cmdlet will fail if the user has successfully migrated to the unified contact store but has no contacts on his or her Contacts list.</span></span> <span data-ttu-id="3930a-122">指定したユーザーは、 **CsUnifiedContactStore**コマンドレットを正常に完了するために、少なくとも1つの連絡先を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3930a-122">The specified user must have at least one contact for the **Test-CsUnifiedContactStore** cmdlet to complete successfully.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3930a-123">テストの実行</span><span class="sxs-lookup"><span data-stu-id="3930a-123">Running the test</span></span>

<span data-ttu-id="3930a-124">次の例に示すコマンドは、ユーザー litwareinc\\kenmyer の連絡先がユニファイド連絡先ストアで見つかるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="3930a-124">The commands shown in the following example determine whether contacts for the user litwareinc\\kenmyer can be found in the unified contact store.</span></span> <span data-ttu-id="3930a-125">これを行うには、この例の最初のコマンドでは、 **Credential**コマンドレットを使って、user litwareinc\\kenmyer の Windows PowerShell コマンドラインインターフェイスの credentials オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3930a-125">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="3930a-126">有効な資格情報オブジェクトを作成し、 **CsUnifiedContactStore**コマンドレットでチェックを実行できるようにするには、このアカウントのパスワードを指定する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3930a-126">Note that you must supply the password for this account to create a valid credentials object and to make sure that the **Test-CsUnifiedContactStore** cmdlet can run its check.</span></span>

<span data-ttu-id="3930a-127">この例の2番目のコマンドでは、指定された資格情報オブジェクト ($x) と\\ユーザーの litwareinc KENMYER の SIP アドレスを使って、自分の連絡先がユニファイド連絡先ストアで見つかるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3930a-127">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether his contacts can be found in the unified contact store.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3930a-128">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="3930a-128">Determining success or failure</span></span>

<span data-ttu-id="3930a-129">連絡先ストアへのアクセスが適切に構成されている場合は、次のような結果が返され、Result プロパティは Success とマークされ**ます。**</span><span class="sxs-lookup"><span data-stu-id="3930a-129">If access to the contact store is configured correctly, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="3930a-130">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3930a-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3930a-131">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="3930a-131">Result : Success</span></span>

<span data-ttu-id="3930a-132">待ち時間:00:00: 14.9862716</span><span class="sxs-lookup"><span data-stu-id="3930a-132">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="3930a-133">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="3930a-133">Error Message :</span></span>

<span data-ttu-id="3930a-134">診断</span><span class="sxs-lookup"><span data-stu-id="3930a-134">Diagnosis :</span></span>

<span data-ttu-id="3930a-135">連絡先ストアへのアクセスが正しく構成されていない場合は、結果が**失敗**として表示され、エラーと診断のプロパティに追加の情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="3930a-135">If access to the contact store is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="3930a-136">警告: 指定した完全修飾のレジストラーポート番号の読み取りに失敗しました</span><span class="sxs-lookup"><span data-stu-id="3930a-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="3930a-137">ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="3930a-137">domain name (FQDN).</span></span> <span data-ttu-id="3930a-138">既定のレジストラーポート番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="3930a-138">Using default Registrar port number.</span></span> <span data-ttu-id="3930a-139">エラー</span><span class="sxs-lookup"><span data-stu-id="3930a-139">Exception:</span></span>

<span data-ttu-id="3930a-140">InvalidOperationException: トポロジで一致するクラスターが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="3930a-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="3930a-141">自宅</span><span class="sxs-lookup"><span data-stu-id="3930a-141">at</span></span>

<span data-ttu-id="3930a-142">SipSyntheticTransaction-TryRetri の同期を行います。</span><span class="sxs-lookup"><span data-stu-id="3930a-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="3930a-143">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="3930a-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="3930a-144">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3930a-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3930a-145">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="3930a-145">Result : Failure</span></span>

<span data-ttu-id="3930a-146">待ち時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="3930a-146">Latency : 00:00:00</span></span>

<span data-ttu-id="3930a-147">エラーメッセージ: 10060、接続されているパーティのため、接続に失敗しました</span><span class="sxs-lookup"><span data-stu-id="3930a-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="3930a-148">一定の期間が経過した後に正しく応答しなかった場合、または</span><span class="sxs-lookup"><span data-stu-id="3930a-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="3930a-149">接続されているホストに、接続に失敗しました</span><span class="sxs-lookup"><span data-stu-id="3930a-149">established connection failed because connected host has</span></span>

<span data-ttu-id="3930a-150">10.188.116.96 に応答できませんでした: 5061</span><span class="sxs-lookup"><span data-stu-id="3930a-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="3930a-151">内部例外: 接続の試行が失敗したため、接続できませんでした。</span><span class="sxs-lookup"><span data-stu-id="3930a-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="3930a-152">しばらくしても、接続されているパーティが正しく応答しませんでした</span><span class="sxs-lookup"><span data-stu-id="3930a-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="3930a-153">接続されているホストが原因で、時刻、または接続に失敗しました</span><span class="sxs-lookup"><span data-stu-id="3930a-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="3930a-154">さんが10.188.116.96 に応答できませんでした: 5061</span><span class="sxs-lookup"><span data-stu-id="3930a-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="3930a-155">診断</span><span class="sxs-lookup"><span data-stu-id="3930a-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3930a-156">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="3930a-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="3930a-157">次に **、テスト-CsUnifiedContactStore**が失敗する可能性がある一般的な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="3930a-157">Here are some common reasons why **Test-CsUnifiedContactStore** might fail:</span></span>

  - <span data-ttu-id="3930a-158">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="3930a-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="3930a-159">使用する場合は、オプションのパラメーターが正しく構成されている必要があります。または、テストが失敗します。</span><span class="sxs-lookup"><span data-stu-id="3930a-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="3930a-160">省略可能なパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3930a-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="3930a-161">ユニファイド連絡先ストアに接続できませんでした。ユーザーの連絡先を取得しようとしましたが、できませんでした。</span><span class="sxs-lookup"><span data-stu-id="3930a-161">Connect to the unified contact store failed, and the attempt to retrieve a contact for the user was not possible.</span></span> <span data-ttu-id="3930a-162">ネットワーク接続に問題がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3930a-162">There may be network connectivity issues.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3930a-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="3930a-163">See Also</span></span>


[<span data-ttu-id="3930a-164">New-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="3930a-164">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[<span data-ttu-id="3930a-165">Set-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="3930a-165">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

