---
title: 'Lync Server 2013: 代理トランザクションの特別なセットアップ手順'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a749e4349f6dae6ab7cae079af443734f9cfbc15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "41985052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="b3786-102">Lync Server 2013 での代理トランザクションの特別なセットアップ手順</span><span class="sxs-lookup"><span data-stu-id="b3786-102">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3786-103">_**トピックの最終更新日:** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="b3786-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="b3786-p101">大半の代理トランザクションは、監視ノード上でそのまま実行できます。つまり、代理トランザクションが監視ノード構成設定に追加されると、監視ノードはその代理トランザクションの使用をテスト パス中に直ちに開始できます。ただし、これは、すべての代理トランザクションに当てはまるわけではありません。以降のセクションで、特別なセットアップが必要な代理トランザクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b3786-p101">Most synthetic transactions can run on a watcher node as-is; that is, as soon as the synthetic transaction has been added to the watcher node configuration settings, the watcher node can begin using the synthetic transaction during its test passes. However, this is not true for all synthetic transactions. The exceptions—synthetic transactions that require special setup instructions—are discussed in the following sections.</span></span>

<div>

## <a name="dealing-with-server-timeout-errors"></a><span data-ttu-id="b3786-107">サーバーのタイムアウトエラーを処理する</span><span class="sxs-lookup"><span data-stu-id="b3786-107">Dealing With Server Timeout Errors</span></span>

<span data-ttu-id="b3786-108">場合によっては、代理トランザクションがサーバータイムアウトエラーで失敗することがあります (エラーコード 504)。</span><span class="sxs-lookup"><span data-stu-id="b3786-108">In some cases you might find that your synthetic transactions are failing with server timeout errors (error code 504).</span></span> <span data-ttu-id="b3786-109">これらのエラーは、通常、ファイアウォールの問題によって発生します。</span><span class="sxs-lookup"><span data-stu-id="b3786-109">These errors are typically due to firewall problems.</span></span> <span data-ttu-id="b3786-110">代理トランザクションが実行されると、そのトランザクションは MonitoringHost .exe プロセスの下で実行されます。その後、MonitoringHost は PowerShell プロセスのインスタンスを開始します。</span><span class="sxs-lookup"><span data-stu-id="b3786-110">When a synthetic transaction is executed, that transaction runs under the MonitoringHost.exe process; in turn, MonitoringHost.exe starts an instance of the PowerShell.exe process.</span></span> <span data-ttu-id="b3786-111">MonitoringHost または PowerShell がファイアウォールによってブロックされている場合、代理トランザクションは失敗し、504エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b3786-111">If either MonitoringHost.exe or PowerShell.exe is blocked by your firewall then the synthetic transaction will fail and will generate a 504 error.</span></span>

<span data-ttu-id="b3786-112">この問題を解決するには、ローカルコンピューター上の MonitoringHost と PowerShell の両方に対して、受信ファイアウォール規則を手動で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3786-112">To resolve this issue, you should manually create inbound firewall rules for both MonitoringHost.exe and PowerShell.exe on the local machine.</span></span> <span data-ttu-id="b3786-113">この操作は、サーバーの既存の構成に応じて、Windows ファイアウォールまたはサードパーティのローカルファイアウォールソフトウェアを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b3786-113">This can be done via Windows firewall or a third-party local firewall software, depending on your server's preexisting configuration.</span></span>

<span data-ttu-id="b3786-114">代理トランザクションホストマシンと、監視しようとしている Lync サーバーとの間でネットワークファイアウォールデバイスを使用する場合は、ホストをクライアントコンピューターとして扱い、 [Lync Server 2013 の内部サーバーのポートとプロトコル](lync-server-2013-ports-and-protocols-for-internal-servers.md)に関するすべてのファイアウォールポート要件をオブザーバーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3786-114">If you're employing a network firewall device between the synthetic transaction host machine and the Lync Servers you're attempting to monitor, you should treat the host as a client machine, and observer all firewall port requirements from [Ports and protocols for internal servers in Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span></span>

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a><span data-ttu-id="b3786-115">データ会議代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="b3786-115">Data Conferencing Synthetic Transactions</span></span>

<span data-ttu-id="b3786-116">監視ノードコンピューターが境界ネットワークの外部に配置されている場合は、ネットワークサービスアカウントの Internet Explorer プロキシ設定を最初に無効にしない限り、データ会議の代理トランザクションを実行できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b3786-116">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Internet Explorer proxy settings for the Network Service account.</span></span> <span data-ttu-id="b3786-117">このサービスのプロキシ設定を無効にするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b3786-117">To disable the proxy settings for this service, complete the following procedure:</span></span>

1.  <span data-ttu-id="b3786-118">ウォッチャー ノード コンピューターで、[**スタート**] ボタンをクリックし、[**すべてのプログラム**]、[**アクセサリ**] の順にクリックします。次に、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3786-118">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="b3786-119">コンソール ウィンドウで、次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b3786-119">In the console window, type the following command and then press ENTER:</span></span>
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

