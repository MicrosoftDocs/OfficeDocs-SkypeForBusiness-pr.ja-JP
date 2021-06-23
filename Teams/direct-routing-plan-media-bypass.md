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
description: ダイレクト ルーティングを使用してメディア バイパス電話システムを計画する方法について説明します。これにより、メディア トラフィックのパスを短縮し、パフォーマンスを向上させることができます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8d60513dbcf1128d303102f494600a67335b366d
ms.sourcegitcommit: cae94cd5761baafde51aea1137e6d164722eead9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2021
ms.locfileid: "53075400"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="a99a6-103">ダイレクト ルーティングでメディア バイパスを計画する</span><span class="sxs-lookup"><span data-stu-id="a99a6-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="a99a6-104">ダイレクト ルーティングを使用したメディア バイパスについて</span><span class="sxs-lookup"><span data-stu-id="a99a6-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="a99a6-105">メディア バイパスを使用すると、メディア トラフィックのパスを短縮し、転送中のホップ数を減らしてパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="a99a6-106">メディア バイパスを使用すると、メディアは、セッション ボーダー コントローラー (SBC) とクライアントの間で、Microsoft 電話されます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="a99a6-107">メディア バイパスを構成するには、SBC とクライアントが同じ場所またはネットワークにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="a99a6-108">**-MediaBypass** パラメーターを true または false に設定した **Set-CSOnlinePSTNGateway** コマンドを使用して、各 SBC のメディア バイパスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="a99a6-109">メディア バイパスを有効にした場合、すべてのメディア トラフィックが企業ネットワーク内に残るという意味ではありません。</span><span class="sxs-lookup"><span data-stu-id="a99a6-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="a99a6-110">この記事では、さまざまなシナリオでの呼び出しフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a99a6-110">This article describes the call flow in different scenarios.</span></span>

