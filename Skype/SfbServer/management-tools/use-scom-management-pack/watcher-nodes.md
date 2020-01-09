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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: '概要: Skype for Business Server の代理トランザクション用にウォッチャーノードをインストールして構成します。'
ms.openlocfilehash: 7711c7c2009149fc6dd49ed34b4c55312cb7417a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992444"
---
# <a name="install-and-configure-watcher-nodes"></a><span data-ttu-id="1f563-103">監視ノードのインストールと構成</span><span class="sxs-lookup"><span data-stu-id="1f563-103">Install and configure watcher nodes</span></span>
 
<span data-ttu-id="1f563-104">**概要:** Skype for Business Server の代理トランザクション用にウォッチャーノードをインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="1f563-104">**Summary:** Install and configure watcher nodes for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="1f563-105">ウォッチャーノードは、Skype for Business Server の代理トランザクションを定期的に実行するコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="1f563-105">Watcher nodes are computers that periodically run Skype for Business Server synthetic transactions.</span></span> <span data-ttu-id="1f563-106">代理トランザクションは、Windows PowerShell コマンドレットであり、サインインや exchange のインスタントメッセージなどの主要なユーザーシナリオが期待どおりに機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f563-106">Synthetic transactions are Windows PowerShell cmdlets that verify that key user scenarios, such as the ability to sign in or to exchange instant messages, are working as expected.</span></span> <span data-ttu-id="1f563-107">Skype for Business Server 2015 の場合、System Center Operations Manager は、次の表に示す代理トランザクションを実行できます。これには、3つの組み込みトランザクションの種類が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1f563-107">For Skype for Business Server 2015, System Center Operations Manager can run the synthetic transactions shown in the following table, which includes three synthetic transaction types:</span></span>
  
