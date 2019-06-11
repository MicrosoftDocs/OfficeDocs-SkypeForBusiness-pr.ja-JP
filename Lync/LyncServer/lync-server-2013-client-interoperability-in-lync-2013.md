---
title: 'Lync Server 2013: Lync 2013 でのクライアント相互運用性'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8ccc6239ffa0216e36839a7e58b510d8c8c3240
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="8b6fc-102">Lync 2013 でのクライアント相互運用性</span><span class="sxs-lookup"><span data-stu-id="8b6fc-102">Client interoperability in Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b6fc-103">_**最終更新日:** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="8b6fc-103">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="8b6fc-104">このトピックでは、Microsoft Lync Server 2013 クライアントが、以前のバージョンの Lync Server と Office Communications Server からクライアントとの共存と操作を行うことができるようにする機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-104">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="8b6fc-105">サーバーとクライアントの互換性</span><span class="sxs-lookup"><span data-stu-id="8b6fc-105">Server and Client Compatibility</span></span>

<span data-ttu-id="8b6fc-106">次の表は、クライアントバージョンとサーバーバージョンのサポートされる組み合わせを示しています。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-106">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="8b6fc-107">次の表は、クライアントが指定したサーバーに接続しようとしたときにサインインがサポートされるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-107">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="8b6fc-108">Lync Server 2013 では、以前のクライアントバージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-108">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="8b6fc-109">また、以前のリリースとは異なり、Lync Server 2010 では新しい Lync 2013 クライアントがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-109">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="8b6fc-110">これにより、Lync Server 2010 からアップグレードしている組織は、Lync Server のアップグレードに関係なく、新しいクライアントを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-110">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b6fc-111">クライアント</span><span class="sxs-lookup"><span data-stu-id="8b6fc-111">Client</span></span></th>
<th><span data-ttu-id="8b6fc-112">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b6fc-112">Lync Server 2013</span></span></th>
<th><span data-ttu-id="8b6fc-113">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="8b6fc-113">Lync Server 2010</span></span></th>
<th><span data-ttu-id="8b6fc-114">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="8b6fc-114">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b6fc-115">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="8b6fc-115">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-116">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-116">Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-117">Supported5</span><span class="sxs-lookup"><span data-stu-id="8b6fc-117">Supported5</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-118">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="8b6fc-118">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b6fc-119">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="8b6fc-119">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-120">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-120">Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-121">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-122">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="8b6fc-122">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b6fc-123">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="8b6fc-123">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-124">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-124">Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-125">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="8b6fc-125">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-126">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="8b6fc-126">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b6fc-127">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="8b6fc-127">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-128">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-128">Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-129">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-130">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="8b6fc-130">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b6fc-131">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="8b6fc-131">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-132">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-132">Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-133">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-134">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="8b6fc-134">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b6fc-135">Lync 2010 グループ チャット</span><span class="sxs-lookup"><span data-stu-id="8b6fc-135">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-136">Supported1</span><span class="sxs-lookup"><span data-stu-id="8b6fc-136">Supported1</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-137">Supported2</span><span class="sxs-lookup"><span data-stu-id="8b6fc-137">Supported2</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-138">該当なし</span><span class="sxs-lookup"><span data-stu-id="8b6fc-138">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b6fc-139">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="8b6fc-139">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-140">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="8b6fc-140">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-141">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-141">Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-142">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="8b6fc-142">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b6fc-143">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="8b6fc-143">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-144">Supported3 しない</span><span class="sxs-lookup"><span data-stu-id="8b6fc-144">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-145">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-145">Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-146">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="8b6fc-146">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b6fc-147">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="8b6fc-147">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-148">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="8b6fc-148">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-149">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-149">Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-150">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-150">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b6fc-151">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="8b6fc-151">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-152">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="8b6fc-152">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-153">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-153">Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-154">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-154">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b6fc-155">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="8b6fc-155">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-156">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="8b6fc-156">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-157">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-157">Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-158">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-158">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b6fc-159">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="8b6fc-159">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-160">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="8b6fc-160">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-161">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-161">Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-162">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-162">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b6fc-163">Lync Windows ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="8b6fc-163">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-164">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-164">Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-165">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-166">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="8b6fc-166">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8b6fc-167">1For については、「 [Lync server 2010、グループチャット、または Office Communications Server 2007 R2 グループチャットから Lync server 2013、常設チャットサーバーへの移行](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-167">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="8b6fc-168">2In Lync Server 2010 では、グループチャット機能は、Lync Server 2010 用のサードパーティの信頼済みアプリケーションであるグループチャットサーバーで利用できました。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-168">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="8b6fc-169">Lync 2013 クライアントは、Lync Server 2010、グループチャットとは互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-169">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="8b6fc-170">3Lync Web App 2013 は、コンピューターの音声やビデオなどの完全な会議エクスペリエンスを提供するようになりました。 Lync 2010 の出席者に代わるものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-170">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="8b6fc-171">Lync 2010 出席者は、サポートされていないブラウザー (Internet Explorer 6 または Internet Explorer 7) と Windows XP を使用している場合にのみ Lync Server 2013 に接続します。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-171">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="8b6fc-172">4 Office Communicator 2007 R2 のプレゼンス機能と IM 機能は Lync Server 2013 と互換性がありますが、会議機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-172">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="8b6fc-173">Office Communications Server 2007 R2 からの移行中、Office Communicator 2007 R2 はプレゼンスと IM の相互運用性に適していますが、ユーザーは Lync Web App 2013 を使って Lync Server 2013 会議に参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-173">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="8b6fc-174">5制限事項については、このトピックで後述する「lync Server 2010 会議での Lync 2013 クライアントの会議機能のサポート」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-174">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="8b6fc-175">クライアント間の相互運用性</span><span class="sxs-lookup"><span data-stu-id="8b6fc-175">Interoperability among Clients</span></span>

