---
title: Skype for Business Server の新機能 2019 |用意
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: これらの機能は、Skype for Business Server 2019 で新しく追加されたものです。'
ms.openlocfilehash: 86a8ce580a8aafcfb487a4b0cf839cd001dace8f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129400"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="e27c4-103">Skype for Business Server 2019 の機能</span><span class="sxs-lookup"><span data-stu-id="e27c4-103">What's in Skype for Business Server 2019</span></span>

<span data-ttu-id="e27c4-104">**概要:** このトピックでは、Skype for Business Server 2019 の新機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="e27c4-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="e27c4-105">Skype for Business Server 2019 の新機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e27c4-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="e27c4-106">クラウドボイスメール</span><span class="sxs-lookup"><span data-stu-id="e27c4-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="e27c4-107">Call Data コネクタ</span><span class="sxs-lookup"><span data-stu-id="e27c4-107">Call Data Connector</span></span>
- <span data-ttu-id="e27c4-108">サイド バイ サイド移行</span><span class="sxs-lookup"><span data-stu-id="e27c4-108">Side-by-side migration</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="e27c4-109">ユニファイドメッセージングサービス: クラウドボイスメール</span><span class="sxs-lookup"><span data-stu-id="e27c4-109">Unified messaging services: Cloud Voicemail</span></span>

<span data-ttu-id="e27c4-110">Exchange UM は、skype for business 2019 を Exchange 2013 または Exchange 2016 と統合する場合、Skype for Business Server 2019 で引き続き利用できます。</span><span class="sxs-lookup"><span data-stu-id="e27c4-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="e27c4-111">Exchange 2019 のサポートが変更されたため、クラウドボイスメールとクラウド自動応答機能を優先して Exchange UM 統合を重視しています。</span><span class="sxs-lookup"><span data-stu-id="e27c4-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="e27c4-112">クラウドボイスメールを使用すると、すべての Skype for Business 2019 ユーザーがオンプレミスまたはオンライン&#x2014;に所属しているかどうか&#x2014;、Microsoft クラウド内の同じボイスメールサービスにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="e27c4-112">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="e27c4-113">クラウドボイスメールには、オンプレミスのユーザーとオンラインユーザーの両方に対して次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="e27c4-113">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="e27c4-114">Skype for Business Online、Teams、または Outlook クライアントを使用した Exchange メールボックス内のボイスメールへのアクセス</span><span class="sxs-lookup"><span data-stu-id="e27c4-114">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span>
- <span data-ttu-id="e27c4-115">Web ベースのポータルを使用してボイスメールのオプションを管理する機能</span><span class="sxs-lookup"><span data-stu-id="e27c4-115">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="e27c4-116">詳細については、「 [Plan Cloud ボイスメールサービス](../sfbhybrid/hybrid/plan-cloud-voicemail.md)」および「 [plan For Skype for Business Server and Exchange server migration](../sfbhybrid/hybrid/plan-um-migration.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e27c4-116">See [Plan Cloud Voicemail service](../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="e27c4-117">通話監視: データコネクタの呼び出し</span><span class="sxs-lookup"><span data-stu-id="e27c4-117">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="e27c4-118">通話データコネクタを使用すると、ユーザーの通話品質をすべて監視するためにオンプレミスとオンラインツールの異なるセットを使用する必要がなくなるため、ハイブリッド環境での通話監視が大幅に簡素化されます。</span><span class="sxs-lookup"><span data-stu-id="e27c4-118">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="e27c4-119">ユーザーがオンプレミスまたはオンラインに所属しているかどうかにかかわらず、組織全体の通話品質をオンラインで表示するように選択できます。</span><span class="sxs-lookup"><span data-stu-id="e27c4-119">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="e27c4-120">Call Data Connector を使用すると、1つのツールセットを使用して次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e27c4-120">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="e27c4-121">Microsoft Teams、Skype for Business Online、Skype for Business Server でのユーザーの作業状況を監視します。</span><span class="sxs-lookup"><span data-stu-id="e27c4-121">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="e27c4-122">ネットワーク全体で問題の表示とトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="e27c4-122">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="e27c4-123">ヘルプデスクおよび管理者の役割を呼び出し分析に割り当てて、ヘルプデスクの作業者が自分の責任範囲を表示およびトラブルシューティングできるようにします。</span><span class="sxs-lookup"><span data-stu-id="e27c4-123">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="e27c4-124">詳細については、「 [Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e27c4-124">See [Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) for more information.</span></span>

### <a name="see-also"></a><span data-ttu-id="e27c4-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="e27c4-125">See also</span></span>

[<span data-ttu-id="e27c4-126">Skype for Business Server 2019 で廃止された機能</span><span class="sxs-lookup"><span data-stu-id="e27c4-126">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)
