---
title: 監視ノードのインストールと構成
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: '概要: をインストールし、Skype のビジネス サーバー代理トランザクションの監視ノードを構成します。'
ms.openlocfilehash: 2ba6c6e0ac201d9721d281c87665fe9bf9c0407c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="install-and-configure-watcher-nodes"></a><span data-ttu-id="24643-103">監視ノードのインストールと構成</span><span class="sxs-lookup"><span data-stu-id="24643-103">Install and configure watcher nodes</span></span>
 
<span data-ttu-id="24643-104">**の概要:**インストールし、Skype のビジネス サーバー代理トランザクションの監視ノードを構成します。</span><span class="sxs-lookup"><span data-stu-id="24643-104">**Summary:** Install and configure watcher nodes for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="24643-105">ウォッチャー ノードとは、Skype をビジネス サーバー代理トランザクションを定期的に実行しているコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="24643-105">Watcher nodes are computers that periodically run Skype for Business Server synthetic transactions.</span></span> <span data-ttu-id="24643-106">代理トランザクションは、サインインする機能や、インスタント メッセージを交換する機能などの主要なユーザー シナリオが期待どおりに動作していることを確認する Windows PowerShell コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="24643-106">Synthetic transactions are Windows PowerShell cmdlets that verify that key user scenarios, such as the ability to sign in or to exchange instant messages, are working as expected.</span></span> <span data-ttu-id="24643-107">ビジネス サーバー 2015 の Skype は、System Center Operations Manager は 3 つの合成のトランザクション タイプは、次の表に示すように代理トランザクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="24643-107">For Skype for Business Server 2015, System Center Operations Manager can run the synthetic transactions shown in the following table, which includes three synthetic transaction types:</span></span>
  
