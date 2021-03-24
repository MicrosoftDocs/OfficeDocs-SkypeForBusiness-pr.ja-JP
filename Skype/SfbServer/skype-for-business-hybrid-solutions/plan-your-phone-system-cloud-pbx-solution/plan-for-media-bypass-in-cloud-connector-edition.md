---
title: クラウド コネクタ エディションでのメディア バイパスの計画
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
description: このトピックを参照して、Cloud Connector Edition バージョン 2.0 以降でメディア バイパスを実装するための計画に関する考慮事項を確認してください。 メディア バイパスの展開の詳細については、「Deploy media bypass in Cloud Connector Edition」を参照してください。
ms.openlocfilehash: bae10c77a6b382eaca7189ed6ae52960a6fb1bf9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096201"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="c8e1e-104">クラウド コネクタ エディションでのメディア バイパスの計画</span><span class="sxs-lookup"><span data-stu-id="c8e1e-104">Plan for media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="c8e1e-105">このトピックを参照して、Cloud Connector Edition バージョン 2.0 以降でメディア バイパスを実装するための計画に関する考慮事項を確認してください。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-105">Read this topic to review planning considerations for implementing media bypass with Cloud Connector Edition version 2.0 and later.</span></span> <span data-ttu-id="c8e1e-106">メディア バイパスの展開の詳細については [、「Deploy media bypass in Cloud Connector Edition」を参照してください](deploy-media-bypass-in-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-106">For information about deploying media bypass, see [Deploy media bypass in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md).</span></span>
  
<span data-ttu-id="c8e1e-107">メディア バイパスを使用すると、クライアントはパブリック 交換電話網 (PSTN) ネクスト ホップ (ゲートウェイまたはセッション ボーダー コントローラー (SBC)) にメディアを直接送信し、メディア パスから Cloud Connector Edition コンポーネントを削除できます。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span>
  
<span data-ttu-id="c8e1e-108">メディア バイパスは、遅延、パケット損失の可能性、および潜在的な障害のポイント数を減らすことによって、音声品質を向上できます。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-108">Media bypass can improve voice quality by reducing latency, the possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="c8e1e-109">バイパスされた呼び出しのメディア処理を排除すると、クラウド コネクタの負荷が軽減され、同時呼び出しの数が増え、スケーラビリティが向上します。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-109">Elimination of media processing for bypassed calls reduces the load on Cloud Connector, which enables a higher number of concurrent calls, and can improve scalability.</span></span> 
  
 <span data-ttu-id="c8e1e-110">クラウド コネクタをメディア処理タスクから解放すると、インフラストラクチャで必要なクラウド コネクタ アプライアンスの数が減る可能性があります。そのため、可能な限りメディア バイパスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-110">Freeing Cloud Connector from media processing tasks may reduce the number of Cloud Connector appliances an infrastructure requires, so you should enable media bypass whenever possible.</span></span>
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a><span data-ttu-id="c8e1e-111">メディア バイパスがメディアおよび信号経路に与える影響</span><span class="sxs-lookup"><span data-stu-id="c8e1e-111">How media bypass affects media and signaling pathways</span></span>

<span data-ttu-id="c8e1e-112">信号はメディア バイパスの場合と使用しない場合と同じパスを使用しますが、メディア フローは異なります。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-112">While signaling takes the same path with or without media bypass, the media flow will differ.</span></span> <span data-ttu-id="c8e1e-113">次の図は、メディア バイパスの場合と使用しないトポロジのメディアと信号経路を示しています。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-113">The following diagrams show media and signaling pathways in topologies with and without media bypass.</span></span> 
  
<span data-ttu-id="c8e1e-114">たとえば、メディア バイパスを使用しない次のトポロジでは、Skype for Business クライアントが PSTN 呼び出しを外部番号に発信すると、SIP シグナリングは Microsoft 365 または Office 365 に送信され、エンド ユーザーの音声ポリシーに従ってシグナリング トラフィックが送信されます。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-114">For example, in the following topology—which does not employ media bypass—a Skype for Business client places a PSTN call to an external number, the SIP signaling goes to Microsoft 365 or Office 365, which directs the signaling traffic according to the end-user voice policy.</span></span> <span data-ttu-id="c8e1e-115">クラウド コネクタ ユーザーの場合、音声ポリシーはシグナリング トラフィックをクラウド コネクタ エッジ サーバーに送信し、その信号トラフィックを PSTN セッション ボーダー コントローラー (SBC) またはゲートウェイをクラウド コネクタ 仲介サーバー経由でルーティングします。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-115">For Cloud Connector users, the voice policy directs signaling traffic to the Cloud Connector Edge Server, which then routes the signaling traffic to a PSTN Session Border Controller (SBC) or gateway via the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="c8e1e-116">次の図に示すように、メディアは Skype for Business クライアントからクラウド コネクタ 仲介サーバーに、次に SBC またはゲートウェイに流れます。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-116">Media flows from the Skype for Business client to the Cloud Connector Mediation Server, and then to the SBC or gateway, as shown in the following diagram:</span></span>
  
<span data-ttu-id="c8e1e-117">**メディア バイパスのないメディアと信号経路**</span><span class="sxs-lookup"><span data-stu-id="c8e1e-117">**Media and signaling pathways without media bypass**</span></span>

![メディア バイパスなしのシグナリング](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
<span data-ttu-id="c8e1e-119">PSTN からの着信呼び出しは、逆方向に同じ信号パスを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-119">An inbound call from the PSTN uses the same signaling path in the reverse direction.</span></span> <span data-ttu-id="c8e1e-120">内部ユーザーの場合、メディアは最終的には Skype for Business クライアントとクラウド コネクタ仲介サーバー、次に SBC またはゲートウェイの間を流れる。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-120">For internal users, media will still ultimately flow between the Skype for Business client and the Cloud Connector Mediation Server and then the SBC or gateway.</span></span>
  
<span data-ttu-id="c8e1e-121">次のトポロジでは、メディア バイパスを使用しますが、シグナリングは同じパスを使用しますが、次の図に示すように、メディアは Skype for Business クライアントと SBC またはゲートウェイの間で直接流れます。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-121">In the next topology—which does employ media bypass—signaling takes the same path, but media flows directly between the Skype for Business client and the SBC or gateway, as shown in the following diagram:</span></span>
  
<span data-ttu-id="c8e1e-122">**メディア バイパスを使用したメディアとシグナリングの経路**</span><span class="sxs-lookup"><span data-stu-id="c8e1e-122">**Media and signaling pathways with media bypass**</span></span>

![メディア バイパスを使用したシグナリング](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a><span data-ttu-id="c8e1e-124">マルチサイト シナリオとメディア バイパス</span><span class="sxs-lookup"><span data-stu-id="c8e1e-124">Multi-site scenario and media bypass</span></span>

<span data-ttu-id="c8e1e-125">メディア バイパスは、単一のクラウド コネクタ アプライアンスを使用して複数のサイトにテレフォニー サービスを提供する場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-125">Media bypass is also useful when you want to provide telephony services to multiple sites using a single Cloud Connector appliance.</span></span> <span data-ttu-id="c8e1e-126">クラウド コネクタは送信元番号または宛先番号に基づいて通話をルーティングできないので、ほとんどの企業は、ルーティングの決定を行うクラウド コネクタの背後に SBC またはゲートウェイを展開します。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-126">Because Cloud Connector cannot route calls based on source or destination numbers, most enterprises deploy an SBC or gateway behind Cloud Connector to make routing decisions.</span></span> <span data-ttu-id="c8e1e-127">このシナリオのメディア バイパスでは、次の図に示すように、クライアントと中央 SBC またはゲートウェイの間のホップが排除されます。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-127">Media bypass in this scenario eliminates the hop between the client and the central SBC or gateway, as shown in the following diagram:</span></span>
  
<span data-ttu-id="c8e1e-128">**マルチサイト アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="c8e1e-128">**Multi-site application**</span></span>

![クラウド コネクタマルチサイトの例](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. <span data-ttu-id="c8e1e-130">SIP トラフィックは、チューリッヒのユーザーから Microsoft 365 または Office 365 に流れます。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-130">The SIP traffic flows from the user in Zurich to Microsoft 365 or Office 365.</span></span>
    
2. <span data-ttu-id="c8e1e-131">その後、トラフィックは、ユーザー音声ルーティング ポリシーで指定されているアムステルダムのクラウド コネクタ アプライアンスにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-131">The traffic then routes to the Cloud Connector appliance in Amsterdam as specified in the user voice routing policy.</span></span>
    
3. <span data-ttu-id="c8e1e-132">アムステルダムのクラウド コネクタ アプライアンスは、SIP トラフィックをアムステルダムの中央ゲートウェイに送信します。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-132">The Cloud Connector appliance in Amsterdam sends the SIP traffic to the central gateway in Amsterdam.</span></span>
    
4. <span data-ttu-id="c8e1e-133">アムステルダムの中央ゲートウェイは適切なルーティング決定を行い、トラフィックをチューリッヒの SBC またはゲートウェイに送信しますが、メディアは Skype for Business クライアントとアムステルダムの SBC またはゲートウェイの間で直接流れます。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-133">The central gateway in Amsterdam makes the appropriate routing decisions, and then sends the traffic to an SBC or gateway in Zurich, while media flows directly between the Skype for Business client and SBC or gateway in Amsterdam.</span></span>
    
   <span data-ttu-id="c8e1e-134">この方法では、クラウド コネクタが集中管理されている 1 つのクラウド コネクタ展開ごとに、より多くのユーザーにサービスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-134">This approach allows serving more users per one Cloud Connector deployment where Cloud Connector is centralized.</span></span> <span data-ttu-id="c8e1e-135">クラウド コネクタはメディア パスから削除された場合でも、集中型マルチサイト シナリオ メディアでは、集中管理された SBC またはゲートウェイを通過するために必要な 2 倍の WAN を通過する場合があります。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-135">Even though Cloud Connector is eliminated from the media path, in a centralized multi-site scenario media may still traverse the WAN twice as required to flow through the centralized SBC or gateway.</span></span>
  
<span data-ttu-id="c8e1e-136">クライアントが企業ネットワーク外に発信通話を発信している場合、次の図に示すように、メディア トラフィックは、チューリッヒとアムステルダムの間のクラウド コネクタと WAN リンクのエッジ サーバーと仲介サーバーを介して流れます。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-136">If a client is outside the corporate network placing an outbound call, the media traffic flows via the Edge and Mediation servers of Cloud Connector and WAN link between Zurich and Amsterdam, as shown in the following diagram:</span></span>
  
![クラウド コネクタマルチサイトの例 2](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a><span data-ttu-id="c8e1e-138">メディア バイパスでサポートされるクライアント</span><span class="sxs-lookup"><span data-stu-id="c8e1e-138">Supported clients for media bypass</span></span>

<span data-ttu-id="c8e1e-139">メディア バイパスの最初のリリースでは、サポートされているクライアントは、Microsoft 365 Apps for enterprise バージョン 16.0.7870.2020 以上の Skype for Business 2016 Windows クライアントのみです。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-139">With the first release of media bypass, the only supported client is the Skype for Business 2016 Windows Client that is part of Microsoft 365 Apps for enterprise, version 16.0.7870.2020 or greater.</span></span> <span data-ttu-id="c8e1e-140">お客様は、現在のチャネル、遅延チャネル、初回リリース延期チャネルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-140">Customers can use any channel: Current, Deferred, or First Release Deferred.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c8e1e-141">Skype for Business クライアントと組み合わせてクライアント VPN ソリューションを使用している場合、メディア バイパスは VPN スプリット トンネル構成でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-141">If you are using a client VPN solution in combination with the Skype for Business client, then media bypass is supported only with a VPN split-tunnel configuration.</span></span> 
  
<span data-ttu-id="c8e1e-142">リリース チャネルの詳細については、「Microsoft 365 Apps for enterprise の更新プログラム チャネル [の概要」を参照してください](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-142">For more information about the release channels, see [Overview of update channels for Microsoft 365 Apps for enterprise](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
<span data-ttu-id="c8e1e-143">異なるチャネルのクライアントの現在のリリース バージョンについては、「エンタープライズ向け [Microsoft 365 Apps](/officeupdates/release-notes-office365-proplus)の更新プログラムのリリース情報」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-143">For the current release version of the clients in different channels, see [Release information for updates to Microsoft 365 Apps for enterprise](/officeupdates/release-notes-office365-proplus).</span></span> 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a><span data-ttu-id="c8e1e-144">メディア バイパスを使用したクラウド コネクタの容量に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="c8e1e-144">Cloud Connector capacity considerations with media bypass</span></span>

<span data-ttu-id="c8e1e-145">メディア バイパスなしで、ハードウェアに応じて、クラウド コネクタ アプライアンスは、仲介サーバーを経由するメディアを必要とする 50 ~ 500 の同時呼び出しを処理できます。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-145">Without media bypass—and depending on the hardware—a Cloud Connector appliance can handle from 50 to 500 simultaneous calls that require media to travel through a Mediation Server.</span></span> <span data-ttu-id="c8e1e-146">詳細については [、「Plan for Skype for Business Cloud Connector Edition」を参照してください](./plan-skype-for-business-cloud-connector-edition.md)。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-146">For more information, see [Plan for Skype for Business Cloud Connector Edition](./plan-skype-for-business-cloud-connector-edition.md).</span></span> 
  
<span data-ttu-id="c8e1e-147">メディア バイパスを有効にすると、サポートされているバージョンの内部クライアントは仲介サーバーを使用しないので、内部クライアントの数が大幅に増加する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-147">With media bypass enabled, internal clients on the supported version do not use the Mediation Server, so the number of internal clients can increase significantly.</span></span> 
  
<span data-ttu-id="c8e1e-148">上記のように、外部クライアントまたはサポートされていないクライアントは、メディアにクラウド コネクタ エッジサーバーと仲介サーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-148">As noted above, external clients or unsupported clients will use the Cloud Connector Edge and Mediation servers for media.</span></span> <span data-ttu-id="c8e1e-149">サイトに配置するクラウド コネクタ アプライアンスの数を計算する場合は、サポートされていないクライアント上の外部ユーザーとユーザーからのトラフィックを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-149">When calculating how many Cloud Connector appliances should be placed in a site, you must consider traffic from external users and users on unsupported clients.</span></span>
  
## <a name="cloud-connector-supports-always-bypass-mode"></a><span data-ttu-id="c8e1e-150">クラウド コネクタは常にバイパス モードをサポートしています</span><span class="sxs-lookup"><span data-stu-id="c8e1e-150">Cloud Connector supports Always Bypass mode</span></span>

<span data-ttu-id="c8e1e-151">クラウド コネクタは、常にバイパス モードのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-151">Cloud Connector supports Always Bypass mode only.</span></span> <span data-ttu-id="c8e1e-152">オンプレミス環境では、[常にバイパスする] と [サイトと地域情報を使用する] の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-152">In on-premises environments, there are two options: Always Bypass and Use Site and Region Information.</span></span>
  
<span data-ttu-id="c8e1e-153">Always Bypass は、内部クライアントを発信元または宛先ポイントとしてすべての PSTN 呼び出しに対してメディア バイパスが試行されるという意味です。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-153">Always Bypass means that media bypass will be attempted for all PSTN calls with internal clients as an origin or destination point.</span></span> <span data-ttu-id="c8e1e-154">クライアントが内部または外部かどうかを判断するために、仲介サーバー仮想マシン上の Web サイトが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-154">To determine if the client is internal or external, a web site on the mediation server virtual machine is used.</span></span> <span data-ttu-id="c8e1e-155">クライアントがサイトに到達できる場合は、内部と見なされ、メディア バイパスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-155">If the client can reach the site, it is considered internal and media bypass is used.</span></span> <span data-ttu-id="c8e1e-156">クライアントがサイトに到達できない場合 (たとえば、クライアントがホーム ネットワーク上にあります)、メディア バイパスは使用されません。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-156">If the client cannot reach the site (for example the client is on a home network), media bypass is not used.</span></span> 
  
<span data-ttu-id="c8e1e-157">Always Bypass には、PSTN サイト内のユーザーと PSTN ゲートウェイ間のブロックされていない接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-157">Always Bypass requires unobstructed connectivity between users and the PSTN gateways within a PSTN Site.</span></span> 
  
<span data-ttu-id="c8e1e-158">詳細については [、「Plan for Skype for Business Cloud Connector Edition」を参照してください](./plan-skype-for-business-cloud-connector-edition.md)。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-158">For more information, see [Plan for Skype for Business Cloud Connector Edition](./plan-skype-for-business-cloud-connector-edition.md).</span></span> 
  
<span data-ttu-id="c8e1e-159">たとえば、下の図では、ヨーロッパのユーザーはアムステルダムの 3 つのセッション ボーダー コントローラー (SPC) に十分に接続されている必要があります。米国西部のユーザーはシアトルの 2 つの SPC に十分に接続されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-159">For example, in the diagram below, Europe users must be well connected to the three Session Border Controllers (SBCs) in Amsterdam while US West users must be well connected to the two SBCs in Seattle.</span></span> <span data-ttu-id="c8e1e-160">適切に接続されているということは、SPC またはゲートウェイと同じネットワーク サイトに、または適切な帯域幅を持つ WAN リンク上に位置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-160">Well connected means that they are either located in the same network sites as the SBCs or gateways, or over WAN links that have proper bandwidth.</span></span>
  
![クラウド コネクタの容量](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> <span data-ttu-id="c8e1e-162">チューリッヒのユーザーがシアトルオフィスに移動し、内部ネットワークを使用して(インターネットを越えるのではなく)ヨーロッパの旅行ユーザーとゲートウェイ間のメディア トラフィックを配信する場合は、シアトルのオフィスと、ヨーロッパの SPC またはゲートウェイが存在するアムステルダムオフィスが同様に接続されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-162">If a user from Zurich travels to the Seattle office, and you want to use the internal network to deliver media traffic between the traveling user and gateways in Europe (as opposed to going over the Internet), then you must make sure the Seattle office and the Amsterdam office where European SBCs or gateways are located qualify as well connected.</span></span> 
  
## <a name="codecs-used-in-media-bypass"></a><span data-ttu-id="c8e1e-163">メディア バイパスで使用されるコーデック</span><span class="sxs-lookup"><span data-stu-id="c8e1e-163">Codecs used in media bypass</span></span>

<span data-ttu-id="c8e1e-164">メディア バイパスを有効にすると、クライアントと SBC またはゲートウェイ間のメディア トラフィックは G.711 コーデックを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8e1e-164">With media bypass enabled, media traffic between a client and an SBC or gateway uses the G.711 codec.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c8e1e-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8e1e-165">See also</span></span>

[<span data-ttu-id="c8e1e-166">Cloud Connector Edition でのメディア バイパスの展開</span><span class="sxs-lookup"><span data-stu-id="c8e1e-166">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md)