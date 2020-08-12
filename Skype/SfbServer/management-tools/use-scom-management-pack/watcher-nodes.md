---
title: 監視ノードのインストールと構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: '概要: Skype for Business Server 代理トランザクションの監視ノードをインストールして構成します。'
ms.openlocfilehash: 8efe291f72312b7634ae644d0e910cf58951b7a6
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640949"
---
# <a name="install-and-configure-watcher-nodes"></a><span data-ttu-id="4187c-103">監視ノードのインストールと構成</span><span class="sxs-lookup"><span data-stu-id="4187c-103">Install and configure watcher nodes</span></span>
 
<span data-ttu-id="4187c-104">**概要:** Skype for Business Server 代理トランザクションの監視ノードをインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="4187c-104">**Summary:** Install and configure watcher nodes for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="4187c-105">監視ノードは、Skype for Business Server 代理トランザクションを定期的に実行するコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="4187c-105">Watcher nodes are computers that periodically run Skype for Business Server synthetic transactions.</span></span> <span data-ttu-id="4187c-106">代理トランザクションは Windows PowerShell コマンドレットで、サインインまたは exchange インスタントメッセージへのサインイン機能など、主要なユーザーシナリオが期待どおりに動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4187c-106">Synthetic transactions are Windows PowerShell cmdlets that verify that key user scenarios, such as the ability to sign in or to exchange instant messages, are working as expected.</span></span> <span data-ttu-id="4187c-107">Skype for Business Server 2015 の場合、System Center Operations Manager は、次の表に示す代理トランザクションを実行できます。これには、次の3つの代理トランザクションの種類が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4187c-107">For Skype for Business Server 2015, System Center Operations Manager can run the synthetic transactions shown in the following table, which includes three synthetic transaction types:</span></span>
  
- <span data-ttu-id="4187c-108">**既定値**既定で監視ノードが実行する代理トランザクション。</span><span class="sxs-lookup"><span data-stu-id="4187c-108">**Default** Synthetic transactions that a watcher node runs by default.</span></span> <span data-ttu-id="4187c-109">新しい監視ノードを作成するときに、そのノードが実行する代理トランザクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4187c-109">When you create a new watcher node, you can specify which synthetic transactions that node will run.</span></span> <span data-ttu-id="4187c-110">(これは、Set-cswatchernodeconfiguration コマンドレットで使用される Tests パラメーターの目的です。)監視ノードの作成時に Tests パラメーターを使用しない場合、既定の代理トランザクションがすべて自動的に実行され、既定以外の代理トランザクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="4187c-110">(That's the purpose of the Tests parameter used by the New-CsWatcherNodeConfiguration cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="4187c-111">これは、たとえば、監視ノードが Test-CsAddressBookService テストを実行するように構成されていますが、テスト-CsExumConnectivity テストを実行するように構成されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="4187c-111">This means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>
    