- <span data-ttu-id="24643-108">**既定**ウォッチャー ノードが既定で実行されるトランザクションを合成します。</span><span class="sxs-lookup"><span data-stu-id="24643-108">**Default** Synthetic transactions that a watcher node runs by default.</span></span> <span data-ttu-id="24643-109">(合成) するを指定することができます新しいウォッチャー ノードを作成するときにそのノードで実行するトランザクションです。</span><span class="sxs-lookup"><span data-stu-id="24643-109">When you create a new watcher node, you can specify which synthetic transactions that node will run.</span></span> <span data-ttu-id="24643-110">(新規 CsWatcherNodeConfiguration コマンドレットで使用されるテスト パラメーターの目的は) です。ウォッチャー ノードを作成するときにテスト パラメーターを使用しない場合は自動的にすべてのデフォルト代理トランザクションを実行し、いずれかの既定以外の代理トランザクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="24643-110">(That's the purpose of the Tests parameter used by the New-CsWatcherNodeConfiguration cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="24643-111">つまりなどの監視ノード テスト CsAddressBookService テストを実行するように構成されますが、テスト CsExumConnectivity テストを実行するのには構成されません。</span><span class="sxs-lookup"><span data-stu-id="24643-111">This means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>
    
- <span data-ttu-id="24643-112">**既定ではないです。**ウォッチャー ノードが既定では実行しないことをテストします。</span><span class="sxs-lookup"><span data-stu-id="24643-112">**Non-default** Tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="24643-113">(詳細については、既定の種類の説明を参照してください)。ただし、既定以外の代理トランザクションを実行するウォッチャー ノードを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="24643-113">(For details, see the description of the Default type.) However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="24643-114">(新規 CsWatcherNodeConfiguration コマンドレットを使用して) で、[監視] ノードを作成するまたはウォッチャー ノードの後に、いつでもが作成されたときに、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="24643-114">You can do this when you create the watcher node (by using the New-CsWatcherNodeConfiguration cmdlet), or any time after the watcher node has been created.</span></span> <span data-ttu-id="24643-115">追加のセットアップ手順を必要とする既定以外の代理トランザクションの多くに注意してください。</span><span class="sxs-lookup"><span data-stu-id="24643-115">Note that many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="24643-116">これらの手順の詳細については、代理トランザクションの特殊なセットアップ手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24643-116">For details about these steps, see Special Setup Instructions for Synthetic Transactions.</span></span> <span data-ttu-id="24643-117">次の手順の詳細については、[代理トランザクションのセットアップの特別な指示](test-users-and-settings.md#special_synthetictrans)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24643-117">For more details about these steps, see [Special Setup Instructions for Synthetic Transactions ](test-users-and-settings.md#special_synthetictrans).</span></span>
    
- <span data-ttu-id="24643-118">**拡張**代理トランザクションの既定以外の特別な種類です。</span><span class="sxs-lookup"><span data-stu-id="24643-118">**Extended** A special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="24643-119">他の代理トランザクションとは異なり、拡張テストは、1 回のパスで複数回実行できます。</span><span class="sxs-lookup"><span data-stu-id="24643-119">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="24643-120">これは、プールに対する複数の公衆交換電話網 (PSTN) 音声ルートなどの動作を検証するときに便利です。</span><span class="sxs-lookup"><span data-stu-id="24643-120">This is useful when verifying behavior, such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="24643-121">これは、拡張テストの複数のインスタンスを監視ノードに追加するだけで構成できます。</span><span class="sxs-lookup"><span data-stu-id="24643-121">You can configure this simply by adding multiple instances of an extended test to a watcher node.</span></span>
    
<span data-ttu-id="24643-122">監視ノードに他の代理トランザクションを追加する方法については、「[Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24643-122">For details about the process for adding other synthetic transactions to a watcher node, see [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).</span></span> <span data-ttu-id="24643-123">ビジネス サーバー管理シェルの Skype は、監視ノードから代理トランザクションを削除するのにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="24643-123">You can also use Skype for Business Server Management Shell to remove synthetic transactions from a watcher node.</span></span>
  
<span data-ttu-id="24643-124">監視ノードで使用できる代理トランザクションは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="24643-124">The synthetic transactions available to watcher nodes include the following:</span></span>
  
|<span data-ttu-id="24643-125">**コマンドレット名 (テスト)**</span><span class="sxs-lookup"><span data-stu-id="24643-125">**Cmdlet Name (Test Name)**</span></span>|<span data-ttu-id="24643-126">**説明**</span><span class="sxs-lookup"><span data-stu-id="24643-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="24643-127">Test-CsAddressBookService (ABS)</span><span class="sxs-lookup"><span data-stu-id="24643-127">Test-CsAddressBookService (ABS)</span></span>  <br/> |<span data-ttu-id="24643-128">ユーザーが連絡先リストに登録されていないユーザーを検索することを確認します。</span><span class="sxs-lookup"><span data-stu-id="24643-128">Confirms that users are able to look up users who aren't in their contact list.</span></span>  <br/> |
|<span data-ttu-id="24643-129">Test-CsAddressBookWebQuery (ABWQ)</span><span class="sxs-lookup"><span data-stu-id="24643-129">Test-CsAddressBookWebQuery (ABWQ)</span></span>  <br/> |<span data-ttu-id="24643-130">ユーザーが HTTP 経由で自分の連絡先リストに登録されていないユーザーを検索することを確認します。</span><span class="sxs-lookup"><span data-stu-id="24643-130">Confirms that users are able to look up users who aren't in their contact list via HTTP.</span></span>  <br/> |
|<span data-ttu-id="24643-131">テスト-CsAVConference (AvConference)</span><span class="sxs-lookup"><span data-stu-id="24643-131">Test-CsAVConference (AvConference)</span></span>  <br/> |<span data-ttu-id="24643-132">ユーザーが音声/ビデオ会議で作成と参加が可能なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="24643-132">Confirms that users are able to create and participate in an audio/video conference.</span></span>  <br/> |
|<span data-ttu-id="24643-133">Test-CsGroupIM (IM Conferencing)</span><span class="sxs-lookup"><span data-stu-id="24643-133">Test-CsGroupIM (IM Conferencing)</span></span>  <br/> |<span data-ttu-id="24643-134">ユーザーが会議中にインスタント メッセージを送信でき、3 人以上のユーザーとインスタント メッセージでの会話に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24643-134">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span>  <br/> |
|<span data-ttu-id="24643-135">Test-CsIM (P2P IM)</span><span class="sxs-lookup"><span data-stu-id="24643-135">Test-CsIM (P2P IM)</span></span>  <br/> |<span data-ttu-id="24643-136">ユーザーがピアツーピア インスタント メッセージを送信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24643-136">Confirms that users are able to send peer-to-peer instant messages.</span></span>  <br/> |
|<span data-ttu-id="24643-137">Test-CsP2PAV (P2PAV)</span><span class="sxs-lookup"><span data-stu-id="24643-137">Test-CsP2PAV (P2PAV)</span></span>  <br/> |<span data-ttu-id="24643-138">ユーザーがピアツーピア音声通話を開始できることを確認します (シグナリングのみ)。</span><span class="sxs-lookup"><span data-stu-id="24643-138">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span>  <br/> |
|<span data-ttu-id="24643-139">Test-CsPresence (Presence)</span><span class="sxs-lookup"><span data-stu-id="24643-139">Test-CsPresence (Presence)</span></span>  <br/> |<span data-ttu-id="24643-140">ユーザーが他のユーザーのプレゼンスを表示することを確認します。</span><span class="sxs-lookup"><span data-stu-id="24643-140">Confirms that users are able to view other users' presence.</span></span>  <br/> |
|<span data-ttu-id="24643-141">Test-CsRegistration (Registration)</span><span class="sxs-lookup"><span data-stu-id="24643-141">Test-CsRegistration (Registration)</span></span>  <br/> |<span data-ttu-id="24643-142">ユーザーは、Skype をビジネスのために、サインインすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24643-142">Confirms that users are able sign in to Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="24643-143">Test-CsPstnPeerToPeerCall (PSTN)</span><span class="sxs-lookup"><span data-stu-id="24643-143">Test-CsPstnPeerToPeerCall (PSTN)</span></span>  <br/> |<span data-ttu-id="24643-144">ユーザーが企業の外部のユーザー (PSTN 番号) と通話できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24643-144">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span>  <br/> |
|<span data-ttu-id="24643-145">Test-CsASConference (ASConference)</span><span class="sxs-lookup"><span data-stu-id="24643-145">Test-CsASConference (ASConference)</span></span>  <br/> |<span data-ttu-id="24643-146">ユーザーがアプリケーション共有電話会議の作成と参加を行うことができることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24643-146">Confirms that users are able to create and participate in an application sharing conference.</span></span>  <br/> |
|<span data-ttu-id="24643-147">テスト-CsAVEdgeConnectivity (AVEdgeConnectivity)</span><span class="sxs-lookup"><span data-stu-id="24643-147">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span>  <br/> |<span data-ttu-id="24643-148">音声ビデオ エッジ サーバーがピアツーピア通話と会議通話を行うための接続を受け入れることができることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24643-148">Confirms that the Audio Video Edge servers are able to accept connections for peer-to- peer calls and conference calls.</span></span>  <br/> |
|<span data-ttu-id="24643-149">テスト-CsDataConference (DataConference)</span><span class="sxs-lookup"><span data-stu-id="24643-149">Test-CsDataConference (DataConference)</span></span>  <br/> |<span data-ttu-id="24643-150">ユーザーが、データ グループ作業電話会議 (ホワイトボードや投票などのアクティビティが含まれるオンライン会議) に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24643-150">Confirms that users can participate in a data collaboration conference (an online meeting that includes activities such as whiteboards and polls).</span></span>  <br/> |
|<span data-ttu-id="24643-151">テスト-CsDialinConferencing (DialinConferencing)</span><span class="sxs-lookup"><span data-stu-id="24643-151">Test-CsDialinConferencing (DialinConferencing)</span></span>  <br/> |<span data-ttu-id="24643-152">ユーザーが電話番号をダイヤルして電話会議に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24643-152">Confirms that users are able to dial phone numbers to join conferences.</span></span>  <br/> |
|<span data-ttu-id="24643-153">テスト-CsDialinConferencing (DialinConferencing)</span><span class="sxs-lookup"><span data-stu-id="24643-153">Test-CsDialinConferencing (DialinConferencing)</span></span>  <br/> |<span data-ttu-id="24643-154">ユーザーが電話番号をダイヤルして電話会議に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24643-154">Confirms that users are able to dial phone numbers to join conferences.</span></span>  <br/> |
|<span data-ttu-id="24643-155">テスト-CsExumConnectivity (ExumConnectivity)</span><span class="sxs-lookup"><span data-stu-id="24643-155">Test-CsExumConnectivity (ExumConnectivity)</span></span>  <br/> |<span data-ttu-id="24643-156">ユーザーが Exchange ユニファイド メッセージング (UM) に接続できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24643-156">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span>  <br/> |
|<span data-ttu-id="24643-157">テスト-CsGroupIM-TestJoinLauncher (JoinLauncher)</span><span class="sxs-lookup"><span data-stu-id="24643-157">Test-CsGroupIM -TestJoinLauncher (JoinLauncher)</span></span>  <br/> |<span data-ttu-id="24643-158">ユーザーがミーティングを作成でき、予定されたミーティングに Web アドレス リンクにより参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24643-158">Confirms that users are able to create and join scheduled meetings (by a web address link).</span></span>  <br/> |
|<span data-ttu-id="24643-159">Test-CsMCXP2PIM (MCXP2PIM)</span><span class="sxs-lookup"><span data-stu-id="24643-159">Test-CsMCXP2PIM (MCXP2PIM)</span></span>  <br/> |<span data-ttu-id="24643-160">モバイル デバイス ユーザーがインスタント メッセージの登録と送信を実行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24643-160">Confirms that mobile device users are able to register and send instant messages.</span></span>  <br/> |
|<span data-ttu-id="24643-161">テスト-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)</span><span class="sxs-lookup"><span data-stu-id="24643-161">Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)</span></span>  <br/> |<span data-ttu-id="24643-162">ビデオの相互運用機能のサーバーが起動して、ビデオの SIP トランク経由で着信接続を処理できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24643-162">Confirms that Video Interop Server is up and can handle incoming connections over a video SIP trunk.</span></span>  <br/> |
|<span data-ttu-id="24643-163">テスト-CsPersistentChatMessage (PersistentChatMessage)</span><span class="sxs-lookup"><span data-stu-id="24643-163">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span>  <br/> |<span data-ttu-id="24643-164">ユーザーが常設チャット サービスを使用してメッセージを交換できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24643-164">Confirms that users can exchange messages by using the Persistent Chat service.</span></span>  <br/> |
|<span data-ttu-id="24643-165">テスト-CsUcwaConference (UcwaConference)</span><span class="sxs-lookup"><span data-stu-id="24643-165">Test-CsUcwaConference (UcwaConference)</span></span>  <br/> |<span data-ttu-id="24643-166">ユーザーが Web を介して電話会議に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24643-166">Confirms that users can join conferences via the web.</span></span>  <br/> |
|<span data-ttu-id="24643-167">テスト-CsUnifiedContactStore (UnifiedContactStore)</span><span class="sxs-lookup"><span data-stu-id="24643-167">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span>  <br/> |<span data-ttu-id="24643-168">統合連絡先ストアを通じてユーザーの連絡先にアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24643-168">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="24643-169">統合連絡先ストアには、ユーザーが単一のビジネス サーバー 2015、Outlook メッセージングおよびコラボレーション クライアントでは、または Outlook Web Access の Skype を使用してアクセスできるメンバーのセットを維持する方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="24643-169">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Skype for Business Server 2015, Outlook messaging and collaboration client, and/or Outlook Web Access.</span></span>  <br/> |
|<span data-ttu-id="24643-170">テスト-CsXmppIM (XmppIM)</span><span class="sxs-lookup"><span data-stu-id="24643-170">Test-CsXmppIM (XmppIM)</span></span>  <br/> |<span data-ttu-id="24643-171">インスタント メッセージを Extensible Messaging and Presence Protocol (XMPP) ゲートウェイ経由で送信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24643-171">Confirms that an instant message can be sent across the Extensible Messaging and Presence Protocol (XMPP) gateway.</span></span>  <br/> |
   
<span data-ttu-id="24643-172">System Center Operations Manager を使用するウォッチャー ノードをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="24643-172">You do not need to install watcher nodes to use System Center Operations Manager.</span></span> <span data-ttu-id="24643-173">これらのノードをインストールしない場合でもから入手できますリアルタイム ・ アラート Skype サーバー 2015 のビジネス コンポーネントの問題が発生するたびにします。</span><span class="sxs-lookup"><span data-stu-id="24643-173">If you do not install these nodes, you can still get real-time alerts from Skype for Business Server 2015 components whenever an issue occurs.</span></span> <span data-ttu-id="24643-174">(コンポーネントとユーザーの管理パックが使用ウォッチャー ノード)。ただし、監視ノードは、アクティブな監視管理パックを使用して、エンド ・ ツー ・ エンドのシナリオを監視する場合は、必要があります。</span><span class="sxs-lookup"><span data-stu-id="24643-174">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>
  
> [!NOTE]
> <span data-ttu-id="24643-175">管理者は、Operations Manager の使用やインストールを行わなくても、代理トランザクションを手動で実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="24643-175">Administrators can also run synthetic transactions manually, without using or installing Operations Manager.</span></span> <span data-ttu-id="24643-176">サイズによっては、Skype をビジネス サーバーの展開の代理トランザクションは、大量のコンピューターのメモリとプロセッサ時間を使用できます。</span><span class="sxs-lookup"><span data-stu-id="24643-176">Depending on the size of your Skype for Business Server deployment, synthetic transactions can use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="24643-177">このため、監視ノードとして専用のコンピューターを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="24643-177">Because of this, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="24643-178">など、Skype のビジネス サーバー フロント エンド サーバー監視ノードとして機能するように構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="24643-178">For example, you should not configure a Skype for Business Server Front End Server to act as a watcher node.</span></span> <span data-ttu-id="24643-179">ウォッチャー ノードは、ビジネスのサーバー トポロジの場合、Skype での他のコンピューターと同じハードウェアの基本的な要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="24643-179">Watcher nodes should meet the same basic hardware requirements as any other computer in your Skype for Business Server topology.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="24643-180">同じコンピューター上の Lync Server 2013 と Skype ビジネス サーバー 2015 のコア システム ファイルをインストールすることはできませんので、ビジネス サーバー 2015 ウォッチャー ノードを Skype と同じコンピューターにレガシーの Lync Server 2013 のウォッチャー ノードを共存させることはできません。</span><span class="sxs-lookup"><span data-stu-id="24643-180">A legacy Lync Server 2013 watcher node cannot be collocated on the same machine as a Skype for Business Server 2015 watcher node because the core system files for Lync Server 2013 and Skype for Business Server 2015 cannot be installed on the same computer.</span></span> <span data-ttu-id="24643-181">ただし、Skype のビジネス サーバー 2015 ウォッチャー ノードがビジネス サーバー 2015 と Lync Server 2013 の Skype を同時に監視することができます。</span><span class="sxs-lookup"><span data-stu-id="24643-181">However, Skype for Business Server 2015 watcher nodes can simultaneously monitor Skype for Business Server 2015 and Lync Server 2013.</span></span> <span data-ttu-id="24643-182">代理トランザクションの既定値は、両方の製品のバージョンでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="24643-182">Default synthetic transactions are supported for both product versions.</span></span> 
  
<span data-ttu-id="24643-183">確認するためにエンタープライズの内外は、Lync Server 2013 のウォッチャー ノードを展開する場合があります。</span><span class="sxs-lookup"><span data-stu-id="24643-183">Lync Server 2013 watcher nodes may be deployed inside or outside an enterprise to help verify:</span></span>
  
- <span data-ttu-id="24643-184">社内ユーザー用プールへの接続。</span><span class="sxs-lookup"><span data-stu-id="24643-184">Connectivity to pools for users inside the enterprise.</span></span>
    
- <span data-ttu-id="24643-185">社外で働くリモート ユーザー用の境界ネットワーク経由の接続。</span><span class="sxs-lookup"><span data-stu-id="24643-185">Connectivity through perimeter networks for remote users working outside the enterprise.</span></span>
    
- <span data-ttu-id="24643-186">ブランチ オフィス アプライアンスへの接続。</span><span class="sxs-lookup"><span data-stu-id="24643-186">Connectivity to branch office appliances.</span></span>
    
- <span data-ttu-id="24643-187">企業の内部および境界領域のネットワークを介して Lync Server 2013 に接続します。</span><span class="sxs-lookup"><span data-stu-id="24643-187">Connectivity to Lync Server 2013 inside the enterprise and through perimeter networks.</span></span>
    
<span data-ttu-id="24643-p110">管理を容易にするため、社内および社外用の異なる認証オプションがあります。詳細については、「[Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24643-p110">To help simplify administration, different authentication options are available for inside and outside of the enterprise. For details, see [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).</span></span>
  
<span data-ttu-id="24643-190">監視ノードとして動作するようにコンピューターを構成するには、まず次の前提条件をすべて満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="24643-190">To configure a computer to act as a watcher node, you must first complete the following prerequisites:</span></span> 
  
- <span data-ttu-id="24643-191">System Center Operations Manager をインストールし、管理パックのビジネス サーバー 2015 の Skype をインポートします。</span><span class="sxs-lookup"><span data-stu-id="24643-191">Install System Center Operations Manager and import the Skype for Business Server 2015 management packs.</span></span> <span data-ttu-id="24643-192">まず、監視ノード コンピューターがビジネス サーバー 2015 の Skype をインストールするためのすべての前提条件を満たしているを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24643-192">You must also first verify that the watcher node computer meets all prerequisites for installing Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="24643-193">監視ノード コンピューターに以下のアイテムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="24643-193">Install the following items on the watcher node computer:</span></span>
    
  - <span data-ttu-id="24643-194">フル バージョンの.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="24643-194">The full version of .NET Framework 4.5</span></span>
    
  - <span data-ttu-id="24643-195">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="24643-195">Windows Identity Foundation</span></span>
    
  - <span data-ttu-id="24643-196">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="24643-196">Windows PowerShell 3.0</span></span>
    
<span data-ttu-id="24643-197">これらの前提条件が満たされた後、次の操作を実行して監視ノードを構成できます。</span><span class="sxs-lookup"><span data-stu-id="24643-197">After the prerequisites are met, you can configure the watcher node by following these steps:</span></span>
  
1. <span data-ttu-id="24643-198">ウォッチャー ノード コンピューター上のコア ファイルのビジネス サーバー 2015 の Skype をインストールします。</span><span class="sxs-lookup"><span data-stu-id="24643-198">Install the Skype for Business Server 2015 core files on the watcher node computer.</span></span>
    
2. <span data-ttu-id="24643-199">ウォッチャー ノード コンピューターの System Center Operations Manager エージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="24643-199">Install System Center Operations Manager agent on the watcher node computer.</span></span>
    
3. <span data-ttu-id="24643-200">Watchernode.msi 実行可能ファイルの実行。</span><span class="sxs-lookup"><span data-stu-id="24643-200">Run the Watchernode.msi executable file.</span></span>
    
4. <span data-ttu-id="24643-201">**CsWatcherNodeConfiguration** コマンドレットによる監視ノードで使用されるテスト ユーザー アカウントの構成。</span><span class="sxs-lookup"><span data-stu-id="24643-201">Use the **New-CsWatcherNodeConfiguration** cmdlet to configure test user accounts to be employed by the watcher node.</span></span>
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a><span data-ttu-id="24643-202">Skype for Business Server 2015 コア ファイルおよび RTCLocal データベースのインストール</span><span class="sxs-lookup"><span data-stu-id="24643-202">Install the Skype for Business Server 2015 Core Files and the RTCLocal Database</span></span>

<span data-ttu-id="24643-203">ビジネス サーバー 2015 中核となるコンピューター上のファイル、Skype をインストールするには、次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="24643-203">To install the Skype for Business Server 2015 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="24643-204">RTCLocal データベースは、コア ファイルをインストールするときに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="24643-204">The RTCLocal database will automatically be installed when you install the core files.</span></span> <span data-ttu-id="24643-205">ウォッチャー ノードで SQL Server をインストールする必要はありません注意してください。</span><span class="sxs-lookup"><span data-stu-id="24643-205">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="24643-206">SQL Server Express が自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="24643-206">SQL Server Express will be automatically installed.</span></span>
  
<span data-ttu-id="24643-207">ビジネス サーバー 2015 のコア ファイルと RTCLocal データベースの Skype をインストールするには。</span><span class="sxs-lookup"><span data-stu-id="24643-207">To install the Skype for Business Server 2015 core files and the RTCLocal database:</span></span>
  
1. <span data-ttu-id="24643-208">監視ノード コンピューターで、[スタート] ボタン、[すべてのプログラム]、[アクセサリ] の順にクリックし、[コマンド プロンプト] を右クリックし、[管理者として実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24643-208">On the watcher node computer, click Start, click All Programs, click Accessories, right-click Command Prompt, and then click Run as administrator.</span></span>
    
2. <span data-ttu-id="24643-209">コンソール ウィンドウで、次のコマンドを入力して Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="24643-209">In the console window, type the following command and press ENTER.</span></span> <span data-ttu-id="24643-210">Skype をビジネス サーバーのセットアップ ファイルを適切なパスを入力してください:/BootstrapLocalMgmtTo は、ビジネス サーバー コンポーネントのコア Skype が正常にインストールされていることを確認して D:\Setup.exe が [**スタート**] ボタン、[**すべてのプログラム**] をクリックして**ビジネス サーバー 2015 の Skype**をクリックし、 **Skype ビジネス サーバー管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24643-210">Be sure to enter the appropriate path to your Skype for Business Server setup files: D:\Setup.exe /BootstrapLocalMgmtTo verify that the core Skype for Business Server components are successfully installed, click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server Management Shell**.</span></span> <span data-ttu-id="24643-211">ビジネス サーバー管理シェルの Skype では、次の Windows PowerShell コマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="24643-211">In the Skype for Business Server Management Shell, type the following Windows PowerShell command and press ENTER:</span></span>
  
```
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> <span data-ttu-id="24643-212">最初にこのコマンドを実行したときは、まだ監視ノード コンピューターを構成していないので何もデータが表示されません。</span><span class="sxs-lookup"><span data-stu-id="24643-212">The first time you run this command, no data will be returned because you have not yet configured any watcher node computers.</span></span> <span data-ttu-id="24643-213">エラーを返さずにコマンドを実行する場合は、ビジネス サーバーのセットアップの Skype が正常に完了したことを想定できます。</span><span class="sxs-lookup"><span data-stu-id="24643-213">If the command runs without returning an error, you can assume that the Skype for Business Server setup completed successfully.</span></span> 
  
<span data-ttu-id="24643-214">監視ノード コンピューターが境界ネットワーク内にある場合は、次のコマンドを実行して Skype for Business Server 2015 のインストールを確認できます。</span><span class="sxs-lookup"><span data-stu-id="24643-214">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Skype for Business Server 2015:</span></span>
  
<span data-ttu-id="24643-215">Get CsPinPolicyYou 暗証番号 (pin) ポリシーを構成、組織で使用するための数によって、次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="24643-215">Get-CsPinPolicyYou will receive information similar to this, depending on the number of PIN policies configured for use in your organization:</span></span>
  
<span data-ttu-id="24643-216">識別情報: グローバル</span><span class="sxs-lookup"><span data-stu-id="24643-216">Identity : Global</span></span>
  
<span data-ttu-id="24643-217">説明:</span><span class="sxs-lookup"><span data-stu-id="24643-217">Description :</span></span>
  
<span data-ttu-id="24643-218">MinPasswordLength: 5</span><span class="sxs-lookup"><span data-stu-id="24643-218">MinPasswordLength : 5</span></span>
  
<span data-ttu-id="24643-219">PINHistoryCount: 0</span><span class="sxs-lookup"><span data-stu-id="24643-219">PINHistoryCount : 0</span></span>
  
<span data-ttu-id="24643-220">AllowCommonPatterns: False</span><span class="sxs-lookup"><span data-stu-id="24643-220">AllowCommonPatterns : False</span></span>
  
<span data-ttu-id="24643-221">PINLifetime: 0</span><span class="sxs-lookup"><span data-stu-id="24643-221">PINLifetime : 0</span></span>
  
<span data-ttu-id="24643-222">MaximumLogonAttempts :</span><span class="sxs-lookup"><span data-stu-id="24643-222">MaximumLogonAttempts :</span></span>
  
<span data-ttu-id="24643-223">PIN ポリシーに関する情報が表示された場合は、コア コンポーネントが正常にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="24643-223">If you see information about your PIN policies, the core components have been successfully installed.</span></span>
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a><span data-ttu-id="24643-224">監視ノードの Operation Manager エージェント ファイルのインストール</span><span class="sxs-lookup"><span data-stu-id="24643-224">Install the Operation Manager Agent Files on a Watcher Node</span></span>

<span data-ttu-id="24643-225">同様に Skype ビジネス サーバーのセットアップ コンポーネントのアラートを報告するためのビジネス サーバー 2015 ウォッチャー ノードを Skype には、System Center Operations Manager エージェントのファイルをインストールするが必要です。</span><span class="sxs-lookup"><span data-stu-id="24643-225">Similar to Skype for Business Server setup for reporting component alerts, a Skype for Business Server 2015 watcher node requires System Center Operations Manager agent files to be installed.</span></span> <span data-ttu-id="24643-226">これにより、合成のトランザクションを実行して、システム センター操作マネージャー ルートの管理サーバーに報告する警告です。</span><span class="sxs-lookup"><span data-stu-id="24643-226">This enables the synthetic transactions to be run and alerts to be reported to the System Center Operations Manager Root Management Server.</span></span>
  
<span data-ttu-id="24643-227">エージェントのファイルをインストールするには、[構成 Skype ビジネス サーバーのコンピューターを監視するため](configure-computers-to-monitor.md)に記載されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="24643-227">To install the agent files, follow the procedures listed in [Configure the Skype for Business Server computers that will be monitored](configure-computers-to-monitor.md).</span></span>
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a><span data-ttu-id="24643-228">代理トランザクションを実行する監視ノードの構成</span><span class="sxs-lookup"><span data-stu-id="24643-228">Configure a Watcher Node to Run Synthetic Transactions</span></span>
<span data-ttu-id="24643-229"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="24643-229"></span></span>

<span data-ttu-id="24643-230">System Center Operations Manager エージェントのファイルをインストールすると、ウォッチャー ノード自体を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24643-230">After the System Center Operations Manager agent files have been installed, you must configure the watcher node itself.</span></span> <span data-ttu-id="24643-231">監視ノードを構成する手順は監視ノードを境界ネットワークの内側に置くか、外側に置くかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="24643-231">The steps you take to do this will vary, depending on whether your watcher node computer is inside your perimeter network or outside your perimeter network.</span></span> 
  
<span data-ttu-id="24643-232">監視ノードの構成時には、そのノードが使用する認証方法の種類も選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24643-232">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="24643-233">ビジネス サーバー 2015 の Skype を使用すると、2 つの認証方法のいずれかを選択する: 信頼されたサーバーまたは認証の資格情報です。</span><span class="sxs-lookup"><span data-stu-id="24643-233">Skype for Business Server 2015 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="24643-234">この 2 つの方法の主な違いを次の表にまとめます。</span><span class="sxs-lookup"><span data-stu-id="24643-234">The following table shows the differences between these two methods:</span></span>
  
||<span data-ttu-id="24643-235">**説明**</span><span class="sxs-lookup"><span data-stu-id="24643-235">**Description**</span></span>|<span data-ttu-id="24643-236">**サポートされている場所**</span><span class="sxs-lookup"><span data-stu-id="24643-236">**Locations supported**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="24643-237">向こう側にあります。</span><span class="sxs-lookup"><span data-stu-id="24643-237">TrustedServer</span></span>  <br/> |<span data-ttu-id="24643-238">内部サーバーを偽装し、認証の問題を回避するには、証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="24643-238">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span>  <br/> <span data-ttu-id="24643-239">ウォッチャー ノードごとに多くのユーザーのパスワードの代わりに、単一の証明書を管理する管理者のために便利です。</span><span class="sxs-lookup"><span data-stu-id="24643-239">Useful for administrators who prefer to manage a single certificate, instead of many user passwords on each watcher node.</span></span>  <br/> |<span data-ttu-id="24643-240">中企業。</span><span class="sxs-lookup"><span data-stu-id="24643-240">Inside the enterprise.</span></span>  <br/> <span data-ttu-id="24643-241">この方法では、監視ノードが監視対象のプールと同じドメイン内に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24643-241">With this method, the watcher node must be in the same domain as the pools being monitored.</span></span> <span data-ttu-id="24643-242">監視ノードとプールが別のドメインに存在する場合は、この方法ではなく、資格情報認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="24643-242">If the watcher node and the pools are in different domains, use Credential Authentication instead.</span></span>  <br/> |
|<span data-ttu-id="24643-243">Negotiate</span><span class="sxs-lookup"><span data-stu-id="24643-243">Negotiate</span></span>  <br/> |<span data-ttu-id="24643-244">格納ユーザー名およびパスワードの安全に Windows 資格情報マネージャーで各監視ノードにします。</span><span class="sxs-lookup"><span data-stu-id="24643-244">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span>  <br/> <span data-ttu-id="24643-245">このモードは、パスワード管理の手間を必要としますが、エンタープライズの外側に位置する監視ノードの場合には唯一の選択肢となります。</span><span class="sxs-lookup"><span data-stu-id="24643-245">This mode requires more password management, but is the only option for watcher nodes outside the enterprise.</span></span> <span data-ttu-id="24643-246">このような外側に位置する監視ノードを認証の際に信頼済みのエンドポイントとして扱うことはできません。</span><span class="sxs-lookup"><span data-stu-id="24643-246">These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span>  <br/> |<span data-ttu-id="24643-247">社内外です。</span><span class="sxs-lookup"><span data-stu-id="24643-247">Outside the enterprise.</span></span>  <br/> <span data-ttu-id="24643-248">中企業。</span><span class="sxs-lookup"><span data-stu-id="24643-248">Inside the enterprise.</span></span>  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a><span data-ttu-id="24643-249">信頼されたサーバー認証を使用する監視ノードの構成</span><span class="sxs-lookup"><span data-stu-id="24643-249">Configure a Watcher Node to Use Trusted Server Authentication</span></span>
<span data-ttu-id="24643-250"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="24643-250"></span></span>

<span data-ttu-id="24643-251">監視ノード コンピューターが境界ネットワーク内にある場合、信頼済みサーバー認証によって 1 つの証明書を管理するだけでよくなるので、管理負荷が大幅に軽減されます。膨大な数のユーザー アカウント パスワードを管理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="24643-251">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration tasks by maintaining a single certificate, rather than using numerous user account passwords.</span></span>
  
<span data-ttu-id="24643-252">信頼済みサーバー認証を構成するには、まず監視ノード コンピューターをホストする信頼済みアプリケーション プールを作成します。</span><span class="sxs-lookup"><span data-stu-id="24643-252">To configure Trusted Server authentication, you must first create a trusted application pool to host the watcher node computer.</span></span> <span data-ttu-id="24643-253">信頼されたアプリケーション プールを作成した後は、信頼されたアプリケーションとして実行するウォッチャー ノードにし、代理トランザクションを構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="24643-253">After you've created the trusted application pool, you must then configure synthetic transactions on that watcher node to run as trusted applications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="24643-254">信頼されたアプリケーションは、ビジネス サーバー 2015 年の Skype の一部として実行するのには信頼される側のステータスが与えられますが、組み込み製品の一部ではないアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="24643-254">A trusted application is an application that is given trusted status to run as part of Skype for Business Server 2015, but is not a built-in part of the product.</span></span> <span data-ttu-id="24643-255">信頼された状態では、アプリケーションがない認証を実行するたびに対処するを意味します。</span><span class="sxs-lookup"><span data-stu-id="24643-255">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>
  
<span data-ttu-id="24643-256">信頼されたアプリケーション プールを作成するには、ビジネス サーバー管理シェルを開くには、Skype と次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="24643-256">To create a trusted application pool, open the Skype for Business Server Management Shell and run a command similar to this:</span></span>
  
```
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> <span data-ttu-id="24643-257">上記のコマンドのパラメーターに関する詳細については、ビジネスのサーバー管理シェル プロンプトの Skype から以下を入力します。</span><span class="sxs-lookup"><span data-stu-id="24643-257">For details about the parameters in the preceding command, type the following from the Skype for Business Server Management Shell prompt:</span></span> 
  
```
Get-Help New-CsTrustedApplicationPool -Full | more
```

<span data-ttu-id="24643-258">信頼済みアプリケーション プールの作成後、これを行うには、**New-CsTrustedApplication** コマンドレットと次のようなコマンドを使用して、代理トランザクションが信頼済みアプリケーションとして実行されるように監視ノード コンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="24643-258">After creating the trusted application pool, you can then configure the watcher node computer to run synthetic transactions as a trusted application by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>
  
```
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

<span data-ttu-id="24643-259">上記のコマンドが完了し、信頼済みアプリケーションが作成されたら、**Enable-CsTopology** コマンドレットを実行して変更を有効にします。</span><span class="sxs-lookup"><span data-stu-id="24643-259">When this command completes and the trusted application is created, you must then run the **Enable-CsTopology** cmdlet to make sure that the changes take effect:</span></span>
  
```
Enable-CsTopology
```

<span data-ttu-id="24643-260">Enable-CsTopology を実行後、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="24643-260">After running Enable-CsTopology, restart the computer.</span></span>
  
<span data-ttu-id="24643-261">新しい信頼されたアプリケーションが作成されたことを確認するには、ビジネス サーバー管理シェル プロンプトの Skype で次を入力します。</span><span class="sxs-lookup"><span data-stu-id="24643-261">To verify that the new trusted application has been created, type the following at the Skype for Business Server Management Shell prompt:</span></span>
  
```
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="24643-262">監視ノードで既定の証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="24643-262">Configure a Default Certificate on the Watcher Node</span></span>
<span data-ttu-id="24643-263"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="24643-263"></span></span>

<span data-ttu-id="24643-264">向こう側にある認証を使用する各監視ノードには、Skype ビジネス サーバーの展開ウィザードを使用して割り当てられている既定の証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="24643-264">Each watcher node that uses TrustedServer authentication must have a Default certificate assigned by using the Skype for Business Server Deployment wizard.</span></span> 
  
<span data-ttu-id="24643-265">既定の証明書を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="24643-265">To assign a Default certificate:</span></span>
  
1. <span data-ttu-id="24643-266">[開始] をクリックしてすべてのプログラム] をクリックして、Skype ビジネス サーバー 2015 年の Skype をビジネス サーバーの展開ウィザードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="24643-266">Click Start, click All Programs, click Skype for Business Server 2015, and then click Skype for Business Server Deployment Wizard.</span></span> 
    
2. <span data-ttu-id="24643-267">ビジネス サーバーの展開ウィザードの Skype、サーバーのビジネス システムのインストールまたは更新プログラムの Skype をクリックして.] の下の要求の実行、インストール、または証明書を割り当てる] をクリックし、</span><span class="sxs-lookup"><span data-stu-id="24643-267">In the Skype for Business Server Deployment Wizard, click Install or Update Skype for Business Server System, and then click Run under the heading Request, Install, or Assign Certificate.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="24643-268">[実行] ボタンをが無効になっている場合は、[ローカル構成ストアのインストール] で [実行] を最初にクリックしなければならないことがあります。</span><span class="sxs-lookup"><span data-stu-id="24643-268">If the Run button is disabled, you may need to first click Run under Install Local Configuration Store.</span></span> 
  
