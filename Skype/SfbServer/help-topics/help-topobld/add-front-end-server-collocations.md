---
title: フロントエンド サーバーの併置の追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
description: Enterprise Edition 展開の場合、A V 会議サービスがフロント エンド プールに併設されているとします。 また、フロント エンド プールに仲介サーバーに集約できます。 またはスタンドアロン サーバーとして展開することができます。 A V 会議サービスは、常に同じ場所に会議が有効になっている場合とします。
ms.openlocfilehash: 3b5929b27d5a6de7dcc8f5f128da649577ddc810
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903818"
---
# <a name="add-front-end-server-collocations"></a><span data-ttu-id="b0d69-105">フロントエンド サーバーの併置の追加</span><span class="sxs-lookup"><span data-stu-id="b0d69-105">Add Front End Server Collocations</span></span>

<span data-ttu-id="b0d69-106">Enterprise Edition 展開の場合、A V 会議サービスがフロント エンド プールに併設されているとします。</span><span class="sxs-lookup"><span data-stu-id="b0d69-106">For an Enterprise Edition deployment, the A/V Conferencing service is collocated on the Front End pool.</span></span> <span data-ttu-id="b0d69-107">また、フロント エンド プールに仲介サーバーに集約できます。 またはスタンドアロン サーバーとして展開することができます。</span><span class="sxs-lookup"><span data-stu-id="b0d69-107">You can also collocate the Mediation Server on the Front End pool, or you can deploy it as a stand-alone server.</span></span> <span data-ttu-id="b0d69-108">A V 会議サービスは、常に同じ場所に会議が有効になっている場合とします。</span><span class="sxs-lookup"><span data-stu-id="b0d69-108">The A/V Conferencing service is always collocated if conferencing is enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="b0d69-109">A/V 会議サービスは、**会議**は、**機能の選択**] ページで選択した場合必要です。</span><span class="sxs-lookup"><span data-stu-id="b0d69-109">An A/V Conferencing service is required if **Conferencing** was selected on the **Select features** page.</span></span> <span data-ttu-id="b0d69-110">エンタープライズ エディションのフロント エンド プールを使用して、配置されている A/V 会議サービスです。</span><span class="sxs-lookup"><span data-stu-id="b0d69-110">An Enterprise Edition Front End pool uses a collocated A/V Conferencing service.</span></span> <span data-ttu-id="b0d69-111">会議がなかった場合は、選択すると、Collocate A/V 会議サービスを使用可能にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b0d69-111">If Conferencing was not selected, the Collocate A/V Conferencing service will not be available.</span></span>

<span data-ttu-id="b0d69-112">標準エディションのフロント エンド サーバーまたはエンタープライズ エディションのフロント エンド プールに仲介サーバーの役割に集約できます。</span><span class="sxs-lookup"><span data-stu-id="b0d69-112">You can collocate the Mediation Server role on a Standard Edition Front End Server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="b0d69-113">メディア バイ パスとドメイン ネーム システム (DNS) 負荷分散をサポートする修飾の公衆交換電話網 (PSTN) ゲートウェイに直接 SIP 接続を展開する場合、スタンドアロンの仲介サーバー プールは必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="b0d69-113">If you deploy Direct SIP connections to a qualified public switched telephone network (PSTN) gateway that supports media bypass and Domain Name System (DNS) load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="b0d69-114">修飾のゲートウェイは、仲介サーバーのプールに DNS のロードバランシングに対応し、プール内のすべての仲介サーバーからのトラフィックを受信できるため、スタンドアロンの仲介サーバー プールは必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="b0d69-114">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span> <span data-ttu-id="b0d69-115">まとめてフロント エンド プールに仲介サーバー IP Pbx を展開しているか、接続、インターネット テレフォニー サービス プロバイダーのセッション ボーダー コント ローラー (SBC) に次の条件のいずれかを満たしている限り、またお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b0d69-115">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider's Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

- <span data-ttu-id="b0d69-116">IP PBX、または SBC、プール内のすべての仲介サーバーからのトラフィックを受信するように構成し、プール内のすべての仲介サーバーに均等にトラフィックをルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="b0d69-116">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

- <span data-ttu-id="b0d69-117">IP PBX、または SBC、プール内のすべての仲介サーバーからのトラフィックを受信するように構成し、プール内のすべての仲介サーバーに均等にトラフィックをルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="b0d69-117">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

<span data-ttu-id="b0d69-118">Microsoft Lync Server 2013 フロント エンド プール、仲介サーバーを連結するが、負荷を処理できるかどうかを評価するために、計画ツールを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b0d69-118">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="b0d69-119">お客様の環境では、これら要件を満たすことはできません、する場合は、スタンドアロン仲介サーバー プールを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0d69-119">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="b0d69-120">一般に、高い可用性とスケーラビリティの要件がある場合、仲介サーバーのコロケーションは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="b0d69-120">In general, collocation of Mediation Server is not recommended if your organization has high availability and scalability requirements.</span></span> <span data-ttu-id="b0d69-121">Enterprise Edition の展開でフロント エンド プール内のこれらのサーバー ロールの配置についての詳細は、展開に関するドキュメントの[定義およびフロント エンド プールを構成する](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0d69-121">For details about collocating these server roles in a Front End pool in an Enterprise Edition deployment, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="b0d69-122">詳細については、A の V 会議の機能およびコンポーネントは、計画のドキュメントで[の会議を計画する](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)を参照するくださいとします。</span><span class="sxs-lookup"><span data-stu-id="b0d69-122">For details about the A/V Conferencing feature and components, see [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in the Planning documentation.</span></span> <span data-ttu-id="b0d69-123">エンタープライズ VoIP 機能と、仲介サーバーを含め、コンポーネントの詳細についてを参照してください[ビジネス サーバー 2015 の Skype でエンタープライズ VoIP の計画](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)計画マニュアルを参照します。</span><span class="sxs-lookup"><span data-stu-id="b0d69-123">For details about Enterprise Voice features and components, including Mediation Server, see [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in the Planning documentation.</span></span>


