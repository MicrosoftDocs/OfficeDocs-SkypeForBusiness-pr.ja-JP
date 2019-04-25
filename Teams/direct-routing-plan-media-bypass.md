---
title: ダイレクト ルーティングでメディア バイパスを計画する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: 電話システムの直接のルーティングのメディア バイ パスを計画する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: b3a31e23ef065840d830c111c64e0618d90aa71b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232787"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="4498b-103">ダイレクト ルーティングでメディア バイパスを計画する</span><span class="sxs-lookup"><span data-stu-id="4498b-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="4498b-104">直接ルーティングでのメディア バイ パスについて</span><span class="sxs-lookup"><span data-stu-id="4498b-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="4498b-105">メディア バイ パスを使用すると、メディア トラフィックのパスを短くして、パフォーマンス向上のための転送中にホップの数を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="4498b-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="4498b-106">メディアのバイパスをメディアは、セッション ボーダー コント ローラー (SBC) と Microsoft の電話システムを使用して送信する代わりにクライアントの間で保持されます。</span><span class="sxs-lookup"><span data-stu-id="4498b-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="4498b-107">メディアを構成するのには、SBC とクライアントのバイパスは、同じ場所またはネットワークでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="4498b-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="4498b-108">各 SBC のメディア バイ パスを制御するには、**セット CSOnlinePSTNGateway**コマンドを使用するには true または false に設定 **- MediaBypass**パラメーターを使用しています。</span><span class="sxs-lookup"><span data-stu-id="4498b-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="4498b-109">メディアのバイパスを有効にした場合とメディアのすべてのトラフィックが企業ネットワークの範囲内に収まることは限りません。</span><span class="sxs-lookup"><span data-stu-id="4498b-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="4498b-110">この資料では、さまざまなシナリオでの呼び出しの流れを説明します。</span><span class="sxs-lookup"><span data-stu-id="4498b-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="4498b-111">次の図は、呼び出しの流れとメディア バイ パスなしの違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="4498b-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="4498b-112">メディアのバイパスのないクライアントまたは呼び出しを受信するとシグナリングとメディアの両方フロー、SBC、Microsoft の電話システムとクライアント間で、チーム、次の図に示すように。</span><span class="sxs-lookup"><span data-stu-id="4498b-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

![番組の信号およびメディア バイ パスなしのメディア フロー](media/direct-routing-media-bypass-1.png)


<span data-ttu-id="4498b-114">ですが、同じ建物や、SBC とネットワークのユーザーであると仮定します。</span><span class="sxs-lookup"><span data-stu-id="4498b-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="4498b-115">たとえば、PSTN のユーザーへの呼び出しにより、フランクフルトでの建物内にあるユーザーを想定しています。</span><span class="sxs-lookup"><span data-stu-id="4498b-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="4498b-116">**メディアなしをバイパス**するには、メディアは、アムステルダムまたはダブリン (マイクロソフトのデータ センターが展開されている) を使用して、フランクフルトで SBC をフローします。</span><span class="sxs-lookup"><span data-stu-id="4498b-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="4498b-117">SBC は、ヨーロッパでは、マイクロソフトでは、SBC に最も近いデータ センターは、ヨーロッパのデータ センターが選択されます。</span><span class="sxs-lookup"><span data-stu-id="4498b-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="4498b-118">このアプローチは、ほとんどの地域で Microsoft ネットワーク内のトラフィック フローの最適化のための通話の音質には影響しません、トラフィックが不要なループします。</span><span class="sxs-lookup"><span data-stu-id="4498b-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="4498b-119">メディアは**メディアをバイパス**するには、チームのユーザーと、次の図に示すようの間で直接保持されます。</span><span class="sxs-lookup"><span data-stu-id="4498b-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

![番組の信号とメディアは、メディア バイ パスの流れ](media/direct-routing-media-bypass-2.png)

<span data-ttu-id="4498b-121">メディアでは、チームのクライアントと氷に、SBC のライトで対話型の接続の確立 (ICE) と呼ばれる活用してプロトコルをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="4498b-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE light on the SBC.</span></span> <span data-ttu-id="4498b-122">これらのプロトコルでは、最適な品質に最も直接のメディアのパスを使用する直接ルーティングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4498b-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="4498b-123">氷と氷のライトは、WebRTC の標準です。</span><span class="sxs-lookup"><span data-stu-id="4498b-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="4498b-124">これらのプロトコルの詳細については、RFC 5245 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4498b-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="4498b-125">通話フロー、およびファイアウォールの計画</span><span class="sxs-lookup"><span data-stu-id="4498b-125">Call flow and firewall planning</span></span>

