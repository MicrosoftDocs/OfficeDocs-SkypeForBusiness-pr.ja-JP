---
title: 'Lync Server 2013: Lync Server サービスのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd9f2924d2f66e27e3893ccca0502915ee8a3e97
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-server-services-in-lync-server-2013"></a><span data-ttu-id="78bb6-102">Lync server 2013 での Lync Server サービスのテスト</span><span class="sxs-lookup"><span data-stu-id="78bb6-102">Testing Lync Server services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78bb6-103">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="78bb6-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78bb6-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="78bb6-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="78bb6-105">毎日</span><span class="sxs-lookup"><span data-stu-id="78bb6-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78bb6-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="78bb6-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="78bb6-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="78bb6-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78bb6-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="78bb6-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="78bb6-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="78bb6-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="78bb6-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テスト用のコンピューターコマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="78bb6-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsComputer cmdlet.</span></span> <span data-ttu-id="78bb6-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="78bb6-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="78bb6-112">説明</span><span class="sxs-lookup"><span data-stu-id="78bb6-112">Description</span></span>

<span data-ttu-id="78bb6-113">テスト-CsComputer は、ローカルコンピューター上で実行されているすべての Lync Server 2013 サービスの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="78bb6-113">Test-CsComputer verifies the status of all the Lync Server 2013 services that are running on the local computer.</span></span> <span data-ttu-id="78bb6-114">(Test-CsComputer はローカルでのみ実行できますが、Windows PowerShell のリモートインスタンスからは実行できません)。また、このコマンドレットは、コンピューター上で適切なファイアウォールポートが開かれているかどうかを確認し、Lync Server 2013 のインストール時に作成された Active Directory グループが対応するローカルグループに追加されたかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="78bb6-114">(Test-CsComputer can only be run locally, it cannot be run from a remote instance of Windows PowerShell.) The cmdlet also checks whether the appropriate firewall ports are opened on the computer, and determines whether the Active Directory groups that were created when you installed Lync Server 2013 were added to the corresponding local groups.</span></span> <span data-ttu-id="78bb6-115">たとえば、Test-CsComputer は、Active Directory グループ RTCUniversalUserAdmins が Administrators グループに追加されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="78bb6-115">For example, Test-CsComputer will verify that the Active Directory group RTCUniversalUserAdmins was added to the Administrators group.</span></span>

<span data-ttu-id="78bb6-116">詳細については、「 [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78bb6-116">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="78bb6-117">テストの実行</span><span class="sxs-lookup"><span data-stu-id="78bb6-117">Running the test</span></span>

<span data-ttu-id="78bb6-118">Test-CsComputer コマンドレットは、ローカルコンピューターでのみ実行できます。 Windows PowerShell のリモートインスタンスからテスト用コンピューターを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="78bb6-118">The Test-CsComputer cmdlet can only be run on the local computer, you can't call Test-CsComputer from a remote instance of Windows PowerShell.</span></span> <span data-ttu-id="78bb6-119">既定では、テスト用のコンピューターで画面に表示される出力は少なく、代わりにコマンドレットから返された情報が HTML ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="78bb6-119">By default, Test-CsComputer displays very little output on-screen, instead information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="78bb6-120">そのため、Test CsComputer を実行するたびに、Verbose パラメーターと Report パラメーターを含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="78bb6-120">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsComputer.</span></span> <span data-ttu-id="78bb6-121">Verbose パラメーターは、コマンドレットの実行中に画面により詳細な出力を提供します。</span><span class="sxs-lookup"><span data-stu-id="78bb6-121">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="78bb6-122">Report パラメーターを使用すると、Test CsComputer で生成された HTML ファイルのファイルパスとファイル名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="78bb6-122">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsComputer.</span></span> <span data-ttu-id="78bb6-123">Report パラメーターを指定しない場合は、HTML ファイルは自動的にユーザーのフォルダーに保存され、次のような名前が付けられます。 ce84964a-c4da-c4da-4622 2-ad34-c54ff3ed361f .html。</span><span class="sxs-lookup"><span data-stu-id="78bb6-123">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="78bb6-124">次のサンプルコマンドは、Test-CsComputer を実行し、出力を C:\\Logs\\computertest .html という名前のファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="78bb6-124">The following sample command runs Test-CsComputer and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="78bb6-125">詳細については、「 [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78bb6-125">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="78bb6-126">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="78bb6-126">Determining success or failure</span></span>

<span data-ttu-id="78bb6-127">テストが成功したかどうかについては、確認のチェックの数が多くなるため、テストが**成功**したかどうかについては、テストに**失敗しました**。</span><span class="sxs-lookup"><span data-stu-id="78bb6-127">Because of the number of verification checks that it performs, Test-CsComputer does not report back a simple **Yes, the test succeeded** or **No, the test failed**.</span></span> <span data-ttu-id="78bb6-128">代わりに、生成された HTML ファイルを表示するには、Internet Explorer を使用して、各テストの成功または失敗を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78bb6-128">Instead, you have to view the generated HTML file by using Internet Explorer to determine the success or failure of each test.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="78bb6-129">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="78bb6-129">Reasons why the test might have failed</span></span>

<span data-ttu-id="78bb6-130">テスト用のコンピューターで障害が発生する主な理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="78bb6-130">Here are some common reasons why Test-CsComputer might fail:</span></span>

  - <span data-ttu-id="78bb6-131">テストコンピューターが Lync Server で使用可能になっていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="78bb6-131">The test computer might not be enabled for use with Lync Server.</span></span> <span data-ttu-id="78bb6-132">これは、コンピューター上の Lync Server サービスまたはサーバーの役割が変更されていて、CsComputer コマンドレットが実行されていなかった場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="78bb6-132">This can occur if the Lync Server services or server roles on the computer have changed and the Enable-CsComputer cmdlet was not run.</span></span> <span data-ttu-id="78bb6-133">この問題を解決するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="78bb6-133">To resolve this issue, run the following command:</span></span>
    
        Enable-CsComputer

  - <span data-ttu-id="78bb6-134">テストコンピューターでレプリケーションが最新の状態になっていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="78bb6-134">Replication might not be up to date on the test computer.</span></span> <span data-ttu-id="78bb6-135">Get-csmanagementstorereplicationstatus コマンドレットを実行して、コンピューターの現在のレプリケーションの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="78bb6-135">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="78bb6-136">レプリケーションの状態が最新ではない場合は、次のようなコマンドを使用して、レプリケーションを手動で強制的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="78bb6-136">If the replication status is not up to date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="78bb6-137">トポロジを有効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="78bb6-137">The topology might have to be enabled.</span></span> <span data-ttu-id="78bb6-138">Lync Server トポロジ (ローカルコンピューターに影響する可能性がある変更) を変更する場合は、新しいトポロジを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="78bb6-138">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="78bb6-139">次のコマンドを実行することによって、いつでもトポロジを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="78bb6-139">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

