---
title: フロントエンド サーバーの併置を追加する (2010)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Enterprise Edition 展開の場合は、音声ビデオ会議サービス、仲介サーバー、またはその両方をフロント エンド プールに併置するか、またはそれぞれをスタンドアロン サーバーとして展開できます。Standard Edition サーバー展開の場合は、会議が有効であれば、常に音声ビデオ会議サービスが併置されます。
ms.openlocfilehash: 86bef8bdcbdd36033e64912bdce2d9ea3469e45c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216518"
---
# <a name="add-front-end-server-collocations-2010"></a><span data-ttu-id="b684a-104">フロントエンド サーバーの併置を追加する (2010)</span><span class="sxs-lookup"><span data-stu-id="b684a-104">Add Front End Server Collocations 2010</span></span>

<span data-ttu-id="b684a-p102">Enterprise Edition 展開の場合は、音声ビデオ会議サービス、仲介サーバー、またはその両方をフロント エンド プールに併置するか、またはそれぞれをスタンドアロン サーバーとして展開できます。Standard Edition サーバー展開の場合は、会議が有効であれば、常に音声ビデオ会議サービスが併置されます。</span><span class="sxs-lookup"><span data-stu-id="b684a-p102">For an Enterprise Edition deployment, you can collocate either the A/V Conferencing service, the Mediation Server, or both on the Front End pool, or you can deploy each as stand-alone servers. For a Standard Edition server deployment, the A/V Conferencing service is always collocated if conferencing is enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="b684a-p103">[**機能の選択**] ページで [**電話会議**] を選択した場合には、音声ビデオ会議サービスが必要です。Enterprise Edition フロント エンド プールでは、併置された音声ビデオ会議サービスまたはスタンドアロン音声ビデオ会議プールを使用できます。[電話会議] を選択しなかった場合、[音声ビデオ会議サービスを併置する] は使用できません。</span><span class="sxs-lookup"><span data-stu-id="b684a-p103">An A/V Conferencing service is required if **Conferencing** was selected on the **Select features** page. An Enterprise Edition Front End pool may use a collocated A/V Conferencing service or a stand-alone A/V conferencing pool. If Conferencing was not selected, the Collocate A/V Conferencing service will not be available.</span></span>

<span data-ttu-id="b684a-110">Standard Edition フロントエンド サーバーまたは Enterprise Edition フロントエンド プールに仲介サーバーの役割を併置できます。</span><span class="sxs-lookup"><span data-stu-id="b684a-110">You can collocate the Mediation Server role on a Standard Edition Front End Server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="b684a-111">メディア バイパスとドメイン ネーム システム (DNS) 負荷分散をサポートする認定公衆交換電話網 (PSTN) ゲートウェイへ直接 SIP 接続を展開する場合、スタンドアロンの仲介サーバー プールは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b684a-111">If you deploy Direct SIP connections to a qualified public switched telephone network (PSTN) gateway that supports media bypass and Domain Name System (DNS) load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="b684a-112">スタンドアロンの仲介サーバー プールが必要でないのは、認定ゲートウェイが仲介サーバーのプールへの DNS 負荷分散に対応しており、プール内のすべての仲介サーバーからトラフィックを受信できるからです。</span><span class="sxs-lookup"><span data-stu-id="b684a-112">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span> <span data-ttu-id="b684a-113">また、次のいずれかの条件が満たされている場合は、IP-PBX をフロントエンドプールに併置するか、またはインターネットテレフォニーサーバープロバイダーのセッションボーダーコントローラー (SBC) に接続しているときに、仲介サーバーをフロントエンドプールに併置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b684a-113">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider's Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

- <span data-ttu-id="b684a-114">IP-PBX または SBC は、プール内の任意の仲介サーバーからのトラフィックを受信するように構成されており、プール内のすべての仲介サーバーにトラフィックを均等にルーティングできる。</span><span class="sxs-lookup"><span data-stu-id="b684a-114">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

- <span data-ttu-id="b684a-115">IP-PBX または SBC は、プール内の任意の仲介サーバーからのトラフィックを受信するように構成されており、プール内のすべての仲介サーバーにトラフィックを均等にルーティングできる。</span><span class="sxs-lookup"><span data-stu-id="b684a-115">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

<span data-ttu-id="b684a-116">Microsoft Lync Server 2013、計画ツールを使用して、仲介サーバーを併置するフロントエンドプールが負荷を処理できるかどうかを評価できます。</span><span class="sxs-lookup"><span data-stu-id="b684a-116">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="b684a-117">これらの要件に適合しない環境では、スタンドアロン仲介サーバー プールを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b684a-117">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="b684a-118">一般に、組織が高可用性とスケーラビリティを備えている場合、requirementsFor/V 会議サーバーまたは仲介サーバーの併置は推奨されません。これらのサーバーの役割を Enterprise Edition 展開のフロントエンドプールに配置する詳細については、「展開」のドキュメントの「 [Define And Configure A Front End pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b684a-118">In general, collocation of A/V Conferencing Server or Mediation Server is not recommended if your organization has high availability and scalability requirementsFor details about collocating these server roles in a Front End pool in an Enterprise Edition deployment, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="b684a-119">音声ビデオ会議の機能とコンポーネントの詳細については、「計画」のドキュメントの「[Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b684a-119">For details about the A/V Conferencing feature and components, see [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in the Planning documentation.</span></span> <span data-ttu-id="b684a-120">仲介サーバーを含むエンタープライズ Voip の機能とコンポーネントの詳細については、「計画」のドキュメントの「 [Plan For Enterprise voice In Skype For Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b684a-120">For details about Enterprise Voice features and components, including Mediation Server, see [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in the Planning documentation.</span></span>


