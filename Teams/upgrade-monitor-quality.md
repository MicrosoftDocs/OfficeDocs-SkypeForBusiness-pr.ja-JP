---
title: 体験レビュー ガイド - マイクロソフトのチームの質
author: turgayo
ms.author: turgayo
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: タスクと活動の品質とマイクロソフトのチームの使用率を監視するために必要な
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: f74757654fffc46276907e54c41223fe7d533f2e
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886071"
---
<span data-ttu-id="776c7-103">![オペレーショナル ・ エクセレンスの段階に重点を置いて、旅アップグレードの段階](media/upgrade-banner-op-excellence.png "オペレーショナル ・ エクセレンスの段階に重点を置いて、旅アップグレードの段階")</span><span class="sxs-lookup"><span data-stu-id="776c7-103">![Stages of the upgrade journey, with emphasis on the Operational Excellence stage](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="776c7-104">この資料では、オペレーショナル ・ エクセレンスの段階と同時に開始のチームにビジネス用の Skype からのアップグレードが完了したら、アップグレードの旅の一部です。</span><span class="sxs-lookup"><span data-stu-id="776c7-104">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="776c7-105">レビュー ガイドの経験の質</span><span class="sxs-lookup"><span data-stu-id="776c7-105">Quality of Experience Review Guide</span></span>

<span data-ttu-id="776c7-106">[発生レビュー ガイドの品質](https://aka.ms/qerguide)には、評価し、次のように、ユーザー エクスペリエンスの向上に大きな影響がある主な分野で改善策のガイダンスを提供するアクティビティのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="776c7-106">The [Quality of Experience Review Guide](https://aka.ms/qerguide) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="776c7-107">![品質の経験の確認中に調査する主要な領域: オーディオ、信頼性、およびユーザー調査の結果です]。(media/plan-my-service-management-image2.png "品質の経験の確認中に調査する主要な領域: オーディオ、信頼性、およびユーザー調査の結果です")。</span><span class="sxs-lookup"><span data-stu-id="776c7-107">![The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="776c7-108">によって継続的に評価し、このガイドで説明されている領域を得られるように、ユーザー エクスペリエンスに悪影響を及ぼす可能性があるを減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="776c7-108">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="776c7-109">展開で発生したユーザー エクスペリエンスの問題の多くは、次のカテゴリに分類できます。</span><span class="sxs-lookup"><span data-stu-id="776c7-109">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

-   <span data-ttu-id="776c7-110">不完全なファイアウォールまたはプロキシの構成</span><span class="sxs-lookup"><span data-stu-id="776c7-110">Incomplete firewall or proxy configuration</span></span>

-   <span data-ttu-id="776c7-111">Wifi カバレッジが低い</span><span class="sxs-lookup"><span data-stu-id="776c7-111">Poor Wi-Fi coverage</span></span>

-   <span data-ttu-id="776c7-112">十分な帯域幅</span><span class="sxs-lookup"><span data-stu-id="776c7-112">Insufficient bandwidth</span></span>

-   <span data-ttu-id="776c7-113">VPN</span><span class="sxs-lookup"><span data-stu-id="776c7-113">VPN</span></span>

-   <span data-ttu-id="776c7-114">最適化されていない、または組み込みのオーディオ デバイスの使用</span><span class="sxs-lookup"><span data-stu-id="776c7-114">Use of unoptimized or built-in audio devices</span></span>

-   <span data-ttu-id="776c7-115">問題のあるサブネットまたはネットワーク デバイス</span><span class="sxs-lookup"><span data-stu-id="776c7-115">Problematic subnets or network devices</span></span>

<span data-ttu-id="776c7-116">品質のエクスペリエンス評価ガイドで提供されるガイダンスを報告し、説明したとおりで、オーディオを採用し、影響を最大化に重点を置いた各領域を調査する主要なツールとして呼び出す品質ダッシュ ボード (救難) オンラインを使用して重点的に説明します。</span><span class="sxs-lookup"><span data-stu-id="776c7-116">The guidance provided in the Quality of Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="776c7-117">すべてが最適化され、ネットワーク、オーディオ ・ エクスペリエンスを向上させるためには、ビデオ、およびデスクトップの共有の機能強化にも直接変換します。</span><span class="sxs-lookup"><span data-stu-id="776c7-117">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="776c7-118">早い段階で品質の支持者を指名するを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="776c7-118">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="776c7-119">後、指定されている[体験レビュー ガイドの品質](https://aka.ms/qerguide)の内容を十分に理解する、開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="776c7-119">After being nominated, they should start to familiarize themselves with the content in the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

<!--ENDOFSECTION-->