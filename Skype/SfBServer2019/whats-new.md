---
title: Skype for Business Server 2019 の新機能 |機能
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: これらの機能は、Skype for Business Server 2019 の新機能です。'
ms.openlocfilehash: f20abfa7d48717052c8ee0144e143a21b168286d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812587"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="f6200-103">Skype for Business Server 2019 の機能</span><span class="sxs-lookup"><span data-stu-id="f6200-103">What's in Skype for Business Server 2019</span></span>

<span data-ttu-id="f6200-104">**概要:** このトピックでは、Skype for Business Server 2019 の新機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="f6200-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="f6200-105">Skype for Business Server 2019 の新機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6200-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="f6200-106">クラウド ボイスメール</span><span class="sxs-lookup"><span data-stu-id="f6200-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="f6200-107">通話データ コネクタ</span><span class="sxs-lookup"><span data-stu-id="f6200-107">Call Data Connector</span></span>
- <span data-ttu-id="f6200-108">サイド バイ サイド移行</span><span class="sxs-lookup"><span data-stu-id="f6200-108">Side-by-side migration</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="f6200-109">ユニファイド メッセージング サービス: クラウド ボイスメール</span><span class="sxs-lookup"><span data-stu-id="f6200-109">Unified messaging services: Cloud Voicemail</span></span>

<span data-ttu-id="f6200-110">Skype for Business 2019 と Exchange 2013 または Exchange 2016 を統合する場合、Exchange UM は Skype for Business Server 2019 で引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6200-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="f6200-111">Exchange 2019 のサポートの変更により、Exchange UM 統合は、クラウド ボイスメール機能とクラウド ボイスメール機能の使用を重視自動応答されています。</span><span class="sxs-lookup"><span data-stu-id="f6200-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="f6200-112">クラウド ボイスメールを使用すると、すべての Skype for Business 2019 ユーザー&#x2014;がオンプレミスまたはオンラインの&#x2014;にホームの場合でも、Microsoft Cloud の同じボイスメール サービスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f6200-112">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="f6200-113">クラウド ボイスメールは、オンプレミスユーザーとオンライン ユーザーの両方に次の利点があります。</span><span class="sxs-lookup"><span data-stu-id="f6200-113">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="f6200-114">Skype for Business Online、Teams、または Outlook クライアントを使用した Exchange メールボックス内のボイスメールへのアクセス</span><span class="sxs-lookup"><span data-stu-id="f6200-114">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span>
- <span data-ttu-id="f6200-115">Web ベースのポータルを使用してボイスメール オプションを管理する機能</span><span class="sxs-lookup"><span data-stu-id="f6200-115">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="f6200-116">詳細 [については、「クラウド ボイスメール サービスの計画](../sfbhybrid/hybrid/plan-cloud-voicemail.md) 」と [「Skype for Business Server](../sfbhybrid/hybrid/plan-um-migration.md) の計画」および「Exchange Server移行」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6200-116">See [Plan Cloud Voicemail service](../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="f6200-117">通話監視: 通話データ コネクタ</span><span class="sxs-lookup"><span data-stu-id="f6200-117">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="f6200-118">Call Data Connector は、すべてのユーザーの通話品質を監視するために異なるセットのオンプレミスツールとオンライン ツールを使用する必要がなくなったため、ハイブリッド環境での通話の監視を大幅に簡素化します。</span><span class="sxs-lookup"><span data-stu-id="f6200-118">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="f6200-119">ユーザーがオンプレミスに所属する場合もオンラインの場合でも、組織全体の通話品質をオンラインで表示できます。</span><span class="sxs-lookup"><span data-stu-id="f6200-119">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="f6200-120">Call Data Connector を使用すると、1 つのツールセットを使用して次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f6200-120">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="f6200-121">Microsoft Teams、Skype for Business Online、Skype for Business Server のユーザー エクスペリエンスを監視します。</span><span class="sxs-lookup"><span data-stu-id="f6200-121">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="f6200-122">ネットワーク全体の問題を表示およびトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="f6200-122">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="f6200-123">ヘルプデスクの作業者が自分の責任分野を表示およびトラブルシューティングできるよう、通話分析にヘルプデスクと管理者の役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f6200-123">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="f6200-124">詳細 [については、「Plan Call Data Connector」](../sfbhybrid/hybrid/plan-call-data-connector.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6200-124">See [Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) for more information.</span></span>

### <a name="see-also"></a><span data-ttu-id="f6200-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6200-125">See also</span></span>

[<span data-ttu-id="f6200-126">Skype for Business Server 2019 で廃止された機能</span><span class="sxs-lookup"><span data-stu-id="f6200-126">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)