<span data-ttu-id="4498b-126">通話フロー、およびファイアウォールの計画は、ユーザーが、SBC のパブリック IP アドレスへの直接アクセスを持っているかどうかと、ユーザーは、内部または外部ネットワークかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="4498b-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="4498b-127">ユーザーが、SBC のパブリック IP アドレスへの直接アクセスを持っている場合、通話フロー</span><span class="sxs-lookup"><span data-stu-id="4498b-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="4498b-128">ユーザーに、SBC のパブリック IP アドレスへの直接アクセスがある場合は、呼び出しの流れのとおりです。</span><span class="sxs-lookup"><span data-stu-id="4498b-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="4498b-129">メディアのバイパス、チームのクライアント アクセス権が必要、SBC のパブリック IP アドレスに内部ネットワークからもします。</span><span class="sxs-lookup"><span data-stu-id="4498b-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="4498b-130">ダイレクト ・ メディアは、必要ない場合、メディア トランスポート リレー経由で流れることができます。</span><span class="sxs-lookup"><span data-stu-id="4498b-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="4498b-131">ユーザーは、同じ建物や、SBC とネットワークで、これは、推奨されるソリューション – メディア パスからマイクロソフト クラウド コンポーネントを削除します。</span><span class="sxs-lookup"><span data-stu-id="4498b-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="4498b-132">信号を常には、マイクロソフトのクラウド経由で送られます。</span><span class="sxs-lookup"><span data-stu-id="4498b-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="4498b-133">次の図は、メディアをバイパスすると、呼び出しの流れが有効になっている、クライアントは、内部および SBC (ダイレクト ・ メディア) のパブリック IP アドレスにアクセスできるクライアントを示しています。</span><span class="sxs-lookup"><span data-stu-id="4498b-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="4498b-134">矢印と数値を指定のパスの[マイクロソフトのチームは、フローを呼び出す](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)資料です。</span><span class="sxs-lookup"><span data-stu-id="4498b-134">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="4498b-135">パス 4 は、常に SIP シグナリングと 4' (トラフィックの方向) に依存します。</span><span class="sxs-lookup"><span data-stu-id="4498b-135">The SIP signaling always takes paths 4 and 4’ (depending on the direction of the traffic).</span></span> <span data-ttu-id="4498b-136">メディアは、ローカルのままし、5 b のパスは、です。</span><span class="sxs-lookup"><span data-stu-id="4498b-136">Media stays local and takes path 5b.</span></span>

![メディア バイ パスの呼び出しの流れを示していますが有効になっている場合、クライアントは内部であり、セッション ボーダー コント ローラー (ダイレクト ・ メディア) のパブリック ip アドレスに到達することができます。](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="4498b-138">ユーザーには、SBC のパブリック IP アドレスへのアクセスがない場合、通話フロー</span><span class="sxs-lookup"><span data-stu-id="4498b-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="4498b-139">次に示しますユーザーには、SBC のパブリック IP アドレスへのアクセスがない場合の呼び出しの流れを。</span><span class="sxs-lookup"><span data-stu-id="4498b-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="4498b-140">たとえば、ユーザーが外部にあり、テナント管理者がマイクロソフト クラウドに移行するだけですが、インターネット上ですべてのユーザーに、SBC のパブリック IP アドレスを開かないことにしました。</span><span class="sxs-lookup"><span data-stu-id="4498b-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="4498b-141">トラフィックの内部コンポーネントは、チーム ・ トランスポート ・ リレー経由で流れることができます。</span><span class="sxs-lookup"><span data-stu-id="4498b-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="4498b-142">これは、企業ネットワーク外部のユーザーに対して推奨される構成です。</span><span class="sxs-lookup"><span data-stu-id="4498b-142">This is the recommended configuration for users outside of the corporate network.</span></span> <span data-ttu-id="4498b-143">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="4498b-143">Consider the following:</span></span>

- <span data-ttu-id="4498b-144">チームのトランスポートのリレーを使用します。</span><span class="sxs-lookup"><span data-stu-id="4498b-144">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="4498b-145">メディアのバイパスには、マイクロソフトは、(3478 と 3479 だけのポートを必要とするバージョンに移行する計画は将来) で 50 000 に 59 999 チームのトランスポートのリレーと、SBC との間の範囲のポートを開く必要がありますトランスポート リレーのバージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="4498b-145">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>

- <span data-ttu-id="4498b-146">メディアの最適化のために、トランスポートのリレーをチームにのみ、SBC のパブリック IP アドレスを開くをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4498b-146">For media optimization purposes, Microsoft recommends opening the public IP address of the SBC only to Teams Transport Relays.</span></span> <span data-ttu-id="4498b-147">企業ネットワークの外部クライアントは、トランスポートのリレーを使用して、SBC のパブリック IP アドレスを直接に到達するのではなくをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4498b-147">For clients outside of the corporate network, Microsoft recommends using Transport Relays instead of reaching the public IP address of the SBC directly.</span></span>

<span data-ttu-id="4498b-148">メディアをバイパスすると、呼び出しの流れが有効になっている、クライアントは、外部クライアントは、セッション ボーダー コント ローラー (メディアはチームのトランスポートのリレーで中継) のパブリック IP アドレスに到達できない次の図を示しています。</span><span class="sxs-lookup"><span data-stu-id="4498b-148">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="4498b-149">矢印と数値を指定のパスの[マイクロソフトのチームは、フローを呼び出す](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)資料です。</span><span class="sxs-lookup"><span data-stu-id="4498b-149">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="4498b-150">メディアは、パス 3、3'、4 を使用して中継は、4'</span><span class="sxs-lookup"><span data-stu-id="4498b-150">Media is relayed via paths 3, 3', 4 and 4'</span></span>

![ユーザーに、SBC のパブリック ip アドレスへのアクセスがないかどうかは呼び出しのフローを示しています)](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="4498b-152">フローを呼び出す場合は、ユーザーはネットワークの外部であり、SBC のパブリック ip アドレスへのアクセス</span><span class="sxs-lookup"><span data-stu-id="4498b-152">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="4498b-153">これは推奨される構成には利用できませんトランスポート リレーのチームのためです。</span><span class="sxs-lookup"><span data-stu-id="4498b-153">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="4498b-154">代わりに、場所、ユーザーには、SBC のパブリック IP アドレスへのアクセスはありません、前のシナリオを検討してください。</span><span class="sxs-lookup"><span data-stu-id="4498b-154">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="4498b-155">メディアをバイパスすると、呼び出しの流れが有効になっている、クライアントは、外部、および SBC (ダイレクト ・ メディア) のパブリック IP アドレスがクライアントに到達できる次の図を示しています。</span><span class="sxs-lookup"><span data-stu-id="4498b-155">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="4498b-156">矢印と数値を指定のパスの[マイクロソフトのチームは、フローを呼び出す](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)資料です。</span><span class="sxs-lookup"><span data-stu-id="4498b-156">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="4498b-157">パス 3 は、常に SIP シグナリングおよび 3' (トラフィックの方向) に依存します。</span><span class="sxs-lookup"><span data-stu-id="4498b-157">The SIP signaling always takes paths 3 and 3’ (depending on the direction of the traffic).</span></span> <span data-ttu-id="4498b-158">メディア フローが 2 のパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="4498b-158">Media flows using path 2.</span></span>

![ユーザーに、SBC のパブリック ip アドレスへのアクセスがないかどうかは呼び出しのフローを示しています)](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="4498b-160">メディア プロセッサとトランスポートのリレーを使用</span><span class="sxs-lookup"><span data-stu-id="4498b-160">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="4498b-161">メディア トラフィックをパスすることができるマイクロソフトのクラウドでは、2 つのコンポーネントがあります: メディア プロセッサとトランスポートのリレーです。</span><span class="sxs-lookup"><span data-stu-id="4498b-161">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="4498b-162">メディア プロセッサは、非バイパスの場合は、メディアを処理し、音声アプリケーション用にメディアを処理するパブリック向けコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="4498b-162">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="4498b-163">メディア プロセッサは、常にバイパスされる呼び出しのパスのことはありませんが、非バイパスの呼び出しをエンド ・ ユーザーのパスにします。</span><span class="sxs-lookup"><span data-stu-id="4498b-163">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="4498b-164">メディア プロセッサは、コール パーク、組織の自動応答を呼び出してキューなどのすべての音声アプリケーションのパスには常にします。</span><span class="sxs-lookup"><span data-stu-id="4498b-164">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="4498b-165">トランスポートのリレーを使用して、リアルタイムのトラフィックを送信する最も近いトランスポート サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="4498b-165">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="4498b-166">トランスポートのリレーは、バイパスされる呼び出し--元または - であるし、ネットワークの構成方法に応じて、エンド ・ ユーザー宛てのパスにあります。</span><span class="sxs-lookup"><span data-stu-id="4498b-166">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="4498b-167">無効には、次の図は、– 2 つの呼び出しのフローを示しています。 1 つはメディア バイ パスが有効になっている、2 番目はメディアから省略。</span><span class="sxs-lookup"><span data-stu-id="4498b-167">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="4498b-168">注ダイアグラムには、--元、またはエンド ・ ユーザーに送信されるトラフィックのみ示しています。</span><span class="sxs-lookup"><span data-stu-id="4498b-168">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="4498b-169">メディア コント ローラーは、Azure メディア プロセッサの割り当てし、セッション記述プロトコル (SDP) の提供を作成するには microservice です。</span><span class="sxs-lookup"><span data-stu-id="4498b-169">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="4498b-170">SIP プロキシは、SIP をチームで使用されている HTTP の残りの信号に変換するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="4498b-170">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

![– メディア バイ パスが有効になっていると、メディア バイ パスが無効になっているもう一方の 2 つの呼び出しフローを示しています)](media/direct-routing-media-bypass-6.png)


