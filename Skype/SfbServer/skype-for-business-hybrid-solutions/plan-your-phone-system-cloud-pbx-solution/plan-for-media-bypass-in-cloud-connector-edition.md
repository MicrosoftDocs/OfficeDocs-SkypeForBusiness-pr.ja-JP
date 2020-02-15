---
title: Cloud Connector エディションでメディアバイパスを計画する
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: このトピックでは、Cloud Connector エディションバージョン2.0 以降でメディアバイパスを実装する場合の計画の検討事項について説明します。 メディアバイパスの展開の詳細については、「Cloud Connector エディションでメディアバイパスを展開する」を参照してください。
ms.openlocfilehash: 47b8d9e5d0b69b95c48f89591d75d53591b7426c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010310"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="6efcc-104">Cloud Connector エディションでメディアバイパスを計画する</span><span class="sxs-lookup"><span data-stu-id="6efcc-104">Plan for media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="6efcc-105">このトピックでは、Cloud Connector エディションバージョン2.0 以降でメディアバイパスを実装する場合の計画の検討事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="6efcc-105">Read this topic to review planning considerations for implementing media bypass with Cloud Connector Edition version 2.0 and later.</span></span> <span data-ttu-id="6efcc-106">メディアバイパスの展開の詳細については、「 [Cloud Connector エディションでメディアバイパスを展開](deploy-media-bypass-in-cloud-connector.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6efcc-106">For information about deploying media bypass, see [Deploy media bypass in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md).</span></span>
  
<span data-ttu-id="6efcc-107">メディアバイパスを使用すると、クライアントはメディアを公衆交換電話網 (PSTN) の次ホップに直接送信できます。ゲートウェイまたはセッションボーダーコントローラー (SBC) を使用して、Cloud Connector Edition コンポーネントをメディアパスから削除します。</span><span class="sxs-lookup"><span data-stu-id="6efcc-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span>
  
<span data-ttu-id="6efcc-108">メディアバイパスは、待機時間、パケット損失の可能性、および潜在的な障害点の数を減らすことで、音声品質を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="6efcc-108">Media bypass can improve voice quality by reducing latency, the possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="6efcc-109">バイパスされた通話のメディア処理を排除することで、クラウドコネクタの負荷が軽減されます。これにより、同時呼び出しの数が増加し、スケーラビリティが向上します。</span><span class="sxs-lookup"><span data-stu-id="6efcc-109">Elimination of media processing for bypassed calls reduces the load on Cloud Connector, which enables a higher number of concurrent calls, and can improve scalability.</span></span> 
  
 <span data-ttu-id="6efcc-110">クラウドコネクタをメディア処理タスクから解放すると、インフラストラクチャに必要な Cloud Connector アプライアンスの数が減少する可能性があるため、可能な場合は常にメディアバイパスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6efcc-110">Freeing Cloud Connector from media processing tasks may reduce the number of Cloud Connector appliances an infrastructure requires, so you should enable media bypass whenever possible.</span></span>
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a><span data-ttu-id="6efcc-111">メディアバイパスがメディアと信号経路に与える影響</span><span class="sxs-lookup"><span data-stu-id="6efcc-111">How media bypass affects media and signaling pathways</span></span>

<span data-ttu-id="6efcc-112">信号はメディアバイパスの有無にかかわらず同じパスになりますが、メディアの流れは異なります。</span><span class="sxs-lookup"><span data-stu-id="6efcc-112">While signaling takes the same path with or without media bypass, the media flow will differ.</span></span> <span data-ttu-id="6efcc-113">次の図は、メディアバイパスを使用する場合と使用しない場合のトポロジでのメディアと信号経路を示しています。</span><span class="sxs-lookup"><span data-stu-id="6efcc-113">The following diagrams show media and signaling pathways in topologies with and without media bypass.</span></span> 
  