<span data-ttu-id="a99a6-111">次の図は、メディア バイパスの場合とメディア バイパスなしの呼び出しフローの違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="a99a6-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="a99a6-112">次の図に示すように、メディア バイパスを使用しない場合、クライアントが呼び出しを行った場合または受信すると、SBC、Microsoft 電話 システム、Teams クライアントの間で信号とメディアの両方が流れる。</span><span class="sxs-lookup"><span data-stu-id="a99a6-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a99a6-113">![メディア バイパスなしで信号とメディア フローを表示する](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="a99a6-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="a99a6-114">ただし、ユーザーが SBC と同じビルまたはネットワーク内にあるとします。</span><span class="sxs-lookup"><span data-stu-id="a99a6-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="a99a6-115">たとえば、フランクフルトのビルに入っているユーザーが PSTN ユーザーに通話を発信するとします。</span><span class="sxs-lookup"><span data-stu-id="a99a6-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="a99a6-116">**メディア バイパスを使用** しない場合、メディアはアムステルダムまたはダブリン (Microsoft データセンターが展開されている場所) を経由し、フランクフルトの SBC に戻されます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="a99a6-117">ヨーロッパのデータセンターは、SBC がヨーロッパに存在し、Microsoft が SBC に最も近いデータセンターを使用するために選択されます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="a99a6-118">この方法は、ほとんどの地域で Microsoft ネットワーク内のトラフィック フローを最適化するために呼び出し品質に影響しませんが、トラフィックには不必要なループがあります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="a99a6-119">**メディア バイパスでは**、次の図に示すように、Teams ユーザーと SBC の間でメディアが直接保持されます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="a99a6-120">![メディア バイパスを使用したシグナルとメディア フローの表示](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="a99a6-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="a99a6-121">メディア バイパスは、SBC 上のクライアントと ICE lite の Teams接続確立 (ICE) と呼ばれるプロトコルを利用します。</span><span class="sxs-lookup"><span data-stu-id="a99a6-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="a99a6-122">これらのプロトコルにより、ダイレクト ルーティングは最適な品質のために最も直接的なメディア パスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="a99a6-123">ICE と ICE Lite は WebRTC 標準です。</span><span class="sxs-lookup"><span data-stu-id="a99a6-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="a99a6-124">これらのプロトコルの詳細については、RFC 5245 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a99a6-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="a99a6-125">呼び出しフローとファイアウォールの計画</span><span class="sxs-lookup"><span data-stu-id="a99a6-125">Call flow and firewall planning</span></span>

<span data-ttu-id="a99a6-126">呼び出しフローとファイアウォールの計画は、ユーザーが SBC のパブリック IP アドレスに直接アクセスできるかどうか、およびユーザーがネットワークの内部か外部かによって異なります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="a99a6-127">ユーザーが SBC のパブリック IP アドレスに直接アクセスできる場合の呼び出しフロー</span><span class="sxs-lookup"><span data-stu-id="a99a6-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="a99a6-128">ユーザーが SBC のパブリック IP アドレスに直接アクセスできる場合、呼び出しフローは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="a99a6-129">メディア バイパスの場合、Teamsクライアントは、内部ネットワークからでも SBC のパブリック IP アドレスにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="a99a6-130">ダイレクト メディアが必要ない場合、メディアはトランスポート リレー経由で流れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="a99a6-131">これは、ユーザーが SBC と同じ建物やネットワーク内にある場合に推奨されるソリューションです。メディア パスから Microsoft Cloud コンポーネントを削除します。</span><span class="sxs-lookup"><span data-stu-id="a99a6-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="a99a6-132">シグナルは常に Microsoft クラウド経由で流れます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="a99a6-133">次の図は、メディア バイパスが有効で、クライアントが内部であり、クライアントが SBC (ダイレクト メディア) のパブリック IP アドレスに到達できる場合の呼び出しフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="a99a6-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="a99a6-134">パスの矢印と数値は、呼び出しフローのMicrosoft Teams[に従います](./microsoft-teams-online-call-flows.md)。</span><span class="sxs-lookup"><span data-stu-id="a99a6-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="a99a6-135">SIP シグナルは、(トラフィックの方向に応じて) 常にパス 4 と 4' を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="a99a6-136">メディアはローカルのままで、パス 5b を受け取る。</span><span class="sxs-lookup"><span data-stu-id="a99a6-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a99a6-137">![メディア バイパスを有効にした通話フロー、クライアントが内部的に表示される](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="a99a6-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="a99a6-138">ユーザーが SBC のパブリック IP アドレスにアクセスできない場合の呼び出しフロー</span><span class="sxs-lookup"><span data-stu-id="a99a6-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="a99a6-139">ユーザーが SBC のパブリック IP アドレスにアクセスできない場合の呼び出しフローを次に示します。</span><span class="sxs-lookup"><span data-stu-id="a99a6-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="a99a6-140">たとえば、ユーザーが外部のユーザーであり、テナント管理者が SBC のパブリック IP アドレスをインターネット内のすべてのユーザーに対して開くのではなく、Microsoft Cloud に対して開くことを決定したとします。</span><span class="sxs-lookup"><span data-stu-id="a99a6-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="a99a6-141">トラフィックの内部コンポーネントは、トランスポート リレーを介Teamsできます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="a99a6-142">次の状況について検討しましょう。</span><span class="sxs-lookup"><span data-stu-id="a99a6-142">Consider the following:</span></span>

- <span data-ttu-id="a99a6-143">Teamsトランスポート リレーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="a99a6-144">メディア バイパスの場合、Microsoft は、Teams トランスポート リレーと SBC の間でポート 50 000 から 59 999 を開く必要があるトランスポート リレーのバージョンを使用します (将来、3478 - 3481 ポートが必要なバージョンに移行する予定です)。</span><span class="sxs-lookup"><span data-stu-id="a99a6-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires 3478-3481 ports).</span></span>


<span data-ttu-id="a99a6-145">次の図は、メディア バイパスが有効で、クライアントが外部であり、クライアントがセッション ボーダー コントローラーのパブリック IP アドレスに到達できない場合の呼び出しフローを示しています (メディアは Teams トランスポート リレーによって中継されます)。</span><span class="sxs-lookup"><span data-stu-id="a99a6-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="a99a6-146">パスの矢印と数値は、呼び出しフローのMicrosoft Teams[に従います](./microsoft-teams-online-call-flows.md)。</span><span class="sxs-lookup"><span data-stu-id="a99a6-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="a99a6-147">メディアは、パス 3、3、4、4' を介してリレーされます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a99a6-148">![ユーザーが SBC のパブリック IP にアクセスできない場合の呼び出しフローを示します](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="a99a6-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="a99a6-149">ユーザーがネットワークの外部にいて、SBC のパブリック IP にアクセスできる場合の呼び出しフロー</span><span class="sxs-lookup"><span data-stu-id="a99a6-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="a99a6-150">この構成は、トランスポート リレーの機能を利用Teamsされていません。</span><span class="sxs-lookup"><span data-stu-id="a99a6-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="a99a6-151">代わりに、ユーザーが SBC のパブリック IP アドレスにアクセスできない前のシナリオを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="a99a6-152">次の図は、メディア バイパスが有効で、クライアントが外部であり、クライアントが SBC (ダイレクト メディア) のパブリック IP アドレスに到達できる場合の呼び出しフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="a99a6-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="a99a6-153">パスの矢印と数値は、呼び出しフローに関する記事Microsoft Teams[従](./microsoft-teams-online-call-flows.md)っています。</span><span class="sxs-lookup"><span data-stu-id="a99a6-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md) article.</span></span>

- <span data-ttu-id="a99a6-154">SIP シグナルは、(トラフィックの方向に応じて) 常にパス 3 と 3' を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="a99a6-155">パス 2 を使用したメディア フロー。</span><span class="sxs-lookup"><span data-stu-id="a99a6-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a99a6-156">![ユーザーが SBC のパブリック IP にアクセスできない場合の呼び出しフローを示します](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="a99a6-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="a99a6-157">メディア プロセッサとトランスポート リレーの使用</span><span class="sxs-lookup"><span data-stu-id="a99a6-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="a99a6-158">Microsoft Cloud には、メディア トラフィックのパスに含め可能な 2 つのコンポーネントがあります。メディア プロセッサとトランスポート リレーです。</span><span class="sxs-lookup"><span data-stu-id="a99a6-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="a99a6-159">メディア プロセッサは、バイパスしないケースでメディアを処理し、音声アプリケーションのメディアを処理する公開コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="a99a6-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="a99a6-160">メディア プロセッサは常にエンド ユーザーのバイパスされていない呼び出しのパスに入っていますが、バイパスされた呼び出しのパスには含めずにいます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="a99a6-161">メディア プロセッサは常に、コール パーク、組織の管理、通話キューなどのすべての音声自動応答パスに配置されます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="a99a6-162">トランスポート リレーは、最も近いトランスポート サービスに接続してリアルタイム トラフィックを送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="a99a6-163">トランスポート リレーは、ユーザーの場所とネットワークの構成方法に応じて、エンド ユーザーからの呼び出しやエンド ユーザー宛てのバイパスされた呼び出しのパス内にある場合と存在しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="a99a6-164">次の図は、2 つの呼び出しフローを示しています。1 つはメディア バイパスが有効で、もう 1 つはメディア バイパスが無効です。</span><span class="sxs-lookup"><span data-stu-id="a99a6-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span>

> [!NOTE]
> <span data-ttu-id="a99a6-165">この図は、エンド ユーザーから送信されるトラフィックまたはエンド ユーザー宛てのトラフィックのみを示しています。</span><span class="sxs-lookup"><span data-stu-id="a99a6-165">The diagram only illustrates traffic originating from--or destined to--end users.</span></span>  

- <span data-ttu-id="a99a6-166">メディア コントローラーは、メディア プロセッサを割り当て、セッション記述プロトコル (SDP) オファーを作成する Azure のマイクロサービスです。</span><span class="sxs-lookup"><span data-stu-id="a99a6-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="a99a6-167">SIP プロキシは、アプリケーションで使用される HTTP REST シグナルを SIP にTeamsコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="a99a6-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a99a6-168">![メディア バイパスを有効または無効にした通話フローを示します](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="a99a6-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="a99a6-169">次の表は、メディア プロセッサとトランスポート リレーの違いをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="a99a6-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="a99a6-170">メディア プロセッサ</span><span class="sxs-lookup"><span data-stu-id="a99a6-170">Media Processors</span></span> | <span data-ttu-id="a99a6-171">トランスポート リレー</span><span class="sxs-lookup"><span data-stu-id="a99a6-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="a99a6-172">エンド ユーザーのバイパスされていない呼び出しのメディア パス内</span><span class="sxs-lookup"><span data-stu-id="a99a6-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="a99a6-173">いつも</span><span class="sxs-lookup"><span data-stu-id="a99a6-173">Always</span></span> | <span data-ttu-id="a99a6-174">クライアントがメディア プロセッサに直接到達できない場合</span><span class="sxs-lookup"><span data-stu-id="a99a6-174">If client cannot reach the Media Processor directly</span></span> | 
<span data-ttu-id="a99a6-175">エンド ユーザーのバイパスされた呼び出しのメディア パス内</span><span class="sxs-lookup"><span data-stu-id="a99a6-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="a99a6-176">ぜんぜん</span><span class="sxs-lookup"><span data-stu-id="a99a6-176">Never</span></span> | <span data-ttu-id="a99a6-177">クライアントがパブリック IP アドレスで SBC に到達できない場合</span><span class="sxs-lookup"><span data-stu-id="a99a6-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="a99a6-178">音声アプリケーションのメディア パス内</span><span class="sxs-lookup"><span data-stu-id="a99a6-178">In media path for voice applications</span></span> | <span data-ttu-id="a99a6-179">いつも</span><span class="sxs-lookup"><span data-stu-id="a99a6-179">Always</span></span> | <span data-ttu-id="a99a6-180">ぜんぜん</span><span class="sxs-lookup"><span data-stu-id="a99a6-180">Never</span></span> | 
<span data-ttu-id="a99a6-181">コード変換を実行できる (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="a99a6-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="a99a6-182">はい</span><span class="sxs-lookup"><span data-stu-id="a99a6-182">Yes</span></span> | <span data-ttu-id="a99a6-183">いいえ、エンドポイント間でのみオーディオをリレーします</span><span class="sxs-lookup"><span data-stu-id="a99a6-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="a99a6-184">世界中のインスタンスの数と場所</span><span class="sxs-lookup"><span data-stu-id="a99a6-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="a99a6-185">合計 10: 米国東部と西部に 2。アムステルダムとダブリンの 2;香港、シンガポールの 2 つ。2 in Japan ;オーストラリア東部と南東部の 2</span><span class="sxs-lookup"><span data-stu-id="a99a6-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="a99a6-186">複数</span><span class="sxs-lookup"><span data-stu-id="a99a6-186">Multiple</span></span>

<span data-ttu-id="a99a6-187">IP 範囲は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a99a6-187">The IP ranges are:</span></span>
- <span data-ttu-id="a99a6-188">52.112.0.0/14 (52.112.0.1 から 52.115.255.254 の IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="a99a6-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="a99a6-189">52.120.0.0/14 (52.120.0.1 から 52.123.255.254 の IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="a99a6-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="a99a6-190">\* コード変換の説明:</span><span class="sxs-lookup"><span data-stu-id="a99a6-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="a99a6-191">メディア プロセッサは B2BUA です。つまり、コーデック (たとえば、SILK を Teams クライアントから MP と G.711 に MP と SBC の間で変更できます)。</span><span class="sxs-lookup"><span data-stu-id="a99a6-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="a99a6-192">トランスポート リレーは B2BUA ではありません。つまり、トラフィックがリレー経由で流れる場合でも、クライアントと SBC の間でコーデックが変更されません。</span><span class="sxs-lookup"><span data-stu-id="a99a6-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="a99a6-193">トランクがメディア Teams構成されている場合のメディア プロセッサの使用</span><span class="sxs-lookup"><span data-stu-id="a99a6-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="a99a6-194">Teamsメディア プロセッサは、次のシナリオでは常にメディア パスに挿入されます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="a99a6-195">通話は 1:1 からグループ通話にエスカレートされます</span><span class="sxs-lookup"><span data-stu-id="a99a6-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="a99a6-196">フェデレーション ユーザーへの呼び出Teamsしています</span><span class="sxs-lookup"><span data-stu-id="a99a6-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="a99a6-197">通話がユーザーに転送または転送Skype for Businessされます</span><span class="sxs-lookup"><span data-stu-id="a99a6-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="a99a6-198">以下で説明するように、SBC がメディア プロセッサとトランスポート リレーの範囲にアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="a99a6-199">SIP シグナル: FQDN</span><span class="sxs-lookup"><span data-stu-id="a99a6-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="a99a6-200">SIP シグナルの場合、FQDN とファイアウォールの要件はバイパスされていない場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="a99a6-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="a99a6-201">ダイレクト ルーティングは、次の環境またはMicrosoft 365でOffice 365されます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="a99a6-202">Microsoft 365またはOffice 365</span><span class="sxs-lookup"><span data-stu-id="a99a6-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="a99a6-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="a99a6-203">Office 365 GCC</span></span>
- <span data-ttu-id="a99a6-204">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="a99a6-204">Office 365 GCC High</span></span>
- <span data-ttu-id="a99a6-205">Office 365DoD Office 365、GCC [High、DoD](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)などの米国政府GCC環境の詳細について学習します。</span><span class="sxs-lookup"><span data-stu-id="a99a6-205">Office 365 DoD Learn more about [Office 365 and US Government environments](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="a99a6-206">Microsoft 365、Office 365、Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="a99a6-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="a99a6-207">ダイレクト ルーティングの接続ポイントは、次の 3 つの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="a99a6-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="a99a6-208">**sip.pstnhub.microsoft.com** – グローバル FQDN – 最初に試す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="a99a6-209">SBC がこの名前を解決する要求を送信すると、Microsoft Azure DNS サーバーは、SBC に割り当てられているプライマリ Azure データセンターを指す IP アドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="a99a6-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="a99a6-210">この割り当ては、データセンターのパフォーマンス メトリックと SBC に対する地理的な近接性に基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="a99a6-211">返される IP アドレスは、プライマリ FQDN に対応します。</span><span class="sxs-lookup"><span data-stu-id="a99a6-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="a99a6-212">**sip2.pstnhub.microsoft.com** – セカンダリ FQDN – 第 2 の優先度のリージョンに地理的にマップされます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="a99a6-213">**sip3.pstnhub.microsoft.com** – 第 3 の FQDN – 第 3 の優先度のリージョンに地理的にマップされます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="a99a6-214">次の手順を実行するには、これら 3 つの FQDN を配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="a99a6-215">最適なエクスペリエンスを提供します (読み込み量が少なく、最初の FQDN を照会することで割り当てられた SBC データセンターに最も近い)。</span><span class="sxs-lookup"><span data-stu-id="a99a6-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="a99a6-216">一時的な問題が発生しているデータセンターへの SBC からの接続が確立された場合は、フェールオーバーを提供します。</span><span class="sxs-lookup"><span data-stu-id="a99a6-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="a99a6-217">詳細については、以下の「フェールオーバー メカニズム」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a99a6-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="a99a6-218">FQDN sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com、およびsip3.pstnhub.microsoft.com は、次のサブネットの IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to IP addresses from the following subnets:</span></span>
- <span data-ttu-id="a99a6-219">52.112.0.0/14</span><span class="sxs-lookup"><span data-stu-id="a99a6-219">52.112.0.0/14</span></span>
- <span data-ttu-id="a99a6-220">52.120.0.0/14</span><span class="sxs-lookup"><span data-stu-id="a99a6-220">52.120.0.0/14</span></span>

<span data-ttu-id="a99a6-221">これらの IP 範囲のすべてのポートをファイアウォールで開いて、アドレス間の着信トラフィックと発信トラフィックを許可して、信号を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-221">You need to open ports for all these IP ranges in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="a99a6-222">ファイアウォールで DNS 名がサポートされている場合 **、FQDN** sip-all.pstnhub.microsoft.com IP サブネットすべてに解決されます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-222">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP subnets.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="a99a6-223">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="a99a6-223">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="a99a6-224">ダイレクト ルーティングの接続ポイントは、次の FQDN です。</span><span class="sxs-lookup"><span data-stu-id="a99a6-224">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="a99a6-225">**sip.pstnhub.dod.teams.microsoft.us** – グローバル FQDN。</span><span class="sxs-lookup"><span data-stu-id="a99a6-225">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="a99a6-226">DoD 環境Office 365米国のデータ センターにのみ存在する場合、第 2 および第 3 の FQDN はありません。</span><span class="sxs-lookup"><span data-stu-id="a99a6-226">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="a99a6-227">FQDN sip.pstnhub.dod.teams.microsoft.us は、次のサブネットの IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-227">The FQDN sip.pstnhub.dod.teams.microsoft.us will be resolved to an IP address from the following subnet:</span></span>

- <span data-ttu-id="a99a6-228">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="a99a6-228">52.127.64.0/21</span></span>

<span data-ttu-id="a99a6-229">これらの IP 範囲のすべてのポートをファイアウォールで開いて、アドレス間の着信トラフィックと発信トラフィックを許可して、信号を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-229">You need to open ports for all these IP ranges in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="a99a6-230">ファイアウォールで DNS 名がサポートされている場合、FQDN sip.pstnhub.dod.teams.microsoft.us IP サブネットすべてに解決されます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-230">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP subnets.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="a99a6-231">Office 365 GCC High Environment</span><span class="sxs-lookup"><span data-stu-id="a99a6-231">Office 365 GCC High environment</span></span>

<span data-ttu-id="a99a6-232">ダイレクト ルーティングの接続ポイントは、次の FQDN です。</span><span class="sxs-lookup"><span data-stu-id="a99a6-232">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="a99a6-233">**sip.pstnhub.gov.teams.microsoft.us** – グローバル FQDN。</span><span class="sxs-lookup"><span data-stu-id="a99a6-233">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="a99a6-234">High 環境GCC米国のデータ センターにのみ存在する場合、第 2 および第 3 の FQDN はありません。</span><span class="sxs-lookup"><span data-stu-id="a99a6-234">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="a99a6-235">FQDN sip.pstnhub.gov.teams.microsoft.us は、次のサブネットの IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-235">The FQDN sip.pstnhub.gov.teams.microsoft.us will be resolved to an IP address from the following subnet:</span></span>

- <span data-ttu-id="a99a6-236">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="a99a6-236">52.127.64.0/21</span></span>

<span data-ttu-id="a99a6-237">これらの IP 範囲のすべてのポートをファイアウォールで開いて、アドレス間の着信トラフィックと発信トラフィックを許可して、信号を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-237">You need to open ports for all these IP ranges in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="a99a6-238">ファイアウォールで DNS 名がサポートされている場合、FQDN sip.pstnhub.gov.teams.microsoft.us IP サブネットすべてに解決されます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-238">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP subnets.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="a99a6-239">SIP シグナル: ポート</span><span class="sxs-lookup"><span data-stu-id="a99a6-239">SIP Signaling: Ports</span></span>

<span data-ttu-id="a99a6-240">ポート要件は、ダイレクト ルーティングが提供Office 365環境で同じです。</span><span class="sxs-lookup"><span data-stu-id="a99a6-240">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="a99a6-241">Microsoft 365またはOffice 365</span><span class="sxs-lookup"><span data-stu-id="a99a6-241">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="a99a6-242">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="a99a6-242">Office 365 GCC</span></span>
- <span data-ttu-id="a99a6-243">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="a99a6-243">Office 365 GCC High</span></span>
- <span data-ttu-id="a99a6-244">Office 365DoD</span><span class="sxs-lookup"><span data-stu-id="a99a6-244">Office 365 DoD</span></span>

<span data-ttu-id="a99a6-245">次のポートを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-245">You must use the following ports:</span></span>

| <span data-ttu-id="a99a6-246">トラフィック</span><span class="sxs-lookup"><span data-stu-id="a99a6-246">Traffic</span></span> | <span data-ttu-id="a99a6-247">開始</span><span class="sxs-lookup"><span data-stu-id="a99a6-247">From</span></span> | <span data-ttu-id="a99a6-248">終了</span><span class="sxs-lookup"><span data-stu-id="a99a6-248">To</span></span> | <span data-ttu-id="a99a6-249">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="a99a6-249">Source port</span></span> | <span data-ttu-id="a99a6-250">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="a99a6-250">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="a99a6-251">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="a99a6-251">SIP/TLS</span></span>| <span data-ttu-id="a99a6-252">SIP プロキシ</span><span class="sxs-lookup"><span data-stu-id="a99a6-252">SIP Proxy</span></span> | <span data-ttu-id="a99a6-253">SBC</span><span class="sxs-lookup"><span data-stu-id="a99a6-253">SBC</span></span> | <span data-ttu-id="a99a6-254">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="a99a6-254">1024 - 65535</span></span> | <span data-ttu-id="a99a6-255">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="a99a6-255">Defined on the SBC</span></span> |
| <span data-ttu-id="a99a6-256">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="a99a6-256">SIP/TLS</span></span> | <span data-ttu-id="a99a6-257">SBC</span><span class="sxs-lookup"><span data-stu-id="a99a6-257">SBC</span></span> | <span data-ttu-id="a99a6-258">SIP プロキシ</span><span class="sxs-lookup"><span data-stu-id="a99a6-258">SIP Proxy</span></span> | <span data-ttu-id="a99a6-259">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="a99a6-259">Defined on the SBC</span></span> | <span data-ttu-id="a99a6-260">5061</span><span class="sxs-lookup"><span data-stu-id="a99a6-260">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="a99a6-261">メディア トラフィック: IP とポートの範囲</span><span class="sxs-lookup"><span data-stu-id="a99a6-261">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="a99a6-262">直接接続が使用可能な場合、またはクライアントがパブリック IP アドレスを使用して SBC に到達できない場合は Teams トランスポート リレーを介して、SBC と Teams クライアントの間でメディア トラフィックが流れます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-262">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="a99a6-263">ダイレクト メディア トラフィックの要件 (Teams クライアントと SBC の間)</span><span class="sxs-lookup"><span data-stu-id="a99a6-263">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="a99a6-264">クライアントは、SBC のパブリック IP アドレスで指定されたポート (表を参照) にアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-264">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

> [!NOTE]
> <span data-ttu-id="a99a6-265">クライアントが内部ネットワーク内にある場合、メディアは SBC のパブリック IP アドレスに流れます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-265">If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="a99a6-266">NAT デバイスで、トラフィックがエンタープライズ ネットワーク機器から出て行かねない、という構成が可能です。</span><span class="sxs-lookup"><span data-stu-id="a99a6-266">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="a99a6-267">トラフィック</span><span class="sxs-lookup"><span data-stu-id="a99a6-267">Traffic</span></span> | <span data-ttu-id="a99a6-268">開始</span><span class="sxs-lookup"><span data-stu-id="a99a6-268">From</span></span> | <span data-ttu-id="a99a6-269">終了</span><span class="sxs-lookup"><span data-stu-id="a99a6-269">To</span></span> | <span data-ttu-id="a99a6-270">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="a99a6-270">Source port</span></span> | <span data-ttu-id="a99a6-271">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="a99a6-271">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="a99a6-272">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a99a6-272">UDP/SRTP</span></span> | <span data-ttu-id="a99a6-273">クライアント</span><span class="sxs-lookup"><span data-stu-id="a99a6-273">Client</span></span> | <span data-ttu-id="a99a6-274">SBC</span><span class="sxs-lookup"><span data-stu-id="a99a6-274">SBC</span></span> | <span data-ttu-id="a99a6-275">3478-3481 および 49152 – 53247</span><span class="sxs-lookup"><span data-stu-id="a99a6-275">3478-3481 and 49152 – 53247</span></span>| <span data-ttu-id="a99a6-276">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="a99a6-276">Defined on the SBC</span></span> |
| <span data-ttu-id="a99a6-277">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a99a6-277">UDP/SRTP</span></span> | <span data-ttu-id="a99a6-278">SBC</span><span class="sxs-lookup"><span data-stu-id="a99a6-278">SBC</span></span> | <span data-ttu-id="a99a6-279">クライアント</span><span class="sxs-lookup"><span data-stu-id="a99a6-279">Client</span></span> | <span data-ttu-id="a99a6-280">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="a99a6-280">Defined on the SBC</span></span> | <span data-ttu-id="a99a6-281">3478-3481 および 49152 – 53247</span><span class="sxs-lookup"><span data-stu-id="a99a6-281">3478-3481 and 49152 – 53247</span></span>  |


> [!NOTE]
> <span data-ttu-id="a99a6-282">クライアントのソース ポートを変換するネットワーク デバイスがある場合は、変換されたポートがネットワーク機器と SBC の間で開いているか確認してください。</span><span class="sxs-lookup"><span data-stu-id="a99a6-282">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="a99a6-283">トランスポート リレーを使用する場合の要件</span><span class="sxs-lookup"><span data-stu-id="a99a6-283">Requirements for using Transport Relays</span></span>

<span data-ttu-id="a99a6-284">トランスポート リレーは、メディア プロセッサと同じ範囲内です (バイパス以外の場合):</span><span class="sxs-lookup"><span data-stu-id="a99a6-284">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="a99a6-285">Microsoft 365、Office 365、Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="a99a6-285">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="a99a6-286">52.112.0.0 /14 (52.112.0.1 から 52.115.255.254 の IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="a99a6-286">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="a99a6-287">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="a99a6-287">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="a99a6-288">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="a99a6-288">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="a99a6-289">Office 365 GCC High Environment</span><span class="sxs-lookup"><span data-stu-id="a99a6-289">Office 365 GCC High environment</span></span>

- <span data-ttu-id="a99a6-290">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="a99a6-290">52.127.88.0/21</span></span>


<span data-ttu-id="a99a6-291">次の表に、Teams トランスポート リレーのポート範囲 (すべての環境に適用) を示します。</span><span class="sxs-lookup"><span data-stu-id="a99a6-291">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="a99a6-292">トラフィック</span><span class="sxs-lookup"><span data-stu-id="a99a6-292">Traffic</span></span> | <span data-ttu-id="a99a6-293">開始</span><span class="sxs-lookup"><span data-stu-id="a99a6-293">From</span></span> | <span data-ttu-id="a99a6-294">終了</span><span class="sxs-lookup"><span data-stu-id="a99a6-294">To</span></span> | <span data-ttu-id="a99a6-295">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="a99a6-295">Source port</span></span> | <span data-ttu-id="a99a6-296">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="a99a6-296">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="a99a6-297">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a99a6-297">UDP/SRTP</span></span> | <span data-ttu-id="a99a6-298">トランスポート リレー</span><span class="sxs-lookup"><span data-stu-id="a99a6-298">Transport Relay</span></span> | <span data-ttu-id="a99a6-299">SBC</span><span class="sxs-lookup"><span data-stu-id="a99a6-299">SBC</span></span> | <span data-ttu-id="a99a6-300">50 000 -59 999</span><span class="sxs-lookup"><span data-stu-id="a99a6-300">50 000 -59 999</span></span>    | <span data-ttu-id="a99a6-301">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="a99a6-301">Defined on the SBC</span></span> |
| <span data-ttu-id="a99a6-302">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a99a6-302">UDP/SRTP</span></span> | <span data-ttu-id="a99a6-303">SBC</span><span class="sxs-lookup"><span data-stu-id="a99a6-303">SBC</span></span> | <span data-ttu-id="a99a6-304">トランスポート リレー</span><span class="sxs-lookup"><span data-stu-id="a99a6-304">Transport Relay</span></span> | <span data-ttu-id="a99a6-305">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="a99a6-305">Defined on the SBC</span></span> | <span data-ttu-id="a99a6-306">50 000 – 59 999, 3478-3481</span><span class="sxs-lookup"><span data-stu-id="a99a6-306">50 000 – 59 999, 3478-3481</span></span>     |


> [!NOTE]
> <span data-ttu-id="a99a6-307">Microsoft では、SBC での同時呼び出しごとに少なくとも 2 つのポートを推奨しています。</span><span class="sxs-lookup"><span data-stu-id="a99a6-307">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="a99a6-308">Microsoft には 2 つのバージョンのトランスポート リレーが含まれています。次が必要です。</span><span class="sxs-lookup"><span data-stu-id="a99a6-308">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="a99a6-309">v4:ポート範囲 50 000 ~ 59 999 でのみ動作可能</span><span class="sxs-lookup"><span data-stu-id="a99a6-309">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="a99a6-310">v6(ポート 3478-3481 で動作)</span><span class="sxs-lookup"><span data-stu-id="a99a6-310">v6, which works with ports 3478-3481</span></span>

<span data-ttu-id="a99a6-311">現時点では、メディア バイパスは v4 バージョンのトランスポート リレーのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a99a6-311">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="a99a6-312">今後、v6 のサポートを導入する予定です。</span><span class="sxs-lookup"><span data-stu-id="a99a6-312">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="a99a6-313">移行のためにポート 3478-3481 を開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-313">You need to open ports 3478-3481 for transitioning.</span></span> <span data-ttu-id="a99a6-314">Microsoft がメディア バイパスを使用した v6 トランスポート リレーのサポートを導入した場合、ネットワーク機器や SBC を再構成する必要が生じ得ない。</span><span class="sxs-lookup"><span data-stu-id="a99a6-314">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="a99a6-315">メディア プロセッサを使用する場合の要件</span><span class="sxs-lookup"><span data-stu-id="a99a6-315">Requirements for using media processors</span></span>

<span data-ttu-id="a99a6-316">メディア プロセッサは、音声アプリケーションと Web クライアントのメディア パスに常に含Teams Edge や Google Chrome のクライアントなどです。</span><span class="sxs-lookup"><span data-stu-id="a99a6-316">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="a99a6-317">要件は、バイパス以外の構成の場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="a99a6-317">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="a99a6-318">メディア トラフィックの IP 範囲は次の通り</span><span class="sxs-lookup"><span data-stu-id="a99a6-318">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="a99a6-319">Office 365環境Office 365 GCC環境</span><span class="sxs-lookup"><span data-stu-id="a99a6-319">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="a99a6-320">52.112.0.0 /14 (52.112.0.1 から 52.115.255.254 の IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="a99a6-320">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="a99a6-321">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="a99a6-321">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="a99a6-322">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="a99a6-322">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="a99a6-323">Office 365 GCC High Environment</span><span class="sxs-lookup"><span data-stu-id="a99a6-323">Office 365 GCC High environment</span></span>

- <span data-ttu-id="a99a6-324">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="a99a6-324">52.127.88.0/21</span></span>

<span data-ttu-id="a99a6-325">メディア プロセッサのポート範囲 (すべての環境に適用) を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="a99a6-325">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="a99a6-326">トラフィック</span><span class="sxs-lookup"><span data-stu-id="a99a6-326">Traffic</span></span> | <span data-ttu-id="a99a6-327">開始</span><span class="sxs-lookup"><span data-stu-id="a99a6-327">From</span></span> | <span data-ttu-id="a99a6-328">終了</span><span class="sxs-lookup"><span data-stu-id="a99a6-328">To</span></span> | <span data-ttu-id="a99a6-329">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="a99a6-329">Source port</span></span> | <span data-ttu-id="a99a6-330">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="a99a6-330">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="a99a6-331">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a99a6-331">UDP/SRTP</span></span> | <span data-ttu-id="a99a6-332">メディア プロセッサ</span><span class="sxs-lookup"><span data-stu-id="a99a6-332">Media Processor</span></span> | <span data-ttu-id="a99a6-333">SBC</span><span class="sxs-lookup"><span data-stu-id="a99a6-333">SBC</span></span> | <span data-ttu-id="a99a6-334">3478-3481 および 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="a99a6-334">3478-3481 and 49 152 – 53 247</span></span>    | <span data-ttu-id="a99a6-335">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="a99a6-335">Defined on the SBC</span></span> |
| <span data-ttu-id="a99a6-336">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="a99a6-336">UDP/SRTP</span></span> | <span data-ttu-id="a99a6-337">SBC</span><span class="sxs-lookup"><span data-stu-id="a99a6-337">SBC</span></span> | <span data-ttu-id="a99a6-338">メディア プロセッサ</span><span class="sxs-lookup"><span data-stu-id="a99a6-338">Media Processor</span></span> | <span data-ttu-id="a99a6-339">SBC で定義</span><span class="sxs-lookup"><span data-stu-id="a99a6-339">Defined on the SBC</span></span> | <span data-ttu-id="a99a6-340">3478-3481 および 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="a99a6-340">3478-3481 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="a99a6-341">メディア バイパスと非メディア バイパス用に個別のトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="a99a6-341">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="a99a6-342">メディア バイパスからメディア バイパスに移行し、すべての使用状況をメディア バイパスに移行する前に機能を確認する場合は、メディア バイパス トランクにルーティングして特定のユーザーに割り当てる個別のトランクと個別のオンライン音声ルーティング ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-342">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="a99a6-343">大レベルの構成手順:</span><span class="sxs-lookup"><span data-stu-id="a99a6-343">High-level configuration steps:</span></span>

- <span data-ttu-id="a99a6-344">メディア バイパスをテストするユーザーを特定します。</span><span class="sxs-lookup"><span data-stu-id="a99a6-344">Identify users to test media bypass.</span></span>

- <span data-ttu-id="a99a6-345">FQDN が異なる 2 つの個別のトランクを作成します。1 つはメディア バイパスが有効です。もう 1 つではありません。</span><span class="sxs-lookup"><span data-stu-id="a99a6-345">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="a99a6-346">両方のトランクが同じ SBC を指します。</span><span class="sxs-lookup"><span data-stu-id="a99a6-346">Both trunks point to the same SBC.</span></span> <span data-ttu-id="a99a6-347">TLS SIP シグナルのポートは異なる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-347">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="a99a6-348">メディアのポートは同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-348">The ports for media must be the same.</span></span>

- <span data-ttu-id="a99a6-349">新しいオンライン音声ルーティング ポリシーを作成し、このポリシーの PSTN 使用法に関連付けられている対応するルートにメディア バイパス トランクを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="a99a6-349">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="a99a6-350">メディア バイパスをテストするために特定したユーザーに新しいオンライン音声ルーティング ポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="a99a6-350">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="a99a6-351">次の例は、このロジックを示しています。</span><span class="sxs-lookup"><span data-stu-id="a99a6-351">The example below illustrates this logic.</span></span>

| <span data-ttu-id="a99a6-352">一連のユーザー</span><span class="sxs-lookup"><span data-stu-id="a99a6-352">Set of users</span></span> | <span data-ttu-id="a99a6-353">ユーザー数</span><span class="sxs-lookup"><span data-stu-id="a99a6-353">Number of users</span></span> | <span data-ttu-id="a99a6-354">OVRP で割り当てられたトランク FQDN</span><span class="sxs-lookup"><span data-stu-id="a99a6-354">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="a99a6-355">メディア バイパスが有効</span><span class="sxs-lookup"><span data-stu-id="a99a6-355">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="a99a6-356">メディア バイパス 以外のトランクを持つユーザー</span><span class="sxs-lookup"><span data-stu-id="a99a6-356">Users with non-media bypass trunk</span></span> | <span data-ttu-id="a99a6-357">980</span><span class="sxs-lookup"><span data-stu-id="a99a6-357">980</span></span> | <span data-ttu-id="a99a6-358">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="a99a6-358">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="a99a6-359">false</span><span class="sxs-lookup"><span data-stu-id="a99a6-359">false</span></span> |
<span data-ttu-id="a99a6-360">メディア バイパス トランクを持つユーザー</span><span class="sxs-lookup"><span data-stu-id="a99a6-360">Users with media bypass trunk</span></span> | <span data-ttu-id="a99a6-361">20</span><span class="sxs-lookup"><span data-stu-id="a99a6-361">20</span></span> | <span data-ttu-id="a99a6-362">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="a99a6-362">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="a99a6-363">true</span><span class="sxs-lookup"><span data-stu-id="a99a6-363">true</span></span> | 

<span data-ttu-id="a99a6-364">両方のトランクが、同じパブリック IP アドレスを持つ同じ SBC をポイントできます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-364">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="a99a6-365">次の図に示すように、SBC 上の TLS シグナル ポートは異なる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-365">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="a99a6-366">証明書が両方のトランクをサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-366">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="a99a6-367">SAN では、2 つの名前 **(sbc1.contoso.com** と **sbc2.contoso.com)** を持つ必要があります。または、ワイルドカード証明書を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a99a6-367">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a99a6-368">![両方のトランクが同じパブリック IP を持つ同じ SBC を指し示す](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="a99a6-368">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="a99a6-369">同じ SBC で 2 つのトランクを構成する方法については、SBC ベンダーが提供するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a99a6-369">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="a99a6-370">AudioCodes デプロイのドキュメント</span><span class="sxs-lookup"><span data-stu-id="a99a6-370">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="a99a6-371">Oracle デプロイのドキュメント</span><span class="sxs-lookup"><span data-stu-id="a99a6-371">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="a99a6-372">リボンコミュニケーションの展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="a99a6-372">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="a99a6-373">TE-Systems (anynode) のデプロイに関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="a99a6-373">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="a99a6-374">メディア バイパスでサポートされるクライアント エンドポイント</span><span class="sxs-lookup"><span data-stu-id="a99a6-374">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="a99a6-375">メディア バイパスは、デスクトップ クライアント、Android Teams iOS クライアント、および Teams 電話 デバイスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a99a6-375">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="a99a6-376">メディア バイパスをサポートしていない他のすべてのエンドポイントでは、バイパス呼び出しとして開始された場合でも、呼び出しを非バイパスに変換します。</span><span class="sxs-lookup"><span data-stu-id="a99a6-376">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="a99a6-377">これは自動的に行われます。管理者からのアクションは必要とされません。</span><span class="sxs-lookup"><span data-stu-id="a99a6-377">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="a99a6-378">これには、Skype for Business 3PIP Phone と、ダイレクト ルーティング呼び出し (Microsoft Edge、Google Chrome、Mozilla Firefox で実行される WebRTC ベースのクライアント) をサポートする Teams Web クライアントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a99a6-378">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="a99a6-379">関連項目</span><span class="sxs-lookup"><span data-stu-id="a99a6-379">See also</span></span>

[<span data-ttu-id="a99a6-380">ダイレクト ルーティングでメディア バイパスを構成する</span><span class="sxs-lookup"><span data-stu-id="a99a6-380">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)
