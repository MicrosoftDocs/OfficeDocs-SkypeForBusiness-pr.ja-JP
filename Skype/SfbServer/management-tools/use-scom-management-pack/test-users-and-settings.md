---
title: 監視ノードのテストユーザーと設定を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: '概要: Skype for Business Server 代理トランザクションのテストユーザーアカウントと監視ノード設定を構成します。'
ms.openlocfilehash: 8b586cf4c1d003bb54afa050469a10eee8d113e3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005952"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="5f574-103">監視ノードのテストユーザーと設定を構成する</span><span class="sxs-lookup"><span data-stu-id="5f574-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="5f574-104">**概要:** Skype for Business Server 代理トランザクションのテストユーザーアカウントと監視ノード設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="5f574-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="5f574-105">監視ノードとして動作するコンピューターを構成した後、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="5f574-106">これらの監視ノードで使用される[テストユーザーアカウントを構成](test-users-and-settings.md#testuser)します。</span><span class="sxs-lookup"><span data-stu-id="5f574-106">[Configure Test User Accounts](test-users-and-settings.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="5f574-107">Negotiate の認証方法を使用している場合は、 **set-cstestusercredential**コマンドレットを使用して、監視ノードで使用するためにこれらのテストアカウントを有効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="5f574-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="5f574-108">監視ノードの構成設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="5f574-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="5f574-109">テストユーザーアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="5f574-109">Configure Test User Accounts</span></span>
<span data-ttu-id="5f574-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="5f574-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="5f574-111">テストアカウントは、実際のユーザーを表す必要はありませんが、有効な Active Directory アカウントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="5f574-112">さらに、これらのアカウントは Skype for Business Server に対して有効にする必要があり、有効な SIP アドレスを持っている必要があります。また、エンタープライズ Voip を有効にする必要があります (テスト-CsPstnPeerToPeerCall 代理トランザクションを使用する場合)。</span><span class="sxs-lookup"><span data-stu-id="5f574-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="5f574-113">TrustedServer の認証方法を使用している場合は、これらのアカウントが存在していることを確認してから、前述のように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="5f574-114">テストする各プールについて、少なくとも2人のテストユーザーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-114">You should assign at least two test users for each pool that you want to test.</span></span> <span data-ttu-id="5f574-115">Negotiate の認証方法を使用している場合は、これらのテストアカウントが代理トランザクションと連携できるようにするには、Set-cstestusercredential コマンドレットと Skype for Business Server 管理シェルも使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="5f574-116">そのためには、次のようなコマンドを実行します (これらのコマンドは、2つの Active Directory ユーザーアカウントが作成されており、これらのアカウントが Skype for Business Server で有効になっていることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="5f574-116">Do this by running a command similar to the following (these commands assume that the two Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

<span data-ttu-id="5f574-117">SIP アドレスだけでなく、ユーザー名とパスワードも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="5f574-118">パスワードを指定しない場合は、Set-cstestusercredential コマンドレットによってその情報の入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="5f574-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="5f574-119">ユーザー名は、前述のコードブロックに示されているドメインの name\user 名の形式を使用して指定できます。</span><span class="sxs-lookup"><span data-stu-id="5f574-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="5f574-120">テストユーザーの資格情報が作成されたことを確認するには、Skype for Business Server 管理シェルから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5f574-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

<span data-ttu-id="5f574-121">次のような情報が各ユーザーに返されます。</span><span class="sxs-lookup"><span data-stu-id="5f574-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="5f574-122">**UserName**</span><span class="sxs-lookup"><span data-stu-id="5f574-122">**UserName**</span></span>|<span data-ttu-id="5f574-123">**Password**</span><span class="sxs-lookup"><span data-stu-id="5f574-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5f574-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="5f574-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="5f574-125">System.security.securestring</span><span class="sxs-lookup"><span data-stu-id="5f574-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="5f574-126">既定の代理トランザクションを使用した基本的な監視ノードの構成</span><span class="sxs-lookup"><span data-stu-id="5f574-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="5f574-127">テストユーザーが作成されたら、次のようなコマンドを使用して監視ノードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5f574-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

<span data-ttu-id="5f574-128">このコマンドは、既定の設定を使用し、代理トランザクションの既定のセットを実行する新しい監視ノードを作成します。</span><span class="sxs-lookup"><span data-stu-id="5f574-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="5f574-129">新しい監視ノードは、テストユーザー watcher1@litwareinc.com および watcher2@litwareinc.com も使用します。</span><span class="sxs-lookup"><span data-stu-id="5f574-129">The new watcher node also uses the test users watcher1@litwareinc.com, and watcher2@litwareinc.com.</span></span> <span data-ttu-id="5f574-130">監視ノードが TrustedServer 認証を使用する場合、2つのテストアカウントは、Active Directory と Skype for Business Server に対して有効になっている任意の有効なユーザーアカウントにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5f574-130">If the watcher node uses TrustedServer authentication, the two test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="5f574-131">監視ノードが Negotiate 認証方法を使用している場合は、Set-cstestusercredential コマンドレットを使用して、監視ノードについてもこれらのユーザーアカウントを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="5f574-132">サインインするターゲットプールの自動検出が適切に構成されているかどうかを検証するには、プールを直接対象とせずに、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5f574-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="5f574-133">拡張テストの構成</span><span class="sxs-lookup"><span data-stu-id="5f574-133">Configuring Extended Tests</span></span>

<span data-ttu-id="5f574-134">PSTN テストを有効にして、公衆交換電話網との接続を確認する場合は、監視ノードを設定するときに追加の構成を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="5f574-135">最初に、Skype for Business Server 管理シェルから次のようなコマンドを実行して、テストユーザーを PSTN テストの種類に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="5f574-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="5f574-136">このコマンドの結果は、変数に格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="5f574-137">この例では、変数に $pstnTest という名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="5f574-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="5f574-138">次に、 **set-cswatchernodeconfiguration**コマンドレットを使用して、テストの種類 (変数 $pstnTest に格納されている) を Skype For business Server プールに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="5f574-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="5f574-139">たとえば、次のコマンドは、プール atl-cs-001.litwareinc.com の新しい監視ノード構成を作成し、以前に作成した2つのテストユーザーを追加して、PSTN テストの種類を追加します。</span><span class="sxs-lookup"><span data-stu-id="5f574-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the two test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="5f574-140">Skype for Business Server のコアファイルおよび RTCLocal データベースを監視ノードコンピューターにインストールしていない場合、上記のコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="5f574-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="5f574-141">複数の音声ポリシーをテストするには、**新しい-Csexthe dedtest**コマンドレットを使用して、各ポリシーの拡張テストを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="5f574-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="5f574-142">提供されるユーザーは、目的の音声ポリシーを使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="5f574-143">拡張テストは、次のようなコンマ区切り記号を使用して**set-cswatchernodeconfiguration**コマンドレットに渡されます。</span><span class="sxs-lookup"><span data-stu-id="5f574-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="5f574-144">-ExtendedTests @ {Add = $pstnTest 1、$pstnTest 2、$pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="5f574-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="5f574-145">**Set-cswatchernodeconfiguration**コマンドレットは、Tests パラメーターを使用せずに呼び出されたので、既定の代理トランザクション (および指定された拡張代理トランザクション) だけが新しい監視ノードで有効になります。</span><span class="sxs-lookup"><span data-stu-id="5f574-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="5f574-146">そのため、監視ノードは次のコンポーネントをテストします。</span><span class="sxs-lookup"><span data-stu-id="5f574-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="5f574-147">レジスタ</span><span class="sxs-lookup"><span data-stu-id="5f574-147">Registration</span></span>
    
- <span data-ttu-id="5f574-148">IM</span><span class="sxs-lookup"><span data-stu-id="5f574-148">IM</span></span>
    
- <span data-ttu-id="5f574-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="5f574-149">GroupIM</span></span>
    
- <span data-ttu-id="5f574-150">P2PAV (ピアツーピアの音声ビデオセッション)</span><span class="sxs-lookup"><span data-stu-id="5f574-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="5f574-151">AvConference (音声/会議)</span><span class="sxs-lookup"><span data-stu-id="5f574-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="5f574-152">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="5f574-152">Presence</span></span>
    
- <span data-ttu-id="5f574-153">ABS (アドレス帳サービス)</span><span class="sxs-lookup"><span data-stu-id="5f574-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="5f574-154">ABWQ (アドレス帳 web サービス)</span><span class="sxs-lookup"><span data-stu-id="5f574-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="5f574-155">既定では、次のコンポーネントはテストされません。</span><span class="sxs-lookup"><span data-stu-id="5f574-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="5f574-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="5f574-156">ASConference</span></span>
    
- <span data-ttu-id="5f574-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="5f574-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="5f574-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="5f574-158">DataConference</span></span>
    
- <span data-ttu-id="5f574-159">ダイヤルイン会議</span><span class="sxs-lookup"><span data-stu-id="5f574-159">DialinConferencing</span></span>
    
- <span data-ttu-id="5f574-160">ExumConnectivity (Exchange ユニファイドメッセージング)</span><span class="sxs-lookup"><span data-stu-id="5f574-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="5f574-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="5f574-161">JoinLauncher</span></span>
    
- <span data-ttu-id="5f574-162">MCXP2PIM (従来のモバイルデバイスインスタントメッセージング)</span><span class="sxs-lookup"><span data-stu-id="5f574-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="5f574-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="5f574-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="5f574-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="5f574-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="5f574-165">PSTN (拡張テストとして指定された pstn ゲートウェイ通話)</span><span class="sxs-lookup"><span data-stu-id="5f574-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="5f574-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="5f574-166">UcwaConference</span></span>
    
- <span data-ttu-id="5f574-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="5f574-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="5f574-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="5f574-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="5f574-169">代理トランザクションの追加と削除</span><span class="sxs-lookup"><span data-stu-id="5f574-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="5f574-170">監視ノードの構成後、Set-cswatchernodeconfiguration コマンドレットを使用して、ノードの代理トランザクションを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="5f574-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="5f574-171">たとえば、監視ノードに PersistentChatMessage テストを追加するには、Add メソッドと次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5f574-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="5f574-172">テスト名をコンマで区切ることで、複数のテストを追加できます。</span><span class="sxs-lookup"><span data-stu-id="5f574-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="5f574-173">例:</span><span class="sxs-lookup"><span data-stu-id="5f574-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="5f574-174">これらのテストの1つ以上 (たとえば、DataConference) が既に監視ノードで有効になっている場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="5f574-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="5f574-175">この場合、次のようなエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f574-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="5f574-176">Set-cswatchernodeconfiguration: ' urn: schema: Watchernode.msi: TestName ' キーまたは一意の id 制約に対して、重複するキーシーケンス ' DataConference ' が存在しています。</span><span class="sxs-lookup"><span data-stu-id="5f574-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="5f574-177">このエラーが発生した場合、変更は適用されません。</span><span class="sxs-lookup"><span data-stu-id="5f574-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="5f574-178">重複するテストを削除した状態でコマンドを再度実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="5f574-179">監視ノードから代理トランザクションを削除するには、Remove メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5f574-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="5f574-180">たとえば、次のコマンドを実行すると、監視ノードから ABWQ テストが削除されます。</span><span class="sxs-lookup"><span data-stu-id="5f574-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="5f574-181">Replace メソッドを使用すると、現在有効になっているすべてのテストを1つまたは複数の新しいテストに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="5f574-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="5f574-182">たとえば、監視ノードが IM テストのみを実行するように構成するには、次のコマンドを使用してそれを構成します。</span><span class="sxs-lookup"><span data-stu-id="5f574-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="5f574-183">このコマンドを実行すると、指定された監視ノードのすべての代理トランザクションは IM 以外は無効になります。</span><span class="sxs-lookup"><span data-stu-id="5f574-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="5f574-184">監視ノード構成の表示とテスト</span><span class="sxs-lookup"><span data-stu-id="5f574-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="5f574-185">監視ノードに割り当てられているテストを表示する場合は、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5f574-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="5f574-186">このコマンドは、ノードに割り当てられている代理トランザクションに応じて、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="5f574-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="5f574-187">Registration IM GroupIM P2PAV AvConference プレゼンス PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="5f574-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="5f574-188">代理トランザクションをアルファベット順で表示するには、代わりに次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5f574-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="5f574-189">監視ノードが作成されたことを確認するには、Skype for Business Server 管理シェルから次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="5f574-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="5f574-190">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f574-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="5f574-191">Identity: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5f574-191">Identity : atl-cs-001.litwareinc.com</span></span> <br/>
<span data-ttu-id="5f574-192">TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...}</span><span class="sxs-lookup"><span data-stu-id="5f574-192">TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span><br/>
<span data-ttu-id="5f574-193">ExtendedTests: {TestUsers = IList<System.string>;Name = PSTN テスト;Te...}</span><span class="sxs-lookup"><span data-stu-id="5f574-193">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span><br/>
<span data-ttu-id="5f574-194">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5f574-194">TargetFqdn : atl-cs-001.litwareinc.com</span></span><br/>
<span data-ttu-id="5f574-195">ポート番号: 5061</span><span class="sxs-lookup"><span data-stu-id="5f574-195">PortNumber : 5061</span></span><br/>

<span data-ttu-id="5f574-196">監視ノードが正しく構成されていることを確認するには、Skype for Business Server 管理シェルから次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="5f574-196">To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="5f574-197">このコマンドは、展開内の各監視ノードをテストし、次の操作が完了したかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5f574-197">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="5f574-198">必要なレジストラーの役割がインストールされている。</span><span class="sxs-lookup"><span data-stu-id="5f574-198">The required Registrar role is installed.</span></span>
    
- <span data-ttu-id="5f574-199">必要なレジストリキーが作成されます (Set-cswatchernodeconfiguration コマンドレットを実行したときに完了)。</span><span class="sxs-lookup"><span data-stu-id="5f574-199">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet).</span></span>
    
