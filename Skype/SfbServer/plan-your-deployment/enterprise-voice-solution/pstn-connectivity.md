---
title: Skype for Business Server の PSTN 接続コンポーネント
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Skype for Business Server でのエンタープライズ Voip の SIP トランクと PSTN ゲートウェイについて説明します。
ms.openlocfilehash: 6d11ea3204c9b924c9e700194ee04beb9a0df56c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276484"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a><span data-ttu-id="5927a-103">Skype for Business Server の PSTN 接続コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5927a-103">PSTN connectivity components in Skype for Business Server</span></span>
 
<span data-ttu-id="5927a-104">Skype for Business Server でのエンタープライズ Voip の SIP トランクと PSTN ゲートウェイについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5927a-104">Learn about SIP trunking and PSTN gateways for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="5927a-105">エンタープライズ レベルの VoIP ソリューションでは、サービスの品質 (QoS) を低下させずに公衆交換電話網 (PSTN) との通話の発信および着信を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5927a-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="5927a-106">また、通話の発信時および着信時に、基礎となるテクノロジをユーザーが意識しなくても済むようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5927a-106">In addition, users should not be aware of the underlying technology when they place and receive calls.</span></span> <span data-ttu-id="5927a-107">ユーザーから見れば、エンタープライズボイスインフラストラクチャと PSTN 間の通話は、別の SIP セッションと同じように見えます。</span><span class="sxs-lookup"><span data-stu-id="5927a-107">From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>
  
<span data-ttu-id="5927a-108">PSTN 接続を行うには、(PBX (直接 SIP リンク) を使用して、または PBX を使用せずに) SIP トランクまたは PSTN ゲートウェイを展開します。</span><span class="sxs-lookup"><span data-stu-id="5927a-108">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>
  
## <a name="sip-trunking"></a><span data-ttu-id="5927a-109">SIP トランキング</span><span class="sxs-lookup"><span data-stu-id="5927a-109">SIP Trunking</span></span>

<span data-ttu-id="5927a-110">PSTN ゲートウェイを使用する代わりに、SIP トランキングを使用してエンタープライズ Voip ソリューションを PSTN に接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="5927a-110">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking.</span></span> <span data-ttu-id="5927a-111">SIP トランキングを使用すると、次のようなシナリオが実現します。</span><span class="sxs-lookup"><span data-stu-id="5927a-111">SIP trunking enables the following scenarios:</span></span>
  
- <span data-ttu-id="5927a-112">企業のファイアウォールの内側または外側にいるエンタープライズ ユーザーが、E.164 準拠の番号で指定される市内通話や長距離通話を発信できます。この通話は、対応するサービス プロバイダーのサービスとして PSTN 上で終端されます。</span><span class="sxs-lookup"><span data-stu-id="5927a-112">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>
    
- <span data-ttu-id="5927a-113">PSTN サブスクライバーはだれでも、エンタープライズ ユーザーに関連付けられた Direct Inward Dialing (DID) 番号をダイヤルして、企業のファイアウォールの内側または外側にいるエンタープライズ ユーザーに連絡することができます。</span><span class="sxs-lookup"><span data-stu-id="5927a-113">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>
    
<span data-ttu-id="5927a-114">この展開ソリューションを使用するには、SIP トランキング サービス プロバイダーが必要です。</span><span class="sxs-lookup"><span data-stu-id="5927a-114">The use of this deployment solution requires a SIP trunking service provider.</span></span> 
  
## <a name="pstn-gateways"></a><span data-ttu-id="5927a-115">PSTN ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="5927a-115">PSTN gateways</span></span>

<span data-ttu-id="5927a-116">PSTN ゲートウェイは、エンタープライズボイスインフラストラクチャと PSTN または PBX 間のシグナリングおよびメディアを変換するサードパーティ製のデバイスです。</span><span class="sxs-lookup"><span data-stu-id="5927a-116">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="5927a-117">PSTN ゲートウェイは、仲介サーバーと連携して、エンタープライズボイスクライアントに PSTN または PBX 通話を提供します。</span><span class="sxs-lookup"><span data-stu-id="5927a-117">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="5927a-118">また、仲介サーバーは、PSTN または PBX にルーティングするために、エンタープライズボイスクライアントから PSTN ゲートウェイへの通話を提供します。</span><span class="sxs-lookup"><span data-stu-id="5927a-118">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="5927a-119">Microsoft と連携して Skype for Business Server で動作するデバイスを提供しているパートナーのリストについては、 [Microsoft ユニファイドコミュニケーションパートナーの web サイト](https://go.microsoft.com/fwlink/p/?linkId=202836)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5927a-119">For a list of partners who work with Microsoft to provide devices that work with Skype for Business Server, see  [the Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span> 
  
## <a name="private-branch-exchanges"></a><span data-ttu-id="5927a-120">構内交換機</span><span class="sxs-lookup"><span data-stu-id="5927a-120">Private Branch Exchanges</span></span>

 <span data-ttu-id="5927a-121">構内交換会社 (PBX) を使用する既存の音声インフラストラクチャを使用している場合は、PBX をエンタープライズ Voip として使用できます。</span><span class="sxs-lookup"><span data-stu-id="5927a-121">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Enterprise Voice.</span></span>
  
<span data-ttu-id="5927a-122">サポートされているエンタープライズ Voip 統合シナリオは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5927a-122">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>
  
- <span data-ttu-id="5927a-123">仲介サーバーでメディアバイパスをサポートする IP PBX。</span><span class="sxs-lookup"><span data-stu-id="5927a-123">IP-PBX that supports media bypass, with a Mediation Server.</span></span>
    
- <span data-ttu-id="5927a-124">スタンドアロンの PSTN ゲートウェイが必要な IP-PBX。</span><span class="sxs-lookup"><span data-stu-id="5927a-124">IP-PBX that requires a stand-alone PSTN gateway.</span></span>
    
- <span data-ttu-id="5927a-125">時分割多重 (TDM) PBX とスタンドアロンの PSTN ゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="5927a-125">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5927a-126">メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="5927a-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="5927a-127">マイクロソフトでは、認定パートナーの PSTN ゲートウェイと SBC でテストを行い、Cisco IP-PBX でも一定のテストを行いました。</span><span class="sxs-lookup"><span data-stu-id="5927a-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="5927a-128">メディアのバイパスは、統合された通信の[オープンな相互運用性プログラム-Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406)での製品とバージョンでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5927a-128">Media bypass is supported only with products and versions listed at [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span></span> 
  
<span data-ttu-id="5927a-129">エンタープライズ Voip ソリューションを提供しているパートナーの詳細については、 [Microsoft ユニファイドコミュニケーションパートナーの web サイト](https://go.microsoft.com/fwlink/p/?linkId=202836)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5927a-129">For details about partners who offer Enterprise Voice solutions, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  
<span data-ttu-id="5927a-130">PSTN ゲートウェイなど、エンタープライズボイスハードウェアソリューションを提供しているパートナーの詳細については、 [Microsoft ユニファイドコミュニケーションパートナーの web サイト](https://go.microsoft.com/fwlink/p/?linkId=202836)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5927a-130">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  

