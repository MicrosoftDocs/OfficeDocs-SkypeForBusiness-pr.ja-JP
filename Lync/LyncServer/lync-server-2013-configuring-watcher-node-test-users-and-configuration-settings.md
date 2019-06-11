---
title: ウォッチャーノードのテストユーザーと構成設定を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d446934e8d84a12a6eecd84fbc94a956d8ae95e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="12579-102">Lync Server 2013 で監視ノードのテストユーザーと構成設定を構成する</span><span class="sxs-lookup"><span data-stu-id="12579-102">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12579-103">_**最終更新日:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="12579-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="12579-104">監視ノードとして動作するコンピューターを構成したら、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="12579-104">After configuring the computer that will act as a watcher node, you must:</span></span>

1.  <span data-ttu-id="12579-105">これらのウォッチャーノードで使用するテストアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="12579-105">Create the test accounts to be used by these watcher nodes.</span></span> <span data-ttu-id="12579-106">Negotiate の認証方法を使用している場合は、[Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)) コマンドレットを使用し、監視ノードで使用するためにこれらのテスト アカウントを有効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="12579-106">If you are using the Negotiate authentication method, you must also use the [Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)) cmdlet to enable these test accounts for use on the watcher node.</span></span>

2.  <span data-ttu-id="12579-107">監視ノード構成設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="12579-107">Update the watcher node configuration settings.</span></span>

<span data-ttu-id="12579-108">このセクションの内容:</span><span class="sxs-lookup"><span data-stu-id="12579-108">This section covers:</span></span>

  - <span data-ttu-id="12579-109">テストユーザーアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="12579-109">Configuring Test User Accounts</span></span>

  - <span data-ttu-id="12579-110">既定の代理トランザクションを使った基本的なウォッチャーノードの構成</span><span class="sxs-lookup"><span data-stu-id="12579-110">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

  - <span data-ttu-id="12579-111">拡張テストの構成</span><span class="sxs-lookup"><span data-stu-id="12579-111">Configuring Extended Tests</span></span>

  - <span data-ttu-id="12579-112">代理トランザクションの追加と削除</span><span class="sxs-lookup"><span data-stu-id="12579-112">Adding and Removing Synthetic Transactions</span></span>

  - <span data-ttu-id="12579-113">監視ノード構成の表示とテスト</span><span class="sxs-lookup"><span data-stu-id="12579-113">Viewing and Testing the Watcher Node Configuration</span></span>

<div>

## <a name="configuring-test-user-accounts"></a><span data-ttu-id="12579-114">テストユーザーアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="12579-114">Configuring Test User Accounts</span></span>

<span data-ttu-id="12579-115">テストユーザーは、実際のユーザーを表す必要はありませんが、有効な Active Directory ドメインサービスアカウントである必要があります。さらに、これらのアカウントは Lync Server 2013 で有効にしておく必要があります。また、有効な SIP アドレスがある必要があります。また、エンタープライズ Voip を有効にする必要があります (テスト-CsPstnPeerToPeerCall 代理トランザクションを使う場合)。</span><span class="sxs-lookup"><span data-stu-id="12579-115">Test users do not need to represent actual people, but they must be valid Active Directory Domain Services accounts; in addition, these accounts must be enabled for Lync Server 2013, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> <span data-ttu-id="12579-116">TrustedServer 認証方法を使用する場合は、これらのアカウントが存在し、ここで指定したように構成されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12579-116">If you use the TrustedServer authentication method, then all you need to do is to make sure that these accounts exist and have been configured as specified here.</span></span> <span data-ttu-id="12579-117">テストしようとする各プールに対して、少なくとも 3 つのテスト ユーザーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="12579-117">You should assign at least three test users for each pool that you want to test.</span></span>

