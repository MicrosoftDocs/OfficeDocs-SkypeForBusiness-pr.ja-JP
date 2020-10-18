---
title: 'Lync Server 2013: 監視ノードのインストールと構成'
description: 'Lync Server 2013: 監視ノードのインストールと構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87bf43e1651fabfa0137d09234d663cc905e947b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574003"
---
# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="e43ed-103">Lync Server 2013 での監視ノードのインストールと構成</span><span class="sxs-lookup"><span data-stu-id="e43ed-103">Installing and configuring watcher nodes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e43ed-104">_**トピックの最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="e43ed-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="e43ed-105">*監視ノード* は、定期的に Lync Server 代理トランザクションを実行するコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="e43ed-105">*Watcher nodes* are computers that periodically run Lync Server synthetic transactions.</span></span> <span data-ttu-id="e43ed-106">*代理トランザクション* は Windows PowerShell コマンドレットで、システムにサインインする機能、またはインスタントメッセージを交換できるかどうかなど、主要なエンドユーザーシナリオが想定どおりに動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e43ed-106">*Synthetic transactions* are Windows PowerShell cmdlets that verify that key end user scenarios—such as the ability to sign in to the system, or the ability to exchange instant messages—are working as expected.</span></span> <span data-ttu-id="e43ed-107">Lync Server 2013 の場合、System Center Operations Manager は、次の表に示す代理トランザクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e43ed-107">For Lync Server 2013, System Center Operations Manager can run the synthetic transactions shown in the following table.</span></span> <span data-ttu-id="e43ed-108">代理トランザクションには、表に示す 3 つの種類があります。</span><span class="sxs-lookup"><span data-stu-id="e43ed-108">There are three different synthetic transaction types shown in the table:</span></span>

  - <span data-ttu-id="e43ed-109">**既定値**です。</span><span class="sxs-lookup"><span data-stu-id="e43ed-109">**Default**.</span></span> <span data-ttu-id="e43ed-110">既定では、監視ノードが実行する代理トランザクションです。</span><span class="sxs-lookup"><span data-stu-id="e43ed-110">These are the synthetic transactions that a watcher node will run by default.</span></span> <span data-ttu-id="e43ed-111">新しい監視ノードを作成するときに、そのノードが実行する代理トランザクションを指定するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="e43ed-111">When you create a new watcher node, you have the option of specifying which synthetic transactions that node will run.</span></span> <span data-ttu-id="e43ed-112">(これは、 **set-cswatchernodeconfiguration** コマンドレットで使用される Tests パラメーターの目的です。)監視ノードの作成時に Tests パラメーターを使用しない場合、既定の代理トランザクションがすべて自動的に実行され、既定以外の代理トランザクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="e43ed-112">(That's the purpose of the Tests parameter used by the **New-CsWatcherNodeConfiguration** cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="e43ed-113">つまり、監視ノードは Test-CsAddressBookService テストを実行するように構成されますが、Test-CsExumConnectivity テストを実行するように構成されることはありません。</span><span class="sxs-lookup"><span data-stu-id="e43ed-113">That means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>

  - <span data-ttu-id="e43ed-114">**既定値ではない**。</span><span class="sxs-lookup"><span data-stu-id="e43ed-114">**Non-default**.</span></span> <span data-ttu-id="e43ed-115">名前が意味するように、既定以外の代理トランザクションは、監視ノードが既定で実行しないテストです。</span><span class="sxs-lookup"><span data-stu-id="e43ed-115">As the name implies, Non-default synthetic transactions are tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="e43ed-116">ただし、監視ノードは、任意の既定以外の代理トランザクションを実行するように設定できます。</span><span class="sxs-lookup"><span data-stu-id="e43ed-116">However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="e43ed-117">これは、**New-CsWatcherNodeConfiguration** コマンドレットを使用して監視ノードを作成するとき、または作成後の任意の時点で実行できます。</span><span class="sxs-lookup"><span data-stu-id="e43ed-117">You can do this when you create the watcher node (by using the **New-CsWatcherNodeConfiguration** cmdlet), or at any time after that.</span></span> <span data-ttu-id="e43ed-118">既定以外の代理トランザクションの多くは、追加のセットアップ手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e43ed-118">Many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="e43ed-119">詳細については、「 [Lync Server 2013 の代理トランザクションの特別なセットアップ手順](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e43ed-119">For details, see [Special setup instructions for synthetic transactions in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span></span>

  - <span data-ttu-id="e43ed-120">**拡張**。</span><span class="sxs-lookup"><span data-stu-id="e43ed-120">**Extended**.</span></span> <span data-ttu-id="e43ed-121">拡張テストは、特別な種類の既定以外の代理トランザクションです。</span><span class="sxs-lookup"><span data-stu-id="e43ed-121">Extended tests are a special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="e43ed-122">他の代理トランザクションとは異なり、拡張テストは、1 回のパスで複数回実行できます。</span><span class="sxs-lookup"><span data-stu-id="e43ed-122">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="e43ed-123">これは、プールに対する複数の公衆交換電話網 (PSTN) 音声ルートなどの動作を検証するときに便利です。</span><span class="sxs-lookup"><span data-stu-id="e43ed-123">This can be useful when verifying behavior such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="e43ed-124">これは、拡張テストの複数のインスタンスを監視ノードに追加するだけで構成できます。</span><span class="sxs-lookup"><span data-stu-id="e43ed-124">This can be configured simply by adding multiple instances of an Extended test to a watcher node.</span></span>

<span data-ttu-id="e43ed-125">他の代理トランザクションを監視ノードに追加するプロセスの詳細については、「 [Lync Server 2013 の監視ノードの管理](lync-server-2013-managing-watcher-nodes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e43ed-125">For details about the process of adding other synthetic transactions to a watcher node, see [Managing watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span></span> <span data-ttu-id="e43ed-126">Lync Server 管理シェルを使用して、監視ノードから代理トランザクションを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="e43ed-126">You can use the Lync Server Management Shell to remove synthetic transactions from a watcher node.</span></span>

<span data-ttu-id="e43ed-127">監視ノードで使用できる代理トランザクションは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e43ed-127">The synthetic transactions available to watcher nodes include the following:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e43ed-128">コマンドレット名 (テスト名)</span><span class="sxs-lookup"><span data-stu-id="e43ed-128">Cmdlet Name (Test Name)</span></span></th>
<th><span data-ttu-id="e43ed-129">説明</span><span class="sxs-lookup"><span data-stu-id="e43ed-129">Description</span></span></th>
<th><span data-ttu-id="e43ed-130">代理トランザクションの種類</span><span class="sxs-lookup"><span data-stu-id="e43ed-130">Synthetic Transaction Type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e43ed-131">Test-CsAddressBookService (ABS)</span><span class="sxs-lookup"><span data-stu-id="e43ed-131">Test-CsAddressBookService (ABS)</span></span></p></td>
<td><p><span data-ttu-id="e43ed-132">ユーザーが各自の連絡先リストに含まれていないユーザーを検索できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e43ed-132">Confirms that users are able to look up users that aren’t in their contact list.</span></span></p></td>
<td><p><span data-ttu-id="e43ed-133">既定値</span><span class="sxs-lookup"><span data-stu-id="e43ed-133">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e43ed-134">Test-CsAddressBookWebQuery (ABWQ)</span><span class="sxs-lookup"><span data-stu-id="e43ed-134">Test-CsAddressBookWebQuery (ABWQ)</span></span></p></td>
<td><p><span data-ttu-id="e43ed-135">ユーザーが各自の連絡先リストに含まれていないユーザーを HTTP 経由で検索できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e43ed-135">Confirms that users are able to look up users that aren’t in their contact list via HTTP.</span></span></p></td>
<td><p><span data-ttu-id="e43ed-136">既定値</span><span class="sxs-lookup"><span data-stu-id="e43ed-136">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e43ed-137">Test-CsIM (IM)</span><span class="sxs-lookup"><span data-stu-id="e43ed-137">Test-CsIM (IM)</span></span></p></td>
<td><p><span data-ttu-id="e43ed-138">ユーザーがピアツーピア インスタント メッセージを送信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e43ed-138">Confirms that users are able to send peer-to-peer instant messages.</span></span></p></td>
<td><p><span data-ttu-id="e43ed-139">既定値</span><span class="sxs-lookup"><span data-stu-id="e43ed-139">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e43ed-140">Test-CsP2PAV (P2PAV)</span><span class="sxs-lookup"><span data-stu-id="e43ed-140">Test-CsP2PAV (P2PAV)</span></span></p></td>
<td><p><span data-ttu-id="e43ed-141">ユーザーがピアツーピア音声通話を開始できることを確認します (シグナリングのみ)。</span><span class="sxs-lookup"><span data-stu-id="e43ed-141">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span></p></td>
<td><p><span data-ttu-id="e43ed-142">既定値</span><span class="sxs-lookup"><span data-stu-id="e43ed-142">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e43ed-143">Test-CsPresence (Presence)</span><span class="sxs-lookup"><span data-stu-id="e43ed-143">Test-CsPresence (Presence)</span></span></p></td>
<td><p><span data-ttu-id="e43ed-144">ユーザーが他のユーザーのプレゼンスを表示できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e43ed-144">Confirms that users are able to view other users’ presence.</span></span></p></td>
<td><p><span data-ttu-id="e43ed-145">既定値</span><span class="sxs-lookup"><span data-stu-id="e43ed-145">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e43ed-146">Test-CsRegistration (Registration)</span><span class="sxs-lookup"><span data-stu-id="e43ed-146">Test-CsRegistration (Registration)</span></span></p></td>
<td><p><span data-ttu-id="e43ed-147">ユーザーが Lync にサインインできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e43ed-147">Confirms that users are able sign in to Lync.</span></span></p></td>
<td><p><span data-ttu-id="e43ed-148">既定値</span><span class="sxs-lookup"><span data-stu-id="e43ed-148">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e43ed-149">Test-CsAudioConferencingProvider (ACP)</span><span class="sxs-lookup"><span data-stu-id="e43ed-149">Test-CsAudioConferencingProvider (ACP)</span></span></p></td>
<td><p><span data-ttu-id="e43ed-150">社内バージョンの Lync Server 2013 では使用されません。</span><span class="sxs-lookup"><span data-stu-id="e43ed-150">Not used with the on-premises version of Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="e43ed-151">拡張</span><span class="sxs-lookup"><span data-stu-id="e43ed-151">Extended</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e43ed-152">Test-CsPstnPeerToPeerCall (PSTN)</span><span class="sxs-lookup"><span data-stu-id="e43ed-152">Test-CsPstnPeerToPeerCall (PSTN)</span></span></p></td>
<td><p><span data-ttu-id="e43ed-153">ユーザーが企業の外部のユーザー (PSTN 番号) と通話できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e43ed-153">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span></p></td>
<td><p><span data-ttu-id="e43ed-154">既定以外、拡張</span><span class="sxs-lookup"><span data-stu-id="e43ed-154">Non-default, Extended</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e43ed-155">Test-CsAVConference (AvConference)</span><span class="sxs-lookup"><span data-stu-id="e43ed-155">Test-CsAVConference (AvConference)</span></span></p></td>
<td><p><span data-ttu-id="e43ed-156">ユーザーが音声/ビデオ会議で作成と参加が可能なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e43ed-156">Confirms that users are able to create and participate in an audio/video conference.</span></span></p></td>
<td><p><span data-ttu-id="e43ed-157">既定値</span><span class="sxs-lookup"><span data-stu-id="e43ed-157">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e43ed-158">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span><span class="sxs-lookup"><span data-stu-id="e43ed-158">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="e43ed-159">音声ビデオ エッジ サーバーがピアツーピア通話と会議通話を行うための接続を受け入れることができることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e43ed-159">Confirms that the A/V Edge servers are able to accept connections for peer-to-peer calls and conference calls.</span></span></p></td>
<td><p><span data-ttu-id="e43ed-160">既定以外</span><span class="sxs-lookup"><span data-stu-id="e43ed-160">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e43ed-161">Test-CsDataConference (DataConference)</span><span class="sxs-lookup"><span data-stu-id="e43ed-161">Test-CsDataConference (DataConference)</span></span></p></td>
<td><p><span data-ttu-id="e43ed-162">ユーザーが、データ グループ作業電話会議 (ホワイトボードや投票などのアクティビティが含まれるオンライン ミーティング) に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e43ed-162">Confirms that users can participate in a data collaboration conference, an online meeting that includes activities such as whiteboards and polls.</span></span></p></td>
<td><p><span data-ttu-id="e43ed-163">既定以外</span><span class="sxs-lookup"><span data-stu-id="e43ed-163">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e43ed-164">Test-CsExumConnectivity (ExumConnectivity)</span><span class="sxs-lookup"><span data-stu-id="e43ed-164">Test-CsExumConnectivity (ExumConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="e43ed-165">ユーザーが Exchange ユニファイドメッセージング (UM) に接続できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e43ed-165">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="e43ed-166">既定以外</span><span class="sxs-lookup"><span data-stu-id="e43ed-166">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e43ed-167">Test-CsGroupIM (GroupIM)</span><span class="sxs-lookup"><span data-stu-id="e43ed-167">Test-CsGroupIM (GroupIM)</span></span></p></td>
<td><p><span data-ttu-id="e43ed-168">ユーザーが会議中にインスタント メッセージを送信でき、3 人以上のユーザーとインスタント メッセージでの会話に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e43ed-168">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span></p></td>
<td><p><span data-ttu-id="e43ed-169">既定値</span><span class="sxs-lookup"><span data-stu-id="e43ed-169">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e43ed-170">Test-CsGroupIM – TestJoinLauncher (Joinランチャー)</span><span class="sxs-lookup"><span data-stu-id="e43ed-170">Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</span></span></p></td>
<td><p><span data-ttu-id="e43ed-171">ユーザーがミーティングを作成でき、予定されたミーティングに Web アドレス リンクを介して参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e43ed-171">Confirms that users are able to create and join scheduled meetings via a web address link.</span></span></p></td>
<td><p><span data-ttu-id="e43ed-172">既定以外</span><span class="sxs-lookup"><span data-stu-id="e43ed-172">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e43ed-173">Test-CsMCXP2PIM (MCXP2PIM)</span><span class="sxs-lookup"><span data-stu-id="e43ed-173">Test-CsMCXP2PIM (MCXP2PIM)</span></span></p></td>
<td><p><span data-ttu-id="e43ed-174">モバイル デバイス ユーザーがインスタント メッセージの登録と送信を実行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e43ed-174">Confirms that mobile device users are able to register and send instant messages.</span></span></p></td>
<td><p><span data-ttu-id="e43ed-175">既定以外</span><span class="sxs-lookup"><span data-stu-id="e43ed-175">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e43ed-176">Test-CsPersistentChatMessage (PersistentChatMessage)</span><span class="sxs-lookup"><span data-stu-id="e43ed-176">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span></p></td>
<td><p><span data-ttu-id="e43ed-177">ユーザーが常設チャットサービスを使用してメッセージを交換できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e43ed-177">Confirms that users can exchange messages by using the Persistent Chat service.</span></span></p></td>
<td><p><span data-ttu-id="e43ed-178">既定以外</span><span class="sxs-lookup"><span data-stu-id="e43ed-178">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e43ed-179">Test-CsUnifiedContactStore (UnifiedContactStore)</span><span class="sxs-lookup"><span data-stu-id="e43ed-179">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span></p></td>
<td><p><span data-ttu-id="e43ed-180">統合連絡先ストアを通じてユーザーの連絡先にアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e43ed-180">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="e43ed-181">統合連絡先ストアは、Lync 2013、Outlook、または Outlook Web Access を使用してアクセスできる単一の連絡先セットを管理する方法をユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="e43ed-181">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Lync 2013, Outlook, and/or Outlook Web Access.</span></span></p></td>
<td><p><span data-ttu-id="e43ed-182">既定以外</span><span class="sxs-lookup"><span data-stu-id="e43ed-182">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e43ed-183">Test-CsXmppIM (XmppIM)</span><span class="sxs-lookup"><span data-stu-id="e43ed-183">Test-CsXmppIM (XmppIM)</span></span></p></td>
<td><p><span data-ttu-id="e43ed-184">インスタント メッセージを XMPP (Extensible Messaging and Presence Protocol) ゲートウェイ経由で送信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e43ed-184">Confirms that an instant message can be sent across the XMPP (Extensible Messaging and Presence Protocol) gateway.</span></span></p></td>
<td><p><span data-ttu-id="e43ed-185">既定以外</span><span class="sxs-lookup"><span data-stu-id="e43ed-185">Non-default</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e43ed-186">System Center Operations Manager を使用するために監視ノードをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e43ed-186">You do not need to install watcher nodes in order to use System Center Operations Manager.</span></span> <span data-ttu-id="e43ed-187">これらのノードをインストールしていない場合でも、問題が発生したときに Lync Server 2013 コンポーネントからリアルタイム通知を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="e43ed-187">If you do not install these nodes, you can still get real-time alerts from Lync Server 2013 components when an issue occurs.</span></span> <span data-ttu-id="e43ed-188">(コンポーネントおよびユーザー管理パックでは、監視ノードは使用されません)。ただし、アクティブな監視管理パックを使用してエンドツーエンドのシナリオを監視する場合は、監視ノードが必要です。</span><span class="sxs-lookup"><span data-stu-id="e43ed-188">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e43ed-189">管理者は、Operations Manager を使用したり、それをインストールすることなく、代理トランザクションを手動で実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="e43ed-189">Administrators can also run synthetic transactions manually, without needing to use, or install, Operations Manager.</span></span> <span data-ttu-id="e43ed-190">さまざまな Test-Cs コマンドレットの詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 コマンドレットのインデックス</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e43ed-190">For details about the various Test-Cs cmdlets, see the <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlets index</A>.</span></span>



</div>

<span data-ttu-id="e43ed-191">展開の規模によっては、代理トランザクションがコンピューター メモリを大量に使用し、プロセッサを長時間使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="e43ed-191">Depending on the size of your deployment, synthetic transactions may use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="e43ed-192">このため、監視ノードとして動作する専用コンピューターを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e43ed-192">For this reason, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="e43ed-193">たとえば、監視ノードとして動作するようにフロントエンドサーバーを構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e43ed-193">For example, you should not configure a Front End Server to act as a watcher node.</span></span> <span data-ttu-id="e43ed-194">監視ノードは、次のハードウェア仕様を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e43ed-194">Watcher nodes should meet the following hardware specifications:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e43ed-195">従来の Microsoft Lync Server 2010 監視ノードを、Lync Server 2013 監視ノードと同じコンピューターに併置することはできません。</span><span class="sxs-lookup"><span data-stu-id="e43ed-195">A legacy Microsoft Lync Server 2010 watcher node cannot be collocated on the same machine with a Lync Server 2013 watcher node.</span></span> <span data-ttu-id="e43ed-196">これは、Lync Server 2010 および Lync Server 2013 のコアシステムファイルを同じコンピューターにインストールできないためです。</span><span class="sxs-lookup"><span data-stu-id="e43ed-196">This is because the core system files for Lync Server 2010 and Lync Server 2013 cannot be installed on the same computer.</span></span><BR><span data-ttu-id="e43ed-197">ただし、Lync server 2013 監視ノードは、Lync Server 2013 と Lync Server 2010 の両方を同時に監視できます。</span><span class="sxs-lookup"><span data-stu-id="e43ed-197">However, Lync Server 2013 watcher nodes can simultaneously monitor both Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="e43ed-198">既定の代理トランザクションは、両方のバージョンの製品でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e43ed-198">The Default synthetic transactions are supported on both product versions.</span></span>



</div>

<span data-ttu-id="e43ed-199">Lync Server 2013 監視ノードはエンタープライズの内部または外部に展開され、次の点を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e43ed-199">Lync Server 2013 watcher nodes may be deployed inside or outside of an enterprise to help verify:</span></span>

  - <span></span>  
    <span data-ttu-id="e43ed-200">社内ユーザー用プールへの接続。</span><span class="sxs-lookup"><span data-stu-id="e43ed-200">Connectivity to pools for users inside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="e43ed-201">社外で働くリモート ユーザー用の境界ネットワーク経由の接続。</span><span class="sxs-lookup"><span data-stu-id="e43ed-201">Connectivity through perimeter networks for remote users who work outside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="e43ed-202">ブランチ オフィス アプライアンスへの接続。</span><span class="sxs-lookup"><span data-stu-id="e43ed-202">Connectivity to branch office appliances.</span></span>

  - <span></span>  
    <span data-ttu-id="e43ed-203">企業内および境界ネットワークを介した Lync Server 2010 への接続。</span><span class="sxs-lookup"><span data-stu-id="e43ed-203">Connectivity to Lync Server 2010 inside the enterprise and through perimeter networks.</span></span>

<span data-ttu-id="e43ed-204">管理を容易にするため、社内および社外用の異なる認証オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="e43ed-204">Different authentication options are available for inside and outside of the enterprise to help simplify administration.</span></span> <span data-ttu-id="e43ed-205">詳細については、「 [Lync Server 2013 で代理トランザクションを実行する監視ノードの構成](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e43ed-205">For details, see [Configuring a watcher node to run synthetic transactions in Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span></span>

<span data-ttu-id="e43ed-206">監視ノードとして動作するようにコンピューターを構成するには、System Center Operations Manager をインストールして Lync Server 2013 管理パックをインポートした後、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e43ed-206">To configure a computer to act as a watcher node, you must complete the following steps after you have installed System Center Operations Manager and imported the Lync Server 2013 management packs.</span></span>

<span data-ttu-id="e43ed-207">Lync Server 2013 コアファイルおよび System Center エージェントファイルをインストールする前に、監視ノードコンピューターが Lync Server 2013 をインストールするための前提条件をすべて満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e43ed-207">Before you install the Lync Server 2013 core files and the System Center agent files, you should also make sure that the watcher node computer meets all the prerequisites for installing Lync Server 2013.</span></span> <span data-ttu-id="e43ed-208">さらに、監視ノード コンピューターには、次の項目がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e43ed-208">In addition, the watcher node computer should also have the following items installed:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e43ed-209">ハードウェア コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e43ed-209">Hardware component</span></span></th>
<th><span data-ttu-id="e43ed-210">最小要件</span><span class="sxs-lookup"><span data-stu-id="e43ed-210">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e43ed-211">CPU</span><span class="sxs-lookup"><span data-stu-id="e43ed-211">CPU</span></span></p></td>
<td><p><span data-ttu-id="e43ed-212">次のいずれかの要件:</span><span class="sxs-lookup"><span data-stu-id="e43ed-212">One of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e43ed-213">64ビットプロセッサ、クアッドコア、2.33 GHz またはそれ以上</span><span class="sxs-lookup"><span data-stu-id="e43ed-213">64-bit processor, quad-core, 2.33 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="e43ed-214">64ビット2ウェイプロセッサ、デュアルコア、2.33 GHz またはそれ以上</span><span class="sxs-lookup"><span data-stu-id="e43ed-214">64-bit 2-way processor, dual-core, 2.33 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e43ed-215">メモリ</span><span class="sxs-lookup"><span data-stu-id="e43ed-215">Memory</span></span></p></td>
<td><p><span data-ttu-id="e43ed-216">8 GB</span><span class="sxs-lookup"><span data-stu-id="e43ed-216">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e43ed-217">ネットワークオペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="e43ed-217">Network operating system</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e43ed-218">1ネットワークアダプター 1 Gbps</span><span class="sxs-lookup"><span data-stu-id="e43ed-218">1 network adapter 1 Gbps</span></span></p></li>
<li><p><span data-ttu-id="e43ed-219">Windows Server 2008 R2、Windows Server 2012、または</span><span class="sxs-lookup"><span data-stu-id="e43ed-219">Windows Server 2008 R2, Windows Server 2012, or</span></span></p>
<p><span data-ttu-id="e43ed-220">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="e43ed-220">Windows Server 2012 R2</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


  - <span data-ttu-id="e43ed-221">製品版の .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="e43ed-221">The full version of .NET Framework 4.5.</span></span>

  - <span data-ttu-id="e43ed-222">Windows Identity Foundation。</span><span class="sxs-lookup"><span data-stu-id="e43ed-222">Windows Identity Foundation.</span></span>

  - <span data-ttu-id="e43ed-223">Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="e43ed-223">Windows PowerShell 3.0.</span></span>

<span data-ttu-id="e43ed-224">これらの前提条件がすべて満たされた後、次を行うことで監視ノードを構成できます。</span><span class="sxs-lookup"><span data-stu-id="e43ed-224">As soon as all these prerequisites have been met, you can configure the watcher node by:</span></span>

  - <span data-ttu-id="e43ed-225">監視ノードコンピューターに Lync Server 2013 コアファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e43ed-225">Installing the Lync Server 2013 core files on the watcher node computer.</span></span>

  - <span data-ttu-id="e43ed-226">監視ノードコンピューターに System Center Operations Manager エージェントをインストールしています。</span><span class="sxs-lookup"><span data-stu-id="e43ed-226">Installing System Center Operations Manager agent on the watcher node computer.</span></span>

  - <span data-ttu-id="e43ed-227">Watchernode.msi 実行可能ファイルの実行。</span><span class="sxs-lookup"><span data-stu-id="e43ed-227">Running the Watchernode.msi executable file.</span></span>

  - <span data-ttu-id="e43ed-228">**CsWatcherNodeConfiguration** コマンドレットによる監視ノードで使用されるテスト ユーザーの構成。</span><span class="sxs-lookup"><span data-stu-id="e43ed-228">Using the **CsWatcherNodeConfiguration** cmdlets to configure test users to be employed by the watcher node.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

