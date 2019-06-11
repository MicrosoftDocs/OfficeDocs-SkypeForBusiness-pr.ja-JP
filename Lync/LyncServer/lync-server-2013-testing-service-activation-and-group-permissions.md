---
title: 'Lync Server 2013: サービスのアクティブ化とグループのアクセス許可をテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6616e1f2835ab55f9e3e8f98e5a8693ef3d2fb4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a><span data-ttu-id="69c8f-102">Lync Server 2013 でのサービスのアクティブ化とグループのアクセス許可のテスト</span><span class="sxs-lookup"><span data-stu-id="69c8f-102">Testing service activation and group permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69c8f-103">_**最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="69c8f-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69c8f-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="69c8f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="69c8f-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="69c8f-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69c8f-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="69c8f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="69c8f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="69c8f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69c8f-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="69c8f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="69c8f-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="69c8f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="69c8f-110">Windows PowerShell のリモートインスタンスを使って実行する場合、ユーザーには、テスト-CsTopology コマンドレットを実行するアクセス許可が与えられた RBAC の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="69c8f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTopology cmdlet.</span></span> <span data-ttu-id="69c8f-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="69c8f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="69c8f-112">説明</span><span class="sxs-lookup"><span data-stu-id="69c8f-112">Description</span></span>

<span data-ttu-id="69c8f-113">テスト用の CsTopology コマンドレットを使用すると、Lync Server 2013 がグローバルスコープで正常に機能していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="69c8f-113">The Test-CsTopology cmdlet enables you to verify that Lync Server 2013 is functioning correctly at a global scope.</span></span> <span data-ttu-id="69c8f-114">既定では、コマンドレットは Lync Server インフラストラクチャ全体をチェックし、必要なサービスが実行されていること、およびこれらのサービスに適切な権限が設定されていること、および Lync Server をインストールするときに作成されるユニバーサルセキュリティグループについて確認します。.</span><span class="sxs-lookup"><span data-stu-id="69c8f-114">By default, the cmdlet checks your whole Lync Server infrastructure, verifying that the required services are running and that the appropriate permissions are set for these services and for the universal security groups that are created when you install Lync Server.</span></span>

<span data-ttu-id="69c8f-115">Lync Server のインストールの有効性を確認するだけでなく、テスト用に特定のサービスの有効性を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="69c8f-115">In addition to verifying the validity of the Lync Server installation, Test-CsTopology also lets you check the validity of a specific service.</span></span> <span data-ttu-id="69c8f-116">たとえば、次のコマンドは、プール atl-cs-001.litwareinc.com で A/V 会議サーバーの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="69c8f-116">For example, this command checks the state of the A/V Conferencing Server on the pool atl-cs-001.litwareinc.com:</span></span>

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="69c8f-117">テストの実行</span><span class="sxs-lookup"><span data-stu-id="69c8f-117">Running the test</span></span>

<span data-ttu-id="69c8f-118">既定では、テスト用の CsTopology 内容は画面上に非常に小さな出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="69c8f-118">By default, Test-CsTopology displays very little output on-screen.</span></span> <span data-ttu-id="69c8f-119">代わりに、コマンドレットによって返される情報は、HTML ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="69c8f-119">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="69c8f-120">Report パラメーターを使用すると、テスト用に生成された HTML ファイルのファイルパスとファイル名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="69c8f-120">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsTopology.</span></span> <span data-ttu-id="69c8f-121">レポートパラメーターが含まれていない場合、HTML ファイルは [ユーザー] フォルダーに自動的に保存され、次のような名前が付けられます。 ce84964a-c4da-4622 2-ad34-361f、.html</span><span class="sxs-lookup"><span data-stu-id="69c8f-121">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="69c8f-122">次の例のコマンドは、テスト用の CsTopology ツールを実行して、出力を C\\:\\Logs computertest .html という名前のファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="69c8f-122">The following sample command runs Test-CsTopology and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="69c8f-123">詳細については、「[テスト-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology)ツールレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69c8f-123">For more information, see the Help documentation for the [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="69c8f-124">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="69c8f-124">Determining success or failure</span></span>

<span data-ttu-id="69c8f-125">テスト用コマンドレットのほとんどは、テスト用のコマンドレットによって、成功または失敗を報告します。</span><span class="sxs-lookup"><span data-stu-id="69c8f-125">Unlike most of the test cmdlets, Test-CsTopology does report back Success or Failure.</span></span> <span data-ttu-id="69c8f-126">一部では、コマンドレットが実行されるたびに実行する必要がある多数の確認チェックが行われるためです。</span><span class="sxs-lookup"><span data-stu-id="69c8f-126">In part, that’s due to the large number of verification checks that the cmdlet must make every time that it runs.</span></span> <span data-ttu-id="69c8f-127">代わりに、Internet Explorer を使用して表示できる HTML レポートにデータが保存されます。</span><span class="sxs-lookup"><span data-stu-id="69c8f-127">Instead, data is saved to an HTML report that can then be viewed by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="69c8f-128">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="69c8f-128">Reasons why the test might have failed</span></span>

<span data-ttu-id="69c8f-129">次に、テスト用の CsTopology が失敗する一般的な理由をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="69c8f-129">Here are some common reasons why Test-CsTopology might fail:</span></span>

  - <span data-ttu-id="69c8f-130">テストコンピューターのレプリケーションは最新ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="69c8f-130">Replication might not be up-to-date on the test computer.</span></span> <span data-ttu-id="69c8f-131">CsManagementStoreReplicationStatus コマンドレットを実行して、コンピューターの現在のレプリケーションの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="69c8f-131">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="69c8f-132">レプリケーションの状態が最新でない場合は、次のようなコマンドを使用して、手動でレプリケーションを強制的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="69c8f-132">If the replication status is not up-to-date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="69c8f-133">トポロジを有効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="69c8f-133">The topology might have to be enabled.</span></span> <span data-ttu-id="69c8f-134">Lync Server のトポロジ (ローカルコンピューターに影響を与える可能性のある変更) を変更する場合は、新しいトポロジを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="69c8f-134">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="69c8f-135">このコマンドを実行すると、いつでもトポロジーを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="69c8f-135">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

