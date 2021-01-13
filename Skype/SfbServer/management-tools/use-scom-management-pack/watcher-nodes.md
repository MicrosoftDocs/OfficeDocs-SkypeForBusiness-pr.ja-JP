---
title: 監視ノードのインストールと構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '概要: Skype for Business Server 代理トランザクションの監視ノードをインストールおよび構成します。'
ms.openlocfilehash: f6d3db973291b8a41647a3c4a4d3c3530c7af019
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812752"
---
# <a name="install-and-configure-watcher-nodes"></a><span data-ttu-id="34ad6-103">監視ノードのインストールと構成</span><span class="sxs-lookup"><span data-stu-id="34ad6-103">Install and configure watcher nodes</span></span>
 
<span data-ttu-id="34ad6-104">**概要:** Skype for Business Server 代理トランザクションの監視ノードをインストールおよび構成します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-104">**Summary:** Install and configure watcher nodes for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="34ad6-105">監視ノードは、Skype for Business Server 代理トランザクションを定期的に実行するコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="34ad6-105">Watcher nodes are computers that periodically run Skype for Business Server synthetic transactions.</span></span> <span data-ttu-id="34ad6-106">代理トランザクションはWindows PowerShellユーザーの主要なシナリオ (サインインやインスタント メッセージの交換など) が期待通り動作しているのを確認するコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="34ad6-106">Synthetic transactions are Windows PowerShell cmdlets that verify that key user scenarios, such as the ability to sign in or to exchange instant messages, are working as expected.</span></span> <span data-ttu-id="34ad6-107">Skype for Business Server 2015 の場合、System Center Operations Manager は、次の表に示す代理トランザクションを実行できます。これには、次の 3 種類の代理トランザクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-107">For Skype for Business Server 2015, System Center Operations Manager can run the synthetic transactions shown in the following table, which includes three synthetic transaction types:</span></span>
  
- <span data-ttu-id="34ad6-108">**既定値** 監視ノードが既定で実行される代理トランザクション。</span><span class="sxs-lookup"><span data-stu-id="34ad6-108">**Default** Synthetic transactions that a watcher node runs by default.</span></span> <span data-ttu-id="34ad6-109">新しい監視ノードを作成するときに、そのノードを実行する代理トランザクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-109">When you create a new watcher node, you can specify which synthetic transactions that node will run.</span></span> <span data-ttu-id="34ad6-110">(これは、テスト コマンドレットで使用される Tests パラメーターNew-CsWatcherNodeConfigurationです)。監視ノードの作成時に Tests パラメーターを使用しない場合は、すべての既定の代理トランザクションが自動的に実行され、既定以外の代理トランザクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="34ad6-110">(That's the purpose of the Tests parameter used by the New-CsWatcherNodeConfiguration cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="34ad6-111">つまり、たとえば、監視ノードは Test-CsAddressBookService テストを実行するように構成されますが、Test-CsExumConnectivity テストを実行するように構成されません。</span><span class="sxs-lookup"><span data-stu-id="34ad6-111">This means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>
    
