---
title: Cloud Connector エディションでのメディア バイパスを計画する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: このトピックでは、Cloud Connector エディション バージョン 2.0 以降でのメディア バイパスの実装を計画する上で考慮すべき事項を説明します。 メディアを展開する方法については省略し、クラウド コネクタのエディションで使用しない展開メディアを参照してください。
ms.openlocfilehash: 70c7f8721386c3ef0270e7ef938624a70184b942
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967137"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="85b9e-104">Cloud Connector エディションでのメディア バイパスを計画する</span><span class="sxs-lookup"><span data-stu-id="85b9e-104">Plan for media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="85b9e-105">このトピックでは、Cloud Connector エディション バージョン 2.0 以降でのメディア バイパスの実装を計画する上で考慮すべき事項を説明します。</span><span class="sxs-lookup"><span data-stu-id="85b9e-105">Read this topic to review planning considerations for implementing media bypass with Cloud Connector Edition version 2.0 and later.</span></span> <span data-ttu-id="85b9e-106">メディアを展開する方法についてはバイパス、[コネクタのエディションをクラウドに展開メディアをバイパス](deploy-media-bypass-in-cloud-connector.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85b9e-106">For information about deploying media bypass, see [Deploy media bypass in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md).</span></span>
  
<span data-ttu-id="85b9e-107">メディア バイ パスにより、公衆交換電話網 (PSTN) の次のホップに直接メディアを送信するクライアント-ゲートウェイまたはセッション ボーダー コント ローラー (SBC)-メディアのパスからクラウドのコネクタのエディションのコンポーネントを削除するとします。</span><span class="sxs-lookup"><span data-stu-id="85b9e-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span>
  
<span data-ttu-id="85b9e-108">メディア バイパスにより、遅延、パケット損失の可能性、および潜在的な障害点の数を低減して、音声品質を向上できます。</span><span class="sxs-lookup"><span data-stu-id="85b9e-108">Media bypass can improve voice quality by reducing latency, the possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="85b9e-109">バイパスされる呼び出しの処理、メディアの消去では、クラウドのコネクタは、同時呼び出し数を設定するには、可能で負荷が減り、スケーラビリティを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="85b9e-109">Elimination of media processing for bypassed calls reduces the load on Cloud Connector, which enables a higher number of concurrent calls, and can improve scalability.</span></span> 
  
 <span data-ttu-id="85b9e-110">メディア タスクの処理からクラウドのコネクタを解放する可能性があります数を減らして、インフラストラクチャを必要とするクラウドのコネクタのアプライアンスの可能な場合、メディア バイ パスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="85b9e-110">Freeing Cloud Connector from media processing tasks may reduce the number of Cloud Connector appliances an infrastructure requires, so you should enable media bypass whenever possible.</span></span>
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a><span data-ttu-id="85b9e-111">メディア バイパスがメディアと信号の経路に及ぼす影響</span><span class="sxs-lookup"><span data-stu-id="85b9e-111">How media bypass affects media and signaling pathways</span></span>

<span data-ttu-id="85b9e-p104">信号はメディア バイパスの有無に関係なく同じ経路を通りますが、メディアの流れはその影響を受けて異なる経路を通ります。次の図は、メディア バイパスを使用した場合と使用しない場合の、トポロジ内のメディアと信号の経路を示しています。</span><span class="sxs-lookup"><span data-stu-id="85b9e-p104">While signaling takes the same path with or without media bypass, the media flow will differ. The following diagrams show media and signaling pathways in topologies with and without media bypass.</span></span> 
  
