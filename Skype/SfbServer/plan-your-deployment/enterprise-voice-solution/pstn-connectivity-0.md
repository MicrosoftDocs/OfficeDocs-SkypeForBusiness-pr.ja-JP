---
title: Skype for Business Server での PSTN 接続を計画する
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
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Skype for Business Server のエンタープライズボイスで PSTN 接続を計画します。
ms.openlocfilehash: f0b6aa6b43562fea91885b0d55d75fd234ab97de
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276498"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="4e98e-103">Skype for Business Server での PSTN 接続を計画する</span><span class="sxs-lookup"><span data-stu-id="4e98e-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="4e98e-104">Skype for Business Server のエンタープライズボイスで PSTN 接続を計画します。</span><span class="sxs-lookup"><span data-stu-id="4e98e-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="4e98e-105">エンタープライズ レベルの VoIP ソリューションでは、サービスの品質 (QoS) を低下させずに公衆交換電話網 (PSTN) との通話の発信および着信を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e98e-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="4e98e-106">通話の発信と受信を行うユーザーは、基になるテクノロジを認識していません。ユーザーの視点から見ると、エンタープライズ Voip インフラストラクチャと PSTN との間の通話は、別の電話会議と同じように見えます。</span><span class="sxs-lookup"><span data-stu-id="4e98e-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="4e98e-107">Skype for Business Server は、次のオプションを使用して、信頼性の高いスケーラブルな PSTN 接続を提供します。</span><span class="sxs-lookup"><span data-stu-id="4e98e-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="4e98e-108">インターネット テレフォニー サービス プロバイダー (ITSP) への **SIP トランク**</span><span class="sxs-lookup"><span data-stu-id="4e98e-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="4e98e-109">PSTN ゲートウェイへの**直接 SIP 接続**</span><span class="sxs-lookup"><span data-stu-id="4e98e-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="4e98e-110">PBX への**直接 SIP 接続**</span><span class="sxs-lookup"><span data-stu-id="4e98e-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="4e98e-p102">企業は、その規模、地理的範囲、および既存の音声インフラストラクチャに応じて、さまざまな場所でこれらのオプションのうちの 1 つ、2 つ、または 3 つすべてを使用できます。これらのオプションの詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e98e-p102">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations. For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="4e98e-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4e98e-113">In this section</span></span>

- [<span data-ttu-id="4e98e-114">Skype for Business Server の SIP トランキング</span><span class="sxs-lookup"><span data-stu-id="4e98e-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="4e98e-115">Skype for Business Server での直接 SIP 接続</span><span class="sxs-lookup"><span data-stu-id="4e98e-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="4e98e-116">Skype for Business Server の M:N トランク</span><span class="sxs-lookup"><span data-stu-id="4e98e-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="4e98e-117">Skype for Business Server の翻訳ルール</span><span class="sxs-lookup"><span data-stu-id="4e98e-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="4e98e-118">Skype for Business Server での送信ボイスルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="4e98e-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