- <span data-ttu-id="34ad6-112">**既定以外** 監視ノードが既定で実行されないテスト。</span><span class="sxs-lookup"><span data-stu-id="34ad6-112">**Non-default** Tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="34ad6-113">(詳細については、Default 型の説明を参照してください)。ただし、監視ノードを有効にすると、既定以外の代理トランザクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-113">(For details, see the description of the Default type.) However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="34ad6-114">これは、監視ノードを作成するときに (New-CsWatcherNodeConfiguration コマンドレットを使用して)、または監視ノードの作成後にいつでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-114">You can do this when you create the watcher node (by using the New-CsWatcherNodeConfiguration cmdlet), or any time after the watcher node has been created.</span></span> <span data-ttu-id="34ad6-115">既定以外の代理トランザクションの多くは、追加のセットアップ手順を必要とします。</span><span class="sxs-lookup"><span data-stu-id="34ad6-115">Note that many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="34ad6-116">これらの手順の詳細については、「代理トランザクションの [特別なセットアップ手順」を参照してください](test-users-and-settings.md#special_synthetictrans)。</span><span class="sxs-lookup"><span data-stu-id="34ad6-116">For more details about these steps, see [Special Setup Instructions for Synthetic Transactions](test-users-and-settings.md#special_synthetictrans).</span></span>
    
- <span data-ttu-id="34ad6-117">**拡張** 特殊な種類の既定以外の代理トランザクション。</span><span class="sxs-lookup"><span data-stu-id="34ad6-117">**Extended** A special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="34ad6-118">他の代理トランザクションとは異なり、拡張テストは、1 回のパスで複数回実行できます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-118">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="34ad6-119">これは、プールの複数の公衆交換電話網 (PSTN) ボイス ルートなどの動作を確認する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-119">This is useful when verifying behavior, such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="34ad6-120">これは、拡張テストの複数のインスタンスを監視ノードに追加するだけで構成できます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-120">You can configure this simply by adding multiple instances of an extended test to a watcher node.</span></span>
    
<span data-ttu-id="34ad6-121">監視ノードに他の代理トランザクションを追加するプロセスの詳細については [、「Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34ad6-121">For details about the process for adding other synthetic transactions to a watcher node, see [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).</span></span> <span data-ttu-id="34ad6-122">Skype for Business Server 管理シェルを使用して監視ノードから代理トランザクションを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-122">You can also use Skype for Business Server Management Shell to remove synthetic transactions from a watcher node.</span></span>
  
<span data-ttu-id="34ad6-123">監視ノードで使用できる代理トランザクションは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="34ad6-123">The synthetic transactions available to watcher nodes include the following:</span></span>
  
|<span data-ttu-id="34ad6-124">**コマンドレット名 (テスト名)**</span><span class="sxs-lookup"><span data-stu-id="34ad6-124">**Cmdlet Name (Test Name)**</span></span>|<span data-ttu-id="34ad6-125">**説明**</span><span class="sxs-lookup"><span data-stu-id="34ad6-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="34ad6-126">Test-CsAddressBookService (ABS)</span><span class="sxs-lookup"><span data-stu-id="34ad6-126">Test-CsAddressBookService (ABS)</span></span>  <br/> |<span data-ttu-id="34ad6-127">ユーザーが自分の連絡先リストに含されていないユーザーを参照できるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-127">Confirms that users are able to look up users who aren't in their contact list.</span></span>  <br/> |
|<span data-ttu-id="34ad6-128">Test-CsAddressBookWebQuery (ABWQ)</span><span class="sxs-lookup"><span data-stu-id="34ad6-128">Test-CsAddressBookWebQuery (ABWQ)</span></span>  <br/> |<span data-ttu-id="34ad6-129">ユーザーが HTTP 経由で連絡先リストに登録されていないユーザーを参照できる状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-129">Confirms that users are able to look up users who aren't in their contact list via HTTP.</span></span>  <br/> |
|<span data-ttu-id="34ad6-130">Test-CsAVConference (AvConference)</span><span class="sxs-lookup"><span data-stu-id="34ad6-130">Test-CsAVConference (AvConference)</span></span>  <br/> |<span data-ttu-id="34ad6-131">ユーザーが音声/ビデオ会議で作成と参加が可能なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-131">Confirms that users are able to create and participate in an audio/video conference.</span></span>  <br/> |
|<span data-ttu-id="34ad6-132">Test-CsGroupIM (IM 会議)</span><span class="sxs-lookup"><span data-stu-id="34ad6-132">Test-CsGroupIM (IM Conferencing)</span></span>  <br/> |<span data-ttu-id="34ad6-133">ユーザーが会議中にインスタント メッセージを送信でき、3 人以上のユーザーとインスタント メッセージでの会話に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-133">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span>  <br/> |
|<span data-ttu-id="34ad6-134">Test-CsIM (P2P IM)</span><span class="sxs-lookup"><span data-stu-id="34ad6-134">Test-CsIM (P2P IM)</span></span>  <br/> |<span data-ttu-id="34ad6-135">ユーザーがピアツーピア インスタント メッセージを送信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-135">Confirms that users are able to send peer-to-peer instant messages.</span></span>  <br/> |
|<span data-ttu-id="34ad6-136">Test-CsP2PAV (P2PAV)</span><span class="sxs-lookup"><span data-stu-id="34ad6-136">Test-CsP2PAV (P2PAV)</span></span>  <br/> |<span data-ttu-id="34ad6-137">ユーザーがピアツーピア音声通話を開始できることを確認します (シグナリングのみ)。</span><span class="sxs-lookup"><span data-stu-id="34ad6-137">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span>  <br/> |
|<span data-ttu-id="34ad6-138">Test-CsPresence (Presence)</span><span class="sxs-lookup"><span data-stu-id="34ad6-138">Test-CsPresence (Presence)</span></span>  <br/> |<span data-ttu-id="34ad6-139">ユーザーが他のユーザーのプレゼンスを表示できる状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-139">Confirms that users are able to view other users' presence.</span></span>  <br/> |
|<span data-ttu-id="34ad6-140">Test-CsRegistration (Registration)</span><span class="sxs-lookup"><span data-stu-id="34ad6-140">Test-CsRegistration (Registration)</span></span>  <br/> |<span data-ttu-id="34ad6-141">ユーザーが Skype for Business にサインイン可能なユーザーを確認します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-141">Confirms that users are able sign in to Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="34ad6-142">Test-CsPstnPeerToPeerCall (PSTN)</span><span class="sxs-lookup"><span data-stu-id="34ad6-142">Test-CsPstnPeerToPeerCall (PSTN)</span></span>  <br/> |<span data-ttu-id="34ad6-143">ユーザーが企業の外部のユーザー (PSTN 番号) と通話できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-143">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span>  <br/> |
|<span data-ttu-id="34ad6-144">Test-CsASConference (ASConference)</span><span class="sxs-lookup"><span data-stu-id="34ad6-144">Test-CsASConference (ASConference)</span></span>  <br/> |<span data-ttu-id="34ad6-145">ユーザーがアプリケーション共有会議を作成して参加可能なユーザーを確認します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-145">Confirms that users are able to create and participate in an application sharing conference.</span></span>  <br/> |
|<span data-ttu-id="34ad6-146">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span><span class="sxs-lookup"><span data-stu-id="34ad6-146">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span>  <br/> |<span data-ttu-id="34ad6-147">音声ビデオ エッジ サーバーが、ピアツーピア通話と電話会議の接続を受け入れ可能に設定します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-147">Confirms that the Audio Video Edge servers are able to accept connections for peer-to- peer calls and conference calls.</span></span>  <br/> |
|<span data-ttu-id="34ad6-148">Test-CsDataConference (DataConference)</span><span class="sxs-lookup"><span data-stu-id="34ad6-148">Test-CsDataConference (DataConference)</span></span>  <br/> |<span data-ttu-id="34ad6-149">ユーザーがデータ コラボレーション会議 (ホワイトボードや投票などのアクティビティを含むオンライン会議) に参加できるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-149">Confirms that users can participate in a data collaboration conference (an online meeting that includes activities such as whiteboards and polls).</span></span>  <br/> |
|<span data-ttu-id="34ad6-150">Test-CsDialinConferencing (DialinConferencing)</span><span class="sxs-lookup"><span data-stu-id="34ad6-150">Test-CsDialinConferencing (DialinConferencing)</span></span>  <br/> |<span data-ttu-id="34ad6-151">ユーザーが電話会議に参加するために電話番号をダイヤルできるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-151">Confirms that users are able to dial phone numbers to join conferences.</span></span>  <br/> |
|<span data-ttu-id="34ad6-152">Test-CsDialinConferencing (DialinConferencing)</span><span class="sxs-lookup"><span data-stu-id="34ad6-152">Test-CsDialinConferencing (DialinConferencing)</span></span>  <br/> |<span data-ttu-id="34ad6-153">ユーザーが電話会議に参加するために電話番号をダイヤルできるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-153">Confirms that users are able to dial phone numbers to join conferences.</span></span>  <br/> |
|<span data-ttu-id="34ad6-154">Test-CsExumConnectivity (ExumConnectivity)</span><span class="sxs-lookup"><span data-stu-id="34ad6-154">Test-CsExumConnectivity (ExumConnectivity)</span></span>  <br/> |<span data-ttu-id="34ad6-155">ユーザーが Exchange ユニファイド メッセージング (UM) に接続可能なのを確認します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-155">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span>  <br/> |
|<span data-ttu-id="34ad6-156">Test-CsGroupIM -TestJoinLauncher (JoinLauncher)</span><span class="sxs-lookup"><span data-stu-id="34ad6-156">Test-CsGroupIM -TestJoinLauncher (JoinLauncher)</span></span>  <br/> |<span data-ttu-id="34ad6-157">ユーザーが (Web アドレス リンクを使用して) スケジュールされた会議を作成して参加可能なユーザーを確認します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-157">Confirms that users are able to create and join scheduled meetings (by a web address link).</span></span>  <br/> |
|<span data-ttu-id="34ad6-158">Test-CsMCXP2PIM (MCXP2PIM)</span><span class="sxs-lookup"><span data-stu-id="34ad6-158">Test-CsMCXP2PIM (MCXP2PIM)</span></span>  <br/> |<span data-ttu-id="34ad6-159">モバイル デバイス ユーザーがインスタント メッセージの登録と送信を実行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-159">Confirms that mobile device users are able to register and send instant messages.</span></span>  <br/> |
|<span data-ttu-id="34ad6-160">Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)</span><span class="sxs-lookup"><span data-stu-id="34ad6-160">Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)</span></span>  <br/> |<span data-ttu-id="34ad6-161">ビデオ相互運用サーバーが立ち上がり、ビデオ SIP トランクを使用した着信接続を処理できるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-161">Confirms that Video Interop Server is up and can handle incoming connections over a video SIP trunk.</span></span>  <br/> <span data-ttu-id="34ad6-162">**注:** 従来のモバイル クライアントの MCX サポートは、Skype for Business Server 2019 では使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="34ad6-162">**Note:** MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> |
|<span data-ttu-id="34ad6-163">Test-CsPersistentChatMessage (PersistentChatMessage)</span><span class="sxs-lookup"><span data-stu-id="34ad6-163">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span>  <br/> |<span data-ttu-id="34ad6-164">ユーザーが常設チャット サービスを使用してメッセージを交換できるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-164">Confirms that users can exchange messages by using the Persistent Chat service.</span></span>  <br/> |
|<span data-ttu-id="34ad6-165">Test-CsUcwaConference (UcwaConference)</span><span class="sxs-lookup"><span data-stu-id="34ad6-165">Test-CsUcwaConference (UcwaConference)</span></span>  <br/> |<span data-ttu-id="34ad6-166">ユーザーが Web 経由で会議に参加可能なのを確認します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-166">Confirms that users can join conferences via the web.</span></span>  <br/> |
|<span data-ttu-id="34ad6-167">Test-CsUnifiedContactStore (UnifiedContactStore)</span><span class="sxs-lookup"><span data-stu-id="34ad6-167">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span>  <br/> |<span data-ttu-id="34ad6-168">統合連絡先ストアを通じてユーザーの連絡先にアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-168">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="34ad6-169">統合連絡先ストアを使用すると、ユーザーは Skype for Business Server 2015、Outlook メッセージングおよびコラボレーション クライアント、Outlook Web Access を使用してアクセスできる連絡先の単一セットを維持できます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-169">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Skype for Business Server 2015, Outlook messaging and collaboration client, and/or Outlook Web Access.</span></span>  <br/> |
|<span data-ttu-id="34ad6-170">Test-CsXmppIM (XmppIM)</span><span class="sxs-lookup"><span data-stu-id="34ad6-170">Test-CsXmppIM (XmppIM)</span></span>  <br/> |<span data-ttu-id="34ad6-171">インスタント メッセージが XMPP (Extensible Messaging and Presence Protocol) ゲートウェイを通して送信可能な状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-171">Confirms that an instant message can be sent across the Extensible Messaging and Presence Protocol (XMPP) gateway.</span></span>  <br/> <span data-ttu-id="34ad6-172">XMPP ゲートウェイとプロキシは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="34ad6-172">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span>  |

