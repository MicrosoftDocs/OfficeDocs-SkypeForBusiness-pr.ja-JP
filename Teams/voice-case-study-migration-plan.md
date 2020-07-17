---
title: チームボイスの Contoso のケーススタディ
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
description: 多国籍企業向けの Teams の音声のケーススタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786092"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="fab83-103">Contoso のケーススタディ: Teams アップグレード計画</span><span class="sxs-lookup"><span data-stu-id="fab83-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="fab83-104">Skype for Business から Teams への移行を決定する際に、Contoso はエンドユーザー向けの簡単な切り替えエクスペリエンスを提供する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="fab83-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="fab83-105">全員を同時に Teams に切り替えるのではなく、ハイブリッド接続を設定し、重複する機能のメソッドを使用してユーザーを Teams に移動することにしました。</span><span class="sxs-lookup"><span data-stu-id="fab83-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="fab83-106">これにより、チームと Skype for Business のオンプレミスのユーザーがプレゼンスを共有して通信できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fab83-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="fab83-107">ユーザーが電話システムのパイロットを入力すると、そのユーザーは [Teams のみ] モードに移動されました。</span><span class="sxs-lookup"><span data-stu-id="fab83-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="fab83-108">アップグレード、方法、およびモードに関する基本概念を理解するために、Contoso は次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fab83-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="fab83-109">Microsoft Teams へのアップグレードを開始する</span><span class="sxs-lookup"><span data-stu-id="fab83-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="fab83-110">Skype for Business から Teams へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="fab83-110">Upgrade from Skype for Business to Teams</span></span>](upgrade-to-teams-on-prem-overview.md) 
- [<span data-ttu-id="fab83-111">移行と相互運用性のガイダンス</span><span class="sxs-lookup"><span data-stu-id="fab83-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="fab83-112">Contoso は、 [Skype For business から Teams へのパスを設計して](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)いる Ignite 2019 セッションも参加しています。</span><span class="sxs-lookup"><span data-stu-id="fab83-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="fab83-113">Contoso が次のことを学習しました。</span><span class="sxs-lookup"><span data-stu-id="fab83-113">Contoso learned about:</span></span>

- <span data-ttu-id="fab83-114">相互運用性、フェデレーション、アップグレード動作などの基本的な概念</span><span class="sxs-lookup"><span data-stu-id="fab83-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="fab83-115">TeamsUpgradePolicy に基づく共存モードと管理</span><span class="sxs-lookup"><span data-stu-id="fab83-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="fab83-116">エンドユーザーエクスペリエンス:</span><span class="sxs-lookup"><span data-stu-id="fab83-116">End user experience for:</span></span> 

  - <span data-ttu-id="fab83-117">チャットと通話</span><span class="sxs-lookup"><span data-stu-id="fab83-117">Chat and Calling</span></span> 

  - <span data-ttu-id="fab83-118">会議のスケジュール</span><span class="sxs-lookup"><span data-stu-id="fab83-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="fab83-119">チームクライアントのコラボレーション機能の可用性</span><span class="sxs-lookup"><span data-stu-id="fab83-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="fab83-120">ハイブリッド接続を計画して構成するために、最初の手順として、オンプレミス環境をクラウドに移行するには、「[ハイブリッド接続の計画](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)とハイブリッド接続の[構成](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)」を参照して、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fab83-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="fab83-121">Office 365 とのフェデレーションを行うために、オンプレミス環境サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="fab83-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="fab83-122">Office 365 を信頼するようにオンプレミス環境を構成して、Office 365 で共有 SIP アドレススペースを有効にする</span><span class="sxs-lookup"><span data-stu-id="fab83-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="fab83-123">Office 365 テナントで共有 SIP アドレス空間を有効にします。</span><span class="sxs-lookup"><span data-stu-id="fab83-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="fab83-124">テクニカルパイロットでは、諸島モードを使用します。</span><span class="sxs-lookup"><span data-stu-id="fab83-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="fab83-125">ユーザーが電話システムを有効にしている場合は、ユーザーをチームのみに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="fab83-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="fab83-126">プランの呼び出しと直接ルーティングを行うには、TeamsOnly モードが必要です。</span><span class="sxs-lookup"><span data-stu-id="fab83-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span> 
