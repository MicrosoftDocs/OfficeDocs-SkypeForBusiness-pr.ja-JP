---
title: 'Lync Server 2013: スマートフォンへのプッシュ通知のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0e8d6198fc022c03e69e68475d77f513d577ad4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519204"
---
# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a><span data-ttu-id="71c5b-102">Lync Server 2013 でのスマートフォンへのプッシュ通知のテスト</span><span class="sxs-lookup"><span data-stu-id="71c5b-102">Test push notifications to smart phones in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71c5b-103">_**トピックの最終更新日:** 2017-03-15_</span><span class="sxs-lookup"><span data-stu-id="71c5b-103">_**Topic Last Modified:** 2017-03-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71c5b-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="71c5b-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="71c5b-105">毎月</span><span class="sxs-lookup"><span data-stu-id="71c5b-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71c5b-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="71c5b-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="71c5b-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="71c5b-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71c5b-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="71c5b-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="71c5b-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="71c5b-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="71c5b-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsMcxPushNotification コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="71c5b-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="71c5b-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="71c5b-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="71c5b-112">説明</span><span class="sxs-lookup"><span data-stu-id="71c5b-112">Description</span></span>

<span data-ttu-id="71c5b-113">プッシュ通知サービス (Apple Push Notification Service および Microsoft プッシュ通知サービス) は、新しいインスタントメッセージや新しいボイスメールなどのイベントに関する通知を、そのデバイス上の Lync クライアントが現在停止しているか、またはバックグラウンドで実行している場合でも、モバイルデバイスに送信できます。</span><span class="sxs-lookup"><span data-stu-id="71c5b-113">The push notification service (Apple Push Notification Service and Microsoft Push Notification Service) can send notifications about events such as new instant messages or new voice mail to mobile devices such as iPhones and Windows Phones, even if the Lync client on those devices is currently suspended or running in the background.</span></span> <span data-ttu-id="71c5b-114">プッシュ通知サービスは、Microsoft サーバー上で実行されているクラウドベースのサービスです。</span><span class="sxs-lookup"><span data-stu-id="71c5b-114">The push notification service is a cloud-based service that is running on Microsoft servers.</span></span> <span data-ttu-id="71c5b-115">プッシュ通知を利用するには、プッシュ通知クリアリングハウスに接続して認証される必要があります。</span><span class="sxs-lookup"><span data-stu-id="71c5b-115">In order to take advantage of push notifications, you must be able to connect to, and be authenticated by, the push notification clearinghouse.</span></span> <span data-ttu-id="71c5b-116">Test-CsMcxPushNotification コマンドレットを使用すると、管理者はプッシュ通知要求がエッジサーバーを経由してプッシュ通知クリアリングハウスにルーティングされることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="71c5b-116">The Test-CsMcxPushNotification cmdlet enables administrators to verify that push notification requests can be routed through your Edge server to the push notification clearinghouse.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="71c5b-117">テストの実行</span><span class="sxs-lookup"><span data-stu-id="71c5b-117">Running the test</span></span>

<span data-ttu-id="71c5b-118">プッシュ通知サービスをテストするには、Test-CsMcxPushNotification コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="71c5b-118">To test the push notification service, call the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="71c5b-119">エッジサーバーの完全修飾ドメイン名を指定していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="71c5b-119">Make sure that you specify the fully qualified domain name of your Edge server:</span></span>

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

