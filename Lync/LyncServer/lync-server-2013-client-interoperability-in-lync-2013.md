---
title: 'Lync Server 2013: Lync 2013 でのクライアントの相互運用性'
description: 'Lync Server 2013: Lync 2013 でのクライアントの相互運用性。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ea6e90d9479f03dd6d946787e70a2b3cc078699
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549613"
---
# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="f118a-103">Lync 2013 でのクライアントの相互運用性</span><span class="sxs-lookup"><span data-stu-id="f118a-103">Client interoperability in Lync 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f118a-104">_**トピックの最終更新日:** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="f118a-104">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="f118a-105">このトピックでは、Microsoft Lync Server 2013 クライアントが、以前のバージョンの Lync Server および Office Communications Server のクライアントと共存して対話する機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="f118a-105">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="f118a-106">サーバーとクライアントの互換性</span><span class="sxs-lookup"><span data-stu-id="f118a-106">Server and Client Compatibility</span></span>

<span data-ttu-id="f118a-107">次の表に、サポートされるクライアント バージョンとサーバー バージョンの組み合わせを示します。</span><span class="sxs-lookup"><span data-stu-id="f118a-107">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="f118a-108">次の表は、クライアントが指定されたサーバーに接続しようとした場合に、サインインがサポートされるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="f118a-108">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="f118a-109">Lync Server 2013 では、以前のクライアントバージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f118a-109">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="f118a-110">また、以前のリリースとは異なり、Lync Server 2010 は新しい Lync 2013 クライアントをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f118a-110">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="f118a-111">これにより、Lync server 2010 からアップグレードする組織は、Lync Server のアップグレードに関係なく新しいクライアントをロールアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="f118a-111">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f118a-112">クライアント</span><span class="sxs-lookup"><span data-stu-id="f118a-112">Client</span></span></th>
<th><span data-ttu-id="f118a-113">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f118a-113">Lync Server 2013</span></span></th>
<th><span data-ttu-id="f118a-114">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f118a-114">Lync Server 2010</span></span></th>
<th><span data-ttu-id="f118a-115">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="f118a-115">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f118a-116">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="f118a-116">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="f118a-117">サポート</span><span class="sxs-lookup"><span data-stu-id="f118a-117">Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-118">Supported5</span><span class="sxs-lookup"><span data-stu-id="f118a-118">Supported5</span></span></p></td>
<td><p><span data-ttu-id="f118a-119">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="f118a-119">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f118a-120">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="f118a-120">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="f118a-121">サポート</span><span class="sxs-lookup"><span data-stu-id="f118a-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-122">サポートされている</span><span class="sxs-lookup"><span data-stu-id="f118a-122">Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-123">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="f118a-123">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f118a-124">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="f118a-124">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="f118a-125">サポートされている</span><span class="sxs-lookup"><span data-stu-id="f118a-125">Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-126">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="f118a-126">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-127">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="f118a-127">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f118a-128">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="f118a-128">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="f118a-129">サポート</span><span class="sxs-lookup"><span data-stu-id="f118a-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-130">サポートされている</span><span class="sxs-lookup"><span data-stu-id="f118a-130">Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-131">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="f118a-131">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f118a-132">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="f118a-132">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="f118a-133">サポート</span><span class="sxs-lookup"><span data-stu-id="f118a-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-134">サポートされている</span><span class="sxs-lookup"><span data-stu-id="f118a-134">Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-135">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="f118a-135">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f118a-136">Lync 2010 グループ チャット</span><span class="sxs-lookup"><span data-stu-id="f118a-136">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="f118a-137">1</span><span class="sxs-lookup"><span data-stu-id="f118a-137">Supported1</span></span></p></td>
<td><p><span data-ttu-id="f118a-138">Supported2</span><span class="sxs-lookup"><span data-stu-id="f118a-138">Supported2</span></span></p></td>
<td><p><span data-ttu-id="f118a-139">該当なし</span><span class="sxs-lookup"><span data-stu-id="f118a-139">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f118a-140">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="f118a-140">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="f118a-141">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="f118a-141">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-142">サポートされている</span><span class="sxs-lookup"><span data-stu-id="f118a-142">Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-143">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="f118a-143">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f118a-144">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="f118a-144">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="f118a-145">Not Supported3</span><span class="sxs-lookup"><span data-stu-id="f118a-145">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="f118a-146">サポートされている</span><span class="sxs-lookup"><span data-stu-id="f118a-146">Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-147">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="f118a-147">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f118a-148">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="f118a-148">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="f118a-149">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="f118a-149">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="f118a-150">サポート</span><span class="sxs-lookup"><span data-stu-id="f118a-150">Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-151">サポート</span><span class="sxs-lookup"><span data-stu-id="f118a-151">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f118a-152">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="f118a-152">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="f118a-153">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="f118a-153">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-154">サポートされます</span><span class="sxs-lookup"><span data-stu-id="f118a-154">Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-155">サポート</span><span class="sxs-lookup"><span data-stu-id="f118a-155">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f118a-156">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="f118a-156">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="f118a-157">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="f118a-157">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-158">サポートされます</span><span class="sxs-lookup"><span data-stu-id="f118a-158">Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-159">サポート</span><span class="sxs-lookup"><span data-stu-id="f118a-159">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f118a-160">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="f118a-160">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="f118a-161">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="f118a-161">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-162">サポートされます</span><span class="sxs-lookup"><span data-stu-id="f118a-162">Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-163">サポート</span><span class="sxs-lookup"><span data-stu-id="f118a-163">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f118a-164">Lync Windows ストアアプリ</span><span class="sxs-lookup"><span data-stu-id="f118a-164">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="f118a-165">サポート</span><span class="sxs-lookup"><span data-stu-id="f118a-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-166">サポートされている</span><span class="sxs-lookup"><span data-stu-id="f118a-166">Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-167">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="f118a-167">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f118a-168">1For については、「 [Lync server 2010、グループチャットまたは Office Communications server 2007 R2 グループチャットから Lync server 2013、常設チャットサーバーへの移行](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f118a-168">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="f118a-169">2In Lync Server 2010 では、グループチャットの機能は、Lync Server 2010 用のサードパーティの信頼されたアプリケーションであるグループチャットサーバーで利用できました。</span><span class="sxs-lookup"><span data-stu-id="f118a-169">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="f118a-170">Lync 2013 クライアントは、Lync Server 2010、グループチャットと互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="f118a-170">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="f118a-171">3Lync Web App 2013 には、コンピューターの音声とビデオを含む完全な会議環境が提供されており、Lync 2010 の出席者に代わるものと見なされています。</span><span class="sxs-lookup"><span data-stu-id="f118a-171">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="f118a-172">Lync 2010 出席者は、サポートされていないブラウザー (Internet Explorer 6 または Internet Explorer 7) および Windows XP を使用している場合にのみ Lync Server 2013 に接続します。</span><span class="sxs-lookup"><span data-stu-id="f118a-172">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="f118a-173">4The Communicator 2007 R2 のプレゼンスおよび IM 機能は Lync Server 2013 と互換性がありますが、会議機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f118a-173">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="f118a-174">Office Communications Server 2007 R2 からの移行時に、Office Communicator 2007 R2 はプレゼンスおよび IM の相互運用性に適していますが、ユーザーは lync Server の2013会議に参加するために Lync Web App 2013 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f118a-174">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="f118a-175">5制限については、このトピックの後の「Lync Server 2010 会議での Lync 2013 クライアントの会議機能のサポート」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f118a-175">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="f118a-176">クライアント間の相互運用性</span><span class="sxs-lookup"><span data-stu-id="f118a-176">Interoperability among Clients</span></span>

