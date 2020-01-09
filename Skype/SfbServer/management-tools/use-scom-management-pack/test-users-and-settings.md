---
title: 監視ノードのテスト ユーザーおよび設定の構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: '概要: Skype for Business Server の代理トランザクションのテストユーザーアカウントとウォッチャーノード設定を構成します。'
ms.openlocfilehash: 3aa711e9da588b6843f7e31940e15772b1376084
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992454"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="249f9-103">監視ノードのテスト ユーザーおよび設定の構成</span><span class="sxs-lookup"><span data-stu-id="249f9-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="249f9-104">**概要:** Skype for Business Server の代理トランザクションのテストユーザーアカウントとウォッチャーノード設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="249f9-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="249f9-105">監視ノードとして動作するコンピューターを構成したら、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="249f9-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="249f9-106">これらのウォッチャーノードによって使用される[テストユーザーアカウントを構成](test-users-and-settings.md#testuser)します。</span><span class="sxs-lookup"><span data-stu-id="249f9-106">[Configure Test User Accounts](test-users-and-settings.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="249f9-107">Negotiate の認証方法を使用している場合は、**Set-CsTestUserCredential** コマンドレットを使用し、監視ノードで使用するためにこれらのテスト アカウントを有効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="249f9-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="249f9-108">監視ノード構成設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="249f9-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="249f9-109">テスト ユーザー アカウントの構成</span><span class="sxs-lookup"><span data-stu-id="249f9-109">Configure Test User Accounts</span></span>
<span data-ttu-id="249f9-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="249f9-110"></span></span>

<span data-ttu-id="249f9-111">テストアカウントは、実際のユーザーを表す必要はありませんが、有効な Active Directory アカウントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="249f9-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="249f9-112">また、これらのアカウントは、Skype for Business Server で有効にしておく必要があります。また、有効な SIP アドレスが必要であり、エンタープライズ Voip に対して有効になっている必要があります (テスト-CsPstnPeerToPeerCall 代理トランザクションを使う場合)。</span><span class="sxs-lookup"><span data-stu-id="249f9-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="249f9-113">TrustedServer の認証方法を使用している場合に実行する必要があるのは、これらのアカウントが存在していることを確認し、説明に従って構成することのみです。</span><span class="sxs-lookup"><span data-stu-id="249f9-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="249f9-114">テスト対象の各プールについて、少なくとも2つのテストユーザーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="249f9-114">You should assign at least two test users for each pool that you want to test.</span></span> <span data-ttu-id="249f9-115">Negotiate 認証方法を使用している場合は、CsTestUserCredential コマンドレットと Skype for Business Server の管理シェルも使用して、これらのテストアカウントで代理トランザクションを操作できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="249f9-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="249f9-116">この操作を実行するには、次のようなコマンドを実行します (これらのコマンドは、2つの Active Directory ユーザーアカウントが作成され、これらのアカウントが Skype for Business Server に対して有効になっていることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="249f9-116">Do this by running a command similar to the following (these commands assume that the two Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

<span data-ttu-id="249f9-p104">SIP アドレスだけでなくユーザー名とパスワードも含める必要があります。パスワードを含めない場合は、Set-CsTestUserCredential コマンドレットを実行したときに、この情報の入力が求められます。ユーザー名は、上記のコード ブロックのようにドメイン名\ユーザー名の形式を使用して指定できます。</span><span class="sxs-lookup"><span data-stu-id="249f9-p104">You must include not only the SIP address, but also the user name and password. If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information. The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="249f9-120">テストユーザーの資格情報が作成されたことを確認するには、Skype for Business Server 管理シェルから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="249f9-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

<span data-ttu-id="249f9-121">次のような情報が各ユーザーに返されます。</span><span class="sxs-lookup"><span data-stu-id="249f9-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="249f9-122">**Chap**</span><span class="sxs-lookup"><span data-stu-id="249f9-122">**UserName**</span></span>|<span data-ttu-id="249f9-123">**パスワード**</span><span class="sxs-lookup"><span data-stu-id="249f9-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="249f9-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="249f9-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="249f9-125">「</span><span class="sxs-lookup"><span data-stu-id="249f9-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="249f9-126">既定の代理トランザクションを使用した基本的な監視ノードの構成</span><span class="sxs-lookup"><span data-stu-id="249f9-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="249f9-127">テスト ユーザーが作成されたら、次のようなコマンドを使用して監視ノードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="249f9-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

<span data-ttu-id="249f9-128">このコマンドでは、既定の設定を使用し、既定の代理トランザクションのセットを実行する新しい監視ノードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="249f9-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="249f9-129">新しいウォッチャーノードでは、テストユーザー watcher1@litwareinc.com と watcher2@litwareinc.com も使用されます。</span><span class="sxs-lookup"><span data-stu-id="249f9-129">The new watcher node also uses the test users watcher1@litwareinc.com, and watcher2@litwareinc.com.</span></span> <span data-ttu-id="249f9-130">ウォッチャーノードが TrustedServer 認証を使用している場合は、2つのテストアカウントで Active Directory と Skype for Business Server に対して有効なユーザーアカウントを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="249f9-130">If the watcher node uses TrustedServer authentication, the two test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="249f9-131">監視ノードが Negotiate 認証方法を使用している場合は、Set-CsTestUserCredential コマンドレットを使用してこれらのユーザー アカウントを監視ノードで有効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="249f9-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="249f9-132">これらのステップでプールを直接ターゲット指定する代わりに、サインインするターゲット プールの自動検出が正しく構成されていることを確認するには</span><span class="sxs-lookup"><span data-stu-id="249f9-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="249f9-133">拡張テストの構成</span><span class="sxs-lookup"><span data-stu-id="249f9-133">Configuring Extended Tests</span></span>

<span data-ttu-id="249f9-p106">公衆交換電話網との接続を検証する公衆交換電話網 (PSTN) テストを有効にする場合、監視ノードのセットアップ時に追加の構成を行う必要があります。最初に、テスト ユーザーを PSTN のテストの種類に関連付ける必要があります。これを行うには、Skype for Business Server 管理シェルから次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="249f9-p106">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node. First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="249f9-p107">このコマンドの結果は変数に格納する必要があります。この例では、$pstnTest という名前の変数です。</span><span class="sxs-lookup"><span data-stu-id="249f9-p107">The results of this command must be stored in a variable. In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="249f9-138">次に、 **CsWatcherNodeConfiguration**コマンドレットを使用して、テストの種類 (可変 $pstnTest) を Skype For business Server プールに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="249f9-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="249f9-139">たとえば、次のコマンドは、プール atl-cs-001.litwareinc.com の新しいウォッチャーノード構成を作成し、前に作成した2つのテストユーザーを追加して、PSTN テストの種類を追加します。</span><span class="sxs-lookup"><span data-stu-id="249f9-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the two test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="249f9-140">Skype for Business Server の中核となるファイルと RTCLocal データベースを監視ノード コンピューターにインストールしていない場合、上記のコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="249f9-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="249f9-p109">複数の音声ポリシーをテストするには、**New-CsExtendedTest** コマンドレットを使用して各ポリシーに拡張テストを作成する必要があります。このテストに割り当てられたユーザーは、目的の音声ポリシーを使用して構成する必要があります。次のようなコマンドを使用すると、拡張テストは **New-CsWatcherNodeConfiguration** コマンドレットに渡されます。</span><span class="sxs-lookup"><span data-stu-id="249f9-p109">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet. The users provided should be configured with the desired voice policies. The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="249f9-144">-ExtendedTests @ {Add = $pstnTest 1、$pstnTest 2、$pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="249f9-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="249f9-p110">Tests パラメーターを使用しないで **New-CsWatcherNodeConfiguration** コマンドレットを呼び出す場合、既定の代理トランザクション (および指定された拡張代理トランザクション) のみが新しい監視ノードで有効になります。このため、監視ノードは次のコンポーネントをテストします。</span><span class="sxs-lookup"><span data-stu-id="249f9-p110">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node. Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="249f9-147">Registration</span><span class="sxs-lookup"><span data-stu-id="249f9-147">Registration</span></span>
    
- <span data-ttu-id="249f9-148">IM</span><span class="sxs-lookup"><span data-stu-id="249f9-148">IM</span></span>
    
- <span data-ttu-id="249f9-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="249f9-149">GroupIM</span></span>
    
- <span data-ttu-id="249f9-150">P2PAV (ピアツーピアの音声/ビデオ セッション)</span><span class="sxs-lookup"><span data-stu-id="249f9-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="249f9-151">AvConference (音声/会議)</span><span class="sxs-lookup"><span data-stu-id="249f9-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="249f9-152">Presence</span><span class="sxs-lookup"><span data-stu-id="249f9-152">Presence</span></span>
    
- <span data-ttu-id="249f9-153">ABS (アドレス帳サービス)</span><span class="sxs-lookup"><span data-stu-id="249f9-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="249f9-154">ABWQ (アドレス帳 Web サービス)</span><span class="sxs-lookup"><span data-stu-id="249f9-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="249f9-155">また、次のコンポーネントは既定ではテストされません。</span><span class="sxs-lookup"><span data-stu-id="249f9-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="249f9-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="249f9-156">ASConference</span></span>
    
- <span data-ttu-id="249f9-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="249f9-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="249f9-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="249f9-158">DataConference</span></span>
    
- <span data-ttu-id="249f9-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="249f9-159">DialinConferencing</span></span>
    
- <span data-ttu-id="249f9-160">ExumConnectivity (Exchange ユニファイド メッセージング)</span><span class="sxs-lookup"><span data-stu-id="249f9-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="249f9-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="249f9-161">JoinLauncher</span></span>
    
- <span data-ttu-id="249f9-162">MCXP2PIM (従来のモバイルデバイスのインスタントメッセージング)</span><span class="sxs-lookup"><span data-stu-id="249f9-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="249f9-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="249f9-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="249f9-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="249f9-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="249f9-165">PSTN (拡張テストとして指定された PSTN ゲートウェイ通話)</span><span class="sxs-lookup"><span data-stu-id="249f9-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="249f9-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="249f9-166">UcwaConference</span></span>
    
- <span data-ttu-id="249f9-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="249f9-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="249f9-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="249f9-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="249f9-169">代理トランザクションの追加と削除</span><span class="sxs-lookup"><span data-stu-id="249f9-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="249f9-p111">監視ノードを構成した後は、Set-CsWatcherNodeConfiguration コマンドレットを使用してノードから代理トランザクションを追加または削除できます。たとえば、監視ノードに PersistentChatMessage テストを追加するには Add メソッドと次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="249f9-p111">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node. For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="249f9-p112">テスト名をコンマで区切ることにより、複数のテストを追加することができます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="249f9-p112">Multiple tests can be added by separating the test names by using commas. For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="249f9-p113">これらのテストの 1 つまたは複数 (たとえば DataConference) が既に監視ノードで有効になっていた場合、エラーが発生します。この場合、次のようなエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="249f9-p113">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node. In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="249f9-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span><span class="sxs-lookup"><span data-stu-id="249f9-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="249f9-177">このエラーが発生した場合、変更は一切適用されません。</span><span class="sxs-lookup"><span data-stu-id="249f9-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="249f9-178">重複するテストを削除してコマンドを再実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="249f9-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="249f9-p115">監視ノードから代理トランザクションを削除するには、Remove メソッドを使用します。たとえば、次のコマンドでは、監視ノードから ABWQ テストを削除します。</span><span class="sxs-lookup"><span data-stu-id="249f9-p115">To remove a synthetic transaction from a watcher node, use the Remove method. For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="249f9-p116">また、Replace メソッドを使用すると、現在有効になっているすべてのテストを 1 つ以上の新しいテストに置き換えることができます。たとえば、1 つの監視ノードが IM テストを実行するようにする場合、次のコマンドを使用してこれを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="249f9-p116">You can use the Replace method to replace all the currently-enabled tests with one or more new tests. For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="249f9-183">上記のコマンドを実行する場合、指定された監視ノードのすべての代理トランザクションでは IM 以外無効になります。</span><span class="sxs-lookup"><span data-stu-id="249f9-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="249f9-184">監視ノード構成の表示とテスト</span><span class="sxs-lookup"><span data-stu-id="249f9-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="249f9-185">監視ノードに割り当てられているテストを表示する場合は、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="249f9-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="249f9-186">上記のコマンドは、ノードに割り当てられている代理トランザクションに応じて次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="249f9-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="249f9-187">登録 IM GroupIM AvConference プレゼンス PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="249f9-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="249f9-188">代理トランザクションをアルファベット順で表示するには、代わりに次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="249f9-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="249f9-189">監視ノードが作成されていることを確認するには、Skype for Business Server 管理シェルから次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="249f9-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="249f9-190">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="249f9-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="249f9-191">Id: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="249f9-191">Identity : atl-cs-001.litwareinc.com</span></span> <br/>
<span data-ttu-id="249f9-192">TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...}</span><span class="sxs-lookup"><span data-stu-id="249f9-192">TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span><br/>
<span data-ttu-id="249f9-193">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span><span class="sxs-lookup"><span data-stu-id="249f9-193">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span><br/>
<span data-ttu-id="249f9-194">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="249f9-194">TargetFqdn : atl-cs-001.litwareinc.com</span></span><br/>
<span data-ttu-id="249f9-195">ポート番号: 5061</span><span class="sxs-lookup"><span data-stu-id="249f9-195">PortNumber : 5061</span></span><br/>

<span data-ttu-id="249f9-196">監視ノードが正しく構成されていることを確認するには、Skype for Business Server 管理シェルから次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="249f9-196">To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="249f9-197">上記のコマンドでは、展開内の監視ノードをそれぞれテストし、次のような情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="249f9-197">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="249f9-198">必要なレジストラー役割がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="249f9-198">The required Registrar role is installed.</span></span>
    
- <span data-ttu-id="249f9-199">必要なレジストリキーが作成されます (CsWatcherNodeConfiguration コマンドレットを実行すると完了します)。</span><span class="sxs-lookup"><span data-stu-id="249f9-199">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet).</span></span>
    
- <span data-ttu-id="249f9-200">お使いのサーバーで、正しいバージョンの Skype for Business Server が実行されています。</span><span class="sxs-lookup"><span data-stu-id="249f9-200">Your servers are running the correct version of Skype for Business Server.</span></span>
    
- <span data-ttu-id="249f9-201">ポートが正しく構成されています。</span><span class="sxs-lookup"><span data-stu-id="249f9-201">Your ports are configured correctly.</span></span>
    
- <span data-ttu-id="249f9-202">割り当てられたテストユーザーには、必要な資格情報があります。</span><span class="sxs-lookup"><span data-stu-id="249f9-202">Your assigned test users have the required credentials.</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="249f9-203">監視ノードの管理</span><span class="sxs-lookup"><span data-stu-id="249f9-203">Managing Watcher Nodes</span></span>
<span data-ttu-id="249f9-204"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="249f9-204"></span></span>

<span data-ttu-id="249f9-205">監視ノードで実行される代理トランザクションの変更に加え、管理者は **Set-CsWatcherNodeConfiguration** コマンドレットを使用して、監視ノードを有効化または無効化すること、およびテストの実行時に内部 Web URL または外部 Web URL を使用するように監視ノードを構成すること、という他の 2 つの重要なタスクも実行できます。</span><span class="sxs-lookup"><span data-stu-id="249f9-205">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="249f9-p117">既定では、監視ノードは、すべての有効な代理トランザクションを定期的に実行するように設計されています。ただし、これらのトランザクションの中断が必要な場合があります。たとえば、監視ノードを一時的にネットワークから切り離す場合は、代理トランザクションを実行する理由がありません。ネットワーク接続がなければ、これらのトランザクションは失敗します。監視ノードを一時的に無効にする場合は、Skype for Business Server 管理シェルから次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="249f9-p117">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions. At times, however, you may want to suspend those transactions. For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions. Without network connectivity, those transactions will fail. To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="249f9-p118">このコマンドは、監視ノード atl-watcher- 001.litwareinc.com での代理トランザクションの実行を無効にします。代理トランザクションの実行を再開するには、Enabled プロパティを True ($True) に戻します。</span><span class="sxs-lookup"><span data-stu-id="249f9-p118">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com. To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="249f9-p119">Enabled プロパティを使用して監視ノードをオンまたはオフにできます。監視ノードを完全に削除する場合は、**Remove-CsWatcherNodeConfiguration** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="249f9-p119">The Enabled property can be used to turn watcher nodes on or off. If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="249f9-215">このコマンドは、指定されたコンピューターからすべてのウォッチャーノードの構成設定を削除します。これにより、そのコンピューターは代理トランザクションを自動的に実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="249f9-215">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="249f9-216">ただし、このコマンドを実行しても、System Center agent ファイルまたは Skype for Business Server システムファイルはアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="249f9-216">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="249f9-p121">既定では、監視ノードは、テストを実行するときに組織の外部 Web URL を使用します。ただし、監視ノードは、組織の内部 Web URL を使用するように構成することもできます。これにより、管理者は、境界ネットワーク内に配置されたユーザーの URL アクセスを検証できます。監視ノードを外部 URL ではなく内部 URL を使用するように構成するには、UseInternalWebUrls プロパティを True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="249f9-p121">By default, watcher nodes use an organization's external Web URLs when conducting tests. However, watcher nodes can also be configured to use the organization's internal Web URLs. This enables administrators to verify URL access for users located inside the perimeter network. To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="249f9-221">このプロパティを既定値である False ($False) にリセットすると、監視ノードは外部 URL を使用します。</span><span class="sxs-lookup"><span data-stu-id="249f9-221">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="249f9-222">代理トランザクションの特別なセットアップ指示</span><span class="sxs-lookup"><span data-stu-id="249f9-222">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="249f9-223"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="249f9-223"></span></span>

<span data-ttu-id="249f9-p122">大半の代理トランザクションは、監視ノード上でそのまま実行できます。ほとんどの場合、代理トランザクションが監視ノード構成設定に追加されると、監視ノードはその代理トランザクションの使用をテスト パス中に直ちに開始できます。ただし、以降のセクションで説明するように、一部の代理トランザクションでは特別なセットアップが必要です。</span><span class="sxs-lookup"><span data-stu-id="249f9-p122">Most synthetic transactions can run on a watcher node as-is. In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes. However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="249f9-227">データ会議代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="249f9-227">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="249f9-228">監視ノード コンピューターが境界ネットワークの外部に配置されている場合は、以下の手順を実行してネットワーク サービス アカウントの Windows Internet Explorer® Internet ブラウザーでのプロキシ設定を最初に無効にしない限り、データ会議代理トランザクションはほぼ実行できません。</span><span class="sxs-lookup"><span data-stu-id="249f9-228">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="249f9-229">監視ノード コンピューターで、[**スタート**] ボタン、[**すべてのプログラム**]、[**アクセサリ**] の順にクリックし、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="249f9-229">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="249f9-230">コンソール ウィンドウで、次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="249f9-230">In the console window, type the following command and then press ENTER.</span></span> 
    
```console
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="249f9-231">コマンド ウィンドウに次のようなメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="249f9-231">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="249f9-p123">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span><span class="sxs-lookup"><span data-stu-id="249f9-p123">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="249f9-234">Internet proxy settings for account NetworkService set to NO_PROXY.</span><span class="sxs-lookup"><span data-stu-id="249f9-234">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="249f9-235">(connection = default)</span><span class="sxs-lookup"><span data-stu-id="249f9-235">(connection = default)</span></span>
  
<span data-ttu-id="249f9-236">このメッセージは、ネットワーク サービス アカウントの Internet Explorer プロキシ設定が無効になったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="249f9-236">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="249f9-237">Exchange ユニファイド メッセージング代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="249f9-237">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="249f9-238">Exchange Unified Messaging (UM) 代理トランザクションは、テスト ユーザーが Exchange に属するボイスメール アカウントに接続できることを検証します。</span><span class="sxs-lookup"><span data-stu-id="249f9-238">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="249f9-239">これらのテスト ユーザーは、ボイスメール アカウントを使用して事前に構成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="249f9-239">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="249f9-240">常設チャット代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="249f9-240">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="249f9-241">常設チャット代理トランザクションを使用するには、管理者は、まずチャネルを作成し、テスト ユーザーにチャネルを使用する許可を与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="249f9-241">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="249f9-242">常設チャット代理トランザクションを使用して、このチャネルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="249f9-242">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="249f9-243">このセットアップ タスクは、社内から実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="249f9-243">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="249f9-244">サーバー以外のコンピューターから実行する場合、コマンドレットを実行するユーザーは、役割ベースのアクセス制御 (RBAC) の CsPersistentChatAdministrators 役割のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="249f9-244">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="249f9-245">サーバー自体から実行する場合、コマンドレットを実行するユーザーは、RTCUniversalServerAdmins グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="249f9-245">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="249f9-246">PSTN ピアツーピア通話代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="249f9-246">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="249f9-247">Test-CsPstnPeerToPeerCall 代理トランザクションは、公衆交換電話網 (PSTN) 経由で通話を発信および受信できるかどうか検証します。</span><span class="sxs-lookup"><span data-stu-id="249f9-247">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="249f9-248">この代理トランザクションを実行するには、管理者は以下を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="249f9-248">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="249f9-249">UC 用に有効化された 2 つのテスト ユーザー (発信者と受信者)。</span><span class="sxs-lookup"><span data-stu-id="249f9-249">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="249f9-250">各ユーザー アカウントのダイレクト インワード ダイヤリング (DID) 番号。</span><span class="sxs-lookup"><span data-stu-id="249f9-250">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="249f9-251">受信者の電話番号への通話を許可する VoIP ポリシーとボイスルーティング。 PSTN ゲートウェイに到達できます。</span><span class="sxs-lookup"><span data-stu-id="249f9-251">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="249f9-252">PSTN ゲートウェイは、ダイヤル先のホームプールに着信を転送する通話とメディアを受信します。</span><span class="sxs-lookup"><span data-stu-id="249f9-252">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="249f9-253">統合連絡先ストア代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="249f9-253">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="249f9-254">統合連絡先ストアの代理トランザクションでは、Skype for Business Server が Exchange のユーザーの代わりに連絡先を取得できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="249f9-254">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="249f9-255">この代理トランザクションを使用するには、次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="249f9-255">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="249f9-256">Lyss-Exchange サーバーからのサーバー認証が構成済みであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="249f9-256">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="249f9-257">テスト ユーザーが有効な Exchange メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="249f9-257">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="249f9-258">これらの条件が満たされた後、次の Windows PowerShell コマンドレットを実行して、テストユーザーの連絡先リストを Exchange に移行することができます。</span><span class="sxs-lookup"><span data-stu-id="249f9-258">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="249f9-259">テスト ユーザーの連絡先リストを Exchange に移行するには、ある程度の時間を要することがあります。</span><span class="sxs-lookup"><span data-stu-id="249f9-259">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="249f9-260">移行の進行状況を監視するために、次のコマンドラインは、セットアップフラグなしで実行できます。</span><span class="sxs-lookup"><span data-stu-id="249f9-260">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="249f9-261">移行が完了した後、このコマンドが成功するようになります。</span><span class="sxs-lookup"><span data-stu-id="249f9-261">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="249f9-262">XMPP 代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="249f9-262">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="249f9-263">XMPP (Extensible Messaging and Presence Protocol) IM 代理トランザクションでは、XMPP 機能を 1 つ以上のフェデレーション ドメインで構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="249f9-263">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="249f9-264">XMPP 代理トランザクションを有効にするには、XmppTestReceiverMailAddress パラメーターにルーティング可能な XMPP ドメインのユーザー アカントを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="249f9-264">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="249f9-265">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="249f9-265">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="249f9-266">この例では、litwareinc.com のメッセージを XMPP ゲートウェイにルーティングするために、Skype for Business Server ルールが存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="249f9-266">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="249f9-267">XMPP ゲートウェイとプロキシは、Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="249f9-267">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="249f9-268">詳細については、「 [XMPP フェデレーションを移行](../../../SfBServer2019/migration/migrating-xmpp-federation.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="249f9-268">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="249f9-269">Video Interop Server (VIS) 代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="249f9-269">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="249f9-270">ビデオ相互運用機能サーバー (VIS) の代理トランザクションでは、代理トランザクションサポートファイル ([VISSTSupportPackage](https://www.microsoft.com/en-us/download/details.aspx?id=46921)) をダウンロードしてインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="249f9-270">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="249f9-271">VISSTSupportPackage をインストールするには、msi の依存関係 (システム要件の下) が既にインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="249f9-271">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="249f9-272">簡単なインストールを実行するには、VISSTSupportPackage を実行します。</span><span class="sxs-lookup"><span data-stu-id="249f9-272">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="249f9-273">.Msi は、次のパスにあるすべてのファイルをインストールします。 "%ProgramFiles%\VIS の代理トランザクションサポートパッケージ"。</span><span class="sxs-lookup"><span data-stu-id="249f9-273">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="249f9-274">VIS の代理トランザクションの実行方法の詳細については、 [CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx)コマンドレットのマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="249f9-274">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="249f9-275">代理トランザクションの実行頻度の変更</span><span class="sxs-lookup"><span data-stu-id="249f9-275">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="249f9-276"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="249f9-276"></span></span>

<span data-ttu-id="249f9-277">既定では、代理トランザクションは構成済みのユーザーに対して 15 分ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="249f9-277">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="249f9-278">2 つの代理トランザクションが互いに競合することを防止するために、代理トランザクションはユーザー セットを対象にして順に実行されます。</span><span class="sxs-lookup"><span data-stu-id="249f9-278">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="249f9-279">すべての代理トランザクションが完了するように、より長い間隔が必要とされます。</span><span class="sxs-lookup"><span data-stu-id="249f9-279">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="249f9-280">定期的なトランザクションをより頻繁に実行する必要がある場合は、特定のユーザーのセットを使って実行される代理トランザクションの数を減らして、一定の時間帯にテストを完了できるようにします。これにより、ネットワークの遅延が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="249f9-280">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="249f9-281">代理トランザクションをさらに実行することが望ましい場合は、さらに多くの代理トランザクションを実行するためにユーザーセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="249f9-281">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="249f9-282">代理トランザクションを実行する頻度を変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="249f9-282">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="249f9-283">System Center Operations Manager を開きます。</span><span class="sxs-lookup"><span data-stu-id="249f9-283">Open System Center Operations Manager.</span></span> <span data-ttu-id="249f9-284">[Authoring] セクションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="249f9-284">Click Authoring section.</span></span> <span data-ttu-id="249f9-285">[ルール] セクション ([作成] の下) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="249f9-285">Click Rules section (under Authoring).</span></span>
    
2. <span data-ttu-id="249f9-286">[ルール] セクションで、"メインの代理トランザクションランナーパフォーマンスコレクションルール" という名前のルールを見つけます。</span><span class="sxs-lookup"><span data-stu-id="249f9-286">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule".</span></span>
    
3. <span data-ttu-id="249f9-287">ルールを右クリックし、[上書き] を選択して、[ルールの上書き] を選択し、[クラスのすべてのオブジェクト] で [プールウォッチャー] を選びます。</span><span class="sxs-lookup"><span data-stu-id="249f9-287">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher".</span></span>
    
4. <span data-ttu-id="249f9-288">[プロパティの上書き] ウィンドウで、[パラメーター名 "頻度"] を選び、[Override] の値を目的の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="249f9-288">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="249f9-289">同じウィンドウで、上書きを適用する必要がある管理パックを選びます。</span><span class="sxs-lookup"><span data-stu-id="249f9-289">In the same window, select the Management pack to which this override needs to be applied.</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="249f9-290">代理トランザクションのリッチ ログの使用</span><span class="sxs-lookup"><span data-stu-id="249f9-290">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="249f9-291"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="249f9-291"></span></span>

<span data-ttu-id="249f9-292">代理トランザクションは、システムの問題を特定する際に非常に役立つことが実証されてきました。</span><span class="sxs-lookup"><span data-stu-id="249f9-292">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="249f9-293">たとえば、Test-CsRegistration コマンドレットを使用して、ユーザーが Skype for Business Server に登録しようとするときに問題が発生していることを管理者に警告できます。</span><span class="sxs-lookup"><span data-stu-id="249f9-293">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="249f9-294">ただし、障害の実際の原因を突き止めるには、付加的な詳細が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="249f9-294">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="249f9-p132">この理由で、代理トランザクションはリッチ ログを提供しています。リッチ ログを使用すると、代理トランザクションが実行するアクティビティごとに次の情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="249f9-p132">For this reason, synthetic transactions provide rich logging. With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="249f9-297">アクティビティが開始した時間</span><span class="sxs-lookup"><span data-stu-id="249f9-297">The time that the activity started.</span></span>
    
- <span data-ttu-id="249f9-298">アクティビティが終了した時間</span><span class="sxs-lookup"><span data-stu-id="249f9-298">The time that the activity finished.</span></span>
    
- <span data-ttu-id="249f9-299">実行されたアクション (たとえば、電話会議の作成、参加、または終了、Skype for Business Server へのサインオン、インスタント メッセージの送信など)</span><span class="sxs-lookup"><span data-stu-id="249f9-299">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="249f9-300">アクティビティの実行時に生成される情報、詳細、警告、またはエラーメッセージ。</span><span class="sxs-lookup"><span data-stu-id="249f9-300">Informational, verbose, warning, or error messages generated when the activity ran.</span></span>
    
- <span data-ttu-id="249f9-301">SIP 登録メッセージ</span><span class="sxs-lookup"><span data-stu-id="249f9-301">SIP registration messages.</span></span>
    
- <span data-ttu-id="249f9-302">アクティビティが行われたときに生成された例外レコードまたは診断コード</span><span class="sxs-lookup"><span data-stu-id="249f9-302">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="249f9-303">アクティビティを実行した全体的な結果</span><span class="sxs-lookup"><span data-stu-id="249f9-303">The net result of running the activity.</span></span>
    
<span data-ttu-id="249f9-p133">代理トランザクションが実行されるたびに、この情報は自動的に生成されます。しかし、この情報は、自動的に表示されることや、ログ ファイルに保存されることはありません。手動で代理トランザクションを実行中の管理者は、OutLoggerVariable パラメーターを使用して、情報を保存する Windows PowerShell 変数を指定できます。次に、管理者は、2 つの方法のいずれかを使用して、リッチ ログのエラー メッセージを XML または HTML 形式で保存または表示できます。</span><span class="sxs-lookup"><span data-stu-id="249f9-p133">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file. If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored. From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="249f9-307">トラブルシューティング情報を収集するには、OutLoggerVariable パラメーターと、それに続く任意の変数名を指定します。</span><span class="sxs-lookup"><span data-stu-id="249f9-307">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="249f9-308">変数名の先頭に $ 文字を付けないでください。</span><span class="sxs-lookup"><span data-stu-id="249f9-308">Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="249f9-309">$RegistrationTest ではなく、RegistrationTest のような変数名を使用します。</span><span class="sxs-lookup"><span data-stu-id="249f9-309">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="249f9-310">このコマンドを実行すると、次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="249f9-310">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="249f9-311">ターゲット Fqdn: atl-cs-001.litwareinc.com Result: エラー待ち時間: 00:00:00 エラーメッセージ: このコンピューターには、割り当てられている証明書がありません。</span><span class="sxs-lookup"><span data-stu-id="249f9-311">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="249f9-312">診断: このエラーの詳細情報にアクセスするには、ここに示すエラーメッセージだけでなく、さらに詳しい情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="249f9-312">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span>

<span data-ttu-id="249f9-313">この情報に HTML 形式でアクセスするには、以下のようなコマンドを使用して、変数 RegistrationTest に格納された情報を HTML ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="249f9-313">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="249f9-314">別の方法として、ToXML() メソッドを使用して、XML ファイルにデータを保存できます。</span><span class="sxs-lookup"><span data-stu-id="249f9-314">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="249f9-315">これらのファイルは、Windows Internet Explorer、Microsoft Visual Studio、またはその他すべての HTML/XML ファイルを開けるアプリケーションで表示できます。</span><span class="sxs-lookup"><span data-stu-id="249f9-315">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="249f9-316">System Center Operations Manager の内部で実行される代理トランザクションでは、エラーのログファイルが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="249f9-316">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="249f9-317">しかし、Skype for Business Server PowerShell が読み込まれて代理トランザクションを行う前に、実行が失敗した場合、これらのログは生成されません。</span><span class="sxs-lookup"><span data-stu-id="249f9-317">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="249f9-318">既定では、Skype for Business Server は共有されていないフォルダーにログファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="249f9-318">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="249f9-319">これらのログを簡単にアクセスできるようにするには、このフォルダーを共有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="249f9-319">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="249f9-320">たとえば、litwareinc \\のようになります。 com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="249f9-320">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
