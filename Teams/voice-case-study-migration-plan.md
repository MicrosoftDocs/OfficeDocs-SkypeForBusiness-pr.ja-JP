---
title: Teams の音声 Contoso のケース スタディ
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
description: 多国籍企業向け Teams 音声ケース スタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: 93f6d0877537a740dc867b44c3c4deb9bebb8441
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421292"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="2f4c8-103">Contoso のケース スタディ: Teams アップグレード プラン</span><span class="sxs-lookup"><span data-stu-id="2f4c8-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="2f4c8-104">Skype for Business から Teams に移行する決定で、Contoso はエンド ユーザーに簡単な移行エクスペリエンスを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f4c8-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="2f4c8-105">全員を同時に Teams に切り替える代わりに、ハイブリッド接続をセットアップし、重複する機能の方法を使用してユーザーを Teams に移動することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="2f4c8-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="2f4c8-106">これにより、Teams と Skype for Business オンプレミスのユーザーはプレゼンスを共有し、通信を行う必要がありました。</span><span class="sxs-lookup"><span data-stu-id="2f4c8-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="2f4c8-107">ユーザーが電話システムのパイロットに参加すると、ユーザーは Teams のみモードに移動されました。</span><span class="sxs-lookup"><span data-stu-id="2f4c8-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="2f4c8-108">アップグレード、メソッド、モードに関する基本的な概念を理解するために、Contoso は次の記事を読んで説明します。</span><span class="sxs-lookup"><span data-stu-id="2f4c8-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="2f4c8-109">Microsoft Teams へのアップグレードを開始する</span><span class="sxs-lookup"><span data-stu-id="2f4c8-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="2f4c8-110">IT 管理者向けアップグレード戦略</span><span class="sxs-lookup"><span data-stu-id="2f4c8-110">Upgrade strategies for IT administrators</span></span>](upgrade-to-teams-on-prem-implement.md) 
- <span data-ttu-id="2f4c8-111">詳細については、「[移行と相互運用に関するガイドライン](migration-interop-guidance-for-teams-with-skype.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f4c8-111">[Migration and interoperability guidance](migration-interop-guidance-for-teams-with-skype.md)</span></span>
 
<span data-ttu-id="2f4c8-112">Contoso は、Skype for Business から Teams へのパスを設計する Ignite 2019 [セッションにも参加しました](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)。</span><span class="sxs-lookup"><span data-stu-id="2f4c8-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="2f4c8-113">Contoso は次の情報を学習しました。</span><span class="sxs-lookup"><span data-stu-id="2f4c8-113">Contoso learned about:</span></span>

- <span data-ttu-id="2f4c8-114">相互運用性、フェデレーション、アップグレード動作などの基本的な概念</span><span class="sxs-lookup"><span data-stu-id="2f4c8-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="2f4c8-115">TeamsUpgradePolicy に基づく共存モードと管理</span><span class="sxs-lookup"><span data-stu-id="2f4c8-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="2f4c8-116">エンド ユーザー エクスペリエンス:</span><span class="sxs-lookup"><span data-stu-id="2f4c8-116">End user experience for:</span></span> 

  - <span data-ttu-id="2f4c8-117">チャットと通話</span><span class="sxs-lookup"><span data-stu-id="2f4c8-117">Chat and Calling</span></span> 

  - <span data-ttu-id="2f4c8-118">会議のスケジュール</span><span class="sxs-lookup"><span data-stu-id="2f4c8-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="2f4c8-119">Teams クライアントでのコラボレーション機能の可用性</span><span class="sxs-lookup"><span data-stu-id="2f4c8-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="2f4c8-120">ハイブリッド接続を計画および構成するには、オンプレミス環境をクラウドに移行する最初の手順として、Contoso はハイブリッド[](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)接続を計画し、[](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)次の方法を理解するためにハイブリッド接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="2f4c8-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="2f4c8-121">オンプレミス環境サービスを構成して、Office 365 とフェデレーションします。</span><span class="sxs-lookup"><span data-stu-id="2f4c8-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="2f4c8-122">オンプレミス環境を構成して Office 365 を信頼し、Office 365 で共有 SIP アドレス空間を有効にする</span><span class="sxs-lookup"><span data-stu-id="2f4c8-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="2f4c8-123">Office 365 テナントで共有 SIP アドレス空間を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2f4c8-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="2f4c8-124">テクニカル パイロット中は、諸島モードを使用します。</span><span class="sxs-lookup"><span data-stu-id="2f4c8-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="2f4c8-125">ユーザーが電話システムに対して有効になると、ユーザーを TeamsOnly モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="2f4c8-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="2f4c8-126">通話プランと直接ルーティングには TeamsOnly モードが必要です。</span><span class="sxs-lookup"><span data-stu-id="2f4c8-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span> 