<span data-ttu-id="4498b-172">次の表は、メディア プロセッサとトランスポートの中継の違いをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="4498b-172">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="4498b-173">メディア プロセッサ</span><span class="sxs-lookup"><span data-stu-id="4498b-173">Media Processors</span></span> | <span data-ttu-id="4498b-174">トランスポート リレー</span><span class="sxs-lookup"><span data-stu-id="4498b-174">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="4498b-175">エンド ・ ユーザーのための呼び出しの非バイパスのメディアのパスで</span><span class="sxs-lookup"><span data-stu-id="4498b-175">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="4498b-176">いつも</span><span class="sxs-lookup"><span data-stu-id="4498b-176">Always</span></span> | <span data-ttu-id="4498b-177">ぜんぜん</span><span class="sxs-lookup"><span data-stu-id="4498b-177">Never</span></span> | 
<span data-ttu-id="4498b-178">エンド ・ ユーザーの呼び出しがバイパスされるため、メディア パスに</span><span class="sxs-lookup"><span data-stu-id="4498b-178">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="4498b-179">ぜんぜん</span><span class="sxs-lookup"><span data-stu-id="4498b-179">Never</span></span> | <span data-ttu-id="4498b-180">クライアントは、SBC のパブリック IP アドレスに到達できない場合</span><span class="sxs-lookup"><span data-stu-id="4498b-180">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="4498b-181">音声アプリケーションのメディア パスに</span><span class="sxs-lookup"><span data-stu-id="4498b-181">In media path for voice applications</span></span> | <span data-ttu-id="4498b-182">いつも</span><span class="sxs-lookup"><span data-stu-id="4498b-182">Always</span></span> | <span data-ttu-id="4498b-183">ぜんぜん</span><span class="sxs-lookup"><span data-stu-id="4498b-183">Never</span></span> | 
<span data-ttu-id="4498b-184">トランス コード (B2BUA) を行うことができます。\*</span><span class="sxs-lookup"><span data-stu-id="4498b-184">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="4498b-185">はい</span><span class="sxs-lookup"><span data-stu-id="4498b-185">Yes</span></span> | <span data-ttu-id="4498b-186">いいえ、エンドポイント間の音声を中継のみ</span><span class="sxs-lookup"><span data-stu-id="4498b-186">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="4498b-187">世界中のインスタンスの数と場所</span><span class="sxs-lookup"><span data-stu-id="4498b-187">Number of instances worldwide and location</span></span> | <span data-ttu-id="4498b-188">合計 8: 2 では、米国の東と西。アムステルダム、ダブリン。2 香港とシンガポールです。(Q1CY2019 に追加されている) 日本で 2</span><span class="sxs-lookup"><span data-stu-id="4498b-188">8 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan (being added in Q1CY2019)</span></span>  | <span data-ttu-id="4498b-189">複数</span><span class="sxs-lookup"><span data-stu-id="4498b-189">Multiple</span></span>

