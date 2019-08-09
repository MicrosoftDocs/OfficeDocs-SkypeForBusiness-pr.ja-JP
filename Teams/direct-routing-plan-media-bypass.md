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
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: このトピックでは、電話システムのダイレクトルーティングを使用してメディアのバイパスを計画する方法について説明します。
ms.openlocfilehash: 70d0b5ea61d0d7a8001bb1dbfabda2c45274e521
ms.sourcegitcommit: 6cbdcb8606044ad7ab49a4e3c828c2dc3d50fcc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "36271448"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="a6e67-103">ダイレクト ルーティングでメディア バイパスを計画する</span><span class="sxs-lookup"><span data-stu-id="a6e67-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="a6e67-104">ダイレクトルーティングによるメディアのバイパスについて</span><span class="sxs-lookup"><span data-stu-id="a6e67-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="a6e67-105">メディアのバイパスにより、メディアトラフィックのパスを短縮し、転送中のホップの数を減らしてパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="a6e67-106">メディアをバイパスすると、メディアは、Microsoft 電話システム経由で送信されるのではなく、セッション境界コントローラー (SBC) とクライアントの間で保持されます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="a6e67-107">メディアバイパスを構成するには、SBC とクライアントが同じ場所またはネットワーク内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="a6e67-108">**Mediabypass**コマンドを使用して、各\*\*\*\* SBC のメディアのバイパスを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="a6e67-109">メディアのバイパスを有効にすると、すべてのメディアトラフィックが企業ネットワーク内に収まるというわけではありません。</span><span class="sxs-lookup"><span data-stu-id="a6e67-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="a6e67-110">この記事では、さまざまなシナリオでのコールフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a6e67-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="a6e67-111">以下の図は、メディアのバイパスを含む、または含まれていない通話フローの違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="a6e67-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="a6e67-112">メディアのバイパスがない場合、クライアントが通話を発信または受信したときに、次の図に示すように、SBC、Microsoft 電話システム、および Teams クライアント間のシグナリングとメディアフローの両方が行われます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

![メディアバイパスのないシグナリングとメディアフローを示す](media/direct-routing-media-bypass-1.png)


<span data-ttu-id="a6e67-114">ただし、ユーザーが SBC と同じ建物またはネットワーク内にあることを前提としてみましょう。</span><span class="sxs-lookup"><span data-stu-id="a6e67-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="a6e67-115">たとえば、Frankfurt で建物内にいるユーザーが PSTN ユーザーに電話をかけるとします。</span><span class="sxs-lookup"><span data-stu-id="a6e67-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="a6e67-116">メディアがバイパスされて**いない**場合、メディアはアムステルダムまたはダブリン (Microsoft データセンターが展開されている場所) で、FRANKFURT の SBC に戻ります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="a6e67-117">ヨーロッパのデータセンターが選択されているため、Microsoft は SBC に最も近いデータセンターを使用しています。</span><span class="sxs-lookup"><span data-stu-id="a6e67-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="a6e67-118">ほとんどの地域では、Microsoft ネットワーク内でのトラフィックフローの最適化による通話品質には影響ありませんが、トラフィックには不要なループがあります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="a6e67-119">**メディアをバイパスすると**、次の図に示すように、Teams ユーザーと SBC の間でメディアが直接保持されます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

![メディアバイパスによるシグナリングとメディアフローを示しています](media/direct-routing-media-bypass-2.png)

<span data-ttu-id="a6e67-121">メディアのバイパスでは、SBC の Teams クライアントと ICE lite で対話型接続確立 (ICE) と呼ばれるプロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6e67-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="a6e67-122">これらのプロトコルでは、最適な音質を実現するために、ダイレクトルーティングで最も直接的なメディアパスを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="a6e67-123">ICE および ICE Lite は WebRTC 標準です。</span><span class="sxs-lookup"><span data-stu-id="a6e67-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="a6e67-124">これらのプロトコルの詳細については、RFC 5245 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6e67-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="a6e67-125">コールフローとファイアウォールの計画</span><span class="sxs-lookup"><span data-stu-id="a6e67-125">Call flow and firewall planning</span></span>

<span data-ttu-id="a6e67-126">コールフローとファイアウォールの計画は、ユーザーが SBC のパブリック IP アドレスに直接アクセスできるかどうか、およびユーザーがネットワークの内外にいるかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="a6e67-127">ユーザーが SBC のパブリック IP アドレスに直接アクセスできる場合のコールフロー</span><span class="sxs-lookup"><span data-stu-id="a6e67-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="a6e67-128">ユーザーが SBC のパブリック IP アドレスに直接アクセスできる場合、通話フローは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="a6e67-129">メディアバイパスの場合、チームクライアントは、内部ネットワークからでも、SBC のパブリック IP アドレスにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="a6e67-130">ダイレクトメディアが必要でない場合、メディアはトランスポートリレー経由で流れることができます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="a6e67-131">これは、ユーザーが同じ建物またはネットワークにあるときに、SBC –メディアパスから Microsoft Cloud コンポーネントを削除する場合に推奨される解決策です。</span><span class="sxs-lookup"><span data-stu-id="a6e67-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="a6e67-132">シグナリングは、常に Microsoft cloud 経由でフローします。</span><span class="sxs-lookup"><span data-stu-id="a6e67-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="a6e67-133">次の図は、メディアのバイパスが有効になっている場合、クライアントが内部であり、クライアントが SBC (ダイレクトメディア) のパブリック IP アドレスに到達した場合のコールフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="a6e67-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="a6e67-134">パスの矢印と数値は、 [Microsoft Teams の通話フロー](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)の記事に従っています。</span><span class="sxs-lookup"><span data-stu-id="a6e67-134">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="a6e67-135">SIP シグナリングには、常にパス4と 4 (トラフィックの方向によって異なります) があります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-135">The SIP signaling always takes paths 4 and 4’ (depending on the direction of the traffic).</span></span> <span data-ttu-id="a6e67-136">メディアはローカルのままでパス5b を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-136">Media stays local and takes path 5b.</span></span>

