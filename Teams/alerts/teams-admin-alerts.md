---
title: Microsoft Teams監視とアラート
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
description: 管理センターでTeamsアラートと通知の機能についてMicrosoft Teamsします。
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: c99cc9af08fb1353e0c94e6f8bf156df04327d49
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684607"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a><span data-ttu-id="53afc-103">Microsoft Teams監視とアラート</span><span class="sxs-lookup"><span data-stu-id="53afc-103">Microsoft Teams monitoring and alerting</span></span>

<span data-ttu-id="53afc-104">管理センターでは、Microsoft Teamsの新しい監視Teams機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="53afc-104">New monitoring and alerting capabilities for Microsoft Teams are available in the Teams admin center.</span></span> <span data-ttu-id="53afc-105">Teams 管理センターの [通知&**アラート**] セクションで使用できるさまざまなルール セットを使用して、Teams機能を監視し、アラートを受信します。</span><span class="sxs-lookup"><span data-stu-id="53afc-105">Use different sets of rules available under the **Notifications & alerts** section in the Teams admin center to monitor Teams capabilities and receive alerts.</span></span> <span data-ttu-id="53afc-106">たとえば、IP Phone、コラボレーション バーなどの Teams デバイスの正常性を、予期せずオフラインにした場合にアクティブに監視できます。</span><span class="sxs-lookup"><span data-stu-id="53afc-106">For example, you can actively monitor the health of Teams devices such as IP Phones, collaboration bars, and others if they unexpectedly go offline.</span></span>  

<span data-ttu-id="53afc-107">組織は、監視とTeamsを使用して、次の項目を実行できます。</span><span class="sxs-lookup"><span data-stu-id="53afc-107">Your organization can use Teams monitoring and alerting to do the following items:</span></span>

- <span data-ttu-id="53afc-108">自動管理機能Teamsする</span><span class="sxs-lookup"><span data-stu-id="53afc-108">Automatically manage Teams capabilities</span></span>
- <span data-ttu-id="53afc-109">予期しない情報が表示された場合は、アラートを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="53afc-109">Be alerted if they show something unexpected.</span></span>
- <span data-ttu-id="53afc-110">是正措置を実行して、問題を追跡し戻します。</span><span class="sxs-lookup"><span data-stu-id="53afc-110">Take corrective actions to get things back on-track.</span></span>

## <a name="how-to-manage-monitoring-and-alerting"></a><span data-ttu-id="53afc-111">監視とアラートを管理する方法</span><span class="sxs-lookup"><span data-stu-id="53afc-111">How to manage monitoring and alerting</span></span>

 <span data-ttu-id="53afc-112">アラート ルールを構成するには、Microsoft 365またはサービス管理者Teamsグローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="53afc-112">You must be a global admin in Microsoft 365 or a Teams service admin to configure alerting rules.</span></span> <span data-ttu-id="53afc-113">各[管理者ロールTeamsアクセス](../using-admin-roles.md)できるレポートの詳細については、「Teams 管理者ロールを使用Teams管理者ロールを使用して管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53afc-113">See [Use Teams administrator roles to manage Teams](../using-admin-roles.md) to learn more about Teams admin roles and which reports each admin role can access.</span></span>

1. <span data-ttu-id="53afc-114">Teams 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="53afc-114">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="53afc-115">左側のナビゲーションで、[通知と通知 **] &選択します**。</span><span class="sxs-lookup"><span data-stu-id="53afc-115">From the left navigation, select **Notifications & alerts**.</span></span>
3. <span data-ttu-id="53afc-116">[ルール] から構成するルールを **選択します**。</span><span class="sxs-lookup"><span data-stu-id="53afc-116">Choose the rule you want to configure from **Rules**.</span></span>

## <a name="teams-monitoring-rules-reference"></a><span data-ttu-id="53afc-117">Teams監視ルール リファレンス</span><span class="sxs-lookup"><span data-stu-id="53afc-117">Teams monitoring rules reference</span></span>

<span data-ttu-id="53afc-118">さまざまな監視機能と構成機能を追加Teams監視エクスペリエンスを引き続き追加および改善しています。</span><span class="sxs-lookup"><span data-stu-id="53afc-118">We continue adding to and improving the Teams monitoring experience by adding various monitoring capabilities and configuration functionalities.</span></span> <span data-ttu-id="53afc-119">管理センターで現在使用できるTeams監視ルールの一覧をTeamsします。</span><span class="sxs-lookup"><span data-stu-id="53afc-119">Here's a list of the Teams monitoring rules currently available in the Teams admin center.</span></span>


|<span data-ttu-id="53afc-120">ルール</span><span class="sxs-lookup"><span data-stu-id="53afc-120">Rule</span></span>  |<span data-ttu-id="53afc-121">監視機能</span><span class="sxs-lookup"><span data-stu-id="53afc-121">Monitoring capability</span></span>|<span data-ttu-id="53afc-122">監視対象</span><span class="sxs-lookup"><span data-stu-id="53afc-122">What's monitored?</span></span> |
|---------|---------|---------|
|[<span data-ttu-id="53afc-123">デバイスの正常性状態</span><span class="sxs-lookup"><span data-stu-id="53afc-123">Device health status</span></span>](device-health-status.md)  |<span data-ttu-id="53afc-124">Teamsデバイス</span><span class="sxs-lookup"><span data-stu-id="53afc-124">Teams Devices</span></span> | <span data-ttu-id="53afc-125">ProデバイスがオフラインになTeamsデバイスをアクティブに監視します。</span><span class="sxs-lookup"><span data-stu-id="53afc-125">Pro-actively monitor Teams devices if they go offline.</span></span>|