<span data-ttu-id="4498b-190">IP の範囲は、52.112.0.0/14 (IP アドレス 52.112.0.1 から 52.115.255.254 に)。</span><span class="sxs-lookup"><span data-stu-id="4498b-190">The IP range is 52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span> 

<span data-ttu-id="4498b-191">\*トランス コードの説明:</span><span class="sxs-lookup"><span data-stu-id="4498b-191">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="4498b-192">メディア プロセッサでは、B2BUA、コーデック (たとえば、絹チーム クライアントから MP と MP と SBC の G.711) を変更できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="4498b-192">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="4498b-193">トランスポートのリレーは、リレー経由でのトラフィック フローを使用する場合でも、コーデックは、クライアントと、SBC--の間は変更されませんを意味する B2BUA ではありません。</span><span class="sxs-lookup"><span data-stu-id="4498b-193">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-transport-relays-in-escalation-scenarios-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="4498b-194">チームのトランスポートの中継のトランクは、メディアに対して構成されている場合、エスカレーションのシナリオでの使用を回避します。</span><span class="sxs-lookup"><span data-stu-id="4498b-194">Use of Teams Transport Relays in escalation scenarios if trunk is configured for media bypass</span></span>

<span data-ttu-id="4498b-195">トランスポート リレーのチームは、次のシナリオでのメディアのパスでは常に。</span><span class="sxs-lookup"><span data-stu-id="4498b-195">Teams Transport Relays are always in the media path in the following scenarios:</span></span>

- <span data-ttu-id="4498b-196">グループの呼び出しを 1:1 からの呼び出しがエスカレートします。</span><span class="sxs-lookup"><span data-stu-id="4498b-196">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="4498b-197">呼び出しが連合チームのユーザーになります。</span><span class="sxs-lookup"><span data-stu-id="4498b-197">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="4498b-198">呼び出しを転送またはビジネス ユーザーは、Skype に転送</span><span class="sxs-lookup"><span data-stu-id="4498b-198">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="4498b-199">SBC が次のように、トランスポート中継へのアクセスを持つことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4498b-199">Ensure your SBC has access to the Transport Relays as described below.</span></span>    


## <a name="sip-signaling-fqdns-and-firewall-ports"></a><span data-ttu-id="4498b-200">SIP シグナル: Fqdn およびファイアウォールのポート</span><span class="sxs-lookup"><span data-stu-id="4498b-200">SIP Signaling: FQDNs and firewall ports</span></span>

<span data-ttu-id="4498b-201">SIP シグナリングでは、FQDN とファイアウォールの要件が省略されていない場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="4498b-201">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="4498b-202">直接ルーティングするための接続ポイントは、次の 3 つの Fqdn です。</span><span class="sxs-lookup"><span data-stu-id="4498b-202">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="4498b-203">**sip.pstnhub.microsoft.com** – グローバル FQDN – が最初に試行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4498b-203">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="4498b-204">SBC では、この名前を解決するのには要求を送信するとき、Microsoft Azure の DNS サーバーは、SBC にプライマリの Azure データ センターを指す IP アドレスが割り当てられているを返します。</span><span class="sxs-lookup"><span data-stu-id="4498b-204">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="4498b-205">割り当ては、データ センターおよび、SBC に地理的な近接性のパフォーマンスの測定値に基づいています。</span><span class="sxs-lookup"><span data-stu-id="4498b-205">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="4498b-206">返された IP アドレスは、プライマリの FQDN に対応します。</span><span class="sxs-lookup"><span data-stu-id="4498b-206">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="4498b-207">**sip2.pstnhub.microsoft.com** – セカンダリ FQDN – は、2 番目の優先度の領域に地理的にマップします。</span><span class="sxs-lookup"><span data-stu-id="4498b-207">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="4498b-208">**sip3.pstnhub.microsoft.com** – 第 3 FQDN – は、3 番目の優先度の領域に地理的にマップします。</span><span class="sxs-lookup"><span data-stu-id="4498b-208">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="4498b-209">これらのための 3 つの Fqdn を配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4498b-209">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="4498b-210">(小さい読み込まれ、最初の FQDN を照会することによって割り当てられている SBC のデータ センターに最も近い) の最適なエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="4498b-210">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="4498b-211">SBC からの接続が確立されると、一時的な問題が発生しているデータ センターへのフェイル オーバーを提供します。</span><span class="sxs-lookup"><span data-stu-id="4498b-211">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="4498b-212">詳細については、次のフェイル オーバー ・ メカニズムを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4498b-212">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="4498b-213">Fqdn の**sip.pstnhub.microsoft.com**、 **sip2.pstnhub.microsoft.com**、および**sip3.pstnhub.microsoft.com**は、次の IP アドレスのいずれかに解決されます。</span><span class="sxs-lookup"><span data-stu-id="4498b-213">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="4498b-214">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="4498b-214">52.114.148.0</span></span>
- <span data-ttu-id="4498b-215">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="4498b-215">52.114.132.46</span></span>
- <span data-ttu-id="4498b-216">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="4498b-216">52.114.75.24</span></span>
- <span data-ttu-id="4498b-217">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="4498b-217">52.114.76.76</span></span>
- <span data-ttu-id="4498b-218">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="4498b-218">52.114.7.24</span></span>
- <span data-ttu-id="4498b-219">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="4498b-219">52.114.14.70</span></span>

