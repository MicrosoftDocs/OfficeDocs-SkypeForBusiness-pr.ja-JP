---
title: Skype でエンタープライズ VoIP のサーバーのビジネスに必要なコンポーネント
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Skype ビジネス サーバーでエンタープライズ VoIP のコンポーネントの概要です。
ms.openlocfilehash: 800a12b2d83703f188fff04452cf865757d5cad9
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20970480"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="664a6-103">Skype でエンタープライズ VoIP のサーバーのビジネスに必要なコンポーネント</span><span class="sxs-lookup"><span data-stu-id="664a6-103">Components required for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="664a6-104">Skype ビジネス サーバーでエンタープライズ VoIP のコンポーネントの概要です。</span><span class="sxs-lookup"><span data-stu-id="664a6-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="664a6-105">エンタープライズ VoIP を展開するには、トポロジでは、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="664a6-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="664a6-106">信号と、構成によっては、内部の Skype ビジネス サーバー、エンタープライズ VoIP インフラストラクチャと公衆交換電話網 (PSTN) ゲートウェイまたはセッション開始プロトコルの間でのメディアを変換する 1 つまたは複数の仲介サーバー(SIP) トランク。</span><span class="sxs-lookup"><span data-stu-id="664a6-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="664a6-107">仲介サーバーは、エンタープライズ VoIP 展開で最も重要なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="664a6-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="664a6-108">詳細については、 [Skype のビジネス サーバーの仲介サーバーのコンポーネント](mediation-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="664a6-108">For more information, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>
    
    <span data-ttu-id="664a6-109">仲介サーバーをフロント エンド サーバーと同じ場所またはスタンドアロン サーバーとしてインストールされていることができます。</span><span class="sxs-lookup"><span data-stu-id="664a6-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="664a6-110">SIP トランクまたは PSTN ゲートウェイを含めることができる、PSTN 接続コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="664a6-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="664a6-111">詳細については、 [Skype のビジネス サーバーの PSTN 接続のコンポーネント](pstn-connectivity.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="664a6-111">For more information, see [PSTN connectivity components in Skype for Business Server](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="664a6-112">エッジ サーバーは、組織のファイアウォールの外部にいるときに、ユーザーがエンタープライズ VoIP 機能の使用を有効にします。</span><span class="sxs-lookup"><span data-stu-id="664a6-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="664a6-113">アクセス エッジ サービスは、ビジネス ユーザーが、組織のファイアウォール外の Skype からの通話の SIP シグナリングを提供します。</span><span class="sxs-lookup"><span data-stu-id="664a6-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="664a6-114">音声ビデオ エッジ サービスを使用すると、メディアが NAT およびファイアウォールを通過できます。</span><span class="sxs-lookup"><span data-stu-id="664a6-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="664a6-115">企業ファイアウォールの外部で統合コミュニケーション (UC) クライアントを使用する発信者には、個別の通話と電話会議の両方に音声ビデオ エッジ サービスが必要です。</span><span class="sxs-lookup"><span data-stu-id="664a6-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="664a6-p104">音声ビデオ認証サービスは音声ビデオ エッジ サービスと同じコンピューターに配置され、音声ビデオ エッジ サービスのための認証サービスを実行します。外部のユーザーが音声ビデオ エッジ サービスに接続するには、発信を行う前に、音声ビデオ認証サービスから認証トークンを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="664a6-p104">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="664a6-118">さらに、エンタープライズ VoIP のコンポーネントのいくつかは、フロント エンド サーバーで実行します。</span><span class="sxs-lookup"><span data-stu-id="664a6-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="664a6-119">これらのコンポーネントに関する詳細については、 [Skype のビジネス サーバーのフロント エンド サーバーの VoIP コンポーネント](front-end-server-voip.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="664a6-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server](front-end-server-voip.md)</span></span>
    