![メディアのバイパスが有効になっている、クライアントが内部のコールフローを示しています](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="a6e67-138">ユーザーが SBC のパブリック IP アドレスにアクセスできない場合のコールフロー</span><span class="sxs-lookup"><span data-stu-id="a6e67-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="a6e67-139">次に、ユーザーが SBC のパブリック IP アドレスにアクセスできない場合のコールフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a6e67-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="a6e67-140">たとえば、ユーザーが外部であることを前提としていますが、テナント管理者は、インターネット上のすべてのユーザーに、SBC のパブリック IP アドレスを開くことはできません。ただし、Microsoft Cloud のみです。</span><span class="sxs-lookup"><span data-stu-id="a6e67-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="a6e67-141">トラフィックの内部コンポーネントは、Teams トランスポートリレー経由で流れることができます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="a6e67-142">これは、企業ネットワークの外部のユーザーに推奨される構成です。</span><span class="sxs-lookup"><span data-stu-id="a6e67-142">This is the recommended configuration for users outside of the corporate network.</span></span> <span data-ttu-id="a6e67-143">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="a6e67-143">Consider the following:</span></span>

- <span data-ttu-id="a6e67-144">Teams トランスポートリレーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-144">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="a6e67-145">メディアのバイパスの場合、Microsoft は、チームトランスポートリレーと SBC の間でポート 50 000 59 999 を開く必要があるトランスポートリレーのバージョン (将来は、3478と3479のポートのみを必要とするバージョンに移行する予定です) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="a6e67-145">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>

- <span data-ttu-id="a6e67-146">メディアの最適化のため、Microsoft は、SBC のパブリック IP アドレスを Teams トランスポートリレーにのみ開くことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a6e67-146">For media optimization purposes, Microsoft recommends opening the public IP address of the SBC only to Teams Transport Relays.</span></span> <span data-ttu-id="a6e67-147">企業ネットワークの外部にいるクライアントの場合、Microsoft は、SBC のパブリック IP アドレスに直接アクセスする代わりに、トランスポートリレーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a6e67-147">For clients outside of the corporate network, Microsoft recommends using Transport Relays instead of reaching the public IP address of the SBC directly.</span></span>

<span data-ttu-id="a6e67-148">次の図は、メディアのバイパスが有効になっている場合、クライアントは外部であり、クライアントはセッションの境界コントローラーのパブリック IP アドレスに到達できないことを示しています (メディアは Teams トランスポートリレーによって中継されます)。</span><span class="sxs-lookup"><span data-stu-id="a6e67-148">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="a6e67-149">パスの矢印と数値は、 [Microsoft Teams の通話フロー](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)の記事に従っています。</span><span class="sxs-lookup"><span data-stu-id="a6e67-149">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="a6e67-150">メディアは、3、3、4、4というパスで中継されます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-150">Media is relayed via paths 3, 3', 4 and 4'</span></span>

![ユーザーが SBC のパブリック IP へのアクセス権を持っていない場合のコールフローを示します。](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="a6e67-152">ユーザーがネットワーク外であり、SBC のパブリック IP にアクセスできる場合のコールフロー</span><span class="sxs-lookup"><span data-stu-id="a6e67-152">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="a6e67-153">これは、Teams トランスポートリレーを利用していないため、推奨される構成ではありません。</span><span class="sxs-lookup"><span data-stu-id="a6e67-153">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="a6e67-154">代わりに、ユーザーが SBC のパブリック IP アドレスにアクセスできない前のシナリオを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-154">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="a6e67-155">次の図は、メディアのバイパスが有効になっている場合、クライアントが外部であり、クライアントが SBC (ダイレクトメディア) のパブリック IP アドレスに到達できる場合のコールフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="a6e67-155">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="a6e67-156">パスの矢印と数値は、 [Microsoft Teams の通話フロー](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)の記事に従っています。</span><span class="sxs-lookup"><span data-stu-id="a6e67-156">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="a6e67-157">SIP シグナリングは、常にパス3と 3 (トラフィックの方向によって異なります) を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-157">The SIP signaling always takes paths 3 and 3’ (depending on the direction of the traffic).</span></span> <span data-ttu-id="a6e67-158">パス2を使用したメディアフロー。</span><span class="sxs-lookup"><span data-stu-id="a6e67-158">Media flows using path 2.</span></span>

![ユーザーが SBC のパブリック IP へのアクセス権を持っていない場合のコールフローを示します。](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="a6e67-160">メディアプロセッサとトランスポートリレーの使用</span><span class="sxs-lookup"><span data-stu-id="a6e67-160">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="a6e67-161">メディアトラフィックのパスには、メディアプロセッサとトランスポートリレーという2つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-161">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="a6e67-162">メディアプロセッサは、非バイパスのケースでメディアを処理し、ボイスアプリケーションのメディアを処理するパブリックなフェーシングコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="a6e67-162">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="a6e67-163">メディアプロセッサは、常にエンドユーザーの非バイパス呼び出しのパスにありますが、バイパス呼び出しのパスには含まれません。</span><span class="sxs-lookup"><span data-stu-id="a6e67-163">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="a6e67-164">メディアプロセッサは、コールパーク、組織の自動応答、通話キューなど、すべての音声アプリケーションのパスに常に含まれています。</span><span class="sxs-lookup"><span data-stu-id="a6e67-164">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="a6e67-165">トランスポートリレーは、リアルタイムトラフィックを送信するために最も近いトランスポートサービスに接続するために使われます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-165">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="a6e67-166">トランスポート中継は、ユーザーがどこにいるかによって、またはエンドユーザーがどのように構成されているかに応じて、バイパスされた通話のパスに含まれている場合とできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-166">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="a6e67-167">次の図は、2つのコールフローを示しています。メディアのバイパスが有効で、もう1つはメディアバイパスが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="a6e67-167">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="a6e67-168">注図には、エンドユーザーからのトラフィックのみが示されます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-168">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="a6e67-169">メディアコントローラーは、メディアプロセッサを割り当て、セッション記述プロトコル (SDP) オファーを作成する Azure のマイクロサービスです。</span><span class="sxs-lookup"><span data-stu-id="a6e67-169">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="a6e67-170">SIP プロキシは、チームで使用される HTTP REST シグナリングを SIP に変換するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="a6e67-170">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

![メディアバイパスを有効または無効にしたコールフローを表示します](media/direct-routing-media-bypass-6.png)


<span data-ttu-id="a6e67-172">以下の表は、メディアプロセッサとトランスポートリレーの違いをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="a6e67-172">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="a6e67-173">メディアプロセッサ</span><span class="sxs-lookup"><span data-stu-id="a6e67-173">Media Processors</span></span> | <span data-ttu-id="a6e67-174">トランスポートリレー</span><span class="sxs-lookup"><span data-stu-id="a6e67-174">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="a6e67-175">エンドユーザーへの非バイパス呼び出しのメディアパス</span><span class="sxs-lookup"><span data-stu-id="a6e67-175">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="a6e67-176">いつも</span><span class="sxs-lookup"><span data-stu-id="a6e67-176">Always</span></span> | <span data-ttu-id="a6e67-177">ぜんぜん</span><span class="sxs-lookup"><span data-stu-id="a6e67-177">Never</span></span> | 
<span data-ttu-id="a6e67-178">エンドユーザーに対してバイパスされる通話のメディアパス</span><span class="sxs-lookup"><span data-stu-id="a6e67-178">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="a6e67-179">ぜんぜん</span><span class="sxs-lookup"><span data-stu-id="a6e67-179">Never</span></span> | <span data-ttu-id="a6e67-180">クライアントがパブリック IP アドレスの SBC に到達できない場合</span><span class="sxs-lookup"><span data-stu-id="a6e67-180">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="a6e67-181">ボイスアプリケーションのメディアパス</span><span class="sxs-lookup"><span data-stu-id="a6e67-181">In media path for voice applications</span></span> | <span data-ttu-id="a6e67-182">いつも</span><span class="sxs-lookup"><span data-stu-id="a6e67-182">Always</span></span> | <span data-ttu-id="a6e67-183">ぜんぜん</span><span class="sxs-lookup"><span data-stu-id="a6e67-183">Never</span></span> | 
<span data-ttu-id="a6e67-184">コード変換を実行できる (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="a6e67-184">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="a6e67-185">はい</span><span class="sxs-lookup"><span data-stu-id="a6e67-185">Yes</span></span> | <span data-ttu-id="a6e67-186">いいえ、エンドポイント間の音声のみを中継します</span><span class="sxs-lookup"><span data-stu-id="a6e67-186">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="a6e67-187">ワールドワイドおよび場所のインスタンス数</span><span class="sxs-lookup"><span data-stu-id="a6e67-187">Number of instances worldwide and location</span></span> | <span data-ttu-id="a6e67-188">8合計: 米国東部および西での22 (アムステルダムとダブリン)香港およびシンガポールでの2日本の 2 (Q1CY2019 に追加されています)</span><span class="sxs-lookup"><span data-stu-id="a6e67-188">8 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan (being added in Q1CY2019)</span></span>  | <span data-ttu-id="a6e67-189">多数</span><span class="sxs-lookup"><span data-stu-id="a6e67-189">Multiple</span></span>

<span data-ttu-id="a6e67-190">IP 範囲は 52.112.0.0/14 (IP アドレスは52.112.0.1 から 52.115.255.254) です。</span><span class="sxs-lookup"><span data-stu-id="a6e67-190">The IP range is 52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span> 

<span data-ttu-id="a6e67-191">\*コード変換の説明:</span><span class="sxs-lookup"><span data-stu-id="a6e67-191">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="a6e67-192">メディアプロセッサは B2BUA であることを意味します。つまり、SILK (Teams クライアントの場合は、MP と SBC の間の mp と G) に変更できます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-192">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="a6e67-193">トランスポートリレーは B2BUA ではありません。つまり、リレー経由でトラフィックが流れる場合でも、クライアントと SBC の間でコーデックが変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="a6e67-193">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-transport-relays-in-escalation-scenarios-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="a6e67-194">メディアバイパス用にトランクが構成されている場合のエスカレーションシナリオでの Teams トランスポートリレーの使用</span><span class="sxs-lookup"><span data-stu-id="a6e67-194">Use of Teams Transport Relays in escalation scenarios if trunk is configured for media bypass</span></span>

<span data-ttu-id="a6e67-195">Teams トランスポートリレーは、次のシナリオでは常にメディアパスにあります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-195">Teams Transport Relays are always in the media path in the following scenarios:</span></span>

- <span data-ttu-id="a6e67-196">通話は1:1 からグループ通話にエスカレートされます</span><span class="sxs-lookup"><span data-stu-id="a6e67-196">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="a6e67-197">フェデレーションされた Teams ユーザーに通話を発信する</span><span class="sxs-lookup"><span data-stu-id="a6e67-197">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="a6e67-198">通話が Skype for Business ユーザーに転送または転送される</span><span class="sxs-lookup"><span data-stu-id="a6e67-198">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="a6e67-199">以下で説明するように、SBC がトランスポートリレーにアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6e67-199">Ensure your SBC has access to the Transport Relays as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="a6e67-200">SIP シグナリング: Fqdn</span><span class="sxs-lookup"><span data-stu-id="a6e67-200">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="a6e67-201">SIP シグナリングの場合、FQDN とファイアウォールの要件は、非バイパスのケースと同じです。</span><span class="sxs-lookup"><span data-stu-id="a6e67-201">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="a6e67-202">直接ルーティングは、次の Office 365 環境で提供されます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-202">Direct Routing is offered in the following Office 365 environments:</span></span>
- <span data-ttu-id="a6e67-203">Office 365</span><span class="sxs-lookup"><span data-stu-id="a6e67-203">Office 365</span></span>
- <span data-ttu-id="a6e67-204">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="a6e67-204">Office 365 GCC</span></span>
- <span data-ttu-id="a6e67-205">Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="a6e67-205">Office 365 GCC High</span></span>
- <span data-ttu-id="a6e67-206">Office 365 DoD の詳細については、「GCC、GCC 高、DoD などの[office 365 および米国政府機関向けの環境](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6e67-206">Office 365 DoD Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="a6e67-207">Office 365 および Office 365 の GCC 環境</span><span class="sxs-lookup"><span data-stu-id="a6e67-207">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="a6e67-208">直接ルーティングの接続ポイントは、次の3つの Fqdn です。</span><span class="sxs-lookup"><span data-stu-id="a6e67-208">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="a6e67-209">**sip.pstnhub.microsoft.com** –グローバル FQDN –最初に試す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-209">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="a6e67-210">SBC がこの名前を解決するための要求を送信すると、Microsoft Azure DNS サーバーは、SBC に割り当てられているプライマリ Azure datacenter をポイントしている IP アドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="a6e67-210">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="a6e67-211">課題は、データセンターのパフォーマンスメトリックと SBC への地理的な距離に基づいています。</span><span class="sxs-lookup"><span data-stu-id="a6e67-211">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="a6e67-212">返される IP アドレスは、プライマリ FQDN に対応しています。</span><span class="sxs-lookup"><span data-stu-id="a6e67-212">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="a6e67-213">**sip2.pstnhub.microsoft.com** –セカンダリ FQDN –地理的に2番目の優先度の地域にマップされます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-213">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="a6e67-214">**sip3.pstnhub.microsoft.com** –第3の FQDN –地理的に3番目の優先度の地域にマップされます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-214">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="a6e67-215">次のために、これらの3つの Fqdn を配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-215">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="a6e67-216">最適なエクスペリエンスを提供します (読み込みが少なく、最初の FQDN を照会することによって割り当てられた SBC データセンターに最も近い)。</span><span class="sxs-lookup"><span data-stu-id="a6e67-216">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="a6e67-217">一時的な問題が発生しているデータセンターに対して SBC からの接続が確立された場合のフェールオーバーを提供します。</span><span class="sxs-lookup"><span data-stu-id="a6e67-217">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="a6e67-218">詳細については、以下の「フェールオーバーのメカニズム」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a6e67-218">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="a6e67-219">Fqdn **sip.pstnhub.microsoft.com**、 **sip2.pstnhub.microsoft.com**、および**sip3.pstnhub.microsoft.com**は、次のいずれかの IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-219">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="a6e67-220">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="a6e67-220">52.114.148.0</span></span>
- <span data-ttu-id="a6e67-221">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="a6e67-221">52.114.132.46</span></span>
- <span data-ttu-id="a6e67-222">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="a6e67-222">52.114.75.24</span></span>
- <span data-ttu-id="a6e67-223">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="a6e67-223">52.114.76.76</span></span>
- <span data-ttu-id="a6e67-224">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="a6e67-224">52.114.7.24</span></span>
- <span data-ttu-id="a6e67-225">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="a6e67-225">52.114.14.70</span></span>

<span data-ttu-id="a6e67-226">シグナリングのアドレスとの送受信トラフィックを許可するには、ファイアウォール内のすべての IP アドレスのポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-226">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="a6e67-227">ファイアウォールで DNS 名がサポートされている場合、FQDN **sip-all.pstnhub.microsoft.com**はこれらのすべての IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-227">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="a6e67-228">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="a6e67-228">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="a6e67-229">ダイレクトルーティングの接続ポイントは、次の FQDN です。</span><span class="sxs-lookup"><span data-stu-id="a6e67-229">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="a6e67-230">**sip.pstnhub.dod.teams.microsoft.us** –グローバル FQDN。</span><span class="sxs-lookup"><span data-stu-id="a6e67-230">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="a6e67-231">Office 365 DoD 環境は US データセンターにのみ存在するため、第2および第3の Fqdn はありません。</span><span class="sxs-lookup"><span data-stu-id="a6e67-231">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="a6e67-232">Fqdn – sip.pstnhub.dod.teams.microsoft.us は、次のいずれかの IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-232">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="a6e67-233">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="a6e67-233">52.127.64.33</span></span>
- <span data-ttu-id="a6e67-234">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="a6e67-234">52.127.68.34</span></span>

<span data-ttu-id="a6e67-235">シグナリングのアドレスとの送受信トラフィックを許可するには、ファイアウォール内のすべての IP アドレスのポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-235">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="a6e67-236">ファイアウォールで DNS 名がサポートされている場合、FQDN sip.pstnhub.dod.teams.microsoft.us はこれらのすべての IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-236">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="a6e67-237">Office 365 GCC 高環境</span><span class="sxs-lookup"><span data-stu-id="a6e67-237">Office 365 GCC High environment</span></span>

<span data-ttu-id="a6e67-238">ダイレクトルーティングの接続ポイントは、次の FQDN です。</span><span class="sxs-lookup"><span data-stu-id="a6e67-238">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="a6e67-239">**sip.pstnhub.gov.teams.microsoft.us** –グローバル FQDN。</span><span class="sxs-lookup"><span data-stu-id="a6e67-239">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="a6e67-240">GCC 高環境は US データセンターにのみ存在するため、第2の Fqdn はありません。</span><span class="sxs-lookup"><span data-stu-id="a6e67-240">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="a6e67-241">Fqdn – sip.pstnhub.gov.teams.microsoft.us は、次のいずれかの IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-241">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="a6e67-242">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="a6e67-242">52.127.88.59</span></span>
- <span data-ttu-id="a6e67-243">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="a6e67-243">52.127.92.64</span></span>

<span data-ttu-id="a6e67-244">シグナリングのアドレスとの送受信トラフィックを許可するには、ファイアウォール内のすべての IP アドレスのポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-244">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="a6e67-245">ファイアウォールで DNS 名がサポートされている場合、FQDN sip.pstnhub.gov.teams.microsoft.us はこれらのすべての IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-245">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="a6e67-246">SIP シグナリング: ポート</span><span class="sxs-lookup"><span data-stu-id="a6e67-246">SIP Signaling: Ports</span></span>

<span data-ttu-id="a6e67-247">ダイレクトルーティングが提供されているすべての Office 365 環境では、ポート要件は同じです。</span><span class="sxs-lookup"><span data-stu-id="a6e67-247">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="a6e67-248">Office 365</span><span class="sxs-lookup"><span data-stu-id="a6e67-248">Office 365</span></span>
- <span data-ttu-id="a6e67-249">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="a6e67-249">Office 365 GCC</span></span>
- <span data-ttu-id="a6e67-250">Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="a6e67-250">Office 365 GCC High</span></span>
- <span data-ttu-id="a6e67-251">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="a6e67-251">Office 365 DoD</span></span>

<span data-ttu-id="a6e67-252">次のポートを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-252">You must use the following ports:</span></span>

| <span data-ttu-id="a6e67-253">通過</span><span class="sxs-lookup"><span data-stu-id="a6e67-253">Traffic</span></span> | <span data-ttu-id="a6e67-254">開始</span><span class="sxs-lookup"><span data-stu-id="a6e67-254">From</span></span> | <span data-ttu-id="a6e67-255">終了</span><span class="sxs-lookup"><span data-stu-id="a6e67-255">To</span></span> | <span data-ttu-id="a6e67-256">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="a6e67-256">Source port</span></span> | <span data-ttu-id="a6e67-257">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="a6e67-257">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="a6e67-258">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="a6e67-258">SIP/TLS</span></span>| <span data-ttu-id="a6e67-259">SIP プロキシ</span><span class="sxs-lookup"><span data-stu-id="a6e67-259">SIP Proxy</span></span> | <span data-ttu-id="a6e67-260">SBC</span><span class="sxs-lookup"><span data-stu-id="a6e67-260">SBC</span></span> | <span data-ttu-id="a6e67-261">1024-65535</span><span class="sxs-lookup"><span data-stu-id="a6e67-261">1024 - 65535</span></span> | <span data-ttu-id="a6e67-262">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="a6e67-262">Defined on the SBC</span></span> |
| <span data-ttu-id="a6e67-263">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="a6e67-263">SIP/TLS</span></span> | <span data-ttu-id="a6e67-264">SBC</span><span class="sxs-lookup"><span data-stu-id="a6e67-264">SBC</span></span> | <span data-ttu-id="a6e67-265">SIP プロキシ</span><span class="sxs-lookup"><span data-stu-id="a6e67-265">SIP Proxy</span></span> | <span data-ttu-id="a6e67-266">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="a6e67-266">Defined on the SBC</span></span> | <span data-ttu-id="a6e67-267">5061</span><span class="sxs-lookup"><span data-stu-id="a6e67-267">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="a6e67-268">メディアトラフィック: IP とポートの範囲</span><span class="sxs-lookup"><span data-stu-id="a6e67-268">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="a6e67-269">直接接続が利用できるか、またはクライアントがパブリック IP アドレスを使用して SBC に到達できない場合は、SBC と Teams クライアント間でメディアトラフィックが流れます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-269">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="a6e67-270">ダイレクトメディアトラフィック (Teams クライアントと SBC の間) の要件</span><span class="sxs-lookup"><span data-stu-id="a6e67-270">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="a6e67-271">クライアントは、SBC のパブリック IP アドレスで指定されたポート (表を参照) にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-271">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="a6e67-272">注: クライアントが内部ネットワーク内にある場合、メディアは SBC のパブリック IP アドレスに送られます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-272">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="a6e67-273">NAT デバイスで hairpinning を構成して、トラフィックが企業ネットワーク機器を離れることがないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-273">You can configure hairpinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="a6e67-274">通過</span><span class="sxs-lookup"><span data-stu-id="a6e67-274">Traffic</span></span> | <span data-ttu-id="a6e67-275">開始</span><span class="sxs-lookup"><span data-stu-id="a6e67-275">From</span></span> | <span data-ttu-id="a6e67-276">終了</span><span class="sxs-lookup"><span data-stu-id="a6e67-276">To</span></span> | <span data-ttu-id="a6e67-277">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="a6e67-277">Source port</span></span> | <span data-ttu-id="a6e67-278">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="a6e67-278">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="a6e67-279">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a6e67-279">UDP/SRTP</span></span> | <span data-ttu-id="a6e67-280">クライアント</span><span class="sxs-lookup"><span data-stu-id="a6e67-280">Client</span></span> | <span data-ttu-id="a6e67-281">SBC</span><span class="sxs-lookup"><span data-stu-id="a6e67-281">SBC</span></span> | <span data-ttu-id="a6e67-282">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="a6e67-282">50 000 – 50 019</span></span>  | <span data-ttu-id="a6e67-283">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="a6e67-283">Defined on the SBC</span></span> |
| <span data-ttu-id="a6e67-284">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a6e67-284">UDP/SRTP</span></span> | <span data-ttu-id="a6e67-285">SBC</span><span class="sxs-lookup"><span data-stu-id="a6e67-285">SBC</span></span> | <span data-ttu-id="a6e67-286">クライアント</span><span class="sxs-lookup"><span data-stu-id="a6e67-286">Client</span></span> | <span data-ttu-id="a6e67-287">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="a6e67-287">Defined on the SBC</span></span> | <span data-ttu-id="a6e67-288">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="a6e67-288">50 000 – 50 019</span></span>  |


<span data-ttu-id="a6e67-289">注: クライアントのソースポートを変換するネットワークデバイスがある場合は、ネットワーク機器と SBC の間で変換されたポートが開かれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a6e67-289">Note: If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="a6e67-290">トランスポートリレーを使用するための要件</span><span class="sxs-lookup"><span data-stu-id="a6e67-290">Requirements for using Transport Relays</span></span>

<span data-ttu-id="a6e67-291">トランスポートリレーは、メディアプロセッサ (バイパス以外のケース) と同じ範囲にあります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-291">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="a6e67-292">Office 365 および Office 365 の GCC 環境</span><span class="sxs-lookup"><span data-stu-id="a6e67-292">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="a6e67-293">-52.112.0.0/14 (52.112.0.1 から52.115.255.254 への IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="a6e67-293">-52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="a6e67-294">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="a6e67-294">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="a6e67-295">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="a6e67-295">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="a6e67-296">Office 365 GCC 高環境</span><span class="sxs-lookup"><span data-stu-id="a6e67-296">Office 365 GCC High environment</span></span>

- <span data-ttu-id="a6e67-297">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="a6e67-297">52.127.88.0/21</span></span>


<span data-ttu-id="a6e67-298">Teams トランスポートリレーのポート範囲 (すべての環境に適用されます) については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6e67-298">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="a6e67-299">通過</span><span class="sxs-lookup"><span data-stu-id="a6e67-299">Traffic</span></span> | <span data-ttu-id="a6e67-300">開始</span><span class="sxs-lookup"><span data-stu-id="a6e67-300">From</span></span> | <span data-ttu-id="a6e67-301">終了</span><span class="sxs-lookup"><span data-stu-id="a6e67-301">To</span></span> | <span data-ttu-id="a6e67-302">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="a6e67-302">Source port</span></span> | <span data-ttu-id="a6e67-303">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="a6e67-303">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="a6e67-304">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a6e67-304">UDP/SRTP</span></span> | <span data-ttu-id="a6e67-305">トランスポートリレー</span><span class="sxs-lookup"><span data-stu-id="a6e67-305">Transport Relay</span></span> | <span data-ttu-id="a6e67-306">SBC</span><span class="sxs-lookup"><span data-stu-id="a6e67-306">SBC</span></span> | <span data-ttu-id="a6e67-307">50 000-59 999</span><span class="sxs-lookup"><span data-stu-id="a6e67-307">50 000 -59 999</span></span>    | <span data-ttu-id="a6e67-308">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="a6e67-308">Defined on the SBC</span></span> |
| <span data-ttu-id="a6e67-309">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a6e67-309">UDP/SRTP</span></span> | <span data-ttu-id="a6e67-310">SBC</span><span class="sxs-lookup"><span data-stu-id="a6e67-310">SBC</span></span> | <span data-ttu-id="a6e67-311">トランスポートリレー</span><span class="sxs-lookup"><span data-stu-id="a6e67-311">Transport Relay</span></span> | <span data-ttu-id="a6e67-312">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="a6e67-312">Defined on the SBC</span></span> | <span data-ttu-id="a6e67-313">50 000 – 59 999、3478、3479</span><span class="sxs-lookup"><span data-stu-id="a6e67-313">50 000 – 59 999, 3478, 3479</span></span>     |


<span data-ttu-id="a6e67-314">注: SBC では、同時通話ごとに少なくとも2つのポートが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-314">Note: Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="a6e67-315">Microsoft にはトランスポートリレーの2つのバージョンがあるため、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="a6e67-315">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>

- <span data-ttu-id="a6e67-316">v4 (ポート範囲 59 999 50 000 でのみ使用可能)</span><span class="sxs-lookup"><span data-stu-id="a6e67-316">v4, which can only work with port range 50 000 to 59 999</span></span>

- <span data-ttu-id="a6e67-317">v6 (ポート3478、3479と連携)</span><span class="sxs-lookup"><span data-stu-id="a6e67-317">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="a6e67-318">現時点では、メディアバイパスは、トランスポートリレーの v4 バージョンのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a6e67-318">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="a6e67-319">今後、v6 のサポートが導入される予定です。</span><span class="sxs-lookup"><span data-stu-id="a6e67-319">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="a6e67-320">移行するには、ポート3478と3479を開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-320">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="a6e67-321">Microsoft がメディアバイパスでの v6 トランスポートリレーのサポートを導入する場合、ネットワーク機器または SBCs を再設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a6e67-321">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="a6e67-322">メディアプロセッサを使うための要件</span><span class="sxs-lookup"><span data-stu-id="a6e67-322">Requirements for using media processors</span></span>

<span data-ttu-id="a6e67-323">メディアプロセッサは、常にボイスアプリケーションと Web cleints (exampe の場合は、Edge または Google Chrome の Teams cleint のメディアパス) にあります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-323">Media Processors are always in the media path for voice applications and for Web cleints (for exampe, Teams cleint in Edge or Google Chrome).</span></span> <span data-ttu-id="a6e67-324">要件は、非バイパス構成の場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="a6e67-324">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="a6e67-325">メディアトラフィックの IP 範囲は</span><span class="sxs-lookup"><span data-stu-id="a6e67-325">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="a6e67-326">Office 365 および Office 365 の GCC 環境</span><span class="sxs-lookup"><span data-stu-id="a6e67-326">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="a6e67-327">-52.112.0.0/14 (52.112.0.1 から52.115.255.254 への IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="a6e67-327">-52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="a6e67-328">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="a6e67-328">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="a6e67-329">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="a6e67-329">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="a6e67-330">Office 365 GCC 高環境</span><span class="sxs-lookup"><span data-stu-id="a6e67-330">Office 365 GCC High environment</span></span>

- <span data-ttu-id="a6e67-331">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="a6e67-331">52.127.88.0/21</span></span>

<span data-ttu-id="a6e67-332">メディアプロセッサのポート範囲 (すべての環境に該当) を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="a6e67-332">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="a6e67-333">通過</span><span class="sxs-lookup"><span data-stu-id="a6e67-333">Traffic</span></span> | <span data-ttu-id="a6e67-334">開始</span><span class="sxs-lookup"><span data-stu-id="a6e67-334">From</span></span> | <span data-ttu-id="a6e67-335">終了</span><span class="sxs-lookup"><span data-stu-id="a6e67-335">To</span></span> | <span data-ttu-id="a6e67-336">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="a6e67-336">Source port</span></span> | <span data-ttu-id="a6e67-337">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="a6e67-337">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="a6e67-338">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a6e67-338">UDP/SRTP</span></span> | <span data-ttu-id="a6e67-339">メディアプロセッサ</span><span class="sxs-lookup"><span data-stu-id="a6e67-339">Media Processor</span></span> | <span data-ttu-id="a6e67-340">SBC</span><span class="sxs-lookup"><span data-stu-id="a6e67-340">SBC</span></span> | <span data-ttu-id="a6e67-341">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="a6e67-341">49 152 – 53 247</span></span>    | <span data-ttu-id="a6e67-342">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="a6e67-342">Defined on the SBC</span></span> |
| <span data-ttu-id="a6e67-343">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a6e67-343">UDP/SRTP</span></span> | <span data-ttu-id="a6e67-344">SBC</span><span class="sxs-lookup"><span data-stu-id="a6e67-344">SBC</span></span> | <span data-ttu-id="a6e67-345">メディアプロセッサ</span><span class="sxs-lookup"><span data-stu-id="a6e67-345">Media Processor</span></span> | <span data-ttu-id="a6e67-346">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="a6e67-346">Defined on the SBC</span></span> | <span data-ttu-id="a6e67-347">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="a6e67-347">49 152 – 53 247</span></span>     |

## <a name="considerations-if-you-have-skype-for-business-phones-in-your-network"></a><span data-ttu-id="a6e67-348">ネットワークで Skype for Business 電話を使用している場合の考慮事項</span><span class="sxs-lookup"><span data-stu-id="a6e67-348">Considerations if you have Skype for Business phones in your network</span></span>  

<span data-ttu-id="a6e67-349">直接ルーティングを使用しているネットワーク内の Skype for Business エンドポイントがある場合、チームユーザーは、Skype for Business クライアントに基づく3PIP 電話を持つことができます。これらのユーザーに対応しているトランクでのメディアのバイパスは、無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-349">If you have any Skype for Business end points in your network that are using Direct Routing--for example, a Teams user can have a 3PIP phone that is based on Skype for Business client--the media bypass on the trunk that serves these users must be turned off.</span></span>

<span data-ttu-id="a6e67-350">これらのユーザーに対して個別のトランクを作成し、オンラインボイスルーティングポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-350">You can create a separate trunk for these users and assign it an Online Voice Routing policy.</span></span>

<span data-ttu-id="a6e67-351">高レベルの構成手順:</span><span class="sxs-lookup"><span data-stu-id="a6e67-351">High-level configuration steps:</span></span>

- <span data-ttu-id="a6e67-352">ユーザーが3PIP 電話を使っているかどうかに応じて、種類によってユーザーを分割します。</span><span class="sxs-lookup"><span data-stu-id="a6e67-352">Split users by type – depending on whether the user has a 3PIP phone or not.</span></span>

- <span data-ttu-id="a6e67-353">異なる Fqdn を使用して2つの別個の trunks を作成します。1つはメディアバイパス用です。それ以外の場合は、</span><span class="sxs-lookup"><span data-stu-id="a6e67-353">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="a6e67-354">どちらの trunks も、同じ SBC をポイントします。</span><span class="sxs-lookup"><span data-stu-id="a6e67-354">Both trunks point to the same SBC.</span></span> <span data-ttu-id="a6e67-355">TLS SIP シグナリングのポートは異なっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-355">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="a6e67-356">メディアのポートは同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-356">The ports for media must be the same.</span></span>

- <span data-ttu-id="a6e67-357">オンラインボイスルーティングポリシーのユーザのタイプに応じて、正しいトランクを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-357">Assign the correct trunk depending on the type of the user in the Online Voice Routing policy.</span></span>

<span data-ttu-id="a6e67-358">次の例は、このロジックを示しています。</span><span class="sxs-lookup"><span data-stu-id="a6e67-358">The example below illustrates this logic.</span></span>

| <span data-ttu-id="a6e67-359">ユーザーのセット</span><span class="sxs-lookup"><span data-stu-id="a6e67-359">Set of users</span></span> | <span data-ttu-id="a6e67-360">ユーザー数</span><span class="sxs-lookup"><span data-stu-id="a6e67-360">Number of users</span></span> | <span data-ttu-id="a6e67-361">"の順番で割り当てられたトランクの FQDN</span><span class="sxs-lookup"><span data-stu-id="a6e67-361">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="a6e67-362">メディアのバイパスを有効にする</span><span class="sxs-lookup"><span data-stu-id="a6e67-362">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="a6e67-363">Teams クライアントと3PIP 電話を使用するユーザー</span><span class="sxs-lookup"><span data-stu-id="a6e67-363">Users with Teams clients and 3PIP phones</span></span> | <span data-ttu-id="a6e67-364">超える</span><span class="sxs-lookup"><span data-stu-id="a6e67-364">20</span></span> | <span data-ttu-id="a6e67-365">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="a6e67-365">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="a6e67-366">false</span><span class="sxs-lookup"><span data-stu-id="a6e67-366">false</span></span> | 
<span data-ttu-id="a6e67-367">チームのエンドポイントのみを持つユーザー (Teams で認定された新しい電話を含む)</span><span class="sxs-lookup"><span data-stu-id="a6e67-367">Users with only Teams end points (including new phones certified for Teams)</span></span> | <span data-ttu-id="a6e67-368">980</span><span class="sxs-lookup"><span data-stu-id="a6e67-368">980</span></span> | <span data-ttu-id="a6e67-369">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="a6e67-369">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="a6e67-370">true</span><span class="sxs-lookup"><span data-stu-id="a6e67-370">true</span></span>

<span data-ttu-id="a6e67-371">どちらの trunks も、同じ SBC を同じパブリック IP アドレスで指すことができます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-371">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="a6e67-372">次の図に示すように、SBC の TLS シグナリングポートは異なっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-372">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="a6e67-373">注: 証明書で trunks の両方がサポートされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-373">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="a6e67-374">SAN では、2つの名前 (**sbc1.contoso.com**と**sbc2.contoso.com**) を使用するか、ワイルドカード証明書を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e67-374">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>


![両方の trunks が同じ SBC をポイントし、同じパブリック IP アドレスを持つことを示します。](media/direct-routing-media-bypass-7.png)

<span data-ttu-id="a6e67-376">同じ SBC で2つの trunks を構成する方法については、SBC ベンダーから提供されているドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6e67-376">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="a6e67-377">AudioCodes の展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="a6e67-377">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="a6e67-378">Oracle 展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="a6e67-378">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="a6e67-379">リボンの通信展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="a6e67-379">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="a6e67-380">TE システム (anynode) の展開ドキュメント</span><span class="sxs-lookup"><span data-stu-id="a6e67-380">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="a6e67-381">メディアバイパスでサポートされているクライアントエンドポイント</span><span class="sxs-lookup"><span data-stu-id="a6e67-381">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="a6e67-382">メディアのバイパスは、すべてのチームのエンドポイントでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a6e67-382">Media bypass is supported with all Teams endpoints.</span></span>

<span data-ttu-id="a6e67-383">注 webcleints (Microsoft Edge、Google Chrome、Mozilla Firefox の Teams Web アプリ) では、着信がバイパスの呼び出しとして開始されても、バイパスなしに変換されます。</span><span class="sxs-lookup"><span data-stu-id="a6e67-383">Note for webcleints (Teams Web app in Microsoft Edge, Google Chrome or Mozilla Firefox) we will covert the call to non-bypass even of it started as a bypass call.</span></span> <span data-ttu-id="a6e67-384">これは自動的に行われるため、管理者に対して操作を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a6e67-384">This happens automatically and does not require any actions on the administrator.</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="a6e67-385">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6e67-385">See also</span></span>

[<span data-ttu-id="a6e67-386">ダイレクト ルーティングでメディア バイパスを構成する</span><span class="sxs-lookup"><span data-stu-id="a6e67-386">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)