<span data-ttu-id="4498b-220">シグナル用とアドレスからの着信および発信トラフィックを許可するファイアウォールでこれらのすべての IP アドレスのポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="4498b-220">You will need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="4498b-221">お使いのファイアウォールでは、DNS 名をサポートする場合上記のすべての IP アドレスを**sip all.pstnhub.microsoft.com**の FQDN を解決します。</span><span class="sxs-lookup"><span data-stu-id="4498b-221">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all the IP addresses above.</span></span> <span data-ttu-id="4498b-222">次のポートを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4498b-222">You must use the following ports:</span></span>

| <span data-ttu-id="4498b-223">トラフィック</span><span class="sxs-lookup"><span data-stu-id="4498b-223">Traffic</span></span> | <span data-ttu-id="4498b-224">開始</span><span class="sxs-lookup"><span data-stu-id="4498b-224">From</span></span> | <span data-ttu-id="4498b-225">終了</span><span class="sxs-lookup"><span data-stu-id="4498b-225">To</span></span> | <span data-ttu-id="4498b-226">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="4498b-226">Source port</span></span> | <span data-ttu-id="4498b-227">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="4498b-227">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="4498b-228">SIP や TLS</span><span class="sxs-lookup"><span data-stu-id="4498b-228">SIP/TLS</span></span>| <span data-ttu-id="4498b-229">SIP プロキシ</span><span class="sxs-lookup"><span data-stu-id="4498b-229">SIP Proxy</span></span> | <span data-ttu-id="4498b-230">SBC</span><span class="sxs-lookup"><span data-stu-id="4498b-230">SBC</span></span> | <span data-ttu-id="4498b-231">1024-65535</span><span class="sxs-lookup"><span data-stu-id="4498b-231">1024 - 65535</span></span> | <span data-ttu-id="4498b-232">SBC で定義されています。</span><span class="sxs-lookup"><span data-stu-id="4498b-232">Defined on the SBC</span></span> |
| <span data-ttu-id="4498b-233">SIP や TLS</span><span class="sxs-lookup"><span data-stu-id="4498b-233">SIP/TLS</span></span> | <span data-ttu-id="4498b-234">SBC</span><span class="sxs-lookup"><span data-stu-id="4498b-234">SBC</span></span> | <span data-ttu-id="4498b-235">SIP プロキシ</span><span class="sxs-lookup"><span data-stu-id="4498b-235">SIP Proxy</span></span> | <span data-ttu-id="4498b-236">SBC で定義されています。</span><span class="sxs-lookup"><span data-stu-id="4498b-236">Defined on the SBC</span></span> | <span data-ttu-id="4498b-237">5061</span><span class="sxs-lookup"><span data-stu-id="4498b-237">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="4498b-238">メディア トラフィック: ip アドレスとポートの範囲</span><span class="sxs-lookup"><span data-stu-id="4498b-238">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="4498b-239">メディア トラフィック フロー SBC およびチームのクライアントとの間の直接接続がある場合、またはチームのトランスポートのリレーを使用して、クライアントがパブリック IP アドレスを使用して、SBC に到達できない場合。</span><span class="sxs-lookup"><span data-stu-id="4498b-239">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="4498b-240">(チームのクライアントと、SBC) の間の直接のメディア トラフィックの要件</span><span class="sxs-lookup"><span data-stu-id="4498b-240">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="4498b-241">クライアントには、SBC のパブリック IP アドレスでは、(表を参照)、指定したポートにアクセス必要があります。</span><span class="sxs-lookup"><span data-stu-id="4498b-241">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="4498b-242">注: クライアントが内部ネットワーク内にある場合は、メディア、SBC のパブリック IP アドレスに回り込みます。</span><span class="sxs-lookup"><span data-stu-id="4498b-242">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="4498b-243">NAT デバイスの hairpinning を構成するには、トラフィックがエンタープライズ ネットワーク機器を送信しないようにします。</span><span class="sxs-lookup"><span data-stu-id="4498b-243">You can configure hairpinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="4498b-244">トラフィック</span><span class="sxs-lookup"><span data-stu-id="4498b-244">Traffic</span></span> | <span data-ttu-id="4498b-245">開始</span><span class="sxs-lookup"><span data-stu-id="4498b-245">From</span></span> | <span data-ttu-id="4498b-246">終了</span><span class="sxs-lookup"><span data-stu-id="4498b-246">To</span></span> | <span data-ttu-id="4498b-247">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="4498b-247">Source port</span></span> | <span data-ttu-id="4498b-248">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="4498b-248">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="4498b-249">UDP または SRTP</span><span class="sxs-lookup"><span data-stu-id="4498b-249">UDP/SRTP</span></span> | <span data-ttu-id="4498b-250">クライアント</span><span class="sxs-lookup"><span data-stu-id="4498b-250">Client</span></span> | <span data-ttu-id="4498b-251">SBC</span><span class="sxs-lookup"><span data-stu-id="4498b-251">SBC</span></span> | <span data-ttu-id="4498b-252">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="4498b-252">50 000 – 50 019</span></span>  | <span data-ttu-id="4498b-253">SBC で定義されています。</span><span class="sxs-lookup"><span data-stu-id="4498b-253">Defined on the SBC</span></span> |
| <span data-ttu-id="4498b-254">UDP または SRTP</span><span class="sxs-lookup"><span data-stu-id="4498b-254">UDP/SRTP</span></span> | <span data-ttu-id="4498b-255">SBC</span><span class="sxs-lookup"><span data-stu-id="4498b-255">SBC</span></span> | <span data-ttu-id="4498b-256">クライアント</span><span class="sxs-lookup"><span data-stu-id="4498b-256">Client</span></span> | <span data-ttu-id="4498b-257">SBC で定義されています。</span><span class="sxs-lookup"><span data-stu-id="4498b-257">Defined on the SBC</span></span> | <span data-ttu-id="4498b-258">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="4498b-258">50 000 – 50 019</span></span>  |