<span data-ttu-id="85b9e-114">次のトポロジでは、-はない採用メディアをバイパスなど、Skype のビジネスのクライアントは、PSTN の呼び出しを外部、Office 365 には、SIP シグナリングおよび Office 365 によって、エンド ・ ユーザーの音声信号のトラフィックを指示し、ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="85b9e-114">For example, in the following topology—which does not employ media bypass—a Skype for Business client places a PSTN call to an external number, the SIP signaling goes to Office 365, and Office 365 then directs the signaling traffic according to the end-user voice policy.</span></span> <span data-ttu-id="85b9e-115">クラウド コネクタのユーザーは、ボイス ポリシーは、クラウドのコネクタ エッジ サーバー、PSTN セッション ボーダー コント ローラー (SBC) またはクラウド コネクタの仲介サーバー経由でゲートウェイにシグナリング トラフィックをルーティングする信号のトラフィックを指示します。</span><span class="sxs-lookup"><span data-stu-id="85b9e-115">For Cloud Connector users, the voice policy directs signaling traffic to the Cloud Connector Edge Server, which then routes the signaling traffic to a PSTN Session Border Controller (SBC) or gateway via the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="85b9e-116">メディア フロー ビジネス クライアント用の Skype からクラウド コネクタの仲介サーバー、ゲートウェイ、SBC、次の図に示すように。</span><span class="sxs-lookup"><span data-stu-id="85b9e-116">Media flows from the Skype for Business client to the Cloud Connector Mediation Server, and then to the SBC or gateway, as shown in the following diagram:</span></span>
  
<span data-ttu-id="85b9e-117">**メディア バイパスを使用しない場合のメディアと信号の経路**</span><span class="sxs-lookup"><span data-stu-id="85b9e-117">**Media and signaling pathways without media bypass**</span></span>