<span data-ttu-id="24643-269">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="24643-269">Do one of the following:</span></span>
  
- <span data-ttu-id="24643-p122">既定の証明書として使用できる証明書が既にある場合は、証明書ウィザードで [既定] をクリックし、[割り当て] をクリックします。証明書の割り当てウィザードの手順に従って、証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="24643-p122">If you already have a certificate that can be used as the Default certificate, click Default in the Certificate wizard, and then click Assign. Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
- <span data-ttu-id="24643-p123">既定の証明書として使用する証明書を要求する必要がある場合は、[要求] をクリックし、証明書要求ウィザードの手順に従ってその証明書を要求します。Web サーバー証明書の既定値を使用すると、既定の証明書として割り当てることができる証明書を取得できます。</span><span class="sxs-lookup"><span data-stu-id="24643-p123">If you need to request a certificate for use the Default certificate, click Request, and then follow the steps in the Certificate Request wizard to request that certificate. If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>
    
## <a name="install-and-configure-a-watcher-node"></a><span data-ttu-id="24643-274">監視ノードをインストールおよび構成する</span><span class="sxs-lookup"><span data-stu-id="24643-274">Install and Configure a Watcher Node</span></span>
<span data-ttu-id="24643-275"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="24643-275"></span></span>

<span data-ttu-id="24643-276">ウォッチャー ノードのコンピューターを再起動し、証明書を構成した後は、ファイル Watchernode.msi を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24643-276">After you have restarted the watcher node computer and configured a certificate, you must run the file Watchernode.msi.</span></span> <span data-ttu-id="24643-277">(必要がありますを実行する Watchernode.msi の任意のコンピューターのオペレーション マネージャー エージェントのファイルとサーバー 2015 のビジネスのコア ・ コンポーネントの Skype の両方がインストールされている)</span><span class="sxs-lookup"><span data-stu-id="24643-277">(You must run Watchernode.msi on any computer where both the Operations Manager agent files and the Skype for Business Server 2015 core components are installed.)</span></span> 
  
