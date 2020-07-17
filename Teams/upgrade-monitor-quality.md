---
title: ユーザーエクスペリエンスの品質 |Microsoft Teams |QoS |通話音質
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 管理者は、Microsoft Teams の品質および使用状況を監視するために必要なタスクとアクティビティについて知ることができます。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 843acff0dafc7cd5ad2b3fd63ccc009c64716b03
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085923"
---
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="d225d-103">QoE のレビュー ガイド</span><span class="sxs-lookup"><span data-stu-id="d225d-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="d225d-104">![アップグレード過程のオペレーショナルエクセレンスステージを強調した図](media/upgrade-banner-op-excellence.png "オペレーショナルエクセレンスステージに重点を置いたアップグレードの段階")</span><span class="sxs-lookup"><span data-stu-id="d225d-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="d225d-105">この記事は、Skype for Business から Teams へのアップグレードが完了したらすぐに、アップグレードの過程のオペレーショナルエクセレンスステージの一部です。</span><span class="sxs-lookup"><span data-stu-id="d225d-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

## <a name="improve-and-monitor-call-quality"></a><span data-ttu-id="d225d-106">通話品質の向上と監視</span><span class="sxs-lookup"><span data-stu-id="d225d-106">Improve and monitor call quality</span></span>

<span data-ttu-id="d225d-107">[チームの通話品質の向上と監視](monitor-call-quality-qos.md)。以下に示すように、ユーザーエクスペリエンスを向上させるための大きな影響を受ける主要な領域の一連のアクティビティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d225d-107">[Improve and monitor call quality for Teams](monitor-call-quality-qos.md) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="d225d-108">![レビュー中に確認する主要な領域の図。](media/plan-my-service-management-image2.png "音質のレビュー中に、音声、信頼性、ユーザー調査の結果について調べる主要な領域。")</span><span class="sxs-lookup"><span data-stu-id="d225d-108">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="d225d-109">ガイドで説明されている領域を継続的に評価してを修復するすることで、ユーザーエクスペリエンスに悪影響を及ぼす可能性を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="d225d-109">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="d225d-110">展開で生じる多くのユーザー エクスペリエンスに関する問題は、次のカテゴリにグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="d225d-110">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="d225d-111">不完全なファイアウォールまたはプロキシの構成</span><span class="sxs-lookup"><span data-stu-id="d225d-111">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="d225d-112">貧弱な Wi-Fi の有効範囲</span><span class="sxs-lookup"><span data-stu-id="d225d-112">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="d225d-113">不十分な帯域幅</span><span class="sxs-lookup"><span data-stu-id="d225d-113">Insufficient bandwidth</span></span>

- <span data-ttu-id="d225d-114">VPN</span><span class="sxs-lookup"><span data-stu-id="d225d-114">VPN</span></span>

- <span data-ttu-id="d225d-115">最適化されていない内蔵音声デバイスの使用</span><span class="sxs-lookup"><span data-stu-id="d225d-115">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="d225d-116">問題のあるサブネットまたはネットワーク デバイス</span><span class="sxs-lookup"><span data-stu-id="d225d-116">Problematic subnets or network devices</span></span>

<span data-ttu-id="d225d-117">[チームの通話品質の向上と監視](monitor-call-quality-qos.md)に関するガイダンスでは、説明されている各領域を報告して調査するための主要なツールとして、通話品質ダッシュボード (CQD) をオンラインで使用することに重点を置いています。音声に重点を置いて、導入と影響を最大限に高めます。</span><span class="sxs-lookup"><span data-stu-id="d225d-117">The guidance provided in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md) focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="d225d-118">音声エクスペリエンスを改善するためにネットワークに対して行われた最適化は、ビデオおよびデスクトップ共有を改善することにも直接転用されます。</span><span class="sxs-lookup"><span data-stu-id="d225d-118">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="d225d-119">品質チャンピオンをいち早く紹介することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d225d-119">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="d225d-120">推薦されたユーザーは、[チームの通話品質を向上させる](monitor-call-quality-qos.md)ために、コンテンツの理解を深めていく必要があります。</span><span class="sxs-lookup"><span data-stu-id="d225d-120">After being nominated, they should start to familiarize themselves with the content in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md).</span></span>

<!--ENDOFSECTION-->
