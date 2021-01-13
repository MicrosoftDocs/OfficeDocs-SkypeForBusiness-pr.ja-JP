---
title: 監視ノードのテスト ユーザーと設定を構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: Skype for Business Server 代理トランザクションのテスト ユーザー アカウントと監視ノードの設定を構成します。'
ms.openlocfilehash: 6edce666345e4691d8850e5806eedbebc98e3743
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812767"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="6ab64-103">監視ノードのテスト ユーザーと設定を構成する</span><span class="sxs-lookup"><span data-stu-id="6ab64-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="6ab64-104">**概要:** Skype for Business Server 代理トランザクションのテスト ユーザー アカウントと監視ノードの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="6ab64-105">監視ノードとして機能するコンピューターを構成したら、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="6ab64-106">[これらの監視ノードで使用](test-users-and-settings-2019.md#testuser) するテスト ユーザー アカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-106">[Configure Test User Accounts](test-users-and-settings-2019.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="6ab64-107">ネゴシエート認証方法を使用している場合は **、Set-CsTestUserCredential** コマンドレットを使用して、監視ノードで使用するためにこれらのテスト アカウントを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="6ab64-108">監視ノードの構成設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="6ab64-109">テスト ユーザー アカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="6ab64-109">Configure Test User Accounts</span></span>
<span data-ttu-id="6ab64-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="6ab64-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="6ab64-111">テスト アカウントは、実際のユーザーを表す必要はありません。ただし、有効な Active Directory アカウントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="6ab64-112">さらに、これらのアカウントは Skype for Business Server に対して有効にし、有効な SIP アドレスを持っている必要があります。また、エンタープライズ VoIP に対して有効にする必要があります (Test-CsPstnPeerToPeerCall 代理トランザクションを使用する場合)。</span><span class="sxs-lookup"><span data-stu-id="6ab64-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="6ab64-113">TrustedServer 認証方法を使用している場合は、これらのアカウントが存在し、これらのアカウントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="6ab64-114">テストするプールごとに、少なくとも 3 人のテスト ユーザーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-114">You should assign at least three test users for each pool that you want to test.</span></span> <span data-ttu-id="6ab64-115">ネゴシエート認証方法を使用している場合は、Set-CsTestUserCredential コマンドレットと Skype for Business Server 管理シェルも使用して、これらのテスト アカウントが代理トランザクションで機能する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="6ab64-116">これを行うには、次のようなコマンドを実行します (これらのコマンドは、3 つの Active Directory ユーザー アカウントが作成され、これらのアカウントが Skype for Business Server に対して有効になっていると想定しています)。</span><span class="sxs-lookup"><span data-stu-id="6ab64-116">Do this by running a command similar to the following (these commands assume that the three Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

<span data-ttu-id="6ab64-117">SIP アドレスだけでなく、ユーザー名とパスワードも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="6ab64-118">パスワードを含めない場合は、Set-CsTestUserCredentialを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="6ab64-119">ユーザー名は、前のコード ブロックに示したドメイン名\ユーザー名の形式を使用して指定できます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="6ab64-120">テスト ユーザーの資格情報が作成されたのを確認するには、Skype for Business Server 管理シェルから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

<span data-ttu-id="6ab64-121">次のような情報は、ユーザーごとに返されます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="6ab64-122">**UserName**</span><span class="sxs-lookup"><span data-stu-id="6ab64-122">**UserName**</span></span>|<span data-ttu-id="6ab64-123">**Password**</span><span class="sxs-lookup"><span data-stu-id="6ab64-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6ab64-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="6ab64-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="6ab64-125">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="6ab64-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="6ab64-126">既定の代理トランザクションを使用して基本監視ノードを構成する</span><span class="sxs-lookup"><span data-stu-id="6ab64-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="6ab64-127">テスト ユーザーを作成したら、次のようなコマンドを使用して監視ノードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

<span data-ttu-id="6ab64-128">このコマンドは、既定の設定を使用する新しい監視ノードを作成し、代理トランザクションの既定のセットを実行します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="6ab64-129">新しい監視ノードでは、テスト ユーザーがwatcher1@litwareinc.com、watcher2@litwareinc.com、およびwatcher3@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="6ab64-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="6ab64-130">監視ノードで TrustedServer 認証を使用する場合、3 つのテスト アカウントには、Active Directory と Skype for Business Server に対して有効な任意の有効なユーザー アカウントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-130">If the watcher node uses TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="6ab64-131">監視ノードでネゴシエート認証方法を使用する場合は、これらのユーザー アカウントも監視ノードに対して有効にし、Set-CsTestUserCredentialがあります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="6ab64-132">プールを直接対象にするのではなく、サインインするターゲット プールの自動検出が正しく構成されていることを検証するには、代わりに次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="6ab64-133">拡張テストの構成</span><span class="sxs-lookup"><span data-stu-id="6ab64-133">Configuring Extended Tests</span></span>

<span data-ttu-id="6ab64-134">公衆交換電話網との接続を確認する PSTN テストを有効にする場合は、監視ノードを設定するときに追加の構成を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="6ab64-135">まず、Skype for Business Server 管理シェルから次のようなコマンドを実行して、テスト ユーザーを PSTN テストの種類に関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="6ab64-136">このコマンドの結果は変数に格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="6ab64-137">この例では、変数の名前は $pstnTest。</span><span class="sxs-lookup"><span data-stu-id="6ab64-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="6ab64-138">次に **、New-CsWatcherNodeConfiguration** コマンドレットを使用して、テストの種類 (変数 $pstnTest に格納) を Skype for Business Server プールに関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="6ab64-139">たとえば、次のコマンドを実行すると、プール atl-cs-001.litwareinc.com の新しい監視ノード構成が作成され、前に作成した 3 人のテスト ユーザーが追加され、PSTN テストの種類が追加されます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="6ab64-140">監視ノード コンピューターに Skype for Business Server のコア ファイルと RTCLocal データベースをインストールしていない場合、上記のコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="6ab64-141">複数の音声ポリシーをテストするには **、New-CsExtendedTest** コマンドレットを使用して、ポリシーごとに拡張テストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="6ab64-142">提供されたユーザーは、目的の音声ポリシーで構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="6ab64-143">拡張テストは、次のようなコンマ区切り文字を使用して **New-CsWatcherNodeConfiguration** コマンドレットに渡されます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="6ab64-144">-ExtendedTests @{Add=$pstnTest 1,$pstnTest 2,$pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="6ab64-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="6ab64-145">**New-CsWatcherNodeConfiguration** コマンドレットは Tests パラメーターを使用せずに呼び出されたため、新しい監視ノードでは既定の代理トランザクション (および指定された拡張代理トランザクション) だけが有効になります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="6ab64-146">したがって、監視ノードは次のコンポーネントをテストします。</span><span class="sxs-lookup"><span data-stu-id="6ab64-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="6ab64-147">Registration</span><span class="sxs-lookup"><span data-stu-id="6ab64-147">Registration</span></span>
    
- <span data-ttu-id="6ab64-148">IM</span><span class="sxs-lookup"><span data-stu-id="6ab64-148">IM</span></span>
    
- <span data-ttu-id="6ab64-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="6ab64-149">GroupIM</span></span>
    
- <span data-ttu-id="6ab64-150">P2PAV (ピアツーピア音声/ビデオ セッション)</span><span class="sxs-lookup"><span data-stu-id="6ab64-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="6ab64-151">AvConference (電話会議)</span><span class="sxs-lookup"><span data-stu-id="6ab64-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="6ab64-152">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="6ab64-152">Presence</span></span>
    
- <span data-ttu-id="6ab64-153">ABS (アドレス帳サービス)</span><span class="sxs-lookup"><span data-stu-id="6ab64-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="6ab64-154">ABWQ (アドレス帳 Web サービス)</span><span class="sxs-lookup"><span data-stu-id="6ab64-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="6ab64-155">既定では、次のコンポーネントはテストされません。</span><span class="sxs-lookup"><span data-stu-id="6ab64-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="6ab64-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="6ab64-156">ASConference</span></span>
    
- <span data-ttu-id="6ab64-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="6ab64-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="6ab64-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="6ab64-158">DataConference</span></span>
    
- <span data-ttu-id="6ab64-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="6ab64-159">DialinConferencing</span></span>
    
- <span data-ttu-id="6ab64-160">ExumConnectivity (Exchange ユニファイド メッセージング)</span><span class="sxs-lookup"><span data-stu-id="6ab64-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="6ab64-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="6ab64-161">JoinLauncher</span></span>
    
- <span data-ttu-id="6ab64-162">MCXP2PIM (従来のモバイル デバイス インスタント メッセージング)</span><span class="sxs-lookup"><span data-stu-id="6ab64-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="6ab64-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="6ab64-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="6ab64-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="6ab64-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="6ab64-165">PSTN (拡張テストとして指定された PSTN ゲートウェイ通話)</span><span class="sxs-lookup"><span data-stu-id="6ab64-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="6ab64-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="6ab64-166">UcwaConference</span></span>
    
- <span data-ttu-id="6ab64-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="6ab64-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="6ab64-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="6ab64-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="6ab64-169">代理トランザクションの追加と削除</span><span class="sxs-lookup"><span data-stu-id="6ab64-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="6ab64-170">監視ノードを構成した後、Set-CsWatcherNodeConfiguration コマンドレットを使用して、ノードに代理トランザクションを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="6ab64-171">たとえば、PersistentChatMessage テストを監視ノードに追加するには、Add メソッドと次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="6ab64-172">テスト名をコンマで区切って、複数のテストを追加できます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="6ab64-173">例:</span><span class="sxs-lookup"><span data-stu-id="6ab64-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="6ab64-174">これらのテスト (DataConference など) の 1 つ以上が監視ノードで既に有効になっている場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="6ab64-175">この場合、次のようなエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="6ab64-176">Set-CsWatcherNodeConfiguration : 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' キーまたは一意の ID 制約に重複するキー シーケンス 'DataConference' があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="6ab64-177">このエラーが発生した場合、変更は適用されません。</span><span class="sxs-lookup"><span data-stu-id="6ab64-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="6ab64-178">重複するテストを削除して、コマンドを再実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="6ab64-179">代理トランザクションを監視ノードから削除するには、Remove メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="6ab64-180">たとえば、次のコマンドは監視ノードから ABWQ テストを削除します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="6ab64-181">Replace メソッドを使用すると、現在有効になっているすべてのテストを 1 つ以上の新しいテストに置き換できます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="6ab64-182">たとえば、監視ノードで IM テストのみを実行する場合は、次のコマンドを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="6ab64-183">このコマンドを実行すると、指定した監視ノード上のすべての代理トランザクションが IM を除いて無効になります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="6ab64-184">監視ノード構成の表示とテスト</span><span class="sxs-lookup"><span data-stu-id="6ab64-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="6ab64-185">監視ノードに割り当てられているテストを表示するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="6ab64-186">このコマンドは、ノードに割り当てられている代理トランザクションに応じて、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="6ab64-187">登録 IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="6ab64-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="6ab64-188">代理トランザクションをアルファベット順で表示するには、代わりに次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="6ab64-189">監視ノードが作成されたのを確認するには、Skype for Business Server 管理シェルから次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="6ab64-190">次のような情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="6ab64-191">Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span><span class="sxs-lookup"><span data-stu-id="6ab64-191">Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span> <span data-ttu-id="6ab64-192">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test;Te...}</span><span class="sxs-lookup"><span data-stu-id="6ab64-192">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span> <span data-ttu-id="6ab64-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061 監視ノードが正しく構成されていることを確認するには、Skype for Business Server 管理シェルから次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="6ab64-194">このコマンドは、展開内の各監視ノードをテストし、次の操作が完了したかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-194">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="6ab64-195">必要なレジストラーの役割がインストールされている</span><span class="sxs-lookup"><span data-stu-id="6ab64-195">The required Registrar role is installed</span></span>
    
- <span data-ttu-id="6ab64-196">必要なレジストリ キーが作成されます (このコマンドレットを実行するとSet-CsWatcherNodeConfigurationされます)</span><span class="sxs-lookup"><span data-stu-id="6ab64-196">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet)</span></span>
    
- <span data-ttu-id="6ab64-197">サーバーで正しいバージョンの Skype for Business Server を実行している</span><span class="sxs-lookup"><span data-stu-id="6ab64-197">Your servers are running the correct version of Skype for Business Server</span></span>
    
- <span data-ttu-id="6ab64-198">ポートが正しく構成されている</span><span class="sxs-lookup"><span data-stu-id="6ab64-198">Your ports are configured correctly</span></span>
    
- <span data-ttu-id="6ab64-199">割り当てられたテスト ユーザーが必要な資格情報を持っている</span><span class="sxs-lookup"><span data-stu-id="6ab64-199">Your assigned test users have the required credentials</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="6ab64-200">監視ノードの管理</span><span class="sxs-lookup"><span data-stu-id="6ab64-200">Managing Watcher Nodes</span></span>
<span data-ttu-id="6ab64-201"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="6ab64-201"><a name="testuser"> </a></span></span>

<span data-ttu-id="6ab64-202">監視ノードで実行される代理トランザクションの変更に加えて **、Set-CsWatcherNodeConfiguration** コマンドレットを使用して、監視ノードの有効化と無効化、およびテストの実行中に内部 Web URL または外部 Web URL を使用する監視ノードの構成という 2 つの重要なタスクを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-202">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="6ab64-203">既定では、監視ノードは、すべての有効な代理トランザクションを定期的に実行するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="6ab64-203">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="6ab64-204">ただし、これらのトランザクションを中断する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-204">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="6ab64-205">たとえば、監視ノードを一時的にネットワークから切り離す場合は、代理トランザクションを実行する理由がありません。</span><span class="sxs-lookup"><span data-stu-id="6ab64-205">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="6ab64-206">ネットワーク接続がない場合、これらのトランザクションは失敗します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-206">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="6ab64-207">監視ノードを一時的に無効にするには、Skype for Business Server 管理シェルから次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-207">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="6ab64-208">このコマンドは、監視ノード atl ウォッチャー サーバー上での代理トランザクションの実行を001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="6ab64-208">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="6ab64-209">代理トランザクションの実行を再開するには、Enabled プロパティを True ($True) に戻します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-209">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="6ab64-210">Enabled プロパティを使用して監視ノードをオンまたはオフにできます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-210">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="6ab64-211">監視ノードを完全に削除する場合は、**Remove-CsWatcherNodeConfiguration** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-211">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="6ab64-212">このコマンドを実行すると、指定したコンピューターからすべての監視ノード構成設定が削除され、そのコンピューターは代理トランザクションを自動的に実行できません。</span><span class="sxs-lookup"><span data-stu-id="6ab64-212">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="6ab64-213">ただし、このコマンドを実行しても、System Center エージェント ファイルや Skype for Business Server システム ファイルはアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="6ab64-213">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="6ab64-214">既定では、監視ノードはテストを実行するときに組織の外部 Web URL を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-214">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="6ab64-215">ただし、監視ノードは、組織の内部 Web URL を使用するように構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-215">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="6ab64-216">これにより、管理者は、境界ネットワーク内に配置されたユーザーの URL アクセスを検証できます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-216">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="6ab64-217">外部 URL ではなく内部 URL を使用する監視ノードを構成するには、UseInternalWebURls プロパティを True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-217">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="6ab64-218">このプロパティを既定値の False ($False) にリセットすると、ウォッチャーはもう一度外部 URL を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-218">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="6ab64-219">代理トランザクションの特別なセットアップ指示</span><span class="sxs-lookup"><span data-stu-id="6ab64-219">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="6ab64-220"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="6ab64-220"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="6ab64-221">ほとんどの代理トランザクションは、監視ノードで同じ方法で実行できます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-221">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="6ab64-222">ほとんどの場合、代理トランザクションが監視ノード構成設定に追加されたとすぐに、監視ノードはテスト パス中に代理トランザクションの使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-222">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="6ab64-223">ただし、以下のセクションで説明したように、特別なセットアップ手順を必要とする代理トランザクションがあります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-223">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="6ab64-224">データ会議代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="6ab64-224">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="6ab64-225">監視ノード コンピューターが境界ネットワークの外側にある場合は、次の手順を実行してネットワーク サービス アカウントの Windows Internet Explorer® インターネット ブラウザー プロキシ設定を最初に無効にしない限り、データ会議代理トランザクションを実行できません。</span><span class="sxs-lookup"><span data-stu-id="6ab64-225">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="6ab64-226">監視ノード コンピューターで、[スタート]ボタン、[すべてのプログラム]、[アクセサリ] の順にクリックし、コマンド プロンプトを右クリックして、[管理者として実行] をクリック **します**。 </span><span class="sxs-lookup"><span data-stu-id="6ab64-226">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="6ab64-227">コンソール ウィンドウで、次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-227">In the console window, type the following command and then press ENTER.</span></span> 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="6ab64-228">コマンド ウィンドウに次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-228">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="6ab64-229">BITSAdmin は廃止され、将来のバージョンの Windows で使用できるとは保証されません。</span><span class="sxs-lookup"><span data-stu-id="6ab64-229">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows.</span></span> <span data-ttu-id="6ab64-230">BITS サービスの管理ツールは、BITS PowerShell コマンドレットによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-230">Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="6ab64-231">NetworkService アカウントのインターネット プロキシ設定が NO_PROXY。</span><span class="sxs-lookup"><span data-stu-id="6ab64-231">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="6ab64-232">(connection = default)</span><span class="sxs-lookup"><span data-stu-id="6ab64-232">(connection = default)</span></span>
  
<span data-ttu-id="6ab64-233">このメッセージは、ネットワーク サービス アカウントのプロキシInternet Explorer無効にしたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-233">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="6ab64-234">Exchange ユニファイド メッセージング代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="6ab64-234">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="6ab64-235">Exchange ユニファイド メッセージング (UM) 代理トランザクションは、テスト ユーザーが Exchange にホームのボイスメール アカウントに接続できるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-235">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="6ab64-236">テスト ユーザーは、ボイスメール アカウントで事前構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-236">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="6ab64-237">常設チャット代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="6ab64-237">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="6ab64-238">常設チャット代理トランザクションを使用するには、まずチャネルを作成し、テスト ユーザーにチャネルを使用するアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-238">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="6ab64-239">常設チャット代理トランザクションを使用して、このチャネルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-239">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="6ab64-240">このセットアップ タスクは、エンタープライズ内から実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-240">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="6ab64-241">サーバー以外のコンピューターから実行する場合、コマンドレットを実行するユーザーは、サーバー アクセス制御 (RBAC) の CsPersistentChatAdministrators 役割のメンバーRole-Based必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-241">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="6ab64-242">サーバー自体から実行する場合、コマンドレットを実行するユーザーは RTCUniversalServerAdmins グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-242">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="6ab64-243">PSTN ピアツーピア通話代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="6ab64-243">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="6ab64-244">代理Test-CsPstnPeerToPeerCallは、公衆交換電話網 (PSTN) 経由で通話を発信および受信する機能を確認します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-244">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="6ab64-245">この代理トランザクションを実行するには、以下を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-245">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="6ab64-246">UC が有効な 2 人のテスト ユーザー (発信者と受信者)。</span><span class="sxs-lookup"><span data-stu-id="6ab64-246">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="6ab64-247">各ユーザー アカウントのダイレクト インワード ダイヤリング (DID) 番号。</span><span class="sxs-lookup"><span data-stu-id="6ab64-247">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="6ab64-248">受信者の番号への通話が PSTN ゲートウェイに到達できる VoIP ポリシーとボイス ルート。</span><span class="sxs-lookup"><span data-stu-id="6ab64-248">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="6ab64-249">通話を受け付け、ダイヤルされた番号に基づいて受信者のホーム プールに通話を戻すメディアを受け入れる PSTN ゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="6ab64-249">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="6ab64-250">統合連絡先ストア代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="6ab64-250">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="6ab64-251">統合連絡先ストア代理トランザクションは、Skype for Business Server が Exchange からユーザーに代わって連絡先を取得する機能を検証します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-251">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="6ab64-252">この代理トランザクションを使用するには、次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-252">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="6ab64-253">Lyss-Exchange対サーバー認証を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-253">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="6ab64-254">テスト ユーザーは有効な Exchange メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-254">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="6ab64-255">これらの条件が満たされた後、次のコマンドレットWindows PowerShell実行して、テスト ユーザーの連絡先リストを Exchange に移行できます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-255">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="6ab64-256">テスト ユーザーの連絡先リストが Exchange に移行するには、時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-256">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="6ab64-257">移行の進行状況を監視するには、-Setup フラグを指定せずに同じコマンド ラインを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-257">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="6ab64-258">移行が完了すると、このコマンド ラインは成功します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-258">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="6ab64-259">XMPP 代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="6ab64-259">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="6ab64-260">XMPP (Extensible Messaging and Presence Protocol) IM 代理トランザクションでは、1 つ以上のフェデレーション ドメインで XMPP 機能を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-260">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="6ab64-261">XMPP 代理トランザクションを有効にするには、XmppTestReceiverMailAddress パラメーターに、ログアウト可能な XMPP ドメインのユーザー アカウントを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-261">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="6ab64-262">例:</span><span class="sxs-lookup"><span data-stu-id="6ab64-262">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="6ab64-263">この例では、XMPP ゲートウェイにメッセージをルーティングするために Skype for Business Server litwareinc.com存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-263">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="6ab64-264">XMPP ゲートウェイとプロキシは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="6ab64-264">XMPP Gateways and proxies were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="6ab64-265">詳細 [については、「XMPP フェデレーションの移行](../migration/migrating-xmpp-federation.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ab64-265">See [Migrating XMPP federation](../migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="6ab64-266">ビデオ相互運用サーバー (VIS) 代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="6ab64-266">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="6ab64-267">ビデオ相互運用サーバー (VIS) 代理トランザクションでは、代理トランザクション サポート ファイル (VISSTSupportPackage.msi) をダウンロードしてインストール[ する必要があります ](https://www.microsoft.com/download/details.aspx?id=46921)。</span><span class="sxs-lookup"><span data-stu-id="6ab64-267">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="6ab64-268">インストールするにはVISSTSupportPackage.msi msi の依存関係 ([システム要件] の下) が既にインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-268">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="6ab64-269">簡単VISSTSupportPackage.msiを実行するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-269">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="6ab64-270">.msi は、"%ProgramFiles%\VIS Synthetic Transaction Support Package" というパスのすべてのファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6ab64-270">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="6ab64-271">VIS 代理トランザクションの実行方法の詳細については [、Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ab64-271">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="6ab64-272">代理トランザクションの実行頻度の変更</span><span class="sxs-lookup"><span data-stu-id="6ab64-272">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="6ab64-273"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="6ab64-273"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="6ab64-274">既定では、代理トランザクションは構成済みのユーザーと 15 分ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-274">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="6ab64-275">代理トランザクションは、2 つの代理トランザクションが互いに競合しないように、一連のユーザー内で順番に実行されます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-275">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="6ab64-276">すべての代理トランザクションが完了する時間を提供するには、より長い間隔が必要です。</span><span class="sxs-lookup"><span data-stu-id="6ab64-276">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="6ab64-277">代理トランザクションの実行頻度を高くすることが望ましい場合は、特定のユーザー のセットで実行される代理トランザクションの数を減らして、ネットワーク遅延が発生する可能性のあるバッファーを使用して目的の時間範囲内でテストを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-277">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="6ab64-278">より多くの代理トランザクションを実行することが望ましい場合は、追加の代理トランザクションを実行するユーザー セットを作成します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-278">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="6ab64-279">代理トランザクションを実行する頻度を変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-279">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="6ab64-280">System Center Operations Manager を開きます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-280">Open System Center Operations Manager.</span></span> <span data-ttu-id="6ab64-281">[作成] セクションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ab64-281">Click Authoring section.</span></span> <span data-ttu-id="6ab64-282">[ルール] セクション ([作成] の下) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ab64-282">Click Rules section (under Authoring)</span></span>
    
2. <span data-ttu-id="6ab64-283">[Rules] セクションで、"Main Synthetic Transaction Runner Performance Collection Rule" という名前のルールを見つける</span><span class="sxs-lookup"><span data-stu-id="6ab64-283">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule"</span></span>
    
3. <span data-ttu-id="6ab64-284">ルールを右クリックし、[上書き] を選択し、[ルールの上書き] を選択して、[クラスのすべてのオブジェクトの場合: プール ウォッチャー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-284">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher"</span></span>
    
4. <span data-ttu-id="6ab64-285">[プロパティの上書き] ウィンドウで、パラメーター名 "Frequency" を選択し、優先値を目的の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-285">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="6ab64-286">同じウィンドウで、このオーバーライドを適用する必要がある管理パックを選択します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-286">In the same window, select the Management pack to which this override needs to be applied</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="6ab64-287">代理トランザクションのリッチ ログの使用</span><span class="sxs-lookup"><span data-stu-id="6ab64-287">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="6ab64-288"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="6ab64-288"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="6ab64-289">代理トランザクションは、システムの問題を特定するのに非常に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-289">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="6ab64-290">たとえば、Test-CsRegistrationコマンドレットを使用すると、ユーザーが Skype for Business Server への登録で問題が発生したという事実を管理者に警告できます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-290">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="6ab64-291">ただし、エラーの実際の原因を特定するには、追加の詳細が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-291">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="6ab64-292">このため、代理トランザクションは豊富なログを提供します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-292">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="6ab64-293">リッチ ログでは、代理トランザクションが実行するアクティビティごとに、次の情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-293">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="6ab64-294">アクティビティが開始された時刻。</span><span class="sxs-lookup"><span data-stu-id="6ab64-294">The time that the activity started.</span></span>
    
- <span data-ttu-id="6ab64-295">アクティビティが終了した時刻。</span><span class="sxs-lookup"><span data-stu-id="6ab64-295">The time that the activity finished.</span></span>
    
- <span data-ttu-id="6ab64-296">実行されたアクション (会議の作成、参加、退出、Skype for Business Server へのサインイン、インスタント メッセージの送信など)。</span><span class="sxs-lookup"><span data-stu-id="6ab64-296">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="6ab64-297">アクティビティが行われたとき生成された、情報提供メッセージ、詳細メッセージ、警告メッセージ、またはエラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="6ab64-297">Informational, verbose, warning, or error messages generated when the activity ran</span></span>
    
- <span data-ttu-id="6ab64-298">SIP 登録メッセージ。</span><span class="sxs-lookup"><span data-stu-id="6ab64-298">SIP registration messages.</span></span>
    
- <span data-ttu-id="6ab64-299">アクティビティの実行時に生成された例外レコードまたは診断コード。</span><span class="sxs-lookup"><span data-stu-id="6ab64-299">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="6ab64-300">アクティビティを実行した結果の結果。</span><span class="sxs-lookup"><span data-stu-id="6ab64-300">The net result of running the activity.</span></span>
    
<span data-ttu-id="6ab64-301">この情報は代理トランザクションが実行されるたび自動的に生成されますが、ログ ファイルに自動的に表示または保存されるのではありません。</span><span class="sxs-lookup"><span data-stu-id="6ab64-301">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="6ab64-302">代理トランザクションを手動で実行している場合は、OutLoggerVariable パラメーターを使用して、情報が格納される Windows PowerShell 変数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-302">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="6ab64-303">そこから、2 つの方法のいずれかを使用して、エラー メッセージを XML 形式または HTML 形式でリッチ ログに保存または表示することができます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-303">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="6ab64-304">トラブルシューティング情報を取得するには、OutLoggerVariable パラメーターを指定し、その後に変数名を指定します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-304">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="6ab64-305">: 変数名の前に $ 文字を付けない。</span><span class="sxs-lookup"><span data-stu-id="6ab64-305">: Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="6ab64-306">RegistrationTest などの変数名を使用します ($RegistrationTest)。</span><span class="sxs-lookup"><span data-stu-id="6ab64-306">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="6ab64-307">このコマンドを実行すると、次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-307">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="6ab64-308">ターゲット Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span><span class="sxs-lookup"><span data-stu-id="6ab64-308">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="6ab64-309">診断 :このエラーに関する詳細な情報には、ここに示すエラー メッセージに加え、より詳細な情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-309">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span> <span data-ttu-id="6ab64-310">この情報に HTML 形式でアクセスするには、次のようなコマンドを使用して、変数 RegistrationTest に格納されている情報を HTML ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-310">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="6ab64-311">別の方法として、ToXML() メソッドを使用して、XML ファイルにデータを保存できます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-311">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="6ab64-312">これらのファイルは、Windows Internet Explorer、Microsoft Visual Studio、または HTML/XML ファイルを開くことができる他のアプリケーションを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="6ab64-312">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="6ab64-313">System Center Operations Manager の内部から実行される代理トランザクションは、障害が発生した場合にこれらのログ ファイルを自動的に生成します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-313">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="6ab64-314">これらのログは、Skype for Business Server PowerShell が代理トランザクションを読み込み、実行する前に実行が失敗した場合は生成されません。</span><span class="sxs-lookup"><span data-stu-id="6ab64-314">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6ab64-315">既定では、Skype for Business Server はログ ファイルを共有されていないフォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="6ab64-315">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="6ab64-316">これらのログに簡単にアクセスするには、このフォルダーを共有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab64-316">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="6ab64-317">例: \\ atl-watcher-001.litwareinc.com\WatcherNode。</span><span class="sxs-lookup"><span data-stu-id="6ab64-317">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