- <span data-ttu-id="5f574-200">サーバーで適切なバージョンの Skype for Business Server が実行されている。</span><span class="sxs-lookup"><span data-stu-id="5f574-200">Your servers are running the correct version of Skype for Business Server.</span></span>
    
- <span data-ttu-id="5f574-201">ポートが正しく構成されている。</span><span class="sxs-lookup"><span data-stu-id="5f574-201">Your ports are configured correctly.</span></span>
    
- <span data-ttu-id="5f574-202">割り当てられたテストユーザーが必要な資格情報を持っている。</span><span class="sxs-lookup"><span data-stu-id="5f574-202">Your assigned test users have the required credentials.</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="5f574-203">監視ノードの管理</span><span class="sxs-lookup"><span data-stu-id="5f574-203">Managing Watcher Nodes</span></span>
<span data-ttu-id="5f574-204"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="5f574-204"><a name="testuser"> </a></span></span>

<span data-ttu-id="5f574-205">監視ノードで実行される代理トランザクションの変更に加えて、 **set-cswatchernodeconfiguration**コマンドレットを使用して、監視ノードの有効化と無効化、およびテストの実行時に内部 web url または外部 web url のいずれかを使用する監視ノードの構成を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="5f574-205">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="5f574-206">既定では、監視ノードは、すべての有効な代理トランザクションを定期的に実行するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="5f574-206">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="5f574-207">ただし、これらのトランザクションを中断する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="5f574-207">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="5f574-208">たとえば、監視ノードを一時的にネットワークから切り離す場合は、代理トランザクションを実行する理由がありません。</span><span class="sxs-lookup"><span data-stu-id="5f574-208">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="5f574-209">ネットワーク接続がない場合、これらのトランザクションは失敗します。</span><span class="sxs-lookup"><span data-stu-id="5f574-209">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="5f574-210">監視ノードを一時的に無効にするには、Skype for Business Server 管理シェルから次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5f574-210">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="5f574-211">このコマンドは、監視ノードの atl 監視001.litwareinc.com で代理トランザクションの実行を無効にします。</span><span class="sxs-lookup"><span data-stu-id="5f574-211">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="5f574-212">代理トランザクションの実行を再開するには、Enabled プロパティを True ($True) に戻します。</span><span class="sxs-lookup"><span data-stu-id="5f574-212">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="5f574-213">Enabled プロパティを使用して監視ノードをオンまたはオフにできます。</span><span class="sxs-lookup"><span data-stu-id="5f574-213">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="5f574-214">監視ノードを完全に削除する場合は、**Remove-CsWatcherNodeConfiguration** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5f574-214">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="5f574-215">このコマンドは、指定されたコンピューターからすべての監視ノード構成設定を削除します。これにより、そのコンピューターは代理トランザクションを自動的に実行することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="5f574-215">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="5f574-216">ただし、このコマンドを実行しても、System Center エージェントファイルまたは Skype for Business Server システムファイルはアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="5f574-216">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="5f574-217">既定では、監視ノードはテストを実施するときに組織の外部 Web Url を使用します。</span><span class="sxs-lookup"><span data-stu-id="5f574-217">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="5f574-218">ただし、監視ノードは、組織の内部 Web Url を使用するように構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="5f574-218">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="5f574-219">これにより、管理者は、境界ネットワーク内に配置されたユーザーの URL アクセスを検証できます。</span><span class="sxs-lookup"><span data-stu-id="5f574-219">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="5f574-220">外部 Url の代わりに内部 Url を使用するように監視ノードを構成するには、UseInternalWebURls プロパティを True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="5f574-220">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="5f574-221">このプロパティを既定値の False ($False) にリセットすると、ウォッチャーが再び外部 Url を使用するようになります。</span><span class="sxs-lookup"><span data-stu-id="5f574-221">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="5f574-222">代理トランザクションの特別なセットアップ指示</span><span class="sxs-lookup"><span data-stu-id="5f574-222">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="5f574-223"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="5f574-223"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="5f574-224">ほとんどの代理トランザクションは、監視ノードでそのように実行できます。</span><span class="sxs-lookup"><span data-stu-id="5f574-224">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="5f574-225">ほとんどの場合、代理トランザクションが監視ノード構成設定に追加されると、監視ノードはその代理トランザクションの使用をテストパス中にすぐに開始できます。</span><span class="sxs-lookup"><span data-stu-id="5f574-225">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="5f574-226">ただし、以下のセクションで説明するように、特別なセットアップ手順を必要とする代理トランザクションがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="5f574-226">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="5f574-227">データ会議代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="5f574-227">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="5f574-228">監視ノードコンピューターが境界ネットワークの外部に配置されている場合、最初にネットワークの Internet browser プロキシ設定® Windows Internet Explorer を無効にした場合を除き、データ会議の代理トランザクションを実行できないことがあります。サービスアカウントの場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5f574-228">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="5f574-229">監視ノードコンピューターで、[**スタート**] ボタン、[**すべてのプログラム**]、[**アクセサリ**] の順にクリックし、[**コマンドプロンプト**] を右クリックし、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f574-229">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="5f574-230">コンソールウィンドウで、次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5f574-230">In the console window, type the following command and then press ENTER.</span></span> 
    
    ```console
    bitsadmin /util /SetIEProxy NetworkService NO_PROXY
    ```

    <span data-ttu-id="5f574-231">コマンドウィンドウに次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f574-231">You will see the following message displayed in the command window:</span></span>

    ```console
    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
  
    Internet proxy settings for account NetworkService set to NO_PROXY. 
      
    (connection = default)
    ```
      
    <span data-ttu-id="5f574-232">このメッセージは、ネットワークサービスアカウントの Internet Explorer プロキシ設定が無効になっていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="5f574-232">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="5f574-233">Exchange ユニファイドメッセージング代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="5f574-233">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="5f574-234">Exchange ユニファイドメッセージング (UM) 代理トランザクションは、テストユーザーが Exchange に所属しているボイスメールアカウントに接続できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5f574-234">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="5f574-235">テストユーザーは、ボイスメールアカウントを使用して事前に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-235">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="5f574-236">常設チャット代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="5f574-236">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="5f574-237">常設チャット代理トランザクションを使用するには、まずチャネルを作成し、それを使用するためのアクセス許可をテストユーザーに付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-237">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="5f574-238">常設チャット代理トランザクションを使用して、このチャネルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5f574-238">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```powershell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="5f574-239">このセットアップタスクは、エンタープライズ内部から実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-239">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="5f574-240">サーバー以外のコンピューターから実行する場合、コマンドレットを実行するユーザーは、役割ベースのアクセス制御 (RBAC) の CsPersistentChatAdministrators 役割のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-240">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="5f574-241">サーバー自体から実行する場合、コマンドレットを実行するユーザーは、RTCUniversalServerAdmins グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-241">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="5f574-242">PSTN ピアツーピア通話代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="5f574-242">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="5f574-243">テスト-CsPstnPeerToPeerCall 代理トランザクションは、公衆交換電話網 (PSTN) を使用して通話を発信および受信できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5f574-243">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="5f574-244">この代理トランザクションを実行するには、次のものを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-244">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="5f574-245">2つの UC 対応テストユーザー (発信者と受信者)。</span><span class="sxs-lookup"><span data-stu-id="5f574-245">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="5f574-246">各ユーザー アカウントのダイレクト インワード ダイヤリング (DID) 番号。</span><span class="sxs-lookup"><span data-stu-id="5f574-246">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="5f574-247">受信者の番号への通話が PSTN ゲートウェイに到達できるようにする VoIP ポリシーと音声ルート。</span><span class="sxs-lookup"><span data-stu-id="5f574-247">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="5f574-248">通話を受信し、ダイヤルされた番号に基づいて受信者のホームプールに通話を戻す PSTN ゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="5f574-248">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="5f574-249">統合連絡先ストア代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="5f574-249">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="5f574-250">統合連絡先ストア代理トランザクションは、Exchange からユーザーの代わりに、Skype for Business Server が連絡先を取得できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5f574-250">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="5f574-251">この代理トランザクションを使用するには、次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-251">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="5f574-252">一 ss-Exchange サーバーからサーバーへの認証を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-252">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="5f574-253">テストユーザーは、有効な Exchange メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-253">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="5f574-254">これらの条件が満たされたら、次の Windows PowerShell コマンドレットを実行して、テストユーザーの連絡先リストを Exchange に移行できます。</span><span class="sxs-lookup"><span data-stu-id="5f574-254">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="5f574-255">テストユーザーの連絡先リストが Exchange に移行されるまでに時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-255">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="5f574-256">移行の進行状況を監視するために、-Setup フラグを使用せずに、同じコマンドラインを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5f574-256">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="5f574-257">このコマンドラインは、移行が完了した後に成功します。</span><span class="sxs-lookup"><span data-stu-id="5f574-257">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="5f574-258">XMPP 代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="5f574-258">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="5f574-259">拡張メッセージングおよびプレゼンスプロトコル (XMPP) IM 代理トランザクションでは、XMPP 機能を1つ以上のフェデレーションドメインで構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-259">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="5f574-260">XMPP 代理トランザクションを有効にするには、XmppTestReceiverMailAddress パラメーターに、ルーティング可能な XMPP ドメインのユーザーアカウントを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-260">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="5f574-261">例:</span><span class="sxs-lookup"><span data-stu-id="5f574-261">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="5f574-262">この例では、litwareinc.com のメッセージを XMPP ゲートウェイにルーティングするために、Skype for Business Server ルールが存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-262">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="5f574-263">XMPP ゲートウェイおよびプロキシは、Skype for business Server 2015 で利用できますが、Skype for business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="5f574-263">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="5f574-264">詳細については、「 [XMPP フェデレーションの移行](../../../SfBServer2019/migration/migrating-xmpp-federation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f574-264">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="5f574-265">ビデオ相互運用サーバー (VIS) 代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="5f574-265">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="5f574-266">ビデオ相互運用サーバー (VIS) 代理トランザクションを使用するには、代理トランザクションサポートファイル ([VISSTSupportPackage](https://www.microsoft.com/download/details.aspx?id=46921)) をダウンロードしてインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-266">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="5f574-267">VISSTSupportPackage をインストールするには、msi の依存関係 (システム要件の下) が既にインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5f574-267">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="5f574-268">VISSTSupportPackage を実行して、単純なインストールを実行します。</span><span class="sxs-lookup"><span data-stu-id="5f574-268">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="5f574-269">.Msi は、次のパスにあるすべてのファイルをインストールします。 "%ProgramFiles%\VIS 代理トランザクションサポートパッケージ"。</span><span class="sxs-lookup"><span data-stu-id="5f574-269">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="5f574-270">VIS 代理トランザクションの実行方法の詳細については、 [CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx)コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f574-270">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="5f574-271">代理トランザクションの実行頻度の変更</span><span class="sxs-lookup"><span data-stu-id="5f574-271">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="5f574-272"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="5f574-272"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="5f574-273">既定では、代理トランザクションは構成済みのユーザーと共に15分ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="5f574-273">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="5f574-274">代理トランザクションは、2つの代理トランザクションが互いに競合しないように、一連のユーザーの間で順次実行されます。</span><span class="sxs-lookup"><span data-stu-id="5f574-274">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="5f574-275">すべての代理トランザクションの完了時間を提供するには、より長い間隔が必要です。</span><span class="sxs-lookup"><span data-stu-id="5f574-275">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="5f574-276">代理トランザクションをより頻繁に実行することが望ましい場合は、特定のユーザーセットで実行される代理トランザクションの数を減らす必要があります。これにより、一定の時間範囲内で、長時間のネットワーク遅延のためのバッファーを使用してテストを完了できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5f574-276">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="5f574-277">代理トランザクションをさらに実行する必要がある場合は、追加の代理トランザクションを実行するために、より多くのユーザーセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="5f574-277">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="5f574-278">代理トランザクションが実行される頻度を変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5f574-278">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="5f574-279">System Center Operations Manager を開きます。</span><span class="sxs-lookup"><span data-stu-id="5f574-279">Open System Center Operations Manager.</span></span> <span data-ttu-id="5f574-280">[作成] セクションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f574-280">Click Authoring section.</span></span> <span data-ttu-id="5f574-281">[ルール] セクション ([作成中] の下) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f574-281">Click Rules section (under Authoring).</span></span>
    
2. <span data-ttu-id="5f574-282">[ルール] セクションで、"Main 代理トランザクションランナー Performance Collection Rule" という名前のルールを見つけます。</span><span class="sxs-lookup"><span data-stu-id="5f574-282">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule".</span></span>
    
3. <span data-ttu-id="5f574-283">ルールを右クリックして [上書き] を選択し、[ルールを上書きする] を選択してから、[class: Pool Watcher のすべてのオブジェクト] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5f574-283">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher".</span></span>
    
4. <span data-ttu-id="5f574-284">[プロパティのオーバーライド] ウィンドウで、[パラメーター名 "頻度"] を選択し、Override 値を目的の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="5f574-284">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="5f574-285">同じウィンドウで、この上書きを適用する必要がある管理パックを選択します。</span><span class="sxs-lookup"><span data-stu-id="5f574-285">In the same window, select the Management pack to which this override needs to be applied.</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="5f574-286">代理トランザクションのリッチ ログの使用</span><span class="sxs-lookup"><span data-stu-id="5f574-286">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="5f574-287"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="5f574-287"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="5f574-288">代理トランザクションは、システムの問題を特定するのに役立つように、非常に役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="5f574-288">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="5f574-289">たとえば、ユーザーが Skype for Business Server に登録するのに苦労していたことを管理者に通知するには、Test-CsRegistration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5f574-289">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="5f574-290">ただし、エラーの実際の原因を特定するには、追加の詳細が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-290">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="5f574-291">このため、代理トランザクションには豊富なログ記録が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5f574-291">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="5f574-292">リッチログを使用すると、代理トランザクションが undertakes するアクティビティごとに、次の情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="5f574-292">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="5f574-293">アクティビティが開始された時刻。</span><span class="sxs-lookup"><span data-stu-id="5f574-293">The time that the activity started.</span></span>
    
- <span data-ttu-id="5f574-294">アクティビティが終了した時刻。</span><span class="sxs-lookup"><span data-stu-id="5f574-294">The time that the activity finished.</span></span>
    
- <span data-ttu-id="5f574-295">実行されたアクション (会議の作成、参加、または退室、Skype for Business Server へのサインオン、インスタントメッセージの送信など)。</span><span class="sxs-lookup"><span data-stu-id="5f574-295">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="5f574-296">アクティビティが実行されたときに生成された情報、詳細、警告、またはエラーメッセージ。</span><span class="sxs-lookup"><span data-stu-id="5f574-296">Informational, verbose, warning, or error messages generated when the activity ran.</span></span>
    
- <span data-ttu-id="5f574-297">SIP 登録メッセージ。</span><span class="sxs-lookup"><span data-stu-id="5f574-297">SIP registration messages.</span></span>
    
- <span data-ttu-id="5f574-298">アクティビティの実行時に生成された例外レコードまたは診断コード。</span><span class="sxs-lookup"><span data-stu-id="5f574-298">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="5f574-299">アクティビティを実行した最終的な結果。</span><span class="sxs-lookup"><span data-stu-id="5f574-299">The net result of running the activity.</span></span>
    
<span data-ttu-id="5f574-300">この情報は、代理トランザクションが実行されるたびに自動的に生成されますが、自動的に表示されたり、ログファイルに保存されたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="5f574-300">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="5f574-301">代理トランザクションを手動で実行している場合は、OutLoggerVariable パラメーターを使用して、情報を格納する Windows PowerShell 変数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5f574-301">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="5f574-302">そこから、2つの方法のいずれかを使用して、リッチログのエラーメッセージを XML 形式または HTML 形式で保存したり、表示したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5f574-302">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="5f574-303">トラブルシューティング情報を取得するには、OutLoggerVariable パラメーターを指定し、その後に任意の変数名を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f574-303">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="5f574-304">変数名の前に $ 記号を付けないでください。</span><span class="sxs-lookup"><span data-stu-id="5f574-304">Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="5f574-305">RegistrationTest ($RegistrationTest ではない) などの変数名を使用します。</span><span class="sxs-lookup"><span data-stu-id="5f574-305">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="5f574-306">このコマンドを実行すると、次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f574-306">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="5f574-307">ターゲット Fqdn: atl-cs-001.litwareinc.com Result: エラー待機時間: 00:00:00 エラーメッセージ: このコンピューターには、割り当てられた証明書がありません。</span><span class="sxs-lookup"><span data-stu-id="5f574-307">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="5f574-308">診断: このエラーの詳細については、ここに示すエラーメッセージだけではなく、さらに多くの情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5f574-308">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span>

<span data-ttu-id="5f574-309">HTML 形式でこの情報にアクセスするには、次のようなコマンドを使用して、変数 RegistrationTest に格納されている情報を HTML ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="5f574-309">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="5f574-310">別の方法として、ToXML() メソッドを使用して、XML ファイルにデータを保存できます。</span><span class="sxs-lookup"><span data-stu-id="5f574-310">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="5f574-311">これらのファイルを表示するには、Windows Internet Explorer、Microsoft Visual Studio、または HTML/XML ファイルを開くことができるその他のアプリケーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="5f574-311">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="5f574-312">System Center Operations Manager の内部から実行される代理トランザクションは、エラーが発生したときにこれらのログファイルを自動的に生成します。</span><span class="sxs-lookup"><span data-stu-id="5f574-312">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="5f574-313">これらのログは、Skype for Business Server PowerShell が代理トランザクションを読み込んで実行できるようになる前に、実行が失敗した場合は生成されません。</span><span class="sxs-lookup"><span data-stu-id="5f574-313">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5f574-314">既定では、Skype for Business Server は、共有されていないフォルダーにログファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="5f574-314">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="5f574-315">これらのログに容易にアクセスできるようにするには、このフォルダーを共有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f574-315">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="5f574-316">次に例\\を示します。 litwareinc。 com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="5f574-316">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