<span data-ttu-id="6efcc-114">たとえば、メディアバイパスが使用されていない次のトポロジでは、Skype for Business クライアントは PSTN 通話を外部番号に接続し、SIP シグナリングは Office 365 に送られ、Office 365 はエンドユーザーの音声に従ってシグナルトラフィックを送信します。原則.</span><span class="sxs-lookup"><span data-stu-id="6efcc-114">For example, in the following topology—which does not employ media bypass—a Skype for Business client places a PSTN call to an external number, the SIP signaling goes to Office 365, and Office 365 then directs the signaling traffic according to the end-user voice policy.</span></span> <span data-ttu-id="6efcc-115">Cloud Connector ユーザーの場合、音声ポリシーは、シグナリングトラフィックを Cloud Connector エッジサーバーにリダイレクトします。これにより、シグナリングトラフィックは、Cloud Connector 仲介サーバーを介して PSTN セッションボーダーコントローラー (SBC) またはゲートウェイにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="6efcc-115">For Cloud Connector users, the voice policy directs signaling traffic to the Cloud Connector Edge Server, which then routes the signaling traffic to a PSTN Session Border Controller (SBC) or gateway via the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="6efcc-116">メディアは、次の図に示すように、Skype for Business クライアントから Cloud Connector 仲介サーバー、次に SBC またはゲートウェイに流れます。</span><span class="sxs-lookup"><span data-stu-id="6efcc-116">Media flows from the Skype for Business client to the Cloud Connector Mediation Server, and then to the SBC or gateway, as shown in the following diagram:</span></span>
  
<span data-ttu-id="6efcc-117">**メディアバイパスを使用しないメディアおよび信号経路**</span><span class="sxs-lookup"><span data-stu-id="6efcc-117">**Media and signaling pathways without media bypass**</span></span>

