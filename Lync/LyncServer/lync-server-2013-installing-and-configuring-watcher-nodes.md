---
title: 'Lync Server 2013: ウォッチャーノードのインストールと構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36d466cbffff1cf1e68eefe120215895e52e7c81
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="ad38f-102">Lync Server 2013 でのウォッチャーノードのインストールと構成</span><span class="sxs-lookup"><span data-stu-id="ad38f-102">Installing and configuring watcher nodes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad38f-103">_**最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="ad38f-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="ad38f-104">*ウォッチャーノード*は、定期的に Lync Server の代理トランザクションを実行するコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="ad38f-104">*Watcher nodes* are computers that periodically run Lync Server synthetic transactions.</span></span> <span data-ttu-id="ad38f-105">*代理トランザクション*は、Windows PowerShell コマンドレットであり、システムへのサインイン機能や、インスタントメッセージの交換機能など、主要なエンドユーザーシナリオが期待どおりに機能していることを確認するための Windows PowerShell コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="ad38f-105">*Synthetic transactions* are Windows PowerShell cmdlets that verify that key end user scenarios—such as the ability to sign in to the system, or the ability to exchange instant messages—are working as expected.</span></span> <span data-ttu-id="ad38f-106">Lync Server 2013 の場合、System Center Operations Manager は、次の表に示す代理トランザクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ad38f-106">For Lync Server 2013, System Center Operations Manager can run the synthetic transactions shown in the following table.</span></span> <span data-ttu-id="ad38f-107">テーブルには、次の3種類の代理トランザクションタイプが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad38f-107">There are three different synthetic transaction types shown in the table:</span></span>

  - <span data-ttu-id="ad38f-108">**既定値**。</span><span class="sxs-lookup"><span data-stu-id="ad38f-108">**Default**.</span></span> <span data-ttu-id="ad38f-109">これは、既定でウォッチャーノードが実行する代理トランザクションです。</span><span class="sxs-lookup"><span data-stu-id="ad38f-109">These are the synthetic transactions that a watcher node will run by default.</span></span> <span data-ttu-id="ad38f-110">新しいウォッチャーノードを作成するときに、ノードが実行する代理トランザクションを指定するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="ad38f-110">When you create a new watcher node, you have the option of specifying which synthetic transactions that node will run.</span></span> <span data-ttu-id="ad38f-111">(これは、 **CsWatcherNodeConfiguration**コマンドレットで使用されるテストパラメーターの目的です。)ウォッチャーノードが作成されたときに Tests パラメーターを使用しないと、既定のすべての合成トランザクションが自動的に実行され、既定以外の代理トランザクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="ad38f-111">(That's the purpose of the Tests parameter used by the **New-CsWatcherNodeConfiguration** cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="ad38f-112">つまり、たとえば、watcher ノードは、CsAddressBookService のテストを実行するように構成されていますが、テスト-CsExumConnectivity テストを実行するように構成されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="ad38f-112">That means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>

  - <span data-ttu-id="ad38f-113">**既定以外の値**。</span><span class="sxs-lookup"><span data-stu-id="ad38f-113">**Non-default**.</span></span> <span data-ttu-id="ad38f-114">名前が示すように、既定以外の代理トランザクションは、既定ではウォッチャーノードが実行されないテストです。</span><span class="sxs-lookup"><span data-stu-id="ad38f-114">As the name implies, Non-default synthetic transactions are tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="ad38f-115">ただし、ウォッチャーノードを有効にして、既定以外の代理トランザクションのいずれかを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="ad38f-115">However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="ad38f-116">これは、( **CsWatcherNodeConfiguration**コマンドレットを使用して) ウォッチャーノードを作成するとき、またはそれ以降の任意の時点で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ad38f-116">You can do this when you create the watcher node (by using the **New-CsWatcherNodeConfiguration** cmdlet), or at any time after that.</span></span> <span data-ttu-id="ad38f-117">既定以外の代理トランザクションの多くには、追加のセットアップ手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="ad38f-117">Many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="ad38f-118">詳細については、「 [Lync Server 2013 での代理トランザクション用の特別なセットアップ手順](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad38f-118">For details, see [Special setup instructions for synthetic transactions in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span></span>

  - <span data-ttu-id="ad38f-119">**拡張**します。</span><span class="sxs-lookup"><span data-stu-id="ad38f-119">**Extended**.</span></span> <span data-ttu-id="ad38f-120">拡張テストは、特別な種類の既定以外の代理トランザクションです。</span><span class="sxs-lookup"><span data-stu-id="ad38f-120">Extended tests are a special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="ad38f-121">他の代理トランザクションとは異なり、拡張テストは、1 回のパスで複数回実行できます。</span><span class="sxs-lookup"><span data-stu-id="ad38f-121">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="ad38f-122">これは、複数の公衆交換電話網 (PSTN) のプールのボイスルーティングなどの動作を確認するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ad38f-122">This can be useful when verifying behavior such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="ad38f-123">これは、1つの拡張テストの複数のインスタンスをウォッチャーノードに追加するだけで構成できます。</span><span class="sxs-lookup"><span data-stu-id="ad38f-123">This can be configured simply by adding multiple instances of an Extended test to a watcher node.</span></span>

<span data-ttu-id="ad38f-124">他の代理トランザクションをウォッチャーノードに追加するプロセスの詳細については、「 [Lync Server 2013 でウォッチャーノードを管理](lync-server-2013-managing-watcher-nodes.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad38f-124">For details about the process of adding other synthetic transactions to a watcher node, see [Managing watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span></span> <span data-ttu-id="ad38f-125">Lync Server 管理シェルを使って、ウォッチャーノードから合成トランザクションを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="ad38f-125">You can use the Lync Server Management Shell to remove synthetic transactions from a watcher node.</span></span>

<span data-ttu-id="ad38f-126">監視ノードで使用できる代理トランザクションは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ad38f-126">The synthetic transactions available to watcher nodes include the following:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad38f-127">コマンドレット名 (テスト名)</span><span class="sxs-lookup"><span data-stu-id="ad38f-127">Cmdlet Name (Test Name)</span></span></th>
<th><span data-ttu-id="ad38f-128">説明</span><span class="sxs-lookup"><span data-stu-id="ad38f-128">Description</span></span></th>
<th><span data-ttu-id="ad38f-129">代理トランザクションの種類</span><span class="sxs-lookup"><span data-stu-id="ad38f-129">Synthetic Transaction Type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad38f-130">Test-CsAddressBookService (ABS)</span><span class="sxs-lookup"><span data-stu-id="ad38f-130">Test-CsAddressBookService (ABS)</span></span></p></td>
<td><p><span data-ttu-id="ad38f-131">ユーザーが連絡先リストに含まれていないユーザーを検索できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad38f-131">Confirms that users are able to look up users that aren’t in their contact list.</span></span></p></td>
<td><p><span data-ttu-id="ad38f-132">既定</span><span class="sxs-lookup"><span data-stu-id="ad38f-132">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad38f-133">Test-CsAddressBookWebQuery (ABWQ)</span><span class="sxs-lookup"><span data-stu-id="ad38f-133">Test-CsAddressBookWebQuery (ABWQ)</span></span></p></td>
<td><p><span data-ttu-id="ad38f-134">ユーザーが、連絡先リストに含まれていないユーザーを HTTP 経由で検索できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad38f-134">Confirms that users are able to look up users that aren’t in their contact list via HTTP.</span></span></p></td>
<td><p><span data-ttu-id="ad38f-135">既定</span><span class="sxs-lookup"><span data-stu-id="ad38f-135">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad38f-136">テスト-CsIM (IM)</span><span class="sxs-lookup"><span data-stu-id="ad38f-136">Test-CsIM (IM)</span></span></p></td>
<td><p><span data-ttu-id="ad38f-137">ユーザーがピアツーピア インスタント メッセージを送信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad38f-137">Confirms that users are able to send peer-to-peer instant messages.</span></span></p></td>
<td><p><span data-ttu-id="ad38f-138">既定</span><span class="sxs-lookup"><span data-stu-id="ad38f-138">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad38f-139">Test-CsP2PAV (P2PAV)</span><span class="sxs-lookup"><span data-stu-id="ad38f-139">Test-CsP2PAV (P2PAV)</span></span></p></td>
<td><p><span data-ttu-id="ad38f-140">ユーザーがピアツーピア音声通話を開始できることを確認します (シグナリングのみ)。</span><span class="sxs-lookup"><span data-stu-id="ad38f-140">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span></p></td>
<td><p><span data-ttu-id="ad38f-141">既定</span><span class="sxs-lookup"><span data-stu-id="ad38f-141">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad38f-142">Test-CsPresence (Presence)</span><span class="sxs-lookup"><span data-stu-id="ad38f-142">Test-CsPresence (Presence)</span></span></p></td>
<td><p><span data-ttu-id="ad38f-143">ユーザーが他のユーザーのプレゼンスを表示できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad38f-143">Confirms that users are able to view other users’ presence.</span></span></p></td>
<td><p><span data-ttu-id="ad38f-144">既定</span><span class="sxs-lookup"><span data-stu-id="ad38f-144">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad38f-145">Test-CsRegistration (Registration)</span><span class="sxs-lookup"><span data-stu-id="ad38f-145">Test-CsRegistration (Registration)</span></span></p></td>
<td><p><span data-ttu-id="ad38f-146">ユーザーが Lync にサインインできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad38f-146">Confirms that users are able sign in to Lync.</span></span></p></td>
<td><p><span data-ttu-id="ad38f-147">既定</span><span class="sxs-lookup"><span data-stu-id="ad38f-147">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad38f-148">CsAudioConferencingProvider (ACP)</span><span class="sxs-lookup"><span data-stu-id="ad38f-148">Test-CsAudioConferencingProvider (ACP)</span></span></p></td>
<td><p><span data-ttu-id="ad38f-149">Lync Server 2013 のオンプレミスバージョンでは使用されませんでした</span><span class="sxs-lookup"><span data-stu-id="ad38f-149">Not used with the on-premises version of Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="ad38f-150">拡張。</span><span class="sxs-lookup"><span data-stu-id="ad38f-150">Extended</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad38f-151">Test-CsPstnPeerToPeerCall (PSTN)</span><span class="sxs-lookup"><span data-stu-id="ad38f-151">Test-CsPstnPeerToPeerCall (PSTN)</span></span></p></td>
<td><p><span data-ttu-id="ad38f-152">ユーザーが企業の外部のユーザー (PSTN 番号) と通話できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad38f-152">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span></p></td>
<td><p><span data-ttu-id="ad38f-153">既定以外の拡張</span><span class="sxs-lookup"><span data-stu-id="ad38f-153">Non-default, Extended</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad38f-154">Test-CsAVConference (AvConference)</span><span class="sxs-lookup"><span data-stu-id="ad38f-154">Test-CsAVConference (AvConference)</span></span></p></td>
<td><p><span data-ttu-id="ad38f-155">ユーザーが音声/ビデオ会議で作成と参加が可能なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad38f-155">Confirms that users are able to create and participate in an audio/video conference.</span></span></p></td>
<td><p><span data-ttu-id="ad38f-156">既定</span><span class="sxs-lookup"><span data-stu-id="ad38f-156">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad38f-157">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span><span class="sxs-lookup"><span data-stu-id="ad38f-157">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="ad38f-158">A/V Edge サーバーが、ピアツーピア通話と電話会議への接続を受け入れることができることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad38f-158">Confirms that the A/V Edge servers are able to accept connections for peer-to-peer calls and conference calls.</span></span></p></td>
<td><p><span data-ttu-id="ad38f-159">既定以外の場合</span><span class="sxs-lookup"><span data-stu-id="ad38f-159">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad38f-160">Test-CsDataConference (DataConference)</span><span class="sxs-lookup"><span data-stu-id="ad38f-160">Test-CsDataConference (DataConference)</span></span></p></td>
<td><p><span data-ttu-id="ad38f-161">ユーザーがデータコラボレーション会議 (ホワイトボードや投票などのアクティビティを含むオンライン会議) に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad38f-161">Confirms that users can participate in a data collaboration conference, an online meeting that includes activities such as whiteboards and polls.</span></span></p></td>
<td><p><span data-ttu-id="ad38f-162">既定以外の場合</span><span class="sxs-lookup"><span data-stu-id="ad38f-162">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad38f-163">Test-CsExumConnectivity (ExumConnectivity)</span><span class="sxs-lookup"><span data-stu-id="ad38f-163">Test-CsExumConnectivity (ExumConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="ad38f-164">ユーザーが Exchange ユニファイドメッセージング (UM) に接続できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad38f-164">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="ad38f-165">既定以外の場合</span><span class="sxs-lookup"><span data-stu-id="ad38f-165">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad38f-166">テスト-CsGroupIM (GroupIM)</span><span class="sxs-lookup"><span data-stu-id="ad38f-166">Test-CsGroupIM (GroupIM)</span></span></p></td>
<td><p><span data-ttu-id="ad38f-167">ユーザーが会議中にインスタント メッセージを送信でき、3 人以上のユーザーとインスタント メッセージでの会話に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad38f-167">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span></p></td>
<td><p><span data-ttu-id="ad38f-168">既定</span><span class="sxs-lookup"><span data-stu-id="ad38f-168">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad38f-169">Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</span><span class="sxs-lookup"><span data-stu-id="ad38f-169">Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</span></span></p></td>
<td><p><span data-ttu-id="ad38f-170">ユーザーが、web アドレスリンク経由でスケジュールされた会議を作成して参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad38f-170">Confirms that users are able to create and join scheduled meetings via a web address link.</span></span></p></td>
<td><p><span data-ttu-id="ad38f-171">既定以外の場合</span><span class="sxs-lookup"><span data-stu-id="ad38f-171">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad38f-172">Test-CsMCXP2PIM (MCXP2PIM)</span><span class="sxs-lookup"><span data-stu-id="ad38f-172">Test-CsMCXP2PIM (MCXP2PIM)</span></span></p></td>
<td><p><span data-ttu-id="ad38f-173">モバイル デバイス ユーザーがインスタント メッセージの登録と送信を実行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad38f-173">Confirms that mobile device users are able to register and send instant messages.</span></span></p></td>
<td><p><span data-ttu-id="ad38f-174">既定以外の場合</span><span class="sxs-lookup"><span data-stu-id="ad38f-174">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad38f-175">Test-CsPersistentChatMessage (PersistentChatMessage)</span><span class="sxs-lookup"><span data-stu-id="ad38f-175">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span></p></td>
<td><p><span data-ttu-id="ad38f-176">ユーザーが常設チャット サービスを使用してメッセージを交換できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad38f-176">Confirms that users can exchange messages by using the Persistent Chat service.</span></span></p></td>
<td><p><span data-ttu-id="ad38f-177">既定以外の場合</span><span class="sxs-lookup"><span data-stu-id="ad38f-177">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad38f-178">Test-CsUnifiedContactStore (UnifiedContactStore)</span><span class="sxs-lookup"><span data-stu-id="ad38f-178">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span></p></td>
<td><p><span data-ttu-id="ad38f-179">統合連絡先ストアを通じてユーザーの連絡先にアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad38f-179">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="ad38f-180">統合連絡先ストアは、Lync 2013、Outlook、または Outlook Web Access を使用してアクセスできる単一の連絡先セットを管理するための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="ad38f-180">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Lync 2013, Outlook, and/or Outlook Web Access.</span></span></p></td>
<td><p><span data-ttu-id="ad38f-181">既定以外の場合</span><span class="sxs-lookup"><span data-stu-id="ad38f-181">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad38f-182">Test-CsXmppIM (XmppIM)</span><span class="sxs-lookup"><span data-stu-id="ad38f-182">Test-CsXmppIM (XmppIM)</span></span></p></td>
<td><p><span data-ttu-id="ad38f-183">インスタントメッセージを XMPP (拡張メッセージングとプレゼンスプロトコル) ゲートウェイ間で送信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad38f-183">Confirms that an instant message can be sent across the XMPP (Extensible Messaging and Presence Protocol) gateway.</span></span></p></td>
<td><p><span data-ttu-id="ad38f-184">既定以外の場合</span><span class="sxs-lookup"><span data-stu-id="ad38f-184">Non-default</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ad38f-185">System Center Operations Manager を使用するためには、監視ノードをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ad38f-185">You do not need to install watcher nodes in order to use System Center Operations Manager.</span></span> <span data-ttu-id="ad38f-186">これらのノードをインストールしていない場合でも、問題が発生したときに Lync Server 2013 コンポーネントからリアルタイムの通知を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="ad38f-186">If you do not install these nodes, you can still get real-time alerts from Lync Server 2013 components when an issue occurs.</span></span> <span data-ttu-id="ad38f-187">(コンポーネントとユーザー管理パックはウォッチャーノードを使用しません)。ただし、アクティブな監視管理パックを使用してエンドツーエンドのシナリオを監視する場合は、監視ノードが必要です。</span><span class="sxs-lookup"><span data-stu-id="ad38f-187">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad38f-188">管理者は、Operations Manager を使用したりインストールしたりすることなく、代理トランザクションを手動で実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="ad38f-188">Administrators can also run synthetic transactions manually, without needing to use, or install, Operations Manager.</span></span> <span data-ttu-id="ad38f-189">さまざまなテスト用コマンドレットの詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 コマンドレットインデックス</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad38f-189">For details about the various Test-Cs cmdlets, see the <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlets index</A>.</span></span>



</div>

<span data-ttu-id="ad38f-190">展開のサイズによっては、合成トランザクションで大量のコンピューターメモリとプロセッサ時間を使うことがあります。</span><span class="sxs-lookup"><span data-stu-id="ad38f-190">Depending on the size of your deployment, synthetic transactions may use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="ad38f-191">このため、専用のコンピューターをウォッチャーノードとして使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ad38f-191">For this reason, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="ad38f-192">たとえば、フロントエンドサーバーを監視ノードとして動作するように構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="ad38f-192">For example, you should not configure a Front End Server to act as a watcher node.</span></span> <span data-ttu-id="ad38f-193">ウォッチャーノードは、次のハードウェア仕様を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad38f-193">Watcher nodes should meet the following hardware specifications:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad38f-194">従来の Microsoft Lync Server 2010 ウォッチャーノードは、Lync Server 2013 ウォッチャーノードと同じコンピューター上にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad38f-194">A legacy Microsoft Lync Server 2010 watcher node cannot be collocated on the same machine with a Lync Server 2013 watcher node.</span></span> <span data-ttu-id="ad38f-195">これは、Lync Server 2010 と Lync Server 2013 のコアシステムファイルを同じコンピューターにインストールできないためです。</span><span class="sxs-lookup"><span data-stu-id="ad38f-195">This is because the core system files for Lync Server 2010 and Lync Server 2013 cannot be installed on the same computer.</span></span><BR><span data-ttu-id="ad38f-196">ただし、lync server 2013 ウォッチャーノードでは、Lync Server 2013 と Lync Server 2010 の両方を同時に監視できます。</span><span class="sxs-lookup"><span data-stu-id="ad38f-196">However, Lync Server 2013 watcher nodes can simultaneously monitor both Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="ad38f-197">既定の代理トランザクションは、両方の製品バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ad38f-197">The Default synthetic transactions are supported on both product versions.</span></span>



</div>

<span data-ttu-id="ad38f-198">Lync Server 2013 ウォッチャーノードは、次の点を確認するために企業内外に展開することができます。</span><span class="sxs-lookup"><span data-stu-id="ad38f-198">Lync Server 2013 watcher nodes may be deployed inside or outside of an enterprise to help verify:</span></span>

  - <span></span>  
    <span data-ttu-id="ad38f-199">社内ユーザー用プールへの接続。</span><span class="sxs-lookup"><span data-stu-id="ad38f-199">Connectivity to pools for users inside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="ad38f-200">組織外で作業しているリモートユーザーに対する境界ネットワーク経由の接続。</span><span class="sxs-lookup"><span data-stu-id="ad38f-200">Connectivity through perimeter networks for remote users who work outside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="ad38f-201">ブランチ オフィス アプライアンスへの接続。</span><span class="sxs-lookup"><span data-stu-id="ad38f-201">Connectivity to branch office appliances.</span></span>

  - <span></span>  
    <span data-ttu-id="ad38f-202">企業内および境界ネットワーク経由での Lync Server 2010 への接続。</span><span class="sxs-lookup"><span data-stu-id="ad38f-202">Connectivity to Lync Server 2010 inside the enterprise and through perimeter networks.</span></span>

<span data-ttu-id="ad38f-203">管理を簡略化するために、エンタープライズの内外でさまざまな認証オプションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="ad38f-203">Different authentication options are available for inside and outside of the enterprise to help simplify administration.</span></span> <span data-ttu-id="ad38f-204">詳細については、「 [Lync Server 2013 で代理トランザクションを実行するためのウォッチャーノードの構成](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad38f-204">For details, see [Configuring a watcher node to run synthetic transactions in Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span></span>

<span data-ttu-id="ad38f-205">ウォッチャーノードとして動作するようにコンピューターを構成するには、System Center Operations Manager をインストールして Lync Server 2013 管理パックをインポートした後、次の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad38f-205">To configure a computer to act as a watcher node, you must complete the following steps after you have installed System Center Operations Manager and imported the Lync Server 2013 management packs.</span></span>

<span data-ttu-id="ad38f-206">Lync Server 2013 コアファイルと System Center agent ファイルをインストールする前に、監視ノードコンピューターが Lync Server 2013 をインストールするための前提条件をすべて満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad38f-206">Before you install the Lync Server 2013 core files and the System Center agent files, you should also make sure that the watcher node computer meets all the prerequisites for installing Lync Server 2013.</span></span> <span data-ttu-id="ad38f-207">また、ウォッチャーノードのコンピューターにも次の項目がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad38f-207">In addition, the watcher node computer should also have the following items installed:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad38f-208">ハードウェア コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ad38f-208">Hardware component</span></span></th>
<th><span data-ttu-id="ad38f-209">最小要件</span><span class="sxs-lookup"><span data-stu-id="ad38f-209">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad38f-210">CPU</span><span class="sxs-lookup"><span data-stu-id="ad38f-210">CPU</span></span></p></td>
<td><p><span data-ttu-id="ad38f-211">次のいずれかの要件:</span><span class="sxs-lookup"><span data-stu-id="ad38f-211">One of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ad38f-212">2.33 GHz またはそれ以上の 64 ビット プロセッサ、クアッド コア</span><span class="sxs-lookup"><span data-stu-id="ad38f-212">64-bit processor, quad-core, 2.33 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="ad38f-213">64 ビット 2 ウェイ プロセッサ、デュアル コア、2.33 GHz 以上</span><span class="sxs-lookup"><span data-stu-id="ad38f-213">64-bit 2-way processor, dual-core, 2.33 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad38f-214">メモリ</span><span class="sxs-lookup"><span data-stu-id="ad38f-214">Memory</span></span></p></td>
<td><p><span data-ttu-id="ad38f-215">8 GB</span><span class="sxs-lookup"><span data-stu-id="ad38f-215">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad38f-216">ネットワークオペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="ad38f-216">Network operating system</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ad38f-217">1 Gbps のネットワークアダプタ 1 Gbps</span><span class="sxs-lookup"><span data-stu-id="ad38f-217">1 network adapter 1 Gbps</span></span></p></li>
<li><p><span data-ttu-id="ad38f-218">Windows Server 2008 R2、Windows Server 2012、または</span><span class="sxs-lookup"><span data-stu-id="ad38f-218">Windows Server 2008 R2, Windows Server 2012, or</span></span></p>
<p><span data-ttu-id="ad38f-219">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ad38f-219">Windows Server 2012 R2</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


  - <span data-ttu-id="ad38f-220">.NET Framework 4.5 の完全バージョン。</span><span class="sxs-lookup"><span data-stu-id="ad38f-220">The full version of .NET Framework 4.5.</span></span>

  - <span data-ttu-id="ad38f-221">Windows Identity Foundation。</span><span class="sxs-lookup"><span data-stu-id="ad38f-221">Windows Identity Foundation.</span></span>

  - <span data-ttu-id="ad38f-222">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="ad38f-222">Windows PowerShell 3.0.</span></span>

<span data-ttu-id="ad38f-223">すべての前提条件が満たされたら、次の方法でウォッチャーノードを構成できます。</span><span class="sxs-lookup"><span data-stu-id="ad38f-223">As soon as all these prerequisites have been met, you can configure the watcher node by:</span></span>

  - <span data-ttu-id="ad38f-224">ウォッチャーノードコンピューターに Lync Server 2013 コアファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ad38f-224">Installing the Lync Server 2013 core files on the watcher node computer.</span></span>

  - <span data-ttu-id="ad38f-225">Watcher ノードコンピューターに System Center Operations Manager エージェントをインストールしています。</span><span class="sxs-lookup"><span data-stu-id="ad38f-225">Installing System Center Operations Manager agent on the watcher node computer.</span></span>

  - <span data-ttu-id="ad38f-226">Watchernode 実行可能ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad38f-226">Running the Watchernode.msi executable file.</span></span>

  - <span data-ttu-id="ad38f-227">**CsWatcherNodeConfiguration**コマンドレットを使用して、ウォッチャーノードによって採用されるテストユーザーを構成します。</span><span class="sxs-lookup"><span data-stu-id="ad38f-227">Using the **CsWatcherNodeConfiguration** cmdlets to configure test users to be employed by the watcher node.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

