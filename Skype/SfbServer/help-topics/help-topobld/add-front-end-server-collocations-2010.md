---
title: フロント エンド サーバー Collocations 2010 を追加します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Enterprise Edition 展開では、どちらか A に集約できます V 会議サービス、仲介サーバー、またはフロント エンド プール、または両方を展開できますスタンドアロン サーバーとして各とします。 Standard Edition サーバーの展開、A V 会議サービスは、常に同じ場所に会議が有効になっている場合とします。
ms.openlocfilehash: f8a1abf168447af7f45ed8f222ef80f029aff2bc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-server-collocations-2010"></a><span data-ttu-id="a3df0-104">フロント エンド サーバー Collocations 2010 を追加します。</span><span class="sxs-lookup"><span data-stu-id="a3df0-104">Add Front End Server Collocations 2010</span></span>
 
<span data-ttu-id="a3df0-105">Enterprise Edition 展開では、どちらか A に集約できます V 会議サービス、仲介サーバー、またはフロント エンド プール、または両方を展開できますスタンドアロン サーバーとして各とします。</span><span class="sxs-lookup"><span data-stu-id="a3df0-105">For an Enterprise Edition deployment, you can collocate either the A/V Conferencing service, the Mediation Server, or both on the Front End pool, or you can deploy each as stand-alone servers.</span></span> <span data-ttu-id="a3df0-106">Standard Edition サーバーの展開、A V 会議サービスは、常に同じ場所に会議が有効になっている場合とします。</span><span class="sxs-lookup"><span data-stu-id="a3df0-106">For a Standard Edition server deployment, the A/V Conferencing service is always collocated if conferencing is enabled.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a3df0-107">A/V 会議サービスは、**会議**は、**機能の選択**] ページで選択した場合必要です。</span><span class="sxs-lookup"><span data-stu-id="a3df0-107">An A/V Conferencing service is required if **Conferencing** was selected on the **Select features** page.</span></span> <span data-ttu-id="a3df0-108">エンタープライズ エディションのフロント エンド プールを使用して、配置されている可能性があります A/V 会議サービスまたはスタンドアロンの A/V 会議のプールです。</span><span class="sxs-lookup"><span data-stu-id="a3df0-108">An Enterprise Edition Front End pool may use a collocated A/V Conferencing service or a stand-alone A/V conferencing pool.</span></span> <span data-ttu-id="a3df0-109">会議がなかった場合は、選択すると、Collocate A/V 会議サービスを使用可能にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a3df0-109">If Conferencing was not selected, the Collocate A/V Conferencing service will not be available.</span></span>
  
<span data-ttu-id="a3df0-110">標準エディションのフロント エンド サーバーまたはエンタープライズ エディションのフロント エンド プールに仲介サーバーの役割に集約できます。</span><span class="sxs-lookup"><span data-stu-id="a3df0-110">You can collocate the Mediation Server role on a Standard Edition Front End Server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="a3df0-111">メディア バイ パスとドメイン ネーム システム (DNS) 負荷分散をサポートする修飾の公衆交換電話網 (PSTN) ゲートウェイに直接 SIP 接続を展開する場合、スタンドアロンの仲介サーバー プールは必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="a3df0-111">If you deploy Direct SIP connections to a qualified public switched telephone network (PSTN) gateway that supports media bypass and Domain Name System (DNS) load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="a3df0-112">修飾のゲートウェイは、仲介サーバーのプールに DNS のロードバランシングに対応し、プール内のすべての仲介サーバーからのトラフィックを受信できるため、スタンドアロンの仲介サーバー プールは必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="a3df0-112">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span> <span data-ttu-id="a3df0-113">まとめてフロント エンド プールに仲介サーバー IP Pbx を展開しているか、接続、インターネット テレフォニー サービス プロバイダーのセッション ボーダー コント ローラー (SBC) に次の条件のいずれかを満たしている限り、またお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a3df0-113">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider's Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>
  
- <span data-ttu-id="a3df0-114">IP PBX、または SBC、プール内のすべての仲介サーバーからのトラフィックを受信するように構成し、プール内のすべての仲介サーバーに均等にトラフィックをルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="a3df0-114">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>
    
- <span data-ttu-id="a3df0-115">IP PBX、または SBC、プール内のすべての仲介サーバーからのトラフィックを受信するように構成し、プール内のすべての仲介サーバーに均等にトラフィックをルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="a3df0-115">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>
    
<span data-ttu-id="a3df0-116">Microsoft Lync Server 2013 フロント エンド プール、仲介サーバーを連結するが、負荷を処理できるかどうかを評価するために、計画ツールを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a3df0-116">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="a3df0-117">お客様の環境では、これら要件を満たすことはできません、する場合は、スタンドアロン仲介サーバー プールを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3df0-117">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>
  
<span data-ttu-id="a3df0-118">A の全般的なコロケーションに/V 会議サーバーまたは仲介サーバー組織が高可用性とスケーラビリティ要件の詳細、Enterprise Edition フロント エンド プールでこれらのサーバー ロールを配置している場合を推奨されていません展開、展開に関するドキュメントの[定義およびフロント エンド プールを構成する](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3df0-118">In general, collocation of A/V Conferencing Server or Mediation Server is not recommended if your organization has high availability and scalability requirementsFor details about collocating these server roles in a Front End pool in an Enterprise Edition deployment, see [Define and Configure a Front End Pool](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="a3df0-119">詳細については、A の V 会議の機能およびコンポーネントは、計画のドキュメントで[の会議を計画する](http://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)を参照するくださいとします。</span><span class="sxs-lookup"><span data-stu-id="a3df0-119">For details about the A/V Conferencing feature and components, see [Planning for Conferencing](http://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in the Planning documentation.</span></span> <span data-ttu-id="a3df0-120">エンタープライズ VoIP 機能と、仲介サーバーを含め、コンポーネントの詳細についてを参照してください[ビジネス サーバー 2015 の Skype でエンタープライズ VoIP の計画](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)計画マニュアルを参照します。</span><span class="sxs-lookup"><span data-stu-id="a3df0-120">For details about Enterprise Voice features and components, including Mediation Server, see [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in the Planning documentation.</span></span>
  