- <span data-ttu-id="4187c-112">**既定以外**監視ノードが既定で実行されないことをテストします。</span><span class="sxs-lookup"><span data-stu-id="4187c-112">**Non-default** Tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="4187c-113">(詳細については、既定の種類の説明を参照してください)。ただし、監視ノードを有効にして、既定以外の代理トランザクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="4187c-113">(For details, see the description of the Default type.) However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="4187c-114">これは、監視ノードを作成するとき (Set-cswatchernodeconfiguration コマンドレットを使用して)、または監視ノードが作成された後の任意の時点で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4187c-114">You can do this when you create the watcher node (by using the New-CsWatcherNodeConfiguration cmdlet), or any time after the watcher node has been created.</span></span> <span data-ttu-id="4187c-115">既定以外の代理トランザクションでは、多くの場合、特別なセットアップ手順が必要になることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4187c-115">Note that many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="4187c-116">これらの手順の詳細については、「[代理トランザクションの特別なセットアップ手順](test-users-and-settings.md#special_synthetictrans)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4187c-116">For more details about these steps, see [Special Setup Instructions for Synthetic Transactions](test-users-and-settings.md#special_synthetictrans).</span></span>
    
- <span data-ttu-id="4187c-117">**拡張**特別な種類の既定以外の代理トランザクション。</span><span class="sxs-lookup"><span data-stu-id="4187c-117">**Extended** A special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="4187c-118">他の代理トランザクションとは異なり、拡張テストは、1 回のパスで複数回実行できます。</span><span class="sxs-lookup"><span data-stu-id="4187c-118">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="4187c-119">これは、プールに対する複数の公衆交換電話網 (PSTN) 音声ルートなどの動作を検証する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4187c-119">This is useful when verifying behavior, such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="4187c-120">これを構成するには、監視ノードに拡張テストの複数のインスタンスを追加するだけです。</span><span class="sxs-lookup"><span data-stu-id="4187c-120">You can configure this simply by adding multiple instances of an extended test to a watcher node.</span></span>
    
<span data-ttu-id="4187c-121">他の代理トランザクションを監視ノードに追加するプロセスの詳細については、「[代理トランザクションを実行する監視ノードを構成する](watcher-nodes.md#enable_synthetic_trans)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4187c-121">For details about the process for adding other synthetic transactions to a watcher node, see [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).</span></span> <span data-ttu-id="4187c-122">また、Skype for Business Server 管理シェルを使用して、監視ノードから代理トランザクションを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="4187c-122">You can also use Skype for Business Server Management Shell to remove synthetic transactions from a watcher node.</span></span>
  
<span data-ttu-id="4187c-123">監視ノードで使用できる代理トランザクションは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4187c-123">The synthetic transactions available to watcher nodes include the following:</span></span>
  
|<span data-ttu-id="4187c-124">**コマンドレット名 (テスト名)**</span><span class="sxs-lookup"><span data-stu-id="4187c-124">**Cmdlet Name (Test Name)**</span></span>|<span data-ttu-id="4187c-125">**説明**</span><span class="sxs-lookup"><span data-stu-id="4187c-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4187c-126">Test-CsAddressBookService (ABS)</span><span class="sxs-lookup"><span data-stu-id="4187c-126">Test-CsAddressBookService (ABS)</span></span>  <br/> |<span data-ttu-id="4187c-127">ユーザーが自分の連絡先リストに含まれていないユーザーを検索できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4187c-127">Confirms that users are able to look up users who aren't in their contact list.</span></span>  <br/> |
|<span data-ttu-id="4187c-128">Test-CsAddressBookWebQuery (ABWQ)</span><span class="sxs-lookup"><span data-stu-id="4187c-128">Test-CsAddressBookWebQuery (ABWQ)</span></span>  <br/> |<span data-ttu-id="4187c-129">ユーザーが自分の連絡先リストに含まれていないユーザーを HTTP 経由で検索できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4187c-129">Confirms that users are able to look up users who aren't in their contact list via HTTP.</span></span>  <br/> |
|<span data-ttu-id="4187c-130">テスト-CsAVConference (AvConference)</span><span class="sxs-lookup"><span data-stu-id="4187c-130">Test-CsAVConference (AvConference)</span></span>  <br/> |<span data-ttu-id="4187c-131">ユーザーが音声/ビデオ会議で作成と参加が可能なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4187c-131">Confirms that users are able to create and participate in an audio/video conference.</span></span>  <br/> |
|<span data-ttu-id="4187c-132">テスト-CsGroupIM (IM 会議)</span><span class="sxs-lookup"><span data-stu-id="4187c-132">Test-CsGroupIM (IM Conferencing)</span></span>  <br/> |<span data-ttu-id="4187c-133">ユーザーが会議中にインスタント メッセージを送信でき、3 人以上のユーザーとインスタント メッセージでの会話に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4187c-133">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span>  <br/> |
|<span data-ttu-id="4187c-134">テスト-CsIM (P2P IM)</span><span class="sxs-lookup"><span data-stu-id="4187c-134">Test-CsIM (P2P IM)</span></span>  <br/> |<span data-ttu-id="4187c-135">ユーザーがピアツーピア インスタント メッセージを送信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4187c-135">Confirms that users are able to send peer-to-peer instant messages.</span></span>  <br/> |
|<span data-ttu-id="4187c-136">Test-csp2pav (P2PAV)</span><span class="sxs-lookup"><span data-stu-id="4187c-136">Test-CsP2PAV (P2PAV)</span></span>  <br/> |<span data-ttu-id="4187c-137">ユーザーがピアツーピア音声通話を開始できることを確認します (シグナリングのみ)。</span><span class="sxs-lookup"><span data-stu-id="4187c-137">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span>  <br/> |
|<span data-ttu-id="4187c-138">Test-CsPresence (Presence)</span><span class="sxs-lookup"><span data-stu-id="4187c-138">Test-CsPresence (Presence)</span></span>  <br/> |<span data-ttu-id="4187c-139">ユーザーが他のユーザーのプレゼンスを表示できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4187c-139">Confirms that users are able to view other users' presence.</span></span>  <br/> |
|<span data-ttu-id="4187c-140">Test-CsRegistration (Registration)</span><span class="sxs-lookup"><span data-stu-id="4187c-140">Test-CsRegistration (Registration)</span></span>  <br/> |<span data-ttu-id="4187c-141">ユーザーが Skype for Business にサインインできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4187c-141">Confirms that users are able sign in to Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="4187c-142">Test-CsPstnPeerToPeerCall (PSTN)</span><span class="sxs-lookup"><span data-stu-id="4187c-142">Test-CsPstnPeerToPeerCall (PSTN)</span></span>  <br/> |<span data-ttu-id="4187c-143">ユーザーが企業の外部のユーザー (PSTN 番号) と通話できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4187c-143">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span>  <br/> |
|<span data-ttu-id="4187c-144">テスト-CsASConference (Asコンファレンス)</span><span class="sxs-lookup"><span data-stu-id="4187c-144">Test-CsASConference (ASConference)</span></span>  <br/> |<span data-ttu-id="4187c-145">ユーザーがアプリケーション共有会議の作成と参加を行うことができることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4187c-145">Confirms that users are able to create and participate in an application sharing conference.</span></span>  <br/> |
|<span data-ttu-id="4187c-146">Test-csavedgeconnectivity (AVEdgeConnectivity)</span><span class="sxs-lookup"><span data-stu-id="4187c-146">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span>  <br/> |<span data-ttu-id="4187c-147">音声ビデオエッジサーバーがピアツーピア通話と電話会議のための接続を受け入れることができることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4187c-147">Confirms that the Audio Video Edge servers are able to accept connections for peer-to- peer calls and conference calls.</span></span>  <br/> |
|<span data-ttu-id="4187c-148">Test-csdataconference (DataConference)</span><span class="sxs-lookup"><span data-stu-id="4187c-148">Test-CsDataConference (DataConference)</span></span>  <br/> |<span data-ttu-id="4187c-149">ユーザーがデータコラボレーション会議 (ホワイトボードや投票などのアクティビティが含まれるオンライン会議) に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4187c-149">Confirms that users can participate in a data collaboration conference (an online meeting that includes activities such as whiteboards and polls).</span></span>  <br/> |
|<span data-ttu-id="4187c-150">テスト-Csダイヤルイン会議 (ダイヤルイン会議)</span><span class="sxs-lookup"><span data-stu-id="4187c-150">Test-CsDialinConferencing (DialinConferencing)</span></span>  <br/> |<span data-ttu-id="4187c-151">ユーザーが会議に参加するために電話番号をダイヤルできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4187c-151">Confirms that users are able to dial phone numbers to join conferences.</span></span>  <br/> |
|<span data-ttu-id="4187c-152">テスト-Csダイヤルイン会議 (ダイヤルイン会議)</span><span class="sxs-lookup"><span data-stu-id="4187c-152">Test-CsDialinConferencing (DialinConferencing)</span></span>  <br/> |<span data-ttu-id="4187c-153">ユーザーが会議に参加するために電話番号をダイヤルできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4187c-153">Confirms that users are able to dial phone numbers to join conferences.</span></span>  <br/> |
|<span data-ttu-id="4187c-154">テスト-CsExumConnectivity (ExumConnectivity)</span><span class="sxs-lookup"><span data-stu-id="4187c-154">Test-CsExumConnectivity (ExumConnectivity)</span></span>  <br/> |<span data-ttu-id="4187c-155">ユーザーが Exchange ユニファイドメッセージング (UM) に接続できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4187c-155">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span>  <br/> |
|<span data-ttu-id="4187c-156">Test-CsGroupIM-TestJoinLauncher (Joinラウンチャー)</span><span class="sxs-lookup"><span data-stu-id="4187c-156">Test-CsGroupIM -TestJoinLauncher (JoinLauncher)</span></span>  <br/> |<span data-ttu-id="4187c-157">ユーザーがスケジュールされた会議を作成し、(web アドレスリンクで) 参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4187c-157">Confirms that users are able to create and join scheduled meetings (by a web address link).</span></span>  <br/> |
|<span data-ttu-id="4187c-158">Test-csmcxp2pim (MCXP2PIM)</span><span class="sxs-lookup"><span data-stu-id="4187c-158">Test-CsMCXP2PIM (MCXP2PIM)</span></span>  <br/> |<span data-ttu-id="4187c-159">モバイル デバイス ユーザーがインスタント メッセージの登録と送信を実行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4187c-159">Confirms that mobile device users are able to register and send instant messages.</span></span>  <br/> |
|<span data-ttu-id="4187c-160">CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)</span><span class="sxs-lookup"><span data-stu-id="4187c-160">Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)</span></span>  <br/> |<span data-ttu-id="4187c-161">ビデオ相互運用サーバーが稼働しており、ビデオ SIP トランク経由の受信接続を処理できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4187c-161">Confirms that Video Interop Server is up and can handle incoming connections over a video SIP trunk.</span></span>  <br/> <span data-ttu-id="4187c-162">**注:** 従来のモバイルクライアントに対する MCX サポートは、Skype for Business Server 2019 では利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="4187c-162">**Note:** MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> |
|<span data-ttu-id="4187c-163">Test-cspersistentchatmessage (PersistentChatMessage)</span><span class="sxs-lookup"><span data-stu-id="4187c-163">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span>  <br/> |<span data-ttu-id="4187c-164">ユーザーが常設チャットサービスを使用してメッセージを交換できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4187c-164">Confirms that users can exchange messages by using the Persistent Chat service.</span></span>  <br/> |
|<span data-ttu-id="4187c-165">Test-csucwaconference (UcwaConference)</span><span class="sxs-lookup"><span data-stu-id="4187c-165">Test-CsUcwaConference (UcwaConference)</span></span>  <br/> |<span data-ttu-id="4187c-166">ユーザーが web 経由で会議に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4187c-166">Confirms that users can join conferences via the web.</span></span>  <br/> |
|<span data-ttu-id="4187c-167">Test-csunifiedcontactstore (UnifiedContactStore)</span><span class="sxs-lookup"><span data-stu-id="4187c-167">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span>  <br/> |<span data-ttu-id="4187c-168">統合連絡先ストアを通じてユーザーの連絡先にアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4187c-168">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="4187c-169">統合連絡先ストアを使用すると、ユーザーは、Skype for Business Server 2015、Outlook メッセージングおよびコラボレーションクライアント、または Outlook Web Access を使用してアクセスできる単一の連絡先セットを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="4187c-169">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Skype for Business Server 2015, Outlook messaging and collaboration client, and/or Outlook Web Access.</span></span>  <br/> |
|<span data-ttu-id="4187c-170">テスト-CsXmppIM (XmppIM)</span><span class="sxs-lookup"><span data-stu-id="4187c-170">Test-CsXmppIM (XmppIM)</span></span>  <br/> |<span data-ttu-id="4187c-171">拡張メッセージングとプレゼンスプロトコル (XMPP) ゲートウェイを介してインスタントメッセージを送信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4187c-171">Confirms that an instant message can be sent across the Extensible Messaging and Presence Protocol (XMPP) gateway.</span></span>  <br/> <span data-ttu-id="4187c-172">XMPP ゲートウェイおよびプロキシは、Skype for business Server 2015 で利用できますが、Skype for business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="4187c-172">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span>  |