![メディア バイパスなしの信号](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
<span data-ttu-id="85b9e-119">PSTN からの着信通話は、同一の信号経路を逆方向で使用します。</span><span class="sxs-lookup"><span data-stu-id="85b9e-119">An inbound call from the PSTN uses the same signaling path in the reverse direction.</span></span> <span data-ttu-id="85b9e-120">内部ユーザーにメディアがビジネス クライアント用の Skype とクラウド コネクタの仲介サーバーとし、SBC またはゲートウェイとの間も最終的にフローします。</span><span class="sxs-lookup"><span data-stu-id="85b9e-120">For internal users, media will still ultimately flow between the Skype for Business client and the Cloud Connector Mediation Server and then the SBC or gateway.</span></span>
  
<span data-ttu-id="85b9e-121">次のトポロジでは、-は採用メディアをバイパス、信号は、同じパスですが、メディアのビジネスのクライアント、および SBC またはゲートウェイ、Skype 間で直接フローを次の図に示すように。</span><span class="sxs-lookup"><span data-stu-id="85b9e-121">In the next topology—which does employ media bypass—signaling takes the same path, but media flows directly between the Skype for Business client and the SBC or gateway, as shown in the following diagram:</span></span>
  
<span data-ttu-id="85b9e-122">**メディア バイパスを使用する場合のメディアと信号の経路**</span><span class="sxs-lookup"><span data-stu-id="85b9e-122">**Media and signaling pathways with media bypass**</span></span>

![メディア バイパスありの信号](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a><span data-ttu-id="85b9e-124">マルチサイトのシナリオおよびメディア バイパス</span><span class="sxs-lookup"><span data-stu-id="85b9e-124">Multi-site scenario and media bypass</span></span>

<span data-ttu-id="85b9e-125">メディア バイ パスは、クラウドのコネクタの 1 つのアプライアンスを使用して複数のサイトに、テレフォニー サービスを提供する場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="85b9e-125">Media bypass is also useful when you want to provide telephony services to multiple sites using a single Cloud Connector appliance.</span></span> <span data-ttu-id="85b9e-126">クラウドのコネクタは、送信元または送信先の番号を基に呼をルーティングできません、ために、ほとんどの企業では、ルーティングを決定するのには、SBC やクラウドのコネクタの背後にあるゲートウェイを展開します。</span><span class="sxs-lookup"><span data-stu-id="85b9e-126">Because Cloud Connector cannot route calls based on source or destination numbers, most enterprises deploy an SBC or gateway behind Cloud Connector to make routing decisions.</span></span> <span data-ttu-id="85b9e-127">このシナリオでは、次の図に示すようにメディア バイパスによりクライアントと中央 SBC またはゲートウェイ間の転送が排除されています。</span><span class="sxs-lookup"><span data-stu-id="85b9e-127">Media bypass in this scenario eliminates the hop between the client and the central SBC or gateway, as shown in the following diagram:</span></span>
  
<span data-ttu-id="85b9e-128">**マルチサイトでの適用**</span><span class="sxs-lookup"><span data-stu-id="85b9e-128">**Multi-site application**</span></span>

![Cloud Connector のマルチサイトの例](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. <span data-ttu-id="85b9e-130">SIP トラフィックでは、Office 365 にチューリッヒのユーザーから送られます。</span><span class="sxs-lookup"><span data-stu-id="85b9e-130">The SIP traffic flows from the user in Zurich to Office 365.</span></span>
    
2. <span data-ttu-id="85b9e-131">トラフィックは、アプライアンスは、ユーザーの音声ルーティング ポリシーで指定されているアムステルダムのクラウドのコネクタにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="85b9e-131">The traffic then routes to the Cloud Connector appliance in Amsterdam as specified in the user voice routing policy.</span></span>
    
3. <span data-ttu-id="85b9e-132">アムステルダムにコネクタのクラウド アプライアンスは、アムステルダムで中心的なゲートウェイに SIP トラフィックを送信します。</span><span class="sxs-lookup"><span data-stu-id="85b9e-132">The Cloud Connector appliance in Amsterdam sends the SIP traffic to the central gateway in Amsterdam.</span></span>
    
4. <span data-ttu-id="85b9e-133">アムステルダムで中央のゲートウェイは、適切なルーティングの決定は、し、SBC やチューリッヒ、ビジネス クライアントと SBC またはアムステルダムにゲートウェイの Skype 間で直接メディア フロー中にゲートウェイにトラフィックを送信します。</span><span class="sxs-lookup"><span data-stu-id="85b9e-133">The central gateway in Amsterdam makes the appropriate routing decisions, and then sends the traffic to an SBC or gateway in Zurich, while media flows directly between the Skype for Business client and SBC or gateway in Amsterdam.</span></span>
    
 <span data-ttu-id="85b9e-134">このアプローチにより、クラウドのコネクタが一元化され、クラウド コネクタの展開を 1 つあたりのより多くのユーザーにサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="85b9e-134">This approach allows serving more users per one Cloud Connector deployment where Cloud Connector is centralized.</span></span> <span data-ttu-id="85b9e-135">メディア パスから削除されると、クラウドのコネクタも、一元的なマルチサイトのシナリオでメディア可能性がありますも WAN に送り出さ一元的な SBC またはゲートウェイを通過するのには必要に応じて 2 回です。</span><span class="sxs-lookup"><span data-stu-id="85b9e-135">Even though Cloud Connector is eliminated from the media path, in a centralized multi-site scenario media may still traverse the WAN twice as required to flow through the centralized SBC or gateway.</span></span>
  
<span data-ttu-id="85b9e-136">クライアントが発信呼び出しを配置する企業ネットワークの外部にある場合は、メディア トラフィックは次の図に示すように、チューリッヒ、アムステルダムの間でのクラウドのコネクタおよび WAN リンクのエッジと仲介サーバーを経由して配信されます。</span><span class="sxs-lookup"><span data-stu-id="85b9e-136">If a client is outside the corporate network placing an outbound call, the media traffic flows via the Edge and Mediation servers of Cloud Connector and WAN link between Zurich and Amsterdam, as shown in the following diagram:</span></span>
  
![Cloud Connector のマルチサイトの例 2](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a><span data-ttu-id="85b9e-138">メディア バイパスでサポートされるクライアント</span><span class="sxs-lookup"><span data-stu-id="85b9e-138">Supported clients for media bypass</span></span>

<span data-ttu-id="85b9e-139">メディア バイ パスの最初のリリースでのみサポートされているクライアントは、Office 365 用リソース、バージョン 16.0.7870.2020 の一部であるビジネス 2016年の Windows クライアントの Skype またはそれ以上です。</span><span class="sxs-lookup"><span data-stu-id="85b9e-139">With the first release of media bypass, the only supported client is the Skype for Business 2016 Windows Client that is part of Office 365 ProPlus, version 16.0.7870.2020 or greater.</span></span> <span data-ttu-id="85b9e-140">お客様は、最新機能提供、段階的提供、段階的提供チャネルの最初のリリースから任意のチャネルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="85b9e-140">Customers can use any channel: Current, Deferred, or First Release Deferred.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="85b9e-141">クライアント VPN ソリューションを Skype for Business クライアントと組み合わせて使用している場合、メディア バイパスは VPN 分割トンネル構成でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="85b9e-141">If you are using a client VPN solution in combination with the Skype for Business client, then media bypass is supported only with a VPN split-tunnel configuration.</span></span> 
  
<span data-ttu-id="85b9e-142">リリース チャネルの詳細については、 [Office 365 用リソースの更新チャンネルの概要](https://support.office.com/en-us/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85b9e-142">For more information about the release channels, see [Overview of update channels for Office 365 ProPlus](https://support.office.com/en-us/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
<span data-ttu-id="85b9e-143">さまざまなチャネルでクライアントの現在のリリース バージョンは、[リリースの Office 365 用リソースへの更新情報](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85b9e-143">For the current release version of the clients in different channels, see [Release information for updates to Office 365 ProPlus](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus).</span></span> 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a><span data-ttu-id="85b9e-144">メディア バイパスに関連する Cloud Connector の容量の考慮事項</span><span class="sxs-lookup"><span data-stu-id="85b9e-144">Cloud Connector capacity considerations with media bypass</span></span>

<span data-ttu-id="85b9e-145">メディアを省略せず、およびハードウェアによって-コネクタのクラウド アプライアンスは、50 から仲介サーバーを経由するようにメディアを必要とする 500 の同時呼び出しを処理できます。</span><span class="sxs-lookup"><span data-stu-id="85b9e-145">Without media bypass—and depending on the hardware—a Cloud Connector appliance can handle from 50 to 500 simultaneous calls that require media to travel through a Mediation Server.</span></span> <span data-ttu-id="85b9e-146">詳細については、 [Skype ビジネス クラウド コネクタ ・ エディションの計画](https://technet.microsoft.com/en-us/library/mt605227.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85b9e-146">For more information, see [Plan for Skype for Business Cloud Connector Edition](https://technet.microsoft.com/en-us/library/mt605227.aspx).</span></span> 
  
<span data-ttu-id="85b9e-147">メディア バイパスを使用すると、サポートされるバージョンの内部クライアントでは仲介サーバーが使用されないため、内部クライアントの数を大幅に増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="85b9e-147">With media bypass enabled, internal clients on the supported version do not use the Mediation Server, so the number of internal clients can increase significantly.</span></span> 
  
<span data-ttu-id="85b9e-148">前述したように、外部のクライアント、またはサポートされていないクライアント、メディアのコネクタの端をクラウドと仲介サーバーを使用しています。</span><span class="sxs-lookup"><span data-stu-id="85b9e-148">As noted above, external clients or unsupported clients will use the Cloud Connector Edge and Mediation servers for media.</span></span> <span data-ttu-id="85b9e-149">クラウド コネクタ アプライアンスの数は、サイトに配置する必要がありますを計算するときは、外部のユーザーとユーザーがサポートされていないクライアントからのトラフィックを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85b9e-149">When calculating how many Cloud Connector appliances should be placed in a site, you must consider traffic from external users and users on unsupported clients.</span></span>
  
## <a name="cloud-connector-supports-always-bypass-mode"></a><span data-ttu-id="85b9e-150">Cloud Connector による [常にバイパスする] モードのサポート</span><span class="sxs-lookup"><span data-stu-id="85b9e-150">Cloud Connector supports Always Bypass mode</span></span>

<span data-ttu-id="85b9e-151">クラウドのコネクタには、常にバイパス モードのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="85b9e-151">Cloud Connector supports Always Bypass mode only.</span></span> <span data-ttu-id="85b9e-152">オンプレミス環境では、[常にバイパスする] と [サイトおよび地域情報の使用] の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="85b9e-152">In on-premises environments, there are two options: Always Bypass and Use Site and Region Information.</span></span>
  
<span data-ttu-id="85b9e-p113">[常にバイパスする] では、内部クライアントを発信元または発信先とするすべての PSTN 通話に対してメディア バイパスが試行されます。クライアントが内部または外部のクライアントであるかを判別するには、仲介サーバーの仮想マシン上にある Web サイトを使用します。クライアントがサイトに到達できる場合は、内部クライアントであると見なされて、メディア バイパスが使用されます。クライアントがサイトに到達できない場合 (たとえば、クライアントがホーム ネットワーク上に存在しない場合)、メディア バイパスは使用されません。</span><span class="sxs-lookup"><span data-stu-id="85b9e-p113">Always Bypass means that media bypass will be attempted for all PSTN calls with internal clients as an origin or destination point. To determine if the client is internal or external, a web site on the mediation server virtual machine is used. If the client can reach the site, it is considered internal and media bypass is used. If the client cannot reach the site (for example the client is on a home network), media bypass is not used.</span></span> 
  
<span data-ttu-id="85b9e-157">[常にバイパスする] を使用するには、PSTN サイト内でユーザーと PSTN ゲートウェイ間に妨げのない接続が必要になります。</span><span class="sxs-lookup"><span data-stu-id="85b9e-157">Always Bypass requires unobstructed connectivity between users and the PSTN gateways within a PSTN Site.</span></span> 
  
<span data-ttu-id="85b9e-158">詳細については、 [Skype ビジネス クラウド コネクタ ・ エディションの計画](https://technet.microsoft.com/en-us/library/mt605227.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85b9e-158">For more information, see [Plan for Skype for Business Cloud Connector Edition](https://technet.microsoft.com/en-us/library/mt605227.aspx).</span></span> 
  
<span data-ttu-id="85b9e-159">などの下の図では、ヨーロッパのユーザーする必要があります 3 つのセッション ボーダー コント ローラー (SBCs) アムステルダムに適切に接続されて中に、米国の西のユーザーは、シアトルの 2 つの半角英数字にも接続されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="85b9e-159">For example, in the diagram below, Europe users must be well connected to the three Session Border Controllers (SBCs) in Amsterdam while US West users must be well connected to the two SBCs in Seattle.</span></span> <span data-ttu-id="85b9e-160">良好な接続性とは、ユーザーが SBC またはゲートウェイとしての同一ネットワーク サイト内に存在するか、適切なバンド幅を備えた WAN リンク上に存在することを意味します。</span><span class="sxs-lookup"><span data-stu-id="85b9e-160">Well connected means that they are either located in the same network sites as the SBCs or gateways, or over WAN links that have proper bandwidth.</span></span>
  
![Cloud Connector の処理能力](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> <span data-ttu-id="85b9e-162">ユーザーがチューリッヒからシアトルのオフィスに移動する場合に、そのユーザーとヨーロッパのゲートウェイ間でメディア トラフィックを可能にするために (インターネットの代わりに) 内部ネットワークを使用するには、ヨーロッパの SBC またはゲートウェイが配置されているアムステルダム オフィスとシアトル オフィスが良好な接続性を保っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="85b9e-162">If a user from Zurich travels to the Seattle office, and you want to use the internal network to deliver media traffic between the traveling user and gateways in Europe (as opposed to going over the Internet), then you must make sure the Seattle office and the Amsterdam office where European SBCs or gateways are located qualify as well connected.</span></span> 
  
## <a name="codecs-used-in-media-bypass"></a><span data-ttu-id="85b9e-163">メディア バイパスで使用されるコーデック</span><span class="sxs-lookup"><span data-stu-id="85b9e-163">Codecs used in media bypass</span></span>

<span data-ttu-id="85b9e-164">メディア バイパスを有効にすると、クライアントと SBC またはゲートウェイ間で G.711 コーデックが使用されます。</span><span class="sxs-lookup"><span data-stu-id="85b9e-164">With media bypass enabled, media traffic between a client and an SBC or gateway uses the G.711 codec.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="85b9e-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="85b9e-165">See also</span></span>

[<span data-ttu-id="85b9e-166">Cloud Connector エディションでメディア バイパスを展開する</span><span class="sxs-lookup"><span data-stu-id="85b9e-166">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md)