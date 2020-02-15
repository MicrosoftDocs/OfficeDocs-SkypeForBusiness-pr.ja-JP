---
title: 監視ノードのテストユーザーと構成設定の構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5373984e3a4349d73974d9f3b6c243999fbb165
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="4a05d-102">Lync Server 2013 で監視ノードのテストユーザーと構成設定を構成する</span><span class="sxs-lookup"><span data-stu-id="4a05d-102">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a05d-103">_**トピックの最終更新日:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="4a05d-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="4a05d-104">監視ノードとして動作するコンピューターを構成した後、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a05d-104">After configuring the computer that will act as a watcher node, you must:</span></span>

1.  <span data-ttu-id="4a05d-105">これらの監視ノードによって使用されるテストアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="4a05d-105">Create the test accounts to be used by these watcher nodes.</span></span> <span data-ttu-id="4a05d-106">Negotiate の認証方法を使用している場合は、 [set-cstestusercredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15))コマンドレットを使用して、監視ノードで使用するためにこれらのテストアカウントを有効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="4a05d-106">If you are using the Negotiate authentication method, you must also use the [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) cmdlet to enable these test accounts for use on the watcher node.</span></span>

2.  <span data-ttu-id="4a05d-107">監視ノードの構成設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="4a05d-107">Update the watcher node configuration settings.</span></span>

<span data-ttu-id="4a05d-108">このセクションの内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4a05d-108">This section covers:</span></span>

  - <span data-ttu-id="4a05d-109">テストユーザーアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="4a05d-109">Configuring Test User Accounts</span></span>

  - <span data-ttu-id="4a05d-110">既定の代理トランザクションを使用した基本的な監視ノードの構成</span><span class="sxs-lookup"><span data-stu-id="4a05d-110">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

  - <span data-ttu-id="4a05d-111">拡張テストの構成</span><span class="sxs-lookup"><span data-stu-id="4a05d-111">Configuring Extended Tests</span></span>

  - <span data-ttu-id="4a05d-112">代理トランザクションの追加と削除</span><span class="sxs-lookup"><span data-stu-id="4a05d-112">Adding and Removing Synthetic Transactions</span></span>

  - <span data-ttu-id="4a05d-113">監視ノード構成の表示とテスト</span><span class="sxs-lookup"><span data-stu-id="4a05d-113">Viewing and Testing the Watcher Node Configuration</span></span>

<div>

## <a name="configuring-test-user-accounts"></a><span data-ttu-id="4a05d-114">テストユーザーアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="4a05d-114">Configuring Test User Accounts</span></span>

<span data-ttu-id="4a05d-115">テストユーザーは、実際の人物を表す必要はありませんが、有効な Active Directory ドメインサービスアカウントである必要があります。さらに、これらのアカウントは Lync Server 2013 に対して有効にする必要があります。また、有効な SIP アドレスを持っている必要があります。また、エンタープライズ Voip を有効にする必要があります (テスト-CsPstnPeerToPeerCall 代理トランザクションを使用する場合)。</span><span class="sxs-lookup"><span data-stu-id="4a05d-115">Test users do not need to represent actual people, but they must be valid Active Directory Domain Services accounts; in addition, these accounts must be enabled for Lync Server 2013, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> <span data-ttu-id="4a05d-116">TrustedServer の認証方法を使用する場合は、これらのアカウントが存在し、ここで指定したとおりに構成されていることを確認するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="4a05d-116">If you use the TrustedServer authentication method, then all you need to do is to make sure that these accounts exist and have been configured as specified here.</span></span> <span data-ttu-id="4a05d-117">テストする各プールについて、少なくとも3つのテストユーザーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a05d-117">You should assign at least three test users for each pool that you want to test.</span></span>

