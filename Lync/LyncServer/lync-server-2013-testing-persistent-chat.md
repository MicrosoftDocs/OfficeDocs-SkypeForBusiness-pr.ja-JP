---
title: 'Lync Server 2013: 常設チャットのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78e756de75dda7d7b0a96d9a49233818a5c86576
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="445ba-102">Lync Server 2013 での常設チャットのテスト</span><span class="sxs-lookup"><span data-stu-id="445ba-102">Testing persistent chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="445ba-103">_**最終更新日:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="445ba-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="445ba-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="445ba-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="445ba-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="445ba-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="445ba-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="445ba-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="445ba-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="445ba-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="445ba-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="445ba-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="445ba-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="445ba-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="445ba-110">Windows PowerShell のリモートインスタンスを使って実行する場合は、 <strong>CsPersistentChatMessage</strong>コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="445ba-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsPersistentChatMessage</strong> cmdlet.</span></span> <span data-ttu-id="445ba-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="445ba-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="445ba-112">説明</span><span class="sxs-lookup"><span data-stu-id="445ba-112">Description</span></span>

<span data-ttu-id="445ba-113">**CsPersistentChatMessage**コマンドレットは、1組のテストユーザーが常設チャットサービスを使ってメッセージを交換できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="445ba-113">The **Test-CsPersistentChatMessage** cmdlet verifies that a pair of test users can exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="445ba-114">これを行うには、コマンドレットは2人のユーザーを Lync Server 2013 に記録し、ユーザーを永続的なチャットルームに接続して、1組のメッセージを交換し、チャットルームを終了して2人のユーザーをログオフします。</span><span class="sxs-lookup"><span data-stu-id="445ba-114">To do this, the cmdlet logs the two users on to Lync Server 2013, connects the users to a persistent Chat room, exchanges a pair of messages, then exits the chat room and logs off the two users.</span></span> <span data-ttu-id="445ba-115">チャットルームを作成していない場合、または2つのテストユーザーアカウントに常設チャットサービスへのアクセスを提供する常設チャットポリシーが割り当てられていない場合は、このコマンドレットの呼び出しは失敗します。</span><span class="sxs-lookup"><span data-stu-id="445ba-115">Note that calls to this cmdlet will fail if you have not created any chat rooms or if the two test user accounts are not assigned a Persistent Chat policy that gives them access to the Persistent Chat service.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="445ba-116">テストの実行</span><span class="sxs-lookup"><span data-stu-id="445ba-116">Running the test</span></span>

<span data-ttu-id="445ba-117">次の例に示すコマンドは、一対のユーザー (litwareinc\\pilar と litwareinc\\Kenmyer) が Lync Server 2013 にログオンして、常設チャットサービスを使ってメッセージを交換する機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="445ba-117">The commands shown in the following example test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="445ba-118">これを行うには、この例の最初のコマンドでは、 **Credential**コマンドレットを使用して、User Pilar Ackerman の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="445ba-118">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="445ba-119">(Logon name、litwareinc\\pilar はパラメーターとして指定されているため、Windows PowerShell 資格情報の要求ダイアログボックスでは、管理者は Pilar Ackerman アカウントのパスワードを入力する必要があります)。結果として得られた資格情報オブジェクトは、$cred 1 という名前の変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="445ba-119">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="445ba-120">2番目のコマンドでも同じことが実行されますが、今回は Ken Myer アカウントの credential オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="445ba-120">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="445ba-121">資格情報オブジェクトが手元にある場合、3番目のコマンドは、これら2人のユーザーが Lync Server 2013 にログオンして、常設チャットを使ってメッセージを交換できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="445ba-121">With the credential objects in hand, the third command determines whether these two users can log on to Lync Server 2013 and exchange messages using Persistent Chat.</span></span> <span data-ttu-id="445ba-122">この処理を実行するには、 **CsPersistentChatMessage**コマンドレットは、次のパラメーターを使用して呼び出されます。 Targetfqdn (レジストラープールの FQDN)SenderSipAddress (最初のテストユーザーの SIP アドレス)SenderCredential (同じユーザーの資格情報を格納する Windows PowerShell オブジェクト)ReceiverSipAddress (他のテストユーザーの SIP アドレス)と ReceiverCredential (他のテストユーザーの資格情報を格納する Windows PowerShell オブジェクト)。</span><span class="sxs-lookup"><span data-stu-id="445ba-122">To perform this task, the **Test-CsPersistentChatMessage** cmdlet is called using the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object that contains the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object that contains the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="445ba-123">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="445ba-123">Determining success or failure</span></span>