![メディアバイパスを使用しない信号](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
<span data-ttu-id="6efcc-119">PSTN からの着信通話では、逆方向の同じ信号パスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6efcc-119">An inbound call from the PSTN uses the same signaling path in the reverse direction.</span></span> <span data-ttu-id="6efcc-120">内部ユーザーの場合、メディアは引き続き、Skype for Business クライアントと Cloud Connector 仲介サーバー、次に SBC またはゲートウェイの間でフローします。</span><span class="sxs-lookup"><span data-stu-id="6efcc-120">For internal users, media will still ultimately flow between the Skype for Business client and the Cloud Connector Mediation Server and then the SBC or gateway.</span></span>
  
<span data-ttu-id="6efcc-121">次のトポロジでは、メディアバイパスが使用されますが、次の図に示すように、media は Skype for Business クライアントと SBC またはゲートウェイの間で直接転送されます。</span><span class="sxs-lookup"><span data-stu-id="6efcc-121">In the next topology—which does employ media bypass—signaling takes the same path, but media flows directly between the Skype for Business client and the SBC or gateway, as shown in the following diagram:</span></span>
  
<span data-ttu-id="6efcc-122">**メディアバイパスを使用したメディアと信号の経路**</span><span class="sxs-lookup"><span data-stu-id="6efcc-122">**Media and signaling pathways with media bypass**</span></span>

![メディアバイパスを使用した信号](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a><span data-ttu-id="6efcc-124">マルチサイトのシナリオおよびメディアバイパス</span><span class="sxs-lookup"><span data-stu-id="6efcc-124">Multi-site scenario and media bypass</span></span>

<span data-ttu-id="6efcc-125">メディアバイパスは、単一の Cloud Connector アプライアンスを使用して、複数のサイトにテレフォニーサービスを提供する場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6efcc-125">Media bypass is also useful when you want to provide telephony services to multiple sites using a single Cloud Connector appliance.</span></span> <span data-ttu-id="6efcc-126">Cloud Connector は発信元または宛先番号に基づいて通話をルーティングできないため、ほとんどの企業では、ルーティングを決定するために、クラウドコネクタの背後に SBC またはゲートウェイを展開しています。</span><span class="sxs-lookup"><span data-stu-id="6efcc-126">Because Cloud Connector cannot route calls based on source or destination numbers, most enterprises deploy an SBC or gateway behind Cloud Connector to make routing decisions.</span></span> <span data-ttu-id="6efcc-127">メディアバイパスこのシナリオでは、次の図に示すように、クライアントと中央の SBC またはゲートウェイ間のホップを削除します。</span><span class="sxs-lookup"><span data-stu-id="6efcc-127">Media bypass in this scenario eliminates the hop between the client and the central SBC or gateway, as shown in the following diagram:</span></span>
  
<span data-ttu-id="6efcc-128">**マルチサイトアプリケーション**</span><span class="sxs-lookup"><span data-stu-id="6efcc-128">**Multi-site application**</span></span>

![Cloud Connector のマルチサイトの例](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. <span data-ttu-id="6efcc-130">SIP トラフィックは、Zurich フルタ内のユーザーから Office 365 に送られます。</span><span class="sxs-lookup"><span data-stu-id="6efcc-130">The SIP traffic flows from the user in Zurich to Office 365.</span></span>
    
2. <span data-ttu-id="6efcc-131">次に、ユーザーの音声ルーティングポリシーで指定されているように、アムステルダムの Cloud Connector アプライアンスにトラフィックがルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="6efcc-131">The traffic then routes to the Cloud Connector appliance in Amsterdam as specified in the user voice routing policy.</span></span>
    
3. <span data-ttu-id="6efcc-132">アムステルダムの Cloud Connector アプライアンスは、アムステルダムにある中央ゲートウェイに SIP トラフィックを送信します。</span><span class="sxs-lookup"><span data-stu-id="6efcc-132">The Cloud Connector appliance in Amsterdam sends the SIP traffic to the central gateway in Amsterdam.</span></span>
    
4. <span data-ttu-id="6efcc-133">アムステルダムにある中央ゲートウェイは、適切なルーティング決定を行い、そのトラフィックを Zurich フルタの SBC またはゲートウェイに送信します。メディアは、「Skype for Business クライアントと、アムステルダムの SBC またはゲートウェイの間で直接フローします。</span><span class="sxs-lookup"><span data-stu-id="6efcc-133">The central gateway in Amsterdam makes the appropriate routing decisions, and then sends the traffic to an SBC or gateway in Zurich, while media flows directly between the Skype for Business client and SBC or gateway in Amsterdam.</span></span>
    
   <span data-ttu-id="6efcc-134">このアプローチを使用すると、cloud connector が集中管理されているクラウドコネクタ展開1つにつき、より多くのユーザーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="6efcc-134">This approach allows serving more users per one Cloud Connector deployment where Cloud Connector is centralized.</span></span> <span data-ttu-id="6efcc-135">クラウドコネクタがメディアパスから除外されている場合でも、集中化された複数サイトシナリオでは、集中型 SBC またはゲートウェイを通過するために必要とされるように、WAN を2回通過する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6efcc-135">Even though Cloud Connector is eliminated from the media path, in a centralized multi-site scenario media may still traverse the WAN twice as required to flow through the centralized SBC or gateway.</span></span>
  
<span data-ttu-id="6efcc-136">クライアントが企業ネットワークの外部に発信呼び出しを行う場合、メディアトラフィックは、次の図に示すように、Cloud Connector のエッジサーバーと仲介サーバー、および Zurich フルタとアムステルダム間の WAN リンクを経由してフローします。</span><span class="sxs-lookup"><span data-stu-id="6efcc-136">If a client is outside the corporate network placing an outbound call, the media traffic flows via the Edge and Mediation servers of Cloud Connector and WAN link between Zurich and Amsterdam, as shown in the following diagram:</span></span>
  
![Cloud Connector のマルチサイトの例2](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a><span data-ttu-id="6efcc-138">メディアバイパスに対してサポートされているクライアント</span><span class="sxs-lookup"><span data-stu-id="6efcc-138">Supported clients for media bypass</span></span>

<span data-ttu-id="6efcc-139">メディアバイパスの最初のリリースでは、サポートされている唯一のクライアントは、Office 365 ProPlus、バージョン16.0.7870.2020 またはそれ以上の一部である Skype for Business 2016 Windows クライアントです。</span><span class="sxs-lookup"><span data-stu-id="6efcc-139">With the first release of media bypass, the only supported client is the Skype for Business 2016 Windows Client that is part of Office 365 ProPlus, version 16.0.7870.2020 or greater.</span></span> <span data-ttu-id="6efcc-140">お客様は、現在、延期、または最初のリリース延期を使用して、任意のチャネルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6efcc-140">Customers can use any channel: Current, Deferred, or First Release Deferred.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6efcc-141">クライアントの VPN ソリューションを Skype for Business クライアントと組み合わせて使用している場合、メディアバイパスは VPN 分割トンネル構成でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="6efcc-141">If you are using a client VPN solution in combination with the Skype for Business client, then media bypass is supported only with a VPN split-tunnel configuration.</span></span> 
  
<span data-ttu-id="6efcc-142">リリースチャネルの詳細については、「 [Office 365 ProPlus の更新プログラムチャネルの概要](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6efcc-142">For more information about the release channels, see [Overview of update channels for Office 365 ProPlus](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
<span data-ttu-id="6efcc-143">異なるチャネルにあるクライアントの現在のリリースバージョンについては、「 [Office 365 ProPlus への更新プログラムのリリース情報](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6efcc-143">For the current release version of the clients in different channels, see [Release information for updates to Office 365 ProPlus](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus).</span></span> 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a><span data-ttu-id="6efcc-144">メディアバイパスに関する Cloud Connector の容量に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="6efcc-144">Cloud Connector capacity considerations with media bypass</span></span>

<span data-ttu-id="6efcc-145">メディアバイパスを使用せず、ハードウェアに応じて、Cloud Connector アプライアンスは、仲介サーバーを経由してメディアを通過する必要がある50から500の同時通話を処理できます。</span><span class="sxs-lookup"><span data-stu-id="6efcc-145">Without media bypass—and depending on the hardware—a Cloud Connector appliance can handle from 50 to 500 simultaneous calls that require media to travel through a Mediation Server.</span></span> <span data-ttu-id="6efcc-146">詳細については、「 [Plan For Skype for Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605227.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6efcc-146">For more information, see [Plan for Skype for Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605227.aspx).</span></span> 
  
<span data-ttu-id="6efcc-147">メディアバイパスが有効になっている場合、サポートされているバージョンの内部クライアントが仲介サーバーを使用しないため、内部クライアントの数が大幅に増加する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6efcc-147">With media bypass enabled, internal clients on the supported version do not use the Mediation Server, so the number of internal clients can increase significantly.</span></span> 
  
<span data-ttu-id="6efcc-148">前述したように、外部クライアントまたはサポートされていないクライアントは、メディア用の Cloud Connector エッジと仲介サーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="6efcc-148">As noted above, external clients or unsupported clients will use the Cloud Connector Edge and Mediation servers for media.</span></span> <span data-ttu-id="6efcc-149">サイトに配置する必要がある Cloud Connector アプライアンスの数を計算する場合は、サポートされていないクライアントの外部ユーザーとユーザーからのトラフィックを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6efcc-149">When calculating how many Cloud Connector appliances should be placed in a site, you must consider traffic from external users and users on unsupported clients.</span></span>
  
## <a name="cloud-connector-supports-always-bypass-mode"></a><span data-ttu-id="6efcc-150">Cloud Connector は常にバイパスモードをサポートする</span><span class="sxs-lookup"><span data-stu-id="6efcc-150">Cloud Connector supports Always Bypass mode</span></span>

<span data-ttu-id="6efcc-151">Cloud Connector は常にバイパスモードのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="6efcc-151">Cloud Connector supports Always Bypass mode only.</span></span> <span data-ttu-id="6efcc-152">オンプレミスの環境では、2つのオプションがあります。常にバイパスして、サイトと地域の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="6efcc-152">In on-premises environments, there are two options: Always Bypass and Use Site and Region Information.</span></span>
  
<span data-ttu-id="6efcc-153">常にバイパスとは、内部クライアントと送信元または送信先のすべての PSTN 通話に対してメディアバイパスが試行されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="6efcc-153">Always Bypass means that media bypass will be attempted for all PSTN calls with internal clients as an origin or destination point.</span></span> <span data-ttu-id="6efcc-154">クライアントが内部か外部かを判断するには、仲介サーバーの仮想マシン上の web サイトが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6efcc-154">To determine if the client is internal or external, a web site on the mediation server virtual machine is used.</span></span> <span data-ttu-id="6efcc-155">クライアントがサイトに到達できる場合は、[内部] として認識され、メディアバイパスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6efcc-155">If the client can reach the site, it is considered internal and media bypass is used.</span></span> <span data-ttu-id="6efcc-156">クライアントがサイトに到達できない場合 (たとえば、クライアントがホームネットワーク上にある場合)、メディアバイパスは使用されません。</span><span class="sxs-lookup"><span data-stu-id="6efcc-156">If the client cannot reach the site (for example the client is on a home network), media bypass is not used.</span></span> 
  
<span data-ttu-id="6efcc-157">常にバイパスする必要があるのは、PSTN サイト内のユーザーと PSTN ゲートウェイ間の接続に障害がある場合です。</span><span class="sxs-lookup"><span data-stu-id="6efcc-157">Always Bypass requires unobstructed connectivity between users and the PSTN gateways within a PSTN Site.</span></span> 
  
<span data-ttu-id="6efcc-158">詳細については、「 [Plan For Skype for Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605227.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6efcc-158">For more information, see [Plan for Skype for Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605227.aspx).</span></span> 
  
<span data-ttu-id="6efcc-159">たとえば、次の図では、ヨーロッパユーザーがアムステルダムの3つのセッションボーダーコントローラー (sbc) に適切に接続されている必要がありますが、US 西部ユーザーはシアトルの2つの SBCs に十分に接続されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6efcc-159">For example, in the diagram below, Europe users must be well connected to the three Session Border Controllers (SBCs) in Amsterdam while US West users must be well connected to the two SBCs in Seattle.</span></span> <span data-ttu-id="6efcc-160">適切に接続されているということは、それらが SBCs またはゲートウェイと同じネットワークサイトにあるか、または適切な帯域幅を持つ WAN リンクに配置されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="6efcc-160">Well connected means that they are either located in the same network sites as the SBCs or gateways, or over WAN links that have proper bandwidth.</span></span>
  
![Cloud Connector の容量](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> <span data-ttu-id="6efcc-162">Zurich フルタのユーザーがシアトルのオフィスに移動し、内部ネットワークを使用して、(インターネットを経由するのではなく) ヨーロッパの移動元のユーザーとゲートウェイ間のメディアトラフィックを配信する場合は、シアトルのオフィスとアムステルダムにいることを確認する必要があります。ヨーロッパの SBCs またはゲートウェイが配置されている office。適切に接続されています。</span><span class="sxs-lookup"><span data-stu-id="6efcc-162">If a user from Zurich travels to the Seattle office, and you want to use the internal network to deliver media traffic between the traveling user and gateways in Europe (as opposed to going over the Internet), then you must make sure the Seattle office and the Amsterdam office where European SBCs or gateways are located qualify as well connected.</span></span> 
  
## <a name="codecs-used-in-media-bypass"></a><span data-ttu-id="6efcc-163">メディアバイパスで使用されるコーデック</span><span class="sxs-lookup"><span data-stu-id="6efcc-163">Codecs used in media bypass</span></span>

<span data-ttu-id="6efcc-164">メディアバイパスが有効になっている場合、クライアントと SBC またはゲートウェイ間のメディアトラフィックでは、A-g-dl-p コーデックが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6efcc-164">With media bypass enabled, media traffic between a client and an SBC or gateway uses the G.711 codec.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6efcc-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="6efcc-165">See also</span></span>

[<span data-ttu-id="6efcc-166">Cloud Connector エディションでのメディアバイパスの展開</span><span class="sxs-lookup"><span data-stu-id="6efcc-166">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md)