<span data-ttu-id="4a05d-118">Negotiate の認証方法を使用している場合は、 **set-cstestusercredential**コマンドレットと Lync Server 管理シェルも使用して、これらのテストアカウントが代理トランザクションと連携できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a05d-118">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet and the Lync Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="4a05d-119">これを行うには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4a05d-119">You can do this by running a command similar to the following.</span></span> <span data-ttu-id="4a05d-120">(これらのコマンドは、3つの Active Directory ユーザーアカウントが既に作成されており、これらのアカウントが Lync Server 2013 に対して有効になっていることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="4a05d-120">(These commands assume that the three Active Directory user accounts have already been created and that those accounts have been enabled for Lync Server 2013.):</span></span>

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

<span data-ttu-id="4a05d-121">SIP アドレスだけでなく、ユーザー名とパスワードも含める必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4a05d-121">Note that you must include not only the SIP address but also the user name and password.</span></span> <span data-ttu-id="4a05d-122">パスワードが設定されていない場合は、Set-cstestusercredential によってその情報の入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="4a05d-122">If you do not include the password Set-CsTestUserCredential will prompt you to enter that information.</span></span> <span data-ttu-id="4a05d-123">ユーザー名を指定するには、上記の\\ドメイン名のユーザー名の形式を使用するか、またはユーザー name@domain 名の形式を使用します。例えば：</span><span class="sxs-lookup"><span data-stu-id="4a05d-123">The user name can be specified using the domain name\\user name format shown above, or by using the format user name@domain name; for example:</span></span>

    -UserName "watcher3@litwareinc.com"

<span data-ttu-id="4a05d-124">テストユーザーの資格情報が作成されたことを確認するには、Lync Server 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4a05d-124">To verify that the test user credentials were created, run these commands from within the Lync Server Management Shell:</span></span>

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

<span data-ttu-id="4a05d-125">次のような情報が各ユーザーに返されます。</span><span class="sxs-lookup"><span data-stu-id="4a05d-125">Information similar to this should be returned for each user:</span></span>

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="4a05d-126">既定の代理トランザクションを使用した基本的な監視ノードの構成</span><span class="sxs-lookup"><span data-stu-id="4a05d-126">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="4a05d-127">テストユーザーが作成されたら、次のようなコマンドを使用して監視ノードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4a05d-127">After the test users have been created you can then create a watcher node by using a command similar to this:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

<span data-ttu-id="4a05d-128">このコマンドは、既定の設定を使用し、代理トランザクションの既定のセットを実行する新しい監視ノードを作成します。</span><span class="sxs-lookup"><span data-stu-id="4a05d-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="4a05d-129">新しい監視ノードは、テストユーザー watcher1@litwareinc.com、watcher2@litwareinc.com、および watcher3@litwareinc.com も使用します。</span><span class="sxs-lookup"><span data-stu-id="4a05d-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="4a05d-130">監視ノードが TrustedServer 認証を使用している場合、3つのテストアカウントは、Active Directory および Lync Server に対して有効になっている任意の有効なユーザーアカウントにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4a05d-130">If the watcher node is using TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Lync Server.</span></span> <span data-ttu-id="4a05d-131">監視ノードが Negotiate 認証方法を使用している場合は、 **set-cstestusercredential**コマンドレットを使用して、監視ノードに対してこれらのユーザーアカウントを有効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="4a05d-131">If the watcher node is using the Negotiate authentication method, you must also enable these user accounts for watcher node by using the **Set-CsTestUserCredential** cmdlet.</span></span>

</div>

<div>

## <a name="configuring-extended-tests"></a><span data-ttu-id="4a05d-132">拡張テストの構成</span><span class="sxs-lookup"><span data-stu-id="4a05d-132">Configuring Extended Tests</span></span>

<span data-ttu-id="4a05d-133">公衆交換電話網との接続を確認する公衆交換電話網 (PSTN テスト) を有効にする場合は、監視ノードを設定するときに追加の構成を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a05d-133">If you want to enable the public switched telephone network (PSTN test), which verifies connectivity with the public switched telephone network, you will need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="4a05d-134">最初に、テストユーザーを PSTN テストの種類に関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a05d-134">First, you need to associate your test users with the PSTN test type.</span></span> <span data-ttu-id="4a05d-135">そのためには、Lync Server 管理シェルで次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4a05d-135">To do that, run a command similar to this from within the Lync Server Management Shell:</span></span>

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

<span data-ttu-id="4a05d-136">このコマンドの結果は変数に格納する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4a05d-136">Note that the results of this command must be stored in a variable.</span></span> <span data-ttu-id="4a05d-137">この例では、$pstnTest という名前の変数です。</span><span class="sxs-lookup"><span data-stu-id="4a05d-137">In this example, that's a variable named $pstnTest.</span></span>

<span data-ttu-id="4a05d-138">この時点で、 **set-cswatchernodeconfiguration**コマンドレットを使用して、テストの種類 (変数 $pstnTest に格納されている) を Lync Server 2013 プールに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="4a05d-138">At this point, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Lync Server 2013 pool.</span></span> <span data-ttu-id="4a05d-139">たとえば、次のコマンドは、プール atl-cs-001.litwareinc.com の新しい監視ノード構成を作成し、以前に作成した3つのテストユーザーを追加し、さらに PSTN テストの種類も追加します。</span><span class="sxs-lookup"><span data-stu-id="4a05d-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users that were created previously, and also adding the PSTN test type:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

<span data-ttu-id="4a05d-140">なお、監視ノードコンピューターに Lync Server コアファイルと RTCLocal データベースをインストールしていない場合は、上記のコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="4a05d-140">Note that the preceding command will fail if you have not installed the Lync Server core files and the RTCLocal database on the watcher node computer.</span></span>

<span data-ttu-id="4a05d-141">複数の音声ポリシーをテストするには、**新しい-Csexthe dedtest**コマンドレットを使用して、各ポリシーの拡張テストを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a05d-141">To test multiple voice policies, you need to create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="4a05d-142">このテストに割り当てられているユーザーは、目的の音声ポリシーを使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a05d-142">The users assigned to this test should be configured with the desired voice policies.</span></span> <span data-ttu-id="4a05d-143">拡張テストは、次のようなコマンドを使用して、 **set-cswatchernodeconfiguration**コマンドレットに渡されます。</span><span class="sxs-lookup"><span data-stu-id="4a05d-143">The extended tests are then passed to the **New-CsWatcherNodeConfiguration** cmdlet by using a command similar to the following:</span></span>

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

<span data-ttu-id="4a05d-144">Set-cswatchernodeconfiguration が Tests パラメーターを使用せずに呼び出された場合は、既定の代理トランザクション (および指定された拡張代理トランザクション) だけが新しい監視ノードに対して有効になることを意味します。</span><span class="sxs-lookup"><span data-stu-id="4a05d-144">If New-CsWatcherNodeConfiguration is called without using the Tests parameter, that means that only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="4a05d-145">これは、監視ノードが次のコンポーネントをテストすることを意味します。</span><span class="sxs-lookup"><span data-stu-id="4a05d-145">This means that the watcher node will test the following components:</span></span>

  - <span data-ttu-id="4a05d-146">レジスタ</span><span class="sxs-lookup"><span data-stu-id="4a05d-146">Registration</span></span>

  - <span data-ttu-id="4a05d-147">IM</span><span class="sxs-lookup"><span data-stu-id="4a05d-147">IM</span></span>

  - <span data-ttu-id="4a05d-148">GroupIM</span><span class="sxs-lookup"><span data-stu-id="4a05d-148">GroupIM</span></span>

  - <span data-ttu-id="4a05d-149">P2PAV (ピアツーピアの音声ビデオセッション)</span><span class="sxs-lookup"><span data-stu-id="4a05d-149">P2PAV (peer-to-peer audio/video sessions)</span></span>

  - <span data-ttu-id="4a05d-150">AvConference (音声/会議)</span><span class="sxs-lookup"><span data-stu-id="4a05d-150">AvConference (audio/conferencing)</span></span>

  - <span data-ttu-id="4a05d-151">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="4a05d-151">Presence</span></span>

  - <span data-ttu-id="4a05d-152">ABS (アドレス帳サービス)</span><span class="sxs-lookup"><span data-stu-id="4a05d-152">ABS (Address Book service)</span></span>

  - <span data-ttu-id="4a05d-153">ABWQ (アドレス帳 web サービス)</span><span class="sxs-lookup"><span data-stu-id="4a05d-153">ABWQ (Address Book web service)</span></span>

  - <span data-ttu-id="4a05d-154">PSTN (PSTN ゲートウェイ呼び出し。拡張テストとして指定されます。</span><span class="sxs-lookup"><span data-stu-id="4a05d-154">PSTN (PSTN gateway calls, specified as an extended test.</span></span> <span data-ttu-id="4a05d-155">既定では、PSTN は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="4a05d-155">By default, PSTN is disabled.</span></span> <span data-ttu-id="4a05d-156">この場合、このテストは、コマンドが ExtendedTests パラメーターを使用して PSTN を有効にしている場合にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="4a05d-156">The test is enabled in this case only because the command enabled PSTN by using the ExtendedTests parameter.)</span></span>

<span data-ttu-id="4a05d-157">これは、次のコンポーネントが既定ではテストされないことも意味します。</span><span class="sxs-lookup"><span data-stu-id="4a05d-157">This also means that the following components will not be tested by default:</span></span>

  - <span data-ttu-id="4a05d-158">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="4a05d-158">AVEdgeConnectivity</span></span>

  - <span data-ttu-id="4a05d-159">MCXP2PIM (モバイルデバイスインスタントメッセージング)</span><span class="sxs-lookup"><span data-stu-id="4a05d-159">MCXP2PIM (mobile device instant messaging)</span></span>

  - <span data-ttu-id="4a05d-160">ExumConnectivity (Exchange ユニファイドメッセージング)</span><span class="sxs-lookup"><span data-stu-id="4a05d-160">ExumConnectivity (Exchange Unified Messaging)</span></span>

  - <span data-ttu-id="4a05d-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="4a05d-161">JoinLauncher</span></span>

  - <span data-ttu-id="4a05d-162">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="4a05d-162">PersistentChatMessage</span></span>

  - <span data-ttu-id="4a05d-163">DataConference</span><span class="sxs-lookup"><span data-stu-id="4a05d-163">DataConference</span></span>

  - <span data-ttu-id="4a05d-164">XmppIM</span><span class="sxs-lookup"><span data-stu-id="4a05d-164">XmppIM</span></span>

  - <span data-ttu-id="4a05d-165">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="4a05d-165">UnifiedContactStore</span></span>

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="4a05d-166">代理トランザクションの追加と削除</span><span class="sxs-lookup"><span data-stu-id="4a05d-166">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="4a05d-167">監視ノードの構成後、 **set-cswatchernodeconfiguration**コマンドレットを使用して、ノードの代理トランザクションを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="4a05d-167">After a watcher node has been configured, you can use the **Set-CsWatcherNodeConfiguration** cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="4a05d-168">たとえば、監視ノードに PersistentChatMessage テストを追加するには、Add メソッドと次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4a05d-168">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

<span data-ttu-id="4a05d-169">テスト名をコンマで区切ることで、複数のテストを追加できます。</span><span class="sxs-lookup"><span data-stu-id="4a05d-169">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="4a05d-170">例:</span><span class="sxs-lookup"><span data-stu-id="4a05d-170">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

<span data-ttu-id="4a05d-171">これらのテストの1つ以上 (たとえば、DataConference) が既に監視ノードで有効になっている場合は、エラーが発生することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4a05d-171">Note that an error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="4a05d-172">この場合、次のようなエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a05d-172">In this case, you will receive an error message similar to the following:</span></span>

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

<span data-ttu-id="4a05d-173">このエラーが発生した場合、変更は適用されません。</span><span class="sxs-lookup"><span data-stu-id="4a05d-173">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="4a05d-174">重複するテストを削除してコマンドを再実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a05d-174">The command should be rerun with the duplicate test removed.</span></span>

<span data-ttu-id="4a05d-175">監視ノードから代理トランザクションを削除するには、Add メソッドではなく Remove メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4a05d-175">To remove a synthetic transaction from a watcher node, use the Remove method instead of the Add method.</span></span> <span data-ttu-id="4a05d-176">たとえば、次のコマンドを実行すると、監視ノードから ABWQ テストが削除されます。</span><span class="sxs-lookup"><span data-stu-id="4a05d-176">For example, this command removes the ABWQ test from a watcher node:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

<span data-ttu-id="4a05d-177">Replace メソッドを使用して、現在有効になっているすべてのテストを1つまたは複数の新しいテストに置き換えることもできます。</span><span class="sxs-lookup"><span data-stu-id="4a05d-177">You can also use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="4a05d-178">たとえば、監視ノードのみが IM テストを実行するようにする場合は、次のコマンドを使用してそれを構成できます。</span><span class="sxs-lookup"><span data-stu-id="4a05d-178">For example, if you only want a watcher node to run the IM test, you can configure that by using this command:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

<span data-ttu-id="4a05d-179">上記のコマンドを実行すると、指定された監視ノードのすべての代理トランザクションは IM 以外は無効になります。</span><span class="sxs-lookup"><span data-stu-id="4a05d-179">When you run the preceding command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="4a05d-180">監視ノード構成の表示とテスト</span><span class="sxs-lookup"><span data-stu-id="4a05d-180">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="4a05d-181">監視ノードに割り当てられているテストを表示する場合は、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4a05d-181">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

<span data-ttu-id="4a05d-182">上記のコマンドは、ノードに割り当てられている代理トランザクションに応じて、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="4a05d-182">The preceding command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>

    Registration
    IM
    GroupIM
    P2PAV
    AvConference
    Presence
    PersistentChatMessage
    DataConference

<div>


> [!TIP]
> <span data-ttu-id="4a05d-183">代理トランザクションをアルファベット順で表示するには、代わりに次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4a05d-183">To view the synthetic transactions in alphabetical order, use this command instead:</span></span><BR><span data-ttu-id="4a05d-184">Set-cswatchernodeconfiguration – Identity "atl-cs-001.litwareinc.com" |Select-Object – ExpandProperty テスト |Sort-オブジェクト</span><span class="sxs-lookup"><span data-stu-id="4a05d-184">Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object</span></span>



</div>

<span data-ttu-id="4a05d-185">監視ノードが作成されたことを確認するには、Lync Server 管理シェルで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="4a05d-185">To verify that a watcher node has been created, type the following command from within the Lync Server Management Shell:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="4a05d-186">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a05d-186">You will receive information similar to this:</span></span>

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

<span data-ttu-id="4a05d-187">監視ノードが正しく構成されていることを確認するには、Lync Server 管理シェルで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="4a05d-187">To verify that the watcher node has been configured correctly, type the following command from within the Lync Server Management Shell:</span></span>

    Test-CsWatcherNodeConfiguration

<span data-ttu-id="4a05d-188">上記のコマンドにより、展開内の各監視ノードがテストされ、次のような情報がわかります。</span><span class="sxs-lookup"><span data-stu-id="4a05d-188">The preceding command will test each watcher node in your deployment and tell you information, such as whether:</span></span>

  - <span data-ttu-id="4a05d-189">必要なレジストラーの役割がインストールされている。</span><span class="sxs-lookup"><span data-stu-id="4a05d-189">The required Registrar role been installed.</span></span>

  - <span data-ttu-id="4a05d-190">Set-cswatchernodeconfiguration を実行したときに必要なレジストリキーが作成されました。</span><span class="sxs-lookup"><span data-stu-id="4a05d-190">The required registry key was created for you when you ran Set-CsWatcherNodeConfiguration.</span></span>

  - <span data-ttu-id="4a05d-191">サーバーで適切なバージョンの Lync Server が実行されている。</span><span class="sxs-lookup"><span data-stu-id="4a05d-191">Your servers are running the correct version of Lync Server.</span></span>

  - <span data-ttu-id="4a05d-192">ポートが正しく構成されている。</span><span class="sxs-lookup"><span data-stu-id="4a05d-192">Your ports been configured correctly.</span></span>

  - <span data-ttu-id="4a05d-193">割り当てられたテストユーザーが必要な資格情報を持っている。</span><span class="sxs-lookup"><span data-stu-id="4a05d-193">Your assigned test users have the required credentials.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

