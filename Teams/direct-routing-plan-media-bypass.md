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
description: 電話システムダイレクト ルーティングを使用してメディア バイパスを計画する方法について説明します。これにより、メディア トラフィックのパスを短縮し、パフォーマンスを向上させることができます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f2cbe739a567588b44bef87f7b852ed8de965ad3
ms.sourcegitcommit: 8750f98d59e74e3835d762d510fb0e038c8f17eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899098"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="6f525-103">ダイレクト ルーティングでメディア バイパスを計画する</span><span class="sxs-lookup"><span data-stu-id="6f525-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="6f525-104">ダイレクト ルーティングを使用したメディア バイパスについて</span><span class="sxs-lookup"><span data-stu-id="6f525-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="6f525-105">メディア バイパスを使用すると、メディア トラフィックのパスを短縮し、転送中のホップ数を減らしてパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="6f525-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="6f525-106">メディア バイパスでは、メディアは Microsoft Phone System 経由で送信する代わりに、セッション ボーダー コントローラー (SBC) とクライアントの間で保持されます。</span><span class="sxs-lookup"><span data-stu-id="6f525-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="6f525-107">メディア バイパスを構成するには、SBC とクライアントが同じ場所またはネットワークにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f525-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="6f525-108">各 SBC のメディア バイパスを制御するには **、-MediaBypass** パラメーターを true または false に設定した **Set-CSOnlinePSTNGateway** コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6f525-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="6f525-109">メディア バイパスを有効にした場合、すべてのメディア トラフィックが企業ネットワーク内に残るという意味ではありません。</span><span class="sxs-lookup"><span data-stu-id="6f525-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="6f525-110">この記事では、さまざまなシナリオでの呼び出しフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6f525-110">This article describes the call flow in different scenarios.</span></span>

