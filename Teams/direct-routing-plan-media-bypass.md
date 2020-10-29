---
title: ダイレクト ルーティングでメディア バイパスを計画する
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 電話システムのダイレクトルーティングを使用してメディアのバイパスを計画する方法について説明します。これにより、メディアトラフィックのパスを短縮し、パフォーマンスを向上させることができます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: efd6d4275d1e83df7821f178ddac8027039b6fce
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790659"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="75fb7-103">ダイレクト ルーティングでメディア バイパスを計画する</span><span class="sxs-lookup"><span data-stu-id="75fb7-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="75fb7-104">ダイレクトルーティングによるメディアのバイパスについて</span><span class="sxs-lookup"><span data-stu-id="75fb7-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="75fb7-105">メディアのバイパスにより、メディアトラフィックのパスを短縮し、転送中のホップの数を減らしてパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="75fb7-106">メディアをバイパスすると、メディアは、Microsoft 電話システム経由で送信されるのではなく、セッション境界コントローラー (SBC) とクライアントの間で保持されます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="75fb7-107">メディアバイパスを構成するには、SBC とクライアントが同じ場所またはネットワーク内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="75fb7-108">**Mediabypass** コマンドを使用し **て、各** SBC のメディアのバイパスを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="75fb7-109">メディアのバイパスを有効にすると、すべてのメディアトラフィックが企業ネットワーク内に収まるというわけではありません。</span><span class="sxs-lookup"><span data-stu-id="75fb7-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="75fb7-110">この記事では、さまざまなシナリオでのコールフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="75fb7-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="75fb7-111">以下の図は、メディアのバイパスを含む、または含まれていない通話フローの違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="75fb7-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="75fb7-112">メディアのバイパスがない場合、クライアントが通話を発信または受信したときに、次の図に示すように、SBC、Microsoft 電話システム、および Teams クライアント間のシグナリングとメディアフローの両方が行われます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="75fb7-113">![メディアバイパスのないシグナリングとメディアフローを示す](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="75fb7-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="75fb7-114">ただし、ユーザーが SBC と同じ建物またはネットワーク内にあることを前提としてみましょう。</span><span class="sxs-lookup"><span data-stu-id="75fb7-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="75fb7-115">たとえば、Frankfurt で建物内にいるユーザーが PSTN ユーザーに電話をかけるとします。</span><span class="sxs-lookup"><span data-stu-id="75fb7-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="75fb7-116">メディアがバイパスされて **いない** 場合、メディアはアムステルダムまたはダブリン (Microsoft データセンターが展開されている場所) で、FRANKFURT の SBC に戻ります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-116">**Without media bypass** , media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="75fb7-117">ヨーロッパのデータセンターが選択されているため、Microsoft は SBC に最も近いデータセンターを使用しています。</span><span class="sxs-lookup"><span data-stu-id="75fb7-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="75fb7-118">ほとんどの地域では、Microsoft ネットワーク内でのトラフィックフローの最適化による通話品質には影響ありませんが、トラフィックには不要なループがあります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="75fb7-119">**メディアをバイパスすると** 、次の図に示すように、Teams ユーザーと SBC の間でメディアが直接保持されます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-119">**With media bypass** , the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="75fb7-120">![メディアバイパスによるシグナリングとメディアフローを示しています](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="75fb7-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="75fb7-121">メディアのバイパスでは、SBC の Teams クライアントと ICE lite で対話型接続確立 (ICE) と呼ばれるプロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="75fb7-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="75fb7-122">これらのプロトコルでは、最適な音質を実現するために、ダイレクトルーティングで最も直接的なメディアパスを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="75fb7-123">ICE および ICE Lite は WebRTC 標準です。</span><span class="sxs-lookup"><span data-stu-id="75fb7-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="75fb7-124">これらのプロトコルの詳細については、RFC 5245 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75fb7-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="75fb7-125">コールフローとファイアウォールの計画</span><span class="sxs-lookup"><span data-stu-id="75fb7-125">Call flow and firewall planning</span></span>

<span data-ttu-id="75fb7-126">コールフローとファイアウォールの計画は、ユーザーが SBC のパブリック IP アドレスに直接アクセスできるかどうか、およびユーザーがネットワークの内外にいるかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="75fb7-127">ユーザーが SBC のパブリック IP アドレスに直接アクセスできる場合のコールフロー</span><span class="sxs-lookup"><span data-stu-id="75fb7-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="75fb7-128">ユーザーが SBC のパブリック IP アドレスに直接アクセスできる場合、通話フローは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="75fb7-129">メディアバイパスの場合、チームクライアントは、内部ネットワークからでも、SBC のパブリック IP アドレスにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="75fb7-130">ダイレクトメディアが必要でない場合、メディアはトランスポートリレー経由で流れることができます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="75fb7-131">これは、ユーザーが同じ建物またはネットワークにあるときに、SBC –メディアパスから Microsoft Cloud コンポーネントを削除する場合に推奨される解決策です。</span><span class="sxs-lookup"><span data-stu-id="75fb7-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="75fb7-132">シグナリングは、常に Microsoft cloud 経由でフローします。</span><span class="sxs-lookup"><span data-stu-id="75fb7-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="75fb7-133">次の図は、メディアのバイパスが有効になっている場合、クライアントが内部であり、クライアントが SBC (ダイレクトメディア) のパブリック IP アドレスに到達した場合のコールフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="75fb7-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="75fb7-134">パスの矢印と数値は、 [Microsoft Teams の通話フロー](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)に従っています。</span><span class="sxs-lookup"><span data-stu-id="75fb7-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows).</span></span>

- <span data-ttu-id="75fb7-135">SIP シグナリングには、常にパス4と 4 (トラフィックの方向によって異なります) があります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="75fb7-136">メディアはローカルのままでパス5b を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="75fb7-137">![メディアのバイパスが有効になっている、クライアントが内部のコールフローを示しています](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="75fb7-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="75fb7-138">ユーザーが SBC のパブリック IP アドレスにアクセスできない場合のコールフロー</span><span class="sxs-lookup"><span data-stu-id="75fb7-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="75fb7-139">次に、ユーザーが SBC のパブリック IP アドレスにアクセスできない場合のコールフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="75fb7-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="75fb7-140">たとえば、ユーザーが外部であることを前提としていますが、テナント管理者は、インターネット上のすべてのユーザーに、SBC のパブリック IP アドレスを開くことはできません。ただし、Microsoft Cloud のみです。</span><span class="sxs-lookup"><span data-stu-id="75fb7-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="75fb7-141">トラフィックの内部コンポーネントは、Teams トランスポートリレー経由で流れることができます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="75fb7-142">次の状況について検討しましょう。</span><span class="sxs-lookup"><span data-stu-id="75fb7-142">Consider the following:</span></span>

- <span data-ttu-id="75fb7-143">Teams トランスポートリレーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="75fb7-144">メディアのバイパスの場合、Microsoft は、チームトランスポートリレーと SBC の間でポート 50 000 59 999 を開く必要があるトランスポートリレーのバージョン (将来は、3478と3479のポートのみを必要とするバージョンに移行する予定です) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="75fb7-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>


<span data-ttu-id="75fb7-145">次の図は、メディアのバイパスが有効になっている場合、クライアントは外部であり、クライアントはセッションの境界コントローラーのパブリック IP アドレスに到達できないことを示しています (メディアは Teams トランスポートリレーによって中継されます)。</span><span class="sxs-lookup"><span data-stu-id="75fb7-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="75fb7-146">パスの矢印と数値は、 [Microsoft Teams の通話フロー](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)に従っています。</span><span class="sxs-lookup"><span data-stu-id="75fb7-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows).</span></span>

- <span data-ttu-id="75fb7-147">メディアは、3、3、4、4というパスで中継されます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="75fb7-148">![ユーザーが SBC のパブリック IP へのアクセス権を持っていない場合のコールフローを示します。](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="75fb7-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="75fb7-149">ユーザーがネットワーク外であり、SBC のパブリック IP にアクセスできる場合のコールフロー</span><span class="sxs-lookup"><span data-stu-id="75fb7-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="75fb7-150">これは、Teams トランスポートリレーを利用していないため、推奨される構成ではありません。</span><span class="sxs-lookup"><span data-stu-id="75fb7-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="75fb7-151">代わりに、ユーザーが SBC のパブリック IP アドレスにアクセスできない前のシナリオを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="75fb7-152">次の図は、メディアのバイパスが有効になっている場合、クライアントが外部であり、クライアントが SBC (ダイレクトメディア) のパブリック IP アドレスに到達できる場合のコールフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="75fb7-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="75fb7-153">パスの矢印と数値は、 [Microsoft Teams の通話フロー](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) の記事に従っています。</span><span class="sxs-lookup"><span data-stu-id="75fb7-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="75fb7-154">SIP シグナリングは、常にパス3と 3 (トラフィックの方向によって異なります) を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="75fb7-155">パス2を使用したメディアフロー。</span><span class="sxs-lookup"><span data-stu-id="75fb7-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="75fb7-156">![ユーザーが SBC のパブリック IP へのアクセス権を持っていない場合のコールフローを示します。](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="75fb7-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="75fb7-157">メディアプロセッサとトランスポートリレーの使用</span><span class="sxs-lookup"><span data-stu-id="75fb7-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="75fb7-158">メディアトラフィックのパスには、メディアプロセッサとトランスポートリレーという2つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="75fb7-159">メディアプロセッサは、非バイパスのケースでメディアを処理し、ボイスアプリケーションのメディアを処理するパブリックなフェーシングコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="75fb7-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="75fb7-160">メディアプロセッサは、常にエンドユーザーの非バイパス呼び出しのパスにありますが、バイパス呼び出しのパスには含まれません。</span><span class="sxs-lookup"><span data-stu-id="75fb7-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="75fb7-161">メディアプロセッサは、コールパーク、組織の自動応答、通話キューなど、すべての音声アプリケーションのパスに常に含まれています。</span><span class="sxs-lookup"><span data-stu-id="75fb7-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="75fb7-162">トランスポートリレーは、リアルタイムトラフィックを送信するために最も近いトランスポートサービスに接続するために使われます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="75fb7-163">トランスポート中継は、ユーザーがどこにいるかによって、またはエンドユーザーがどのように構成されているかに応じて、バイパスされた通話のパスに含まれている場合とできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="75fb7-164">次の図は、2つのコールフローを示しています。メディアのバイパスが有効で、もう1つはメディアバイパスが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="75fb7-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="75fb7-165">注図には、エンドユーザーからのトラフィックのみが示されます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-165">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="75fb7-166">メディアコントローラーは、メディアプロセッサを割り当て、セッション記述プロトコル (SDP) オファーを作成する Azure のマイクロサービスです。</span><span class="sxs-lookup"><span data-stu-id="75fb7-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="75fb7-167">SIP プロキシは、チームで使用される HTTP REST シグナリングを SIP に変換するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="75fb7-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="75fb7-168">![メディアバイパスを有効または無効にしたコールフローを表示します](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="75fb7-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="75fb7-169">以下の表は、メディアプロセッサとトランスポートリレーの違いをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="75fb7-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="75fb7-170">メディアプロセッサ</span><span class="sxs-lookup"><span data-stu-id="75fb7-170">Media Processors</span></span> | <span data-ttu-id="75fb7-171">トランスポートリレー</span><span class="sxs-lookup"><span data-stu-id="75fb7-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="75fb7-172">エンドユーザーへの非バイパス呼び出しのメディアパス</span><span class="sxs-lookup"><span data-stu-id="75fb7-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="75fb7-173">いつも</span><span class="sxs-lookup"><span data-stu-id="75fb7-173">Always</span></span> | <span data-ttu-id="75fb7-174">ぜんぜん</span><span class="sxs-lookup"><span data-stu-id="75fb7-174">Never</span></span> | 
<span data-ttu-id="75fb7-175">エンドユーザーに対してバイパスされる通話のメディアパス</span><span class="sxs-lookup"><span data-stu-id="75fb7-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="75fb7-176">ぜんぜん</span><span class="sxs-lookup"><span data-stu-id="75fb7-176">Never</span></span> | <span data-ttu-id="75fb7-177">クライアントがパブリック IP アドレスの SBC に到達できない場合</span><span class="sxs-lookup"><span data-stu-id="75fb7-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="75fb7-178">ボイスアプリケーションのメディアパス</span><span class="sxs-lookup"><span data-stu-id="75fb7-178">In media path for voice applications</span></span> | <span data-ttu-id="75fb7-179">いつも</span><span class="sxs-lookup"><span data-stu-id="75fb7-179">Always</span></span> | <span data-ttu-id="75fb7-180">ぜんぜん</span><span class="sxs-lookup"><span data-stu-id="75fb7-180">Never</span></span> | 
<span data-ttu-id="75fb7-181">コード変換を実行できる (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="75fb7-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="75fb7-182">はい</span><span class="sxs-lookup"><span data-stu-id="75fb7-182">Yes</span></span> | <span data-ttu-id="75fb7-183">いいえ、エンドポイント間の音声のみを中継します</span><span class="sxs-lookup"><span data-stu-id="75fb7-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="75fb7-184">ワールドワイドおよび場所のインスタンス数</span><span class="sxs-lookup"><span data-stu-id="75fb7-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="75fb7-185">10合計: 米国東部および西での22 (アムステルダムとダブリン)香港およびシンガポールでの2日本の22オーストラリア東部および東南</span><span class="sxs-lookup"><span data-stu-id="75fb7-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="75fb7-186">多数</span><span class="sxs-lookup"><span data-stu-id="75fb7-186">Multiple</span></span>

<span data-ttu-id="75fb7-187">IP 範囲は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="75fb7-187">The IP ranges are:</span></span>
- <span data-ttu-id="75fb7-188">52.112.0.0/14 (52.112.0.1 から52.115.255.254 への IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="75fb7-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="75fb7-189">52.120.0.0/14 (52.120.0.1 から52.123.255.254 への IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="75fb7-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="75fb7-190">\* コード変換の説明:</span><span class="sxs-lookup"><span data-stu-id="75fb7-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="75fb7-191">メディアプロセッサは B2BUA であることを意味します。つまり、SILK (Teams クライアントの場合は、MP と SBC の間の mp と G) に変更できます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="75fb7-192">トランスポートリレーは B2BUA ではありません。つまり、リレー経由でトラフィックが流れる場合でも、クライアントと SBC の間でコーデックが変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="75fb7-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="75fb7-193">メディアバイパス用にトランクが構成されている場合の Teams メディアプロセッサの使用</span><span class="sxs-lookup"><span data-stu-id="75fb7-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="75fb7-194">次のシナリオでは、チームメディアプロセッサは常にメディアパスに挿入されます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="75fb7-195">通話は1:1 からグループ通話にエスカレートされます</span><span class="sxs-lookup"><span data-stu-id="75fb7-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="75fb7-196">フェデレーションされた Teams ユーザーに通話を発信する</span><span class="sxs-lookup"><span data-stu-id="75fb7-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="75fb7-197">通話が Skype for Business ユーザーに転送または転送される</span><span class="sxs-lookup"><span data-stu-id="75fb7-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="75fb7-198">以下で説明するように、SBC がメディアプロセッサとトランスポートリレーの範囲にアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="75fb7-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="75fb7-199">SIP シグナリング: Fqdn</span><span class="sxs-lookup"><span data-stu-id="75fb7-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="75fb7-200">SIP シグナリングの場合、FQDN とファイアウォールの要件は、非バイパスのケースと同じです。</span><span class="sxs-lookup"><span data-stu-id="75fb7-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="75fb7-201">直接ルーティングは、次の Microsoft 365 または Office 365 環境で提供されます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="75fb7-202">Microsoft 365 または Office 365</span><span class="sxs-lookup"><span data-stu-id="75fb7-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="75fb7-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="75fb7-203">Office 365 GCC</span></span>
- <span data-ttu-id="75fb7-204">Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="75fb7-204">Office 365 GCC High</span></span>
- <span data-ttu-id="75fb7-205">Office 365 DoD の詳細については、「GCC、GCC 高、DoD などの [office 365 および米国政府機関向けの環境](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75fb7-205">Office 365 DoD Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="75fb7-206">Microsoft 365、Office 365、Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="75fb7-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="75fb7-207">直接ルーティングの接続ポイントは、次の3つの Fqdn です。</span><span class="sxs-lookup"><span data-stu-id="75fb7-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="75fb7-208">**sip.pstnhub.microsoft.com** –グローバル FQDN –最初に試す必要があります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="75fb7-209">SBC がこの名前を解決するための要求を送信すると、Microsoft Azure DNS サーバーは、SBC に割り当てられているプライマリ Azure datacenter をポイントしている IP アドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="75fb7-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="75fb7-210">課題は、データセンターのパフォーマンスメトリックと SBC への地理的な距離に基づいています。</span><span class="sxs-lookup"><span data-stu-id="75fb7-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="75fb7-211">返される IP アドレスは、プライマリ FQDN に対応しています。</span><span class="sxs-lookup"><span data-stu-id="75fb7-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="75fb7-212">**sip2.pstnhub.microsoft.com** –セカンダリ FQDN –地理的に2番目の優先度の地域にマップされます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="75fb7-213">**sip3.pstnhub.microsoft.com** –第3の FQDN –地理的に3番目の優先度の地域にマップされます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="75fb7-214">次のために、これらの3つの Fqdn を配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="75fb7-215">最適なエクスペリエンスを提供します (読み込みが少なく、最初の FQDN を照会することによって割り当てられた SBC データセンターに最も近い)。</span><span class="sxs-lookup"><span data-stu-id="75fb7-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="75fb7-216">一時的な問題が発生しているデータセンターに対して SBC からの接続が確立された場合のフェールオーバーを提供します。</span><span class="sxs-lookup"><span data-stu-id="75fb7-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="75fb7-217">詳細については、以下の「フェールオーバーのメカニズム」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="75fb7-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="75fb7-218">Fqdn **sip.pstnhub.microsoft.com** 、 **sip2.pstnhub.microsoft.com** 、および **sip3.pstnhub.microsoft.com** は、次のいずれかの IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-218">The FQDNs **sip.pstnhub.microsoft.com** , **sip2.pstnhub.microsoft.com** , and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="75fb7-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="75fb7-219">52.114.148.0</span></span>
- <span data-ttu-id="75fb7-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="75fb7-220">52.114.132.46</span></span>
- <span data-ttu-id="75fb7-221">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="75fb7-221">52.114.16.74</span></span>
- <span data-ttu-id="75fb7-222">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="75fb7-222">52.114.20.29</span></span>
- <span data-ttu-id="75fb7-223">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="75fb7-223">52.114.75.24</span></span>
- <span data-ttu-id="75fb7-224">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="75fb7-224">52.114.76.76</span></span>
- <span data-ttu-id="75fb7-225">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="75fb7-225">52.114.7.24</span></span>
- <span data-ttu-id="75fb7-226">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="75fb7-226">52.114.14.70</span></span>

<span data-ttu-id="75fb7-227">シグナリングのアドレスとの送受信トラフィックを許可するには、ファイアウォール内のすべての IP アドレスのポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-227">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="75fb7-228">ファイアウォールで DNS 名がサポートされている場合、FQDN **sip-all.pstnhub.microsoft.com** はこれらのすべての IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-228">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="75fb7-229">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="75fb7-229">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="75fb7-230">ダイレクトルーティングの接続ポイントは、次の FQDN です。</span><span class="sxs-lookup"><span data-stu-id="75fb7-230">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="75fb7-231">**sip.pstnhub.dod.teams.microsoft.us** –グローバル FQDN。</span><span class="sxs-lookup"><span data-stu-id="75fb7-231">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="75fb7-232">Office 365 DoD 環境は US データセンターにのみ存在するため、第2および第3の Fqdn はありません。</span><span class="sxs-lookup"><span data-stu-id="75fb7-232">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="75fb7-233">Fqdn – sip.pstnhub.dod.teams.microsoft.us は、次のいずれかの IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-233">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="75fb7-234">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="75fb7-234">52.127.64.33</span></span>
- <span data-ttu-id="75fb7-235">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="75fb7-235">52.127.68.34</span></span>

<span data-ttu-id="75fb7-236">シグナリングのアドレスとの送受信トラフィックを許可するには、ファイアウォール内のすべての IP アドレスのポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-236">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="75fb7-237">ファイアウォールで DNS 名がサポートされている場合、FQDN sip.pstnhub.dod.teams.microsoft.us はこれらのすべての IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-237">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="75fb7-238">Office 365 GCC 高環境</span><span class="sxs-lookup"><span data-stu-id="75fb7-238">Office 365 GCC High environment</span></span>

<span data-ttu-id="75fb7-239">ダイレクトルーティングの接続ポイントは、次の FQDN です。</span><span class="sxs-lookup"><span data-stu-id="75fb7-239">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="75fb7-240">**sip.pstnhub.gov.teams.microsoft.us** –グローバル FQDN。</span><span class="sxs-lookup"><span data-stu-id="75fb7-240">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="75fb7-241">GCC 高環境は US データセンターにのみ存在するため、第2の Fqdn はありません。</span><span class="sxs-lookup"><span data-stu-id="75fb7-241">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="75fb7-242">Fqdn – sip.pstnhub.gov.teams.microsoft.us は、次のいずれかの IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-242">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="75fb7-243">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="75fb7-243">52.127.88.59</span></span>
- <span data-ttu-id="75fb7-244">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="75fb7-244">52.127.92.64</span></span>

<span data-ttu-id="75fb7-245">シグナリングのアドレスとの送受信トラフィックを許可するには、ファイアウォール内のすべての IP アドレスのポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-245">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="75fb7-246">ファイアウォールで DNS 名がサポートされている場合、FQDN sip.pstnhub.gov.teams.microsoft.us はこれらのすべての IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-246">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="75fb7-247">SIP シグナリング: ポート</span><span class="sxs-lookup"><span data-stu-id="75fb7-247">SIP Signaling: Ports</span></span>

<span data-ttu-id="75fb7-248">ダイレクトルーティングが提供されているすべての Office 365 環境では、ポート要件は同じです。</span><span class="sxs-lookup"><span data-stu-id="75fb7-248">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="75fb7-249">Microsoft 365 または Office 365</span><span class="sxs-lookup"><span data-stu-id="75fb7-249">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="75fb7-250">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="75fb7-250">Office 365 GCC</span></span>
- <span data-ttu-id="75fb7-251">Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="75fb7-251">Office 365 GCC High</span></span>
- <span data-ttu-id="75fb7-252">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="75fb7-252">Office 365 DoD</span></span>

<span data-ttu-id="75fb7-253">次のポートを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-253">You must use the following ports:</span></span>

| <span data-ttu-id="75fb7-254">通過</span><span class="sxs-lookup"><span data-stu-id="75fb7-254">Traffic</span></span> | <span data-ttu-id="75fb7-255">開始</span><span class="sxs-lookup"><span data-stu-id="75fb7-255">From</span></span> | <span data-ttu-id="75fb7-256">終了</span><span class="sxs-lookup"><span data-stu-id="75fb7-256">To</span></span> | <span data-ttu-id="75fb7-257">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="75fb7-257">Source port</span></span> | <span data-ttu-id="75fb7-258">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="75fb7-258">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="75fb7-259">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="75fb7-259">SIP/TLS</span></span>| <span data-ttu-id="75fb7-260">SIP プロキシ</span><span class="sxs-lookup"><span data-stu-id="75fb7-260">SIP Proxy</span></span> | <span data-ttu-id="75fb7-261">SBC</span><span class="sxs-lookup"><span data-stu-id="75fb7-261">SBC</span></span> | <span data-ttu-id="75fb7-262">1024-65535</span><span class="sxs-lookup"><span data-stu-id="75fb7-262">1024 - 65535</span></span> | <span data-ttu-id="75fb7-263">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="75fb7-263">Defined on the SBC</span></span> |
| <span data-ttu-id="75fb7-264">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="75fb7-264">SIP/TLS</span></span> | <span data-ttu-id="75fb7-265">SBC</span><span class="sxs-lookup"><span data-stu-id="75fb7-265">SBC</span></span> | <span data-ttu-id="75fb7-266">SIP プロキシ</span><span class="sxs-lookup"><span data-stu-id="75fb7-266">SIP Proxy</span></span> | <span data-ttu-id="75fb7-267">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="75fb7-267">Defined on the SBC</span></span> | <span data-ttu-id="75fb7-268">5061</span><span class="sxs-lookup"><span data-stu-id="75fb7-268">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="75fb7-269">メディアトラフィック: IP とポートの範囲</span><span class="sxs-lookup"><span data-stu-id="75fb7-269">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="75fb7-270">直接接続が利用できるか、またはクライアントがパブリック IP アドレスを使用して SBC に到達できない場合は、SBC と Teams クライアント間でメディアトラフィックが流れます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-270">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="75fb7-271">ダイレクトメディアトラフィック (Teams クライアントと SBC の間) の要件</span><span class="sxs-lookup"><span data-stu-id="75fb7-271">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="75fb7-272">クライアントは、SBC のパブリック IP アドレスで指定されたポート (表を参照) にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-272">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="75fb7-273">注: クライアントが内部ネットワーク内にある場合、メディアは SBC のパブリック IP アドレスに送られます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-273">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="75fb7-274">トラフィックが企業ネットワーク機器から出ることがないように、NAT デバイスで髪のピン留めを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-274">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="75fb7-275">通過</span><span class="sxs-lookup"><span data-stu-id="75fb7-275">Traffic</span></span> | <span data-ttu-id="75fb7-276">開始</span><span class="sxs-lookup"><span data-stu-id="75fb7-276">From</span></span> | <span data-ttu-id="75fb7-277">終了</span><span class="sxs-lookup"><span data-stu-id="75fb7-277">To</span></span> | <span data-ttu-id="75fb7-278">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="75fb7-278">Source port</span></span> | <span data-ttu-id="75fb7-279">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="75fb7-279">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="75fb7-280">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="75fb7-280">UDP/SRTP</span></span> | <span data-ttu-id="75fb7-281">クライアント</span><span class="sxs-lookup"><span data-stu-id="75fb7-281">Client</span></span> | <span data-ttu-id="75fb7-282">SBC</span><span class="sxs-lookup"><span data-stu-id="75fb7-282">SBC</span></span> | <span data-ttu-id="75fb7-283">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="75fb7-283">50 000 – 50 019</span></span>  | <span data-ttu-id="75fb7-284">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="75fb7-284">Defined on the SBC</span></span> |
| <span data-ttu-id="75fb7-285">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="75fb7-285">UDP/SRTP</span></span> | <span data-ttu-id="75fb7-286">SBC</span><span class="sxs-lookup"><span data-stu-id="75fb7-286">SBC</span></span> | <span data-ttu-id="75fb7-287">クライアント</span><span class="sxs-lookup"><span data-stu-id="75fb7-287">Client</span></span> | <span data-ttu-id="75fb7-288">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="75fb7-288">Defined on the SBC</span></span> | <span data-ttu-id="75fb7-289">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="75fb7-289">50 000 – 50 019</span></span>  |


> [!NOTE]
> <span data-ttu-id="75fb7-290">クライアントのソースポートを変換するネットワークデバイスがある場合は、ネットワーク機器と SBC の間で変換されたポートが開かれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="75fb7-290">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="75fb7-291">トランスポートリレーを使用するための要件</span><span class="sxs-lookup"><span data-stu-id="75fb7-291">Requirements for using Transport Relays</span></span>

<span data-ttu-id="75fb7-292">トランスポートリレーは、メディアプロセッサ (バイパス以外のケース) と同じ範囲にあります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-292">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="75fb7-293">Microsoft 365、Office 365、Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="75fb7-293">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="75fb7-294">52.112.0.0/14 (52.112.0.1 から52.115.255.254 への IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="75fb7-294">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="75fb7-295">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="75fb7-295">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="75fb7-296">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="75fb7-296">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="75fb7-297">Office 365 GCC 高環境</span><span class="sxs-lookup"><span data-stu-id="75fb7-297">Office 365 GCC High environment</span></span>

- <span data-ttu-id="75fb7-298">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="75fb7-298">52.127.88.0/21</span></span>


<span data-ttu-id="75fb7-299">Teams トランスポートリレーのポート範囲 (すべての環境に適用されます) については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75fb7-299">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="75fb7-300">通過</span><span class="sxs-lookup"><span data-stu-id="75fb7-300">Traffic</span></span> | <span data-ttu-id="75fb7-301">開始</span><span class="sxs-lookup"><span data-stu-id="75fb7-301">From</span></span> | <span data-ttu-id="75fb7-302">終了</span><span class="sxs-lookup"><span data-stu-id="75fb7-302">To</span></span> | <span data-ttu-id="75fb7-303">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="75fb7-303">Source port</span></span> | <span data-ttu-id="75fb7-304">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="75fb7-304">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="75fb7-305">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="75fb7-305">UDP/SRTP</span></span> | <span data-ttu-id="75fb7-306">トランスポートリレー</span><span class="sxs-lookup"><span data-stu-id="75fb7-306">Transport Relay</span></span> | <span data-ttu-id="75fb7-307">SBC</span><span class="sxs-lookup"><span data-stu-id="75fb7-307">SBC</span></span> | <span data-ttu-id="75fb7-308">50 000-59 999</span><span class="sxs-lookup"><span data-stu-id="75fb7-308">50 000 -59 999</span></span>    | <span data-ttu-id="75fb7-309">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="75fb7-309">Defined on the SBC</span></span> |
| <span data-ttu-id="75fb7-310">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="75fb7-310">UDP/SRTP</span></span> | <span data-ttu-id="75fb7-311">SBC</span><span class="sxs-lookup"><span data-stu-id="75fb7-311">SBC</span></span> | <span data-ttu-id="75fb7-312">トランスポートリレー</span><span class="sxs-lookup"><span data-stu-id="75fb7-312">Transport Relay</span></span> | <span data-ttu-id="75fb7-313">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="75fb7-313">Defined on the SBC</span></span> | <span data-ttu-id="75fb7-314">50 000 – 59 999、3478、3479</span><span class="sxs-lookup"><span data-stu-id="75fb7-314">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="75fb7-315">Microsoft は、SBC で同時呼び出しごとに少なくとも2つのポートをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="75fb7-315">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="75fb7-316">Microsoft にはトランスポートリレーの2つのバージョンがあるため、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="75fb7-316">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="75fb7-317">v4 (ポート範囲 59 999 50 000 でのみ使用可能)</span><span class="sxs-lookup"><span data-stu-id="75fb7-317">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="75fb7-318">v6 (ポート3478、3479と連携)</span><span class="sxs-lookup"><span data-stu-id="75fb7-318">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="75fb7-319">現時点では、メディアバイパスは、トランスポートリレーの v4 バージョンのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="75fb7-319">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="75fb7-320">今後、v6 のサポートが導入される予定です。</span><span class="sxs-lookup"><span data-stu-id="75fb7-320">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="75fb7-321">移行するには、ポート3478と3479を開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-321">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="75fb7-322">Microsoft がメディアバイパスでの v6 トランスポートリレーのサポートを導入する場合、ネットワーク機器または SBCs を再設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="75fb7-322">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="75fb7-323">メディアプロセッサを使うための要件</span><span class="sxs-lookup"><span data-stu-id="75fb7-323">Requirements for using media processors</span></span>

<span data-ttu-id="75fb7-324">メディアプロセッサは、常にボイスアプリケーションおよび Web クライアント (たとえば、エッジまたは Google Chrome の Teams クライアント) のメディアパスにあります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-324">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="75fb7-325">要件は、非バイパス構成の場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="75fb7-325">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="75fb7-326">メディアトラフィックの IP 範囲は</span><span class="sxs-lookup"><span data-stu-id="75fb7-326">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="75fb7-327">Office 365 および Office 365 の GCC 環境</span><span class="sxs-lookup"><span data-stu-id="75fb7-327">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="75fb7-328">52.112.0.0/14 (52.112.0.1 から52.115.255.254 への IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="75fb7-328">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="75fb7-329">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="75fb7-329">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="75fb7-330">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="75fb7-330">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="75fb7-331">Office 365 GCC 高環境</span><span class="sxs-lookup"><span data-stu-id="75fb7-331">Office 365 GCC High environment</span></span>

- <span data-ttu-id="75fb7-332">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="75fb7-332">52.127.88.0/21</span></span>

<span data-ttu-id="75fb7-333">メディアプロセッサのポート範囲 (すべての環境に該当) を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="75fb7-333">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="75fb7-334">通過</span><span class="sxs-lookup"><span data-stu-id="75fb7-334">Traffic</span></span> | <span data-ttu-id="75fb7-335">開始</span><span class="sxs-lookup"><span data-stu-id="75fb7-335">From</span></span> | <span data-ttu-id="75fb7-336">終了</span><span class="sxs-lookup"><span data-stu-id="75fb7-336">To</span></span> | <span data-ttu-id="75fb7-337">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="75fb7-337">Source port</span></span> | <span data-ttu-id="75fb7-338">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="75fb7-338">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="75fb7-339">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="75fb7-339">UDP/SRTP</span></span> | <span data-ttu-id="75fb7-340">メディアプロセッサ</span><span class="sxs-lookup"><span data-stu-id="75fb7-340">Media Processor</span></span> | <span data-ttu-id="75fb7-341">SBC</span><span class="sxs-lookup"><span data-stu-id="75fb7-341">SBC</span></span> | <span data-ttu-id="75fb7-342">3478、3479、49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="75fb7-342">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="75fb7-343">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="75fb7-343">Defined on the SBC</span></span> |
| <span data-ttu-id="75fb7-344">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="75fb7-344">UDP/SRTP</span></span> | <span data-ttu-id="75fb7-345">SBC</span><span class="sxs-lookup"><span data-stu-id="75fb7-345">SBC</span></span> | <span data-ttu-id="75fb7-346">メディアプロセッサ</span><span class="sxs-lookup"><span data-stu-id="75fb7-346">Media Processor</span></span> | <span data-ttu-id="75fb7-347">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="75fb7-347">Defined on the SBC</span></span> | <span data-ttu-id="75fb7-348">3478、3479、49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="75fb7-348">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="75fb7-349">メディアバイパスとメディア以外のバイパス用に個別の trunks を構成する</span><span class="sxs-lookup"><span data-stu-id="75fb7-349">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="75fb7-350">メディアバイパスからメディアバイパスに移行していて、すべての使用状況をメディアバイパスに移行する前に機能を確認したい場合は、独立したトランクとオンラインボイスルーティングポリシーを作成して、メディアをスキップして特定のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-350">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="75fb7-351">高レベルの構成手順:</span><span class="sxs-lookup"><span data-stu-id="75fb7-351">High-level configuration steps:</span></span>

- <span data-ttu-id="75fb7-352">メディアバイパスをテストするユーザーを特定します。</span><span class="sxs-lookup"><span data-stu-id="75fb7-352">Identify users to test media bypass.</span></span>

- <span data-ttu-id="75fb7-353">異なる Fqdn を使用して2つの別個の trunks を作成します。1つはメディアバイパス用です。それ以外の場合は、</span><span class="sxs-lookup"><span data-stu-id="75fb7-353">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="75fb7-354">どちらの trunks も、同じ SBC をポイントします。</span><span class="sxs-lookup"><span data-stu-id="75fb7-354">Both trunks point to the same SBC.</span></span> <span data-ttu-id="75fb7-355">TLS SIP シグナリングのポートは異なっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-355">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="75fb7-356">メディアのポートは同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-356">The ports for media must be the same.</span></span>

- <span data-ttu-id="75fb7-357">新しいオンラインボイスルーティングポリシーを作成し、このポリシーの PSTN 使用状況に関連付けられた対応するルートにメディアバイパストランクを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-357">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="75fb7-358">新しいオンラインボイスルーティングポリシーを、[メディアバイパスのテスト用として指定したユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-358">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="75fb7-359">次の例は、このロジックを示しています。</span><span class="sxs-lookup"><span data-stu-id="75fb7-359">The example below illustrates this logic.</span></span>

| <span data-ttu-id="75fb7-360">ユーザーのセット</span><span class="sxs-lookup"><span data-stu-id="75fb7-360">Set of users</span></span> | <span data-ttu-id="75fb7-361">ユーザー数</span><span class="sxs-lookup"><span data-stu-id="75fb7-361">Number of users</span></span> | <span data-ttu-id="75fb7-362">"の順番で割り当てられたトランクの FQDN</span><span class="sxs-lookup"><span data-stu-id="75fb7-362">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="75fb7-363">メディアのバイパスを有効にする</span><span class="sxs-lookup"><span data-stu-id="75fb7-363">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="75fb7-364">メディア以外のトランクを使っているユーザー</span><span class="sxs-lookup"><span data-stu-id="75fb7-364">Users with non-media bypass trunk</span></span> | <span data-ttu-id="75fb7-365">980</span><span class="sxs-lookup"><span data-stu-id="75fb7-365">980</span></span> | <span data-ttu-id="75fb7-366">sbc1.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="75fb7-366">sbc1.contoso.com:5060</span></span> | <span data-ttu-id="75fb7-367">true</span><span class="sxs-lookup"><span data-stu-id="75fb7-367">true</span></span>
<span data-ttu-id="75fb7-368">メディアを使ったユーザーのトランクのバイパス</span><span class="sxs-lookup"><span data-stu-id="75fb7-368">Users with media bypass trunk</span></span> | <span data-ttu-id="75fb7-369">超える</span><span class="sxs-lookup"><span data-stu-id="75fb7-369">20</span></span> | <span data-ttu-id="75fb7-370">sbc2.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="75fb7-370">sbc2.contoso.com:5061</span></span> | <span data-ttu-id="75fb7-371">false</span><span class="sxs-lookup"><span data-stu-id="75fb7-371">false</span></span> | 

<span data-ttu-id="75fb7-372">どちらの trunks も、同じ SBC を同じパブリック IP アドレスで指すことができます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-372">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="75fb7-373">次の図に示すように、SBC の TLS シグナリングポートは異なっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-373">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="75fb7-374">注: 証明書で trunks の両方がサポートされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-374">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="75fb7-375">SAN では、2つの名前 ( **sbc1.contoso.com** と **sbc2.contoso.com** ) を使用するか、ワイルドカード証明書を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="75fb7-375">In SAN, you need to have two names ( **sbc1.contoso.com** and **sbc2.contoso.com** ) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="75fb7-376">![両方の trunks が同じ SBC をポイントし、同じパブリック IP アドレスを持つことを示します。](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="75fb7-376">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="75fb7-377">同じ SBC で2つの trunks を構成する方法については、SBC ベンダーから提供されているドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="75fb7-377">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="75fb7-378">AudioCodes の展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="75fb7-378">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="75fb7-379">Oracle 展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="75fb7-379">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="75fb7-380">リボンの通信展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="75fb7-380">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="75fb7-381">TE システム (anynode) の展開ドキュメント</span><span class="sxs-lookup"><span data-stu-id="75fb7-381">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="75fb7-382">メディアバイパスでサポートされているクライアントエンドポイント</span><span class="sxs-lookup"><span data-stu-id="75fb7-382">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="75fb7-383">メディアのバイパスは、すべてのスタンドアロンの Teams デスクトップクライアント、Android および iOS クライアント、およびチーム電話デバイスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="75fb7-383">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="75fb7-384">メディアのバイパスをサポートしていないその他のすべてのエンドポイントの場合は、バイパスの呼び出しとして呼び出された場合でも、その呼び出しを非バイパスに変換します。</span><span class="sxs-lookup"><span data-stu-id="75fb7-384">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="75fb7-385">これは自動的に行われるため、管理者からの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="75fb7-385">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="75fb7-386">これには、Skype for Business 3PIP 電話、直接ルーティング通話をサポートする Teams Web クライアント (Microsoft Edge、Google Chrome、Mozilla Firefox で実行されている WebRTC ベースのクライアント) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75fb7-386">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="75fb7-387">関連項目</span><span class="sxs-lookup"><span data-stu-id="75fb7-387">See also</span></span>

[<span data-ttu-id="75fb7-388">ダイレクト ルーティングでメディア バイパスを構成する</span><span class="sxs-lookup"><span data-stu-id="75fb7-388">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)


