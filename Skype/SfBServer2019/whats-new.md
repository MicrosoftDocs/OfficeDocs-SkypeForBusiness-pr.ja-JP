---
title: Skype for Business Server 2019 の新機能 |特性
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: これらの機能は、Skype for Business Server 2019 で新しく追加されています。'
ms.openlocfilehash: 6db5ea6589a56f696f233854372fc95d6064fed7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799417"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="d9f06-103">Skype for Business Server 2019 の機能</span><span class="sxs-lookup"><span data-stu-id="d9f06-103">What's in Skype for Business Server 2019</span></span>

<span data-ttu-id="d9f06-104">**概要:** このトピックでは、Skype for Business Server 2019 の新機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="d9f06-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="d9f06-105">Skype for Business Server 2019 の新機能には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="d9f06-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="d9f06-106">クラウド ボイスメール</span><span class="sxs-lookup"><span data-stu-id="d9f06-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="d9f06-107">通話データ コネクタ</span><span class="sxs-lookup"><span data-stu-id="d9f06-107">Call Data Connector</span></span>
- <span data-ttu-id="d9f06-108">サイドバイサイド移行</span><span class="sxs-lookup"><span data-stu-id="d9f06-108">Side-by-side migration</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="d9f06-109">ユニファイドメッセージングサービス: クラウドボイスメール</span><span class="sxs-lookup"><span data-stu-id="d9f06-109">Unified messaging services: Cloud Voicemail</span></span>

<span data-ttu-id="d9f06-110">Skype for business 2019 を Exchange 2013 または Exchange 2016 と統合すると、exchange UM は Skype for Business Server 2019 で利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="d9f06-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="d9f06-111">Exchange 2019 のサポートが変更されたため、クラウドボイスメールとクラウド自動応答機能を利用して、Exchange UM との統合を強調することができます。</span><span class="sxs-lookup"><span data-stu-id="d9f06-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="d9f06-112">クラウドボイスメールを使用すると、社内または&#x2014;オンラインのどちらにいるかを&#x2014;すべての Skype for Business 2019 ユーザーが、Microsoft Cloud で同じボイスメールサービスにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="d9f06-112">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="d9f06-113">クラウドボイスメールでは、オンプレミスとオンラインの両方のユーザーに次の利点があります。</span><span class="sxs-lookup"><span data-stu-id="d9f06-113">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="d9f06-114">Skype for Business Online、Teams、または Outlook クライアントを使用して、Exchange メールボックス内のボイスメールにアクセスする</span><span class="sxs-lookup"><span data-stu-id="d9f06-114">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span>
- <span data-ttu-id="d9f06-115">Web ベースのポータルを使用してボイスメールオプションを管理する機能</span><span class="sxs-lookup"><span data-stu-id="d9f06-115">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="d9f06-116">詳細については、「[クラウドボイスメールサービスの計画](../sfbhybrid/hybrid/plan-cloud-voicemail.md)」および「 [Skype for Business Server と Exchange server の移行の計画](../sfbhybrid/hybrid/plan-um-migration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9f06-116">See [Plan Cloud Voicemail service](../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="d9f06-117">通話監視: データコネクタの呼び出し</span><span class="sxs-lookup"><span data-stu-id="d9f06-117">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="d9f06-118">データコネクタを呼び出すと、すべてのユーザーの通話品質を監視するためにオンプレミスとオンラインの各種ツールのセットを使用する必要がなくなったため、ハイブリッド環境での通話監視が大幅に簡素化されます。</span><span class="sxs-lookup"><span data-stu-id="d9f06-118">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="d9f06-119">ユーザーがオンプレミスとオンラインのどちらであるかにかかわらず、組織全体の通話品質をオンラインで表示するように選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="d9f06-119">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="d9f06-120">通話データコネクタを使用すると、次のタスクを1つのツールセットを使って実行できます。</span><span class="sxs-lookup"><span data-stu-id="d9f06-120">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="d9f06-121">Microsoft Teams、Skype for Business Online、Skype for Business Server でユーザーエクスペリエンスを監視します。</span><span class="sxs-lookup"><span data-stu-id="d9f06-121">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="d9f06-122">ネットワーク全体で問題を表示してトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="d9f06-122">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="d9f06-123">ヘルプヘルプと管理者の役割を通話分析に割り当てて、ヘルプデスクの作業者が責任の範囲を表示し、トラブルシューティングできるようにします。</span><span class="sxs-lookup"><span data-stu-id="d9f06-123">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="d9f06-124">詳細については、「[通話データコネクタを計画](../sfbhybrid/hybrid/plan-call-data-connector.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9f06-124">See [Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) for more information.</span></span>

### <a name="see-also"></a><span data-ttu-id="d9f06-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9f06-125">See also</span></span>

[<span data-ttu-id="d9f06-126">Skype for Business Server 2019 で廃止される機能</span><span class="sxs-lookup"><span data-stu-id="d9f06-126">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)
