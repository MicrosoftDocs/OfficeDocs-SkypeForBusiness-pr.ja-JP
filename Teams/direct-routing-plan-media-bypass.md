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
description: メディア トラフィックのパスを短くし、パフォーマンスを向上できる電話システム ダイレクト ルーティングを使用してメディア バイパスを計画する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bbd31a62bf6ebcd481a3cdafeabaf29bb4767f2d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115595"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="9da77-103">ダイレクト ルーティングでメディア バイパスを計画する</span><span class="sxs-lookup"><span data-stu-id="9da77-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="9da77-104">ダイレクト ルーティングを使用したメディア バイパスについて</span><span class="sxs-lookup"><span data-stu-id="9da77-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="9da77-105">メディア バイパスを使用すると、メディア トラフィックのパスを短くし、送信中のホップ数を減らしてパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="9da77-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="9da77-106">メディア バイパスを使用すると、Microsoft Phone System 経由で送信する代わりに、メディアはセッション ボーダー コントローラー (SBC) とクライアントの間に保持されます。</span><span class="sxs-lookup"><span data-stu-id="9da77-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="9da77-107">メディア バイパスを構成するには、SBC とクライアントが同じ場所またはネットワークにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="9da77-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="9da77-108">各 SBC のメディア バイパスを制御するには **、-MediaBypass** パラメーターを true または false に設定して **Set-CSOnlinePSTNGateway** コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="9da77-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="9da77-109">メディア バイパスを有効にしても、すべてのメディア トラフィックが企業ネットワーク内に残るという意味ではありません。</span><span class="sxs-lookup"><span data-stu-id="9da77-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="9da77-110">この記事では、さまざまなシナリオでのコール フローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9da77-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="9da77-111">次の図は、メディア バイパスの場合とない場合のコール フローの違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="9da77-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="9da77-112">次の図に示すように、メディア バイパスなしで、クライアントが通話を行う場合や受信するときに、SBC、Microsoft Phone System、Teams クライアント間のシグナリングとメディア フローの両方を行います。</span><span class="sxs-lookup"><span data-stu-id="9da77-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9da77-113">![メディア バイパスなしのシグナリングとメディア フローを示す](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="9da77-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="9da77-114">ただし、ユーザーが SBC と同じ建物またはネットワークにいます。</span><span class="sxs-lookup"><span data-stu-id="9da77-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="9da77-115">たとえば、一部の場所にいたユーザーが Pstn ユーザーに対して通話を発信するとします。</span><span class="sxs-lookup"><span data-stu-id="9da77-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="9da77-116">**メディア バイパスを使用しない** 場合、メディアは、アムステルダムまたはダブリン (Microsoft データセンターが展開されている場所) を経由してメディアが流れ、その後、しずけの SBC に戻されます。</span><span class="sxs-lookup"><span data-stu-id="9da77-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="9da77-117">ヨーロッパのデータセンターは、SBC がヨーロッパに存在し、Microsoft が SBC に最も近いデータセンターを使用するために選択されます。</span><span class="sxs-lookup"><span data-stu-id="9da77-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="9da77-118">この方法は、ほとんどの地域で Microsoft ネットワーク内のトラフィック フローの最適化のために通話品質に影響しませんが、トラフィックには不必要なループがあります。</span><span class="sxs-lookup"><span data-stu-id="9da77-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="9da77-119">**メディア バイパスを使用** すると、次の図に示すように、メディアは Teams ユーザーと SBC の間に直接保持されます。</span><span class="sxs-lookup"><span data-stu-id="9da77-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="9da77-120">![メディア バイパスによるシグナリングとメディア フローの表示](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="9da77-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="9da77-121">メディア バイパスは、Teams クライアント上の Interactive Connectivity Connectivity(ICE) と呼ばれるプロトコルと SBC の ICE lite を利用します。</span><span class="sxs-lookup"><span data-stu-id="9da77-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="9da77-122">これらのプロトコルを使用すると、ダイレクト ルーティングで最適な品質を得る最適なメディア パスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9da77-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="9da77-123">ICE と ICE Lite は WebRTC 標準です。</span><span class="sxs-lookup"><span data-stu-id="9da77-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="9da77-124">これらのプロトコルの詳細については、RFC 5245 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9da77-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="9da77-125">コール フローとファイアウォールの計画</span><span class="sxs-lookup"><span data-stu-id="9da77-125">Call flow and firewall planning</span></span>

<span data-ttu-id="9da77-126">コール フローとファイアウォールの計画は、ユーザーが SBC のパブリック IP アドレスに直接アクセスできるかどうか、およびユーザーがネットワークの内部か外部かによって異なります。</span><span class="sxs-lookup"><span data-stu-id="9da77-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="9da77-127">ユーザーが SBC のパブリック IP アドレスに直接アクセスできる場合のコール フロー</span><span class="sxs-lookup"><span data-stu-id="9da77-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="9da77-128">ユーザーが SBC のパブリック IP アドレスに直接アクセスできる場合、コール フローは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9da77-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="9da77-129">メディア バイパスの場合、Teams クライアントは内部ネットワークからでも SBC のパブリック IP アドレスにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9da77-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="9da77-130">直接メディアが必要ない場合、メディアはトランスポート リレー経由で流れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9da77-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="9da77-131">これは、ユーザーが SBC と同じ建物またはネットワーク上にある場合に推奨されるソリューションです。メディア パスから Microsoft Cloud コンポーネントを削除します。</span><span class="sxs-lookup"><span data-stu-id="9da77-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="9da77-132">シグナリングは常に Microsoft クラウド経由で流れます。</span><span class="sxs-lookup"><span data-stu-id="9da77-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="9da77-133">次の図は、メディア バイパスが有効になっている場合、クライアントが内部であり、クライアントが SBC (直接メディア) のパブリック IP アドレスに到達できる場合のコール フローを示しています。</span><span class="sxs-lookup"><span data-stu-id="9da77-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="9da77-134">パスの矢印と数値は、Microsoft Teams のコール フロー [に準拠しています](./microsoft-teams-online-call-flows.md)。</span><span class="sxs-lookup"><span data-stu-id="9da77-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="9da77-135">SIP シグナリングは常にパス 4 と 4' を受け取ります (トラフィックの方向に応じて異なる)。</span><span class="sxs-lookup"><span data-stu-id="9da77-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="9da77-136">メディアはローカルのままで、パス 5b を受け取る。</span><span class="sxs-lookup"><span data-stu-id="9da77-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9da77-137">![メディア バイパスが有効になっている通話フロー、クライアントが内部である](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="9da77-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="9da77-138">ユーザーが SBC のパブリック IP アドレスにアクセスできない場合のコール フロー</span><span class="sxs-lookup"><span data-stu-id="9da77-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="9da77-139">次に、ユーザーが SBC のパブリック IP アドレスにアクセスできない場合のコール フローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9da77-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="9da77-140">たとえば、ユーザーが外部ユーザーであり、テナント管理者が SBC のパブリック IP アドレスをインターネット上のすべてのユーザーに対して開くのではなく、Microsoft Cloud にのみ開くことを決定したとします。</span><span class="sxs-lookup"><span data-stu-id="9da77-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="9da77-141">トラフィックの内部コンポーネントは、Teams トランスポート リレーを介してフローできます。</span><span class="sxs-lookup"><span data-stu-id="9da77-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="9da77-142">次の状況について検討しましょう。</span><span class="sxs-lookup"><span data-stu-id="9da77-142">Consider the following:</span></span>

- <span data-ttu-id="9da77-143">Teams トランスポート リレーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="9da77-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="9da77-144">メディア バイパスの場合、Microsoft は、Teams トランスポート リレーと SBC の間にポート 50 000 から 59 999 を開く必要があるトランスポート リレーのバージョンを使用します (今後、3478 ポートと 3479 ポートのみを必要とするバージョンに移行する予定です)。</span><span class="sxs-lookup"><span data-stu-id="9da77-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>


<span data-ttu-id="9da77-145">次の図は、メディア バイパスが有効になっている場合、クライアントが外部であり、クライアントがセッション ボーダー コントローラーのパブリック IP アドレスに到達できない場合のコール フローを示しています (メディアは Teams トランスポート リレーによって中継されます)。</span><span class="sxs-lookup"><span data-stu-id="9da77-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="9da77-146">パスの矢印と数値は、Microsoft Teams のコール フロー [に準拠しています](./microsoft-teams-online-call-flows.md)。</span><span class="sxs-lookup"><span data-stu-id="9da77-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="9da77-147">メディアは、パス 3、3'、4、4' を介して中継されます。</span><span class="sxs-lookup"><span data-stu-id="9da77-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9da77-148">![ユーザーが SBC のパブリック IP にアクセスできない場合のコール フローを示す](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="9da77-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="9da77-149">ユーザーがネットワークの外にいて、SBC のパブリック IP にアクセスできる場合のコール フロー</span><span class="sxs-lookup"><span data-stu-id="9da77-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="9da77-150">これは、Teams トランスポート リレーを利用しないので、推奨される構成ではありません。</span><span class="sxs-lookup"><span data-stu-id="9da77-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="9da77-151">代わりに、ユーザーが SBC のパブリック IP アドレスにアクセスできない前のシナリオを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9da77-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="9da77-152">次の図は、メディア バイパスが有効になっている場合、クライアントが外部であり、クライアントが SBC (ダイレクト メディア) のパブリック IP アドレスに到達できる場合のコール フローを示しています。</span><span class="sxs-lookup"><span data-stu-id="9da77-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="9da77-153">パスの矢印と数値は [、Microsoft Teams](./microsoft-teams-online-call-flows.md) のコール フロー記事に従っています。</span><span class="sxs-lookup"><span data-stu-id="9da77-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md) article.</span></span>

- <span data-ttu-id="9da77-154">SIP シグナリングは常にパス 3 と 3' を受け取ります (トラフィックの方向に応じて異なる)。</span><span class="sxs-lookup"><span data-stu-id="9da77-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="9da77-155">パス 2 を使用したメディア フロー。</span><span class="sxs-lookup"><span data-stu-id="9da77-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9da77-156">![ユーザーが SBC のパブリック IP にアクセスできない場合のコール フローを示す](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="9da77-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="9da77-157">メディア プロセッサとトランスポート リレーの使用</span><span class="sxs-lookup"><span data-stu-id="9da77-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="9da77-158">メディア トラフィックのパスに含み得る、メディア プロセッサとトランスポート リレーの 2 つのコンポーネントが Microsoft Cloud に含まれています。</span><span class="sxs-lookup"><span data-stu-id="9da77-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="9da77-159">メディア プロセッサは、バイパスしないケースでメディアを処理し、音声アプリケーション用のメディアを処理する一般向けのコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="9da77-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="9da77-160">メディア プロセッサは常に、エンド ユーザーのバイパスされていない呼び出しのパスに入っていますが、バイパスされた呼び出しのパスには入ってこない。</span><span class="sxs-lookup"><span data-stu-id="9da77-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="9da77-161">メディア プロセッサは常に、コール パーク、組織の管理、通話キューなどのすべての音声自動応答パスにあります。</span><span class="sxs-lookup"><span data-stu-id="9da77-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="9da77-162">トランスポート リレーは、リアルタイム トラフィックを送信するために最も近いトランスポート サービスに接続するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9da77-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="9da77-163">トランスポート リレーは、ユーザーの場所とネットワークの構成方法に応じて、バイパスされた通話 (発信元またはエンド ユーザー宛て) のパス内にある場合とない場合があります。</span><span class="sxs-lookup"><span data-stu-id="9da77-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="9da77-164">次の図は、2 つのコール フローを示しています。1 つはメディア バイパスが有効で、もう 1 つはメディア バイパスが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="9da77-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="9da77-165">この図は、エンド ユーザーから送信されるトラフィックまたは宛先のユーザーのみを示しています。</span><span class="sxs-lookup"><span data-stu-id="9da77-165">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="9da77-166">メディア コントローラーは、メディア プロセッサを割り当て、SDP (Session Description Protocol) オファーを作成する Azure のマイクロサービスです。</span><span class="sxs-lookup"><span data-stu-id="9da77-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="9da77-167">SIP プロキシは、Teams で使用される HTTP REST シグナリングを SIP に変換するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="9da77-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9da77-168">![メディア バイパスが有効または無効になっているコール フローを示す](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="9da77-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="9da77-169">次の表は、メディア プロセッサとトランスポート リレーの違いをまとめた表です。</span><span class="sxs-lookup"><span data-stu-id="9da77-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="9da77-170">メディア プロセッサ</span><span class="sxs-lookup"><span data-stu-id="9da77-170">Media Processors</span></span> | <span data-ttu-id="9da77-171">トランスポート リレー</span><span class="sxs-lookup"><span data-stu-id="9da77-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="9da77-172">エンド ユーザーのバイパスされていない呼び出しのメディア パス内</span><span class="sxs-lookup"><span data-stu-id="9da77-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="9da77-173">いつも</span><span class="sxs-lookup"><span data-stu-id="9da77-173">Always</span></span> | <span data-ttu-id="9da77-174">クライアントがメディア プロセッサに直接到達できない場合</span><span class="sxs-lookup"><span data-stu-id="9da77-174">If client cannot reach the Media Processor directly</span></span> | 
<span data-ttu-id="9da77-175">エンド ユーザーのバイパス呼び出しのメディア パス</span><span class="sxs-lookup"><span data-stu-id="9da77-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="9da77-176">ぜんぜん</span><span class="sxs-lookup"><span data-stu-id="9da77-176">Never</span></span> | <span data-ttu-id="9da77-177">クライアントがパブリック IP アドレスで SBC に到達できない場合</span><span class="sxs-lookup"><span data-stu-id="9da77-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="9da77-178">音声アプリケーションのメディア パス内</span><span class="sxs-lookup"><span data-stu-id="9da77-178">In media path for voice applications</span></span> | <span data-ttu-id="9da77-179">いつも</span><span class="sxs-lookup"><span data-stu-id="9da77-179">Always</span></span> | <span data-ttu-id="9da77-180">ぜんぜん</span><span class="sxs-lookup"><span data-stu-id="9da77-180">Never</span></span> | 
<span data-ttu-id="9da77-181">コード変換を実行できる (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="9da77-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="9da77-182">はい</span><span class="sxs-lookup"><span data-stu-id="9da77-182">Yes</span></span> | <span data-ttu-id="9da77-183">いいえ、エンドポイント間のオーディオのみを中継します</span><span class="sxs-lookup"><span data-stu-id="9da77-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="9da77-184">世界中のインスタンスの数と場所</span><span class="sxs-lookup"><span data-stu-id="9da77-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="9da77-185">合計 10: 米国東部と西部で 2。2 in Dublin and Dublin;香港とシンガポールの 2。日本の 2 ;オーストラリア東部と東南部の 2</span><span class="sxs-lookup"><span data-stu-id="9da77-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="9da77-186">倍数</span><span class="sxs-lookup"><span data-stu-id="9da77-186">Multiple</span></span>

<span data-ttu-id="9da77-187">IP 範囲は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9da77-187">The IP ranges are:</span></span>
- <span data-ttu-id="9da77-188">52.112.0.0/14 (52.112.0.1 から 52.115.255.254 の IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="9da77-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="9da77-189">52.120.0.0/14 (52.120.0.1 から 52.123.255.254 の IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="9da77-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="9da77-190">\* コード変換の説明:</span><span class="sxs-lookup"><span data-stu-id="9da77-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="9da77-191">Media Processor は B2BUA です。つまり、コーデックを変更できます (たとえば、SILK を Teams クライアントから MP と G.711 に MP と SBC の間で変更できます)。</span><span class="sxs-lookup"><span data-stu-id="9da77-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="9da77-192">トランスポート リレーは B2BUA ではありません。つまり、リレー経由でトラフィックが流れる場合でも、クライアントと SBC の間でコーデックが変更される必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9da77-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="9da77-193">トランクがメディア バイパス用に構成されている場合の Teams メディア プロセッサの使用</span><span class="sxs-lookup"><span data-stu-id="9da77-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="9da77-194">Teams Media Processors は、次のシナリオでは常にメディア パスに挿入されます。</span><span class="sxs-lookup"><span data-stu-id="9da77-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="9da77-195">通話は 1:1 からグループ通話にエスカレートされます</span><span class="sxs-lookup"><span data-stu-id="9da77-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="9da77-196">フェデレーション Teams ユーザーへの通話の実行</span><span class="sxs-lookup"><span data-stu-id="9da77-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="9da77-197">通話が Skype for Business ユーザーに転送または転送される</span><span class="sxs-lookup"><span data-stu-id="9da77-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="9da77-198">以下で説明するように、SBC がメディア プロセッサとトランスポート リレーの範囲にアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9da77-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="9da77-199">SIP シグナリング: FQDN</span><span class="sxs-lookup"><span data-stu-id="9da77-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="9da77-200">SIP シグナリングの場合、FQDN とファイアウォールの要件はバイパスされていないケースの場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="9da77-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="9da77-201">直接ルーティングは、次の Microsoft 365 または 365 環境Office提供されます。</span><span class="sxs-lookup"><span data-stu-id="9da77-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="9da77-202">Microsoft 365 または Office 365</span><span class="sxs-lookup"><span data-stu-id="9da77-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="9da77-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="9da77-203">Office 365 GCC</span></span>
- <span data-ttu-id="9da77-204">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="9da77-204">Office 365 GCC High</span></span>
- <span data-ttu-id="9da77-205">Office 365 DoD では、GCC、GCC High、DoD などの [Office 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) および米国政府機関の環境の詳細について確認できます。</span><span class="sxs-lookup"><span data-stu-id="9da77-205">Office 365 DoD Learn more about [Office 365 and US Government environments](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="9da77-206">Microsoft 365、Office 365、Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="9da77-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="9da77-207">ダイレクト ルーティングの接続ポイントは、次の 3 つの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="9da77-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="9da77-208">**sip.pstnhub.microsoft.com** – グローバル FQDN - 最初に試す必要があります。</span><span class="sxs-lookup"><span data-stu-id="9da77-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="9da77-209">SBC からこの名前を解決するための要求が送信された場合、Microsoft Azure DNS サーバーは、SBC に割り当てられているプライマリ Azure データセンターを指す IP アドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="9da77-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="9da77-210">この割り当ては、データセンターのパフォーマンスメトリックと SBC への地理的近接性に基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="9da77-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="9da77-211">返される IP アドレスはプライマリ FQDN に対応します。</span><span class="sxs-lookup"><span data-stu-id="9da77-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="9da77-212">**sip2.pstnhub.microsoft.com** – セカンダリ FQDN – 地理的に第 2 の優先度の地域にマップされます。</span><span class="sxs-lookup"><span data-stu-id="9da77-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="9da77-213">**sip3.pstnhub.microsoft.com** – 優先 FQDN – 第 3 の優先度の地域に地理的にマップされます。</span><span class="sxs-lookup"><span data-stu-id="9da77-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="9da77-214">次の 3 つの FQDN を配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9da77-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="9da77-215">最適なエクスペリエンスを提供します (読み込まれ少なく、最初の FQDN にクエリを実行して割り当てられた SBC データセンターに最も近い)。</span><span class="sxs-lookup"><span data-stu-id="9da77-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="9da77-216">SBC から一時的な問題が発生しているデータセンターへの接続が確立された場合は、フェールオーバーを提供します。</span><span class="sxs-lookup"><span data-stu-id="9da77-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="9da77-217">詳細については、以下のフェールオーバー メカニズムを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9da77-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="9da77-218">FQDN sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com、sip3.pstnhub.microsoft.comは、次のいずれかのIP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="9da77-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="9da77-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="9da77-219">52.114.148.0</span></span>
- <span data-ttu-id="9da77-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="9da77-220">52.114.132.46</span></span>
- <span data-ttu-id="9da77-221">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="9da77-221">52.114.16.74</span></span>
- <span data-ttu-id="9da77-222">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="9da77-222">52.114.20.29</span></span>
- <span data-ttu-id="9da77-223">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="9da77-223">52.114.75.24</span></span>
- <span data-ttu-id="9da77-224">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="9da77-224">52.114.76.76</span></span>
- <span data-ttu-id="9da77-225">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="9da77-225">52.114.7.24</span></span>
- <span data-ttu-id="9da77-226">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="9da77-226">52.114.14.70</span></span>

<span data-ttu-id="9da77-227">シグナリング用のアドレスに対する着信および発信トラフィックを許可するには、ファイアウォールでこれらすべての IP アドレスのポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="9da77-227">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="9da77-228">ファイアウォールで DNS 名がサポートされている場合 **、FQDN** sip-all.pstnhub.microsoft.com すべての IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="9da77-228">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="9da77-229">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="9da77-229">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="9da77-230">ダイレクト ルーティングの接続ポイントは、次の FQDN です。</span><span class="sxs-lookup"><span data-stu-id="9da77-230">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="9da77-231">**sip.pstnhub.dod.teams.microsoft.us** – グローバル FQDN。</span><span class="sxs-lookup"><span data-stu-id="9da77-231">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="9da77-232">Office 365 DoD 環境は米国のデータ センターにのみ存在し、第 2 および第 3 の FQDN はありません。</span><span class="sxs-lookup"><span data-stu-id="9da77-232">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="9da77-233">FQDN – sip.pstnhub.dod.teams.microsoft.us 次のいずれかの IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="9da77-233">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="9da77-234">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="9da77-234">52.127.64.33</span></span>
- <span data-ttu-id="9da77-235">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="9da77-235">52.127.68.34</span></span>

<span data-ttu-id="9da77-236">シグナリング用のアドレスに対する着信および発信トラフィックを許可するには、ファイアウォールでこれらすべての IP アドレスのポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="9da77-236">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="9da77-237">ファイアウォールが DNS 名をサポートしている場合、FQDN sip.pstnhub.dod.teams.microsoft.us これらの IP アドレスすべてに解決されます。</span><span class="sxs-lookup"><span data-stu-id="9da77-237">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="9da77-238">Office 365 GCC High 環境</span><span class="sxs-lookup"><span data-stu-id="9da77-238">Office 365 GCC High environment</span></span>

<span data-ttu-id="9da77-239">ダイレクト ルーティングの接続ポイントは、次の FQDN です。</span><span class="sxs-lookup"><span data-stu-id="9da77-239">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="9da77-240">**sip.pstnhub.gov.teams.microsoft.us** – グローバル FQDN。</span><span class="sxs-lookup"><span data-stu-id="9da77-240">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="9da77-241">GCC High 環境は米国のデータ センターにのみ存在しますが、第 2 および第 3 の FQDN はありません。</span><span class="sxs-lookup"><span data-stu-id="9da77-241">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="9da77-242">FQDN – sip.pstnhub.gov.teams.microsoft.us 次のいずれかの IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="9da77-242">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="9da77-243">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="9da77-243">52.127.88.59</span></span>
- <span data-ttu-id="9da77-244">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="9da77-244">52.127.92.64</span></span>

<span data-ttu-id="9da77-245">シグナリング用のアドレスに対する着信および発信トラフィックを許可するには、ファイアウォールでこれらすべての IP アドレスのポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="9da77-245">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="9da77-246">ファイアウォールで DNS 名がサポートされている場合、FQDN sip.pstnhub.gov.teams.microsoft.us IP アドレスはすべて解決されます。</span><span class="sxs-lookup"><span data-stu-id="9da77-246">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="9da77-247">SIP シグナリング: ポート</span><span class="sxs-lookup"><span data-stu-id="9da77-247">SIP Signaling: Ports</span></span>

<span data-ttu-id="9da77-248">ポート要件は、ダイレクト ルーティングが提供Office 365 のすべての環境で同じです。</span><span class="sxs-lookup"><span data-stu-id="9da77-248">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="9da77-249">Microsoft 365 または Office 365</span><span class="sxs-lookup"><span data-stu-id="9da77-249">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="9da77-250">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="9da77-250">Office 365 GCC</span></span>
- <span data-ttu-id="9da77-251">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="9da77-251">Office 365 GCC High</span></span>
- <span data-ttu-id="9da77-252">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="9da77-252">Office 365 DoD</span></span>

<span data-ttu-id="9da77-253">次のポートを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9da77-253">You must use the following ports:</span></span>

| <span data-ttu-id="9da77-254">トラフィック</span><span class="sxs-lookup"><span data-stu-id="9da77-254">Traffic</span></span> | <span data-ttu-id="9da77-255">開始</span><span class="sxs-lookup"><span data-stu-id="9da77-255">From</span></span> | <span data-ttu-id="9da77-256">終了</span><span class="sxs-lookup"><span data-stu-id="9da77-256">To</span></span> | <span data-ttu-id="9da77-257">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="9da77-257">Source port</span></span> | <span data-ttu-id="9da77-258">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="9da77-258">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="9da77-259">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="9da77-259">SIP/TLS</span></span>| <span data-ttu-id="9da77-260">SIP プロキシ</span><span class="sxs-lookup"><span data-stu-id="9da77-260">SIP Proxy</span></span> | <span data-ttu-id="9da77-261">SBC</span><span class="sxs-lookup"><span data-stu-id="9da77-261">SBC</span></span> | <span data-ttu-id="9da77-262">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="9da77-262">1024 - 65535</span></span> | <span data-ttu-id="9da77-263">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="9da77-263">Defined on the SBC</span></span> |
| <span data-ttu-id="9da77-264">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="9da77-264">SIP/TLS</span></span> | <span data-ttu-id="9da77-265">SBC</span><span class="sxs-lookup"><span data-stu-id="9da77-265">SBC</span></span> | <span data-ttu-id="9da77-266">SIP プロキシ</span><span class="sxs-lookup"><span data-stu-id="9da77-266">SIP Proxy</span></span> | <span data-ttu-id="9da77-267">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="9da77-267">Defined on the SBC</span></span> | <span data-ttu-id="9da77-268">5061</span><span class="sxs-lookup"><span data-stu-id="9da77-268">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="9da77-269">メディア トラフィック: IP とポートの範囲</span><span class="sxs-lookup"><span data-stu-id="9da77-269">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="9da77-270">直接接続が使用可能な場合、またはクライアントがパブリック IP アドレスを使用して SBC に到達できない場合、メディア トラフィックは SBC と Teams クライアントの間で流れます。</span><span class="sxs-lookup"><span data-stu-id="9da77-270">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="9da77-271">直接メディア トラフィックの要件 (Teams クライアントと SBC の間)</span><span class="sxs-lookup"><span data-stu-id="9da77-271">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="9da77-272">クライアントは、SBC のパブリック IP アドレスで指定されたポート (表を参照) にアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9da77-272">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="9da77-273">注: クライアントが内部ネットワーク内にある場合、メディアは SBC のパブリック IP アドレスに流れます。</span><span class="sxs-lookup"><span data-stu-id="9da77-273">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="9da77-274">トラフィックがエンタープライズ ネットワーク機器から離れるのを決してしない、NAT デバイスでのヘア ピン留めを構成できます。</span><span class="sxs-lookup"><span data-stu-id="9da77-274">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="9da77-275">トラフィック</span><span class="sxs-lookup"><span data-stu-id="9da77-275">Traffic</span></span> | <span data-ttu-id="9da77-276">開始</span><span class="sxs-lookup"><span data-stu-id="9da77-276">From</span></span> | <span data-ttu-id="9da77-277">終了</span><span class="sxs-lookup"><span data-stu-id="9da77-277">To</span></span> | <span data-ttu-id="9da77-278">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="9da77-278">Source port</span></span> | <span data-ttu-id="9da77-279">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="9da77-279">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="9da77-280">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="9da77-280">UDP/SRTP</span></span> | <span data-ttu-id="9da77-281">クライアント</span><span class="sxs-lookup"><span data-stu-id="9da77-281">Client</span></span> | <span data-ttu-id="9da77-282">SBC</span><span class="sxs-lookup"><span data-stu-id="9da77-282">SBC</span></span> | <span data-ttu-id="9da77-283">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="9da77-283">50 000 – 50 019</span></span>  | <span data-ttu-id="9da77-284">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="9da77-284">Defined on the SBC</span></span> |
| <span data-ttu-id="9da77-285">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="9da77-285">UDP/SRTP</span></span> | <span data-ttu-id="9da77-286">SBC</span><span class="sxs-lookup"><span data-stu-id="9da77-286">SBC</span></span> | <span data-ttu-id="9da77-287">クライアント</span><span class="sxs-lookup"><span data-stu-id="9da77-287">Client</span></span> | <span data-ttu-id="9da77-288">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="9da77-288">Defined on the SBC</span></span> | <span data-ttu-id="9da77-289">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="9da77-289">50 000 – 50 019</span></span>  |


> [!NOTE]
> <span data-ttu-id="9da77-290">クライアントのソース ポートを翻訳するネットワーク デバイスがある場合は、ネットワーク機器と SBC の間で翻訳されたポートが開いているか確認してください。</span><span class="sxs-lookup"><span data-stu-id="9da77-290">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="9da77-291">トランスポート リレーを使用する場合の要件</span><span class="sxs-lookup"><span data-stu-id="9da77-291">Requirements for using Transport Relays</span></span>

<span data-ttu-id="9da77-292">トランスポート リレーはメディア プロセッサと同じ範囲内です (バイパス以外のケースの場合):</span><span class="sxs-lookup"><span data-stu-id="9da77-292">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="9da77-293">Microsoft 365、Office 365、Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="9da77-293">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="9da77-294">52.112.0.0 /14 (52.112.0.1 から 52.115.255.254 の IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="9da77-294">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="9da77-295">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="9da77-295">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="9da77-296">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="9da77-296">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="9da77-297">Office 365 GCC High 環境</span><span class="sxs-lookup"><span data-stu-id="9da77-297">Office 365 GCC High environment</span></span>

- <span data-ttu-id="9da77-298">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="9da77-298">52.127.88.0/21</span></span>


<span data-ttu-id="9da77-299">Teams トランスポート リレー (すべての環境に適用) のポート範囲を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="9da77-299">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="9da77-300">トラフィック</span><span class="sxs-lookup"><span data-stu-id="9da77-300">Traffic</span></span> | <span data-ttu-id="9da77-301">開始</span><span class="sxs-lookup"><span data-stu-id="9da77-301">From</span></span> | <span data-ttu-id="9da77-302">終了</span><span class="sxs-lookup"><span data-stu-id="9da77-302">To</span></span> | <span data-ttu-id="9da77-303">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="9da77-303">Source port</span></span> | <span data-ttu-id="9da77-304">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="9da77-304">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="9da77-305">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="9da77-305">UDP/SRTP</span></span> | <span data-ttu-id="9da77-306">トランスポート リレー</span><span class="sxs-lookup"><span data-stu-id="9da77-306">Transport Relay</span></span> | <span data-ttu-id="9da77-307">SBC</span><span class="sxs-lookup"><span data-stu-id="9da77-307">SBC</span></span> | <span data-ttu-id="9da77-308">50 000 -59 999</span><span class="sxs-lookup"><span data-stu-id="9da77-308">50 000 -59 999</span></span>    | <span data-ttu-id="9da77-309">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="9da77-309">Defined on the SBC</span></span> |
| <span data-ttu-id="9da77-310">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="9da77-310">UDP/SRTP</span></span> | <span data-ttu-id="9da77-311">SBC</span><span class="sxs-lookup"><span data-stu-id="9da77-311">SBC</span></span> | <span data-ttu-id="9da77-312">トランスポート リレー</span><span class="sxs-lookup"><span data-stu-id="9da77-312">Transport Relay</span></span> | <span data-ttu-id="9da77-313">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="9da77-313">Defined on the SBC</span></span> | <span data-ttu-id="9da77-314">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="9da77-314">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="9da77-315">Microsoft では、SBC での同時呼び出しごとに少なくとも 2 つのポートを推奨しています。</span><span class="sxs-lookup"><span data-stu-id="9da77-315">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="9da77-316">Microsoft には 2 つのバージョンのトランスポート リレーが含まれていますので、次の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="9da77-316">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="9da77-317">v4:ポート範囲 50 000 ~ 59 999 でのみ動作する</span><span class="sxs-lookup"><span data-stu-id="9da77-317">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="9da77-318">v6(ポート 3478、3479 で動作)</span><span class="sxs-lookup"><span data-stu-id="9da77-318">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="9da77-319">現時点では、メディア バイパスは v4 バージョンのトランスポート リレーのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9da77-319">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="9da77-320">今後、v6 のサポートを導入する予定です。</span><span class="sxs-lookup"><span data-stu-id="9da77-320">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="9da77-321">移行するには、ポート 3478 と 3479 を開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="9da77-321">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="9da77-322">Microsoft がメディア バイパスを使用した v6 トランスポート リレーのサポートを導入する場合、ネットワーク機器や SBC を再構成する必要は一方で、必要な動作ではありません。</span><span class="sxs-lookup"><span data-stu-id="9da77-322">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="9da77-323">メディア プロセッサを使用する場合の要件</span><span class="sxs-lookup"><span data-stu-id="9da77-323">Requirements for using media processors</span></span>

<span data-ttu-id="9da77-324">メディア プロセッサは、音声アプリケーションと Web クライアント (Edge や Google Chrome の Teams クライアントなど) のメディア パスに常にあります。</span><span class="sxs-lookup"><span data-stu-id="9da77-324">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="9da77-325">要件は、バイパス以外の構成の場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="9da77-325">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="9da77-326">メディア トラフィックの IP 範囲は次の通り</span><span class="sxs-lookup"><span data-stu-id="9da77-326">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="9da77-327">Office 365 および Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="9da77-327">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="9da77-328">52.112.0.0 /14 (52.112.0.1 から 52.115.255.254 の IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="9da77-328">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="9da77-329">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="9da77-329">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="9da77-330">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="9da77-330">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="9da77-331">Office 365 GCC High 環境</span><span class="sxs-lookup"><span data-stu-id="9da77-331">Office 365 GCC High environment</span></span>

- <span data-ttu-id="9da77-332">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="9da77-332">52.127.88.0/21</span></span>

<span data-ttu-id="9da77-333">メディア プロセッサ (すべての環境に適用) のポート範囲を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="9da77-333">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="9da77-334">トラフィック</span><span class="sxs-lookup"><span data-stu-id="9da77-334">Traffic</span></span> | <span data-ttu-id="9da77-335">開始</span><span class="sxs-lookup"><span data-stu-id="9da77-335">From</span></span> | <span data-ttu-id="9da77-336">終了</span><span class="sxs-lookup"><span data-stu-id="9da77-336">To</span></span> | <span data-ttu-id="9da77-337">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="9da77-337">Source port</span></span> | <span data-ttu-id="9da77-338">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="9da77-338">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="9da77-339">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="9da77-339">UDP/SRTP</span></span> | <span data-ttu-id="9da77-340">メディア プロセッサ</span><span class="sxs-lookup"><span data-stu-id="9da77-340">Media Processor</span></span> | <span data-ttu-id="9da77-341">SBC</span><span class="sxs-lookup"><span data-stu-id="9da77-341">SBC</span></span> | <span data-ttu-id="9da77-342">3478、3479、49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="9da77-342">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="9da77-343">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="9da77-343">Defined on the SBC</span></span> |
| <span data-ttu-id="9da77-344">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="9da77-344">UDP/SRTP</span></span> | <span data-ttu-id="9da77-345">SBC</span><span class="sxs-lookup"><span data-stu-id="9da77-345">SBC</span></span> | <span data-ttu-id="9da77-346">メディア プロセッサ</span><span class="sxs-lookup"><span data-stu-id="9da77-346">Media Processor</span></span> | <span data-ttu-id="9da77-347">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="9da77-347">Defined on the SBC</span></span> | <span data-ttu-id="9da77-348">3478、3479、49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="9da77-348">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="9da77-349">メディア バイパスと非メディア バイパス用に個別のトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="9da77-349">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="9da77-350">メディア バイパス以外からメディア バイパスに移行し、すべての使用をメディア バイパスに移行する前に機能を確認する場合は、個別のトランクを作成し、別のオンライン 音声ルーティング ポリシーを作成してメディア バイパス トランクにルーティングし、特定のユーザーに割り当てすることができます。</span><span class="sxs-lookup"><span data-stu-id="9da77-350">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="9da77-351">高レベルの構成手順:</span><span class="sxs-lookup"><span data-stu-id="9da77-351">High-level configuration steps:</span></span>

- <span data-ttu-id="9da77-352">メディア バイパスをテストするユーザーを特定します。</span><span class="sxs-lookup"><span data-stu-id="9da77-352">Identify users to test media bypass.</span></span>

- <span data-ttu-id="9da77-353">異なる FQDN を持つ 2 つの個別のトランクを作成します。1 つはメディア バイパスに対して有効です。もう 1 つではありません。</span><span class="sxs-lookup"><span data-stu-id="9da77-353">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="9da77-354">両方のトランクが同じ SBC を指します。</span><span class="sxs-lookup"><span data-stu-id="9da77-354">Both trunks point to the same SBC.</span></span> <span data-ttu-id="9da77-355">TLS SIP シグナリングのポートは異なる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9da77-355">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="9da77-356">メディアのポートは同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9da77-356">The ports for media must be the same.</span></span>

- <span data-ttu-id="9da77-357">新しいオンライン 音声ルーティング ポリシーを作成し、このポリシーの PSTN 使用状況に関連付けられている対応するルートにメディア バイパス トランクを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="9da77-357">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="9da77-358">メディア バイパスをテストするために識別したユーザーに新しいオンライン音声ルーティング ポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="9da77-358">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="9da77-359">次の例は、このロジックを示しています。</span><span class="sxs-lookup"><span data-stu-id="9da77-359">The example below illustrates this logic.</span></span>

| <span data-ttu-id="9da77-360">一連のユーザー</span><span class="sxs-lookup"><span data-stu-id="9da77-360">Set of users</span></span> | <span data-ttu-id="9da77-361">ユーザー数</span><span class="sxs-lookup"><span data-stu-id="9da77-361">Number of users</span></span> | <span data-ttu-id="9da77-362">OVRP で割り当てられたトランク FQDN</span><span class="sxs-lookup"><span data-stu-id="9da77-362">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="9da77-363">メディア バイパス有効</span><span class="sxs-lookup"><span data-stu-id="9da77-363">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="9da77-364">メディア以外のバイパス トランクを持つユーザー</span><span class="sxs-lookup"><span data-stu-id="9da77-364">Users with non-media bypass trunk</span></span> | <span data-ttu-id="9da77-365">980</span><span class="sxs-lookup"><span data-stu-id="9da77-365">980</span></span> | <span data-ttu-id="9da77-366">sbc1.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="9da77-366">sbc1.contoso.com:5060</span></span> | <span data-ttu-id="9da77-367">true</span><span class="sxs-lookup"><span data-stu-id="9da77-367">true</span></span>
<span data-ttu-id="9da77-368">メディア バイパス トランクを使用するユーザー</span><span class="sxs-lookup"><span data-stu-id="9da77-368">Users with media bypass trunk</span></span> | <span data-ttu-id="9da77-369">20</span><span class="sxs-lookup"><span data-stu-id="9da77-369">20</span></span> | <span data-ttu-id="9da77-370">sbc2.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="9da77-370">sbc2.contoso.com:5061</span></span> | <span data-ttu-id="9da77-371">false</span><span class="sxs-lookup"><span data-stu-id="9da77-371">false</span></span> | 

<span data-ttu-id="9da77-372">両方のトランクが、同じパブリック IP アドレスを持つ同じ SBC をポイントできます。</span><span class="sxs-lookup"><span data-stu-id="9da77-372">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="9da77-373">次の図に示すように、SBC 上の TLS シグナリング ポートは異なる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9da77-373">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="9da77-374">証明書が両方のトランクをサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9da77-374">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="9da77-375">SAN では、2 つの名前 **(sbc1.contoso.com** と **sbc2.contoso.com)** を持つか、ワイルドカード証明書を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9da77-375">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9da77-376">![両方のトランクが同じパブリック IP で同じ SBC をポイントできる](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="9da77-376">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="9da77-377">同じ SBC で 2 つのトランクを構成する方法については、SBC ベンダーが提供するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9da77-377">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="9da77-378">AudioCodes 展開ドキュメント</span><span class="sxs-lookup"><span data-stu-id="9da77-378">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="9da77-379">Oracle の展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="9da77-379">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="9da77-380">リボンコミュニケーションの展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="9da77-380">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="9da77-381">TE-Systems (anynode) 展開ドキュメント</span><span class="sxs-lookup"><span data-stu-id="9da77-381">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="9da77-382">メディア バイパスでサポートされるクライアント エンドポイント</span><span class="sxs-lookup"><span data-stu-id="9da77-382">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="9da77-383">メディア バイパスは、スタンドアロンのすべての Teams デスクトップ クライアント、Android および iOS クライアント、および Teams の電話デバイスでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9da77-383">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="9da77-384">メディア バイパスをサポートしていない他のすべてのエンドポイントでは、バイパス呼び出しとして開始された場合でも、通話をバイパス以外に変換します。</span><span class="sxs-lookup"><span data-stu-id="9da77-384">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="9da77-385">これは自動的に行われます。管理者からの操作は必要とされません。</span><span class="sxs-lookup"><span data-stu-id="9da77-385">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="9da77-386">これには、Skype for Business 3PIP 電話機、および直接ルーティング呼び出しをサポートする Teams Web クライアント (Microsoft Edge、Google Chrome、Mozilla Firefox で実行されている WebRTC ベースのクライアント) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9da77-386">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="9da77-387">関連項目</span><span class="sxs-lookup"><span data-stu-id="9da77-387">See also</span></span>

[<span data-ttu-id="9da77-388">ダイレクト ルーティングでメディア バイパスを構成する</span><span class="sxs-lookup"><span data-stu-id="9da77-388">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)