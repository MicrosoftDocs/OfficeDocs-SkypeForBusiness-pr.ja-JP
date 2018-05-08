---
title: Skype for Business Server 2015 での PSTN 接続コンポーネント
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: ビジネス サーバーの Skype でエンタープライズ VoIP の SIP トランキングと PSTN ゲートウェイについて説明します。
ms.openlocfilehash: 4f346209b483a3d469beba233bd22ee39e45745a
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="pstn-connectivity-components-in-skype-for-business-server-2015"></a><span data-ttu-id="e0fde-103">Skype for Business Server 2015 での PSTN 接続コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e0fde-103">PSTN connectivity components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e0fde-104">ビジネス サーバーの Skype でエンタープライズ VoIP の SIP トランキングと PSTN ゲートウェイについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e0fde-104">Learn about SIP trunking and PSTN gateways for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="e0fde-105">エンタープライズ レベルの VoIP ソリューションでは、サービスの品質 (QoS) を低下させずに公衆交換電話網 (PSTN) との通話の発信および着信を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0fde-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="e0fde-106">また、通話の発信時および着信時に、基礎となるテクノロジをユーザーが意識しなくても済むようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0fde-106">In addition, users should not be aware of the underlying technology when they place and receive calls.</span></span> <span data-ttu-id="e0fde-107">ユーザーの観点から、エンタープライズ VoIP インフラストラクチャと PSTN との間の呼び出しする必要がありますように 1 つの SIP セッション。</span><span class="sxs-lookup"><span data-stu-id="e0fde-107">From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>
  
<span data-ttu-id="e0fde-108">PSTN 接続を行うには、(PBX (直接 SIP リンク) を使用して、または PBX を使用せずに) SIP トランクまたは PSTN ゲートウェイを展開します。</span><span class="sxs-lookup"><span data-stu-id="e0fde-108">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>
  
## <a name="sip-trunking"></a><span data-ttu-id="e0fde-109">SIP トランキング</span><span class="sxs-lookup"><span data-stu-id="e0fde-109">SIP Trunking</span></span>

<span data-ttu-id="e0fde-110">PSTN ゲートウェイを使用する代わりに、エンタープライズ VoIP ソリューションを PSTN に SIP トランクを使用して接続できます。</span><span class="sxs-lookup"><span data-stu-id="e0fde-110">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking.</span></span> <span data-ttu-id="e0fde-111">SIP トランキングを使用すると、次のようなシナリオが実現します。</span><span class="sxs-lookup"><span data-stu-id="e0fde-111">SIP trunking enables the following scenarios:</span></span>
  
- <span data-ttu-id="e0fde-112">企業のファイアウォールの内側または外側にいるエンタープライズ ユーザーが、E.164 準拠の番号で指定される市内通話や長距離通話を発信できます。この通話は、対応するサービス プロバイダーのサービスとして PSTN 上で終端されます。</span><span class="sxs-lookup"><span data-stu-id="e0fde-112">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>
    
- <span data-ttu-id="e0fde-113">PSTN サブスクライバーはだれでも、エンタープライズ ユーザーに関連付けられた Direct Inward Dialing (DID) 番号をダイヤルして、企業のファイアウォールの内側または外側にいるエンタープライズ ユーザーに連絡することができます。</span><span class="sxs-lookup"><span data-stu-id="e0fde-113">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>
    
<span data-ttu-id="e0fde-114">この展開ソリューションを使用するには、SIP トランキング サービス プロバイダーが必要です。</span><span class="sxs-lookup"><span data-stu-id="e0fde-114">The use of this deployment solution requires a SIP trunking service provider.</span></span> 
  
## <a name="pstn-gateways"></a><span data-ttu-id="e0fde-115">PSTN ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="e0fde-115">PSTN gateways</span></span>

<span data-ttu-id="e0fde-116">PSTN ゲートウェイとは、信号に変換するサードパーティ製のデバイスとエンタープライズ VoIP インフラストラクチャと、PSTN または PBX の間でのメディアです。</span><span class="sxs-lookup"><span data-stu-id="e0fde-116">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="e0fde-117">PSTN ゲートウェイは、PSTN または PBX、エンタープライズ VoIP クライアント呼び出しを表示する仲介サーバーと連携します。</span><span class="sxs-lookup"><span data-stu-id="e0fde-117">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="e0fde-118">仲介サーバーは、エンタープライズ VoIP クライアントからゲートウェイへの通話、PSTN PSTN または PBX にルーティングするためにも説明します。</span><span class="sxs-lookup"><span data-stu-id="e0fde-118">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="e0fde-119">ビジネス サーバーの Skype 上で動作するデバイスを提供する Microsoft と協力しているパートナーの一覧は、[マイクロソフトのユニファイド コミュニケーション パートナーの web サイト](https://go.microsoft.com/fwlink/p/?linkId=202836)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0fde-119">For a list of partners who work with Microsoft to provide devices that work with Skype for Business Server, see  [the Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span> 
  
## <a name="private-branch-exchanges"></a><span data-ttu-id="e0fde-120">構内交換機</span><span class="sxs-lookup"><span data-stu-id="e0fde-120">Private Branch Exchanges</span></span>

 <span data-ttu-id="e0fde-121">構内交換機 (PBX) を使用する既存の音声インフラストラクチャがある場合は、エンタープライズ VoIP を PBX を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e0fde-121">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Enterprise Voice.</span></span>
  
<span data-ttu-id="e0fde-122">サポートされているエンタープライズ VoIP を PBX 統合のシナリオは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e0fde-122">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>
  
- <span data-ttu-id="e0fde-123">メディアをサポートしている IP-PBX は、仲介サーバーをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="e0fde-123">IP-PBX that supports media bypass, with a Mediation Server.</span></span>
    
- <span data-ttu-id="e0fde-124">スタンドアロンの PSTN ゲートウェイが必要な IP-PBX。</span><span class="sxs-lookup"><span data-stu-id="e0fde-124">IP-PBX that requires a stand-alone PSTN gateway.</span></span>
    
- <span data-ttu-id="e0fde-125">時分割多重 (TDM) PBX とスタンドアロンの PSTN ゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="e0fde-125">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e0fde-126">メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="e0fde-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="e0fde-127">Microsoft は、認定パートナーと共に一連の PSTN ゲートウェイおよび SBC をテストし、Cisco IP-PBX についてもいくつかのテストを完了しています。</span><span class="sxs-lookup"><span data-stu-id="e0fde-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="e0fde-128">メディアのバイパスが製品でのみサポートされているし、バージョンに記載されている[ユニファイド コミュニケーション オープン相互運用性プログラムの Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406)です。</span><span class="sxs-lookup"><span data-stu-id="e0fde-128">Media bypass is supported only with products and versions listed at [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span></span> 
  
<span data-ttu-id="e0fde-129">詳細については、エンタープライズ VoIP ソリューションを提供するパートナーは、[マイクロソフトのユニファイド コミュニケーション パートナーの web サイト](https://go.microsoft.com/fwlink/p/?linkId=202836)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0fde-129">For details about partners who offer Enterprise Voice solutions, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  
<span data-ttu-id="e0fde-130">PSTN ゲートウェイを含め、エンタープライズ VoIP のハードウェア ソリューションを提供するパートナーの詳細については、[マイクロソフトのユニファイド コミュニケーション パートナーの web サイト](https://go.microsoft.com/fwlink/p/?linkId=202836)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0fde-130">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  

