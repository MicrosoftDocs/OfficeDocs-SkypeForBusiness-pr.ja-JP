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
ms.openlocfilehash: ee9869d5e7a5e3a48451478de334ee656543f6f5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="c380f-102">Lync Server 2013 での常設チャットのテスト</span><span class="sxs-lookup"><span data-stu-id="c380f-102">Testing persistent chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c380f-103">_**トピックの最終更新日:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="c380f-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c380f-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="c380f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c380f-105">毎日</span><span class="sxs-lookup"><span data-stu-id="c380f-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c380f-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="c380f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c380f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c380f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c380f-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="c380f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c380f-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c380f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c380f-110">Windows PowerShell のリモートインスタンスを使用して実行する場合は、 <strong>test-cspersistentchatmessage</strong>コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c380f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsPersistentChatMessage</strong> cmdlet.</span></span> <span data-ttu-id="c380f-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c380f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c380f-112">説明</span><span class="sxs-lookup"><span data-stu-id="c380f-112">Description</span></span>

<span data-ttu-id="c380f-113">**Test-cspersistentchatmessage**コマンドレットでは、テストユーザーのペアが常設チャットサービスを使用してメッセージを交換できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c380f-113">The **Test-CsPersistentChatMessage** cmdlet verifies that a pair of test users can exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="c380f-114">これを行うために、コマンドレットは、Lync Server 2013 に2人のユーザーを記録し、ユーザーを常設チャットルームに接続し、メッセージのペアを交換して、チャットルームを終了し、2人のユーザーをログオフします。</span><span class="sxs-lookup"><span data-stu-id="c380f-114">To do this, the cmdlet logs the two users on to Lync Server 2013, connects the users to a persistent Chat room, exchanges a pair of messages, then exits the chat room and logs off the two users.</span></span> <span data-ttu-id="c380f-115">ただし、チャットルームを作成していない場合や、2つのテストユーザーアカウントに常設チャットサービスへのアクセスを許可する常設チャットポリシーが割り当てられていない場合は、このコマンドレットの呼び出しは失敗します。</span><span class="sxs-lookup"><span data-stu-id="c380f-115">Note that calls to this cmdlet will fail if you have not created any chat rooms or if the two test user accounts are not assigned a Persistent Chat policy that gives them access to the Persistent Chat service.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c380f-116">テストの実行</span><span class="sxs-lookup"><span data-stu-id="c380f-116">Running the test</span></span>

<span data-ttu-id="c380f-117">次の例に示すコマンドは、ユーザーのペア (litwareinc\\pilar と litwareinc\\Kenmyer) が Lync Server 2013 にログオンし、常設チャットサービスを使用してメッセージを交換できるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="c380f-117">The commands shown in the following example test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="c380f-118">これを行うには、例の最初のコマンドは、**資格情報**コマンドレットを使用して、User Pilar Ackerman の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c380f-118">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="c380f-119">(ログオン名 litwareinc\\pilar がパラメーターとして含まれているため、[Windows PowerShell 資格情報の要求] ダイアログボックスでは、管理者のみが Pilar Ackerman アカウントのパスワードを入力する必要があります)。その後、結果の資格情報オブジェクトは $cred 1 という名前の変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="c380f-119">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="c380f-120">2番目のコマンドは同じことを行いますが、今度は Ken Myer アカウントの credential オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c380f-120">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="c380f-121">資格情報オブジェクトが手元にある場合、3番目のコマンドは、これら2人のユーザーが Lync Server 2013 にログオンして、常設チャットを使用して exchange メッセージにログオンできるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="c380f-121">With the credential objects in hand, the third command determines whether these two users can log on to Lync Server 2013 and exchange messages using Persistent Chat.</span></span> <span data-ttu-id="c380f-122">このタスクを実行するには、次のパラメーターを使用して**test-cspersistentchatmessage**コマンドレットを呼び出します。 targetfqdn (レジストラープールの FQDN)。SenderSipAddress (最初のテストユーザーの SIP アドレス)。SenderCredential (同じユーザーの資格情報を含む Windows PowerShell オブジェクト)。ReceiverSipAddress (他のテストユーザーの SIP アドレス)。と ReceiverCredential (他のテストユーザーの資格情報を含む Windows PowerShell オブジェクト)。</span><span class="sxs-lookup"><span data-stu-id="c380f-122">To perform this task, the **Test-CsPersistentChatMessage** cmdlet is called using the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object that contains the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object that contains the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c380f-123">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="c380f-123">Determining success or failure</span></span>