<span data-ttu-id="4498b-259">注: クライアントの発信元ポートを変換するネットワーク デバイスを使っている場合を確認してくださいネットワーク機器との間で翻訳済みのポートが開かれることです。</span><span class="sxs-lookup"><span data-stu-id="4498b-259">Note: If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="4498b-260">トランスポートのリレーを使用するための要件</span><span class="sxs-lookup"><span data-stu-id="4498b-260">Requirements for using Transport Relays</span></span>

<span data-ttu-id="4498b-261">(非バイパスの場合) のメディア プロセッサと同じ範囲では、トランスポートのリレー: 52.112.0.0/14 (IP アドレス 52.112.0.1 から 52.115.255.254 に)。</span><span class="sxs-lookup"><span data-stu-id="4498b-261">Transport Relays are in the same range as Media Processors (for non-bypass cases):  52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span>

<span data-ttu-id="4498b-262">チームのトランスポートの中継のポートの範囲は、次の表で示されます。</span><span class="sxs-lookup"><span data-stu-id="4498b-262">The port range of the Teams Transport Relays is shown in the following table:</span></span>


| <span data-ttu-id="4498b-263">トラフィック</span><span class="sxs-lookup"><span data-stu-id="4498b-263">Traffic</span></span> | <span data-ttu-id="4498b-264">開始</span><span class="sxs-lookup"><span data-stu-id="4498b-264">From</span></span> | <span data-ttu-id="4498b-265">終了</span><span class="sxs-lookup"><span data-stu-id="4498b-265">To</span></span> | <span data-ttu-id="4498b-266">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="4498b-266">Source port</span></span> | <span data-ttu-id="4498b-267">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="4498b-267">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="4498b-268">UDP または SRTP</span><span class="sxs-lookup"><span data-stu-id="4498b-268">UDP/SRTP</span></span> | <span data-ttu-id="4498b-269">トランスポート リレー</span><span class="sxs-lookup"><span data-stu-id="4498b-269">Transport Relay</span></span> | <span data-ttu-id="4498b-270">SBC</span><span class="sxs-lookup"><span data-stu-id="4498b-270">SBC</span></span> | <span data-ttu-id="4498b-271">50 000-59 999</span><span class="sxs-lookup"><span data-stu-id="4498b-271">50 000 -59 999</span></span>    | <span data-ttu-id="4498b-272">SBC で定義されています。</span><span class="sxs-lookup"><span data-stu-id="4498b-272">Defined on the SBC</span></span> |
| <span data-ttu-id="4498b-273">UDP または SRTP</span><span class="sxs-lookup"><span data-stu-id="4498b-273">UDP/SRTP</span></span> | <span data-ttu-id="4498b-274">SBC</span><span class="sxs-lookup"><span data-stu-id="4498b-274">SBC</span></span> | <span data-ttu-id="4498b-275">トランスポート リレー</span><span class="sxs-lookup"><span data-stu-id="4498b-275">Transport Relay</span></span> | <span data-ttu-id="4498b-276">SBC で定義されています。</span><span class="sxs-lookup"><span data-stu-id="4498b-276">Defined on the SBC</span></span> | <span data-ttu-id="4498b-277">50 000 – 59 999、3478、3479</span><span class="sxs-lookup"><span data-stu-id="4498b-277">50 000 – 59 999, 3478, 3479</span></span>     |


<span data-ttu-id="4498b-278">注: マイクロソフトは、SBC の同時呼び出しごとに少なくとも 2 つのポートをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4498b-278">Note: Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="4498b-279">Microsoft には、トランスポートの中継の 2 つのバージョンがあるため、次が必要です。</span><span class="sxs-lookup"><span data-stu-id="4498b-279">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>

- <span data-ttu-id="4498b-280">v4 で、50 000 に 59 999 のポート範囲を操作できます。</span><span class="sxs-lookup"><span data-stu-id="4498b-280">v4, which can only work with port range 50 000 to 59 999</span></span>

