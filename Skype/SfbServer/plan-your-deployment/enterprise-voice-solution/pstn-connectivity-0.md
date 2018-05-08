---
title: Skype for Business Server 2015 での PSTN 接続の計画
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: ビジネス サーバーの PSTN への接続では、Skype でエンタープライズ VoIP の計画。
ms.openlocfilehash: 228391049988c2eb886c0cb4e7caccce6f55ff3b
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server-2015"></a><span data-ttu-id="bf5eb-103">Skype for Business Server 2015 での PSTN 接続の計画</span><span class="sxs-lookup"><span data-stu-id="bf5eb-103">Plan for PSTN connectivity in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bf5eb-104">ビジネス サーバーの PSTN への接続では、Skype でエンタープライズ VoIP の計画。</span><span class="sxs-lookup"><span data-stu-id="bf5eb-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="bf5eb-105">エンタープライズ レベルの VoIP ソリューションでは、サービスの品質 (QoS) を低下させずに公衆交換電話網 (PSTN) との通話の発信および着信を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf5eb-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="bf5eb-106">配置し、呼び出しを受信するユーザーいない注意すべき基礎となるテクノロジ: ユーザーの観点からは、エンタープライズ VoIP インフラストラクチャと PSTN との間の呼び出しする必要がありますだけ別の電話のように思われます。</span><span class="sxs-lookup"><span data-stu-id="bf5eb-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="bf5eb-107">Skype ビジネス サーバーの次のオプションを使用して信頼性の高いスケーラブルな PSTN 接続を提供します。</span><span class="sxs-lookup"><span data-stu-id="bf5eb-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="bf5eb-108">インターネット テレフォニー サービス プロバイダー (ITSP) への **SIP トランク**</span><span class="sxs-lookup"><span data-stu-id="bf5eb-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="bf5eb-109">PSTN ゲートウェイへの**直接 SIP 接続**</span><span class="sxs-lookup"><span data-stu-id="bf5eb-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="bf5eb-110">PBX への**直接 SIP 接続**</span><span class="sxs-lookup"><span data-stu-id="bf5eb-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="bf5eb-p102">企業は、その規模、地理的範囲、および既存の音声インフラストラクチャに応じて、さまざまな場所でこれらのオプションのうちの 1 つ、2 つ、または 3 つすべてを使用できます。これらのオプションの詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf5eb-p102">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations. For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="bf5eb-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bf5eb-113">In this section</span></span>

- [<span data-ttu-id="bf5eb-114">ビジネス サーバー 2015 の Skype での SIP トランク</span><span class="sxs-lookup"><span data-stu-id="bf5eb-114">SIP trunking in Skype for Business Server 2015</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="bf5eb-115">ビジネス サーバー 2015 の Skype で直接 SIP 接続</span><span class="sxs-lookup"><span data-stu-id="bf5eb-115">Direct SIP connections in Skype for Business Server 2015</span></span>](direct-sip.md)
    
- [<span data-ttu-id="bf5eb-116">ビジネス サーバー 2015 の Skype で M:N トランク</span><span class="sxs-lookup"><span data-stu-id="bf5eb-116">M:N trunk in Skype for Business Server 2015</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="bf5eb-117">ビジネス サーバー 2015 の Skype での変換規則</span><span class="sxs-lookup"><span data-stu-id="bf5eb-117">Translation rules in Skype for Business Server 2015</span></span>](translation-rules.md)
    
- [<span data-ttu-id="bf5eb-118">ビジネス サーバー 2015 のアウト バウンドの音声が Skype でルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="bf5eb-118">Plan for outbound voice routing in Skype for Business Server 2015</span></span>](outbound-voice-routing.md)
    