<span data-ttu-id="4187c-173">System Center Operations Manager を使用するために監視ノードをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4187c-173">You do not need to install watcher nodes to use System Center Operations Manager.</span></span> <span data-ttu-id="4187c-174">これらのノードをインストールしていない場合でも、問題が発生したときに Skype for Business Server 2015 のコンポーネントからリアルタイムで通知を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="4187c-174">If you do not install these nodes, you can still get real-time alerts from Skype for Business Server 2015 components whenever an issue occurs.</span></span> <span data-ttu-id="4187c-175">(コンポーネントおよびユーザー管理パックでは、監視ノードは使用されません)。ただし、アクティブな監視管理パックを使用してエンドツーエンドのシナリオを監視する場合は、監視ノードが必要です。</span><span class="sxs-lookup"><span data-stu-id="4187c-175">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4187c-176">管理者は、Operations Manager を使用したりインストールしたりせずに、代理トランザクションを手動で実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="4187c-176">Administrators can also run synthetic transactions manually, without using or installing Operations Manager.</span></span> <span data-ttu-id="4187c-177">Skype for Business Server の展開の規模によっては、代理トランザクションが大量のコンピューターメモリとプロセッサ時間を使用することがあります。</span><span class="sxs-lookup"><span data-stu-id="4187c-177">Depending on the size of your Skype for Business Server deployment, synthetic transactions can use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="4187c-178">このため、監視ノードとして専用のコンピューターを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4187c-178">Because of this, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="4187c-179">たとえば、監視ノードとして動作するように Skype for Business Server フロントエンドサーバーを構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="4187c-179">For example, you should not configure a Skype for Business Server Front End Server to act as a watcher node.</span></span> <span data-ttu-id="4187c-180">監視ノードは、Skype for Business Server トポロジの他のコンピュータと同じ基本的なハードウェア要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="4187c-180">Watcher nodes should meet the same basic hardware requirements as any other computer in your Skype for Business Server topology.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="4187c-181">Lync server 2013 と Skype for Business Server 2015 のコアシステムファイルを同じコンピューターにインストールできないため、従来の Lync Server 2013 監視ノードを Skype for Business Server 2015 監視ノードと同じコンピューターに併置することはできません。</span><span class="sxs-lookup"><span data-stu-id="4187c-181">A legacy Lync Server 2013 watcher node cannot be collocated on the same machine as a Skype for Business Server 2015 watcher node because the core system files for Lync Server 2013 and Skype for Business Server 2015 cannot be installed on the same computer.</span></span> <span data-ttu-id="4187c-182">ただし、Skype for Business Server 2015 監視ノードは、Skype for business Server 2015 および Lync Server 2013 を同時に監視できます。</span><span class="sxs-lookup"><span data-stu-id="4187c-182">However, Skype for Business Server 2015 watcher nodes can simultaneously monitor Skype for Business Server 2015 and Lync Server 2013.</span></span> <span data-ttu-id="4187c-183">両方の製品バージョンで既定の代理トランザクションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4187c-183">Default synthetic transactions are supported for both product versions.</span></span> 
  