<span data-ttu-id="f118a-177">Lync Server 2013 リリースでは、さまざまなクライアントバージョンがピアツーピアおよび電話会議の両方のシナリオでシームレスに対話できます。</span><span class="sxs-lookup"><span data-stu-id="f118a-177">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="f118a-178">このセクションでは、別のバージョンのクライアントやサーバーを使用しているユーザーとやり取りするときに利用できる機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="f118a-178">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="f118a-179">ピアツーピア機能のサポート</span><span class="sxs-lookup"><span data-stu-id="f118a-179">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="f118a-p106">ピアツーピア機能は、さまざまなバージョンのサーバーに所属するユーザーや、さまざまなクライアント バージョンを使用するユーザー向けにサポートされています。エンド ユーザー エクスペリエンスと使用できる機能は、ユーザーのクライアントの機能と、ユーザーがサインインするサーバーのバージョンに準じます。つまり、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f118a-p106">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions. The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to. In other words:</span></span>

  - <span data-ttu-id="f118a-183">以前のクライアントを使用して Lync Server 2013 にサインインしている場合、そのユーザーはと同じ操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f118a-183">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="f118a-184">Lync Server 2013 で導入された新機能は、ユーザーのクライアントがアップグレードされるまで使用できません。</span><span class="sxs-lookup"><span data-stu-id="f118a-184">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="f118a-185">例としては、ビデオギャラリービュー、HD ビデオ、更新された PowerPoint 共有、会議エントリ時にすべての参加者の音声とビデオをミュートするオプションなどがあります。</span><span class="sxs-lookup"><span data-stu-id="f118a-185">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="f118a-186">新しい機能については、「 [Lync server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md) 」と「 [lync server 2013 のクライアント向けの新](lync-server-2013-what-s-new-for-clients.md)機能」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="f118a-186">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="f118a-187">Lync 2013 クライアントで Lync Server 2010 にサインインしている場合、lync server 2010 でサポートされていないすべての新機能は、ユーザーが Lync Server 2013 に移行されるまで使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f118a-187">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="f118a-188">次の表では、クライアントが Lync Server 2013 または Lync Server 2010 のどちらかにサインインしているピアツーピアセッションでの機能の可用性を比較します。</span><span class="sxs-lookup"><span data-stu-id="f118a-188">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f118a-189">Lync Web App および Lync 2010 の出席者は、会議専用クライアントであり、この表には含まれていません。</span><span class="sxs-lookup"><span data-stu-id="f118a-189">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



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
<th><span data-ttu-id="f118a-190">クライアント</span><span class="sxs-lookup"><span data-stu-id="f118a-190">Client</span></span></th>
<th><span data-ttu-id="f118a-191">インスタント メッセージング</span><span class="sxs-lookup"><span data-stu-id="f118a-191">Instant Messaging</span></span></th>
<th><span data-ttu-id="f118a-192">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="f118a-192">Presence</span></span></th>
<th><span data-ttu-id="f118a-193">音声</span><span class="sxs-lookup"><span data-stu-id="f118a-193">Voice</span></span></th>
<th><span data-ttu-id="f118a-194">ビデオ</span><span class="sxs-lookup"><span data-stu-id="f118a-194">Video</span></span></th>
<th><span data-ttu-id="f118a-195">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="f118a-195">Application Sharing</span></span></th>
<th><span data-ttu-id="f118a-196">ファイル送信</span><span class="sxs-lookup"><span data-stu-id="f118a-196">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f118a-197">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="f118a-197">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="f118a-198">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-199">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-200">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-201">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-202">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-203">必要</span><span class="sxs-lookup"><span data-stu-id="f118a-203">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f118a-204">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="f118a-204">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="f118a-205">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-206">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-207">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-208">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-209">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-210">必要</span><span class="sxs-lookup"><span data-stu-id="f118a-210">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f118a-211">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="f118a-211">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="f118a-212">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-213">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-214">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-215">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-216">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-217">必要</span><span class="sxs-lookup"><span data-stu-id="f118a-217">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f118a-218">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="f118a-218">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="f118a-219">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-220">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-220">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-221">必要</span><span class="sxs-lookup"><span data-stu-id="f118a-221">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f118a-222">Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="f118a-222">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="f118a-223">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-224">必要</span><span class="sxs-lookup"><span data-stu-id="f118a-224">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f118a-225">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="f118a-225">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="f118a-226">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-227">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-227">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-228">必要</span><span class="sxs-lookup"><span data-stu-id="f118a-228">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f118a-229">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="f118a-229">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="f118a-230">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-231">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-232">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-233">必要</span><span class="sxs-lookup"><span data-stu-id="f118a-233">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-234">はい1</span><span class="sxs-lookup"><span data-stu-id="f118a-234">Yes1</span></span></p></td>
<td><p><span data-ttu-id="f118a-235">必要</span><span class="sxs-lookup"><span data-stu-id="f118a-235">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f118a-236">パブリック IM (AOL、Yahoo!)</span><span class="sxs-lookup"><span data-stu-id="f118a-236">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="f118a-237">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-237">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-238">必要</span><span class="sxs-lookup"><span data-stu-id="f118a-238">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f118a-239">パブリック IM (MSN、Windows Live Messenger)</span><span class="sxs-lookup"><span data-stu-id="f118a-239">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="f118a-240">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-241">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-242">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-242">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-243">必要</span><span class="sxs-lookup"><span data-stu-id="f118a-243">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="f118a-244">2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス (PIC USL) は、新規購入または更新契約の購入に使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f118a-244">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="f118a-245">アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。</span><span class="sxs-lookup"><span data-stu-id="f118a-245">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="f118a-246">サービスの終了日までの Messenger。</span><span class="sxs-lookup"><span data-stu-id="f118a-246">Messenger until the service shutdown date.</span></span> <span data-ttu-id="f118a-247">AOL および Yahoo! の2014年6月の寿命の終了日</span><span class="sxs-lookup"><span data-stu-id="f118a-247">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="f118a-248">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="f118a-248">has been announced.</span></span> <span data-ttu-id="f118a-249">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f118a-249">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="f118a-250">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの1か月あたりのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="f118a-250">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="f118a-251">Messenger.</span><span class="sxs-lookup"><span data-stu-id="f118a-251">Messenger.</span></span> <span data-ttu-id="f118a-252">このサービスを提供する Microsoft の機能は、Yahoo! からのサポートを受けています。これは、更新されない基になる契約です。</span><span class="sxs-lookup"><span data-stu-id="f118a-252">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="f118a-253">Lync は、組織間や世界中の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="f118a-253">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="f118a-254">Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f118a-254">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="f118a-255">Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を通じて数十万のユーザーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="f118a-255">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="f118a-256">1 Office Communicator 2007 R2 では、デスクトップ共有のみ (プログラム共有は不可) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f118a-256">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f118a-257">Skype for Business 2015 クライアントユーザーインターフェイスが適用されている場合、Office Communicator 2007 R2 と Skype for Business 2015 間のデスクトップ共有を新しいクライアントから開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="f118a-257">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="f118a-258">Lync Server 2010 での Lync 2013 クライアントの会議機能のサポート</span><span class="sxs-lookup"><span data-stu-id="f118a-258">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="f118a-259">ユーザーが lync Server 2010 会議に Lync 2013 クライアントを参加させると、次の例外を除き、Lync 2013 クライアント機能にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="f118a-259">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="f118a-260">[ **参加者** の管理] オプションでは、会議ウィンドウの [ユーザー] アイコンをポイントすることによってアクセスできます。 [ **会議 IM** を利用しない] オプションは機能しません。</span><span class="sxs-lookup"><span data-stu-id="f118a-260">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="f118a-261">ギャラリービューは、ビデオ会議では機能しません。</span><span class="sxs-lookup"><span data-stu-id="f118a-261">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="f118a-262">ユーザーには、すべてのスピーカーではなく、アクティブなスピーカーのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f118a-262">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="f118a-263">[レイアウトオプションの **選択** ] の一覧で、 **ギャラリービュー** を使用できません</span><span class="sxs-lookup"><span data-stu-id="f118a-263">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="f118a-264">参加者リストは、既定では、ビデオ会議に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f118a-264">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="f118a-265">[参加者] リストでユーザーを右クリックすると、[ **ビデオスポットライトをロック** する] および [ギャラリー参加者管理 **にピン留めする** ] オプションが使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f118a-265">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="f118a-266">Lync Server 2013 会議での会議機能のサポート</span><span class="sxs-lookup"><span data-stu-id="f118a-266">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="f118a-267">Lync Server 2013 は、アカウントが Lync Server 2013 に移動され、Lync 2013 クライアントを使用してサインインした後で、ユーザーが利用できるようになる新しい会議機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="f118a-267">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="f118a-268">例としては、ビデオギャラリービュー、HD ビデオ、PowerPoint 共有、会議エントリ時にすべての参加者の音声とビデオをミュートするオプションなどがあります。</span><span class="sxs-lookup"><span data-stu-id="f118a-268">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="f118a-269">新しい機能については、「 [Lync server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md) 」と「 [lync server 2013 のクライアント向けの新](lync-server-2013-what-s-new-for-clients.md)機能」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="f118a-269">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="f118a-270">Lync Server 2013 の会議では、さまざまなバージョンのサーバーに所属しており、異なるクライアントとクライアントバージョンを使用しているユーザーが、特定の会議機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f118a-270">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="f118a-271">クライアントが Lync Server 2013 会議に参加すると、ユーザーはこの表に示されている機能にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="f118a-271">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


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
<th><span data-ttu-id="f118a-272">クライアント</span><span class="sxs-lookup"><span data-stu-id="f118a-272">Client</span></span></th>
<th><span data-ttu-id="f118a-273">ピアツーピア IM</span><span class="sxs-lookup"><span data-stu-id="f118a-273">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="f118a-274">音声</span><span class="sxs-lookup"><span data-stu-id="f118a-274">Voice</span></span></th>
<th><span data-ttu-id="f118a-275">ビデオ</span><span class="sxs-lookup"><span data-stu-id="f118a-275">Video</span></span></th>
<th><span data-ttu-id="f118a-276">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="f118a-276">Application Sharing</span></span></th>
<th><span data-ttu-id="f118a-277">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f118a-277">PowerPoint</span></span></th>
<th><span data-ttu-id="f118a-278">ファイル送信</span><span class="sxs-lookup"><span data-stu-id="f118a-278">File Transfer</span></span></th>
<th><span data-ttu-id="f118a-279">Whiteboard</span><span class="sxs-lookup"><span data-stu-id="f118a-279">Whiteboard</span></span></th>
<th><span data-ttu-id="f118a-280">投票</span><span class="sxs-lookup"><span data-stu-id="f118a-280">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f118a-281">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="f118a-281">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="f118a-282">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-283">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-284">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-285">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-286">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-287">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-288">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-288">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-289">必要</span><span class="sxs-lookup"><span data-stu-id="f118a-289">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f118a-290">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="f118a-290">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="f118a-291">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-292">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-293">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-294">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-295">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-296">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-297">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-297">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-298">必要</span><span class="sxs-lookup"><span data-stu-id="f118a-298">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f118a-299">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="f118a-299">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="f118a-300">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-301">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-302">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-303">必要</span><span class="sxs-lookup"><span data-stu-id="f118a-303">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-304">はい2</span><span class="sxs-lookup"><span data-stu-id="f118a-304">Yes2</span></span></p></td>
<td><p><span data-ttu-id="f118a-305">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-306">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-306">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-307">必要</span><span class="sxs-lookup"><span data-stu-id="f118a-307">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f118a-308">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="f118a-308">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="f118a-309">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-310">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-311">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-312">必要</span><span class="sxs-lookup"><span data-stu-id="f118a-312">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-313">はい3</span><span class="sxs-lookup"><span data-stu-id="f118a-313">Yes3</span></span></p></td>
<td><p><span data-ttu-id="f118a-314">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-315">はい</span><span class="sxs-lookup"><span data-stu-id="f118a-315">Yes</span></span></p></td>
<td><p><span data-ttu-id="f118a-316">必要</span><span class="sxs-lookup"><span data-stu-id="f118a-316">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f118a-317">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="f118a-317">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="f118a-318">必要</span><span class="sxs-lookup"><span data-stu-id="f118a-318">Yes</span></span></p></td>
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