<span data-ttu-id="8b6fc-176">Lync Server 2013 リリースでは、さまざまなクライアントバージョンがピアツーピアと会議の両方のシナリオでシームレスに対話できます。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-176">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="8b6fc-177">このセクションでは、ユーザーがさまざまなバージョンのクライアントとサーバーを使用している他のユーザーと対話する場合の、使用可能な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-177">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="8b6fc-178">ピアツーピア機能のサポート</span><span class="sxs-lookup"><span data-stu-id="8b6fc-178">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="8b6fc-179">ピアツーピア機能は、異なるバージョンのサーバーを使用していて、異なるクライアントバージョンを使っているユーザーに対してサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-179">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions.</span></span> <span data-ttu-id="8b6fc-180">エンドユーザーエクスペリエンスと利用可能な機能は、ユーザーのクライアントの機能と、ユーザーがサインインしているサーバーのバージョンによって一貫しています。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-180">The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to.</span></span> <span data-ttu-id="8b6fc-181">つまり、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-181">In other words:</span></span>

  - <span data-ttu-id="8b6fc-182">ユーザーが古いクライアントを使って Lync Server 2013 にサインインしている場合、ユーザーの使用経験は同じになります。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-182">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="8b6fc-183">Lync Server 2013 で導入された新機能は、ユーザーのクライアントがアップグレードされるまで使用できません。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-183">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="8b6fc-184">例としては、ビデオギャラリービュー、HD ビデオ、更新された PowerPoint 共有、すべての参加者の音声とビデオを会議の入力時にミュートするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-184">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="8b6fc-185">新しい機能については、「 [Lync server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md)」と「 [lync server 2013 でのクライアントの新](lync-server-2013-what-s-new-for-clients.md)機能」で説明しています。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-185">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="8b6fc-186">ユーザーが lync 2013 クライアントを使って Lync Server 2010 にサインインしている場合、lync server 2010 でサポートされていないすべての新機能は、ユーザーが Lync Server 2013 に移動されるまで使用できません。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-186">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="8b6fc-187">次の表では、クライアントが Lync Server 2013 または Lync Server 2010 のいずれかにサインインしているピアツーピアセッションの機能の可用性を比較します。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-187">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b6fc-188">Lync Web App と Lync 2010 の出席者は会議専用クライアントであり、この表には含まれていません。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-188">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



