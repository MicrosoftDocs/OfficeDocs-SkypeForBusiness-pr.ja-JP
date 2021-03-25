---
title: MICROSOFT Teams 用に IT スタッフを準備する
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Microsoft Teams の展開とサポートのために組織内の IT スタッフを準備する方法について説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 94862d7df7151983a8570e6fc458a70618c3a3fe
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119086"
---
# <a name="prepare-your-it-staff-for-microsoft-teams"></a><span data-ttu-id="bcec2-103">MICROSOFT Teams 用に IT スタッフを準備する</span><span class="sxs-lookup"><span data-stu-id="bcec2-103">Prepare your IT staff for Microsoft Teams</span></span>

<span data-ttu-id="bcec2-104">![技術準備段階が協調表示されたアップグレード行程図](media/upgrade-banner-tech-readiness.png "技術準備段階が強調表示された、アップグレード行程の各段階")</span><span class="sxs-lookup"><span data-stu-id="bcec2-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="bcec2-105">この記事は、ユーザーの準備段階と並行して実行されるアクティビティである、アップグレードが行われる技術準備段階の一部です。</span><span class="sxs-lookup"><span data-stu-id="bcec2-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="bcec2-106">次の手順に進む前に、前のステージからこれらのアクティビティを完了したと確認します。</span><span class="sxs-lookup"><span data-stu-id="bcec2-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="bcec2-107">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="bcec2-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="bcec2-108">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="bcec2-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="bcec2-109">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="bcec2-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="bcec2-110">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="bcec2-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="bcec2-111">Microsoft 365 または Office 365 組織の管理者、技術リード、サポート デスクは、高品質のユーザー エクスペリエンスを推進する責任があります。</span><span class="sxs-lookup"><span data-stu-id="bcec2-111">Your Microsoft 365 or Office 365 organization admins, technical leads, and support desk are accountable for driving a high-quality user experience.</span></span> <span data-ttu-id="bcec2-112">これには、ネットワークが Teams をサポートする準備ができていることを確認する、ユーザー用に Teams を構成する、発生する可能性のある問題を効果的にトラブルシューティングおよび解決できるなどです。</span><span class="sxs-lookup"><span data-stu-id="bcec2-112">This includes ensuring that your network is ready to support Teams, configuring Teams for your users, and being able to effectively troubleshoot and resolve issues that might arise.</span></span>

<span data-ttu-id="bcec2-113">次のリソースを IT スタッフ メンバーと共有し、Teams へのアップグレードを開始する前にユーザーをサポートする準備ができていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bcec2-113">Share the following resources with your IT staff members, and confirm that they're ready to support users before you begin your upgrade to Teams:</span></span>

- [<span data-ttu-id="bcec2-114">Microsoft Teams の管理者トレーニング</span><span class="sxs-lookup"><span data-stu-id="bcec2-114">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)
- [<span data-ttu-id="bcec2-115">ビジネス製品についてサポートに問い合わせる - 管理者ヘルプ</span><span class="sxs-lookup"><span data-stu-id="bcec2-115">Contact support for business products - Admin Help</span></span>](/microsoft-365/admin/contact-support-for-business-products)
- [<span data-ttu-id="bcec2-116">Microsoft Teams クライアントの接続性の問題をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="bcec2-116">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>](connectivity-issues.md)
- [<span data-ttu-id="bcec2-117">Microsoft Teams のトラブルシューティングでログ ファイルを使用する</span><span class="sxs-lookup"><span data-stu-id="bcec2-117">Use log files in troubleshooting Microsoft Teams</span></span>](log-files.md)



| | |
|---|---|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="bcec2-119">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="bcec2-119">Decision points</span></span>|<ul><li><span data-ttu-id="bcec2-120">Teams の展開とサポートに関与する可能性が高いすべてのサポート スタッフに関与しましたか?</span><span class="sxs-lookup"><span data-stu-id="bcec2-120">Have you involved all support staff who are likely to be involved in deploying and supporting Teams?</span></span></li><li><span data-ttu-id="bcec2-121">アップグレードの進行に合わせ、追加のスタッフをオンボーディングするトレーニング 計画を作成しましたか?</span><span class="sxs-lookup"><span data-stu-id="bcec2-121">Have you developed a training plan for onboarding additional staff as your upgrade progresses?</span></span></li></ul> |
| ![次の手順を示すアイコン](media/audio_conferencing_image9.png)<br/><span data-ttu-id="bcec2-123">次の手順</span><span class="sxs-lookup"><span data-stu-id="bcec2-123">Next steps</span></span>|<ul><li><span data-ttu-id="bcec2-124">IT スタッフが必要な情報を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcec2-124">Verify that IT staff has the information they need.</span></span></li><li><span data-ttu-id="bcec2-125">新機能がリリースされると、トレーニング計画と準備計画を見直してください。</span><span class="sxs-lookup"><span data-stu-id="bcec2-125">Revisit your training and preparation plans as new features are released.</span></span></li></ul>|

<span data-ttu-id="bcec2-126">Teams の IT スタッフを準備した後、使用している環境がすべての前提条件を満たしていることを [確認します](upgrade-plan-journey-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="bcec2-126">After you've prepared your IT staff for Teams, verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md).</span></span>