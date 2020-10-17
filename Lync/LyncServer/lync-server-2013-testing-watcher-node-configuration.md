---
title: 'Lync Server 2013: 監視ノード構成のテスト'
description: 'Lync Server 2013: 監視ノードの構成をテストしています。'
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
ms.openlocfilehash: f1eeb141eee011d7e06f5dd49e483e026484d733
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546843"
---
# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a><span data-ttu-id="e6511-103">Lync Server 2013 での監視ノード構成のテスト</span><span class="sxs-lookup"><span data-stu-id="e6511-103">Testing watcher node configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6511-104">_**トピックの最終更新日:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="e6511-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6511-105">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="e6511-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e6511-106">毎日</span><span class="sxs-lookup"><span data-stu-id="e6511-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6511-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="e6511-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e6511-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6511-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6511-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e6511-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e6511-110">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6511-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e6511-111">Windows PowerShell のリモートインスタンスを使用して実行する場合は、 <strong>set-cswatchernodeconfiguration</strong> コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6511-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWatcherNodeConfiguration</strong> cmdlet.</span></span> <span data-ttu-id="e6511-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6511-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e6511-113">説明</span><span class="sxs-lookup"><span data-stu-id="e6511-113">Description</span></span>

<span data-ttu-id="e6511-114">Microsoft System Center Operations Manager を使用して Lync Server 2013 を監視している場合は、「監視ノード」を設定することもできます。定期的に、自動的に実行されるコンピューターは、Lync Server が期待どおりに動作していることを確認するために、代理トランザクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6511-114">If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions to verify that Lync Server is working as expected.</span></span> <span data-ttu-id="e6511-115">監視ノードはプールに割り当てられ、 **set-cswatchernodeconfiguration** コマンドレットを使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="e6511-115">Watcher nodes are assigned to pools, and are managed by using the **CsWatcherNodeConfiguration** cmdlets.</span></span> <span data-ttu-id="e6511-116">System Center Operations Manager を使用している場合は、監視ノードをインストールする必要はないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e6511-116">Note that you do not need to install watcher nodes if you are using System Center Operations Manager.</span></span> <span data-ttu-id="e6511-117">監視ノードを使用せずにシステムを監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="e6511-117">You can still monitor your system without using watcher nodes.</span></span> <span data-ttu-id="e6511-118">唯一の違いは、実行する代理トランザクションは、Operations Manager によって自動的に呼び出されるのではなく、手動で起動する必要があることです。</span><span class="sxs-lookup"><span data-stu-id="e6511-118">The only difference is that any synthetic transactions that you want to run must be invoked manually instead of automatically invoked by Operations Manager.</span></span>

<span data-ttu-id="e6511-119">**Set-cswatchernodeconfiguration**コマンドレットを使用すると、監視ノードが正しく構成されており、有効な Lync Server 2013 プールに割り当てられていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e6511-119">The **Test-CsWatcherNodeConfiguration** cmdlet enables you to verify that a watcher node was configured correctly and is assigned to a valid Lync Server 2013 pool.</span></span> <span data-ttu-id="e6511-120">**Set-cswatchernodeconfiguration**コマンドレットは監視ノード自体で実行する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e6511-120">Note that the **Test-CsWatcherNodeConfiguration** cmdlet must be run on the watcher node itself.</span></span> <span data-ttu-id="e6511-121">リモートコンピューターに対してコマンドレットを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="e6511-121">The cmdlet cannot be run against remote computers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e6511-122">テストの実行</span><span class="sxs-lookup"><span data-stu-id="e6511-122">Running the test</span></span>

<span data-ttu-id="e6511-123">次のコマンドは、組織で使用されている各監視ノードの構成設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="e6511-123">The following command verifies the configuration settings for each watcher node that is being used in the organization.</span></span>

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e6511-124">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="e6511-124">Determining success or failure</span></span>

<span data-ttu-id="e6511-125">次の正常なサンプル出力は、エッジサーバーが4台あるシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="e6511-125">The following successful sample output shows a system with four edge servers.</span></span>

<span data-ttu-id="e6511-126">トポロジに対してターゲットプール atl-cs-001.litwareinc.com を検証します。</span><span class="sxs-lookup"><span data-stu-id="e6511-126">Validating target pool atl-cs-001.litwareinc.com against topology.</span></span>

<span data-ttu-id="e6511-127">成功: トポロジにターゲットプール atl-cs-001.litwareinc.com が存在します。</span><span class="sxs-lookup"><span data-stu-id="e6511-127">Success: Target pool atl-cs-001.litwareinc.com exists in topology.</span></span>

<span data-ttu-id="e6511-128">成功: ターゲットプール atl-cs-001.litwareinc.com には、レジストラーの役割がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="e6511-128">Success: Target pool atl-cs-001.litwareinc.com has Registrar role installed.</span></span>

<span data-ttu-id="e6511-129">成功: ターゲットプール atl-cs-001.litwareinc.com がサポートされているバージョンです。</span><span class="sxs-lookup"><span data-stu-id="e6511-129">Success: Target pool atl-cs-001.litwareinc.com is supported version.</span></span>