<span data-ttu-id="4187c-184">Lync Server 2013 監視ノードはエンタープライズの内部または外部に展開され、次の点を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4187c-184">Lync Server 2013 watcher nodes may be deployed inside or outside an enterprise to help verify:</span></span>
  
- <span data-ttu-id="4187c-185">社内ユーザー用プールへの接続。</span><span class="sxs-lookup"><span data-stu-id="4187c-185">Connectivity to pools for users inside the enterprise.</span></span>
    
- <span data-ttu-id="4187c-186">企業外で作業するリモートユーザーのための境界ネットワーク経由の接続。</span><span class="sxs-lookup"><span data-stu-id="4187c-186">Connectivity through perimeter networks for remote users working outside the enterprise.</span></span>
    
- <span data-ttu-id="4187c-187">ブランチ オフィス アプライアンスへの接続。</span><span class="sxs-lookup"><span data-stu-id="4187c-187">Connectivity to branch office appliances.</span></span>
    
- <span data-ttu-id="4187c-188">企業内および境界ネットワークを介した Lync Server 2013 への接続。</span><span class="sxs-lookup"><span data-stu-id="4187c-188">Connectivity to Lync Server 2013 inside the enterprise and through perimeter networks.</span></span>
    
<span data-ttu-id="4187c-189">管理を容易にするために、エンタープライズの内部と外部で異なる認証オプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4187c-189">To help simplify administration, different authentication options are available for inside and outside of the enterprise.</span></span> <span data-ttu-id="4187c-190">詳細については、「[代理トランザクションを実行する監視ノードを構成する](watcher-nodes.md#enable_synthetic_trans)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4187c-190">For details, see [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).</span></span>
  
<span data-ttu-id="4187c-191">監視ノードとして動作するようにコンピューターを構成するには、最初に以下の前提条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="4187c-191">To configure a computer to act as a watcher node, you must first complete the following prerequisites:</span></span> 
  
- <span data-ttu-id="4187c-192">System Center Operations Manager をインストールして、Skype for Business Server 2015 管理パックをインポートします。</span><span class="sxs-lookup"><span data-stu-id="4187c-192">Install System Center Operations Manager and import the Skype for Business Server 2015 management packs.</span></span> <span data-ttu-id="4187c-193">また、監視ノードコンピューターが Skype for Business Server 2015 をインストールするためのすべての前提条件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4187c-193">You must also first verify that the watcher node computer meets all prerequisites for installing Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="4187c-194">監視ノードコンピューターに次のアイテムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="4187c-194">Install the following items on the watcher node computer:</span></span>
    
  - <span data-ttu-id="4187c-195">完全版の .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="4187c-195">The full version of .NET Framework 4.5</span></span>
    
  - <span data-ttu-id="4187c-196">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="4187c-196">Windows Identity Foundation</span></span>
    
  - <span data-ttu-id="4187c-197">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="4187c-197">Windows PowerShell 3.0</span></span>
    
<span data-ttu-id="4187c-198">前提条件が満たされたら、次の手順を実行して監視ノードを構成できます。</span><span class="sxs-lookup"><span data-stu-id="4187c-198">After the prerequisites are met, you can configure the watcher node by following these steps:</span></span>
  
1. <span data-ttu-id="4187c-199">監視ノードコンピューターに Skype for Business Server 2015 コアファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="4187c-199">Install the Skype for Business Server 2015 core files on the watcher node computer.</span></span>
    
2. <span data-ttu-id="4187c-200">監視ノードコンピューターに System Center Operations Manager エージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="4187c-200">Install System Center Operations Manager agent on the watcher node computer.</span></span>
    
3. <span data-ttu-id="4187c-201">Watchernode.msi の実行可能ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="4187c-201">Run the Watchernode.msi executable file.</span></span>
    
4. <span data-ttu-id="4187c-202">監視ノードによって使用されるテストユーザーアカウントを構成するには、 **set-cswatchernodeconfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4187c-202">Use the **New-CsWatcherNodeConfiguration** cmdlet to configure test user accounts to be employed by the watcher node.</span></span>
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a><span data-ttu-id="4187c-203">Skype for Business Server 2015 コアファイルおよび RTCLocal データベースをインストールする</span><span class="sxs-lookup"><span data-stu-id="4187c-203">Install the Skype for Business Server 2015 Core Files and the RTCLocal Database</span></span>

<span data-ttu-id="4187c-204">Skype for Business Server 2015 のコアファイルをコンピューターにインストールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4187c-204">To install the Skype for Business Server 2015 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="4187c-205">RTCLocal データベースは、コアファイルのインストール時に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4187c-205">The RTCLocal database will automatically be installed when you install the core files.</span></span> <span data-ttu-id="4187c-206">監視ノードに SQL Server をインストールする必要はないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4187c-206">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="4187c-207">SQL Server Express は自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4187c-207">SQL Server Express will be automatically installed.</span></span>
  
<span data-ttu-id="4187c-208">Skype for Business Server 2015 コアファイルおよび RTCLocal データベースをインストールするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="4187c-208">To install the Skype for Business Server 2015 core files and the RTCLocal database:</span></span>
  