- <span data-ttu-id="1f563-108">**既定値**ウォッチャーノードが既定で実行する代理トランザクション。</span><span class="sxs-lookup"><span data-stu-id="1f563-108">**Default** Synthetic transactions that a watcher node runs by default.</span></span> <span data-ttu-id="1f563-109">新しいウォッチャーノードを作成するときに、そのノードが実行する代理トランザクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="1f563-109">When you create a new watcher node, you can specify which synthetic transactions that node will run.</span></span> <span data-ttu-id="1f563-110">(これは、CsWatcherNodeConfiguration コマンドレットで使用されるテストパラメーターの目的です。)ウォッチャーノードが作成されたときに Tests パラメーターを使用しないと、既定のすべての合成トランザクションが自動的に実行され、既定以外の代理トランザクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="1f563-110">(That's the purpose of the Tests parameter used by the New-CsWatcherNodeConfiguration cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="1f563-111">つまり、たとえば、watcher ノードは、CsAddressBookService のテストを実行するように構成されていますが、テスト-CsExumConnectivity テストを実行するように構成されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1f563-111">This means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>
    
- <span data-ttu-id="1f563-112">**既定以外の**場合ウォッチャーノードが既定で実行されていないことをテストします。</span><span class="sxs-lookup"><span data-stu-id="1f563-112">**Non-default** Tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="1f563-113">(詳しくは、「既定の型の説明」をご覧ください)。ただし、ウォッチャーノードを有効にして、既定以外の代理トランザクションのいずれかを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="1f563-113">(For details, see the description of the Default type.) However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="1f563-114">これは、(CsWatcherNodeConfiguration コマンドレットを使用して) ウォッチャーノードを作成するとき、またはウォッチャーノードを作成した後であれば、いつでも行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1f563-114">You can do this when you create the watcher node (by using the New-CsWatcherNodeConfiguration cmdlet), or any time after the watcher node has been created.</span></span> <span data-ttu-id="1f563-115">既定以外の代理トランザクションの多くには、追加のセットアップ手順が必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1f563-115">Note that many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="1f563-116">これらの手順の詳細については、「[代理トランザクション用の特別なセットアップ手順](test-users-and-settings.md#special_synthetictrans)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f563-116">For more details about these steps, see [Special Setup Instructions for Synthetic Transactions](test-users-and-settings.md#special_synthetictrans).</span></span>
    
- <span data-ttu-id="1f563-117">**拡張**特別な種類の既定以外の代理トランザクション。</span><span class="sxs-lookup"><span data-stu-id="1f563-117">**Extended** A special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="1f563-118">他の代理トランザクションとは異なり、拡張テストは、1 回のパスで複数回実行できます。</span><span class="sxs-lookup"><span data-stu-id="1f563-118">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="1f563-119">これは、プールに対する複数の公衆交換電話網 (PSTN) 音声ルートなどの動作を検証するときに便利です。</span><span class="sxs-lookup"><span data-stu-id="1f563-119">This is useful when verifying behavior, such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="1f563-120">これは、拡張テストの複数のインスタンスを監視ノードに追加するだけで構成できます。</span><span class="sxs-lookup"><span data-stu-id="1f563-120">You can configure this simply by adding multiple instances of an extended test to a watcher node.</span></span>
    
<span data-ttu-id="1f563-121">監視ノードに他の代理トランザクションを追加する方法については、「[Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f563-121">For details about the process for adding other synthetic transactions to a watcher node, see [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).</span></span> <span data-ttu-id="1f563-122">また、Skype for Business Server 管理シェルを使って、ウォッチャーノードから合成トランザクションを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="1f563-122">You can also use Skype for Business Server Management Shell to remove synthetic transactions from a watcher node.</span></span>
  
<span data-ttu-id="1f563-123">監視ノードで使用できる代理トランザクションは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1f563-123">The synthetic transactions available to watcher nodes include the following:</span></span>
  
|<span data-ttu-id="1f563-124">**コマンドレット名 (テスト名)**</span><span class="sxs-lookup"><span data-stu-id="1f563-124">**Cmdlet Name (Test Name)**</span></span>|<span data-ttu-id="1f563-125">**説明**</span><span class="sxs-lookup"><span data-stu-id="1f563-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1f563-126">Test-CsAddressBookService (ABS)</span><span class="sxs-lookup"><span data-stu-id="1f563-126">Test-CsAddressBookService (ABS)</span></span>  <br/> |<span data-ttu-id="1f563-127">ユーザーが連絡先リストに含まれていないユーザーを検索できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f563-127">Confirms that users are able to look up users who aren't in their contact list.</span></span>  <br/> |
|<span data-ttu-id="1f563-128">Test-CsAddressBookWebQuery (ABWQ)</span><span class="sxs-lookup"><span data-stu-id="1f563-128">Test-CsAddressBookWebQuery (ABWQ)</span></span>  <br/> |<span data-ttu-id="1f563-129">ユーザーが、連絡先リストに含まれていないユーザーを HTTP 経由で検索できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f563-129">Confirms that users are able to look up users who aren't in their contact list via HTTP.</span></span>  <br/> |
|<span data-ttu-id="1f563-130">Test-CsAVConference (AvConference)</span><span class="sxs-lookup"><span data-stu-id="1f563-130">Test-CsAVConference (AvConference)</span></span>  <br/> |<span data-ttu-id="1f563-131">ユーザーが音声/ビデオ会議で作成と参加が可能なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f563-131">Confirms that users are able to create and participate in an audio/video conference.</span></span>  <br/> |
|<span data-ttu-id="1f563-132">Test-CsGroupIM (IM Conferencing)</span><span class="sxs-lookup"><span data-stu-id="1f563-132">Test-CsGroupIM (IM Conferencing)</span></span>  <br/> |<span data-ttu-id="1f563-133">ユーザーが会議中にインスタント メッセージを送信でき、3 人以上のユーザーとインスタント メッセージでの会話に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f563-133">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span>  <br/> |
|<span data-ttu-id="1f563-134">Test-CsIM (P2P IM)</span><span class="sxs-lookup"><span data-stu-id="1f563-134">Test-CsIM (P2P IM)</span></span>  <br/> |<span data-ttu-id="1f563-135">ユーザーがピアツーピア インスタント メッセージを送信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f563-135">Confirms that users are able to send peer-to-peer instant messages.</span></span>  <br/> |
|<span data-ttu-id="1f563-136">Test-CsP2PAV (P2PAV)</span><span class="sxs-lookup"><span data-stu-id="1f563-136">Test-CsP2PAV (P2PAV)</span></span>  <br/> |<span data-ttu-id="1f563-137">ユーザーがピアツーピア音声通話を開始できることを確認します (シグナリングのみ)。</span><span class="sxs-lookup"><span data-stu-id="1f563-137">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span>  <br/> |
|<span data-ttu-id="1f563-138">Test-CsPresence (Presence)</span><span class="sxs-lookup"><span data-stu-id="1f563-138">Test-CsPresence (Presence)</span></span>  <br/> |<span data-ttu-id="1f563-139">ユーザーが他のユーザーのプレゼンスを表示できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f563-139">Confirms that users are able to view other users' presence.</span></span>  <br/> |
|<span data-ttu-id="1f563-140">Test-CsRegistration (Registration)</span><span class="sxs-lookup"><span data-stu-id="1f563-140">Test-CsRegistration (Registration)</span></span>  <br/> |<span data-ttu-id="1f563-141">ユーザーが Skype for Business にサインインできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f563-141">Confirms that users are able sign in to Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="1f563-142">Test-CsPstnPeerToPeerCall (PSTN)</span><span class="sxs-lookup"><span data-stu-id="1f563-142">Test-CsPstnPeerToPeerCall (PSTN)</span></span>  <br/> |<span data-ttu-id="1f563-143">ユーザーが企業の外部のユーザー (PSTN 番号) と通話できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f563-143">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span>  <br/> |
|<span data-ttu-id="1f563-144">Test-CsASConference (ASConference)</span><span class="sxs-lookup"><span data-stu-id="1f563-144">Test-CsASConference (ASConference)</span></span>  <br/> |<span data-ttu-id="1f563-145">ユーザーがアプリケーション共有電話会議の作成と参加を行うことができることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f563-145">Confirms that users are able to create and participate in an application sharing conference.</span></span>  <br/> |
|<span data-ttu-id="1f563-146">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span><span class="sxs-lookup"><span data-stu-id="1f563-146">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span>  <br/> |<span data-ttu-id="1f563-147">音声ビデオ エッジ サーバーがピアツーピア通話と会議通話を行うための接続を受け入れることができることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f563-147">Confirms that the Audio Video Edge servers are able to accept connections for peer-to- peer calls and conference calls.</span></span>  <br/> |
|<span data-ttu-id="1f563-148">Test-CsDataConference (DataConference)</span><span class="sxs-lookup"><span data-stu-id="1f563-148">Test-CsDataConference (DataConference)</span></span>  <br/> |<span data-ttu-id="1f563-149">ユーザーが、データ グループ作業電話会議 (ホワイトボードや投票などのアクティビティが含まれるオンライン会議) に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f563-149">Confirms that users can participate in a data collaboration conference (an online meeting that includes activities such as whiteboards and polls).</span></span>  <br/> |
|<span data-ttu-id="1f563-150">Test-CsDialinConferencing (DialinConferencing)</span><span class="sxs-lookup"><span data-stu-id="1f563-150">Test-CsDialinConferencing (DialinConferencing)</span></span>  <br/> |<span data-ttu-id="1f563-151">ユーザーが電話番号をダイヤルして電話会議に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f563-151">Confirms that users are able to dial phone numbers to join conferences.</span></span>  <br/> |
|<span data-ttu-id="1f563-152">Test-CsDialinConferencing (DialinConferencing)</span><span class="sxs-lookup"><span data-stu-id="1f563-152">Test-CsDialinConferencing (DialinConferencing)</span></span>  <br/> |<span data-ttu-id="1f563-153">ユーザーが電話番号をダイヤルして電話会議に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f563-153">Confirms that users are able to dial phone numbers to join conferences.</span></span>  <br/> |
|<span data-ttu-id="1f563-154">Test-CsExumConnectivity (ExumConnectivity)</span><span class="sxs-lookup"><span data-stu-id="1f563-154">Test-CsExumConnectivity (ExumConnectivity)</span></span>  <br/> |<span data-ttu-id="1f563-155">ユーザーが Exchange ユニファイドメッセージング (UM) に接続できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f563-155">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span>  <br/> |
|<span data-ttu-id="1f563-156">テスト-CsGroupIM-TestJoinLauncher (Joinランチャー)</span><span class="sxs-lookup"><span data-stu-id="1f563-156">Test-CsGroupIM -TestJoinLauncher (JoinLauncher)</span></span>  <br/> |<span data-ttu-id="1f563-157">ユーザーがミーティングを作成でき、予定されたミーティングに Web アドレス リンクにより参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f563-157">Confirms that users are able to create and join scheduled meetings (by a web address link).</span></span>  <br/> |
|<span data-ttu-id="1f563-158">Test-CsMCXP2PIM (MCXP2PIM)</span><span class="sxs-lookup"><span data-stu-id="1f563-158">Test-CsMCXP2PIM (MCXP2PIM)</span></span>  <br/> |<span data-ttu-id="1f563-159">モバイル デバイス ユーザーがインスタント メッセージの登録と送信を実行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f563-159">Confirms that mobile device users are able to register and send instant messages.</span></span>  <br/> |
|<span data-ttu-id="1f563-160">Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)</span><span class="sxs-lookup"><span data-stu-id="1f563-160">Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)</span></span>  <br/> |<span data-ttu-id="1f563-161">ビデオ相互運用機能サーバーが起動していて、ビデオ SIP トランク経由の着信接続を処理できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f563-161">Confirms that Video Interop Server is up and can handle incoming connections over a video SIP trunk.</span></span>  <br/> <span data-ttu-id="1f563-162">**注:** 従来のモバイルクライアントに対する MCX のサポートは、Skype for Business Server 2019 では利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="1f563-162">**Note:** MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> |
|<span data-ttu-id="1f563-163">Test-CsPersistentChatMessage (PersistentChatMessage)</span><span class="sxs-lookup"><span data-stu-id="1f563-163">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span>  <br/> |<span data-ttu-id="1f563-164">ユーザーが常設チャット サービスを使用してメッセージを交換できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f563-164">Confirms that users can exchange messages by using the Persistent Chat service.</span></span>  <br/> |
|<span data-ttu-id="1f563-165">Test-CsUcwaConference (UcwaConference)</span><span class="sxs-lookup"><span data-stu-id="1f563-165">Test-CsUcwaConference (UcwaConference)</span></span>  <br/> |<span data-ttu-id="1f563-166">ユーザーが Web を介して電話会議に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f563-166">Confirms that users can join conferences via the web.</span></span>  <br/> |
|<span data-ttu-id="1f563-167">Test-CsUnifiedContactStore (UnifiedContactStore)</span><span class="sxs-lookup"><span data-stu-id="1f563-167">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span>  <br/> |<span data-ttu-id="1f563-168">統合連絡先ストアを通じてユーザーの連絡先にアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f563-168">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="1f563-169">統合連絡先ストアでは、Skype for Business Server 2015、Outlook メッセージングおよびコラボレーションクライアント、または Outlook Web Access を使用してアクセスできる単一の連絡先セットを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="1f563-169">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Skype for Business Server 2015, Outlook messaging and collaboration client, and/or Outlook Web Access.</span></span>  <br/> |
|<span data-ttu-id="1f563-170">Test-CsXmppIM (XmppIM)</span><span class="sxs-lookup"><span data-stu-id="1f563-170">Test-CsXmppIM (XmppIM)</span></span>  <br/> |<span data-ttu-id="1f563-171">インスタント メッセージを Extensible Messaging and Presence Protocol (XMPP) ゲートウェイ経由で送信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f563-171">Confirms that an instant message can be sent across the Extensible Messaging and Presence Protocol (XMPP) gateway.</span></span>  <br/> <span data-ttu-id="1f563-172">XMPP ゲートウェイとプロキシは、Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="1f563-172">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span>  |

<span data-ttu-id="1f563-173">System Center Operations Manager を使用するためにウォッチャーノードをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1f563-173">You do not need to install watcher nodes to use System Center Operations Manager.</span></span> <span data-ttu-id="1f563-174">これらのノードをインストールしていない場合でも、問題が発生するたびに Skype for Business Server の2015コンポーネントからリアルタイムの通知を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="1f563-174">If you do not install these nodes, you can still get real-time alerts from Skype for Business Server 2015 components whenever an issue occurs.</span></span> <span data-ttu-id="1f563-175">(コンポーネントとユーザー管理パックはウォッチャーノードを使用しません)。ただし、アクティブな監視管理パックを使用してエンドツーエンドのシナリオを監視する場合は、監視ノードが必要です。</span><span class="sxs-lookup"><span data-stu-id="1f563-175">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1f563-176">管理者は、Operations Manager の使用やインストールを行わなくても、代理トランザクションを手動で実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="1f563-176">Administrators can also run synthetic transactions manually, without using or installing Operations Manager.</span></span> <span data-ttu-id="1f563-177">統合トランザクションでは、Skype for Business Server の展開のサイズに応じて、大量のコンピューターメモリとプロセッサ時間を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="1f563-177">Depending on the size of your Skype for Business Server deployment, synthetic transactions can use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="1f563-178">このため、監視ノードとして専用のコンピューターを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1f563-178">Because of this, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="1f563-179">たとえば、Skype for Business Server フロントエンドサーバーを監視ノードとして機能するように構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="1f563-179">For example, you should not configure a Skype for Business Server Front End Server to act as a watcher node.</span></span> <span data-ttu-id="1f563-180">ウォッチャーノードは、Skype for Business Server トポロジの他のコンピューターと同じ基本的なハードウェア要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f563-180">Watcher nodes should meet the same basic hardware requirements as any other computer in your Skype for Business Server topology.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1f563-181">Lync server 2013 と Skype for Business Server 2015 のコアシステムファイルを同じコンピューターにインストールできないため、従来の Lync Server 2013 ウォッチャーノードは、Skype for Business 2015 Server の [ウォッチャー] ノードと同じコンピューター上に併置できません。</span><span class="sxs-lookup"><span data-stu-id="1f563-181">A legacy Lync Server 2013 watcher node cannot be collocated on the same machine as a Skype for Business Server 2015 watcher node because the core system files for Lync Server 2013 and Skype for Business Server 2015 cannot be installed on the same computer.</span></span> <span data-ttu-id="1f563-182">ただし、Skype for Business Server 2015 監視ノードでは、Skype for Business Server 2015 と Lync Server 2013 を同時に監視できます。</span><span class="sxs-lookup"><span data-stu-id="1f563-182">However, Skype for Business Server 2015 watcher nodes can simultaneously monitor Skype for Business Server 2015 and Lync Server 2013.</span></span> <span data-ttu-id="1f563-183">既定の代理トランザクションは、両方の製品バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1f563-183">Default synthetic transactions are supported for both product versions.</span></span> 
  
<span data-ttu-id="1f563-184">Lync Server 2013 ウォッチャーノードは、確認のために企業内外に展開することができます。</span><span class="sxs-lookup"><span data-stu-id="1f563-184">Lync Server 2013 watcher nodes may be deployed inside or outside an enterprise to help verify:</span></span>
  
- <span data-ttu-id="1f563-185">社内ユーザー用プールへの接続。</span><span class="sxs-lookup"><span data-stu-id="1f563-185">Connectivity to pools for users inside the enterprise.</span></span>
    
- <span data-ttu-id="1f563-186">社外で働くリモート ユーザー用の境界ネットワーク経由の接続。</span><span class="sxs-lookup"><span data-stu-id="1f563-186">Connectivity through perimeter networks for remote users working outside the enterprise.</span></span>
    
- <span data-ttu-id="1f563-187">ブランチ オフィス アプライアンスへの接続。</span><span class="sxs-lookup"><span data-stu-id="1f563-187">Connectivity to branch office appliances.</span></span>
    
- <span data-ttu-id="1f563-188">企業内および境界ネットワーク経由での Lync Server 2013 への接続。</span><span class="sxs-lookup"><span data-stu-id="1f563-188">Connectivity to Lync Server 2013 inside the enterprise and through perimeter networks.</span></span>
    
<span data-ttu-id="1f563-p110">管理を容易にするため、社内および社外用の異なる認証オプションがあります。詳細については、「[Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f563-p110">To help simplify administration, different authentication options are available for inside and outside of the enterprise. For details, see [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).</span></span>
  
<span data-ttu-id="1f563-191">監視ノードとして動作するようにコンピューターを構成するには、まず次の前提条件をすべて満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f563-191">To configure a computer to act as a watcher node, you must first complete the following prerequisites:</span></span> 
  
- <span data-ttu-id="1f563-192">System Center Operations Manager をインストールして、Skype for Business Server 2015 管理パックをインポートします。</span><span class="sxs-lookup"><span data-stu-id="1f563-192">Install System Center Operations Manager and import the Skype for Business Server 2015 management packs.</span></span> <span data-ttu-id="1f563-193">また、ウォッチャーノードコンピューターが Skype for Business Server 2015 をインストールするための前提条件をすべて満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f563-193">You must also first verify that the watcher node computer meets all prerequisites for installing Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="1f563-194">監視ノード コンピューターに以下のアイテムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="1f563-194">Install the following items on the watcher node computer:</span></span>
    
  - <span data-ttu-id="1f563-195">.NET Framework 4.5 の完全バージョン</span><span class="sxs-lookup"><span data-stu-id="1f563-195">The full version of .NET Framework 4.5</span></span>
    
  - <span data-ttu-id="1f563-196">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="1f563-196">Windows Identity Foundation</span></span>
    
  - <span data-ttu-id="1f563-197">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="1f563-197">Windows PowerShell 3.0</span></span>
    
<span data-ttu-id="1f563-198">これらの前提条件が満たされた後、次の操作を実行して監視ノードを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1f563-198">After the prerequisites are met, you can configure the watcher node by following these steps:</span></span>
  
1. <span data-ttu-id="1f563-199">ウォッチャーノードコンピューターに Skype for Business Server 2015 コアファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="1f563-199">Install the Skype for Business Server 2015 core files on the watcher node computer.</span></span>
    
2. <span data-ttu-id="1f563-200">Watcher ノードコンピューターに System Center Operations Manager エージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="1f563-200">Install System Center Operations Manager agent on the watcher node computer.</span></span>
    
3. <span data-ttu-id="1f563-201">Watchernode.msi 実行可能ファイルの実行。</span><span class="sxs-lookup"><span data-stu-id="1f563-201">Run the Watchernode.msi executable file.</span></span>
    
4. <span data-ttu-id="1f563-202">**CsWatcherNodeConfiguration** コマンドレットによる監視ノードで使用されるテスト ユーザー アカウントの構成。</span><span class="sxs-lookup"><span data-stu-id="1f563-202">Use the **New-CsWatcherNodeConfiguration** cmdlet to configure test user accounts to be employed by the watcher node.</span></span>
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a><span data-ttu-id="1f563-203">Skype for Business Server 2015 コア ファイルおよび RTCLocal データベースのインストール</span><span class="sxs-lookup"><span data-stu-id="1f563-203">Install the Skype for Business Server 2015 Core Files and the RTCLocal Database</span></span>

<span data-ttu-id="1f563-204">Skype for Business Server 2015 のコアファイルをコンピューターにインストールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1f563-204">To install the Skype for Business Server 2015 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="1f563-205">RTCLocal データベースは、コア ファイルをインストールするときに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="1f563-205">The RTCLocal database will automatically be installed when you install the core files.</span></span> <span data-ttu-id="1f563-206">監視ノードに SQL Server をインストールする必要はないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1f563-206">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="1f563-207">SQL Server Express が自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="1f563-207">SQL Server Express will be automatically installed.</span></span>
  
<span data-ttu-id="1f563-208">Skype for Business Server 2015 コアファイルと RTCLocal データベースをインストールするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1f563-208">To install the Skype for Business Server 2015 core files and the RTCLocal database:</span></span>
  
1. <span data-ttu-id="1f563-209">監視ノード コンピューターで、[スタート] ボタン、[すべてのプログラム]、[アクセサリ] の順にクリックし、[コマンド プロンプト] を右クリックし、[管理者として実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f563-209">On the watcher node computer, click Start, click All Programs, click Accessories, right-click Command Prompt, and then click Run as administrator.</span></span>
    
2. <span data-ttu-id="1f563-210">コンソール ウィンドウで、次のコマンドを入力して Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1f563-210">In the console window, type the following command and press ENTER.</span></span> <span data-ttu-id="1f563-211">Skype for Business Server セットアップファイルへの適切なパスを入力してください: D:\Setup.exe/BootstrapLocalMgmtTo コア Skype for Business Server コンポーネントが正常にインストールされたことを確認するには、[**スタート**] をクリックし、[**すべてのプログラム**] をクリックし、[skype for business server **2015**] をクリックして、[ **skype for business server 管理シェル**] をクリックします</span><span class="sxs-lookup"><span data-stu-id="1f563-211">Be sure to enter the appropriate path to your Skype for Business Server setup files: D:\Setup.exe /BootstrapLocalMgmtTo verify that the core Skype for Business Server components are successfully installed, click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server Management Shell**.</span></span> <span data-ttu-id="1f563-212">Skype for Business Server 管理シェルで、次の Windows PowerShell コマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1f563-212">In the Skype for Business Server Management Shell, type the following Windows PowerShell command and press ENTER:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> <span data-ttu-id="1f563-213">最初にこのコマンドを実行したときは、まだ監視ノード コンピューターを構成していないので何もデータが表示されません。</span><span class="sxs-lookup"><span data-stu-id="1f563-213">The first time you run this command, no data will be returned because you have not yet configured any watcher node computers.</span></span> <span data-ttu-id="1f563-214">このコマンドを実行してもエラーが返されない場合は、Skype for Business Server のセットアップが正常に完了したと見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="1f563-214">If the command runs without returning an error, you can assume that the Skype for Business Server setup completed successfully.</span></span> 
  
<span data-ttu-id="1f563-215">監視ノード コンピューターが境界ネットワーク内にある場合は、次のコマンドを実行して Skype for Business Server 2015 のインストールを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1f563-215">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Skype for Business Server 2015:</span></span>
  
<span data-ttu-id="1f563-216">CsPinPolicyYou は、組織で使用するように構成されている PIN ポリシーの数に応じて、次のような情報を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1f563-216">Get-CsPinPolicyYou will receive information similar to this, depending on the number of PIN policies configured for use in your organization:</span></span>
  
<span data-ttu-id="1f563-217">Identity: グローバル</span><span class="sxs-lookup"><span data-stu-id="1f563-217">Identity : Global</span></span>
  
<span data-ttu-id="1f563-218">説明</span><span class="sxs-lookup"><span data-stu-id="1f563-218">Description :</span></span>
  
<span data-ttu-id="1f563-219">MinPasswordLength: 5</span><span class="sxs-lookup"><span data-stu-id="1f563-219">MinPasswordLength : 5</span></span>
  
<span data-ttu-id="1f563-220">Pinhistory カウント: 0</span><span class="sxs-lookup"><span data-stu-id="1f563-220">PINHistoryCount : 0</span></span>
  
<span data-ttu-id="1f563-221">AllowCommonPatterns: False</span><span class="sxs-lookup"><span data-stu-id="1f563-221">AllowCommonPatterns : False</span></span>
  
<span data-ttu-id="1f563-222">PINLifetime: 0</span><span class="sxs-lookup"><span data-stu-id="1f563-222">PINLifetime : 0</span></span>
  
<span data-ttu-id="1f563-223">MaximumLogonAttempts :</span><span class="sxs-lookup"><span data-stu-id="1f563-223">MaximumLogonAttempts :</span></span>
  
<span data-ttu-id="1f563-224">PIN ポリシーに関する情報が表示された場合は、コア コンポーネントが正常にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="1f563-224">If you see information about your PIN policies, the core components have been successfully installed.</span></span>
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a><span data-ttu-id="1f563-225">監視ノードの Operation Manager エージェント ファイルのインストール</span><span class="sxs-lookup"><span data-stu-id="1f563-225">Install the Operation Manager Agent Files on a Watcher Node</span></span>

<span data-ttu-id="1f563-226">Skype for business Server のセットアップと同じように、レポートコンポーネントの通知を設定するには、Skype for Business Server 2015 ウォッチャーノードで System Center Operations Manager エージェントファイルをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f563-226">Similar to Skype for Business Server setup for reporting component alerts, a Skype for Business Server 2015 watcher node requires System Center Operations Manager agent files to be installed.</span></span> <span data-ttu-id="1f563-227">これにより、代理トランザクションが実行され、警告が System Center Operations Manager ルート管理サーバーに報告されます。</span><span class="sxs-lookup"><span data-stu-id="1f563-227">This enables the synthetic transactions to be run and alerts to be reported to the System Center Operations Manager Root Management Server.</span></span>
  
<span data-ttu-id="1f563-228">エージェントファイルをインストールするには、「監視対象の[Skype For Business サーバーコンピューターを構成](configure-computers-to-monitor.md)する」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="1f563-228">To install the agent files, follow the procedures listed in [Configure the Skype for Business Server computers that will be monitored](configure-computers-to-monitor.md).</span></span>
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a><span data-ttu-id="1f563-229">代理トランザクションを実行する監視ノードの構成</span><span class="sxs-lookup"><span data-stu-id="1f563-229">Configure a Watcher Node to Run Synthetic Transactions</span></span>
<span data-ttu-id="1f563-230"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="1f563-230"></span></span>

<span data-ttu-id="1f563-231">System Center Operations Manager エージェントファイルがインストールされたら、ウォッチャーノード自体を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f563-231">After the System Center Operations Manager agent files have been installed, you must configure the watcher node itself.</span></span> <span data-ttu-id="1f563-232">監視ノードを構成する手順は監視ノードを境界ネットワークの内側に置くか、外側に置くかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1f563-232">The steps you take to do this will vary, depending on whether your watcher node computer is inside your perimeter network or outside your perimeter network.</span></span> 
  
<span data-ttu-id="1f563-233">監視ノードの構成時には、そのノードが使用する認証方法の種類も選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f563-233">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="1f563-234">Skype for Business Server 2015 では、2つの認証方法のいずれかを選択できます。信頼されたサーバーまたは資格情報認証。</span><span class="sxs-lookup"><span data-stu-id="1f563-234">Skype for Business Server 2015 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="1f563-235">この 2 つの方法の主な違いを次の表にまとめます。</span><span class="sxs-lookup"><span data-stu-id="1f563-235">The following table shows the differences between these two methods:</span></span>
  
||<span data-ttu-id="1f563-236">**説明**</span><span class="sxs-lookup"><span data-stu-id="1f563-236">**Description**</span></span>|<span data-ttu-id="1f563-237">**サポートされる場所**</span><span class="sxs-lookup"><span data-stu-id="1f563-237">**Locations supported**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1f563-238">TrustedServer</span><span class="sxs-lookup"><span data-stu-id="1f563-238">TrustedServer</span></span>  <br/> |<span data-ttu-id="1f563-239">内部サーバーを偽装する証明書を使用し、認証チャレンジをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="1f563-239">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span>  <br/> <span data-ttu-id="1f563-240">各監視ノードで多数のユーザー パスワードではなく、1 つの証明書を管理したいと考える管理者にとって便利です。</span><span class="sxs-lookup"><span data-stu-id="1f563-240">Useful for administrators who prefer to manage a single certificate, instead of many user passwords on each watcher node.</span></span>  <br/> |<span data-ttu-id="1f563-241">エンタープライズの内側。</span><span class="sxs-lookup"><span data-stu-id="1f563-241">Inside the enterprise.</span></span>  <br/> <span data-ttu-id="1f563-242">この方法では、監視ノードが監視対象のプールと同じドメイン内に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f563-242">With this method, the watcher node must be in the same domain as the pools being monitored.</span></span> <span data-ttu-id="1f563-243">監視ノードとプールが別のドメインに存在する場合は、この方法ではなく、資格情報認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="1f563-243">If the watcher node and the pools are in different domains, use Credential Authentication instead.</span></span>  <br/> |
|<span data-ttu-id="1f563-244">Negotiate</span><span class="sxs-lookup"><span data-stu-id="1f563-244">Negotiate</span></span>  <br/> |<span data-ttu-id="1f563-245">ユーザー名とパスワードを各監視ノードの Windows 資格情報マネージャーに保管します。</span><span class="sxs-lookup"><span data-stu-id="1f563-245">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span>  <br/> <span data-ttu-id="1f563-246">このモードは、パスワード管理の手間を必要としますが、エンタープライズの外側に位置する監視ノードの場合には唯一の選択肢となります。</span><span class="sxs-lookup"><span data-stu-id="1f563-246">This mode requires more password management, but is the only option for watcher nodes outside the enterprise.</span></span> <span data-ttu-id="1f563-247">このような外側に位置する監視ノードを認証の際に信頼済みのエンドポイントとして扱うことはできません。</span><span class="sxs-lookup"><span data-stu-id="1f563-247">These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span>  <br/> |<span data-ttu-id="1f563-248">エンタープライズの外側。</span><span class="sxs-lookup"><span data-stu-id="1f563-248">Outside the enterprise.</span></span>  <br/> <span data-ttu-id="1f563-249">エンタープライズの内側。</span><span class="sxs-lookup"><span data-stu-id="1f563-249">Inside the enterprise.</span></span>  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a><span data-ttu-id="1f563-250">信頼されたサーバー認証を使用する監視ノードの構成</span><span class="sxs-lookup"><span data-stu-id="1f563-250">Configure a Watcher Node to Use Trusted Server Authentication</span></span>
<span data-ttu-id="1f563-251"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="1f563-251"></span></span>

<span data-ttu-id="1f563-252">監視ノード コンピューターが境界ネットワーク内にある場合、信頼済みサーバー認証によって 1 つの証明書を管理するだけでよくなるので、管理負荷が大幅に軽減されます。膨大な数のユーザー アカウント パスワードを管理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1f563-252">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration tasks by maintaining a single certificate, rather than using numerous user account passwords.</span></span>
  
<span data-ttu-id="1f563-253">信頼済みサーバー認証を構成するには、まず監視ノード コンピューターをホストする信頼済みアプリケーション プールを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f563-253">To configure Trusted Server authentication, you must first create a trusted application pool to host the watcher node computer.</span></span> <span data-ttu-id="1f563-254">信頼されたアプリケーションプールを作成したら、そのウォッチャーノードの代理トランザクションを構成して、信頼できるアプリケーションとして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f563-254">After you've created the trusted application pool, you must then configure synthetic transactions on that watcher node to run as trusted applications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1f563-255">信頼されたアプリケーションとは、Skype for Business Server 2015 の一部として実行される信頼された状態を提供するアプリケーションですが、製品の組み込みの一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="1f563-255">A trusted application is an application that is given trusted status to run as part of Skype for Business Server 2015, but is not a built-in part of the product.</span></span> <span data-ttu-id="1f563-256">Trusted status means that the application will not be challenged for authentication each time it runs.</span><span class="sxs-lookup"><span data-stu-id="1f563-256">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>
  
<span data-ttu-id="1f563-257">信頼されたアプリケーションプールを作成するには、Skype for Business Server 管理シェルを開き、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1f563-257">To create a trusted application pool, open the Skype for Business Server Management Shell and run a command similar to this:</span></span>
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> <span data-ttu-id="1f563-258">上記のコマンドのパラメーターの詳細については、「Skype for Business Server 管理シェルのプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1f563-258">For details about the parameters in the preceding command, type the following from the Skype for Business Server Management Shell prompt:</span></span> 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

<span data-ttu-id="1f563-259">信頼済みアプリケーション プールの作成後、これを行うには、**New-CsTrustedApplication** コマンドレットと次のようなコマンドを使用して、代理トランザクションが信頼済みアプリケーションとして実行されるように監視ノード コンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="1f563-259">After creating the trusted application pool, you can then configure the watcher node computer to run synthetic transactions as a trusted application by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

<span data-ttu-id="1f563-260">上記のコマンドが完了し、信頼済みアプリケーションが作成されたら、**Enable-CsTopology** コマンドレットを実行して変更を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1f563-260">When this command completes and the trusted application is created, you must then run the **Enable-CsTopology** cmdlet to make sure that the changes take effect:</span></span>
  
```PowerShell
Enable-CsTopology
```

<span data-ttu-id="1f563-261">Enable-CsTopology を実行後、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="1f563-261">After running Enable-CsTopology, restart the computer.</span></span>
  
<span data-ttu-id="1f563-262">新しい信頼済みアプリケーションが作成されたことを確認するには、Skype for Business Server 管理シェルプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1f563-262">To verify that the new trusted application has been created, type the following at the Skype for Business Server Management Shell prompt:</span></span>
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="1f563-263">監視ノードで既定の証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="1f563-263">Configure a Default Certificate on the Watcher Node</span></span>
<span data-ttu-id="1f563-264"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="1f563-264"></span></span>

<span data-ttu-id="1f563-265">TrustedServer 認証を使用する各ウォッチャーノードには、Skype for Business Server Deployment wizard を使って既定の証明書を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f563-265">Each watcher node that uses TrustedServer authentication must have a Default certificate assigned by using the Skype for Business Server Deployment wizard.</span></span> 
  
<span data-ttu-id="1f563-266">既定の証明書を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="1f563-266">To assign a Default certificate:</span></span>
  
1. <span data-ttu-id="1f563-267">[スタート] をクリックし、[すべてのプログラム] をクリックし、[Skype for Business server 2015] をクリックして、[Skype for Business Server Deployment ウィザード] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f563-267">Click Start, click All Programs, click Skype for Business Server 2015, and then click Skype for Business Server Deployment Wizard.</span></span> 
    
2. <span data-ttu-id="1f563-268">Skype for Business Server の展開ウィザードで、[Skype for Business Server システムのインストールまたは更新] をクリックし、[タイトルの要求]、[インストール]、または [証明書の割り当て] の [実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f563-268">In the Skype for Business Server Deployment Wizard, click Install or Update Skype for Business Server System, and then click Run under the heading Request, Install, or Assign Certificate.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="1f563-269">[実行] ボタンをが無効になっている場合は、[ローカル構成ストアのインストール] で [実行] を最初にクリックしなければならないことがあります。</span><span class="sxs-lookup"><span data-stu-id="1f563-269">If the Run button is disabled, you may need to first click Run under Install Local Configuration Store.</span></span> 
  
<span data-ttu-id="1f563-270">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1f563-270">Do one of the following:</span></span>
  
- <span data-ttu-id="1f563-p122">既定の証明書として使用できる証明書が既にある場合は、証明書ウィザードで [既定] をクリックし、[割り当て] をクリックします。証明書の割り当てウィザードの手順に従って、証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1f563-p122">If you already have a certificate that can be used as the Default certificate, click Default in the Certificate wizard, and then click Assign. Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
- <span data-ttu-id="1f563-p123">既定の証明書として使用する証明書を要求する必要がある場合は、[要求] をクリックし、証明書要求ウィザードの手順に従ってその証明書を要求します。Web サーバー証明書の既定値を使用すると、既定の証明書として割り当てることができる証明書を取得できます。</span><span class="sxs-lookup"><span data-stu-id="1f563-p123">If you need to request a certificate for use the Default certificate, click Request, and then follow the steps in the Certificate Request wizard to request that certificate. If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>
    
## <a name="install-and-configure-a-watcher-node"></a><span data-ttu-id="1f563-275">監視ノードをインストールおよび構成する</span><span class="sxs-lookup"><span data-stu-id="1f563-275">Install and Configure a Watcher Node</span></span>
<span data-ttu-id="1f563-276"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="1f563-276"></span></span>

<span data-ttu-id="1f563-277">ウォッチャーノードのコンピューターを再起動して証明書を構成したら、Watchernode ファイルを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f563-277">After you have restarted the watcher node computer and configured a certificate, you must run the file Watchernode.msi.</span></span> <span data-ttu-id="1f563-278">(Operations Manager エージェントファイルと Skype for Business Server 2015 コアコンポーネントの両方がインストールされているコンピューターであれば、Watchernode を実行する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="1f563-278">(You must run Watchernode.msi on any computer where both the Operations Manager agent files and the Skype for Business Server 2015 core components are installed.)</span></span> 
  
<span data-ttu-id="1f563-279">監視ノードをインストールおよび構成するには</span><span class="sxs-lookup"><span data-stu-id="1f563-279">To install and configure a watcher node:</span></span>
  
1. <span data-ttu-id="1f563-280">[スタート] をクリックし、[すべてのプログラム]、[Skype for Business Server 2015]、[Skype for business Server 管理シェル] の順にクリックして、Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1f563-280">Open the Skype for Business Server Management Shell by clicking Start, clicking All Programs, clicking Skype for Business Server 2015, and then clicking Skype for Business Server Management Shell.</span></span> 
    
2. <span data-ttu-id="1f563-281">管理シェルで、次のコマンドを入力して、Enter キーを押します (Watchernode.msi のコピーへの実際のパスを指定)。</span><span class="sxs-lookup"><span data-stu-id="1f563-281">In the Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> <span data-ttu-id="1f563-p125">コマンド ウィンドウから Watchernode.msi を実行することもできます。コマンド ウィンドウを開くには、[スタート] をクリックし、[コマンド プロンプト] を右クリックして、[管理者として実行] をクリックします。コマンド ウィンドウが開いたら、上記の手順 2 と同じコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="1f563-p125">You can also run Watchernode.msi n from a command window. To open a command window, click Start, right-click Command Prompt, and then click Run as administrator. When the command window opens, type the same command shown in step 2, above.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1f563-p126">上記のコマンドの名前/値ペア Authentication=TrustedServer は大文字と小文字が区別されるので、ここで示すとおりに正確に入力する必要があります。たとえば次のコマンドは、大文字と小文字が正しく使用されていないので失敗します。</span><span class="sxs-lookup"><span data-stu-id="1f563-p126">In the preceding command, the name/value pair Authentication=TrustedServer is case-sensitive. It must be typed exactly as shown. For example, this command will fail because it does not use the correct letter casing:</span></span> 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

<span data-ttu-id="1f563-p127">TrustedServer モードは、境界ネットワーク内のコンピューターでのみ使用できます。監視ノードが TrustedServer モードで実行されている場合、管理者はコンピューター上のテスト ユーザー パスワードを管理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1f563-p127">TrustedServer mode can be used only with computers that lie inside the perimeter network. When a watcher node runs in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a><span data-ttu-id="1f563-290">ネゴシエートを使用する監視ノードの構成</span><span class="sxs-lookup"><span data-stu-id="1f563-290">Configure a Watcher Node to Use Negotiate</span></span>
<span data-ttu-id="1f563-291"><a name="enable_synthetic_trans"> </a></span><span class="sxs-lookup"><span data-stu-id="1f563-291"></span></span>

<span data-ttu-id="1f563-p128">監視ノード コンピューターが境界ネットワークの外側にある場合は、代理トランザクションを実行するように監視ノードを構成するために、少し異なる手順に従う必要があります。特に、信頼されたアプリケーション プールや信頼されたアプリケーションは作成しないでください。つまり、次に示す個別の 2 つのタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f563-p128">If your watcher node computer lies outside the perimeter network then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions: in particular, you should not create a trusted application pool or a trusted application. That means that you will need to complete the next two tasks.</span></span>
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="1f563-294">RTC Local Read-Only Administrators グループのメンバーシップの更新</span><span class="sxs-lookup"><span data-stu-id="1f563-294">Update Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="1f563-295">監視ノードが境界ネットワークの外側にある場合は、Network Service アカウントを監視ノード コンピューターの RTC Local Read-only Administrators グループに追加する必要があります。そのためには、監視ノードで以下の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="1f563-295">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer by completing the following procedure on the watcher node:</span></span>
  
1. <span data-ttu-id="1f563-296">[スタート] メニューの [コンピューター] を右クリックし、[管理] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f563-296">Click Start, right-click Computer, and then click Manage.</span></span>
    
2. <span data-ttu-id="1f563-297">サーバー マネージャーで、[構成]、[ローカル ユーザーとグループ] の順に展開し、[グループ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f563-297">In Server Manager, expand Configuration, expand Local Users and Groups, and then click Groups.</span></span>
    
3. <span data-ttu-id="1f563-298">[グループ] ウィンドウで、[RTC Local Read-only Administrators] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f563-298">In the Groups pane, double-click RTC Local Read-only Administrators.</span></span>
    
4. <span data-ttu-id="1f563-299">[RTC Local Read-only Administrators のプロパティ] ダイアログ ボックスで、[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f563-299">In the RTC Local Read-only Administrators Properties dialog box, click Add.</span></span>
    
5. <span data-ttu-id="1f563-300">[ユーザー、コンピューター、サービス アカウント、またはグループの選択] ダイアログで、[場所] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f563-300">In the Select Users, Computers, Service Accounts, or Groups dialog box, click Locations.</span></span>
    
6. <span data-ttu-id="1f563-301">[場所] ダイアログ ボックスで、監視ノード コンピューターの名前を選択し、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f563-301">In the Locations dialog box, select the name of the watcher node computer, and then click OK.</span></span>
    
7. <span data-ttu-id="1f563-302">[選択するオブジェクト名を入力してください] ボックスに、「Network Service」と入力し、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f563-302">In the Enter object names to select box, type Network Service, and then click OK.</span></span>
    
8. <span data-ttu-id="1f563-303">[RTC Local Read-only Administrators のプロパティ] ダイアログ ボックスで、[OK] をクリックし、[サーバー マネージャー] を閉じます。</span><span class="sxs-lookup"><span data-stu-id="1f563-303">In the RTC Local Read-only Administrators Properties dialog box, click OK, and then close Server Manager.</span></span>
    
9. <span data-ttu-id="1f563-304">監視ノード コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="1f563-304">Restart the watcher node computer.</span></span>
    
### <a name="install-the-watcher-node-configuration-files"></a><span data-ttu-id="1f563-305">監視ノード構成ファイルのインストール</span><span class="sxs-lookup"><span data-stu-id="1f563-305">Install the Watcher Node Configuration Files</span></span>

<span data-ttu-id="1f563-306">次に、Watchernode.msi ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="1f563-306">Your next step is to run the file Watchernode.msi:</span></span> 
  
1. <span data-ttu-id="1f563-p129">Microsoft Skype for Business Server 2015 管理シェルを以下の手順で起動します。[スタート]、[すべてのプログラム]、[Microsoft Skype for Business Server 2015]、[Skype for Business Server 管理シェル] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f563-p129">Open the Microsoft Skype for Business Server 2015 Management Shell. Click Start, click All Programs, click Microsoft Skype for Business Server 2015, and then click Skype for Business Server Management Shell.</span></span> 
    
2. <span data-ttu-id="1f563-309">Skype for Business Server 管理シェルで、次のコマンドを入力して、Enter キーを押します (Watchernode.msi のコピーへの実際のパスを指定)。</span><span class="sxs-lookup"><span data-stu-id="1f563-309">In Skype for Business Server Management Shell, type the following command, and then press ENTER (be sure to specify the actual path to your copy of Watchernode.msi):</span></span>
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> <span data-ttu-id="1f563-p130">前述のように、Watchernode.msi はコマンド ウィンドウから実行することもできます。コマンド ウィンドウを開くには、[**スタート**] メニューをクリックし、[**コマンド プロンプト**] を右クリックして、[**管理者として実行**] をクリックします。コマンド ウィンドウが開いたら、上記の手順 2 と同じコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="1f563-p130">As mentioned previously, Watchernode.msi can also be run from a command window. To open a command window, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**. When the command window opens, type the same command shown in step 2, above.</span></span> 
  
<span data-ttu-id="1f563-p131">監視ノードを信頼されたアプリケーション プールとしてセットアップできない場合はいつでも、ネゴシエート モードが使用されます。このモードでは、管理者が監視ノードのテスト ユーザー パスワードを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f563-p131">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool. In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>
  