<span data-ttu-id="12579-118">Negotiate 認証方法を使用している場合は、 **CsTestUserCredential**コマンドレットと Lync Server Management Shell を使って、これらのテストアカウントで代理トランザクションを操作できるようにする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="12579-118">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet and the Lync Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="12579-119">これを行うには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="12579-119">You can do this by running a command similar to the following.</span></span> <span data-ttu-id="12579-120">(これらのコマンドは、3つの Active Directory ユーザーアカウントが既に作成されていて、それらのアカウントが Lync Server 2013 用に有効になっていることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="12579-120">(These commands assume that the three Active Directory user accounts have already been created and that those accounts have been enabled for Lync Server 2013.):</span></span>

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

<span data-ttu-id="12579-121">SIP アドレスだけでなく、ユーザー名とパスワードも含める必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="12579-121">Note that you must include not only the SIP address but also the user name and password.</span></span> <span data-ttu-id="12579-122">パスワードを指定しない場合、CsTestUserCredential によって情報の入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="12579-122">If you do not include the password Set-CsTestUserCredential will prompt you to enter that information.</span></span> <span data-ttu-id="12579-123">ユーザー名は、上記のドメイン名\\のユーザー名形式、またはユーザー名 @ ドメイン名の形式を使用して指定できます。例えば：</span><span class="sxs-lookup"><span data-stu-id="12579-123">The user name can be specified using the domain name\\user name format shown above, or by using the format user name@domain name; for example:</span></span>

    -UserName "watcher3@litwareinc.com"

<span data-ttu-id="12579-124">テストユーザーの資格情報が作成されたことを確認するには、Lync Server 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="12579-124">To verify that the test user credentials were created, run these commands from within the Lync Server Management Shell:</span></span>

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

<span data-ttu-id="12579-125">このような情報は、ユーザーごとに返されます。</span><span class="sxs-lookup"><span data-stu-id="12579-125">Information similar to this should be returned for each user:</span></span>

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="12579-126">既定の代理トランザクションを使った基本的なウォッチャーノードの構成</span><span class="sxs-lookup"><span data-stu-id="12579-126">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="12579-127">テストユーザーが作成された後、次のようなコマンドを使用してウォッチャーノードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="12579-127">After the test users have been created you can then create a watcher node by using a command similar to this:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

<span data-ttu-id="12579-128">このコマンドでは、既定の設定を使用し、既定の代理トランザクションのセットを実行する新しい監視ノードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="12579-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="12579-129">新しい監視ノードでは、watcher1@litwareinc.com、watcher2@litwareinc.com、および watcher3@litwareinc.com のテスト ユーザーを使用します。</span><span class="sxs-lookup"><span data-stu-id="12579-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="12579-130">ウォッチャーノードが TrustedServer 認証を使用している場合、3つのテストアカウントは Active Directory と Lync Server で有効になっている有効なユーザーアカウントにすることができます。</span><span class="sxs-lookup"><span data-stu-id="12579-130">If the watcher node is using TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Lync Server.</span></span> <span data-ttu-id="12579-131">ウォッチャーノードが Negotiate 認証方法を使用している場合は、 **CsTestUserCredential**コマンドレットを使用して、ウォッチャーノードに対してもこれらのユーザーアカウントを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="12579-131">If the watcher node is using the Negotiate authentication method, you must also enable these user accounts for watcher node by using the **Set-CsTestUserCredential** cmdlet.</span></span>

</div>

<div>

## <a name="configuring-extended-tests"></a><span data-ttu-id="12579-132">拡張テストの構成</span><span class="sxs-lookup"><span data-stu-id="12579-132">Configuring Extended Tests</span></span>

<span data-ttu-id="12579-133">公衆交換電話網 (PSTN テスト) を有効にして、公衆交換電話網との接続を確認する場合は、ウォッチャーノードを設定するときに追加の構成を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="12579-133">If you want to enable the public switched telephone network (PSTN test), which verifies connectivity with the public switched telephone network, you will need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="12579-134">最初に、テストユーザーに PSTN テストの種類を関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="12579-134">First, you need to associate your test users with the PSTN test type.</span></span> <span data-ttu-id="12579-135">そのためには、Lync Server 管理シェルで次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="12579-135">To do that, run a command similar to this from within the Lync Server Management Shell:</span></span>

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

<span data-ttu-id="12579-136">このコマンドの結果は、変数に格納する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="12579-136">Note that the results of this command must be stored in a variable.</span></span> <span data-ttu-id="12579-137">この例では、$pstnTest という名前の変数です。</span><span class="sxs-lookup"><span data-stu-id="12579-137">In this example, that's a variable named $pstnTest.</span></span>

<span data-ttu-id="12579-138">この時点で、 **CsWatcherNodeConfiguration**コマンドレットを使用して、テストの種類 (可変 $pstnTest) を Lync Server 2013 プールに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="12579-138">At this point, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Lync Server 2013 pool.</span></span> <span data-ttu-id="12579-139">たとえば、次のコマンドは、プール atl-cs-001.litwareinc.com の新しいウォッチャーノード構成を作成し、前に作成した3つのテストユーザーを追加して、PSTN テストタイプも追加します。</span><span class="sxs-lookup"><span data-stu-id="12579-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users that were created previously, and also adding the PSTN test type:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

<span data-ttu-id="12579-140">Communicator ノードコンピューターに Lync Server core ファイルと RTCLocal データベースをインストールしていない場合は、上記のコマンドが失敗します。</span><span class="sxs-lookup"><span data-stu-id="12579-140">Note that the preceding command will fail if you have not installed the Lync Server core files and the RTCLocal database on the watcher node computer.</span></span>

<span data-ttu-id="12579-141">複数のボイスポリシーをテストするには、**新しい-Csex・ Deddedtest**コマンドレットを使用して、各ポリシーの拡張テストを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12579-141">To test multiple voice policies, you need to create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="12579-142">このテストに割り当てられているユーザーは、目的の音声ポリシーで構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12579-142">The users assigned to this test should be configured with the desired voice policies.</span></span> <span data-ttu-id="12579-143">その後、次のようなコマンドを使用して、拡張テストを**新しい-CsWatcherNodeConfiguration**コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="12579-143">The extended tests are then passed to the **New-CsWatcherNodeConfiguration** cmdlet by using a command similar to the following:</span></span>

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

<span data-ttu-id="12579-144">CsWatcherNodeConfiguration が Tests パラメーターを使用せずに呼び出された場合は、既定の代理トランザクション (および指定された拡張合成トランザクション) だけが新しいウォッチャーノードに対して有効になることを意味します。</span><span class="sxs-lookup"><span data-stu-id="12579-144">If New-CsWatcherNodeConfiguration is called without using the Tests parameter, that means that only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="12579-145">これは、ウォッチャーノードが次のコンポーネントをテストすることを意味します。</span><span class="sxs-lookup"><span data-stu-id="12579-145">This means that the watcher node will test the following components:</span></span>

  - <span data-ttu-id="12579-146">Registration</span><span class="sxs-lookup"><span data-stu-id="12579-146">Registration</span></span>

  - <span data-ttu-id="12579-147">IM</span><span class="sxs-lookup"><span data-stu-id="12579-147">IM</span></span>

  - <span data-ttu-id="12579-148">GroupIM</span><span class="sxs-lookup"><span data-stu-id="12579-148">GroupIM</span></span>

  - <span data-ttu-id="12579-149">P2PAV (ピアツーピアの音声/ビデオ セッション)</span><span class="sxs-lookup"><span data-stu-id="12579-149">P2PAV (peer-to-peer audio/video sessions)</span></span>

  - <span data-ttu-id="12579-150">AvConference (音声/会議)</span><span class="sxs-lookup"><span data-stu-id="12579-150">AvConference (audio/conferencing)</span></span>

  - <span data-ttu-id="12579-151">Presence</span><span class="sxs-lookup"><span data-stu-id="12579-151">Presence</span></span>

  - <span data-ttu-id="12579-152">ABS (アドレス帳サービス)</span><span class="sxs-lookup"><span data-stu-id="12579-152">ABS (Address Book service)</span></span>

  - <span data-ttu-id="12579-153">ABWQ (アドレス帳 Web サービス)</span><span class="sxs-lookup"><span data-stu-id="12579-153">ABWQ (Address Book web service)</span></span>

  - <span data-ttu-id="12579-154">PSTN (拡張テストとして指定された pstn ゲートウェイ通話)。</span><span class="sxs-lookup"><span data-stu-id="12579-154">PSTN (PSTN gateway calls, specified as an extended test.</span></span> <span data-ttu-id="12579-155">既定では、PSTN は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="12579-155">By default, PSTN is disabled.</span></span> <span data-ttu-id="12579-156">この場合、テストは、コマンドによって ExtendedTests パラメーターを使って PSTN が有効になっている場合にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="12579-156">The test is enabled in this case only because the command enabled PSTN by using the ExtendedTests parameter.)</span></span>

<span data-ttu-id="12579-157">これは、既定では次のコンポーネントがテストされないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="12579-157">This also means that the following components will not be tested by default:</span></span>

  - <span data-ttu-id="12579-158">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="12579-158">AVEdgeConnectivity</span></span>

  - <span data-ttu-id="12579-159">MCXP2PIM (モバイル デバイス インスタント メッセージング)</span><span class="sxs-lookup"><span data-stu-id="12579-159">MCXP2PIM (mobile device instant messaging)</span></span>

  - <span data-ttu-id="12579-160">ExumConnectivity (Exchange ユニファイド メッセージング)</span><span class="sxs-lookup"><span data-stu-id="12579-160">ExumConnectivity (Exchange Unified Messaging)</span></span>

  - <span data-ttu-id="12579-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="12579-161">JoinLauncher</span></span>

  - <span data-ttu-id="12579-162">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="12579-162">PersistentChatMessage</span></span>

  - <span data-ttu-id="12579-163">DataConference</span><span class="sxs-lookup"><span data-stu-id="12579-163">DataConference</span></span>

  - <span data-ttu-id="12579-164">XmppIM</span><span class="sxs-lookup"><span data-stu-id="12579-164">XmppIM</span></span>

  - <span data-ttu-id="12579-165">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="12579-165">UnifiedContactStore</span></span>

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="12579-166">代理トランザクションの追加と削除</span><span class="sxs-lookup"><span data-stu-id="12579-166">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="12579-167">ウォッチャーノードが構成されると、 **CsWatcherNodeConfiguration**コマンドレットを使用して、ノードの合成トランザクションを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="12579-167">After a watcher node has been configured, you can use the **Set-CsWatcherNodeConfiguration** cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="12579-168">たとえば、監視ノードに PersistentChatMessage テストを追加するには Add メソッドと次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="12579-168">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

<span data-ttu-id="12579-169">テスト名をコンマで区切ることにより、複数のテストを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="12579-169">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="12579-170">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="12579-170">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

<span data-ttu-id="12579-171">このようなテスト (たとえば、DataConference) がウォッチャーノードで既に有効になっている場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="12579-171">Note that an error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="12579-172">この場合、次のようなエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="12579-172">In this case, you will receive an error message similar to the following:</span></span>

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

<span data-ttu-id="12579-173">このエラーが発生した場合、変更は一切適用されません。</span><span class="sxs-lookup"><span data-stu-id="12579-173">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="12579-174">重複したテストを削除してコマンドを再実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12579-174">The command should be rerun with the duplicate test removed.</span></span>

<span data-ttu-id="12579-175">ウォッチャーノードから合成トランザクションを削除するには、Add メソッドの代わりに Remove メソッドを使います。</span><span class="sxs-lookup"><span data-stu-id="12579-175">To remove a synthetic transaction from a watcher node, use the Remove method instead of the Add method.</span></span> <span data-ttu-id="12579-176">たとえば、次のコマンドでは、監視ノードから ABWQ テストを削除します。</span><span class="sxs-lookup"><span data-stu-id="12579-176">For example, this command removes the ABWQ test from a watcher node:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

<span data-ttu-id="12579-177">また、Replace メソッドを使用して、現在有効になっているすべてのテストを1つまたは複数の新しいテストに置き換えることもできます。</span><span class="sxs-lookup"><span data-stu-id="12579-177">You can also use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="12579-178">たとえば、watcher ノードで IM テストを実行する場合は、次のコマンドを使用してそれを構成できます。</span><span class="sxs-lookup"><span data-stu-id="12579-178">For example, if you only want a watcher node to run the IM test, you can configure that by using this command:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

<span data-ttu-id="12579-179">上のコマンドを実行すると、指定したウォッチャーノードのすべての代理トランザクションが、IM 以外は無効になります。</span><span class="sxs-lookup"><span data-stu-id="12579-179">When you run the preceding command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="12579-180">監視ノード構成の表示とテスト</span><span class="sxs-lookup"><span data-stu-id="12579-180">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="12579-181">監視ノードに割り当てられているテストを表示する場合は、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="12579-181">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

<span data-ttu-id="12579-182">上記のコマンドは、ノードに割り当てられている代理トランザクションに応じて、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="12579-182">The preceding command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>

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
> <span data-ttu-id="12579-183">代理トランザクションをアルファベット順で表示するには、代わりに次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="12579-183">To view the synthetic transactions in alphabetical order, use this command instead:</span></span><BR><span data-ttu-id="12579-184">Get-CsWatcherNodeConfiguration – Identity "atl-cs-001.litwareinc.com" |選択-オブジェクト– ExpandProperty テスト |Sort-Object</span><span class="sxs-lookup"><span data-stu-id="12579-184">Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object</span></span>



</div>

<span data-ttu-id="12579-185">ウォッチャーノードが作成されたことを確認するには、Lync Server 管理シェル内から次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="12579-185">To verify that a watcher node has been created, type the following command from within the Lync Server Management Shell:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="12579-186">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="12579-186">You will receive information similar to this:</span></span>

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

<span data-ttu-id="12579-187">ウォッチャーノードが正しく構成されていることを確認するには、Lync Server 管理シェルで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="12579-187">To verify that the watcher node has been configured correctly, type the following command from within the Lync Server Management Shell:</span></span>

    Test-CsWatcherNodeConfiguration

<span data-ttu-id="12579-188">上のコマンドを実行すると、展開の各ウォッチャーノードがテストされ、次のような情報がわかります。</span><span class="sxs-lookup"><span data-stu-id="12579-188">The preceding command will test each watcher node in your deployment and tell you information, such as whether:</span></span>

  - <span data-ttu-id="12579-189">必要なレジストラー役割がインストールされました。</span><span class="sxs-lookup"><span data-stu-id="12579-189">The required Registrar role been installed.</span></span>

  - <span data-ttu-id="12579-190">CsWatcherNodeConfiguration を実行したときに必要なレジストリキーが作成されました。</span><span class="sxs-lookup"><span data-stu-id="12579-190">The required registry key was created for you when you ran Set-CsWatcherNodeConfiguration.</span></span>

  - <span data-ttu-id="12579-191">サーバーで、正しいバージョンの Lync Server が実行されている。</span><span class="sxs-lookup"><span data-stu-id="12579-191">Your servers are running the correct version of Lync Server.</span></span>

  - <span data-ttu-id="12579-192">ポートが正しく構成されています。</span><span class="sxs-lookup"><span data-stu-id="12579-192">Your ports been configured correctly.</span></span>

  - <span data-ttu-id="12579-193">割り当てられたテストユーザーには、必要な資格情報があります。</span><span class="sxs-lookup"><span data-stu-id="12579-193">Your assigned test users have the required credentials.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

