---
title: 'Lync Server 2013: フェデレーションドメインに接続するためのテスト機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a84e952f9c23fc95d3856b73697a049768ea179
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a><span data-ttu-id="6821e-102">Lync Server 2013 からフェデレーションドメインに接続するためのテスト機能</span><span class="sxs-lookup"><span data-stu-id="6821e-102">Testing ability to connect to a federated domain from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6821e-103">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="6821e-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6821e-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="6821e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6821e-105">毎日</span><span class="sxs-lookup"><span data-stu-id="6821e-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6821e-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="6821e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6821e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6821e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6821e-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="6821e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6821e-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6821e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="6821e-110">Windows PowerShell のリモートインスタンスを使用して実行する場合は、Test-csfederatedpartner コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6821e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsFederatedPartner cmdlet.</span></span> <span data-ttu-id="6821e-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6821e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6821e-112">説明</span><span class="sxs-lookup"><span data-stu-id="6821e-112">Description</span></span>

<span data-ttu-id="6821e-113">Test-CsFederatedPartner を実行して、フェデレーション パートナーのドメインに接続できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6821e-113">Test-CsFederatedPartner verifies your ability to connect to the domain of a federated partner.</span></span> <span data-ttu-id="6821e-114">ドメインへの接続を確認するには、そのドメインが許可された (フェデレーション) ドメインのコレクションに記載されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6821e-114">To verify the connectivity to a domain, that domain must be listed in the collection of allowed (federated) domains.</span></span> <span data-ttu-id="6821e-115">次のコマンドを使用して、許可されたドメインの一覧にあるドメインの一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="6821e-115">You can retrieve a list of the domains on your allowed domains list by using this command:</span></span>

    Get-CsAllowedDomain

<span data-ttu-id="6821e-116">詳細については、 [test-csfederatedpartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6821e-116">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6821e-117">テストの実行</span><span class="sxs-lookup"><span data-stu-id="6821e-117">Running the test</span></span>

<span data-ttu-id="6821e-118">FederatedPartner コマンドレットでは、エッジサーバーの FQDN とフェデレーションパートナーの FQDN という2つの情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="6821e-118">The Test-FederatedPartner cmdlet requires two pieces of information: the FQDN of your Edge Server and the FQDN of the federated partner.</span></span> <span data-ttu-id="6821e-119">たとえば、次のコマンドは、ドメイン contoso.com に接続できるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="6821e-119">For example, this command tests the ability to connect to the domain contoso.com:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

<span data-ttu-id="6821e-120">次のコマンドを実行すると、許可されたドメインの一覧に現在あるすべてのドメインへの接続をテストできます。</span><span class="sxs-lookup"><span data-stu-id="6821e-120">This command enables you to test the connections to all the domains currently on your allowed domains list:</span></span>

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

<span data-ttu-id="6821e-121">詳細については、 [test-csfederatedpartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6821e-121">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="6821e-122">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="6821e-122">Determining success or failure</span></span>

<span data-ttu-id="6821e-123">指定したドメインに接続できる場合は、次のような出力が得られ、Result プロパティは Success としてマークされ**ます。**</span><span class="sxs-lookup"><span data-stu-id="6821e-123">If the specified domain can be contacted, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="6821e-124">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6821e-124">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6821e-125">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="6821e-125">Result : Success</span></span>

<span data-ttu-id="6821e-126">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="6821e-126">Latency : 00:00:00</span></span>

<span data-ttu-id="6821e-127">エラー</span><span class="sxs-lookup"><span data-stu-id="6821e-127">Error :</span></span>

<span data-ttu-id="6821e-128">分析</span><span class="sxs-lookup"><span data-stu-id="6821e-128">Diagnosis :</span></span>

<span data-ttu-id="6821e-129">指定したドメインに接続できない場合は、結果がエラーとして表示され、追加情報が Error および診断プロパティに記録されます。</span><span class="sxs-lookup"><span data-stu-id="6821e-129">If the specified domain cannot be contacted, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="6821e-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6821e-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6821e-131">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="6821e-131">Result : Failure</span></span>

<span data-ttu-id="6821e-132">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="6821e-132">Latency : 00:00:00</span></span>

<span data-ttu-id="6821e-133">エラー: 504、サーバーのタイムアウト</span><span class="sxs-lookup"><span data-stu-id="6821e-133">Error : 504, Server time-out</span></span>

<span data-ttu-id="6821e-134">診断: ErrorCode = 2, Source = litwareinc, Reason = 「」を参照</span><span class="sxs-lookup"><span data-stu-id="6821e-134">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="6821e-135">応答コードと理由の語句。</span><span class="sxs-lookup"><span data-stu-id="6821e-135">response code and reason phrase.</span></span>

<span data-ttu-id="6821e-136">DiagnosticHeader ()</span><span class="sxs-lookup"><span data-stu-id="6821e-136">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="6821e-137">たとえば、前回の出力では、サーバータイムアウトエラーによってテストが失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="6821e-137">For example, the previous output states that the test failed because of a server time-out error.</span></span> <span data-ttu-id="6821e-138">これは、通常、ネットワーク接続の問題またはエッジサーバーへの接続の問題を示します。</span><span class="sxs-lookup"><span data-stu-id="6821e-138">This typically indicates either network connectivity problems or problems contacting the Edge Server.</span></span>

<span data-ttu-id="6821e-139">Test-csfederatedpartner が失敗した場合は、次のように詳細なパラメーターを含めて、テストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6821e-139">If Test-CsFederatedPartner fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="6821e-140">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="6821e-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="6821e-141">Test-csfederatedpartner が失敗する可能性のある一般的な原因を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6821e-141">Here are some common reasons why Test-CsFederatedPartner might fail:</span></span>

  - <span data-ttu-id="6821e-142">エッジサーバーを使用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6821e-142">The Edge Server might not be available.</span></span> <span data-ttu-id="6821e-143">次のコマンドを使用して、エッジサーバーの Fqdn を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6821e-143">You can the FQDNs of your Edge Servers by using this command:</span></span>
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    <span data-ttu-id="6821e-144">その後、各エッジサーバーに ping して、ネットワーク経由でアクセスできることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="6821e-144">You can then ping each Edge Server to verify that it can be accessed over the network.</span></span> <span data-ttu-id="6821e-145">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6821e-145">For example:</span></span>
    
        ping atl-edge-001.litwareinc.com

  - <span data-ttu-id="6821e-146">指定したドメインが、許可されたドメインリストに表示されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6821e-146">The specified domain might not be listed on the allowed domains list.</span></span> <span data-ttu-id="6821e-147">許可されたドメインリストに追加されたドメインを確認するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6821e-147">To verify the domains that were added to the allowed domains list, use this command:</span></span>
    
        Get-CsAllowedDomain
    
    <span data-ttu-id="6821e-148">ユーザーが通信をブロックされたドメインの一覧を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6821e-148">If you’d like to see a list of domains that users were blocked from communicating with, then use this command:</span></span>
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