<span data-ttu-id="24643-278">監視ノードをインストールおよび構成するには</span><span class="sxs-lookup"><span data-stu-id="24643-278">To install and configure a watcher node:</span></span>
  
1. <span data-ttu-id="24643-279">ビジネス サーバー管理シェルの開始をクリックすると、すべてのプログラムをクリックすると、Skype ビジネス サーバー 2015 年をクリックし、Skype ビジネス サーバー管理シェルので、Skype を開きます。</span><span class="sxs-lookup"><span data-stu-id="24643-279">Open the Skype for Business Server Management Shell by clicking Start, clicking All Programs, clicking Skype for Business Server 2015, and then clicking Skype for Business Server Management Shell.</span></span> 
    
2. <span data-ttu-id="24643-280">管理シェルで、次のコマンドを入力して、Enter キーを押します (Watchernode.msi のコピーへの実際のパスを指定)。</span><span class="sxs-lookup"><span data-stu-id="24643-280">In the Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>
    
```
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> <span data-ttu-id="24643-p125">コマンド ウィンドウから Watchernode.msi を実行することもできます。コマンド ウィンドウを開くには、[スタート] をクリックし、[コマンド プロンプト] を右クリックして、[管理者として実行] をクリックします。コマンド ウィンドウが開いたら、上記の手順 2 と同じコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="24643-p125">You can also run Watchernode.msi n from a command window. To open a command window, click Start, right-click Command Prompt, and then click Run as administrator. When the command window opens, type the same command shown in step 2, above.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="24643-p126">上記のコマンドの名前/値ペア Authentication=TrustedServer は大文字と小文字が区別されるので、ここで示すとおりに正確に入力する必要があります。たとえば次のコマンドは、大文字と小文字が正しく使用されていないので失敗します。</span><span class="sxs-lookup"><span data-stu-id="24643-p126">In the preceding command, the name/value pair Authentication=TrustedServer is case-sensitive. It must be typed exactly as shown. For example, this command will fail because it does not use the correct letter casing:</span></span> 
  
```
C:\Tools\Watchernode.msi authentication=trustedserver
```

<span data-ttu-id="24643-p127">TrustedServer モードは、境界ネットワーク内のコンピューターでのみ使用できます。監視ノードが TrustedServer モードで実行されている場合、管理者はコンピューター上のテスト ユーザー パスワードを管理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="24643-p127">TrustedServer mode can be used only with computers that lie inside the perimeter network. When a watcher node runs in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a><span data-ttu-id="24643-289">ネゴシエートを使用する監視ノードの構成</span><span class="sxs-lookup"><span data-stu-id="24643-289">Configure a Watcher Node to Use Negotiate</span></span>
<span data-ttu-id="24643-290"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="24643-290"></span></span>

<span data-ttu-id="24643-p128">監視ノード コンピューターが境界ネットワークの外側にある場合は、代理トランザクションを実行するように監視ノードを構成するために、少し異なる手順に従う必要があります。特に、信頼されたアプリケーション プールや信頼されたアプリケーションは作成しないでください。つまり、次に示す個別の 2 つのタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24643-p128">If your watcher node computer lies outside the perimeter network then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions: in particular, you should not create a trusted application pool or a trusted application. That means that you will need to complete the next two tasks.</span></span>
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="24643-293">RTC Local Read-Only Administrators グループのメンバーシップの更新</span><span class="sxs-lookup"><span data-stu-id="24643-293">Update Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="24643-294">監視ノードが境界ネットワークの外側にある場合は、Network Service アカウントを監視ノード コンピューターの RTC Local Read-only Administrators グループに追加する必要があります。そのためには、監視ノードで以下の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="24643-294">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer by completing the following procedure on the watcher node:</span></span>
  
1. <span data-ttu-id="24643-295">[スタート] メニューの [コンピューター] を右クリックし、[管理] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24643-295">Click Start, right-click Computer, and then click Manage.</span></span>
    
2. <span data-ttu-id="24643-296">サーバー マネージャーで、[構成]、[ローカル ユーザーとグループ] の順に展開し、[グループ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24643-296">In Server Manager, expand Configuration, expand Local Users and Groups, and then click Groups.</span></span>
    
3. <span data-ttu-id="24643-297">[グループ] ウィンドウで、[RTC Local Read-only Administrators] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="24643-297">In the Groups pane, double-click RTC Local Read-only Administrators.</span></span>
    
4. <span data-ttu-id="24643-298">[RTC Local Read-only Administrators のプロパティ] ダイアログ ボックスで、[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24643-298">In the RTC Local Read-only Administrators Properties dialog box, click Add.</span></span>
    
5. <span data-ttu-id="24643-299">[ユーザー、コンピューター、サービス アカウント、またはグループの選択] ダイアログで、[場所] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24643-299">In the Select Users, Computers, Service Accounts, or Groups dialog box, click Locations.</span></span>
    
6. <span data-ttu-id="24643-300">[場所] ダイアログ ボックスで、監視ノード コンピューターの名前を選択し、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24643-300">In the Locations dialog box, select the name of the watcher node computer, and then click OK.</span></span>
    
7. <span data-ttu-id="24643-301">[選択するオブジェクト名を入力してください] ボックスに、「Network Service」と入力し、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24643-301">In the Enter object names to select box, type Network Service, and then click OK.</span></span>
    
8. <span data-ttu-id="24643-302">[RTC Local Read-only Administrators のプロパティ] ダイアログ ボックスで、[OK] をクリックし、[サーバー マネージャー] を閉じます。</span><span class="sxs-lookup"><span data-stu-id="24643-302">In the RTC Local Read-only Administrators Properties dialog box, click OK, and then close Server Manager.</span></span>
    
9. <span data-ttu-id="24643-303">監視ノード コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="24643-303">Restart the watcher node computer.</span></span>
    
### <a name="install-the-watcher-node-configuration-files"></a><span data-ttu-id="24643-304">監視ノード構成ファイルのインストール</span><span class="sxs-lookup"><span data-stu-id="24643-304">Install the Watcher Node Configuration Files</span></span>

<span data-ttu-id="24643-305">次に、Watchernode.msi ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="24643-305">Your next step is to run the file Watchernode.msi:</span></span> 
  
1. <span data-ttu-id="24643-p129">Microsoft Skype for Business Server 2015 管理シェルを以下の手順で起動します。[スタート]、[すべてのプログラム]、[Microsoft Skype for Business Server 2015]、[Skype for Business Server 管理シェル] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="24643-p129">Open the Microsoft Skype for Business Server 2015 Management Shell. Click Start, click All Programs, click Microsoft Skype for Business Server 2015, and then click Skype for Business Server Management Shell.</span></span> 
    
2. <span data-ttu-id="24643-308">Skype for Business Server 管理シェルで、次のコマンドを入力して、Enter キーを押します (Watchernode.msi のコピーへの実際のパスを指定)。</span><span class="sxs-lookup"><span data-stu-id="24643-308">In Skype for Business Server Management Shell, type the following command, and then press ENTER (be sure to specify the actual path to your copy of Watchernode.msi):</span></span>
    
  ```
  c:\Tools\Watchernode.msi Authentication=Negotiate
  ```

> [!NOTE]
> <span data-ttu-id="24643-p130">前述のように、Watchernode.msi はコマンド ウィンドウから実行することもできます。コマンド ウィンドウを開くには、[**スタート**] メニューをクリックし、[**コマンド プロンプト**] を右クリックして、[**管理者として実行**] をクリックします。コマンド ウィンドウが開いたら、上記の手順 2 と同じコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="24643-p130">As mentioned previously, Watchernode.msi can also be run from a command window. To open a command window, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**. When the command window opens, type the same command shown in step 2, above.</span></span> 
  
<span data-ttu-id="24643-p131">監視ノードを信頼されたアプリケーション プールとしてセットアップできない場合はいつでも、ネゴシエート モードが使用されます。このモードでは、管理者が監視ノードのテスト ユーザー パスワードを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24643-p131">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool. In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>
  