<span data-ttu-id="b3786-120">コマンド ウィンドウに次のようなメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3786-120">The following message will appear in the command window:</span></span>

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

<span data-ttu-id="b3786-121">このメッセージは、ネットワークサービスアカウントの Internet Explorer プロキシ設定が無効になっていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b3786-121">This message means that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a><span data-ttu-id="b3786-122">Exchange ユニファイド メッセージング代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="b3786-122">Exchange Unified Messaging Synthetic Transactions</span></span>

<span data-ttu-id="b3786-123">Exchange ユニファイドメッセージング (UM) 代理トランザクションは、テストユーザーが Exchange に所属しているボイスメールアカウントに接続できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b3786-123">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span> <span data-ttu-id="b3786-124">これらのテスト ユーザーは、Exchange UM テストを使用する前に、ボイスメール アカウントを使用して事前に構成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3786-124">These test users will need to be preconfigured with voicemail accounts before they can use the Exchange UM tests.</span></span>

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a><span data-ttu-id="b3786-125">常設チャット代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="b3786-125">Persistent Chat Synthetic Transactions</span></span>

<span data-ttu-id="b3786-126">常設チャット代理トランザクションを使用するには、管理者はまずチャネルを作成し、それを使用するためのアクセス許可をテストユーザーに付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3786-126">To use the Persistent Chat synthetic transaction, administrators must first create a channel and give the test users permissions to use it.</span></span> <span data-ttu-id="b3786-127">これらのテストユーザーを適切に構成するには、 [test-cspersistentchatmessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage)コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b3786-127">The [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet can be used to properly configure these test users:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

<span data-ttu-id="b3786-128">このセットアップ タスクは、社内から実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3786-128">This setup task must be run from inside the enterprise:</span></span>

  - <span data-ttu-id="b3786-129">サーバー以外のコンピューターから実行する場合、コマンドレットを実行するユーザーは、役割ベースのアクセス制御 (RBAC) の PersistentChatAdministrators 役割のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3786-129">If run from a nonserver machine, the user who runs the cmdlet must be a member of the PersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>

  - <span data-ttu-id="b3786-130">サーバーから実行する場合、コマンドレットを実行するユーザーは、RTCUniversalServerAdmins グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3786-130">If run from the server itself, the user who runs the cmdlet should be a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="b3786-131">上のコマンドには Setup パラメーターが含まれ、True ($True) が設定されています。</span><span class="sxs-lookup"><span data-stu-id="b3786-131">In the preceding command, the Setup parameter was included and set to True ($True).</span></span> <span data-ttu-id="b3786-132">Setup パラメーターを指定すると、Test-cspersistentchatmessage は特別な常設チャットルームを作成し、そのルームにテストユーザーを設定します。</span><span class="sxs-lookup"><span data-stu-id="b3786-132">If you include the Setup parameter, Test-CsPersistentChatMessage will create a special Persistent Chat room and populate that room with the test users.</span></span> <span data-ttu-id="b3786-133">これにより、テスト目的で使用できるチャット ルームが実際に存在することが保証されます。</span><span class="sxs-lookup"><span data-stu-id="b3786-133">This helps to ensure that there is actually a chat room available for testing purposes.</span></span> <span data-ttu-id="b3786-134">Setup パラメーターは、フロントエンドサーバーからのみ実行する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b3786-134">Note that the Setup parameter should be run only from a Front End Server.</span></span>

<span data-ttu-id="b3786-135">Test-CsPersistentChatMessage を使用して作成されたチャット ルームは、管理者のみが削除できます。</span><span class="sxs-lookup"><span data-stu-id="b3786-135">The chat room that is created by Test-CsPersistentChatMessage can be deleted only by an administrator.</span></span>

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a><span data-ttu-id="b3786-136">PSTN ピアツーピア通話代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="b3786-136">PSTN Peer-to-Peer Call Synthetic Transactions</span></span>

<span data-ttu-id="b3786-137">[テスト-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall)代理トランザクションは、公衆交換電話網 (PSTN) 経由で通話を発信および受信できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b3786-137">The [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) synthetic transaction verifies the ability to place and receive calls via the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="b3786-138">この代理トランザクションを実行するには、管理者は以下を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3786-138">To run this synthetic transaction, administrators must configure:</span></span>

  - <span data-ttu-id="b3786-139">エンタープライズ Voip に対して有効になっている2つのテストユーザー (発信者と受信者)。</span><span class="sxs-lookup"><span data-stu-id="b3786-139">Two test users (a caller and a receiver) enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="b3786-140">各ユーザー アカウントのダイレクト インワード ダイヤリング (DID) 番号。</span><span class="sxs-lookup"><span data-stu-id="b3786-140">Direct Inward Dialing (DID) numbers for each user account.</span></span>

  - <span data-ttu-id="b3786-141">受信者の番号への通話が PSTN ゲートウェイに到達できるようにする音声ポリシーと音声ルート。</span><span class="sxs-lookup"><span data-stu-id="b3786-141">Voice policies and voice routes that enable calls to the receiver’s number to reach the PSTN gateway.</span></span>

  - <span data-ttu-id="b3786-142">通話を受ける PSTN ゲートウェイと、ダイヤルされた番号に基づいて受信者のホーム プールに通話を戻すメディア。</span><span class="sxs-lookup"><span data-stu-id="b3786-142">A PSTN gateway that accepts calls, and media that route calls backs to a receiver’s home pool based on the number dialed.</span></span>

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a><span data-ttu-id="b3786-143">統合連絡先ストア代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="b3786-143">Unified Contact Store Synthetic Transactions</span></span>

<span data-ttu-id="b3786-144">統合連絡先ストア代理トランザクションは、Lync Server 2013 が、ユーザーの代わりに Microsoft Exchange Server 2013 から連絡先を取得できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b3786-144">The Unified Contact Store synthetic transaction verifies that Lync Server 2013 is able to retrieve contacts on behalf of a user from Microsoft Exchange Server 2013.</span></span>

<span data-ttu-id="b3786-145">この代理トランザクションを使用するには、次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3786-145">To use this synthetic transaction, the following conditions must be met:</span></span>

  - <span data-ttu-id="b3786-146">Lync server [2013 でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)は、lync server 2013 と Exchange 2013 の間で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3786-146">[Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) must be configured between Lync Server 2013 and Exchange 2013.</span></span>

  - <span data-ttu-id="b3786-147">テストユーザーは、有効な Exchange 2013 メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3786-147">Test users must have a valid Exchange 2013 mailbox.</span></span>

<span data-ttu-id="b3786-148">これらの条件が満たされた後、管理者は、次のコマンドを実行して、SIP アドレスが kenmyer@litwareinc.com であるユーザーが自分の連絡先を統合連絡先ストアから取得できることを検証できます。</span><span class="sxs-lookup"><span data-stu-id="b3786-148">After these conditions are met, administrators can run the following command to verify that the user with the SIP address kenmyer@litwareinc.com can retrieve his contacts from the unified contact store:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

<span data-ttu-id="b3786-149">前述のコマンドで使用した Setup パラメーターの使用に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b3786-149">Note the use of the Setup parameter used in the preceding command.</span></span> <span data-ttu-id="b3786-150">Test-csunifiedcontactstore の実行中に Setup パラメーターが含まれる場合、指定されたユーザーの連絡先 (この場合は sip:kenmyer@litwareinc.com) が統合連絡先ストアに移動されます。</span><span class="sxs-lookup"><span data-stu-id="b3786-150">If the Setup parameter is included when running Test-CsUnifiedContactStore then the specified user’s contacts (in this case, sip:kenmyer@litwareinc.com) will be moved to the unified contact store.</span></span> <span data-ttu-id="b3786-151">(もちろん、ユーザーの連絡先が既に統合連絡先ストアにある場合は、それらを移動する必要はありません)。Setup パラメーターは、通常、1回だけ使用され (初回は Test-csunifiedcontactstore が実行されます)、テストユーザーのみが使用されます。つまり、実際には Lync Server にログオンしていないユーザーアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="b3786-151">(Of course, if the user’s contacts are already in the Unified Contact Store then they do not have to be moved.) The Setup parameter is typically used only one time (the first time Test-CsUnifiedContactStore is executed), and should only be used with test users; that is, with user accounts that will never actually be logged on to Lync Server.</span></span> <span data-ttu-id="b3786-152">テストユーザーが統合連絡先ストアに移行されたら、次のように、セットアップパラメーターを使用せずに Test-csunifiedcontactstore を呼び出して、ユーザーの連絡先を取得できることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b3786-152">After your test user has been migrated to the unified contact store, you can verify that the user’s contacts can be retrieved by calling Test-CsUnifiedContactStore without the Setup parameter:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a><span data-ttu-id="b3786-153">XMPP 代理トランザクション</span><span class="sxs-lookup"><span data-stu-id="b3786-153">XMPP Synthetic Transactions</span></span>

<span data-ttu-id="b3786-154">XMPP (Extensible Messaging and Presence Protocol) IM 代理トランザクションでは、XMPP 機能を 1 つ以上のフェデレーション ドメインで構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3786-154">The XMPP (Extensible Messaging and Presence Protocol) IM synthetic transaction requires that the XMPP feature be configured with one or more federated domains.</span></span>

<span data-ttu-id="b3786-155">XMPP 代理トランザクションを有効にするには、XmppTestReceiverMailAddress パラメーターにルーティング可能な XMPP ドメインのユーザー アカントを指定して使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3786-155">To enable the XMPP synthetic transaction, an XmppTestReceiverMailAddress parameter must be provided with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="b3786-156">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b3786-156">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

<span data-ttu-id="b3786-157">この例では、litwareinc.com のメッセージを XMPP ゲートウェイにルーティングするために、Lync Server 2013 ルールが存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3786-157">In this example, a Lync Server 2013 rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

