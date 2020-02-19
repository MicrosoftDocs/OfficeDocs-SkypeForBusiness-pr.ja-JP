---
title: 'Lync Server 2013: 監視ノード構成のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53780a34ea3dec6d0ae742333d5f3ce911ac71bb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a><span data-ttu-id="9aed4-102">Lync Server 2013 での監視ノード構成のテスト</span><span class="sxs-lookup"><span data-stu-id="9aed4-102">Testing watcher node configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9aed4-103">_**トピックの最終更新日:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="9aed4-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9aed4-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="9aed4-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9aed4-105">毎日</span><span class="sxs-lookup"><span data-stu-id="9aed4-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9aed4-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="9aed4-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9aed4-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9aed4-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9aed4-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="9aed4-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9aed4-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9aed4-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9aed4-110">Windows PowerShell のリモートインスタンスを使用して実行する場合は、 <strong>set-cswatchernodeconfiguration</strong>コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9aed4-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWatcherNodeConfiguration</strong> cmdlet.</span></span> <span data-ttu-id="9aed4-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9aed4-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9aed4-112">説明</span><span class="sxs-lookup"><span data-stu-id="9aed4-112">Description</span></span>

<span data-ttu-id="9aed4-113">Microsoft System Center Operations Manager を使用して Lync Server 2013 を監視している場合は、「監視ノード」を設定することもできます。コンピューターが定期的かつ自動的に実行している場合は、Lync Server が次のものとして動作していることを確認するために、代理トランザクションを実行します。れる.</span><span class="sxs-lookup"><span data-stu-id="9aed4-113">If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions to verify that Lync Server is working as expected.</span></span> <span data-ttu-id="9aed4-114">監視ノードはプールに割り当てられ、 **set-cswatchernodeconfiguration**コマンドレットを使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="9aed4-114">Watcher nodes are assigned to pools, and are managed by using the **CsWatcherNodeConfiguration** cmdlets.</span></span> <span data-ttu-id="9aed4-115">System Center Operations Manager を使用している場合は、監視ノードをインストールする必要はないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9aed4-115">Note that you do not need to install watcher nodes if you are using System Center Operations Manager.</span></span> <span data-ttu-id="9aed4-116">監視ノードを使用せずにシステムを監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="9aed4-116">You can still monitor your system without using watcher nodes.</span></span> <span data-ttu-id="9aed4-117">唯一の違いは、実行する代理トランザクションは、Operations Manager によって自動的に呼び出されるのではなく、手動で起動する必要があることです。</span><span class="sxs-lookup"><span data-stu-id="9aed4-117">The only difference is that any synthetic transactions that you want to run must be invoked manually instead of automatically invoked by Operations Manager.</span></span>

<span data-ttu-id="9aed4-118">**Set-cswatchernodeconfiguration**コマンドレットを使用すると、監視ノードが正しく構成されており、有効な Lync Server 2013 プールに割り当てられていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="9aed4-118">The **Test-CsWatcherNodeConfiguration** cmdlet enables you to verify that a watcher node was configured correctly and is assigned to a valid Lync Server 2013 pool.</span></span> <span data-ttu-id="9aed4-119">**Set-cswatchernodeconfiguration**コマンドレットは監視ノード自体で実行する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9aed4-119">Note that the **Test-CsWatcherNodeConfiguration** cmdlet must be run on the watcher node itself.</span></span> <span data-ttu-id="9aed4-120">リモートコンピューターに対してコマンドレットを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="9aed4-120">The cmdlet cannot be run against remote computers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9aed4-121">テストの実行</span><span class="sxs-lookup"><span data-stu-id="9aed4-121">Running the test</span></span>

<span data-ttu-id="9aed4-122">次のコマンドは、組織で使用されている各監視ノードの構成設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="9aed4-122">The following command verifies the configuration settings for each watcher node that is being used in the organization.</span></span>

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9aed4-123">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="9aed4-123">Determining success or failure</span></span>

<span data-ttu-id="9aed4-124">次の正常なサンプル出力は、エッジサーバーが4台あるシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="9aed4-124">The following successful sample output shows a system with four edge servers.</span></span>

<span data-ttu-id="9aed4-125">トポロジに対してターゲットプール atl-cs-001.litwareinc.com を検証します。</span><span class="sxs-lookup"><span data-stu-id="9aed4-125">Validating target pool atl-cs-001.litwareinc.com against topology.</span></span>

<span data-ttu-id="9aed4-126">成功: トポロジにターゲットプール atl-cs-001.litwareinc.com が存在します。</span><span class="sxs-lookup"><span data-stu-id="9aed4-126">Success: Target pool atl-cs-001.litwareinc.com exists in topology.</span></span>

<span data-ttu-id="9aed4-127">成功: ターゲットプール atl-cs-001.litwareinc.com には、レジストラーの役割がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="9aed4-127">Success: Target pool atl-cs-001.litwareinc.com has Registrar role installed.</span></span>

<span data-ttu-id="9aed4-128">成功: ターゲットプール atl-cs-001.litwareinc.com がサポートされているバージョンです。</span><span class="sxs-lookup"><span data-stu-id="9aed4-128">Success: Target pool atl-cs-001.litwareinc.com is supported version.</span></span>