<span data-ttu-id="34ad6-173">System Center Operations Manager を使用するために監視ノードをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="34ad6-173">You do not need to install watcher nodes to use System Center Operations Manager.</span></span> <span data-ttu-id="34ad6-174">これらのノードをインストールしない場合でも、問題が発生するたびに Skype for Business Server 2015 コンポーネントからリアルタイムのアラートを取得できます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-174">If you do not install these nodes, you can still get real-time alerts from Skype for Business Server 2015 components whenever an issue occurs.</span></span> <span data-ttu-id="34ad6-175">(コンポーネントおよびユーザー管理パックでは監視ノードは使用されません)。ただし、アクティブ監視管理パックを使用してエンドツーエンドのシナリオを監視する場合は、監視ノードが必要です。</span><span class="sxs-lookup"><span data-stu-id="34ad6-175">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>
  
> [!NOTE]
> <span data-ttu-id="34ad6-176">管理者は、Operations Manager を使用またはインストールせずに、代理トランザクションを手動で実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-176">Administrators can also run synthetic transactions manually, without using or installing Operations Manager.</span></span> <span data-ttu-id="34ad6-177">Skype for Business Server 展開のサイズによっては、代理トランザクションで大量のコンピューター メモリとプロセッサ時間を使用できます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-177">Depending on the size of your Skype for Business Server deployment, synthetic transactions can use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="34ad6-178">そのため、監視ノードとして専用のコンピューターを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="34ad6-178">Because of this, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="34ad6-179">たとえば、監視ノードとして機能する Skype for Business Server フロント エンド サーバーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ad6-179">For example, you should not configure a Skype for Business Server Front End Server to act as a watcher node.</span></span> <span data-ttu-id="34ad6-180">監視ノードは、Skype for Business Server トポロジ内の他のコンピューターと同じ基本的なハードウェア要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ad6-180">Watcher nodes should meet the same basic hardware requirements as any other computer in your Skype for Business Server topology.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="34ad6-181">Lync Server 2013 と Skype for Business Server 2015 のコア システム ファイルは同じコンピューターにインストールできないので、従来の Lync Server 2013 監視ノードを Skype for Business Server 2015 監視ノードと同じコンピューターに同じコンピューターに同時に設置することはできません。</span><span class="sxs-lookup"><span data-stu-id="34ad6-181">A legacy Lync Server 2013 watcher node cannot be collocated on the same machine as a Skype for Business Server 2015 watcher node because the core system files for Lync Server 2013 and Skype for Business Server 2015 cannot be installed on the same computer.</span></span> <span data-ttu-id="34ad6-182">ただし、Skype for Business Server 2015 監視ノードは、Skype for Business Server 2015 と Lync Server 2013 を同時に監視できます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-182">However, Skype for Business Server 2015 watcher nodes can simultaneously monitor Skype for Business Server 2015 and Lync Server 2013.</span></span> <span data-ttu-id="34ad6-183">既定の代理トランザクションは、両方の製品バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="34ad6-183">Default synthetic transactions are supported for both product versions.</span></span> 
  