<span data-ttu-id="e6511-130">成功: 5061 ターゲットプール atl-cs-001.litwareinc.com のポート番号が正しい。</span><span class="sxs-lookup"><span data-stu-id="e6511-130">Success: Port number for 5061 Target pool atl-cs-001.litwareinc.com is correct.</span></span>

<span data-ttu-id="e6511-131">監視ノード構成で不足しているプールの確認が開始されます。</span><span class="sxs-lookup"><span data-stu-id="e6511-131">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="e6511-132">エラーが検出された場合は、出力されます。</span><span class="sxs-lookup"><span data-stu-id="e6511-132">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="e6511-133">監視ノード構成で不足しているプールの確認が完了しました。</span><span class="sxs-lookup"><span data-stu-id="e6511-133">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="e6511-134">監視ノードのインストールによって作成された監視ノードレジストリキーの確認が開始されます。</span><span class="sxs-lookup"><span data-stu-id="e6511-134">Checking for watcher node registry keys created by watcher node installation, is started.</span></span> <span data-ttu-id="e6511-135">エラーが検出された場合は、出力されます。</span><span class="sxs-lookup"><span data-stu-id="e6511-135">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="e6511-136">監視ノードのインストールによって作成された監視ノードレジストリキーの確認が完了しました。</span><span class="sxs-lookup"><span data-stu-id="e6511-136">Checking for watcher node registry keys created by watcher node installation, is finished.</span></span> <span data-ttu-id="e6511-137">検出された認証の種類は Negotiate です。</span><span class="sxs-lookup"><span data-stu-id="e6511-137">Detected authentication type is Negotiate.</span></span>

<span data-ttu-id="e6511-138">テストユーザーの資格情報 sip が存在することが正常に検証されました。資格情報管理ストアで user1@ atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="e6511-138">Successfully validated existence of test user’s credential sip:user1@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="e6511-139">テストユーザーの資格情報 sip が存在することが正常に検証されました。資格情報管理ストアで user2@ atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="e6511-139">Successfully validated existence of test user’s credential sip:user2@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="e6511-140">監視ノード構成で不足しているプールの確認が開始されます。</span><span class="sxs-lookup"><span data-stu-id="e6511-140">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="e6511-141">エラーが検出された場合は、出力されます。</span><span class="sxs-lookup"><span data-stu-id="e6511-141">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="e6511-142">警告: プール atl-cs-001.litwareinc.com にレジストラーがあります</span><span class="sxs-lookup"><span data-stu-id="e6511-142">WARNING: Pool atl-cs-001.litwareinc.com has Registrar</span></span>

<span data-ttu-id="e6511-143">役割がインストールされましたが、それに対して構成されたテストユーザーがありません。</span><span class="sxs-lookup"><span data-stu-id="e6511-143">role installed, but there are no test users configured for it.</span></span>

<span data-ttu-id="e6511-144">監視ノード構成で不足しているプールの確認が完了しました。</span><span class="sxs-lookup"><span data-stu-id="e6511-144">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="e6511-145">監視ノードのインストールによって作成された監視ノードレジストリキーの確認は、</span><span class="sxs-lookup"><span data-stu-id="e6511-145">Checking for watcher node registry keys created by watcher node installation, is</span></span>

<span data-ttu-id="e6511-146">なかっ.</span><span class="sxs-lookup"><span data-stu-id="e6511-146">started.</span></span> <span data-ttu-id="e6511-147">エラーが検出された場合は、出力されます。</span><span class="sxs-lookup"><span data-stu-id="e6511-147">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="e6511-148">Test-CsWatcherNodeConfiguration: で正常性レジストリキーが見つかりません</span><span class="sxs-lookup"><span data-stu-id="e6511-148">Test-CsWatcherNodeConfiguration : Cannot find Health registry key in</span></span>

<span data-ttu-id="e6511-149">ソフトウェア \\ Microsoft \\ のリアルタイムコミュニケーション。</span><span class="sxs-lookup"><span data-stu-id="e6511-149">Software\\Microsoft\\Real-Time Communications.</span></span> <span data-ttu-id="e6511-150">監視ノード .msi がであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e6511-150">Make sure watcher node .msi is</span></span>

<span data-ttu-id="e6511-151">正しくインストールされている。</span><span class="sxs-lookup"><span data-stu-id="e6511-151">installed properly.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e6511-152">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="e6511-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="e6511-153">**Set-cswatchernodeconfiguration**が失敗する可能性のある一般的な原因を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e6511-153">Here are some common reasons why **Test-CsWatcherNodeConfiguration** might fail:</span></span>

  - <span data-ttu-id="e6511-154">監視ノードが正しくインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="e6511-154">Watcher node is not correctly installed.</span></span>

  - <span data-ttu-id="e6511-155">テストユーザーが構成されていません。</span><span class="sxs-lookup"><span data-stu-id="e6511-155">No test users are configured.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e6511-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6511-156">See Also</span></span>


[<span data-ttu-id="e6511-157">Set-cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="e6511-157">Get-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[<span data-ttu-id="e6511-158">Set-cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="e6511-158">New-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[<span data-ttu-id="e6511-159">Set-cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="e6511-159">Remove-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[<span data-ttu-id="e6511-160">Set-cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="e6511-160">Set-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