</div>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b6fc-189">クライアント</span><span class="sxs-lookup"><span data-stu-id="8b6fc-189">Client</span></span></th>
<th><span data-ttu-id="8b6fc-190">インスタントメッセージ (im)</span><span class="sxs-lookup"><span data-stu-id="8b6fc-190">Instant Messaging</span></span></th>
<th><span data-ttu-id="8b6fc-191">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="8b6fc-191">Presence</span></span></th>
<th><span data-ttu-id="8b6fc-192">音声</span><span class="sxs-lookup"><span data-stu-id="8b6fc-192">Voice</span></span></th>
<th><span data-ttu-id="8b6fc-193">ビデオ</span><span class="sxs-lookup"><span data-stu-id="8b6fc-193">Video</span></span></th>
<th><span data-ttu-id="8b6fc-194">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="8b6fc-194">Application Sharing</span></span></th>
<th><span data-ttu-id="8b6fc-195">ファイル送信</span><span class="sxs-lookup"><span data-stu-id="8b6fc-195">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b6fc-196">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="8b6fc-196">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-197">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-197">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-198">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-199">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-200">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-201">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-202">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-202">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b6fc-203">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="8b6fc-203">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-204">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-205">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-206">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-207">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-208">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-209">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-209">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b6fc-210">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="8b6fc-210">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-211">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-211">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-212">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-213">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-214">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-215">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-216">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-216">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b6fc-217">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="8b6fc-217">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-218">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-218">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-219">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-220">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-220">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b6fc-221">Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="8b6fc-221">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-222">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-223">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-223">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b6fc-224">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="8b6fc-224">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-225">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-226">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-227">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-227">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b6fc-228">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="8b6fc-228">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-229">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-230">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-231">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-232">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-233">Yes1</span><span class="sxs-lookup"><span data-stu-id="8b6fc-233">Yes1</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-234">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-234">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b6fc-235">パブリック IM (AOL、Yahoo!)</span><span class="sxs-lookup"><span data-stu-id="8b6fc-235">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-236">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-237">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-237">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b6fc-238">パブリック IM (MSN、Windows Live Messenger)</span><span class="sxs-lookup"><span data-stu-id="8b6fc-238">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-239">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-239">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-240">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-241">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-242">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-242">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="8b6fc-243">2012年9月1日以降、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス (PIC USL) は、新規または更新契約の購入に使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-243">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="8b6fc-244">アクティブなライセンスを持っているお客様は、Yahoo! とのフェデレーションを継続できます。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-244">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="8b6fc-245">サービスのシャットダウン日までメッセンジャーを終了します。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-245">Messenger until the service shutdown date.</span></span> <span data-ttu-id="8b6fc-246">AOL および Yahoo! の2014年6月の終了日</span><span class="sxs-lookup"><span data-stu-id="8b6fc-246">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="8b6fc-247">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-247">has been announced.</span></span> <span data-ttu-id="8b6fc-248">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-248">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="8b6fc-249">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの1か月間のサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-249">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="8b6fc-250">Messenger.</span><span class="sxs-lookup"><span data-stu-id="8b6fc-250">Messenger.</span></span> <span data-ttu-id="8b6fc-251">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートによって決定されましたが、その基となる契約は更新されません。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-251">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="8b6fc-252">Lync は、組織間、および世界各地の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-252">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="8b6fc-253">Windows Live Messenger とのフェデレーションには、Lync 標準 CAL 以外の追加のユーザー/デバイスライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-253">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="8b6fc-254">Skype federation はこのリストに追加されるため、Lync ユーザーは IM や音声を通じて数百人の何百万ものユーザーに連絡できます。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-254">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="8b6fc-255">1 Office Communicator 2007 R2 では、デスクトップ共有 (プログラムによる共有ではない) のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-255">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b6fc-256">Skype for Business 2015 クライアントのユーザーインターフェイスが適用されている場合、Office Communicator 2007 R2 と Skype for Business 2015 の間のデスクトップ共有を新しいクライアントから開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-256">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="8b6fc-257">Lync Server 2010 会議での Lync 2013 クライアントの会議機能のサポート</span><span class="sxs-lookup"><span data-stu-id="8b6fc-257">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="8b6fc-258">Lync 2013 クライアントを使って Lync Server 2010 会議に参加している場合、lync 2013 クライアントの機能にアクセスできますが、次の例外があります。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-258">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="8b6fc-259">[会議] ウィンドウの [連絡先] アイコンをポイントしてアクセスできる**参加者**の管理オプションでは、[**会議 IM**を使わない] オプションは機能しません。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-259">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="8b6fc-260">ギャラリービューは、ビデオ会議では機能しません。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-260">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="8b6fc-261">ユーザーは、すべてのスピーカーではなく、アクティブなスピーカーのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-261">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="8b6fc-262">[**レイアウトの選択**] オプションの一覧で、**ギャラリービュー**を使用できない</span><span class="sxs-lookup"><span data-stu-id="8b6fc-262">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="8b6fc-263">参加者リストは、ビデオ会議の既定で表示されます。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-263">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="8b6fc-264">[参加者] リストでユーザーを右クリックすると、[**ビデオスポットライトをロック**する] と [**ギャラリーに参加するための Pin** ] オプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-264">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="8b6fc-265">Lync Server 2013 会議での会議機能のサポート</span><span class="sxs-lookup"><span data-stu-id="8b6fc-265">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="8b6fc-266">Lync Server 2013 には、アカウントを Lync Server 2013 に移行した後でユーザーが利用できる新しい会議機能が用意されています。また、lync 2013 クライアントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-266">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="8b6fc-267">例としては、ビデオギャラリービュー、HD ビデオ、PowerPoint 共有、すべての出席者の音声とビデオを会議の入力時にミュートするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-267">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="8b6fc-268">新しい機能については、「 [Lync server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md)」と「 [lync server 2013 でのクライアントの新](lync-server-2013-what-s-new-for-clients.md)機能」で説明しています。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-268">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="8b6fc-269">Lync Server 2013 会議では、特定の会議機能が、さまざまなバージョンのサーバーを使用していて、異なるクライアントとクライアントバージョンを使っているユーザーがサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-269">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="8b6fc-270">クライアントが Lync Server 2013 会議に参加すると、ユーザーは次の表に示す機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-270">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b6fc-271">クライアント</span><span class="sxs-lookup"><span data-stu-id="8b6fc-271">Client</span></span></th>
<th><span data-ttu-id="8b6fc-272">ピアツーピア IM</span><span class="sxs-lookup"><span data-stu-id="8b6fc-272">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="8b6fc-273">音声</span><span class="sxs-lookup"><span data-stu-id="8b6fc-273">Voice</span></span></th>
<th><span data-ttu-id="8b6fc-274">ビデオ</span><span class="sxs-lookup"><span data-stu-id="8b6fc-274">Video</span></span></th>
<th><span data-ttu-id="8b6fc-275">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="8b6fc-275">Application Sharing</span></span></th>
<th><span data-ttu-id="8b6fc-276">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="8b6fc-276">PowerPoint</span></span></th>
<th><span data-ttu-id="8b6fc-277">ファイル送信</span><span class="sxs-lookup"><span data-stu-id="8b6fc-277">File Transfer</span></span></th>
<th><span data-ttu-id="8b6fc-278">Whiteboard</span><span class="sxs-lookup"><span data-stu-id="8b6fc-278">Whiteboard</span></span></th>
<th><span data-ttu-id="8b6fc-279">ポーリング</span><span class="sxs-lookup"><span data-stu-id="8b6fc-279">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b6fc-280">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="8b6fc-280">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-281">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-281">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-282">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-283">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-284">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-285">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-286">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-287">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-288">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-288">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b6fc-289">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="8b6fc-289">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-290">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-291">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-292">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-293">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-294">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-295">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-296">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-297">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-297">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b6fc-298">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="8b6fc-298">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-299">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-299">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-300">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-301">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-302">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-303">Yes2</span><span class="sxs-lookup"><span data-stu-id="8b6fc-303">Yes2</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-304">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-304">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-305">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-306">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-306">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b6fc-307">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="8b6fc-307">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-308">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-309">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-310">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-311">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-312">はい3</span><span class="sxs-lookup"><span data-stu-id="8b6fc-312">Yes3</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-313">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-313">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-314">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-315">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-315">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b6fc-316">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="8b6fc-316">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-317">はい</span><span class="sxs-lookup"><span data-stu-id="8b6fc-317">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8b6fc-318">1 Office Communicator 2007 R2 では、デスクトップ共有 (プログラムによる共有ではない) のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-318">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="8b6fc-319">2 Lync Server 2013 では、PowerPoint ファイルをアップロードするためのメカニズムが更新されています。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-319">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="8b6fc-320">Lync Server 2010 でスケジュールされていた会議に参加した lync Web App ユーザーは、PowerPoint プレゼンテーションを表示したり、移動したりすることはできますが、PowerPoint ファイルをアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-320">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="8b6fc-321">3 lync Server 2013 で会議がスケジュールされていて、PowerPoint スライドが Lync 2013 クライアントによってアップロードされている場合、Lync 2010 ユーザーは、スライドへの表示のみのアクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-321">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="8b6fc-322">これに対して、PowerPoint スライドが Lync 2010 ユーザーによってアップロードされた場合、Lync Server 2013 ユーザーは表示およびスライドにアクセスできます。また、Office Web Apps サーバーが構成されている場合は、高解像度のディスプレイ、アニメーション、スライドの画面切り替えなどの新しい機能にアクセスできます。埋め込みビデオ。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-322">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="8b6fc-323">詳細については、「 [Office Web Apps サーバーおよび Lync server 2013 との統合を構成する](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-323">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="8b6fc-324">4 Office Communicator 2007 R2 のプレゼンス機能と IM 機能は Lync Server 2013 と互換性がありますが、会議機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-324">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="8b6fc-325">Office Communications Server 2007 R2 からの移行中、Office Communicator 2007 R2 はプレゼンスと IM の相互運用性に適していますが、ユーザーは Lync Web App 2013 を使って Lync Server 2013 会議に参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-325">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="8b6fc-326">アドインのサポートのスケジュール</span><span class="sxs-lookup"><span data-stu-id="8b6fc-326">Scheduling Add-in Support</span></span>

<span data-ttu-id="8b6fc-327">各種のスケジュールアドインに対するサーバーのサポートは、サーバーとクライアントのバージョンの互換性と一貫性があります。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-327">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="8b6fc-328">一般的に、次のスケジュールのアドインは Lync Server 2013 でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-328">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="8b6fc-329">ただし、以前のバージョンのアドインでは、会議エントリにあるすべての出席者の音声とビデオをミュートするオプションなどの新しい Lync 2013 アドイン機能は提供されていません。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-329">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="8b6fc-330">**Lync 2013**   用のオンライン会議アドインは、lync 2010 用のオンライン会議アドインと同じ機能を備えており、参加者の音声とビデオがミュートになっている会議のスケジュールを設定することができます。設定.</span><span class="sxs-lookup"><span data-stu-id="8b6fc-330">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="8b6fc-331">管理者は、カスタムロゴ、サポート URL、法的免責事項 URL、またはカスタムフッターテキストを追加して、組織の会議出席依頼をカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-331">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="8b6fc-332">**Lync 2010**   用のオンライン会議アドインは、lync 会議のスケジュールを提供し、Office Live Meeting 会議のスケジュール機能を削除します。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-332">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="8b6fc-333">**Office communicator 2007 R2 会議アドイン**   は、office Live Meeting 会議と office Communicator 2007 R2 会議の両方のスケジュールを提供します。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-333">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="8b6fc-334">Lync Server 2013 で Live Meeting の会議をスケジュールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-334">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b6fc-335">クライアントのスケジュール</span><span class="sxs-lookup"><span data-stu-id="8b6fc-335">Scheduling Client</span></span></th>
<th><span data-ttu-id="8b6fc-336">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b6fc-336">Lync Server 2013</span></span></th>
<th><span data-ttu-id="8b6fc-337">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="8b6fc-337">Lync Server 2010</span></span></th>
<th><span data-ttu-id="8b6fc-338">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="8b6fc-338">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b6fc-339">Lync 2013 用のオンライン会議アドイン (Office 2013、Outlook 2010、Outlook 2007 で使用可能)</span><span class="sxs-lookup"><span data-stu-id="8b6fc-339">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-340">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-340">Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-341">サポートされています (新しいアドイン機能は使用できません)</span><span class="sxs-lookup"><span data-stu-id="8b6fc-341">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-342">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="8b6fc-342">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b6fc-343">Lync 2013 Web Scheduler</span><span class="sxs-lookup"><span data-stu-id="8b6fc-343">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-344">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-344">Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-345">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="8b6fc-345">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-346">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="8b6fc-346">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b6fc-347">Lync 2010 用オンライン ミーティング アドイン</span><span class="sxs-lookup"><span data-stu-id="8b6fc-347">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-348">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-348">Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-349">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-350">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="8b6fc-350">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b6fc-351">Office Communicator 2007 R2 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="8b6fc-351">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-352">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="8b6fc-352">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-353">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-353">Supported</span></span></p></td>
<td><p><span data-ttu-id="8b6fc-354">サポート対象</span><span class="sxs-lookup"><span data-stu-id="8b6fc-354">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="8b6fc-355">会議への参加のサポート</span><span class="sxs-lookup"><span data-stu-id="8b6fc-355">Support for Joining Meetings</span></span>

<span data-ttu-id="8b6fc-356">Lync Server 2013 でサポートされているすべてのクライアントは、Lync 2013 会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-356">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="8b6fc-357">Lync Web App はサーバーの Web コンポーネントであるため、lync Web App を使って Lync Server 2013 会議に参加している場合は、新しいバージョンの Lync Web App が常に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-357">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="8b6fc-358">Lync 2013 クライアントは、スケールダウン機能を使用して、Lync 2010 および Office Communications Server 2007 R2 でホストされている会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-358">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="8b6fc-359">会議中機能は、会議がホストされているサーバーのバージョンによって制限されます。</span><span class="sxs-lookup"><span data-stu-id="8b6fc-359">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8b6fc-360">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b6fc-360">See Also</span></span>


[<span data-ttu-id="8b6fc-361">Lync Server 2013 の lync Windows ストアアプリの要件</span><span class="sxs-lookup"><span data-stu-id="8b6fc-361">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="8b6fc-362">Lync Server 2013 の新しい会議機能</span><span class="sxs-lookup"><span data-stu-id="8b6fc-362">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="8b6fc-363">Lync Server 2013 のクライアント向けの新機能</span><span class="sxs-lookup"><span data-stu-id="8b6fc-363">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

