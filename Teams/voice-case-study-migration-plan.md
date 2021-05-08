---
title: Teams Contoso のケース スタディ
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams企業向け音声ケース スタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: b0da56bc0da083654a0cd694bd5983f2fe4fe515
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093727"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="ded3c-103">Contoso のケース スタディ: Teams アップグレード プラン</span><span class="sxs-lookup"><span data-stu-id="ded3c-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="ded3c-104">Contoso は、Skype for Business から Teams に移行する決定で、エンド ユーザーに簡単な移行エクスペリエンスを提供したいと思いました。</span><span class="sxs-lookup"><span data-stu-id="ded3c-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="ded3c-105">全員を同時に Teams に切り替える代わりに、ハイブリッド接続を設定し、オーバーラップ機能方式を使用してユーザーを Teams に移動しました。</span><span class="sxs-lookup"><span data-stu-id="ded3c-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="ded3c-106">これにより、オンプレミスのユーザー Teams、Skype for Businessと通信を共有できます。</span><span class="sxs-lookup"><span data-stu-id="ded3c-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="ded3c-107">ユーザーがパイロット モードに入電話システム、ユーザーは [のみ] Teamsに移動されました。</span><span class="sxs-lookup"><span data-stu-id="ded3c-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="ded3c-108">アップグレード、方法、およびモードに関する基本的な概念を理解するために、Contoso は次の記事を読んで説明します。</span><span class="sxs-lookup"><span data-stu-id="ded3c-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="ded3c-109">Microsoft Teams へのアップグレードを開始する</span><span class="sxs-lookup"><span data-stu-id="ded3c-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="ded3c-110">IT 管理者向けアップグレード戦略</span><span class="sxs-lookup"><span data-stu-id="ded3c-110">Upgrade strategies for IT administrators</span></span>](upgrade-to-teams-on-prem-implement.md) 
- <span data-ttu-id="ded3c-111">詳細については、「[移行と相互運用に関するガイドライン](migration-interop-guidance-for-teams-with-skype.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ded3c-111">[Migration and interoperability guidance](migration-interop-guidance-for-teams-with-skype.md)</span></span>
 
<span data-ttu-id="ded3c-112">Contoso は Ignite 2019 セッションに参加しました。このセッションでは、Skype for Business[から Teams。](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="ded3c-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="ded3c-113">Contoso は次の情報を学習しました。</span><span class="sxs-lookup"><span data-stu-id="ded3c-113">Contoso learned about:</span></span>

- <span data-ttu-id="ded3c-114">相互運用性、フェデレーション、アップグレード動作などの基本的な概念</span><span class="sxs-lookup"><span data-stu-id="ded3c-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="ded3c-115">TeamsUpgradePolicy に基づく共存モードと管理</span><span class="sxs-lookup"><span data-stu-id="ded3c-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="ded3c-116">エンド ユーザー エクスペリエンス:</span><span class="sxs-lookup"><span data-stu-id="ded3c-116">End user experience for:</span></span> 

  - <span data-ttu-id="ded3c-117">チャットと通話</span><span class="sxs-lookup"><span data-stu-id="ded3c-117">Chat and Calling</span></span> 

  - <span data-ttu-id="ded3c-118">会議のスケジュール</span><span class="sxs-lookup"><span data-stu-id="ded3c-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="ded3c-119">新しいクライアントでのコラボレーション機能Teams可能</span><span class="sxs-lookup"><span data-stu-id="ded3c-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="ded3c-120">ハイブリッド接続を計画して構成するには、オンプレミス環境をクラウドに移行する最初の手順として、「ハイブリッド接続の計画[](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)」と「ハイブリッド接続[](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)の構成」を参照して、次の方法を理解します。</span><span class="sxs-lookup"><span data-stu-id="ded3c-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="ded3c-121">オンプレミス環境サービスを構成して、オンプレミスの環境サービスとOffice 365。</span><span class="sxs-lookup"><span data-stu-id="ded3c-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="ded3c-122">オンプレミス環境を構成して、Office 365を信頼し、共有 SIP アドレス空間を有効Office 365</span><span class="sxs-lookup"><span data-stu-id="ded3c-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="ded3c-123">自分のテナントで共有 SIP アドレス空間Office 365します。</span><span class="sxs-lookup"><span data-stu-id="ded3c-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="ded3c-124">テクニカル パイロット中は、Islands モードを使用します。</span><span class="sxs-lookup"><span data-stu-id="ded3c-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="ded3c-125">ユーザーが TeamsOnly モードに切り替える場合は、ユーザーが有効になっていると電話システム。</span><span class="sxs-lookup"><span data-stu-id="ded3c-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="ded3c-126">通話プランと直接ルーティングには TeamsOnly モードが必要です。</span><span class="sxs-lookup"><span data-stu-id="ded3c-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span>