<span data-ttu-id="445ba-124">指定したユーザーが有効な場所のポリシーを持っている場合は、次のような結果が返され、Result プロパティは**Success**とマークされます。</span><span class="sxs-lookup"><span data-stu-id="445ba-124">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="445ba-125">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="445ba-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="445ba-126">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="445ba-126">Result : Success</span></span>

<span data-ttu-id="445ba-127">待ち時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="445ba-127">Latency : 00:00:00</span></span>

<span data-ttu-id="445ba-128">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="445ba-128">Error Message :</span></span>

<span data-ttu-id="445ba-129">診断</span><span class="sxs-lookup"><span data-stu-id="445ba-129">Diagnosis :</span></span>

<span data-ttu-id="445ba-130">指定したユーザーが常設チャットサービスを使用してメッセージを交換できない場合、結果はエラーとして表示さ**れ、その**他の情報はエラーと診断のプロパティに記録されます。</span><span class="sxs-lookup"><span data-stu-id="445ba-130">If the specified users can't exchange messages using the Persistent Chat service, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="445ba-131">警告: 指定した完全修飾のレジストラーポート番号の読み取りに失敗しました</span><span class="sxs-lookup"><span data-stu-id="445ba-131">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="445ba-132">ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="445ba-132">domain name (FQDN).</span></span> <span data-ttu-id="445ba-133">既定のレジストラーポート番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="445ba-133">Using default Registrar port number.</span></span> <span data-ttu-id="445ba-134">エラー</span><span class="sxs-lookup"><span data-stu-id="445ba-134">Exception:</span></span>

<span data-ttu-id="445ba-135">InvalidOperationException: トポロジで一致するクラスターが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="445ba-135">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="445ba-136">自宅</span><span class="sxs-lookup"><span data-stu-id="445ba-136">at</span></span>

<span data-ttu-id="445ba-137">SipSyntheticTransaction-TryRetri の同期を行います。</span><span class="sxs-lookup"><span data-stu-id="445ba-137">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="445ba-138">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="445ba-138">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="445ba-139">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="445ba-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="445ba-140">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="445ba-140">Result : Failure</span></span>

<span data-ttu-id="445ba-141">待ち時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="445ba-141">Latency : 00:00:00</span></span>

<span data-ttu-id="445ba-142">エラーメッセージ: 10060、接続されているパーティのため、接続に失敗しました</span><span class="sxs-lookup"><span data-stu-id="445ba-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="445ba-143">一定の期間が経過した後に正しく応答しなかった場合、または</span><span class="sxs-lookup"><span data-stu-id="445ba-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="445ba-144">接続されているホストに、接続に失敗しました</span><span class="sxs-lookup"><span data-stu-id="445ba-144">established connection failed because connected host has</span></span>

<span data-ttu-id="445ba-145">2001: 4898 \[: f39e: 5c9a: ad83: 81b3: 9944\]: 5061 を応答できませんでした。</span><span class="sxs-lookup"><span data-stu-id="445ba-145">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="445ba-146">内部例外: 接続の試行が失敗したため、接続できませんでした。</span><span class="sxs-lookup"><span data-stu-id="445ba-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="445ba-147">しばらくしても、接続されているパーティが正しく応答しませんでした</span><span class="sxs-lookup"><span data-stu-id="445ba-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="445ba-148">接続されているホストが原因で、時刻、または接続に失敗しました</span><span class="sxs-lookup"><span data-stu-id="445ba-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="445ba-149">が応答しませんでした</span><span class="sxs-lookup"><span data-stu-id="445ba-149">has failed to respond</span></span>

<span data-ttu-id="445ba-150">\[2001: 4898: f39e: 5c9a: ad83: 81b3: 9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="445ba-150">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="445ba-151">診断</span><span class="sxs-lookup"><span data-stu-id="445ba-151">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="445ba-152">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="445ba-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="445ba-153">次に **、テスト-CsPersistentChatMessage**が失敗する可能性がある一般的な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="445ba-153">Here are some common reasons why **Test-CsPersistentChatMessage** might fail:</span></span>

  - <span data-ttu-id="445ba-154">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="445ba-154">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="445ba-155">必須のテストアカウントが存在しないか、正しく作成されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="445ba-155">The required test accounts may not exist or have been correctly created.</span></span>

  - <span data-ttu-id="445ba-156">ネットワークの問題が原因で、予期しないテストの遅延が発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="445ba-156">There may have been a network issue causing an unexpected delay which timed out the test.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="445ba-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="445ba-157">See Also</span></span>


[<span data-ttu-id="445ba-158">Grant-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="445ba-158">Grant-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[<span data-ttu-id="445ba-159">New-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="445ba-159">New-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[<span data-ttu-id="445ba-160">Set-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="445ba-160">Set-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