<span data-ttu-id="34ad6-184">Lync Server 2013 監視ノードは、次の点を確認するために、企業の内部または外部に展開できます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-184">Lync Server 2013 watcher nodes may be deployed inside or outside an enterprise to help verify:</span></span>
  
- <span data-ttu-id="34ad6-185">社内ユーザー用プールへの接続。</span><span class="sxs-lookup"><span data-stu-id="34ad6-185">Connectivity to pools for users inside the enterprise.</span></span>
    
- <span data-ttu-id="34ad6-186">社外で作業するリモート ユーザー向け境界ネットワーク経由の接続。</span><span class="sxs-lookup"><span data-stu-id="34ad6-186">Connectivity through perimeter networks for remote users working outside the enterprise.</span></span>
    
- <span data-ttu-id="34ad6-187">ブランチ オフィス アプライアンスへの接続。</span><span class="sxs-lookup"><span data-stu-id="34ad6-187">Connectivity to branch office appliances.</span></span>
    
- <span data-ttu-id="34ad6-188">企業内部および境界ネットワークを介した Lync Server 2013 への接続。</span><span class="sxs-lookup"><span data-stu-id="34ad6-188">Connectivity to Lync Server 2013 inside the enterprise and through perimeter networks.</span></span>
    
<span data-ttu-id="34ad6-189">管理を簡素化するために、企業の内部と外部で異なる認証オプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-189">To help simplify administration, different authentication options are available for inside and outside of the enterprise.</span></span> <span data-ttu-id="34ad6-190">詳細については、「代理トランザクション [を実行する監視ノードを構成する」を参照してください](watcher-nodes.md#enable_synthetic_trans)。</span><span class="sxs-lookup"><span data-stu-id="34ad6-190">For details, see [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).</span></span>
  
<span data-ttu-id="34ad6-191">監視ノードとして機能するコンピューターを構成するには、まず次の前提条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ad6-191">To configure a computer to act as a watcher node, you must first complete the following prerequisites:</span></span> 
  
- <span data-ttu-id="34ad6-192">System Center Operations Manager をインストールし、Skype for Business Server 2015 管理パックをインポートします。</span><span class="sxs-lookup"><span data-stu-id="34ad6-192">Install System Center Operations Manager and import the Skype for Business Server 2015 management packs.</span></span> <span data-ttu-id="34ad6-193">また、最初に監視ノード コンピューターが Skype for Business Server 2015 をインストールするためのすべての前提条件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ad6-193">You must also first verify that the watcher node computer meets all prerequisites for installing Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="34ad6-194">監視ノード コンピューターに次の項目をインストールします。</span><span class="sxs-lookup"><span data-stu-id="34ad6-194">Install the following items on the watcher node computer:</span></span>
    
  - <span data-ttu-id="34ad6-195">.NET Framework 4.5 のフル バージョン</span><span class="sxs-lookup"><span data-stu-id="34ad6-195">The full version of .NET Framework 4.5</span></span>
    
  - <span data-ttu-id="34ad6-196">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="34ad6-196">Windows Identity Foundation</span></span>
    
  - <span data-ttu-id="34ad6-197">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="34ad6-197">Windows PowerShell 3.0</span></span>
    
<span data-ttu-id="34ad6-198">前提条件を満たした後、次の手順に従って監視ノードを構成できます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-198">After the prerequisites are met, you can configure the watcher node by following these steps:</span></span>
  
1. <span data-ttu-id="34ad6-199">監視ノード コンピューターに Skype for Business Server 2015 コア ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="34ad6-199">Install the Skype for Business Server 2015 core files on the watcher node computer.</span></span>
    
2. <span data-ttu-id="34ad6-200">System Center Operations Manager エージェントを監視ノード コンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="34ad6-200">Install System Center Operations Manager agent on the watcher node computer.</span></span>
    
3. <span data-ttu-id="34ad6-201">実行可能ファイルWatchernode.msi実行します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-201">Run the Watchernode.msi executable file.</span></span>
    
4. <span data-ttu-id="34ad6-202">**New-CsWatcherNodeConfiguration** コマンドレットを使用して、監視ノードで使用するテスト ユーザー アカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-202">Use the **New-CsWatcherNodeConfiguration** cmdlet to configure test user accounts to be employed by the watcher node.</span></span>
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a><span data-ttu-id="34ad6-203">Skype for Business Server 2015 コア ファイルと RTCLocal データベースをインストールする</span><span class="sxs-lookup"><span data-stu-id="34ad6-203">Install the Skype for Business Server 2015 Core Files and the RTCLocal Database</span></span>

<span data-ttu-id="34ad6-204">Skype for Business Server 2015 のコア ファイルをコンピューターにインストールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-204">To install the Skype for Business Server 2015 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="34ad6-205">RTCLocal データベースは、コア ファイルをインストールすると自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-205">The RTCLocal database will automatically be installed when you install the core files.</span></span> <span data-ttu-id="34ad6-206">監視ノードに新しいSQL Serverする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="34ad6-206">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="34ad6-207">SQL Server Express は自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-207">SQL Server Express will be automatically installed.</span></span>
  
<span data-ttu-id="34ad6-208">Skype for Business Server 2015 のコア ファイルと RTCLocal データベースをインストールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-208">To install the Skype for Business Server 2015 core files and the RTCLocal database:</span></span>
  
