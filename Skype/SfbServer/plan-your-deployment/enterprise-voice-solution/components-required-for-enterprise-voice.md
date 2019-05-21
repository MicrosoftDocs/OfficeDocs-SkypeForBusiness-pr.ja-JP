---
title: Skype for Business Server でのエンタープライズ Voip に必要なコンポーネント
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
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Skype for Business Server のエンタープライズボイスコンポーネントの概要。
ms.openlocfilehash: 2c87cc6dceb344e8f39717a62b27e7b50cdff643
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277007"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="e86e7-103">Skype for Business Server でのエンタープライズ Voip に必要なコンポーネント</span><span class="sxs-lookup"><span data-stu-id="e86e7-103">Components required for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="e86e7-104">Skype for Business Server のエンタープライズボイスコンポーネントの概要。</span><span class="sxs-lookup"><span data-stu-id="e86e7-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="e86e7-105">エンタープライズ Voip を展開するには、トポロジに次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="e86e7-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="e86e7-106">1つまたは複数の仲介サーバー (シグナリングと、一部の構成では、内部の Skype for Business Server、エンタープライズ Voip インフラストラクチャ、公衆交換電話網 (PSTN) ゲートウェイ、またはセッション開始プロトコル間のメディア)(SIP) トランク。</span><span class="sxs-lookup"><span data-stu-id="e86e7-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="e86e7-107">仲介サーバーは、エンタープライズ Voip 展開で最も重要なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="e86e7-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="e86e7-108">詳細については、「 [Skype For Business server の仲介サーバーコンポーネント](mediation-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e86e7-108">For more information, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>
    
    <span data-ttu-id="e86e7-109">仲介サーバーは、フロントエンドサーバーと併置したり、スタンドアロンサーバーとしてインストールしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e86e7-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="e86e7-110">SIP トランクまたは PSTN ゲートウェイを含めることができる、PSTN 接続コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="e86e7-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="e86e7-111">詳細については、「 [Skype For Business Server の PSTN 接続コンポーネント](pstn-connectivity.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e86e7-111">For more information, see [PSTN connectivity components in Skype for Business Server](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="e86e7-112">エッジサーバー: 組織のファイアウォール外にいるユーザーによるエンタープライズ Voip 機能の使用を可能にします。</span><span class="sxs-lookup"><span data-stu-id="e86e7-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="e86e7-113">アクセスエッジサービスは、組織のファイアウォール外の Skype for Business ユーザーからの通話に対する SIP シグナルを提供します。</span><span class="sxs-lookup"><span data-stu-id="e86e7-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="e86e7-114">音声ビデオ エッジ サービスを使用すると、メディアが NAT およびファイアウォールを通過できます。</span><span class="sxs-lookup"><span data-stu-id="e86e7-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="e86e7-115">企業ファイアウォールの外部で統合コミュニケーション (UC) クライアントを使用する発信者には、個別の通話と電話会議の両方に音声ビデオ エッジ サービスが必要です。</span><span class="sxs-lookup"><span data-stu-id="e86e7-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="e86e7-p104">音声ビデオ認証サービスは音声ビデオ エッジ サービスと同じコンピューターに配置され、音声ビデオ エッジ サービスのための認証サービスを実行します。外部のユーザーが音声ビデオ エッジ サービスに接続するには、発信を行う前に、音声ビデオ認証サービスから認証トークンを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e86e7-p104">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="e86e7-118">さらに、一部のエンタープライズボイスコンポーネントはフロントエンドサーバーで実行されます。</span><span class="sxs-lookup"><span data-stu-id="e86e7-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="e86e7-119">これらのコンポーネントの詳細については、「 [Skype For Business Server のフロントエンドサーバー VoIP コンポーネント](front-end-server-voip.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e86e7-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server](front-end-server-voip.md)</span></span>
    

