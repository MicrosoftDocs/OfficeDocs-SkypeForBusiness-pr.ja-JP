---
title: 'Lync Server 2013: Lync Server サービスのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b193473ad5941c647c572fae1b7cb5e7ece7f95d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-server-services-in-lync-server-2013"></a><span data-ttu-id="69feb-102">Lync server 2013 での Lync Server サービスのテスト</span><span class="sxs-lookup"><span data-stu-id="69feb-102">Testing Lync Server services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69feb-103">_**最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="69feb-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69feb-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="69feb-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="69feb-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="69feb-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69feb-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="69feb-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="69feb-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="69feb-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69feb-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="69feb-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="69feb-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="69feb-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="69feb-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、CsComputer コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="69feb-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsComputer cmdlet.</span></span> <span data-ttu-id="69feb-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="69feb-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="69feb-112">説明</span><span class="sxs-lookup"><span data-stu-id="69feb-112">Description</span></span>

<span data-ttu-id="69feb-113">テスト-CsComputer は、ローカルコンピューターで実行されているすべての Lync Server 2013 サービスの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="69feb-113">Test-CsComputer verifies the status of all the Lync Server 2013 services that are running on the local computer.</span></span> <span data-ttu-id="69feb-114">(Test-CsComputer はローカルでのみ実行できます。 Windows PowerShell のリモートインスタンスから実行することはできません)。このコマンドレットは、コンピューター上で適切なファイアウォールポートが開かれているかどうかを確認し、Lync Server 2013 のインストール時に作成された Active Directory グループが、対応するローカルグループに追加されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="69feb-114">(Test-CsComputer can only be run locally, it cannot be run from a remote instance of Windows PowerShell.) The cmdlet also checks whether the appropriate firewall ports are opened on the computer, and determines whether the Active Directory groups that were created when you installed Lync Server 2013 were added to the corresponding local groups.</span></span> <span data-ttu-id="69feb-115">たとえば、[テスト] コンピューターは、[Active Directory グループ RTCUniversalUserAdmins が管理者グループに追加されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="69feb-115">For example, Test-CsComputer will verify that the Active Directory group RTCUniversalUserAdmins was added to the Administrators group.</span></span>

<span data-ttu-id="69feb-116">詳細については、「 [CsComputer のテスト](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer)」コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="69feb-116">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="69feb-117">テストの実行</span><span class="sxs-lookup"><span data-stu-id="69feb-117">Running the test</span></span>

<span data-ttu-id="69feb-118">テスト用のコンピューターのコマンドレットは、ローカルコンピューターでのみ実行できます。 Windows PowerShell のリモートインスタンスからテスト用コンピューターを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="69feb-118">The Test-CsComputer cmdlet can only be run on the local computer, you can't call Test-CsComputer from a remote instance of Windows PowerShell.</span></span> <span data-ttu-id="69feb-119">既定では、テスト用のコンピューターは画面上に非常に小さな出力を表示します。代わりに、コマンドレットによって返される情報は HTML ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="69feb-119">By default, Test-CsComputer displays very little output on-screen, instead information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="69feb-120">このため、テスト用のコンピューターを実行するときは、必ず Verbose パラメーターと Report パラメーターを含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="69feb-120">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsComputer.</span></span> <span data-ttu-id="69feb-121">Verbose パラメーターは、コマンドレットが実行されている間、画面上により詳細な出力を提供します。</span><span class="sxs-lookup"><span data-stu-id="69feb-121">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="69feb-122">レポートパラメーターを使用すると、CsComputer によって生成された HTML ファイルのファイルパスとファイル名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="69feb-122">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsComputer.</span></span> <span data-ttu-id="69feb-123">レポートパラメーターが含まれていない場合、HTML ファイルは [ユーザー] フォルダーに自動的に保存され、次のような名前が付けられます。 ce84964a-c4da-4622 2-ad34-361f、.html</span><span class="sxs-lookup"><span data-stu-id="69feb-123">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="69feb-124">次の例のコマンドは、テスト用のコンピューターを実行して、出力を C:\\Logs\\computertest .html という名前のファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="69feb-124">The following sample command runs Test-CsComputer and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="69feb-125">詳細については、「 [CsComputer のテスト](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer)」コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="69feb-125">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="69feb-126">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="69feb-126">Determining success or failure</span></span>

<span data-ttu-id="69feb-127">テストによって実行される確認チェックの数が原因で、テストに不合格になった、テストが**成功**した、またはいいえというテストが**失敗**します。</span><span class="sxs-lookup"><span data-stu-id="69feb-127">Because of the number of verification checks that it performs, Test-CsComputer does not report back a simple **Yes, the test succeeded** or **No, the test failed**.</span></span> <span data-ttu-id="69feb-128">代わりに、生成された HTML ファイルを Internet Explorer を使って表示し、各テストの成功または失敗を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69feb-128">Instead, you have to view the generated HTML file by using Internet Explorer to determine the success or failure of each test.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="69feb-129">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="69feb-129">Reasons why the test might have failed</span></span>

<span data-ttu-id="69feb-130">次に、テスト用のコンピューターで障害が発生する一般的な理由をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="69feb-130">Here are some common reasons why Test-CsComputer might fail:</span></span>

  - <span data-ttu-id="69feb-131">テストコンピューターが Lync Server で使用できるようになっていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="69feb-131">The test computer might not be enabled for use with Lync Server.</span></span> <span data-ttu-id="69feb-132">この問題は、コンピューター上の Lync Server サービスまたはサーバーの役割が変更され、かつ、CsComputer コマンドレットが実行されていない場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="69feb-132">This can occur if the Lync Server services or server roles on the computer have changed and the Enable-CsComputer cmdlet was not run.</span></span> <span data-ttu-id="69feb-133">この問題を解決するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="69feb-133">To resolve this issue, run the following command:</span></span>
    
        Enable-CsComputer

  - <span data-ttu-id="69feb-134">テストコンピューターのレプリケーションが最新ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="69feb-134">Replication might not be up to date on the test computer.</span></span> <span data-ttu-id="69feb-135">CsManagementStoreReplicationStatus コマンドレットを実行して、コンピューターの現在のレプリケーションの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="69feb-135">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="69feb-136">レプリケーションの状態が最新でない場合は、次のようなコマンドを使用して、手動でレプリケーションを強制的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="69feb-136">If the replication status is not up to date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="69feb-137">トポロジを有効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="69feb-137">The topology might have to be enabled.</span></span> <span data-ttu-id="69feb-138">Lync Server のトポロジ (ローカルコンピューターに影響を与える可能性のある変更) を変更する場合は、新しいトポロジを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="69feb-138">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="69feb-139">このコマンドを実行すると、いつでもトポロジーを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="69feb-139">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