<span data-ttu-id="6f525-111">次の図は、メディア バイパスの使用と使用しない通話フローの違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="6f525-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="6f525-112">次の図に示すように、メディア バイパスを使用しない場合、クライアントが通話を行った場合または受信すると、SBC、Microsoft Phone System、Teams クライアント間のシグナリングとメディア フローの両方が発生します。</span><span class="sxs-lookup"><span data-stu-id="6f525-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6f525-113">![メディア バイパスなしでシグナリングとメディア フローを表示する](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="6f525-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="6f525-114">ただし、ユーザーが SBC と同じビルまたはネットワーク内にあるとします。</span><span class="sxs-lookup"><span data-stu-id="6f525-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="6f525-115">たとえば、フランクフルトの建物内にあるユーザーが PSTN ユーザーを呼び出したとします。</span><span class="sxs-lookup"><span data-stu-id="6f525-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="6f525-116">**メディア バイパスを使用しない** 場合、メディアはアムステルダムまたはダブリン (Microsoft データセンターがデプロイされている場所) を経由して、フランクフルトの SBC に戻されます。</span><span class="sxs-lookup"><span data-stu-id="6f525-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="6f525-117">ヨーロッパのデータセンターは、SBC がヨーロッパに存在し、Microsoft が SBC に最も近いデータセンターを使用するために選択されます。</span><span class="sxs-lookup"><span data-stu-id="6f525-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="6f525-118">この方法は、ほとんどの地域で Microsoft ネットワーク内のトラフィック フローを最適化するために呼び出しの品質には影響しませんが、トラフィックには不要なループがあります。</span><span class="sxs-lookup"><span data-stu-id="6f525-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="6f525-119">**メディア バイパスでは**、次の図に示すように、メディアは Teams ユーザーと SBC の間で直接保持されます。</span><span class="sxs-lookup"><span data-stu-id="6f525-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="6f525-120">![メディア バイパスを使用したシグナリングとメディア フローの表示](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="6f525-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="6f525-121">メディア バイパスでは、Teams クライアントの対話型接続確立 (ICE) と SBC 上の ICE lite というプロトコルが利用されます。</span><span class="sxs-lookup"><span data-stu-id="6f525-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="6f525-122">これらのプロトコルを使用すると、ダイレクト ルーティングは最適な品質のために最も直接的なメディア パスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6f525-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="6f525-123">ICE と ICE Lite は WebRTC 標準です。</span><span class="sxs-lookup"><span data-stu-id="6f525-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="6f525-124">これらのプロトコルの詳細については、「RFC 5245」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f525-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="6f525-125">呼び出しフローとファイアウォールの計画</span><span class="sxs-lookup"><span data-stu-id="6f525-125">Call flow and firewall planning</span></span>

<span data-ttu-id="6f525-126">呼び出しフローとファイアウォールの計画は、ユーザーが SBC のパブリック IP アドレスに直接アクセスできるかどうか、およびユーザーがネットワークの内部または外部にあるかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="6f525-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="6f525-127">ユーザーが SBC のパブリック IP アドレスに直接アクセスできる場合の呼び出しフロー</span><span class="sxs-lookup"><span data-stu-id="6f525-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="6f525-128">ユーザーが SBC のパブリック IP アドレスに直接アクセスできる場合、呼び出しフローは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6f525-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="6f525-129">メディア バイパスの場合、Teams クライアントは内部ネットワークからでも SBC のパブリック IP アドレスにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f525-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="6f525-130">ダイレクト メディアが必要ない場合は、トランスポート リレー経由でメディアをフローできます。</span><span class="sxs-lookup"><span data-stu-id="6f525-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="6f525-131">これは、ユーザーが SBC と同じ建物やネットワーク内にある場合に推奨されるソリューションです。メディア パスから Microsoft Cloud コンポーネントを削除します。</span><span class="sxs-lookup"><span data-stu-id="6f525-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="6f525-132">シグナリングは常に Microsoft クラウド経由でフローします。</span><span class="sxs-lookup"><span data-stu-id="6f525-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="6f525-133">次の図は、メディア バイパスが有効で、クライアントが内部的であり、クライアントが SBC (ダイレクト メディア) のパブリック IP アドレスに到達できる場合の呼び出しフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="6f525-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="6f525-134">パスの矢印と数値は、Microsoft Teams の呼び出しフロー [に従っています](./microsoft-teams-online-call-flows.md)。</span><span class="sxs-lookup"><span data-stu-id="6f525-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="6f525-135">SIP シグナリングは常にパス 4 と 4' を受け取ります (トラフィックの方向に応じて)。</span><span class="sxs-lookup"><span data-stu-id="6f525-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="6f525-136">メディアはローカルに残り、パス 5b を受け取る。</span><span class="sxs-lookup"><span data-stu-id="6f525-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6f525-137">![Media Bypass を有効にした通話フローを表示します。クライアントは内部的です](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="6f525-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="6f525-138">ユーザーが SBC のパブリック IP アドレスにアクセスできない場合の呼び出しフロー</span><span class="sxs-lookup"><span data-stu-id="6f525-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="6f525-139">次に、ユーザーが SBC のパブリック IP アドレスにアクセスできない場合の呼び出しフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6f525-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="6f525-140">たとえば、ユーザーが外部ユーザーであり、テナント管理者は、インターネットのすべてのユーザーに対して SBC のパブリック IP アドレスを開くのではなく、Microsoft Cloud にのみ開くことを決定したとします。</span><span class="sxs-lookup"><span data-stu-id="6f525-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="6f525-141">トラフィックの内部コンポーネントは、Teams トランスポート リレーを介してフローできます。</span><span class="sxs-lookup"><span data-stu-id="6f525-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="6f525-142">次の状況について検討しましょう。</span><span class="sxs-lookup"><span data-stu-id="6f525-142">Consider the following:</span></span>

- <span data-ttu-id="6f525-143">Teams トランスポート リレーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6f525-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="6f525-144">メディア バイパスの場合、Microsoft は、Teams トランスポート リレーと SBC の間にポート 50 000 から 59 999 を開く必要があるバージョンのトランスポート リレーを使用します (今後、3478 ポートと 3479 ポートのみを必要とするバージョンに移行する予定です)。</span><span class="sxs-lookup"><span data-stu-id="6f525-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>


<span data-ttu-id="6f525-145">次の図は、メディア バイパスが有効で、クライアントが外部であり、クライアントがセッション ボーダー コントローラーのパブリック IP アドレスに到達できない場合の呼び出しフローを示しています (メディアは Teams トランスポート リレーによって中継されます)。</span><span class="sxs-lookup"><span data-stu-id="6f525-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="6f525-146">パスの矢印と数値は、Microsoft Teams の呼び出しフロー [に従っています](./microsoft-teams-online-call-flows.md)。</span><span class="sxs-lookup"><span data-stu-id="6f525-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="6f525-147">メディアは、パス 3、3、4、4' を介して中継されます。</span><span class="sxs-lookup"><span data-stu-id="6f525-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6f525-148">![ユーザーが SBC のパブリック IP にアクセスできない場合の通話フローを表示します。](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="6f525-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="6f525-149">ユーザーがネットワークの外部にいて、SBC のパブリック IP にアクセスできる場合にフローを呼び出す</span><span class="sxs-lookup"><span data-stu-id="6f525-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="6f525-150">これは、Teams トランスポート リレーを利用しないので、推奨される構成ではありません。</span><span class="sxs-lookup"><span data-stu-id="6f525-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="6f525-151">代わりに、ユーザーが SBC のパブリック IP アドレスにアクセスできない前のシナリオを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f525-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="6f525-152">次の図は、メディア バイパスが有効で、クライアントが外部であり、クライアントが SBC (ダイレクト メディア) のパブリック IP アドレスに到達できる場合の呼び出しフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="6f525-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="6f525-153">パスの矢印と数値は、Microsoft Teams の呼び出しフローに関 [する記事に従](./microsoft-teams-online-call-flows.md) っています。</span><span class="sxs-lookup"><span data-stu-id="6f525-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md) article.</span></span>

- <span data-ttu-id="6f525-154">SIP シグナリングは常にパス 3 と 3' を受け取ります (トラフィックの方向に応じて)。</span><span class="sxs-lookup"><span data-stu-id="6f525-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="6f525-155">パス 2 を使用したメディア フロー。</span><span class="sxs-lookup"><span data-stu-id="6f525-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6f525-156">![ユーザーが SBC のパブリック IP にアクセスできない場合の通話フローを表示します。](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="6f525-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="6f525-157">メディア プロセッサとトランスポート リレーの使用</span><span class="sxs-lookup"><span data-stu-id="6f525-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="6f525-158">メディア トラフィックのパスに含め得る Microsoft Cloud には、メディア プロセッサとトランスポート リレーの 2 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="6f525-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="6f525-159">Media Processor は、バイパスされていないケースのメディアを処理し、音声アプリケーション用のメディアを処理するパブリック向けのコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="6f525-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="6f525-160">メディア プロセッサは常にエンド ユーザーのバイパスされていない呼び出しのパスに入っていますが、バイパスされた呼び出しのパスには含めずにいます。</span><span class="sxs-lookup"><span data-stu-id="6f525-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="6f525-161">メディア プロセッサは、通話パーク、組織の通話、通話キューなど、すべての音声自動応答パスにあります。</span><span class="sxs-lookup"><span data-stu-id="6f525-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="6f525-162">トランスポート リレーは、最も近いトランスポート サービスに接続してリアルタイム のトラフィックを送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6f525-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="6f525-163">トランスポート リレーは、ユーザーの場所とネットワークの構成方法に応じて、バイパスされた呼び出し (発信元またはエンド ユーザー宛て) のパス内にある場合とない場合があります。</span><span class="sxs-lookup"><span data-stu-id="6f525-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="6f525-164">次の図は、メディア バイパスが有効な 2 つの呼び出しフローと、メディア バイパスが無効になっている 2 つの呼び出しフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="6f525-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span>

> [!NOTE]
> <span data-ttu-id="6f525-165">この図は、発信元または宛先のエンドツーエンド ユーザーからのトラフィックのみを示しています。</span><span class="sxs-lookup"><span data-stu-id="6f525-165">The diagram only illustrates traffic originating from--or destined to--end users.</span></span>  

- <span data-ttu-id="6f525-166">Media Controller は、メディア プロセッサを割り当て、セッション記述プロトコル (SDP) オファーを作成する Azure のマイクロサービスです。</span><span class="sxs-lookup"><span data-stu-id="6f525-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="6f525-167">SIP プロキシは、Teams で使用される HTTP REST シグナリングを SIP に変換するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="6f525-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6f525-168">![Media Bypass を有効または無効にした通話フローを表示します。](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="6f525-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="6f525-169">次の表は、メディア プロセッサとトランスポート リレーの違いをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="6f525-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="6f525-170">メディア プロセッサ</span><span class="sxs-lookup"><span data-stu-id="6f525-170">Media Processors</span></span> | <span data-ttu-id="6f525-171">トランスポート リレー</span><span class="sxs-lookup"><span data-stu-id="6f525-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="6f525-172">エンド ユーザーのバイパスされていない呼び出しのメディア パス内</span><span class="sxs-lookup"><span data-stu-id="6f525-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="6f525-173">いつも</span><span class="sxs-lookup"><span data-stu-id="6f525-173">Always</span></span> | <span data-ttu-id="6f525-174">クライアントがメディア プロセッサに直接アクセスできない場合</span><span class="sxs-lookup"><span data-stu-id="6f525-174">If client cannot reach the Media Processor directly</span></span> | 
<span data-ttu-id="6f525-175">エンド ユーザーのバイパスされた呼び出しのメディア パスで</span><span class="sxs-lookup"><span data-stu-id="6f525-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="6f525-176">ぜんぜん</span><span class="sxs-lookup"><span data-stu-id="6f525-176">Never</span></span> | <span data-ttu-id="6f525-177">クライアントがパブリック IP アドレスで SBC に到達できない場合</span><span class="sxs-lookup"><span data-stu-id="6f525-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="6f525-178">音声アプリケーションのメディア パスで</span><span class="sxs-lookup"><span data-stu-id="6f525-178">In media path for voice applications</span></span> | <span data-ttu-id="6f525-179">いつも</span><span class="sxs-lookup"><span data-stu-id="6f525-179">Always</span></span> | <span data-ttu-id="6f525-180">ぜんぜん</span><span class="sxs-lookup"><span data-stu-id="6f525-180">Never</span></span> | 
<span data-ttu-id="6f525-181">トランスコードを実行できます (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="6f525-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="6f525-182">はい</span><span class="sxs-lookup"><span data-stu-id="6f525-182">Yes</span></span> | <span data-ttu-id="6f525-183">いいえ、エンドポイント間でオーディオのみを中継する</span><span class="sxs-lookup"><span data-stu-id="6f525-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="6f525-184">世界中のインスタンスと場所の数</span><span class="sxs-lookup"><span data-stu-id="6f525-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="6f525-185">10 合計: 米国東部と西部の 2 つ。アムステルダムとダブリンの 2;香港とシンガポールの 2;日本の 2;オーストラリア東部と南東部の 2</span><span class="sxs-lookup"><span data-stu-id="6f525-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="6f525-186">複数のユーザー</span><span class="sxs-lookup"><span data-stu-id="6f525-186">Multiple</span></span>

<span data-ttu-id="6f525-187">IP 範囲は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6f525-187">The IP ranges are:</span></span>
- <span data-ttu-id="6f525-188">52.112.0.0/14 (52.112.0.1 から 52.115.255.254 の IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="6f525-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="6f525-189">52.120.0.0/14 (52.120.0.1 から 52.123.255.254 の IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="6f525-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="6f525-190">\* トランスコードの説明:</span><span class="sxs-lookup"><span data-stu-id="6f525-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="6f525-191">メディア プロセッサは B2BUA です。つまり、コーデック (たとえば、TEAMS クライアントから MP に SILK、MP と SBC の間で G.711) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="6f525-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="6f525-192">トランスポート リレーは B2BUA ではありません。つまり、リレー経由でトラフィックが流れる場合でも、クライアントと SBC の間でコーデックが変更される可能性はありません。</span><span class="sxs-lookup"><span data-stu-id="6f525-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="6f525-193">メディア バイパス用にトランクが構成されている場合の Teams Media Processors の使用</span><span class="sxs-lookup"><span data-stu-id="6f525-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="6f525-194">Teams Media Processors は、次のシナリオで常にメディア パスに挿入されます。</span><span class="sxs-lookup"><span data-stu-id="6f525-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="6f525-195">呼び出しが 1:1 からグループ呼び出しにエスカレートされます</span><span class="sxs-lookup"><span data-stu-id="6f525-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="6f525-196">フェデレーション Teams ユーザーへの呼び出し</span><span class="sxs-lookup"><span data-stu-id="6f525-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="6f525-197">Skype for Business ユーザーに転送または転送される通話</span><span class="sxs-lookup"><span data-stu-id="6f525-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="6f525-198">以下で説明するように、SBC が Media Processors および Transport Relay の範囲にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6f525-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="6f525-199">SIP シグナリング: FQDN</span><span class="sxs-lookup"><span data-stu-id="6f525-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="6f525-200">SIP シグナリングの場合、FQDN とファイアウォールの要件はバイパスされていない場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="6f525-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="6f525-201">ダイレクト ルーティングは、次の Microsoft 365 または 365 Officeで提供されます。</span><span class="sxs-lookup"><span data-stu-id="6f525-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="6f525-202">Microsoft 365 または Office 365</span><span class="sxs-lookup"><span data-stu-id="6f525-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="6f525-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="6f525-203">Office 365 GCC</span></span>
- <span data-ttu-id="6f525-204">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="6f525-204">Office 365 GCC High</span></span>
- <span data-ttu-id="6f525-205">Office 365 DoD GCC、GCC High、DoD など、Office [365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) および米国政府機関環境の詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="6f525-205">Office 365 DoD Learn more about [Office 365 and US Government environments](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="6f525-206">Microsoft 365、Office 365、Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="6f525-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="6f525-207">ダイレクト ルーティングの接続ポイントは、次の 3 つの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="6f525-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="6f525-208">**sip.pstnhub.microsoft.com** – グローバル FQDN – 最初に試す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f525-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="6f525-209">SBC がこの名前を解決するための要求を送信すると、Microsoft Azure DNS サーバーは、SBC に割り当てられているプライマリ Azure データセンターを指す IP アドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="6f525-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="6f525-210">割り当ては、データセンターのパフォーマンス メトリックと SBC への地理的な近接性に基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="6f525-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="6f525-211">返される IP アドレスは、プライマリ FQDN に対応します。</span><span class="sxs-lookup"><span data-stu-id="6f525-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="6f525-212">**sip2.pstnhub.microsoft.com** – セカンダリ FQDN – 地理的に 2 番目の優先度のリージョンにマップされます。</span><span class="sxs-lookup"><span data-stu-id="6f525-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="6f525-213">**sip3.pstnhub.microsoft.com** – ターシャリ FQDN – 地理的に 3 番目の優先順位のリージョンにマップされます。</span><span class="sxs-lookup"><span data-stu-id="6f525-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="6f525-214">次の手順を実行するには、次の 3 つの FQDN を配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f525-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="6f525-215">最適なエクスペリエンスを提供します (読み込まれ少なく、最初の FQDN を照会して割り当てられた SBC データセンターに最も近い)。</span><span class="sxs-lookup"><span data-stu-id="6f525-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="6f525-216">SBC から一時的な問題が発生しているデータセンターへの接続が確立された場合は、フェールオーバーを提供します。</span><span class="sxs-lookup"><span data-stu-id="6f525-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="6f525-217">詳細については、以下の「フェールオーバー メカニズム」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f525-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="6f525-218">FQDN **sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com、** およびsip3.pstnhub.microsoft.com は、次のいずれかの IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="6f525-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="6f525-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="6f525-219">52.114.148.0</span></span>
- <span data-ttu-id="6f525-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="6f525-220">52.114.132.46</span></span>
- <span data-ttu-id="6f525-221">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="6f525-221">52.114.16.74</span></span>
- <span data-ttu-id="6f525-222">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="6f525-222">52.114.20.29</span></span>
- <span data-ttu-id="6f525-223">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="6f525-223">52.114.75.24</span></span>
- <span data-ttu-id="6f525-224">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="6f525-224">52.114.76.76</span></span>
- <span data-ttu-id="6f525-225">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="6f525-225">52.114.7.24</span></span>
- <span data-ttu-id="6f525-226">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="6f525-226">52.114.14.70</span></span>

<span data-ttu-id="6f525-227">これらのすべての IP アドレスのポートをファイアウォールで開いて、アドレス間の着信トラフィックと発信トラフィックを許可して、シグナリングを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f525-227">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="6f525-228">ファイアウォールで DNS 名がサポートされている場合、FQDN **sip-all.pstnhub.microsoft.com** すべての IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="6f525-228">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="6f525-229">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="6f525-229">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="6f525-230">ダイレクト ルーティングの接続ポイントは、次の FQDN です。</span><span class="sxs-lookup"><span data-stu-id="6f525-230">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="6f525-231">**sip.pstnhub.dod.teams.microsoft.us** – グローバル FQDN。</span><span class="sxs-lookup"><span data-stu-id="6f525-231">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="6f525-232">365 DoD Officeは米国のデータ センターにのみ存在しますが、セカンダリ FQDN とターシャリー FQDN はありません。</span><span class="sxs-lookup"><span data-stu-id="6f525-232">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="6f525-233">FQDN – sip.pstnhub.dod.teams.microsoft.us は、次のいずれかの IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="6f525-233">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="6f525-234">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="6f525-234">52.127.64.33</span></span>
- <span data-ttu-id="6f525-235">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="6f525-235">52.127.68.34</span></span>

<span data-ttu-id="6f525-236">これらのすべての IP アドレスのポートをファイアウォールで開いて、アドレス間の着信トラフィックと発信トラフィックを許可して、シグナリングを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f525-236">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="6f525-237">ファイアウォールで DNS 名がサポートされている場合、FQDN sip.pstnhub.dod.teams.microsoft.us これらの IP アドレスすべてに解決されます。</span><span class="sxs-lookup"><span data-stu-id="6f525-237">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="6f525-238">Office 365 GCC High Environment</span><span class="sxs-lookup"><span data-stu-id="6f525-238">Office 365 GCC High environment</span></span>

<span data-ttu-id="6f525-239">ダイレクト ルーティングの接続ポイントは、次の FQDN です。</span><span class="sxs-lookup"><span data-stu-id="6f525-239">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="6f525-240">**sip.pstnhub.gov.teams.microsoft.us** – グローバル FQDN。</span><span class="sxs-lookup"><span data-stu-id="6f525-240">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="6f525-241">GCC High 環境は米国のデータ センターにのみ存在しますので、セカンダリ FQDN とターシャリ FQDN はありません。</span><span class="sxs-lookup"><span data-stu-id="6f525-241">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="6f525-242">FQDN – sip.pstnhub.gov.teams.microsoft.us は、次のいずれかの IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="6f525-242">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="6f525-243">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="6f525-243">52.127.88.59</span></span>
- <span data-ttu-id="6f525-244">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="6f525-244">52.127.92.64</span></span>

<span data-ttu-id="6f525-245">これらのすべての IP アドレスのポートをファイアウォールで開いて、アドレス間の着信トラフィックと発信トラフィックを許可して、シグナリングを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f525-245">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="6f525-246">ファイアウォールで DNS 名がサポートされている場合、FQDN sip.pstnhub.gov.teams.microsoft.us すべての IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="6f525-246">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="6f525-247">SIP シグナリング: ポート</span><span class="sxs-lookup"><span data-stu-id="6f525-247">SIP Signaling: Ports</span></span>

<span data-ttu-id="6f525-248">ポート要件は、ダイレクト ルーティングが提供Office 365 環境で同じです。</span><span class="sxs-lookup"><span data-stu-id="6f525-248">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="6f525-249">Microsoft 365 または Office 365</span><span class="sxs-lookup"><span data-stu-id="6f525-249">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="6f525-250">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="6f525-250">Office 365 GCC</span></span>
- <span data-ttu-id="6f525-251">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="6f525-251">Office 365 GCC High</span></span>
- <span data-ttu-id="6f525-252">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="6f525-252">Office 365 DoD</span></span>

<span data-ttu-id="6f525-253">次のポートを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f525-253">You must use the following ports:</span></span>

| <span data-ttu-id="6f525-254">トラフィック</span><span class="sxs-lookup"><span data-stu-id="6f525-254">Traffic</span></span> | <span data-ttu-id="6f525-255">開始</span><span class="sxs-lookup"><span data-stu-id="6f525-255">From</span></span> | <span data-ttu-id="6f525-256">終了</span><span class="sxs-lookup"><span data-stu-id="6f525-256">To</span></span> | <span data-ttu-id="6f525-257">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="6f525-257">Source port</span></span> | <span data-ttu-id="6f525-258">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="6f525-258">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="6f525-259">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="6f525-259">SIP/TLS</span></span>| <span data-ttu-id="6f525-260">SIP プロキシ</span><span class="sxs-lookup"><span data-stu-id="6f525-260">SIP Proxy</span></span> | <span data-ttu-id="6f525-261">SBC</span><span class="sxs-lookup"><span data-stu-id="6f525-261">SBC</span></span> | <span data-ttu-id="6f525-262">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="6f525-262">1024 - 65535</span></span> | <span data-ttu-id="6f525-263">SBC で定義されている</span><span class="sxs-lookup"><span data-stu-id="6f525-263">Defined on the SBC</span></span> |
| <span data-ttu-id="6f525-264">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="6f525-264">SIP/TLS</span></span> | <span data-ttu-id="6f525-265">SBC</span><span class="sxs-lookup"><span data-stu-id="6f525-265">SBC</span></span> | <span data-ttu-id="6f525-266">SIP プロキシ</span><span class="sxs-lookup"><span data-stu-id="6f525-266">SIP Proxy</span></span> | <span data-ttu-id="6f525-267">SBC で定義されている</span><span class="sxs-lookup"><span data-stu-id="6f525-267">Defined on the SBC</span></span> | <span data-ttu-id="6f525-268">5061</span><span class="sxs-lookup"><span data-stu-id="6f525-268">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="6f525-269">メディア トラフィック: IP とポートの範囲</span><span class="sxs-lookup"><span data-stu-id="6f525-269">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="6f525-270">直接接続が利用可能な場合、またはクライアントがパブリック IP アドレスを使用して SBC に到達できない場合は、Teams トランスポート リレーを介して、SBC と Teams クライアントの間でメディア トラフィックが流れます。</span><span class="sxs-lookup"><span data-stu-id="6f525-270">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="6f525-271">直接メディア トラフィックの要件 (Teams クライアントと SBC の間)</span><span class="sxs-lookup"><span data-stu-id="6f525-271">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="6f525-272">クライアントは、SBC のパブリック IP アドレス上の指定されたポート (表を参照) にアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f525-272">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

> [!NOTE]
> <span data-ttu-id="6f525-273">クライアントが内部ネットワーク内にある場合、メディアは SBC のパブリック IP アドレスに流れます。</span><span class="sxs-lookup"><span data-stu-id="6f525-273">If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="6f525-274">NAT デバイスでヘア ピン留めを構成して、トラフィックがエンタープライズ ネットワーク機器から離れなくなじむのを行います。</span><span class="sxs-lookup"><span data-stu-id="6f525-274">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="6f525-275">トラフィック</span><span class="sxs-lookup"><span data-stu-id="6f525-275">Traffic</span></span> | <span data-ttu-id="6f525-276">開始</span><span class="sxs-lookup"><span data-stu-id="6f525-276">From</span></span> | <span data-ttu-id="6f525-277">終了</span><span class="sxs-lookup"><span data-stu-id="6f525-277">To</span></span> | <span data-ttu-id="6f525-278">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="6f525-278">Source port</span></span> | <span data-ttu-id="6f525-279">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="6f525-279">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="6f525-280">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6f525-280">UDP/SRTP</span></span> | <span data-ttu-id="6f525-281">クライアント</span><span class="sxs-lookup"><span data-stu-id="6f525-281">Client</span></span> | <span data-ttu-id="6f525-282">SBC</span><span class="sxs-lookup"><span data-stu-id="6f525-282">SBC</span></span> | <span data-ttu-id="6f525-283">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="6f525-283">50 000 – 50 019</span></span>  | <span data-ttu-id="6f525-284">SBC で定義されている</span><span class="sxs-lookup"><span data-stu-id="6f525-284">Defined on the SBC</span></span> |
| <span data-ttu-id="6f525-285">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6f525-285">UDP/SRTP</span></span> | <span data-ttu-id="6f525-286">SBC</span><span class="sxs-lookup"><span data-stu-id="6f525-286">SBC</span></span> | <span data-ttu-id="6f525-287">クライアント</span><span class="sxs-lookup"><span data-stu-id="6f525-287">Client</span></span> | <span data-ttu-id="6f525-288">SBC で定義されている</span><span class="sxs-lookup"><span data-stu-id="6f525-288">Defined on the SBC</span></span> | <span data-ttu-id="6f525-289">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="6f525-289">50 000 – 50 019</span></span>  |


> [!NOTE]
> <span data-ttu-id="6f525-290">クライアントのソース ポートを変換するネットワーク デバイスがある場合は、ネットワーク機器と SBC の間で翻訳されたポートが開いているか確認してください。</span><span class="sxs-lookup"><span data-stu-id="6f525-290">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="6f525-291">トランスポート リレーを使用する場合の要件</span><span class="sxs-lookup"><span data-stu-id="6f525-291">Requirements for using Transport Relays</span></span>

<span data-ttu-id="6f525-292">トランスポート リレーは、Media Processors と同じ範囲です (バイパス以外の場合)。</span><span class="sxs-lookup"><span data-stu-id="6f525-292">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="6f525-293">Microsoft 365、Office 365、Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="6f525-293">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="6f525-294">52.112.0.0 /14 (52.112.0.1 から 52.115.255.254 の IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="6f525-294">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="6f525-295">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="6f525-295">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="6f525-296">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="6f525-296">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="6f525-297">Office 365 GCC High Environment</span><span class="sxs-lookup"><span data-stu-id="6f525-297">Office 365 GCC High environment</span></span>

- <span data-ttu-id="6f525-298">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="6f525-298">52.127.88.0/21</span></span>


<span data-ttu-id="6f525-299">Teams トランスポート リレー (すべての環境に適用) のポート範囲を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="6f525-299">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="6f525-300">トラフィック</span><span class="sxs-lookup"><span data-stu-id="6f525-300">Traffic</span></span> | <span data-ttu-id="6f525-301">開始</span><span class="sxs-lookup"><span data-stu-id="6f525-301">From</span></span> | <span data-ttu-id="6f525-302">終了</span><span class="sxs-lookup"><span data-stu-id="6f525-302">To</span></span> | <span data-ttu-id="6f525-303">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="6f525-303">Source port</span></span> | <span data-ttu-id="6f525-304">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="6f525-304">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="6f525-305">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6f525-305">UDP/SRTP</span></span> | <span data-ttu-id="6f525-306">トランスポート リレー</span><span class="sxs-lookup"><span data-stu-id="6f525-306">Transport Relay</span></span> | <span data-ttu-id="6f525-307">SBC</span><span class="sxs-lookup"><span data-stu-id="6f525-307">SBC</span></span> | <span data-ttu-id="6f525-308">50 000 -59 999</span><span class="sxs-lookup"><span data-stu-id="6f525-308">50 000 -59 999</span></span>    | <span data-ttu-id="6f525-309">SBC で定義されている</span><span class="sxs-lookup"><span data-stu-id="6f525-309">Defined on the SBC</span></span> |
| <span data-ttu-id="6f525-310">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6f525-310">UDP/SRTP</span></span> | <span data-ttu-id="6f525-311">SBC</span><span class="sxs-lookup"><span data-stu-id="6f525-311">SBC</span></span> | <span data-ttu-id="6f525-312">トランスポート リレー</span><span class="sxs-lookup"><span data-stu-id="6f525-312">Transport Relay</span></span> | <span data-ttu-id="6f525-313">SBC で定義されている</span><span class="sxs-lookup"><span data-stu-id="6f525-313">Defined on the SBC</span></span> | <span data-ttu-id="6f525-314">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="6f525-314">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="6f525-315">Microsoft では、SBC での同時呼び出しごとに少なくとも 2 つのポートをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6f525-315">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="6f525-316">Microsoft には 2 つのバージョンのトランスポート リレーが含まれていますので、次が必要です。</span><span class="sxs-lookup"><span data-stu-id="6f525-316">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="6f525-317">v4:ポート範囲 50 000 ~ 59 999 でのみ動作可能</span><span class="sxs-lookup"><span data-stu-id="6f525-317">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="6f525-318">ポート 3478、3479 で動作する v6</span><span class="sxs-lookup"><span data-stu-id="6f525-318">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="6f525-319">現時点では、メディア バイパスは v4 バージョンのトランスポート リレーのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6f525-319">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="6f525-320">今後、v6 のサポートを紹介します。</span><span class="sxs-lookup"><span data-stu-id="6f525-320">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="6f525-321">移行するには、ポート 3478 と 3479 を開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f525-321">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="6f525-322">Microsoft が Media Bypass を使用した v6 トランスポート リレーのサポートを導入した場合、ネットワーク機器や SBC を再構成する必要が生じかねない。</span><span class="sxs-lookup"><span data-stu-id="6f525-322">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="6f525-323">メディア プロセッサを使用する場合の要件</span><span class="sxs-lookup"><span data-stu-id="6f525-323">Requirements for using media processors</span></span>

<span data-ttu-id="6f525-324">メディア プロセッサは、音声アプリケーションと Web クライアント (Edge や Google Chrome の Teams クライアントなど) のメディア パスに常にあります。</span><span class="sxs-lookup"><span data-stu-id="6f525-324">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="6f525-325">要件は、バイパス以外の構成と同じです。</span><span class="sxs-lookup"><span data-stu-id="6f525-325">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="6f525-326">メディア トラフィックの IP 範囲は次の通り</span><span class="sxs-lookup"><span data-stu-id="6f525-326">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="6f525-327">Office 365 および Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="6f525-327">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="6f525-328">52.112.0.0 /14 (52.112.0.1 から 52.115.255.254 の IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="6f525-328">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="6f525-329">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="6f525-329">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="6f525-330">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="6f525-330">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="6f525-331">Office 365 GCC High Environment</span><span class="sxs-lookup"><span data-stu-id="6f525-331">Office 365 GCC High environment</span></span>

- <span data-ttu-id="6f525-332">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="6f525-332">52.127.88.0/21</span></span>

<span data-ttu-id="6f525-333">メディア プロセッサ (すべての環境に適用) のポート範囲を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="6f525-333">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="6f525-334">トラフィック</span><span class="sxs-lookup"><span data-stu-id="6f525-334">Traffic</span></span> | <span data-ttu-id="6f525-335">開始</span><span class="sxs-lookup"><span data-stu-id="6f525-335">From</span></span> | <span data-ttu-id="6f525-336">終了</span><span class="sxs-lookup"><span data-stu-id="6f525-336">To</span></span> | <span data-ttu-id="6f525-337">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="6f525-337">Source port</span></span> | <span data-ttu-id="6f525-338">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="6f525-338">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="6f525-339">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6f525-339">UDP/SRTP</span></span> | <span data-ttu-id="6f525-340">メディア プロセッサ</span><span class="sxs-lookup"><span data-stu-id="6f525-340">Media Processor</span></span> | <span data-ttu-id="6f525-341">SBC</span><span class="sxs-lookup"><span data-stu-id="6f525-341">SBC</span></span> | <span data-ttu-id="6f525-342">3478、3479、49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="6f525-342">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="6f525-343">SBC で定義されている</span><span class="sxs-lookup"><span data-stu-id="6f525-343">Defined on the SBC</span></span> |
| <span data-ttu-id="6f525-344">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6f525-344">UDP/SRTP</span></span> | <span data-ttu-id="6f525-345">SBC</span><span class="sxs-lookup"><span data-stu-id="6f525-345">SBC</span></span> | <span data-ttu-id="6f525-346">メディア プロセッサ</span><span class="sxs-lookup"><span data-stu-id="6f525-346">Media Processor</span></span> | <span data-ttu-id="6f525-347">SBC で定義されている</span><span class="sxs-lookup"><span data-stu-id="6f525-347">Defined on the SBC</span></span> | <span data-ttu-id="6f525-348">3478、3479、49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="6f525-348">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="6f525-349">メディア バイパスと非メディア バイパス用に個別のトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="6f525-349">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="6f525-350">メディア バイパス以外からメディア バイパスに移行し、すべての使用状況をメディア バイパスに移行する前に機能を確認する場合は、別のトランクを作成し、メディア バイパス トランクにルーティングし、特定のユーザーに割り当てる個別のオンライン 音声ルーティング ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6f525-350">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="6f525-351">高レベルの構成手順:</span><span class="sxs-lookup"><span data-stu-id="6f525-351">High-level configuration steps:</span></span>

- <span data-ttu-id="6f525-352">メディア バイパスをテストするユーザーを識別します。</span><span class="sxs-lookup"><span data-stu-id="6f525-352">Identify users to test media bypass.</span></span>

- <span data-ttu-id="6f525-353">異なる FQDN を持つ 2 つの独立したトランクを作成します。1 つはメディア バイパスに対して有効になっています。もう 1 つではありません。</span><span class="sxs-lookup"><span data-stu-id="6f525-353">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="6f525-354">両方のトランクが同じ SBC を指します。</span><span class="sxs-lookup"><span data-stu-id="6f525-354">Both trunks point to the same SBC.</span></span> <span data-ttu-id="6f525-355">TLS SIP シグナリングのポートは異なる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f525-355">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="6f525-356">メディアのポートは同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f525-356">The ports for media must be the same.</span></span>

- <span data-ttu-id="6f525-357">新しいオンライン 音声ルーティング ポリシーを作成し、このポリシーの PSTN 使用法に関連付けられている対応するルートにメディア バイパス トランクを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="6f525-357">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="6f525-358">メディア バイパスをテストするために識別したユーザーに新しいオンライン 音声ルーティング ポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="6f525-358">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="6f525-359">次の例は、このロジックを示しています。</span><span class="sxs-lookup"><span data-stu-id="6f525-359">The example below illustrates this logic.</span></span>

| <span data-ttu-id="6f525-360">ユーザーのセット</span><span class="sxs-lookup"><span data-stu-id="6f525-360">Set of users</span></span> | <span data-ttu-id="6f525-361">ユーザー数</span><span class="sxs-lookup"><span data-stu-id="6f525-361">Number of users</span></span> | <span data-ttu-id="6f525-362">OVRP で割り当てられたトランク FQDN</span><span class="sxs-lookup"><span data-stu-id="6f525-362">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="6f525-363">メディア バイパスが有効</span><span class="sxs-lookup"><span data-stu-id="6f525-363">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="6f525-364">メディア以外のバイパス トランクを持つユーザー</span><span class="sxs-lookup"><span data-stu-id="6f525-364">Users with non-media bypass trunk</span></span> | <span data-ttu-id="6f525-365">980</span><span class="sxs-lookup"><span data-stu-id="6f525-365">980</span></span> | <span data-ttu-id="6f525-366">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="6f525-366">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="6f525-367">false</span><span class="sxs-lookup"><span data-stu-id="6f525-367">false</span></span> |
<span data-ttu-id="6f525-368">メディア バイパス トランクを持つユーザー</span><span class="sxs-lookup"><span data-stu-id="6f525-368">Users with media bypass trunk</span></span> | <span data-ttu-id="6f525-369">20</span><span class="sxs-lookup"><span data-stu-id="6f525-369">20</span></span> | <span data-ttu-id="6f525-370">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="6f525-370">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="6f525-371">true</span><span class="sxs-lookup"><span data-stu-id="6f525-371">true</span></span> | 

<span data-ttu-id="6f525-372">両方のトランクは、同じパブリック IP アドレスを持つ同じ SBC を指します。</span><span class="sxs-lookup"><span data-stu-id="6f525-372">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="6f525-373">次の図に示すように、SBC の TLS シグナリング ポートは異なっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f525-373">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="6f525-374">証明書が両方のトランクをサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f525-374">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="6f525-375">SAN では、2 つの名前 **(sbc1.contoso.com** と sbc2.contoso.com) を持 **つ** か、ワイルドカード証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="6f525-375">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6f525-376">![両方のトランクが同じパブリック IP を持つ同じ SBC を指し示す](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="6f525-376">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="6f525-377">同じ SBC で 2 つのトランクを構成する方法については、SBC ベンダーが提供するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f525-377">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="6f525-378">AudioCodes のデプロイに関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="6f525-378">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="6f525-379">Oracle のデプロイに関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="6f525-379">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="6f525-380">リボン コミュニケーションの展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="6f525-380">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="6f525-381">TE-Systems (anynode) のデプロイに関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="6f525-381">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="6f525-382">メディア バイパスでサポートされるクライアント エンドポイント</span><span class="sxs-lookup"><span data-stu-id="6f525-382">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="6f525-383">メディア バイパスは、すべてのスタンドアロン Teams デスクトップ クライアント、Android および iOS クライアント、Teams Phone Devices でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="6f525-383">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="6f525-384">メディア バイパスをサポートしていない他のすべてのエンドポイントでは、バイパス呼び出しとして開始された場合でも、呼び出しを非バイパスに変換します。</span><span class="sxs-lookup"><span data-stu-id="6f525-384">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="6f525-385">これは自動的に実行され、管理者からのアクションは必要とされません。</span><span class="sxs-lookup"><span data-stu-id="6f525-385">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="6f525-386">これには、Skype for Business 3PIP Phones と、ダイレクト ルーティング呼び出し (Microsoft Edge、Google Chrome、Mozilla Firefox で実行されている WebRTC ベースのクライアント) をサポートする Teams Web クライアントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6f525-386">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="6f525-387">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f525-387">See also</span></span>

[<span data-ttu-id="6f525-388">ダイレクト ルーティングでメディア バイパスを構成する</span><span class="sxs-lookup"><span data-stu-id="6f525-388">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)