1. <span data-ttu-id="34ad6-209">監視ノード コンピューターで、[スタート] ボタン、[すべてのプログラム]、[アクセサリ] の順にクリックし、[コマンド プロンプト] を右クリックし、[管理者として実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ad6-209">On the watcher node computer, click Start, click All Programs, click Accessories, right-click Command Prompt, and then click Run as administrator.</span></span>
    
2. <span data-ttu-id="34ad6-210">コンソール ウィンドウで、次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-210">In the console window, type the following command and press ENTER.</span></span> <span data-ttu-id="34ad6-211">Skype for Business Server セットアップ ファイルへの適切なパスを入力してください:D:\Setup.exe /BootstrapLocalMgmt。コア Skype for Business Server コンポーネントが正常にインストールされていることを確認し、[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business Server 2015]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ad6-211">Be sure to enter the appropriate path to your Skype for Business Server setup files: D:\Setup.exe /BootstrapLocalMgmtTo verify that the core Skype for Business Server components are successfully installed, click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server Management Shell**.</span></span> <span data-ttu-id="34ad6-212">Skype for Business Server 管理シェルで、次のコマンドを入力Windows PowerShell Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-212">In the Skype for Business Server Management Shell, type the following Windows PowerShell command and press ENTER:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> <span data-ttu-id="34ad6-213">このコマンドを初めて実行する場合、監視ノード コンピューターをまだ構成していないので、データは返されません。</span><span class="sxs-lookup"><span data-stu-id="34ad6-213">The first time you run this command, no data will be returned because you have not yet configured any watcher node computers.</span></span> <span data-ttu-id="34ad6-214">コマンドがエラーを返さずに実行される場合は、Skype for Business Server のセットアップが正常に完了したと想定できます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-214">If the command runs without returning an error, you can assume that the Skype for Business Server setup completed successfully.</span></span> 
  
<span data-ttu-id="34ad6-215">監視ノード コンピューターが境界ネットワーク内にある場合は、次のコマンドを実行して Skype for Business Server 2015 のインストールを確認できます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-215">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Skype for Business Server 2015:</span></span>
  
<span data-ttu-id="34ad6-216">Get-CsPinPolicyYou、組織で使用するように構成されている PIN ポリシーの数に応じて、次のような情報を受信します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-216">Get-CsPinPolicyYou will receive information similar to this, depending on the number of PIN policies configured for use in your organization:</span></span>
  
<span data-ttu-id="34ad6-217">Identity : Global</span><span class="sxs-lookup"><span data-stu-id="34ad6-217">Identity : Global</span></span>
  
<span data-ttu-id="34ad6-218">説明 :</span><span class="sxs-lookup"><span data-stu-id="34ad6-218">Description :</span></span>
  
<span data-ttu-id="34ad6-219">MinPasswordLength : 5</span><span class="sxs-lookup"><span data-stu-id="34ad6-219">MinPasswordLength : 5</span></span>
  
<span data-ttu-id="34ad6-220">PINHistoryCount : 0</span><span class="sxs-lookup"><span data-stu-id="34ad6-220">PINHistoryCount : 0</span></span>
  
<span data-ttu-id="34ad6-221">AllowCommonPatterns : False</span><span class="sxs-lookup"><span data-stu-id="34ad6-221">AllowCommonPatterns : False</span></span>
  
<span data-ttu-id="34ad6-222">PINLifetime : 0</span><span class="sxs-lookup"><span data-stu-id="34ad6-222">PINLifetime : 0</span></span>
  
<span data-ttu-id="34ad6-223">MaximumLogonAttempts :</span><span class="sxs-lookup"><span data-stu-id="34ad6-223">MaximumLogonAttempts :</span></span>
  
<span data-ttu-id="34ad6-224">PIN ポリシーに関する情報が表示された場合は、コア コンポーネントが正常にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="34ad6-224">If you see information about your PIN policies, the core components have been successfully installed.</span></span>
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a><span data-ttu-id="34ad6-225">監視ノードに Operation Manager エージェント ファイルをインストールする</span><span class="sxs-lookup"><span data-stu-id="34ad6-225">Install the Operation Manager Agent Files on a Watcher Node</span></span>

<span data-ttu-id="34ad6-226">コンポーネントの警告を報告する Skype for Business Server のセットアップと同様に、Skype for Business Server 2015 監視ノードには System Center Operations Manager エージェント ファイルをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ad6-226">Similar to Skype for Business Server setup for reporting component alerts, a Skype for Business Server 2015 watcher node requires System Center Operations Manager agent files to be installed.</span></span> <span data-ttu-id="34ad6-227">これにより、代理トランザクションを実行し、System Center Operations Manager ルート管理サーバーに警告を報告できます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-227">This enables the synthetic transactions to be run and alerts to be reported to the System Center Operations Manager Root Management Server.</span></span>
  
<span data-ttu-id="34ad6-228">エージェント ファイルをインストールするには、「監視対象の Skype for Business Server コンピューターを構成する」に記載されている [手順に従います](configure-computers-to-monitor.md)。</span><span class="sxs-lookup"><span data-stu-id="34ad6-228">To install the agent files, follow the procedures listed in [Configure the Skype for Business Server computers that will be monitored](configure-computers-to-monitor.md).</span></span>
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a><span data-ttu-id="34ad6-229">代理トランザクションを実行する監視ノードを構成する</span><span class="sxs-lookup"><span data-stu-id="34ad6-229">Configure a Watcher Node to Run Synthetic Transactions</span></span>
<span data-ttu-id="34ad6-230"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="34ad6-230"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="34ad6-231">System Center Operations Manager エージェント ファイルをインストールしたら、監視ノード自体を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ad6-231">After the System Center Operations Manager agent files have been installed, you must configure the watcher node itself.</span></span> <span data-ttu-id="34ad6-232">これを行う手順は、監視ノード コンピューターが境界ネットワーク内にあるか、境界ネットワークの外側にあるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="34ad6-232">The steps you take to do this will vary, depending on whether your watcher node computer is inside your perimeter network or outside your perimeter network.</span></span> 
  
<span data-ttu-id="34ad6-233">監視ノードの構成時には、そのノードが使用する認証方法の種類も選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ad6-233">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="34ad6-234">Skype for Business Server 2015 では、信頼済みサーバー認証と資格情報認証の 2 つの認証方法のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-234">Skype for Business Server 2015 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="34ad6-235">次の表に、これら 2 つの方法の違いを示します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-235">The following table shows the differences between these two methods:</span></span>
  
||<span data-ttu-id="34ad6-236">**説明**</span><span class="sxs-lookup"><span data-stu-id="34ad6-236">**Description**</span></span>|<span data-ttu-id="34ad6-237">**サポートされる場所**</span><span class="sxs-lookup"><span data-stu-id="34ad6-237">**Locations supported**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="34ad6-238">TrustedServer</span><span class="sxs-lookup"><span data-stu-id="34ad6-238">TrustedServer</span></span>  <br/> |<span data-ttu-id="34ad6-239">内部サーバーを偽装する証明書を使用し、認証チャレンジをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="34ad6-239">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span>  <br/> <span data-ttu-id="34ad6-240">各監視ノードで多数のユーザー パスワードを管理するのではなく、1 つの証明書を管理することを希望する管理者に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-240">Useful for administrators who prefer to manage a single certificate, instead of many user passwords on each watcher node.</span></span>  <br/> |<span data-ttu-id="34ad6-241">エンタープライズの内側。</span><span class="sxs-lookup"><span data-stu-id="34ad6-241">Inside the enterprise.</span></span>  <br/> <span data-ttu-id="34ad6-242">この方法では、監視ノードは監視対象のプールと同じドメインに含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ad6-242">With this method, the watcher node must be in the same domain as the pools being monitored.</span></span> <span data-ttu-id="34ad6-243">監視ノードとプールが異なるドメインにある場合は、代わりに資格情報認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-243">If the watcher node and the pools are in different domains, use Credential Authentication instead.</span></span>  <br/> |
|<span data-ttu-id="34ad6-244">ネゴシエート</span><span class="sxs-lookup"><span data-stu-id="34ad6-244">Negotiate</span></span>  <br/> |<span data-ttu-id="34ad6-245">ユーザー名とパスワードを各監視ノードの Windows 資格情報マネージャーに保管します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-245">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span>  <br/> <span data-ttu-id="34ad6-246">このモードでは、より多くのパスワード管理が必要ですが、企業外の監視ノードの唯一のオプションです。</span><span class="sxs-lookup"><span data-stu-id="34ad6-246">This mode requires more password management, but is the only option for watcher nodes outside the enterprise.</span></span> <span data-ttu-id="34ad6-247">このような外側に位置する監視ノードを認証の際に信頼済みのエンドポイントとして扱うことはできません。</span><span class="sxs-lookup"><span data-stu-id="34ad6-247">These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span>  <br/> |<span data-ttu-id="34ad6-248">エンタープライズの外側。</span><span class="sxs-lookup"><span data-stu-id="34ad6-248">Outside the enterprise.</span></span>  <br/> <span data-ttu-id="34ad6-249">エンタープライズの内側。</span><span class="sxs-lookup"><span data-stu-id="34ad6-249">Inside the enterprise.</span></span>  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a><span data-ttu-id="34ad6-250">信頼済みサーバー認証を使用する監視ノードを構成する</span><span class="sxs-lookup"><span data-stu-id="34ad6-250">Configure a Watcher Node to Use Trusted Server Authentication</span></span>
<span data-ttu-id="34ad6-251"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="34ad6-251"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="34ad6-252">監視ノード コンピューターが境界ネットワーク内にある場合、信頼済みサーバー認証を使用すると、多数のユーザー アカウント パスワードを使用するのではなく、単一の証明書を維持することで管理タスクを大幅に削減できます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-252">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration tasks by maintaining a single certificate, rather than using numerous user account passwords.</span></span>
  
<span data-ttu-id="34ad6-253">信頼済みサーバー認証を構成するには、最初に監視ノード コンピューターをホストする信頼されたアプリケーション プールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ad6-253">To configure Trusted Server authentication, you must first create a trusted application pool to host the watcher node computer.</span></span> <span data-ttu-id="34ad6-254">信頼されたアプリケーション プールを作成したら、その監視ノードで代理トランザクションを構成して、信頼されたアプリケーションとして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ad6-254">After you've created the trusted application pool, you must then configure synthetic transactions on that watcher node to run as trusted applications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="34ad6-255">信頼済みアプリケーションとは、Skype for Business Server 2015 の一部として実行する信頼できる状態が与えられるアプリケーションですが、製品の組み込みの一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="34ad6-255">A trusted application is an application that is given trusted status to run as part of Skype for Business Server 2015, but is not a built-in part of the product.</span></span> <span data-ttu-id="34ad6-256">信頼済みステータスのアプリケーションは、実行のたびに認証でチャレンジされることはありません。</span><span class="sxs-lookup"><span data-stu-id="34ad6-256">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>
  
<span data-ttu-id="34ad6-257">信頼されたアプリケーション プールを作成するには、Skype for Business Server 管理シェルを開き、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-257">To create a trusted application pool, open the Skype for Business Server Management Shell and run a command similar to this:</span></span>
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> <span data-ttu-id="34ad6-258">前のコマンドのパラメーターの詳細については、Skype for Business Server 管理シェル プロンプトから次を入力します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-258">For details about the parameters in the preceding command, type the following from the Skype for Business Server Management Shell prompt:</span></span> 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

<span data-ttu-id="34ad6-259">信頼されたアプリケーション プールを作成した後 **、New-CsTrustedApplication** コマンドレットと次のようなコマンドを使用して、代理トランザクションを信頼されたアプリケーションとして実行する監視ノード コンピューターを構成できます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-259">After creating the trusted application pool, you can then configure the watcher node computer to run synthetic transactions as a trusted application by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

<span data-ttu-id="34ad6-260">このコマンドが完了し、信頼されたアプリケーションが作成されると **、Enable-CsTopology** コマンドレットを実行して、変更が有効になつながっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ad6-260">When this command completes and the trusted application is created, you must then run the **Enable-CsTopology** cmdlet to make sure that the changes take effect:</span></span>
  
```PowerShell
Enable-CsTopology
```

<span data-ttu-id="34ad6-261">監視ノード コンピューター アカウントでは、一部の代理トランザクションについて CMS を照会する機能が必要です。</span><span class="sxs-lookup"><span data-stu-id="34ad6-261">The watcher node computer account requires the ability to query CMS for some synthetic transactions.</span></span> <span data-ttu-id="34ad6-262">この機能を許可するには、監視ノードのコンピューター アカウントを RTCUniversalReadOnlyAdmins セキュリティ グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-262">To allow this ability, add the computer account of the watcher node to the RTCUniversalReadOnlyAdmins security group.</span></span> <span data-ttu-id="34ad6-263">レプリケーションADしたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-263">Once AD replication has occurred, restart the computer.</span></span>
  
<span data-ttu-id="34ad6-264">新しい信頼済みアプリケーションが作成されたのを確認するには、Skype for Business Server 管理シェル プロンプトで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-264">To verify that the new trusted application has been created, type the following at the Skype for Business Server Management Shell prompt:</span></span>
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="34ad6-265">監視ノードで既定の証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="34ad6-265">Configure a Default Certificate on the Watcher Node</span></span>
<span data-ttu-id="34ad6-266"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="34ad6-266"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="34ad6-267">TrustedServer 認証を使用する各監視ノードには、Skype for Business Server 展開ウィザードを使用して割り当てられた既定の証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="34ad6-267">Each watcher node that uses TrustedServer authentication must have a Default certificate assigned by using the Skype for Business Server Deployment wizard.</span></span> 
  
<span data-ttu-id="34ad6-268">既定の証明書を割り当てるには、</span><span class="sxs-lookup"><span data-stu-id="34ad6-268">To assign a Default certificate:</span></span>
  
1. <span data-ttu-id="34ad6-269">[スタート] ボタン、[すべてのプログラム] の順にクリックし、Skype for Business Server 2015 をクリックして、Skype for Business Server 展開ウィザードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ad6-269">Click Start, click All Programs, click Skype for Business Server 2015, and then click Skype for Business Server Deployment Wizard.</span></span> 
    
2. <span data-ttu-id="34ad6-270">Skype for Business Server 展開ウィザードで、[Skype for Business Server システムのインストールまたは更新] をクリックし、[要求、インストール、または証明書の割り当て] という見出しの下の [実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ad6-270">In the Skype for Business Server Deployment Wizard, click Install or Update Skype for Business Server System, and then click Run under the heading Request, Install, or Assign Certificate.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="34ad6-271">[実行] ボタンをが無効になっている場合は、[ローカル構成ストアのインストール] で [実行] を最初にクリックしなければならないことがあります。</span><span class="sxs-lookup"><span data-stu-id="34ad6-271">If the Run button is disabled, you may need to first click Run under Install Local Configuration Store.</span></span> 
  
<span data-ttu-id="34ad6-272">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="34ad6-272">Do one of the following:</span></span>
  
- <span data-ttu-id="34ad6-273">既定の証明書として使用できる証明書が既にある場合は、証明書ウィザードで [既定] をクリックし、[割り当て] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ad6-273">If you already have a certificate that can be used as the Default certificate, click Default in the Certificate wizard, and then click Assign.</span></span> <span data-ttu-id="34ad6-274">証明書の割り当てウィザードの手順に従って、証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-274">Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
- <span data-ttu-id="34ad6-275">既定の証明書を使用するための証明書を要求する必要がある場合は、[要求] をクリックし、証明書要求ウィザードの手順に従って証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-275">If you need to request a certificate for use the Default certificate, click Request, and then follow the steps in the Certificate Request wizard to request that certificate.</span></span> <span data-ttu-id="34ad6-276">Web サーバー証明書の既定値を使用すると、既定の証明書として割り当てることができる証明書を取得できます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-276">If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>
    
## <a name="install-and-configure-a-watcher-node"></a><span data-ttu-id="34ad6-277">監視ノードのインストールと構成</span><span class="sxs-lookup"><span data-stu-id="34ad6-277">Install and Configure a Watcher Node</span></span>
<span data-ttu-id="34ad6-278"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="34ad6-278"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="34ad6-279">監視ノード コンピューターを再起動し、証明書を構成した後、次のコマンドでファイルを実行Watchernode.msi。</span><span class="sxs-lookup"><span data-stu-id="34ad6-279">After you have restarted the watcher node computer and configured a certificate, you must run the file Watchernode.msi.</span></span> <span data-ttu-id="34ad6-280">(Operations Manager エージェント Watchernode.msi Skype for Business Server 2015 コア コンポーネントの両方がインストールされている任意のコンピューターで、このコマンドを実行する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="34ad6-280">(You must run Watchernode.msi on any computer where both the Operations Manager agent files and the Skype for Business Server 2015 core components are installed.)</span></span> 
  
<span data-ttu-id="34ad6-281">監視ノードをインストールして構成するには:</span><span class="sxs-lookup"><span data-stu-id="34ad6-281">To install and configure a watcher node:</span></span>
  
1. <span data-ttu-id="34ad6-282">[スタート] ボタン、[すべてのプログラム] の順にクリックし、[Skype for Business Server 2015] をクリックし、[Skype for Business Server 管理シェル] をクリックして、Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-282">Open the Skype for Business Server Management Shell by clicking Start, clicking All Programs, clicking Skype for Business Server 2015, and then clicking Skype for Business Server Management Shell.</span></span> 
    
2. <span data-ttu-id="34ad6-283">管理シェルで次のコマンドを入力し、Enter キーを押します (このコマンドのコピーへの実際のパスを指定Watchernode.msi)。</span><span class="sxs-lookup"><span data-stu-id="34ad6-283">In the Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> <span data-ttu-id="34ad6-284">コマンド ウィンドウから Watchernode.msi n を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-284">You can also run Watchernode.msi n from a command window.</span></span> <span data-ttu-id="34ad6-285">コマンド ウィンドウを開くには、[スタート] をクリックし、[コマンド プロンプト] を右クリックして、[管理者として実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ad6-285">To open a command window, click Start, right-click Command Prompt, and then click Run as administrator.</span></span> <span data-ttu-id="34ad6-286">コマンド ウィンドウが開いたら、上記の手順 2 と同じコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-286">When the command window opens, type the same command shown in step 2, above.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="34ad6-287">前のコマンドでは、名前と値のペア Authentication=TrustedServer では大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-287">In the preceding command, the name/value pair Authentication=TrustedServer is case-sensitive.</span></span> <span data-ttu-id="34ad6-288">次に示すとおりに入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ad6-288">It must be typed exactly as shown.</span></span> <span data-ttu-id="34ad6-289">たとえば、次のコマンドは正しい大文字小文字を使用しないので失敗します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-289">For example, this command will fail because it does not use the correct letter casing:</span></span> 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

<span data-ttu-id="34ad6-290">TrustedServer モードは、境界ネットワーク内にあるコンピューターでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-290">TrustedServer mode can be used only with computers that lie inside the perimeter network.</span></span> <span data-ttu-id="34ad6-291">監視ノードが TrustedServer モードで実行されている場合、管理者はコンピューター上でテスト ユーザー パスワードを保持する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="34ad6-291">When a watcher node runs in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a><span data-ttu-id="34ad6-292">ネゴシエートを使用する監視ノードを構成する</span><span class="sxs-lookup"><span data-stu-id="34ad6-292">Configure a Watcher Node to Use Negotiate</span></span>
<span data-ttu-id="34ad6-293"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="34ad6-293"><a name="enable_synthetic_trans"> </a></span></span>

<span data-ttu-id="34ad6-294">監視ノード コンピューターが境界ネットワークの外側にある場合、代理トランザクションを実行するために監視ノードを構成するには、少し異なる手順に従う必要があります。特に、信頼されたアプリケーション プールや信頼されたアプリケーションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ad6-294">If your watcher node computer lies outside the perimeter network then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions: in particular, you should not create a trusted application pool or a trusted application.</span></span> <span data-ttu-id="34ad6-295">つまり、次の 2 つのタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ad6-295">That means that you will need to complete the next two tasks.</span></span>
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="34ad6-296">RTC Local Read-Only Administrators グループのメンバーシップを更新する</span><span class="sxs-lookup"><span data-stu-id="34ad6-296">Update Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="34ad6-297">監視ノードが境界ネットワークの外側にある場合は、監視ノードで次の手順を実行して、監視ノード コンピューターの RTC Local Read-only Administrators グループにネットワーク サービス アカウントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ad6-297">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer by completing the following procedure on the watcher node:</span></span>
  
1. <span data-ttu-id="34ad6-298">[スタート] メニューの [コンピューター] を右クリックし、[管理] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ad6-298">Click Start, right-click Computer, and then click Manage.</span></span>
    
2. <span data-ttu-id="34ad6-299">サーバー マネージャーで、[構成]、[ローカル ユーザーとグループ] の順に展開し、[グループ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ad6-299">In Server Manager, expand Configuration, expand Local Users and Groups, and then click Groups.</span></span>
    
3. <span data-ttu-id="34ad6-300">[グループ] ウィンドウで、[RTC Local Read-only Administrators] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ad6-300">In the Groups pane, double-click RTC Local Read-only Administrators.</span></span>
    
4. <span data-ttu-id="34ad6-301">[RTC Local Read-only Administrators のプロパティ] ダイアログ ボックスで、[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ad6-301">In the RTC Local Read-only Administrators Properties dialog box, click Add.</span></span>
    
5. <span data-ttu-id="34ad6-302">[ユーザー、コンピューター、サービス アカウント、またはグループの選択] ダイアログで、[場所] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ad6-302">In the Select Users, Computers, Service Accounts, or Groups dialog box, click Locations.</span></span>
    
6. <span data-ttu-id="34ad6-303">[場所] ダイアログ ボックスで、ウォッチャー ノード コンピューターの名前を選択し、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ad6-303">In the Locations dialog box, select the name of the watcher node computer, and then click OK.</span></span>
    
7. <span data-ttu-id="34ad6-304">[選択するオブジェクト名を入力してください] ボックスに、「Network Service」と入力し、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ad6-304">In the Enter object names to select box, type Network Service, and then click OK.</span></span>
    
8. <span data-ttu-id="34ad6-305">[RTC Local Read-only Administrators のプロパティ] ダイアログ ボックスで、[OK] をクリックし、[サーバー マネージャー] を閉じます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-305">In the RTC Local Read-only Administrators Properties dialog box, click OK, and then close Server Manager.</span></span>
    
9. <span data-ttu-id="34ad6-306">ウォッチャー ノード コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-306">Restart the watcher node computer.</span></span>
    
### <a name="install-the-watcher-node-configuration-files"></a><span data-ttu-id="34ad6-307">監視ノード構成ファイルをインストールする</span><span class="sxs-lookup"><span data-stu-id="34ad6-307">Install the Watcher Node Configuration Files</span></span>

<span data-ttu-id="34ad6-308">次の手順では、次の手順でファイルを実行Watchernode.msi。</span><span class="sxs-lookup"><span data-stu-id="34ad6-308">Your next step is to run the file Watchernode.msi:</span></span> 
  
1. <span data-ttu-id="34ad6-309">Microsoft Skype for Business Server 2015 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-309">Open the Microsoft Skype for Business Server 2015 Management Shell.</span></span> <span data-ttu-id="34ad6-310">[スタート] ボタン、[すべてのプログラム] の順にクリックし、[Microsoft Skype for Business Server 2015] をクリックして、[Skype for Business Server 管理シェル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ad6-310">Click Start, click All Programs, click Microsoft Skype for Business Server 2015, and then click Skype for Business Server Management Shell.</span></span> 
    
2. <span data-ttu-id="34ad6-311">Skype for Business Server 管理シェルで、次のコマンドを入力し、Enter キーを押します (必ず、サーバーのコピーへの実際のパスをWatchernode.msi。</span><span class="sxs-lookup"><span data-stu-id="34ad6-311">In Skype for Business Server Management Shell, type the following command, and then press ENTER (be sure to specify the actual path to your copy of Watchernode.msi):</span></span>
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> <span data-ttu-id="34ad6-312">前述したように、Watchernode.msiウィンドウから実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-312">As mentioned previously, Watchernode.msi can also be run from a command window.</span></span> <span data-ttu-id="34ad6-313">コマンド ウィンドウを開くには、[**スタート**] をクリックし、[**コマンド プロンプト**] を右クリックして、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34ad6-313">To open a command window, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="34ad6-314">コマンド ウィンドウが開いたら、上記の手順 2 と同じコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="34ad6-314">When the command window opens, type the same command shown in step 2, above.</span></span> 
  
<span data-ttu-id="34ad6-315">ウォッチャー ノードを信頼されたアプリケーション プールとしてセットアップできない場合はいつでも、ネゴシエート モードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="34ad6-315">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool.</span></span> <span data-ttu-id="34ad6-316">このモードでは、管理者がウォッチャー ノードのテスト ユーザー パスワードを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34ad6-316">In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>
  