<span data-ttu-id="9aed4-129">成功: 5061 ターゲットプール atl-cs-001.litwareinc.com のポート番号が正しい。</span><span class="sxs-lookup"><span data-stu-id="9aed4-129">Success: Port number for 5061 Target pool atl-cs-001.litwareinc.com is correct.</span></span>

<span data-ttu-id="9aed4-130">監視ノード構成で不足しているプールの確認が開始されます。</span><span class="sxs-lookup"><span data-stu-id="9aed4-130">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="9aed4-131">エラーが検出された場合は、出力されます。</span><span class="sxs-lookup"><span data-stu-id="9aed4-131">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="9aed4-132">監視ノード構成で不足しているプールの確認が完了しました。</span><span class="sxs-lookup"><span data-stu-id="9aed4-132">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="9aed4-133">監視ノードのインストールによって作成された監視ノードレジストリキーの確認が開始されます。</span><span class="sxs-lookup"><span data-stu-id="9aed4-133">Checking for watcher node registry keys created by watcher node installation, is started.</span></span> <span data-ttu-id="9aed4-134">エラーが検出された場合は、出力されます。</span><span class="sxs-lookup"><span data-stu-id="9aed4-134">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="9aed4-135">監視ノードのインストールによって作成された監視ノードレジストリキーの確認が完了しました。</span><span class="sxs-lookup"><span data-stu-id="9aed4-135">Checking for watcher node registry keys created by watcher node installation, is finished.</span></span> <span data-ttu-id="9aed4-136">検出された認証の種類は Negotiate です。</span><span class="sxs-lookup"><span data-stu-id="9aed4-136">Detected authentication type is Negotiate.</span></span>

<span data-ttu-id="9aed4-137">テストユーザーの資格情報 sip が存在することが正常に検証されました。資格情報管理ストアで user1@ atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="9aed4-137">Successfully validated existence of test user’s credential sip:user1@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="9aed4-138">テストユーザーの資格情報 sip が存在することが正常に検証されました。資格情報管理ストアで user2@ atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="9aed4-138">Successfully validated existence of test user’s credential sip:user2@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="9aed4-139">監視ノード構成で不足しているプールの確認が開始されます。</span><span class="sxs-lookup"><span data-stu-id="9aed4-139">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="9aed4-140">エラーが検出された場合は、出力されます。</span><span class="sxs-lookup"><span data-stu-id="9aed4-140">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="9aed4-141">警告: プール atl-cs-001.litwareinc.com にレジストラーがあります</span><span class="sxs-lookup"><span data-stu-id="9aed4-141">WARNING: Pool atl-cs-001.litwareinc.com has Registrar</span></span>

<span data-ttu-id="9aed4-142">役割がインストールされましたが、それに対して構成されたテストユーザーがありません。</span><span class="sxs-lookup"><span data-stu-id="9aed4-142">role installed, but there are no test users configured for it.</span></span>

<span data-ttu-id="9aed4-143">監視ノード構成で不足しているプールの確認が完了しました。</span><span class="sxs-lookup"><span data-stu-id="9aed4-143">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="9aed4-144">監視ノードのインストールによって作成された監視ノードレジストリキーの確認は、</span><span class="sxs-lookup"><span data-stu-id="9aed4-144">Checking for watcher node registry keys created by watcher node installation, is</span></span>

<span data-ttu-id="9aed4-145">なかっ.</span><span class="sxs-lookup"><span data-stu-id="9aed4-145">started.</span></span> <span data-ttu-id="9aed4-146">エラーが検出された場合は、出力されます。</span><span class="sxs-lookup"><span data-stu-id="9aed4-146">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="9aed4-147">Set-cswatchernodeconfiguration: で正常性レジストリキーが見つかりません</span><span class="sxs-lookup"><span data-stu-id="9aed4-147">Test-CsWatcherNodeConfiguration : Cannot find Health registry key in</span></span>

<span data-ttu-id="9aed4-148">ソフトウェア\\Microsoft\\のリアルタイムコミュニケーション。</span><span class="sxs-lookup"><span data-stu-id="9aed4-148">Software\\Microsoft\\Real-Time Communications.</span></span> <span data-ttu-id="9aed4-149">監視ノード .msi がであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9aed4-149">Make sure watcher node .msi is</span></span>

<span data-ttu-id="9aed4-150">正しくインストールされている。</span><span class="sxs-lookup"><span data-stu-id="9aed4-150">installed properly.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9aed4-151">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="9aed4-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="9aed4-152">**Set-cswatchernodeconfiguration**が失敗する可能性のある一般的な原因を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9aed4-152">Here are some common reasons why **Test-CsWatcherNodeConfiguration** might fail:</span></span>

  - <span data-ttu-id="9aed4-153">監視ノードが正しくインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="9aed4-153">Watcher node is not correctly installed.</span></span>

  - <span data-ttu-id="9aed4-154">テストユーザーが構成されていません。</span><span class="sxs-lookup"><span data-stu-id="9aed4-154">No test users are configured.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9aed4-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="9aed4-155">See Also</span></span>


[<span data-ttu-id="9aed4-156">Set-cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="9aed4-156">Get-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[<span data-ttu-id="9aed4-157">Set-cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="9aed4-157">New-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[<span data-ttu-id="9aed4-158">Set-cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="9aed4-158">Remove-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[<span data-ttu-id="9aed4-159">Set-cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="9aed4-159">Set-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

