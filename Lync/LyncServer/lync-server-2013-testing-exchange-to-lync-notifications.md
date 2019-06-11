---
title: 'Lync Server 2013: Lync 通知への Exchange のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Exchange to Lync notifications
ms:assetid: ed2d6325-3cf5-4450-9951-03092bcb0a7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727315(v=OCS.15)
ms:contentKeyID: 63969665
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fba2f5ad22cb4a741192d5e4d51020b8c04cc39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a><span data-ttu-id="ac7b2-102">Lync Server 2013 での Lync からの通知への Exchange のテスト</span><span class="sxs-lookup"><span data-stu-id="ac7b2-102">Testing Exchange to Lync notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac7b2-103">_**最終更新日:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="ac7b2-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac7b2-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="ac7b2-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ac7b2-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="ac7b2-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac7b2-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="ac7b2-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ac7b2-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac7b2-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac7b2-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ac7b2-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ac7b2-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac7b2-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ac7b2-110">Windows PowerShell のリモートインスタンスを使って実行する場合は、 <strong>CsExStorageNotification</strong>コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac7b2-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExStorageNotification</strong> cmdlet.</span></span> <span data-ttu-id="ac7b2-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ac7b2-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ac7b2-112">説明</span><span class="sxs-lookup"><span data-stu-id="ac7b2-112">Description</span></span>

<span data-ttu-id="ac7b2-113">**CsExStorageNotification**コマンドレットを使用して、ユーザーの連絡先リストが更新されたときに、Microsoft Exchange Server 2013 notification Service が Lync Server 2013 に通知することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac7b2-113">The **Test-CsExStorageNotification** cmdlet is used to verify that the Microsoft Exchange Server 2013 notification service can notify Lync Server 2013 any time updates are made to a user's Contact List.</span></span> <span data-ttu-id="ac7b2-114">このコマンドレットは、ユニファイド連絡先ストアを使用している場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="ac7b2-114">This cmdlet is valid only if you are using the unified contact store.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ac7b2-115">テストの実行</span><span class="sxs-lookup"><span data-stu-id="ac7b2-115">Running the test</span></span>

<span data-ttu-id="ac7b2-116">例1に示すコマンドは、Lync Server ストレージサービスが、ユーザー sip:kenmyer@litwareinc.com の Microsoft Exchange Server メールボックス通知サービスに接続できるかどうかを確認するものです。</span><span class="sxs-lookup"><span data-stu-id="ac7b2-116">The command shown in Example 1 tests to see whether the Lync Server Storage Service can connect to the Microsoft Exchange Server mailbox notification service for the user sip:kenmyer@litwareinc.com.</span></span> <span data-ttu-id="ac7b2-117">この例では、NetNamedPipe は WCF バインディングとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="ac7b2-117">In this example, NetNamedPipe is used as the WCF binding.</span></span>

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ac7b2-118">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="ac7b2-118">Determining success or failure</span></span>

<span data-ttu-id="ac7b2-119">Exchange の統合が正しく構成されている場合は、次のような結果が返され、Result プロパティは**Success**とマークされます。</span><span class="sxs-lookup"><span data-stu-id="ac7b2-119">If Exchange integration is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="ac7b2-120">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ac7b2-120">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ac7b2-121">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="ac7b2-121">Result : Success</span></span>

<span data-ttu-id="ac7b2-122">待ち時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ac7b2-122">Latency : 00:00:00</span></span>

<span data-ttu-id="ac7b2-123">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="ac7b2-123">Error Message :</span></span>

<span data-ttu-id="ac7b2-124">診断</span><span class="sxs-lookup"><span data-stu-id="ac7b2-124">Diagnosis :</span></span>

<span data-ttu-id="ac7b2-125">指定したユーザーが通知を受信できない場合、結果はエラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="ac7b2-125">If the specified user can't receive notifications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="ac7b2-126">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ac7b2-126">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ac7b2-127">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="ac7b2-127">Result : Failure</span></span>

<span data-ttu-id="ac7b2-128">待ち時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ac7b2-128">Latency : 00:00:00</span></span>

<span data-ttu-id="ac7b2-129">エラーメッセージ: 10060、接続されているパーティのため、接続に失敗しました</span><span class="sxs-lookup"><span data-stu-id="ac7b2-129">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="ac7b2-130">一定の期間が経過した後に正しく応答しなかった場合、または</span><span class="sxs-lookup"><span data-stu-id="ac7b2-130">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="ac7b2-131">接続されているホストに、接続に失敗しました</span><span class="sxs-lookup"><span data-stu-id="ac7b2-131">established connection failed because connected host has</span></span>

<span data-ttu-id="ac7b2-132">10.188.116.96 に応答できませんでした: 5061</span><span class="sxs-lookup"><span data-stu-id="ac7b2-132">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="ac7b2-133">内部例外: 接続の試行が失敗したため、接続できませんでした。</span><span class="sxs-lookup"><span data-stu-id="ac7b2-133">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="ac7b2-134">しばらくしても、接続されているパーティが正しく応答しませんでした</span><span class="sxs-lookup"><span data-stu-id="ac7b2-134">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="ac7b2-135">接続されているホストが原因で、時刻、または接続に失敗しました</span><span class="sxs-lookup"><span data-stu-id="ac7b2-135">time, or established connection failed because connected host</span></span>

<span data-ttu-id="ac7b2-136">さんが10.188.116.96 に応答できませんでした: 5061</span><span class="sxs-lookup"><span data-stu-id="ac7b2-136">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="ac7b2-137">診断</span><span class="sxs-lookup"><span data-stu-id="ac7b2-137">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ac7b2-138">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="ac7b2-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="ac7b2-139">次に **、テスト-CsExStorageNotification**が失敗する可能性がある一般的な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="ac7b2-139">Here are some common reasons why **Test-CsExStorageNotification** might fail:</span></span>

  - <span data-ttu-id="ac7b2-140">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="ac7b2-140">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="ac7b2-141">使用する場合は、オプションのパラメーターが正しく構成されている必要があります。または、テストが失敗します。</span><span class="sxs-lookup"><span data-stu-id="ac7b2-141">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="ac7b2-142">省略可能なパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac7b2-142">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="ac7b2-143">Microsoft Exchange Server が正しく構成されていないか、まだ展開されていない場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="ac7b2-143">This command will fail if the Microsoft Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ac7b2-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac7b2-144">See Also</span></span>


[<span data-ttu-id="ac7b2-145">テスト-CsExStorageConnectivity</span><span class="sxs-lookup"><span data-stu-id="ac7b2-145">Test-CsExStorageConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

