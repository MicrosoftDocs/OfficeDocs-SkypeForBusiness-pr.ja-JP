---
title: 'Lync Server 2013: Lync 2013 でのクライアントの相互運用性'
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
ms.openlocfilehash: 2e00071edd4a3d65e9db763914577983306491fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502674"
---
# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="19929-102">Lync 2013 でのクライアントの相互運用性</span><span class="sxs-lookup"><span data-stu-id="19929-102">Client interoperability in Lync 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19929-103">_**トピックの最終更新日:** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="19929-103">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="19929-104">このトピックでは、Microsoft Lync Server 2013 クライアントが、以前のバージョンの Lync Server および Office Communications Server のクライアントと共存して対話する機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="19929-104">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="19929-105">サーバーとクライアントの互換性</span><span class="sxs-lookup"><span data-stu-id="19929-105">Server and Client Compatibility</span></span>

<span data-ttu-id="19929-106">次の表に、サポートされるクライアント バージョンとサーバー バージョンの組み合わせを示します。</span><span class="sxs-lookup"><span data-stu-id="19929-106">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="19929-107">次の表は、クライアントが指定されたサーバーに接続しようとした場合に、サインインがサポートされるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="19929-107">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="19929-108">Lync Server 2013 では、以前のクライアントバージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="19929-108">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="19929-109">また、以前のリリースとは異なり、Lync Server 2010 は新しい Lync 2013 クライアントをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="19929-109">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="19929-110">これにより、Lync server 2010 からアップグレードする組織は、Lync Server のアップグレードに関係なく新しいクライアントをロールアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="19929-110">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19929-111">クライアント</span><span class="sxs-lookup"><span data-stu-id="19929-111">Client</span></span></th>
<th><span data-ttu-id="19929-112">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19929-112">Lync Server 2013</span></span></th>
<th><span data-ttu-id="19929-113">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="19929-113">Lync Server 2010</span></span></th>
<th><span data-ttu-id="19929-114">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="19929-114">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19929-115">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="19929-115">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="19929-116">サポート</span><span class="sxs-lookup"><span data-stu-id="19929-116">Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-117">Supported5</span><span class="sxs-lookup"><span data-stu-id="19929-117">Supported5</span></span></p></td>
<td><p><span data-ttu-id="19929-118">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="19929-118">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19929-119">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="19929-119">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="19929-120">サポート</span><span class="sxs-lookup"><span data-stu-id="19929-120">Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-121">サポートされている</span><span class="sxs-lookup"><span data-stu-id="19929-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-122">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="19929-122">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19929-123">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="19929-123">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="19929-124">サポートされている</span><span class="sxs-lookup"><span data-stu-id="19929-124">Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-125">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="19929-125">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-126">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="19929-126">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19929-127">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="19929-127">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="19929-128">サポート</span><span class="sxs-lookup"><span data-stu-id="19929-128">Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-129">サポートされている</span><span class="sxs-lookup"><span data-stu-id="19929-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-130">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="19929-130">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19929-131">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="19929-131">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="19929-132">サポート</span><span class="sxs-lookup"><span data-stu-id="19929-132">Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-133">サポートされている</span><span class="sxs-lookup"><span data-stu-id="19929-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-134">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="19929-134">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19929-135">Lync 2010 グループ チャット</span><span class="sxs-lookup"><span data-stu-id="19929-135">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="19929-136">1</span><span class="sxs-lookup"><span data-stu-id="19929-136">Supported1</span></span></p></td>
<td><p><span data-ttu-id="19929-137">Supported2</span><span class="sxs-lookup"><span data-stu-id="19929-137">Supported2</span></span></p></td>
<td><p><span data-ttu-id="19929-138">該当なし</span><span class="sxs-lookup"><span data-stu-id="19929-138">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19929-139">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="19929-139">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="19929-140">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="19929-140">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-141">サポートされている</span><span class="sxs-lookup"><span data-stu-id="19929-141">Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-142">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="19929-142">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19929-143">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="19929-143">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="19929-144">Not Supported3</span><span class="sxs-lookup"><span data-stu-id="19929-144">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="19929-145">サポートされている</span><span class="sxs-lookup"><span data-stu-id="19929-145">Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-146">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="19929-146">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19929-147">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="19929-147">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="19929-148">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="19929-148">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="19929-149">サポート</span><span class="sxs-lookup"><span data-stu-id="19929-149">Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-150">サポート</span><span class="sxs-lookup"><span data-stu-id="19929-150">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19929-151">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="19929-151">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="19929-152">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="19929-152">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-153">サポートされます</span><span class="sxs-lookup"><span data-stu-id="19929-153">Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-154">サポート</span><span class="sxs-lookup"><span data-stu-id="19929-154">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19929-155">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="19929-155">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="19929-156">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="19929-156">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-157">サポートされます</span><span class="sxs-lookup"><span data-stu-id="19929-157">Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-158">サポート</span><span class="sxs-lookup"><span data-stu-id="19929-158">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19929-159">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="19929-159">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="19929-160">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="19929-160">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-161">サポートされます</span><span class="sxs-lookup"><span data-stu-id="19929-161">Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-162">サポート</span><span class="sxs-lookup"><span data-stu-id="19929-162">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19929-163">Lync Windows ストアアプリ</span><span class="sxs-lookup"><span data-stu-id="19929-163">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="19929-164">サポート</span><span class="sxs-lookup"><span data-stu-id="19929-164">Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-165">サポートされている</span><span class="sxs-lookup"><span data-stu-id="19929-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-166">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="19929-166">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="19929-167">1For については、「 [Lync server 2010、グループチャットまたは Office Communications server 2007 R2 グループチャットから Lync server 2013、常設チャットサーバーへの移行](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19929-167">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="19929-168">2In Lync Server 2010 では、グループチャットの機能は、Lync Server 2010 用のサードパーティの信頼されたアプリケーションであるグループチャットサーバーで利用できました。</span><span class="sxs-lookup"><span data-stu-id="19929-168">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="19929-169">Lync 2013 クライアントは、Lync Server 2010、グループチャットと互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="19929-169">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="19929-170">3Lync Web App 2013 には、コンピューターの音声とビデオを含む完全な会議環境が提供されており、Lync 2010 の出席者に代わるものと見なされています。</span><span class="sxs-lookup"><span data-stu-id="19929-170">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="19929-171">Lync 2010 出席者は、サポートされていないブラウザー (Internet Explorer 6 または Internet Explorer 7) および Windows XP を使用している場合にのみ Lync Server 2013 に接続します。</span><span class="sxs-lookup"><span data-stu-id="19929-171">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="19929-172">4The Communicator 2007 R2 のプレゼンスおよび IM 機能は Lync Server 2013 と互換性がありますが、会議機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="19929-172">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="19929-173">Office Communications Server 2007 R2 からの移行時に、Office Communicator 2007 R2 はプレゼンスおよび IM の相互運用性に適していますが、ユーザーは lync Server の2013会議に参加するために Lync Web App 2013 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19929-173">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="19929-174">5制限については、このトピックの後の「Lync Server 2010 会議での Lync 2013 クライアントの会議機能のサポート」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19929-174">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="19929-175">クライアント間の相互運用性</span><span class="sxs-lookup"><span data-stu-id="19929-175">Interoperability among Clients</span></span>

<span data-ttu-id="19929-176">Lync Server 2013 リリースでは、さまざまなクライアントバージョンがピアツーピアおよび電話会議の両方のシナリオでシームレスに対話できます。</span><span class="sxs-lookup"><span data-stu-id="19929-176">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="19929-177">このセクションでは、別のバージョンのクライアントやサーバーを使用しているユーザーとやり取りするときに利用できる機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="19929-177">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="19929-178">ピアツーピア機能のサポート</span><span class="sxs-lookup"><span data-stu-id="19929-178">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="19929-p106">ピアツーピア機能は、さまざまなバージョンのサーバーに所属するユーザーや、さまざまなクライアント バージョンを使用するユーザー向けにサポートされています。エンド ユーザー エクスペリエンスと使用できる機能は、ユーザーのクライアントの機能と、ユーザーがサインインするサーバーのバージョンに準じます。つまり、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="19929-p106">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions. The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to. In other words:</span></span>

  - <span data-ttu-id="19929-182">以前のクライアントを使用して Lync Server 2013 にサインインしている場合、そのユーザーはと同じ操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="19929-182">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="19929-183">Lync Server 2013 で導入された新機能は、ユーザーのクライアントがアップグレードされるまで使用できません。</span><span class="sxs-lookup"><span data-stu-id="19929-183">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="19929-184">例としては、ビデオギャラリービュー、HD ビデオ、更新された PowerPoint 共有、会議エントリ時にすべての参加者の音声とビデオをミュートするオプションなどがあります。</span><span class="sxs-lookup"><span data-stu-id="19929-184">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="19929-185">新しい機能については、「 [Lync server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md) 」と「 [lync server 2013 のクライアント向けの新](lync-server-2013-what-s-new-for-clients.md)機能」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="19929-185">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="19929-186">Lync 2013 クライアントで Lync Server 2010 にサインインしている場合、lync server 2010 でサポートされていないすべての新機能は、ユーザーが Lync Server 2013 に移行されるまで使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="19929-186">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="19929-187">次の表では、クライアントが Lync Server 2013 または Lync Server 2010 のどちらかにサインインしているピアツーピアセッションでの機能の可用性を比較します。</span><span class="sxs-lookup"><span data-stu-id="19929-187">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="19929-188">Lync Web App および Lync 2010 の出席者は、会議専用クライアントであり、この表には含まれていません。</span><span class="sxs-lookup"><span data-stu-id="19929-188">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



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
<th><span data-ttu-id="19929-189">クライアント</span><span class="sxs-lookup"><span data-stu-id="19929-189">Client</span></span></th>
<th><span data-ttu-id="19929-190">インスタント メッセージング</span><span class="sxs-lookup"><span data-stu-id="19929-190">Instant Messaging</span></span></th>
<th><span data-ttu-id="19929-191">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="19929-191">Presence</span></span></th>
<th><span data-ttu-id="19929-192">音声</span><span class="sxs-lookup"><span data-stu-id="19929-192">Voice</span></span></th>
<th><span data-ttu-id="19929-193">ビデオ</span><span class="sxs-lookup"><span data-stu-id="19929-193">Video</span></span></th>
<th><span data-ttu-id="19929-194">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="19929-194">Application Sharing</span></span></th>
<th><span data-ttu-id="19929-195">ファイル送信</span><span class="sxs-lookup"><span data-stu-id="19929-195">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19929-196">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="19929-196">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="19929-197">はい</span><span class="sxs-lookup"><span data-stu-id="19929-197">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-198">はい</span><span class="sxs-lookup"><span data-stu-id="19929-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-199">はい</span><span class="sxs-lookup"><span data-stu-id="19929-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-200">はい</span><span class="sxs-lookup"><span data-stu-id="19929-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-201">はい</span><span class="sxs-lookup"><span data-stu-id="19929-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-202">必要</span><span class="sxs-lookup"><span data-stu-id="19929-202">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19929-203">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="19929-203">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="19929-204">はい</span><span class="sxs-lookup"><span data-stu-id="19929-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-205">はい</span><span class="sxs-lookup"><span data-stu-id="19929-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-206">はい</span><span class="sxs-lookup"><span data-stu-id="19929-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-207">はい</span><span class="sxs-lookup"><span data-stu-id="19929-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-208">はい</span><span class="sxs-lookup"><span data-stu-id="19929-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-209">必要</span><span class="sxs-lookup"><span data-stu-id="19929-209">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19929-210">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="19929-210">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="19929-211">はい</span><span class="sxs-lookup"><span data-stu-id="19929-211">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-212">はい</span><span class="sxs-lookup"><span data-stu-id="19929-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-213">はい</span><span class="sxs-lookup"><span data-stu-id="19929-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-214">はい</span><span class="sxs-lookup"><span data-stu-id="19929-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-215">はい</span><span class="sxs-lookup"><span data-stu-id="19929-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-216">必要</span><span class="sxs-lookup"><span data-stu-id="19929-216">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19929-217">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="19929-217">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="19929-218">はい</span><span class="sxs-lookup"><span data-stu-id="19929-218">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-219">はい</span><span class="sxs-lookup"><span data-stu-id="19929-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-220">必要</span><span class="sxs-lookup"><span data-stu-id="19929-220">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19929-221">Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="19929-221">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="19929-222">はい</span><span class="sxs-lookup"><span data-stu-id="19929-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-223">必要</span><span class="sxs-lookup"><span data-stu-id="19929-223">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19929-224">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="19929-224">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="19929-225">はい</span><span class="sxs-lookup"><span data-stu-id="19929-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-226">はい</span><span class="sxs-lookup"><span data-stu-id="19929-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-227">必要</span><span class="sxs-lookup"><span data-stu-id="19929-227">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19929-228">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="19929-228">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="19929-229">はい</span><span class="sxs-lookup"><span data-stu-id="19929-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-230">はい</span><span class="sxs-lookup"><span data-stu-id="19929-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-231">はい</span><span class="sxs-lookup"><span data-stu-id="19929-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-232">必要</span><span class="sxs-lookup"><span data-stu-id="19929-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-233">はい1</span><span class="sxs-lookup"><span data-stu-id="19929-233">Yes1</span></span></p></td>
<td><p><span data-ttu-id="19929-234">必要</span><span class="sxs-lookup"><span data-stu-id="19929-234">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19929-235">パブリック IM (AOL、Yahoo!)</span><span class="sxs-lookup"><span data-stu-id="19929-235">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="19929-236">はい</span><span class="sxs-lookup"><span data-stu-id="19929-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-237">必要</span><span class="sxs-lookup"><span data-stu-id="19929-237">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19929-238">パブリック IM (MSN、Windows Live Messenger)</span><span class="sxs-lookup"><span data-stu-id="19929-238">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="19929-239">はい</span><span class="sxs-lookup"><span data-stu-id="19929-239">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-240">はい</span><span class="sxs-lookup"><span data-stu-id="19929-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-241">はい</span><span class="sxs-lookup"><span data-stu-id="19929-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-242">必要</span><span class="sxs-lookup"><span data-stu-id="19929-242">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="19929-243">2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス (PIC USL) は、新規購入または更新契約の購入に使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="19929-243">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="19929-244">アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。</span><span class="sxs-lookup"><span data-stu-id="19929-244">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="19929-245">サービスの終了日までの Messenger。</span><span class="sxs-lookup"><span data-stu-id="19929-245">Messenger until the service shutdown date.</span></span> <span data-ttu-id="19929-246">AOL および Yahoo! の2014年6月の寿命の終了日</span><span class="sxs-lookup"><span data-stu-id="19929-246">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="19929-247">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="19929-247">has been announced.</span></span> <span data-ttu-id="19929-248">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19929-248">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="19929-249">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの1か月あたりのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="19929-249">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="19929-250">Messenger.</span><span class="sxs-lookup"><span data-stu-id="19929-250">Messenger.</span></span> <span data-ttu-id="19929-251">このサービスを提供する Microsoft の機能は、Yahoo! からのサポートを受けています。これは、更新されない基になる契約です。</span><span class="sxs-lookup"><span data-stu-id="19929-251">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="19929-252">Lync は、組織間や世界中の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="19929-252">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="19929-253">Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="19929-253">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="19929-254">Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を通じて数十万のユーザーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="19929-254">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="19929-255">1 Office Communicator 2007 R2 では、デスクトップ共有のみ (プログラム共有は不可) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="19929-255">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="19929-256">Skype for Business 2015 クライアントユーザーインターフェイスが適用されている場合、Office Communicator 2007 R2 と Skype for Business 2015 間のデスクトップ共有を新しいクライアントから開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="19929-256">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="19929-257">Lync Server 2010 での Lync 2013 クライアントの会議機能のサポート</span><span class="sxs-lookup"><span data-stu-id="19929-257">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="19929-258">ユーザーが lync Server 2010 会議に Lync 2013 クライアントを参加させると、次の例外を除き、Lync 2013 クライアント機能にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="19929-258">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="19929-259">[ **参加者** の管理] オプションでは、会議ウィンドウの [ユーザー] アイコンをポイントすることによってアクセスできます。 [ **会議 IM** を利用しない] オプションは機能しません。</span><span class="sxs-lookup"><span data-stu-id="19929-259">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="19929-260">ギャラリービューは、ビデオ会議では機能しません。</span><span class="sxs-lookup"><span data-stu-id="19929-260">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="19929-261">ユーザーには、すべてのスピーカーではなく、アクティブなスピーカーのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19929-261">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="19929-262">[レイアウトオプションの **選択** ] の一覧で、 **ギャラリービュー** を使用できません</span><span class="sxs-lookup"><span data-stu-id="19929-262">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="19929-263">参加者リストは、既定では、ビデオ会議に表示されます。</span><span class="sxs-lookup"><span data-stu-id="19929-263">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="19929-264">[参加者] リストでユーザーを右クリックすると、[ **ビデオスポットライトをロック** する] および [ギャラリー参加者管理 **にピン留めする** ] オプションが使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="19929-264">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="19929-265">Lync Server 2013 会議での会議機能のサポート</span><span class="sxs-lookup"><span data-stu-id="19929-265">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="19929-266">Lync Server 2013 は、アカウントが Lync Server 2013 に移動され、Lync 2013 クライアントを使用してサインインした後で、ユーザーが利用できるようになる新しい会議機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="19929-266">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="19929-267">例としては、ビデオギャラリービュー、HD ビデオ、PowerPoint 共有、会議エントリ時にすべての参加者の音声とビデオをミュートするオプションなどがあります。</span><span class="sxs-lookup"><span data-stu-id="19929-267">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="19929-268">新しい機能については、「 [Lync server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md) 」と「 [lync server 2013 のクライアント向けの新](lync-server-2013-what-s-new-for-clients.md)機能」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="19929-268">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="19929-269">Lync Server 2013 の会議では、さまざまなバージョンのサーバーに所属しており、異なるクライアントとクライアントバージョンを使用しているユーザーが、特定の会議機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="19929-269">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="19929-270">クライアントが Lync Server 2013 会議に参加すると、ユーザーはこの表に示されている機能にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="19929-270">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


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
<th><span data-ttu-id="19929-271">クライアント</span><span class="sxs-lookup"><span data-stu-id="19929-271">Client</span></span></th>
<th><span data-ttu-id="19929-272">ピアツーピア IM</span><span class="sxs-lookup"><span data-stu-id="19929-272">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="19929-273">音声</span><span class="sxs-lookup"><span data-stu-id="19929-273">Voice</span></span></th>
<th><span data-ttu-id="19929-274">ビデオ</span><span class="sxs-lookup"><span data-stu-id="19929-274">Video</span></span></th>
<th><span data-ttu-id="19929-275">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="19929-275">Application Sharing</span></span></th>
<th><span data-ttu-id="19929-276">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="19929-276">PowerPoint</span></span></th>
<th><span data-ttu-id="19929-277">ファイル送信</span><span class="sxs-lookup"><span data-stu-id="19929-277">File Transfer</span></span></th>
<th><span data-ttu-id="19929-278">Whiteboard</span><span class="sxs-lookup"><span data-stu-id="19929-278">Whiteboard</span></span></th>
<th><span data-ttu-id="19929-279">投票</span><span class="sxs-lookup"><span data-stu-id="19929-279">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19929-280">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="19929-280">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="19929-281">はい</span><span class="sxs-lookup"><span data-stu-id="19929-281">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-282">はい</span><span class="sxs-lookup"><span data-stu-id="19929-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-283">はい</span><span class="sxs-lookup"><span data-stu-id="19929-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-284">はい</span><span class="sxs-lookup"><span data-stu-id="19929-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-285">はい</span><span class="sxs-lookup"><span data-stu-id="19929-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-286">はい</span><span class="sxs-lookup"><span data-stu-id="19929-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-287">はい</span><span class="sxs-lookup"><span data-stu-id="19929-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-288">必要</span><span class="sxs-lookup"><span data-stu-id="19929-288">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19929-289">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="19929-289">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="19929-290">はい</span><span class="sxs-lookup"><span data-stu-id="19929-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-291">はい</span><span class="sxs-lookup"><span data-stu-id="19929-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-292">はい</span><span class="sxs-lookup"><span data-stu-id="19929-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-293">はい</span><span class="sxs-lookup"><span data-stu-id="19929-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-294">はい</span><span class="sxs-lookup"><span data-stu-id="19929-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-295">はい</span><span class="sxs-lookup"><span data-stu-id="19929-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-296">はい</span><span class="sxs-lookup"><span data-stu-id="19929-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-297">必要</span><span class="sxs-lookup"><span data-stu-id="19929-297">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19929-298">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="19929-298">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="19929-299">はい</span><span class="sxs-lookup"><span data-stu-id="19929-299">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-300">はい</span><span class="sxs-lookup"><span data-stu-id="19929-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-301">はい</span><span class="sxs-lookup"><span data-stu-id="19929-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-302">必要</span><span class="sxs-lookup"><span data-stu-id="19929-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-303">はい2</span><span class="sxs-lookup"><span data-stu-id="19929-303">Yes2</span></span></p></td>
<td><p><span data-ttu-id="19929-304">はい</span><span class="sxs-lookup"><span data-stu-id="19929-304">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-305">はい</span><span class="sxs-lookup"><span data-stu-id="19929-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-306">必要</span><span class="sxs-lookup"><span data-stu-id="19929-306">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19929-307">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="19929-307">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="19929-308">はい</span><span class="sxs-lookup"><span data-stu-id="19929-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-309">はい</span><span class="sxs-lookup"><span data-stu-id="19929-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-310">はい</span><span class="sxs-lookup"><span data-stu-id="19929-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-311">必要</span><span class="sxs-lookup"><span data-stu-id="19929-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-312">はい3</span><span class="sxs-lookup"><span data-stu-id="19929-312">Yes3</span></span></p></td>
<td><p><span data-ttu-id="19929-313">はい</span><span class="sxs-lookup"><span data-stu-id="19929-313">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-314">はい</span><span class="sxs-lookup"><span data-stu-id="19929-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="19929-315">必要</span><span class="sxs-lookup"><span data-stu-id="19929-315">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19929-316">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="19929-316">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="19929-317">必要</span><span class="sxs-lookup"><span data-stu-id="19929-317">Yes</span></span></p></td>
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


<span data-ttu-id="19929-318">1 Office Communicator 2007 R2 では、デスクトップ共有のみ (プログラム共有は不可) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="19929-318">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="19929-319">2 Lync Server 2013 は、PowerPoint ファイルをアップロードするための更新されたメカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="19929-319">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="19929-320">Lync Server 2010 で最初に予約された会議に参加している lync Web App ユーザーは、PowerPoint プレゼンテーションを表示して移動することはできますが、PowerPoint ファイルをアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="19929-320">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="19929-321">3 Lync Server 2013 で会議がスケジュールされており、PowerPoint スライドが Lync 2013 クライアントによってアップロードされている場合、Lync 2010 ユーザーはスライドに対して表示専用のアクセス権を持ちます。</span><span class="sxs-lookup"><span data-stu-id="19929-321">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="19929-322">反対に、PowerPoint スライドが Lync 2010 ユーザーによってアップロードされている場合、Lync Server 2013 ユーザーは表示やスライドの表示が可能で、Office Web Apps サーバーが構成されていれば、高解像度の表示、アニメーション、画面切り替え、埋め込みビデオなどの新しい機能にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="19929-322">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="19929-323">詳細については、「 [Office Web Apps Server および Lync Server 2013 との統合の構成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19929-323">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="19929-324">4The Communicator 2007 R2 のプレゼンスおよび IM 機能は Lync Server 2013 と互換性がありますが、会議機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="19929-324">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="19929-325">Office Communications Server 2007 R2 からの移行時に、Office Communicator 2007 R2 はプレゼンスおよび IM の相互運用性に適していますが、ユーザーは lync Server の2013会議に参加するために Lync Web App 2013 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19929-325">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="19929-326">スケジュールのアドインのサポート</span><span class="sxs-lookup"><span data-stu-id="19929-326">Scheduling Add-in Support</span></span>

<span data-ttu-id="19929-327">スケジュールのさまざまなアドインに対するサーバーのサポートは、サーバーとクライアントのバージョンの互換性に準じます。</span><span class="sxs-lookup"><span data-stu-id="19929-327">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="19929-328">一般に、Lync Server 2013 では、次のスケジュール設定アドインがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="19929-328">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="19929-329">ただし、以前のバージョンのアドインでは、会議の入力時にすべての参加者の音声とビデオをミュートするオプションなど、Lync 2013 アドインの新しい機能は提供されません。</span><span class="sxs-lookup"><span data-stu-id="19929-329">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="19929-330">**Lync 2013**     用オンラインミーティングアドインLync 2010 用のオンライン会議アドインと同じ機能を提供します。参加者のミュートコントロールを追加すると、会議の開催者は参加者の音声とビデオが既定でミュートされた会議をスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="19929-330">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="19929-331">管理者は、カスタムのロゴ、サポート URL、法的免責事項 URL、またはカスタムのフッター テキストを追加して、組織の会議出席依頼をカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="19929-331">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="19929-332">**Lync 2010**     用オンラインミーティングアドインLync 会議のスケジュールを提供し、Office Live Meeting 会議をスケジュールする機能を削除します。</span><span class="sxs-lookup"><span data-stu-id="19929-332">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="19929-333">**Office Communicator 2007 R2 会議アドイン**    Office Live Meeting 会議と Office Communicator 2007 R2 会議の両方のスケジュールを提供します。</span><span class="sxs-lookup"><span data-stu-id="19929-333">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="19929-334">Live Meeting 会議を Lync Server 2013 でスケジュールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="19929-334">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



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
<th><span data-ttu-id="19929-335">スケジュール クライアント</span><span class="sxs-lookup"><span data-stu-id="19929-335">Scheduling Client</span></span></th>
<th><span data-ttu-id="19929-336">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19929-336">Lync Server 2013</span></span></th>
<th><span data-ttu-id="19929-337">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="19929-337">Lync Server 2010</span></span></th>
<th><span data-ttu-id="19929-338">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="19929-338">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19929-339">Lync 2013 用オンラインミーティングアドイン (Office 2013、Outlook 2010、および Outlook 2007 で使用できます)</span><span class="sxs-lookup"><span data-stu-id="19929-339">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="19929-340">サポート</span><span class="sxs-lookup"><span data-stu-id="19929-340">Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-341">サポート対象 (新しいアドイン機能は使用不可)</span><span class="sxs-lookup"><span data-stu-id="19929-341">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="19929-342">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="19929-342">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19929-343">Lync 2013 Web Scheduler</span><span class="sxs-lookup"><span data-stu-id="19929-343">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="19929-344">サポートされている</span><span class="sxs-lookup"><span data-stu-id="19929-344">Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-345">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="19929-345">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-346">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="19929-346">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19929-347">Online Meeting Add-in for Lync 2010</span><span class="sxs-lookup"><span data-stu-id="19929-347">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="19929-348">サポート</span><span class="sxs-lookup"><span data-stu-id="19929-348">Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-349">サポートされている</span><span class="sxs-lookup"><span data-stu-id="19929-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-350">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="19929-350">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19929-351">Office Communicator 2007 R2 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="19929-351">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="19929-352">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="19929-352">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-353">サポートされます</span><span class="sxs-lookup"><span data-stu-id="19929-353">Supported</span></span></p></td>
<td><p><span data-ttu-id="19929-354">サポート</span><span class="sxs-lookup"><span data-stu-id="19929-354">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="19929-355">会議参加のサポート</span><span class="sxs-lookup"><span data-stu-id="19929-355">Support for Joining Meetings</span></span>

<span data-ttu-id="19929-356">Lync Server 2013 がサポートするすべてのクライアントは、Lync 2013 会議への参加を許可されます。</span><span class="sxs-lookup"><span data-stu-id="19929-356">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="19929-357">Lync web app はサーバーの web コンポーネントであるため、lync Web App を使用して Lync Server 2013 会議に参加している場合は、新しいバージョンの Lync Web App が常に使用されます。</span><span class="sxs-lookup"><span data-stu-id="19929-357">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="19929-358">Lync 2013 クライアントは、拡張機能を使用して Lync 2010 および Office Communications Server 2007 R2 でホストされている会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="19929-358">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="19929-359">会議参加機能は、会議がホストされるサーバーのバージョンによって制限されます。</span><span class="sxs-lookup"><span data-stu-id="19929-359">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="19929-360">関連項目</span><span class="sxs-lookup"><span data-stu-id="19929-360">See Also</span></span>


[<span data-ttu-id="19929-361">Lync Server 2013 の lync Windows ストアアプリの要件</span><span class="sxs-lookup"><span data-stu-id="19929-361">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="19929-362">Lync Server 2013 の新しい会議機能</span><span class="sxs-lookup"><span data-stu-id="19929-362">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="19929-363">Lync Server 2013 のクライアントの新機能</span><span class="sxs-lookup"><span data-stu-id="19929-363">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