<span data-ttu-id="f118a-319">1 Office Communicator 2007 R2 では、デスクトップ共有のみ (プログラム共有は不可) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f118a-319">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="f118a-320">2 Lync Server 2013 は、PowerPoint ファイルをアップロードするための更新されたメカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="f118a-320">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="f118a-321">Lync Server 2010 で最初に予約された会議に参加している lync Web App ユーザーは、PowerPoint プレゼンテーションを表示して移動することはできますが、PowerPoint ファイルをアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f118a-321">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="f118a-322">3 Lync Server 2013 で会議がスケジュールされており、PowerPoint スライドが Lync 2013 クライアントによってアップロードされている場合、Lync 2010 ユーザーはスライドに対して表示専用のアクセス権を持ちます。</span><span class="sxs-lookup"><span data-stu-id="f118a-322">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="f118a-323">反対に、PowerPoint スライドが Lync 2010 ユーザーによってアップロードされている場合、Lync Server 2013 ユーザーは表示やスライドの表示が可能で、Office Web Apps サーバーが構成されていれば、高解像度の表示、アニメーション、画面切り替え、埋め込みビデオなどの新しい機能にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="f118a-323">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="f118a-324">詳細については、「 [Office Web Apps Server および Lync Server 2013 との統合の構成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f118a-324">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="f118a-325">4The Communicator 2007 R2 のプレゼンスおよび IM 機能は Lync Server 2013 と互換性がありますが、会議機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f118a-325">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="f118a-326">Office Communications Server 2007 R2 からの移行時に、Office Communicator 2007 R2 はプレゼンスおよび IM の相互運用性に適していますが、ユーザーは lync Server の2013会議に参加するために Lync Web App 2013 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f118a-326">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="f118a-327">スケジュールのアドインのサポート</span><span class="sxs-lookup"><span data-stu-id="f118a-327">Scheduling Add-in Support</span></span>

<span data-ttu-id="f118a-328">スケジュールのさまざまなアドインに対するサーバーのサポートは、サーバーとクライアントのバージョンの互換性に準じます。</span><span class="sxs-lookup"><span data-stu-id="f118a-328">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="f118a-329">一般に、Lync Server 2013 では、次のスケジュール設定アドインがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f118a-329">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="f118a-330">ただし、以前のバージョンのアドインでは、会議の入力時にすべての参加者の音声とビデオをミュートするオプションなど、Lync 2013 アドインの新しい機能は提供されません。</span><span class="sxs-lookup"><span data-stu-id="f118a-330">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="f118a-331">**Lync 2013**     用オンラインミーティングアドインLync 2010 用のオンライン会議アドインと同じ機能を提供します。参加者のミュートコントロールを追加すると、会議の開催者は参加者の音声とビデオが既定でミュートされた会議をスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="f118a-331">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="f118a-332">管理者は、カスタムのロゴ、サポート URL、法的免責事項 URL、またはカスタムのフッター テキストを追加して、組織の会議出席依頼をカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f118a-332">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="f118a-333">**Lync 2010**     用オンラインミーティングアドインLync 会議のスケジュールを提供し、Office Live Meeting 会議をスケジュールする機能を削除します。</span><span class="sxs-lookup"><span data-stu-id="f118a-333">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="f118a-334">**Office Communicator 2007 R2 会議アドイン**    Office Live Meeting 会議と Office Communicator 2007 R2 会議の両方のスケジュールを提供します。</span><span class="sxs-lookup"><span data-stu-id="f118a-334">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="f118a-335">Live Meeting 会議を Lync Server 2013 でスケジュールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f118a-335">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



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
<th><span data-ttu-id="f118a-336">スケジュール クライアント</span><span class="sxs-lookup"><span data-stu-id="f118a-336">Scheduling Client</span></span></th>
<th><span data-ttu-id="f118a-337">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f118a-337">Lync Server 2013</span></span></th>
<th><span data-ttu-id="f118a-338">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f118a-338">Lync Server 2010</span></span></th>
<th><span data-ttu-id="f118a-339">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="f118a-339">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f118a-340">Lync 2013 用オンラインミーティングアドイン (Office 2013、Outlook 2010、および Outlook 2007 で使用できます)</span><span class="sxs-lookup"><span data-stu-id="f118a-340">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="f118a-341">サポート</span><span class="sxs-lookup"><span data-stu-id="f118a-341">Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-342">サポート対象 (新しいアドイン機能は使用不可)</span><span class="sxs-lookup"><span data-stu-id="f118a-342">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="f118a-343">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="f118a-343">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f118a-344">Lync 2013 Web Scheduler</span><span class="sxs-lookup"><span data-stu-id="f118a-344">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="f118a-345">サポートされている</span><span class="sxs-lookup"><span data-stu-id="f118a-345">Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-346">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="f118a-346">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-347">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="f118a-347">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f118a-348">Online Meeting Add-in for Lync 2010</span><span class="sxs-lookup"><span data-stu-id="f118a-348">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="f118a-349">サポート</span><span class="sxs-lookup"><span data-stu-id="f118a-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-350">サポートされている</span><span class="sxs-lookup"><span data-stu-id="f118a-350">Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-351">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="f118a-351">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f118a-352">Office Communicator 2007 R2 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="f118a-352">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="f118a-353">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="f118a-353">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-354">サポートされます</span><span class="sxs-lookup"><span data-stu-id="f118a-354">Supported</span></span></p></td>
<td><p><span data-ttu-id="f118a-355">サポート</span><span class="sxs-lookup"><span data-stu-id="f118a-355">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="f118a-356">会議参加のサポート</span><span class="sxs-lookup"><span data-stu-id="f118a-356">Support for Joining Meetings</span></span>

<span data-ttu-id="f118a-357">Lync Server 2013 がサポートするすべてのクライアントは、Lync 2013 会議への参加を許可されます。</span><span class="sxs-lookup"><span data-stu-id="f118a-357">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="f118a-358">Lync web app はサーバーの web コンポーネントであるため、lync Web App を使用して Lync Server 2013 会議に参加している場合は、新しいバージョンの Lync Web App が常に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f118a-358">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="f118a-359">Lync 2013 クライアントは、拡張機能を使用して Lync 2010 および Office Communications Server 2007 R2 でホストされている会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="f118a-359">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="f118a-360">会議参加機能は、会議がホストされるサーバーのバージョンによって制限されます。</span><span class="sxs-lookup"><span data-stu-id="f118a-360">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f118a-361">関連項目</span><span class="sxs-lookup"><span data-stu-id="f118a-361">See Also</span></span>


[<span data-ttu-id="f118a-362">Lync Server 2013 の lync Windows ストアアプリの要件</span><span class="sxs-lookup"><span data-stu-id="f118a-362">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="f118a-363">Lync Server 2013 の新しい会議機能</span><span class="sxs-lookup"><span data-stu-id="f118a-363">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="f118a-364">Lync Server 2013 のクライアントの新機能</span><span class="sxs-lookup"><span data-stu-id="f118a-364">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