- <span data-ttu-id="4498b-281">v6 で、使用可能なポート 3478、3479</span><span class="sxs-lookup"><span data-stu-id="4498b-281">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="4498b-282">この時点では、メディアは、トランスポートの中継の v4 バージョンのみをサポートしていますをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="4498b-282">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="4498b-283">紹介 v6 のサポート、将来的にします。</span><span class="sxs-lookup"><span data-stu-id="4498b-283">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="4498b-284">3478 と 3479 を遷移させるためにポートを開放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4498b-284">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="4498b-285">マイクロソフトでは、メディア バイ パスと v6 のトランスポート リレーのサポートが導入されて、ときに、ネットワーク機器または SBCs を再構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4498b-285">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="4498b-286">メディア プロセッサを使用するための要件</span><span class="sxs-lookup"><span data-stu-id="4498b-286">Requirements for using media processors</span></span>

<span data-ttu-id="4498b-287">メディア プロセッサは、常に音声アプリケーションのメディア パスにします。</span><span class="sxs-lookup"><span data-stu-id="4498b-287">Media Processors are always in the media path for voice applications.</span></span> <span data-ttu-id="4498b-288">要件は、非バイパスの構成と同じです。</span><span class="sxs-lookup"><span data-stu-id="4498b-288">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="4498b-289">メディア トラフィック用の IP の範囲は、52.112.0.0/14 (IP アドレス 52.112.0.1 から 52.115.255.254 に)。</span><span class="sxs-lookup"><span data-stu-id="4498b-289">The IP range for media traffic is 52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span>

<span data-ttu-id="4498b-290">メディア プロセッサのポートの範囲は、次の表で示されます。</span><span class="sxs-lookup"><span data-stu-id="4498b-290">The port range of the Media Processors is shown in the following table:</span></span>

| <span data-ttu-id="4498b-291">トラフィック</span><span class="sxs-lookup"><span data-stu-id="4498b-291">Traffic</span></span> | <span data-ttu-id="4498b-292">開始</span><span class="sxs-lookup"><span data-stu-id="4498b-292">From</span></span> | <span data-ttu-id="4498b-293">終了</span><span class="sxs-lookup"><span data-stu-id="4498b-293">To</span></span> | <span data-ttu-id="4498b-294">送信元ポート</span><span class="sxs-lookup"><span data-stu-id="4498b-294">Source port</span></span> | <span data-ttu-id="4498b-295">宛先ポート</span><span class="sxs-lookup"><span data-stu-id="4498b-295">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="4498b-296">UDP または SRTP</span><span class="sxs-lookup"><span data-stu-id="4498b-296">UDP/SRTP</span></span> | <span data-ttu-id="4498b-297">メディア プロセッサ</span><span class="sxs-lookup"><span data-stu-id="4498b-297">Media Processor</span></span> | <span data-ttu-id="4498b-298">SBC</span><span class="sxs-lookup"><span data-stu-id="4498b-298">SBC</span></span> | <span data-ttu-id="4498b-299">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="4498b-299">49 152 – 53 247</span></span>    | <span data-ttu-id="4498b-300">SBC で定義されています。</span><span class="sxs-lookup"><span data-stu-id="4498b-300">Defined on the SBC</span></span> |
| <span data-ttu-id="4498b-301">UDP または SRTP</span><span class="sxs-lookup"><span data-stu-id="4498b-301">UDP/SRTP</span></span> | <span data-ttu-id="4498b-302">SBC</span><span class="sxs-lookup"><span data-stu-id="4498b-302">SBC</span></span> | <span data-ttu-id="4498b-303">メディア プロセッサ</span><span class="sxs-lookup"><span data-stu-id="4498b-303">Media Processor</span></span> | <span data-ttu-id="4498b-304">SBC で定義されています。</span><span class="sxs-lookup"><span data-stu-id="4498b-304">Defined on the SBC</span></span> | <span data-ttu-id="4498b-305">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="4498b-305">49 152 – 53 247</span></span>     |

## <a name="considerations-if-you-have-skype-for-business-phones-in-your-network"></a><span data-ttu-id="4498b-306">ビジネス電話のネットワークでの Skype をした場合の考慮事項</span><span class="sxs-lookup"><span data-stu-id="4498b-306">Considerations if you have Skype for Business phones in your network</span></span>  

<span data-ttu-id="4498b-307">直接ルーティングの場合は - を使用しているネットワークでのビジネスの端点を Skype がある場合など、チームがユーザーのビジネス クライアント--Skype に基づく 3PIP 電話を持つことができますこれらのユーザーにサービスを提供するトランクのメディア バイ パス無効でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="4498b-307">If you have any Skype for Business end points in your network that are using Direct Routing--for example, a Teams user can have a 3PIP phone that is based on Skype for Business client--the media bypass on the trunk that serves these users must be turned off.</span></span>

<span data-ttu-id="4498b-308">これらのユーザーの独立したトランクを作成して、オンライン音声ルーティング ポリシーを割り当てることです。</span><span class="sxs-lookup"><span data-stu-id="4498b-308">You can create a separate trunk for these users and assign it an Online Voice Routing policy.</span></span>

<span data-ttu-id="4498b-309">高度な構成手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4498b-309">High-level configuration steps:</span></span>

- <span data-ttu-id="4498b-310">タイプ]: ユーザーに 3PIP の電話が持っているかどうかどうかに応じて、ユーザーを分割します。</span><span class="sxs-lookup"><span data-stu-id="4498b-310">Split users by type – depending on whether the user has a 3PIP phone or not.</span></span>

