---
title: Microsoft Teams の監視と通知
author: vaibhav
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: vapati
f1.keywords: ''
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-collaboration
description: Microsoft Teams 管理センターで利用できる Teams の通知機能について説明します。
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 1be3ca52d4b03cfbf82d82310148ef4c2bb7f06d
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819494"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a><span data-ttu-id="1dd65-103">Microsoft Teams の監視と警告</span><span class="sxs-lookup"><span data-stu-id="1dd65-103">Microsoft Teams monitoring and alerting</span></span>

<span data-ttu-id="1dd65-104">Microsoft Teams の新しい監視機能と通知機能は、Teams 管理センターで利用できます。</span><span class="sxs-lookup"><span data-stu-id="1dd65-104">New monitoring and alerting capabilities for Microsoft Teams are available in the Teams admin center.</span></span> <span data-ttu-id="1dd65-105">Teams の機能を監視し、通知を受け取&通知セクションの下にあるさまざまなルール セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1dd65-105">Use different sets of rules available under the **Notifications & alerts** section in the Teams admin center to monitor Teams capabilities and receive alerts.</span></span> <span data-ttu-id="1dd65-106">たとえば、IP Phone、コラボレーション バーなどの Teams デバイスが予期せずオフラインになる場合、その他のデバイスの正常性をアクティブに監視できます。</span><span class="sxs-lookup"><span data-stu-id="1dd65-106">For example, you can actively monitor the health of Teams devices such as IP Phones, collaboration bars, and others if they unexpectedly go offline.</span></span>  

<span data-ttu-id="1dd65-107">組織では、Teams の監視と通知を使用して、次の項目を実行できます。</span><span class="sxs-lookup"><span data-stu-id="1dd65-107">Your organization can use Teams monitoring and alerting to do the following items:</span></span>

- <span data-ttu-id="1dd65-108">Teams の機能を自動的に管理する</span><span class="sxs-lookup"><span data-stu-id="1dd65-108">Automatically manage Teams capabilities</span></span>
- <span data-ttu-id="1dd65-109">予期しないメッセージが表示される場合は、警告を表示してください。</span><span class="sxs-lookup"><span data-stu-id="1dd65-109">Be alerted if they show something unexpected.</span></span>
- <span data-ttu-id="1dd65-110">修正アクションを実行して、問題を追跡し戻します。</span><span class="sxs-lookup"><span data-stu-id="1dd65-110">Take corrective actions to get things back on-track.</span></span>

## <a name="how-to-manage-monitoring-and-alerting"></a><span data-ttu-id="1dd65-111">監視と通知を管理する方法</span><span class="sxs-lookup"><span data-stu-id="1dd65-111">How to manage monitoring and alerting</span></span>

 <span data-ttu-id="1dd65-112">通知ルールを構成するには、Microsoft 365 のグローバル管理者または Teams サービス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1dd65-112">You must be a global admin in Microsoft 365 or a Teams service admin to configure alerting rules.</span></span> <span data-ttu-id="1dd65-113">Teams [管理者ロールと各管理者ロールが](../using-admin-roles.md) アクセスできるレポートの詳細については、「Teams 管理者ロールを使用して Teams を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dd65-113">See [Use Teams administrator roles to manage Teams](../using-admin-roles.md) to learn more about Teams admin roles and which reports each admin role can access.</span></span>

1. <span data-ttu-id="1dd65-114">Teams 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="1dd65-114">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="1dd65-115">左側のナビゲーションで、[通知と通知 **] &します**。</span><span class="sxs-lookup"><span data-stu-id="1dd65-115">From the left navigation, select **Notifications & alerts**.</span></span>
3. <span data-ttu-id="1dd65-116">[ルール] から構成するルールを選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="1dd65-116">Choose the rule you want to configure from **Rules**.</span></span>

## <a name="teams-monitoring-rules-reference"></a><span data-ttu-id="1dd65-117">Teams の監視ルールリファレンス</span><span class="sxs-lookup"><span data-stu-id="1dd65-117">Teams monitoring rules reference</span></span>

<span data-ttu-id="1dd65-118">さまざまな監視機能と構成機能を追加することで、Teams の監視エクスペリエンスを引き続き追加および改善しています。</span><span class="sxs-lookup"><span data-stu-id="1dd65-118">We continue adding to and improving the Teams monitoring experience by adding various monitoring capabilities and configuration functionalities.</span></span> <span data-ttu-id="1dd65-119">Teams 管理センターで現在利用可能な Teams の監視ルールの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1dd65-119">Here's a list of the Teams monitoring rules currently available in the Teams admin center.</span></span>


|<span data-ttu-id="1dd65-120">ルール</span><span class="sxs-lookup"><span data-stu-id="1dd65-120">Rule</span></span>  |<span data-ttu-id="1dd65-121">監視機能</span><span class="sxs-lookup"><span data-stu-id="1dd65-121">Monitoring capability</span></span>|<span data-ttu-id="1dd65-122">監視対象</span><span class="sxs-lookup"><span data-stu-id="1dd65-122">What's monitored?</span></span> |
|---------|---------|---------|
|[<span data-ttu-id="1dd65-123">デバイスの正常性の状態</span><span class="sxs-lookup"><span data-stu-id="1dd65-123">Device health status</span></span>](device-health-status.md)  |<span data-ttu-id="1dd65-124">Teams デバイス</span><span class="sxs-lookup"><span data-stu-id="1dd65-124">Teams Devices</span></span> | <span data-ttu-id="1dd65-125">Teams デバイスがオフラインの場合は、積極的に監視します。</span><span class="sxs-lookup"><span data-stu-id="1dd65-125">Pro-actively monitor Teams devices if they go offline.</span></span>|
