---
title: フロントエンド サーバーの併置の追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
description: Enterprise Edition の展開の場合、A/V 会議サービスはフロントエンドプールに併置されています。 また、フロントエンドプールで仲介サーバーを検索することも、スタンドアロンサーバーとして展開することもできます。 会議が有効になっている場合、A/V 会議サービスは常に併置されます。
ms.openlocfilehash: 0f6b3307d73f87af10140ecf594f8e662cfdd369
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820829"
---
# <a name="add-front-end-server-collocations"></a><span data-ttu-id="ab483-105">フロントエンド サーバーの併置の追加</span><span class="sxs-lookup"><span data-stu-id="ab483-105">Add Front End Server Collocations</span></span>

<span data-ttu-id="ab483-106">Enterprise Edition の展開の場合、A/V 会議サービスはフロントエンドプールに併置されています。</span><span class="sxs-lookup"><span data-stu-id="ab483-106">For an Enterprise Edition deployment, the A/V Conferencing service is collocated on the Front End pool.</span></span> <span data-ttu-id="ab483-107">また、フロントエンドプールで仲介サーバーを検索することも、スタンドアロンサーバーとして展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="ab483-107">You can also collocate the Mediation Server on the Front End pool, or you can deploy it as a stand-alone server.</span></span> <span data-ttu-id="ab483-108">会議が有効になっている場合、A/V 会議サービスは常に併置されます。</span><span class="sxs-lookup"><span data-stu-id="ab483-108">The A/V Conferencing service is always collocated if conferencing is enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="ab483-109">**[機能の選択**] ページで**会議**が選択されている場合は、A/V 会議サービスが必要です。</span><span class="sxs-lookup"><span data-stu-id="ab483-109">An A/V Conferencing service is required if **Conferencing** was selected on the **Select features** page.</span></span> <span data-ttu-id="ab483-110">Enterprise Edition のフロントエンドプールでは、併置された A/V 会議サービスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ab483-110">An Enterprise Edition Front End pool uses a collocated A/V Conferencing service.</span></span> <span data-ttu-id="ab483-111">会議が選択されていない場合は、A/V 会議サービスの Collocate は利用できません。</span><span class="sxs-lookup"><span data-stu-id="ab483-111">If Conferencing was not selected, the Collocate A/V Conferencing service will not be available.</span></span>

<span data-ttu-id="ab483-112">この仲介サーバーの役割は、Standard Edition のフロントエンドサーバーまたは Enterprise Edition のフロントエンドプールで検索できます。</span><span class="sxs-lookup"><span data-stu-id="ab483-112">You can collocate the Mediation Server role on a Standard Edition Front End Server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="ab483-113">メディアバイパスとドメインネームシステム (DNS) 負荷分散をサポートする、限定された公衆交換電話網 (PSTN) ゲートウェイに直接 SIP 接続を展開する場合、スタンドアロンの仲介サーバープールは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ab483-113">If you deploy Direct SIP connections to a qualified public switched telephone network (PSTN) gateway that supports media bypass and Domain Name System (DNS) load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="ab483-114">認定ゲートウェイは、仲介サーバーのプールに対する DNS 負荷分散をサポートし、プール内の任意の仲介サーバーからトラフィックを受信できるため、スタンドアロンの仲介サーバープールは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ab483-114">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span> <span data-ttu-id="ab483-115">また、次の条件のいずれかが満たされている限り、IP Pbx を展開した場合、またはインターネットテレフォニーサーバープロバイダーのセッションボーダーコントローラー (SBC) に接続している場合は、仲介サーバーをフロントエンドプールで検索することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ab483-115">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider's Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

- <span data-ttu-id="ab483-116">IP PBX または SBC は、プール内の任意の仲介サーバーからトラフィックを受信し、プール内のすべての仲介サーバーに一律にトラフィックをルーティングできるように構成されています。</span><span class="sxs-lookup"><span data-stu-id="ab483-116">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

- <span data-ttu-id="ab483-117">IP PBX または SBC は、プール内の任意の仲介サーバーからトラフィックを受信し、プール内のすべての仲介サーバーに一律にトラフィックをルーティングできるように構成されています。</span><span class="sxs-lookup"><span data-stu-id="ab483-117">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

<span data-ttu-id="ab483-118">Microsoft Lync Server 2013 の計画ツールを使用すると、仲介サーバーを配置するフロントエンドプールが負荷を処理できるかどうかを評価することができます。</span><span class="sxs-lookup"><span data-stu-id="ab483-118">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="ab483-119">環境がこれらの要件を満たしていない場合は、スタンドアロンの仲介サーバープールを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab483-119">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="ab483-120">一般に、組織に高可用性とスケーラビリティの要件がある場合は、仲介サーバーの collocation はお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="ab483-120">In general, collocation of Mediation Server is not recommended if your organization has high availability and scalability requirements.</span></span> <span data-ttu-id="ab483-121">Enterprise Edition の展開で、フロントエンドプールでこれらのサーバーの役割を特定する方法について詳しくは、「展開ドキュメントで[フロントエンドプールを定義して構成](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ab483-121">For details about collocating these server roles in a Front End pool in an Enterprise Edition deployment, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="ab483-122">A/V 会議機能とコンポーネントの詳細については、計画ドキュメントの「[会議の計画](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab483-122">For details about the A/V Conferencing feature and components, see [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in the Planning documentation.</span></span> <span data-ttu-id="ab483-123">仲介サーバーなどのエンタープライズ Voip 機能とコンポーネントの詳細については、計画ドキュメントの「 [Skype For Business Server 2015 でのエンタープライズ voip の計画](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab483-123">For details about Enterprise Voice features and components, including Mediation Server, see [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in the Planning documentation.</span></span>