<span data-ttu-id="71c5b-120">詳細については、 [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="71c5b-120">For more information, see the help topic for the [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="71c5b-121">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="71c5b-121">Determining success or failure</span></span>

<span data-ttu-id="71c5b-122">Test-CsMcxPushNotification に成功した場合、コマンドレットはテスト結果成功を返します。</span><span class="sxs-lookup"><span data-stu-id="71c5b-122">If Test-CsMcxPushNotification succeeds the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="71c5b-123">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="71c5b-123">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="71c5b-124">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="71c5b-124">Result : Success</span></span>

<span data-ttu-id="71c5b-125">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="71c5b-125">Latency : 00:00:00</span></span>

<span data-ttu-id="71c5b-126">エラー</span><span class="sxs-lookup"><span data-stu-id="71c5b-126">Error :</span></span>

<span data-ttu-id="71c5b-127">分析</span><span class="sxs-lookup"><span data-stu-id="71c5b-127">Diagnosis :</span></span>

<span data-ttu-id="71c5b-128">プッシュ通知クリアリングハウスに接続できない Test-CsMcxPushNotification 場合は、通常、コマンドレットは失敗のテスト結果を返しません。</span><span class="sxs-lookup"><span data-stu-id="71c5b-128">If Test-CsMcxPushNotification is unable to connect to the push notification clearinghouse the cmdlet will typically not return a test result of Failure.</span></span> <span data-ttu-id="71c5b-129">その代わりに、コマンドは完全に失敗します。</span><span class="sxs-lookup"><span data-stu-id="71c5b-129">Instead the command will usually fail completely.</span></span> <span data-ttu-id="71c5b-130">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="71c5b-130">For example:</span></span>

<span data-ttu-id="71c5b-131">Test-CsMcxPushNotification: 504 (サーバーのタイムアウト) 応答がネットワークから受信され、操作に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="71c5b-131">Test-CsMcxPushNotification : A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="71c5b-132">詳細については、例外の詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71c5b-132">See the exception details for more information.</span></span>

<span data-ttu-id="71c5b-133">行: 1 文字:27</span><span class="sxs-lookup"><span data-stu-id="71c5b-133">At line:1 char:27</span></span>

<span data-ttu-id="71c5b-134">\+Test-CsMcxPushNotification \< \< \< \< AccessEdgeFqdn lyncedge.mydomain.com</span><span class="sxs-lookup"><span data-stu-id="71c5b-134">\+ Test-CsMcxPushNotification \<\<\<\< -AccessEdgeFqdn lyncedge.mydomain.com</span></span>

<span data-ttu-id="71c5b-135">\+ カテゴリ情報: OperationStopped: (:) \[テスト-CsMcxPushNotification \] 、FailureResponseException</span><span class="sxs-lookup"><span data-stu-id="71c5b-135">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException</span></span>

<span data-ttu-id="71c5b-136">\+ FullyQualifiedErrorId: WorkflowNotCompleted、TestMcxPushNotificationCmdlet (TestMcxPushNotificationCmdlet)</span><span class="sxs-lookup"><span data-stu-id="71c5b-136">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="71c5b-137">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="71c5b-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="71c5b-138">プッシュ通知サービスが失敗した場合は、通常、エッジサーバーとの通信に関する問題、またはプッシュ通知クリアリングハウスとの通信に問題があることを示します。</span><span class="sxs-lookup"><span data-stu-id="71c5b-138">If the push notification service fails that usually indicates either problems communicating with your Edge server, or problems communicating with the Push Notification Clearing House.</span></span> <span data-ttu-id="71c5b-139">テスト-CsMcxPushNotification の実行時に問題が発生した場合は、まず、エッジサーバーが正しく動作していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71c5b-139">If you encounter problems when you run Test-CsMcxPushNotification, the first thing that you should do is verify that your Edge server is working correctly.</span></span> <span data-ttu-id="71c5b-140">これを行う方法の1つは Test-CsAVEdgeConnectivity コマンドレットを使用することです。</span><span class="sxs-lookup"><span data-stu-id="71c5b-140">One way to do that is to use the Test-CsAVEdgeConnectivity cmdlet:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="71c5b-141">このチェックは、指定されたユーザーがエッジサーバーに接続できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="71c5b-141">This check verifies that a specified user can connect to the Edge server.</span></span>

<span data-ttu-id="71c5b-142">エッジサーバーが正常に動作しているように見える場合、プッシュ通知のクリアリングハウスに接続できないことがよくあります。</span><span class="sxs-lookup"><span data-stu-id="71c5b-142">If the Edge server seems to be working correctly, that often means that you are unable to connect to the push notification clearinghouse.</span></span> <span data-ttu-id="71c5b-143">そのため、通常は、この URL をポイントする DNS SRV レコードが存在しないか、またはクリアリングハウス URI が正しく構成されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="71c5b-143">In turn, that typically means that you either have not configured the clearinghouse URI correctly or that you do not have a DNS SRV record that points to this URL.</span></span> <span data-ttu-id="71c5b-144">次のコマンドを実行することによって、URI が正しい値 (sip:push@push.lync.com) に設定されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="71c5b-144">You can verify that the URI is set to the correct value (sip:push@push.lync.com) by running this command:</span></span>

    Get-CsMcxConfiguration

<span data-ttu-id="71c5b-145">PushNotificationProxyUri プロパティが sip:push@push.lync.com 以外の値に設定されている場合は、Set-McxConfiguration コマンドレットを使用してその問題を修正できます。</span><span class="sxs-lookup"><span data-stu-id="71c5b-145">If the PushNotificationProxyUri property is set to anything other than sip:push@push.lync.com then you can correct that problem by using the Set-McxConfiguration cmdlet.</span></span> <span data-ttu-id="71c5b-146">たとえば、次のコマンドを実行すると、組織全体に URI が正しく設定されます。</span><span class="sxs-lookup"><span data-stu-id="71c5b-146">For example, this command correctly sets the URI throughout your organization:</span></span>

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

<span data-ttu-id="71c5b-147">詳細については、「 [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) コマンドレット」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="71c5b-147">For more information, see the help topic for the [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) cmdlet.</span></span>

<span data-ttu-id="71c5b-148">URI が正しく構成されている場合は、次の手順として、SIP ドメインおよびエッジサーバーに解決する DNS SRV レコードがあることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71c5b-148">If the URI is configured correctly, your next step should be to verify that you have a DNS SRV record that resolves to your SIP domain and your Edge server.</span></span> <span data-ttu-id="71c5b-149">これらのレコードを構成する方法の詳細については、ヘルプトピック「Mobility の DNS 要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71c5b-149">For more information about how to configure these records, see the help topic DNS Requirements for Mobility.</span></span> <span data-ttu-id="71c5b-150">次のエラーメッセージは、通常、DNS レコードに問題があることを示しています。</span><span class="sxs-lookup"><span data-stu-id="71c5b-150">Note that the following error message usually indicates a problem with DNS records:</span></span>

<span data-ttu-id="71c5b-151">ネットワークからの 504 (サーバータイムアウト) 応答を受信し、操作に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="71c5b-151">A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="71c5b-152">詳細については、例外の詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71c5b-152">See the exception details for more information.</span></span>

<span data-ttu-id="71c5b-153">また、次のエラーメッセージが表示され、Test-CsMcxConfiguration が失敗する可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="71c5b-153">It’s also possible that Test-CsMcxConfiguration will fail with this error message:</span></span>

<span data-ttu-id="71c5b-154">Test-CsMcxPushNotification: プッシュ通知要求が拒否されました。</span><span class="sxs-lookup"><span data-stu-id="71c5b-154">Test-CsMcxPushNotification : Push Notification request was rejected.</span></span>

<span data-ttu-id="71c5b-155">行: 1 文字:27</span><span class="sxs-lookup"><span data-stu-id="71c5b-155">At line:1 char:27</span></span>

<span data-ttu-id="71c5b-156">\+ Test-CsMcxPushNotification \<\<\<\<</span><span class="sxs-lookup"><span data-stu-id="71c5b-156">\+ Test-CsMcxPushNotification \<\<\<\<</span></span>

<span data-ttu-id="71c5b-157">\+ カテゴリ情報: OperationStopped: (:) \[テスト-CsMcxPushNotification \] 、SyntheticTransactionException</span><span class="sxs-lookup"><span data-stu-id="71c5b-157">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span></span>

<span data-ttu-id="71c5b-158">\+ FullyQualifiedErrorId: WorkflowNotCompleted、TestMcxPushNotificationCmdlet (TestMcxPushNotificationCmdlet)</span><span class="sxs-lookup"><span data-stu-id="71c5b-158">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

<span data-ttu-id="71c5b-159">通常、[プッシュ通知要求は拒否されました] メッセージは、URL フィルターを有効にしていて、http: および https: プレフィックスをブロックしている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="71c5b-159">The “Push notification request was rejected” message typically occurs if you have enabled URL filtering and are blocking the http: and https: prefixes.</span></span> <span data-ttu-id="71c5b-160">次のようなコマンドを使用して、どのプレフィックスがブロックされているかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="71c5b-160">You can determine which prefixes are being blocked by using a command similar to the following:</span></span>

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

<span data-ttu-id="71c5b-161">[Http:] または [https:] が結果に表示されている場合は、プッシュ通知を機能させるために、ブロックされたプレフィックスリストから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71c5b-161">If http: or https: appear in the results, you must remove them from the blocked prefix list for push notifications to work.</span></span> <span data-ttu-id="71c5b-162">これを行うには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="71c5b-162">That can be done by using commands similar to these:</span></span>

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

<span data-ttu-id="71c5b-163">詳細については、「 [Set-Cシム Filterconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)コマンドレット」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="71c5b-163">For more information, see the help topic for the [Set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

