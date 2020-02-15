---
title: 'Lync Server 2013: サービスのアクティブ化とグループのアクセス許可のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8df9373088e29259ff95de1342000446d0d43d5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a><span data-ttu-id="75bd9-102">Lync Server 2013 でのサービスのアクティブ化とグループのアクセス許可のテスト</span><span class="sxs-lookup"><span data-stu-id="75bd9-102">Testing service activation and group permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75bd9-103">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="75bd9-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75bd9-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="75bd9-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="75bd9-105">毎日</span><span class="sxs-lookup"><span data-stu-id="75bd9-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75bd9-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="75bd9-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="75bd9-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="75bd9-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75bd9-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="75bd9-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="75bd9-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="75bd9-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="75bd9-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テストコマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="75bd9-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTopology cmdlet.</span></span> <span data-ttu-id="75bd9-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="75bd9-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="75bd9-112">説明</span><span class="sxs-lookup"><span data-stu-id="75bd9-112">Description</span></span>

<span data-ttu-id="75bd9-113">Test-CsTopology コマンドレットを使用すると、Lync Server 2013 がグローバルスコープで正常に機能していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="75bd9-113">The Test-CsTopology cmdlet enables you to verify that Lync Server 2013 is functioning correctly at a global scope.</span></span> <span data-ttu-id="75bd9-114">既定では、このコマンドレットは Lync Server インフラストラクチャ全体をチェックし、必要なサービスが実行されていること、およびこれらのサービスに対して適切なアクセス許可が設定されていることと、Lync Server のインストール時に作成されたユニバーサルセキュリティグループに対して適切なアクセス許可が設定されている.</span><span class="sxs-lookup"><span data-stu-id="75bd9-114">By default, the cmdlet checks your whole Lync Server infrastructure, verifying that the required services are running and that the appropriate permissions are set for these services and for the universal security groups that are created when you install Lync Server.</span></span>

<span data-ttu-id="75bd9-115">Lync Server のインストールの有効性を検証するだけでなく、特定のサービスの有効性を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="75bd9-115">In addition to verifying the validity of the Lync Server installation, Test-CsTopology also lets you check the validity of a specific service.</span></span> <span data-ttu-id="75bd9-116">たとえば、次のコマンドは、プール atl-cs-001.litwareinc.com 上の音声ビデオ会議サーバーの状態をチェックします。</span><span class="sxs-lookup"><span data-stu-id="75bd9-116">For example, this command checks the state of the A/V Conferencing Server on the pool atl-cs-001.litwareinc.com:</span></span>

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="75bd9-117">テストの実行</span><span class="sxs-lookup"><span data-stu-id="75bd9-117">Running the test</span></span>

<span data-ttu-id="75bd9-118">既定では、テスト用の出力画面に表示される出力はほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="75bd9-118">By default, Test-CsTopology displays very little output on-screen.</span></span> <span data-ttu-id="75bd9-119">代わりに、コマンドレットによって返される情報は、HTML ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="75bd9-119">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="75bd9-120">Report パラメーターを使用すると、テスト用の HTML ファイルのファイルパスとファイル名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="75bd9-120">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsTopology.</span></span> <span data-ttu-id="75bd9-121">Report パラメーターを指定しない場合は、HTML ファイルは自動的にユーザーのフォルダーに保存され、次のような名前が付けられます。 ce84964a-c4da-c4da-4622 2-ad34-c54ff3ed361f .html。</span><span class="sxs-lookup"><span data-stu-id="75bd9-121">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="75bd9-122">次のサンプルコマンドは、テスト-CsTopology 使い方を実行し、出力を C:\\Logs\\computertest .html という名前のファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="75bd9-122">The following sample command runs Test-CsTopology and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="75bd9-123">詳細については、[テスト](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology)用のヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="75bd9-123">For more information, see the Help documentation for the [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="75bd9-124">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="75bd9-124">Determining success or failure</span></span>

<span data-ttu-id="75bd9-125">Test コマンドレットは、ほとんどのテストコマンドレットとは異なり、成功または失敗の報告を返します。</span><span class="sxs-lookup"><span data-stu-id="75bd9-125">Unlike most of the test cmdlets, Test-CsTopology does report back Success or Failure.</span></span> <span data-ttu-id="75bd9-126">これは、コマンドレットが実行されるたびに実行する必要のある多くの検証チェックが行われるためです。</span><span class="sxs-lookup"><span data-stu-id="75bd9-126">In part, that’s due to the large number of verification checks that the cmdlet must make every time that it runs.</span></span> <span data-ttu-id="75bd9-127">代わりに、Internet Explorer を使用して表示できる HTML レポートにデータが保存されます。</span><span class="sxs-lookup"><span data-stu-id="75bd9-127">Instead, data is saved to an HTML report that can then be viewed by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="75bd9-128">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="75bd9-128">Reasons why the test might have failed</span></span>

<span data-ttu-id="75bd9-129">テスト-Cstopostoが失敗する主な理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="75bd9-129">Here are some common reasons why Test-CsTopology might fail:</span></span>

  - <span data-ttu-id="75bd9-130">テストコンピューターでレプリケーションが最新の状態ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="75bd9-130">Replication might not be up-to-date on the test computer.</span></span> <span data-ttu-id="75bd9-131">Get-csmanagementstorereplicationstatus コマンドレットを実行して、コンピューターの現在のレプリケーションの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="75bd9-131">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="75bd9-132">レプリケーションの状態が最新ではない場合は、次のようなコマンドを使用して、レプリケーションを手動で強制的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="75bd9-132">If the replication status is not up-to-date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="75bd9-133">トポロジを有効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="75bd9-133">The topology might have to be enabled.</span></span> <span data-ttu-id="75bd9-134">Lync Server トポロジ (ローカルコンピューターに影響する可能性がある変更) を変更する場合は、新しいトポロジを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="75bd9-134">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="75bd9-135">次のコマンドを実行することによって、いつでもトポロジを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="75bd9-135">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

