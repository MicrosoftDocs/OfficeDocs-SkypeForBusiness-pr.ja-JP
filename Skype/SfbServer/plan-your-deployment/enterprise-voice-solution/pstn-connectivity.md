---
title: Skype for Business Server の PSTN 接続コンポーネント
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Skype for Business Server の SIP トランキングと PSTN エンタープライズ VoIPについて説明します。
ms.openlocfilehash: 6261b95906699777e62c025889d23e03d381f09d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813537"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a><span data-ttu-id="0e5d6-103">Skype for Business Server の PSTN 接続コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0e5d6-103">PSTN connectivity components in Skype for Business Server</span></span>
 
<span data-ttu-id="0e5d6-104">Skype for Business Server の SIP トランキングと PSTN エンタープライズ VoIPについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0e5d6-104">Learn about SIP trunking and PSTN gateways for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="0e5d6-p101">エンタープライズ レベルの VoIP ソリューションでは、サービスの品質 (QoS) を低下させずに公衆交換電話網 (PSTN) との通話の発信および着信を処理する必要があります。また、通話の発信時および着信時に、基礎となるテクノロジをユーザーが意識しなくても済むようにする必要があります。ユーザーからは、エンタープライズ VoIP インフラストラクチャと PSTN 間の通話は、別の SIP セッションのように見えます。</span><span class="sxs-lookup"><span data-stu-id="0e5d6-p101">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS). In addition, users should not be aware of the underlying technology when they place and receive calls. From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>
  
<span data-ttu-id="0e5d6-108">PSTN 接続の場合は、SIP トランクまたは PSTN ゲートウェイ (PBX (Direct SIP リンクとも呼ばれる) を使用するか、PBX を使用せずに展開できます。</span><span class="sxs-lookup"><span data-stu-id="0e5d6-108">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>
  
## <a name="sip-trunking"></a><span data-ttu-id="0e5d6-109">SIP トランキング</span><span class="sxs-lookup"><span data-stu-id="0e5d6-109">SIP Trunking</span></span>

<span data-ttu-id="0e5d6-p102">PSTN ゲートウェイを使用する代わりに、SIP トランキングを使用してエンタープライズ VoIP ソリューションを PSTN に接続することもできます。 SIP トランキングを使用すると、次のようなシナリオが実現します。</span><span class="sxs-lookup"><span data-stu-id="0e5d6-p102">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking. SIP trunking enables the following scenarios:</span></span>
  
- <span data-ttu-id="0e5d6-112">企業のファイアウォールの内側または外側にいるエンタープライズ ユーザーが、E.164 準拠の番号で指定される市内通話や長距離通話を発信できます。この通話は、対応するサービス プロバイダーのサービスとして PSTN 上で終端されます。</span><span class="sxs-lookup"><span data-stu-id="0e5d6-112">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>
    
- <span data-ttu-id="0e5d6-113">PSTN サブスクライバーはだれでも、エンタープライズ ユーザーに関連付けられた Direct Inward Dialing (DID) 番号をダイヤルして、企業のファイアウォールの内側または外側にいるエンタープライズ ユーザーに連絡することができます。</span><span class="sxs-lookup"><span data-stu-id="0e5d6-113">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>
    
<span data-ttu-id="0e5d6-114">この展開ソリューションを使用するには、SIP トランキング サービス プロバイダーが必要です。</span><span class="sxs-lookup"><span data-stu-id="0e5d6-114">The use of this deployment solution requires a SIP trunking service provider.</span></span> 
  
## <a name="pstn-gateways"></a><span data-ttu-id="0e5d6-115">PSTN ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="0e5d6-115">PSTN gateways</span></span>

<span data-ttu-id="0e5d6-116">PSTN ゲートウェイは、エンタープライズ VoIP インフラストラクチャと PSTN または PBX の間の信号とメディアを変換する、サードパーティのデバイスです。</span><span class="sxs-lookup"><span data-stu-id="0e5d6-116">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="0e5d6-117">PSTN ゲートウェイは、仲介サーバーと連携して、エンタープライズ VoIP クライアントへの PSTN または PBX の通話を処理します。</span><span class="sxs-lookup"><span data-stu-id="0e5d6-117">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="0e5d6-118">また、仲介サーバーは、PSTN または PBX にルーティングするために、エンタープライズ VoIP クライアントから PSTN ゲートウェイへの通話も処理します。</span><span class="sxs-lookup"><span data-stu-id="0e5d6-118">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="0e5d6-119">Microsoft と連携して Skype for Business Server と連携するデバイスを提供するパートナーの一覧については  [、Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836)の Web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e5d6-119">For a list of partners who work with Microsoft to provide devices that work with Skype for Business Server, see  [the Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span> 
  
## <a name="private-branch-exchanges"></a><span data-ttu-id="0e5d6-120">構内交換機</span><span class="sxs-lookup"><span data-stu-id="0e5d6-120">Private Branch Exchanges</span></span>

 <span data-ttu-id="0e5d6-121">PBX (Private Branch Exchange) を使用する既存の音声インフラストラクチャがある場合は、PBX と一緒に エンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="0e5d6-121">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Enterprise Voice.</span></span>
  
<span data-ttu-id="0e5d6-122">サポートされているエンタープライズ VoIP と PBX の統合シナリオは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0e5d6-122">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>
  
- <span data-ttu-id="0e5d6-123">メディア バイパスをサポートしている IP-PBX と仲介サーバー。</span><span class="sxs-lookup"><span data-stu-id="0e5d6-123">IP-PBX that supports media bypass, with a Mediation Server.</span></span>
    
- <span data-ttu-id="0e5d6-124">スタンドアロンの PSTN ゲートウェイが必要な IP-PBX。</span><span class="sxs-lookup"><span data-stu-id="0e5d6-124">IP-PBX that requires a stand-alone PSTN gateway.</span></span>
    
- <span data-ttu-id="0e5d6-125">時分割多重 (TDM) PBX とスタンドアロンの PSTN ゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="0e5d6-125">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0e5d6-126">メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="0e5d6-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="0e5d6-127">Microsoft は、認定パートナーと一連の PSTN ゲートウェイと SBC をテストし、Cisco IP-PBX でいくつかのテストを行っています。</span><span class="sxs-lookup"><span data-stu-id="0e5d6-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="0e5d6-128">メディア バイパスは、Unified Communications Open Interoperability Program - Lync Server に記載されている製品とバージョン [でのみサポートされます](https://go.microsoft.com/fwlink/p/?linkId=214406)。</span><span class="sxs-lookup"><span data-stu-id="0e5d6-128">Media bypass is supported only with products and versions listed at [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span></span> 
  
<span data-ttu-id="0e5d6-129">新しいソリューションを提供するパートナーのエンタープライズ VoIP、Microsoft Unified Communications Partners の Web サイト [を参照してください](https://go.microsoft.com/fwlink/p/?linkId=202836)。</span><span class="sxs-lookup"><span data-stu-id="0e5d6-129">For details about partners who offer Enterprise Voice solutions, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  
<span data-ttu-id="0e5d6-130">PSTN ゲートウェイなどのハードウェア ソリューションエンタープライズ VoIP提供するパートナーの詳細については [、Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836)の Web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e5d6-130">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  