1. <span data-ttu-id="4187c-209">監視ノード コンピューターで、[スタート] ボタン、[すべてのプログラム]、[アクセサリ] の順にクリックし、[コマンド プロンプト] を右クリックし、[管理者として実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4187c-209">On the watcher node computer, click Start, click All Programs, click Accessories, right-click Command Prompt, and then click Run as administrator.</span></span>
    
2. <span data-ttu-id="4187c-210">コンソールウィンドウで、次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4187c-210">In the console window, type the following command and press ENTER.</span></span> <span data-ttu-id="4187c-211">Skype for Business Server のセットアップファイルへの適切なパスを入力してください。 D:\Setup.exe/BootstrapLocalMgmtTo コア Skype for Business Server コンポーネントが正常にインストールされたことを確認するには、[**スタート**]、[**すべてのプログラム**]、[ **skype for business server 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4187c-211">Be sure to enter the appropriate path to your Skype for Business Server setup files: D:\Setup.exe /BootstrapLocalMgmtTo verify that the core Skype for Business Server components are successfully installed, click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server Management Shell**.</span></span> <span data-ttu-id="4187c-212">Skype for Business Server 管理シェルで、次の Windows PowerShell コマンドを入力して enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4187c-212">In the Skype for Business Server Management Shell, type the following Windows PowerShell command and press ENTER:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> <span data-ttu-id="4187c-213">このコマンドを初めて実行したときは、監視ノードコンピューターがまだ構成されていないため、データは返されません。</span><span class="sxs-lookup"><span data-stu-id="4187c-213">The first time you run this command, no data will be returned because you have not yet configured any watcher node computers.</span></span> <span data-ttu-id="4187c-214">コマンドがエラーを返さずに実行されている場合は、Skype for Business Server のセットアップが正常に完了したと見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="4187c-214">If the command runs without returning an error, you can assume that the Skype for Business Server setup completed successfully.</span></span> 
  
<span data-ttu-id="4187c-215">監視ノードコンピューターが境界ネットワーク内にある場合は、次のコマンドを実行して、Skype for Business Server 2015 のインストールを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4187c-215">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Skype for Business Server 2015:</span></span>
  
<span data-ttu-id="4187c-216">CsPinPolicyYou は、組織で使用するように構成された PIN ポリシーの数に応じて、次のような情報を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="4187c-216">Get-CsPinPolicyYou will receive information similar to this, depending on the number of PIN policies configured for use in your organization:</span></span>
  
<span data-ttu-id="4187c-217">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="4187c-217">Identity : Global</span></span>
  
<span data-ttu-id="4187c-218">Description</span><span class="sxs-lookup"><span data-stu-id="4187c-218">Description :</span></span>
  
<span data-ttu-id="4187c-219">MinPasswordLength: 5</span><span class="sxs-lookup"><span data-stu-id="4187c-219">MinPasswordLength : 5</span></span>
  
<span data-ttu-id="4187c-220">Pinhistory Count: 0</span><span class="sxs-lookup"><span data-stu-id="4187c-220">PINHistoryCount : 0</span></span>
  
<span data-ttu-id="4187c-221">AllowCommonPatterns: False</span><span class="sxs-lookup"><span data-stu-id="4187c-221">AllowCommonPatterns : False</span></span>
  
<span data-ttu-id="4187c-222">PINLifetime: 0</span><span class="sxs-lookup"><span data-stu-id="4187c-222">PINLifetime : 0</span></span>
  
<span data-ttu-id="4187c-223">MaximumLogonAttempts:</span><span class="sxs-lookup"><span data-stu-id="4187c-223">MaximumLogonAttempts :</span></span>
  
<span data-ttu-id="4187c-224">PIN ポリシーに関する情報が表示された場合は、コアコンポーネントが正常にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="4187c-224">If you see information about your PIN policies, the core components have been successfully installed.</span></span>
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a><span data-ttu-id="4187c-225">操作マネージャーエージェントファイルを監視ノードにインストールする</span><span class="sxs-lookup"><span data-stu-id="4187c-225">Install the Operation Manager Agent Files on a Watcher Node</span></span>

<span data-ttu-id="4187c-226">レポートコンポーネント通知の Skype for Business Server のセットアップと同様に、Skype for Business Server 2015 監視ノードで System Center Operations Manager エージェントファイルをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4187c-226">Similar to Skype for Business Server setup for reporting component alerts, a Skype for Business Server 2015 watcher node requires System Center Operations Manager agent files to be installed.</span></span> <span data-ttu-id="4187c-227">これにより、代理トランザクションが実行され、警告が System Center Operations Manager のルート管理サーバーに報告されるようになります。</span><span class="sxs-lookup"><span data-stu-id="4187c-227">This enables the synthetic transactions to be run and alerts to be reported to the System Center Operations Manager Root Management Server.</span></span>
  
<span data-ttu-id="4187c-228">エージェントファイルをインストールするには、「監視対象の[Skype For Business Server コンピューターを構成](configure-computers-to-monitor.md)する」に記載されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="4187c-228">To install the agent files, follow the procedures listed in [Configure the Skype for Business Server computers that will be monitored](configure-computers-to-monitor.md).</span></span>
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a><span data-ttu-id="4187c-229">代理トランザクションを実行する監視ノードの構成</span><span class="sxs-lookup"><span data-stu-id="4187c-229">Configure a Watcher Node to Run Synthetic Transactions</span></span>
<span data-ttu-id="4187c-230"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="4187c-230"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="4187c-231">System Center Operations Manager エージェントファイルがインストールされたら、監視ノード自体を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4187c-231">After the System Center Operations Manager agent files have been installed, you must configure the watcher node itself.</span></span> <span data-ttu-id="4187c-232">監視ノードコンピューターが境界ネットワーク内にあるか境界ネットワーク外にあるかによって、これを実行する手順は異なります。</span><span class="sxs-lookup"><span data-stu-id="4187c-232">The steps you take to do this will vary, depending on whether your watcher node computer is inside your perimeter network or outside your perimeter network.</span></span> 
  
<span data-ttu-id="4187c-233">監視ノードの構成時には、そのノードが使用する認証方法の種類も選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4187c-233">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="4187c-234">Skype for Business Server 2015 では、信頼されたサーバーまたは資格情報認証という2つの認証方法のどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="4187c-234">Skype for Business Server 2015 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="4187c-235">次の表は、これら2つのメソッドの違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="4187c-235">The following table shows the differences between these two methods:</span></span>
  
||<span data-ttu-id="4187c-236">**説明**</span><span class="sxs-lookup"><span data-stu-id="4187c-236">**Description**</span></span>|<span data-ttu-id="4187c-237">**サポートされる場所**</span><span class="sxs-lookup"><span data-stu-id="4187c-237">**Locations supported**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4187c-238">TrustedServer</span><span class="sxs-lookup"><span data-stu-id="4187c-238">TrustedServer</span></span>  <br/> |<span data-ttu-id="4187c-239">内部サーバーを偽装する証明書を使用し、認証チャレンジをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="4187c-239">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span>  <br/> <span data-ttu-id="4187c-240">各監視ノードで多数のユーザーパスワードではなく、1つの証明書を管理したいと考える管理者にとって便利です。</span><span class="sxs-lookup"><span data-stu-id="4187c-240">Useful for administrators who prefer to manage a single certificate, instead of many user passwords on each watcher node.</span></span>  <br/> |<span data-ttu-id="4187c-241">エンタープライズの内側。</span><span class="sxs-lookup"><span data-stu-id="4187c-241">Inside the enterprise.</span></span>  <br/> <span data-ttu-id="4187c-242">この方法では、監視ノードは監視対象のプールと同じドメイン内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="4187c-242">With this method, the watcher node must be in the same domain as the pools being monitored.</span></span> <span data-ttu-id="4187c-243">監視ノードとプールが異なるドメインにある場合は、資格情報認証を代わりに使用します。</span><span class="sxs-lookup"><span data-stu-id="4187c-243">If the watcher node and the pools are in different domains, use Credential Authentication instead.</span></span>  <br/> |
|<span data-ttu-id="4187c-244">取り決め</span><span class="sxs-lookup"><span data-stu-id="4187c-244">Negotiate</span></span>  <br/> |<span data-ttu-id="4187c-245">ユーザー名とパスワードを各監視ノードの Windows 資格情報マネージャーに保管します。</span><span class="sxs-lookup"><span data-stu-id="4187c-245">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span>  <br/> <span data-ttu-id="4187c-246">このモードでは、さらに多くのパスワードを管理する必要がありますが、エンタープライズ外部の監視ノードには唯一のオプションです。</span><span class="sxs-lookup"><span data-stu-id="4187c-246">This mode requires more password management, but is the only option for watcher nodes outside the enterprise.</span></span> <span data-ttu-id="4187c-247">このような外側に位置する監視ノードを認証の際に信頼済みのエンドポイントとして扱うことはできません。</span><span class="sxs-lookup"><span data-stu-id="4187c-247">These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span>  <br/> |<span data-ttu-id="4187c-248">エンタープライズの外側。</span><span class="sxs-lookup"><span data-stu-id="4187c-248">Outside the enterprise.</span></span>  <br/> <span data-ttu-id="4187c-249">エンタープライズの内側。</span><span class="sxs-lookup"><span data-stu-id="4187c-249">Inside the enterprise.</span></span>  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a><span data-ttu-id="4187c-250">信頼されたサーバー認証を使用するように監視ノードを構成する</span><span class="sxs-lookup"><span data-stu-id="4187c-250">Configure a Watcher Node to Use Trusted Server Authentication</span></span>
<span data-ttu-id="4187c-251"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="4187c-251"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="4187c-252">監視ノードコンピューターが境界ネットワーク内にある場合、信頼されたサーバー認証を使用すると、多数のユーザーアカウントパスワードを使用するのではなく、1つの証明書を保持することによって管理タスクを大幅に削減できます。</span><span class="sxs-lookup"><span data-stu-id="4187c-252">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration tasks by maintaining a single certificate, rather than using numerous user account passwords.</span></span>
  
<span data-ttu-id="4187c-253">信頼されたサーバー認証を構成するには、最初に、監視ノードコンピューターをホストする信頼されたアプリケーションプールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4187c-253">To configure Trusted Server authentication, you must first create a trusted application pool to host the watcher node computer.</span></span> <span data-ttu-id="4187c-254">信頼済みアプリケーションプールを作成したら、その監視ノードで代理トランザクションを構成して、信頼されたアプリケーションとして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4187c-254">After you've created the trusted application pool, you must then configure synthetic transactions on that watcher node to run as trusted applications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4187c-255">信頼されたアプリケーションとは、信頼された状態で Skype for Business Server 2015 の一部として実行されるアプリケーションですが、製品の組み込みパーツではありません。</span><span class="sxs-lookup"><span data-stu-id="4187c-255">A trusted application is an application that is given trusted status to run as part of Skype for Business Server 2015, but is not a built-in part of the product.</span></span> <span data-ttu-id="4187c-256">信頼済みステータスのアプリケーションは、実行のたびに認証でチャレンジされることはありません。</span><span class="sxs-lookup"><span data-stu-id="4187c-256">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>
  
<span data-ttu-id="4187c-257">信頼されたアプリケーションプールを作成するには、Skype for Business Server 管理シェルを開き、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4187c-257">To create a trusted application pool, open the Skype for Business Server Management Shell and run a command similar to this:</span></span>
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> <span data-ttu-id="4187c-258">上記のコマンドのパラメーターの詳細については、Skype for Business Server 管理シェルプロンプトから次のコマンドを入力してください。</span><span class="sxs-lookup"><span data-stu-id="4187c-258">For details about the parameters in the preceding command, type the following from the Skype for Business Server Management Shell prompt:</span></span> 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

<span data-ttu-id="4187c-259">信頼されたアプリケーションプールを作成したら、**次のよう**なコマンドを使用して、代理トランザクションを信頼されたアプリケーションとして実行するように監視ノードコンピューターを構成できます。</span><span class="sxs-lookup"><span data-stu-id="4187c-259">After creating the trusted application pool, you can then configure the watcher node computer to run synthetic transactions as a trusted application by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

<span data-ttu-id="4187c-260">このコマンドが完了し、信頼されたアプリケーションが作成されたら、 **Enable-CsTopology**コマンドレットを実行して、変更が有効になるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4187c-260">When this command completes and the trusted application is created, you must then run the **Enable-CsTopology** cmdlet to make sure that the changes take effect:</span></span>
  
```PowerShell
Enable-CsTopology
```

<span data-ttu-id="4187c-261">監視ノードのコンピューターアカウントでは、一部の代理トランザクションに対して CMS を照会する機能が必要です。</span><span class="sxs-lookup"><span data-stu-id="4187c-261">The watcher node computer account requires the ability to query CMS for some synthetic transactions.</span></span> <span data-ttu-id="4187c-262">この機能を許可するには、監視ノードのコンピューターアカウントを RTCUniversalReadOnlyAdmins セキュリティグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="4187c-262">To allow this ability, add the computer account of the watcher node to the RTCUniversalReadOnlyAdmins security group.</span></span> <span data-ttu-id="4187c-263">AD レプリケーションが発生したら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="4187c-263">Once AD replication has occurred, restart the computer.</span></span>
  
<span data-ttu-id="4187c-264">新しい信頼済みアプリケーションが作成されたことを確認するには、Skype for Business Server 管理シェルプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4187c-264">To verify that the new trusted application has been created, type the following at the Skype for Business Server Management Shell prompt:</span></span>
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="4187c-265">監視ノードで既定の証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="4187c-265">Configure a Default Certificate on the Watcher Node</span></span>
<span data-ttu-id="4187c-266"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="4187c-266"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="4187c-267">TrustedServer 認証を使用する各監視ノードには、Skype for Business Server 展開ウィザードを使用して割り当てられた既定の証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="4187c-267">Each watcher node that uses TrustedServer authentication must have a Default certificate assigned by using the Skype for Business Server Deployment wizard.</span></span> 
  
<span data-ttu-id="4187c-268">既定の証明書を割り当てるには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="4187c-268">To assign a Default certificate:</span></span>
  
1. <span data-ttu-id="4187c-269">[スタート]、[すべてのプログラム]、[Skype for Business Server 2015]、[Skype for Business Server 展開ウィザード] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="4187c-269">Click Start, click All Programs, click Skype for Business Server 2015, and then click Skype for Business Server Deployment Wizard.</span></span> 
    
2. <span data-ttu-id="4187c-270">Skype for Business Server の展開ウィザードで、[Skype for business Server システムのインストールまたは更新] をクリックし、[タイトルの要求、インストール、または証明書の割り当て] の [実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4187c-270">In the Skype for Business Server Deployment Wizard, click Install or Update Skype for Business Server System, and then click Run under the heading Request, Install, or Assign Certificate.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="4187c-271">[実行] ボタンをが無効になっている場合は、[ローカル構成ストアのインストール] で [実行] を最初にクリックしなければならないことがあります。</span><span class="sxs-lookup"><span data-stu-id="4187c-271">If the Run button is disabled, you may need to first click Run under Install Local Configuration Store.</span></span> 
  
<span data-ttu-id="4187c-272">以下のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4187c-272">Do one of the following:</span></span>
  
- <span data-ttu-id="4187c-273">既定の証明書として使用できる証明書が既にある場合は、証明書ウィザードで [既定] をクリックし、[割り当て] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4187c-273">If you already have a certificate that can be used as the Default certificate, click Default in the Certificate wizard, and then click Assign.</span></span> <span data-ttu-id="4187c-274">証明書の割り当てウィザードの手順に従って、証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4187c-274">Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
- <span data-ttu-id="4187c-275">既定の証明書を使用するために証明書を要求する必要がある場合は、[要求] をクリックし、証明書の要求ウィザードの手順に従って証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="4187c-275">If you need to request a certificate for use the Default certificate, click Request, and then follow the steps in the Certificate Request wizard to request that certificate.</span></span> <span data-ttu-id="4187c-276">Web サーバー証明書の既定値を使用すると、既定の証明書として割り当てることができる証明書を取得できます。</span><span class="sxs-lookup"><span data-stu-id="4187c-276">If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>
    
## <a name="install-and-configure-a-watcher-node"></a><span data-ttu-id="4187c-277">監視ノードをインストールおよび構成する</span><span class="sxs-lookup"><span data-stu-id="4187c-277">Install and Configure a Watcher Node</span></span>
<span data-ttu-id="4187c-278"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="4187c-278"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="4187c-279">監視ノードコンピューターを再起動し、証明書を構成した後、ファイル Watchernode.msi を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4187c-279">After you have restarted the watcher node computer and configured a certificate, you must run the file Watchernode.msi.</span></span> <span data-ttu-id="4187c-280">(Operations Manager エージェントファイルと Skype for Business Server 2015 コアコンポーネントの両方がインストールされているコンピューターで Watchernode.msi を実行する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="4187c-280">(You must run Watchernode.msi on any computer where both the Operations Manager agent files and the Skype for Business Server 2015 core components are installed.)</span></span> 
  
<span data-ttu-id="4187c-281">監視ノードをインストールおよび構成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="4187c-281">To install and configure a watcher node:</span></span>
  
1. <span data-ttu-id="4187c-282">[スタート]、[すべてのプログラム]、[Skype for Business Server 2015] の順にクリックし、[Skype for Business Server 管理シェル] をクリックして、Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4187c-282">Open the Skype for Business Server Management Shell by clicking Start, clicking All Programs, clicking Skype for Business Server 2015, and then clicking Skype for Business Server Management Shell.</span></span> 
    
2. <span data-ttu-id="4187c-283">管理シェルで次のコマンドを入力し、enter キーを押します (Watchernode.msi のコピーへの実際のパスを確認してください)。</span><span class="sxs-lookup"><span data-stu-id="4187c-283">In the Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> <span data-ttu-id="4187c-284">コマンドウィンドウから Watchernode.msi n を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="4187c-284">You can also run Watchernode.msi n from a command window.</span></span> <span data-ttu-id="4187c-285">コマンド ウィンドウを開くには、[スタート] をクリックし、[コマンド プロンプト] を右クリックして、[管理者として実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4187c-285">To open a command window, click Start, right-click Command Prompt, and then click Run as administrator.</span></span> <span data-ttu-id="4187c-286">コマンドウィンドウが開いたら、上記と同じ手順2で示したコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="4187c-286">When the command window opens, type the same command shown in step 2, above.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="4187c-287">上記のコマンドで、名前と値のペアの Authentication = TrustedServer は大文字と小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="4187c-287">In the preceding command, the name/value pair Authentication=TrustedServer is case-sensitive.</span></span> <span data-ttu-id="4187c-288">この値は、示されているとおりに入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4187c-288">It must be typed exactly as shown.</span></span> <span data-ttu-id="4187c-289">たとえば、次のコマンドは、適切な文字の大文字と小文字の区別を使用しないため、失敗します。</span><span class="sxs-lookup"><span data-stu-id="4187c-289">For example, this command will fail because it does not use the correct letter casing:</span></span> 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

<span data-ttu-id="4187c-290">TrustedServer モードは、境界ネットワーク内に存在するコンピューターでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="4187c-290">TrustedServer mode can be used only with computers that lie inside the perimeter network.</span></span> <span data-ttu-id="4187c-291">監視ノードが TrustedServer モードで実行されている場合、管理者はコンピューター上でテストユーザーのパスワードを管理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4187c-291">When a watcher node runs in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a><span data-ttu-id="4187c-292">ネゴシエーションを使用するように監視ノードを構成する</span><span class="sxs-lookup"><span data-stu-id="4187c-292">Configure a Watcher Node to Use Negotiate</span></span>
<span data-ttu-id="4187c-293"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="4187c-293"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="4187c-294">監視ノードコンピューターが境界ネットワークの外側にある場合は、次の手順に従って、代理トランザクションを実行するように監視ノードを構成する必要があります。特に、信頼されたアプリケーションプールまたは信頼されたアプリケーションを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="4187c-294">If your watcher node computer lies outside the perimeter network then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions: in particular, you should not create a trusted application pool or a trusted application.</span></span> <span data-ttu-id="4187c-295">これは、次の2つのタスクを完了する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="4187c-295">That means that you will need to complete the next two tasks.</span></span>
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="4187c-296">RTC ローカルの読み取り専用の Administrators グループのメンバーシップを更新する</span><span class="sxs-lookup"><span data-stu-id="4187c-296">Update Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="4187c-297">監視ノードが境界ネットワークの外側にある場合は、監視ノードで次の手順を実行して、ネットワークサービスアカウントを監視ノードコンピューターの RTC Local 読み取り専用管理者グループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4187c-297">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer by completing the following procedure on the watcher node:</span></span>
  
1. <span data-ttu-id="4187c-298">[スタート] メニューの [コンピューター] を右クリックし、[管理] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4187c-298">Click Start, right-click Computer, and then click Manage.</span></span>
    
2. <span data-ttu-id="4187c-299">サーバー マネージャーで、[構成]、[ローカル ユーザーとグループ] の順に展開し、[グループ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4187c-299">In Server Manager, expand Configuration, expand Local Users and Groups, and then click Groups.</span></span>
    
3. <span data-ttu-id="4187c-300">[グループ] ウィンドウで、[RTC Local Read-only Administrators] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="4187c-300">In the Groups pane, double-click RTC Local Read-only Administrators.</span></span>
    
4. <span data-ttu-id="4187c-301">[RTC Local Read-only Administrators のプロパティ] ダイアログ ボックスで、[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4187c-301">In the RTC Local Read-only Administrators Properties dialog box, click Add.</span></span>
    
5. <span data-ttu-id="4187c-302">[ユーザー、コンピューター、サービス アカウント、またはグループの選択] ダイアログで、[場所] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4187c-302">In the Select Users, Computers, Service Accounts, or Groups dialog box, click Locations.</span></span>
    
6. <span data-ttu-id="4187c-303">[場所] ダイアログ ボックスで、ウォッチャー ノード コンピューターの名前を選択し、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4187c-303">In the Locations dialog box, select the name of the watcher node computer, and then click OK.</span></span>
    
7. <span data-ttu-id="4187c-304">[選択するオブジェクト名を入力してください] ボックスに、「Network Service」と入力し、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4187c-304">In the Enter object names to select box, type Network Service, and then click OK.</span></span>
    
8. <span data-ttu-id="4187c-305">[RTC Local Read-only Administrators のプロパティ] ダイアログ ボックスで、[OK] をクリックし、[サーバー マネージャー] を閉じます。</span><span class="sxs-lookup"><span data-stu-id="4187c-305">In the RTC Local Read-only Administrators Properties dialog box, click OK, and then close Server Manager.</span></span>
    
9. <span data-ttu-id="4187c-306">ウォッチャー ノード コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="4187c-306">Restart the watcher node computer.</span></span>
    
### <a name="install-the-watcher-node-configuration-files"></a><span data-ttu-id="4187c-307">監視ノード構成ファイルをインストールする</span><span class="sxs-lookup"><span data-stu-id="4187c-307">Install the Watcher Node Configuration Files</span></span>

<span data-ttu-id="4187c-308">次の手順では、ファイル Watchernode.msi を実行します。</span><span class="sxs-lookup"><span data-stu-id="4187c-308">Your next step is to run the file Watchernode.msi:</span></span> 
  
1. <span data-ttu-id="4187c-309">Microsoft Skype for Business Server 2015 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4187c-309">Open the Microsoft Skype for Business Server 2015 Management Shell.</span></span> <span data-ttu-id="4187c-310">[スタート]、[すべてのプログラム]、[Microsoft Skype for Business Server 2015]、[Skype for Business Server 管理シェル] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="4187c-310">Click Start, click All Programs, click Microsoft Skype for Business Server 2015, and then click Skype for Business Server Management Shell.</span></span> 
    
2. <span data-ttu-id="4187c-311">Skype for Business Server 管理シェルで、次のコマンドを入力し、enter キーを押します (Watchernode.msi のコピーへの実際のパスを必ず指定してください)。</span><span class="sxs-lookup"><span data-stu-id="4187c-311">In Skype for Business Server Management Shell, type the following command, and then press ENTER (be sure to specify the actual path to your copy of Watchernode.msi):</span></span>
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> <span data-ttu-id="4187c-312">前述したように、Watchernode.msi はコマンドウィンドウから実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="4187c-312">As mentioned previously, Watchernode.msi can also be run from a command window.</span></span> <span data-ttu-id="4187c-313">コマンド ウィンドウを開くには、[**スタート**] をクリックし、[**コマンド プロンプト**] を右クリックして、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4187c-313">To open a command window, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="4187c-314">コマンドウィンドウが開いたら、上記と同じ手順2で示したコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="4187c-314">When the command window opens, type the same command shown in step 2, above.</span></span> 
  
<span data-ttu-id="4187c-315">ウォッチャー ノードを信頼されたアプリケーション プールとしてセットアップできない場合はいつでも、ネゴシエート モードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="4187c-315">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool.</span></span> <span data-ttu-id="4187c-316">このモードでは、管理者がウォッチャー ノードのテスト ユーザー パスワードを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4187c-316">In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>
  