<span data-ttu-id="c380f-124">指定したユーザーに有効な場所ポリシーがある場合は、次のような出力が得られ、Result プロパティは**Success**としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="c380f-124">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="c380f-125">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c380f-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c380f-126">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="c380f-126">Result : Success</span></span>

<span data-ttu-id="c380f-127">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c380f-127">Latency : 00:00:00</span></span>

<span data-ttu-id="c380f-128">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="c380f-128">Error Message :</span></span>

<span data-ttu-id="c380f-129">分析</span><span class="sxs-lookup"><span data-stu-id="c380f-129">Diagnosis :</span></span>

<span data-ttu-id="c380f-130">指定したユーザーが常設チャットサービスを使用してメッセージを交換できない場合は、結果**がエラーとして**表示され、追加情報が Error および診断プロパティに記録されます。</span><span class="sxs-lookup"><span data-stu-id="c380f-130">If the specified users can't exchange messages using the Persistent Chat service, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="c380f-131">警告: 指定された完全修飾のレジストラーポート番号を読み取ることができませんでした</span><span class="sxs-lookup"><span data-stu-id="c380f-131">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="c380f-132">ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="c380f-132">domain name (FQDN).</span></span> <span data-ttu-id="c380f-133">既定のレジストラーポート番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="c380f-133">Using default Registrar port number.</span></span> <span data-ttu-id="c380f-134">例外</span><span class="sxs-lookup"><span data-stu-id="c380f-134">Exception:</span></span>

<span data-ttu-id="c380f-135">System.invalidoperationexception: トポロジ内に一致するクラスターが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="c380f-135">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="c380f-136">下部</span><span class="sxs-lookup"><span data-stu-id="c380f-136">at</span></span>

<span data-ttu-id="c380f-137">TryRetri を SipSyntheticTransaction していることを示します。</span><span class="sxs-lookup"><span data-stu-id="c380f-137">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="c380f-138">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="c380f-138">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="c380f-139">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c380f-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c380f-140">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="c380f-140">Result : Failure</span></span>

<span data-ttu-id="c380f-141">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c380f-141">Latency : 00:00:00</span></span>

<span data-ttu-id="c380f-142">エラーメッセージ: 10060。接続しているパーティが原因で接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="c380f-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="c380f-143">一定期間後に正しく応答しなかったか、または</span><span class="sxs-lookup"><span data-stu-id="c380f-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="c380f-144">接続されたホストの接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="c380f-144">established connection failed because connected host has</span></span>

<span data-ttu-id="c380f-145">2001年に\[応答できませんでした: 4898: e8: f39e: 5c9a: ad83:\]81b3: 9944: 5061</span><span class="sxs-lookup"><span data-stu-id="c380f-145">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="c380f-146">内部例外: 接続の試行が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="c380f-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="c380f-147">接続されたパーティは、一定期間の後に正しく応答しませんでした</span><span class="sxs-lookup"><span data-stu-id="c380f-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="c380f-148">接続されているホストが原因で、接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="c380f-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="c380f-149">応答に失敗した</span><span class="sxs-lookup"><span data-stu-id="c380f-149">has failed to respond</span></span>

<span data-ttu-id="c380f-150">\[2001年: 4898: e8: f39e: 5c9a: ad83: 81b3:\]9944: 5061</span><span class="sxs-lookup"><span data-stu-id="c380f-150">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="c380f-151">分析</span><span class="sxs-lookup"><span data-stu-id="c380f-151">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c380f-152">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="c380f-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="c380f-153">**Test-cspersistentchatmessage**が失敗する可能性のある一般的な原因を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c380f-153">Here are some common reasons why **Test-CsPersistentChatMessage** might fail:</span></span>

  - <span data-ttu-id="c380f-154">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="c380f-154">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="c380f-155">必要なテストアカウントが存在しないか、正しく作成されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c380f-155">The required test accounts may not exist or have been correctly created.</span></span>

  - <span data-ttu-id="c380f-156">ネットワークの問題が原因で、テストのタイムアウトによる予期しない遅延が発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c380f-156">There may have been a network issue causing an unexpected delay which timed out the test.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c380f-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="c380f-157">See Also</span></span>


[<span data-ttu-id="c380f-158">Get-cspersistentchatpolicy 戻し</span><span class="sxs-lookup"><span data-stu-id="c380f-158">Grant-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[<span data-ttu-id="c380f-159">Get-cspersistentchatpolicy 戻し</span><span class="sxs-lookup"><span data-stu-id="c380f-159">New-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[<span data-ttu-id="c380f-160">Get-cspersistentchatpolicy 戻し</span><span class="sxs-lookup"><span data-stu-id="c380f-160">Set-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

