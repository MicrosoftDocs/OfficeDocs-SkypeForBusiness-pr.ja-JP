---
title: 'Lync Server 2013: Lync 通知への Exchange のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Exchange to Lync notifications
ms:assetid: ed2d6325-3cf5-4450-9951-03092bcb0a7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727315(v=OCS.15)
ms:contentKeyID: 63969665
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5e6010d7884bca7ec82d4992b83e22cce315b1f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a><span data-ttu-id="9afd6-102">Lync Server 2013 での Lync 通知への Exchange のテスト</span><span class="sxs-lookup"><span data-stu-id="9afd6-102">Testing Exchange to Lync notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9afd6-103">_**トピックの最終更新日:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="9afd6-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9afd6-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="9afd6-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9afd6-105">毎日</span><span class="sxs-lookup"><span data-stu-id="9afd6-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9afd6-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="9afd6-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9afd6-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9afd6-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9afd6-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="9afd6-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9afd6-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9afd6-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9afd6-110">Windows PowerShell のリモートインスタンスを使用して実行する場合は、 <strong>test-csexstoragenotification</strong>コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9afd6-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExStorageNotification</strong> cmdlet.</span></span> <span data-ttu-id="9afd6-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9afd6-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9afd6-112">説明</span><span class="sxs-lookup"><span data-stu-id="9afd6-112">Description</span></span>

<span data-ttu-id="9afd6-113">**Test-csexstoragenotification**コマンドレットは、ユーザーの連絡先リストに対して更新が行われたときに、Microsoft Exchange Server 2013 notification Service が Lync Server 2013 に通知することを確認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9afd6-113">The **Test-CsExStorageNotification** cmdlet is used to verify that the Microsoft Exchange Server 2013 notification service can notify Lync Server 2013 any time updates are made to a user's Contact List.</span></span> <span data-ttu-id="9afd6-114">このコマンドレットは、統合連絡先ストアを使用しているときにのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="9afd6-114">This cmdlet is valid only if you are using the unified contact store.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9afd6-115">テストの実行</span><span class="sxs-lookup"><span data-stu-id="9afd6-115">Running the test</span></span>

<span data-ttu-id="9afd6-116">例1に示すコマンドは、Lync Server Storage Service がユーザー sip:kenmyer@litwareinc.com の Microsoft Exchange Server メールボックス通知サービスに接続できるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="9afd6-116">The command shown in Example 1 tests to see whether the Lync Server Storage Service can connect to the Microsoft Exchange Server mailbox notification service for the user sip:kenmyer@litwareinc.com.</span></span> <span data-ttu-id="9afd6-117">この例では、WCF バインドとして NetNamedPipe を使用します。</span><span class="sxs-lookup"><span data-stu-id="9afd6-117">In this example, NetNamedPipe is used as the WCF binding.</span></span>

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9afd6-118">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="9afd6-118">Determining success or failure</span></span>

<span data-ttu-id="9afd6-119">Exchange 統合が正しく構成されている場合は、次のような出力が得られます。 Result プロパティは**Success**としてマークされています。</span><span class="sxs-lookup"><span data-stu-id="9afd6-119">If Exchange integration is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="9afd6-120">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9afd6-120">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9afd6-121">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="9afd6-121">Result : Success</span></span>

<span data-ttu-id="9afd6-122">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9afd6-122">Latency : 00:00:00</span></span>

<span data-ttu-id="9afd6-123">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="9afd6-123">Error Message :</span></span>

<span data-ttu-id="9afd6-124">分析</span><span class="sxs-lookup"><span data-stu-id="9afd6-124">Diagnosis :</span></span>

<span data-ttu-id="9afd6-125">指定したユーザーが通知を受信できない場合は、結果がエラーとして表示され、追加情報が Error および診断プロパティに記録されます。</span><span class="sxs-lookup"><span data-stu-id="9afd6-125">If the specified user can't receive notifications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="9afd6-126">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9afd6-126">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9afd6-127">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="9afd6-127">Result : Failure</span></span>

<span data-ttu-id="9afd6-128">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9afd6-128">Latency : 00:00:00</span></span>

<span data-ttu-id="9afd6-129">エラーメッセージ: 10060。接続しているパーティが原因で接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="9afd6-129">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="9afd6-130">一定期間後に正しく応答しなかったか、または</span><span class="sxs-lookup"><span data-stu-id="9afd6-130">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="9afd6-131">接続されたホストの接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="9afd6-131">established connection failed because connected host has</span></span>

<span data-ttu-id="9afd6-132">10.188.116.96: 5061 に応答できませんでした</span><span class="sxs-lookup"><span data-stu-id="9afd6-132">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="9afd6-133">内部例外: 接続の試行が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="9afd6-133">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="9afd6-134">接続されたパーティは、一定期間の後に正しく応答しませんでした</span><span class="sxs-lookup"><span data-stu-id="9afd6-134">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="9afd6-135">接続されているホストが原因で、接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="9afd6-135">time, or established connection failed because connected host</span></span>

<span data-ttu-id="9afd6-136">10.188.116.96: 5061 に応答できませんでした</span><span class="sxs-lookup"><span data-stu-id="9afd6-136">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="9afd6-137">分析</span><span class="sxs-lookup"><span data-stu-id="9afd6-137">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9afd6-138">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="9afd6-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="9afd6-139">**Test-csexstoragenotification**が失敗する可能性のある一般的な原因を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9afd6-139">Here are some common reasons why **Test-CsExStorageNotification** might fail:</span></span>

  - <span data-ttu-id="9afd6-140">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="9afd6-140">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="9afd6-141">省略可能なパラメーターが使用されている場合、オプションのパラメーターが正しく構成されている必要があります。テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="9afd6-141">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="9afd6-142">オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="9afd6-142">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="9afd6-143">Microsoft Exchange Server が正しく構成されていないか、まだ展開されていない場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="9afd6-143">This command will fail if the Microsoft Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9afd6-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="9afd6-144">See Also</span></span>


[<span data-ttu-id="9afd6-145">Test-csexstorageconnectivity</span><span class="sxs-lookup"><span data-stu-id="9afd6-145">Test-CsExStorageConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