- <span data-ttu-id="4498b-311">異なる Fqdn を持つ 2 つの独立したトランクを作成する: いずれかの有効にメディアをバイパスします。他のないです。</span><span class="sxs-lookup"><span data-stu-id="4498b-311">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="4498b-312">両方のトランクは、同じ SBC をポイントします。</span><span class="sxs-lookup"><span data-stu-id="4498b-312">Both trunks point to the same SBC.</span></span> <span data-ttu-id="4498b-313">TLS の SIP シグナリング用のポートが異なる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4498b-313">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="4498b-314">メディア用のポートを同じにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4498b-314">The ports for media must be the same.</span></span>

- <span data-ttu-id="4498b-315">オンラインの音声ルーティング ポリシーのユーザーの種類に応じて適切なトランクを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4498b-315">Assign the correct trunk depending on the type of the user in the Online Voice Routing policy.</span></span>

<span data-ttu-id="4498b-316">次の例は、このロジックを示しています。</span><span class="sxs-lookup"><span data-stu-id="4498b-316">The example below illustrates this logic.</span></span>

| <span data-ttu-id="4498b-317">ユーザーの設定</span><span class="sxs-lookup"><span data-stu-id="4498b-317">Set of users</span></span> | <span data-ttu-id="4498b-318">ユーザーの数</span><span class="sxs-lookup"><span data-stu-id="4498b-318">Number of users</span></span> | <span data-ttu-id="4498b-319">トランクの FQDN が OVRP に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="4498b-319">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="4498b-320">メディア バイ パスが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="4498b-320">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="4498b-321">チーム クライアントおよび 3PIP の電話を持つユーザー</span><span class="sxs-lookup"><span data-stu-id="4498b-321">Users with Teams clients and 3PIP phones</span></span> | <span data-ttu-id="4498b-322">20</span><span class="sxs-lookup"><span data-stu-id="4498b-322">20</span></span> | <span data-ttu-id="4498b-323">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="4498b-323">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="4498b-324">false</span><span class="sxs-lookup"><span data-stu-id="4498b-324">false</span></span> | 
<span data-ttu-id="4498b-325">(新しい電話がチームの認定を含む) のみのチームの端点を持つユーザー</span><span class="sxs-lookup"><span data-stu-id="4498b-325">Users with only Teams end points (including new phones certified for Teams)</span></span> | <span data-ttu-id="4498b-326">980</span><span class="sxs-lookup"><span data-stu-id="4498b-326">980</span></span> | <span data-ttu-id="4498b-327">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="4498b-327">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="4498b-328">true</span><span class="sxs-lookup"><span data-stu-id="4498b-328">true</span></span>

<span data-ttu-id="4498b-329">両方のトランクは、同じパブリック IP アドレスと同じ SBC を指すことができます。</span><span class="sxs-lookup"><span data-stu-id="4498b-329">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="4498b-330">TLS を SBC のポートの信号は、次の図に示すようである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4498b-330">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="4498b-331">証明書が両方のトランクをサポートしているかどうかを確認する必要があります注意してください。</span><span class="sxs-lookup"><span data-stu-id="4498b-331">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="4498b-332">SAN では、(**sbc1.contoso.com**および**sbc2.contoso.com**) の 2 つの名前またはワイルドカード証明書が存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4498b-332">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>


![表示の両方のトランクは、同じパブリック ip アドレスと同じ SBC を指すことができます)](media/direct-routing-media-bypass-7.png)

<span data-ttu-id="4498b-334">同じ SBC の 2 つのトランクを構成する方法の詳細については、SBC の製造元によって提供されるマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4498b-334">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

- <span data-ttu-id="4498b-335">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="4498b-335">AudioCodes</span></span>
- <span data-ttu-id="4498b-336">リボン</span><span class="sxs-lookup"><span data-stu-id="4498b-336">Ribbon</span></span>
- <span data-ttu-id="4498b-337">TE ・ システム (Anynode)</span><span class="sxs-lookup"><span data-stu-id="4498b-337">TE-Systems (Anynode)</span></span>   

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="4498b-338">メディアでサポートされているクライアントのエンドポイントを使用しません。</span><span class="sxs-lookup"><span data-stu-id="4498b-338">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="4498b-339">通知があるまでチームの Web クライアント以外、チームのすべてのエンドポイントでは、メディア バイ パスがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="4498b-339">Media bypass is supported with all Teams endpoints, except Teams Web clients until further notice.</span></span> 

<span data-ttu-id="4498b-340">場合マイクロソフトのエッジ、Google のクロムや Mozilla の Firefox のチームの Web アプリケーションは、ユーザーは、このようなユーザーに対してメディア バイ パスをオフにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4498b-340">If your users prefer Teams Web app in Microsoft Edge, Google Chrome or Mozilla Firefox, the media bypass for such users must be turned off.</span></span> <span data-ttu-id="4498b-341">メディアのバイパスが有効になっているトランクを使用して、将来的に呼び出すことを紹介します。</span><span class="sxs-lookup"><span data-stu-id="4498b-341">We will introduce calling using a media bypass enabled trunk in the future.</span></span>   
 
## <a name="see-also"></a><span data-ttu-id="4498b-342">関連項目</span><span class="sxs-lookup"><span data-stu-id="4498b-342">See also</span></span>

[<span data-ttu-id="4498b-343">ダイレクト ルーティングでメディア バイパスを構成する</span><span class="sxs-lookup"><span data-stu-id="4498b-343">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)



