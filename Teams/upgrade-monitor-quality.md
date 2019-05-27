---
title: ユーザーエクスペリエンスの品質 |Microsoft Teams |QoS |通話音質
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
description: Microsoft Teams の品質と使用状況を監視するために必要なタスクとアクティビティ
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a64e374e674fed4c6efe267d6559a260dce960e1
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "34432913"
---
<span data-ttu-id="eeaef-103">![アップグレード過程のオペレーショナルエクセレンスステージを強調した図](media/upgrade-banner-op-excellence.png "オペレーショナルエクセレンスステージに重点を置いたアップグレードの段階")</span><span class="sxs-lookup"><span data-stu-id="eeaef-103">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="eeaef-104">この記事は、Skype for Business から Teams へのアップグレードが完了したらすぐに、アップグレードの過程のオペレーショナルエクセレンスステージの一部です。</span><span class="sxs-lookup"><span data-stu-id="eeaef-104">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="eeaef-105">QoE のレビュー ガイド</span><span class="sxs-lookup"><span data-stu-id="eeaef-105">Quality of Experience Review Guide</span></span>

<span data-ttu-id="eeaef-106">[品質経験レビューガイド](https://aka.ms/qerguide)には、以下に示すように、ユーザーエクスペリエンスを向上させるための最も大きな影響を受ける主要な領域の一連のアクティビティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="eeaef-106">The [Quality of Experience Review Guide](https://aka.ms/qerguide) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="eeaef-107">![レビュー中に確認する主要な領域の図。](media/plan-my-service-management-image2.png "音質のレビュー中に、音声、信頼性、ユーザー調査の結果について調べる主要な領域。")</span><span class="sxs-lookup"><span data-stu-id="eeaef-107">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="eeaef-108">ガイドで説明されている領域を継続的に評価してを修復するすることで、ユーザーエクスペリエンスに悪影響を及ぼす可能性を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="eeaef-108">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="eeaef-109">展開で生じる多くのユーザー エクスペリエンスに関する問題は、次のカテゴリにグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="eeaef-109">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="eeaef-110">不完全なファイアウォールまたはプロキシの構成</span><span class="sxs-lookup"><span data-stu-id="eeaef-110">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="eeaef-111">貧弱な Wi-Fi の有効範囲</span><span class="sxs-lookup"><span data-stu-id="eeaef-111">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="eeaef-112">不十分な帯域幅</span><span class="sxs-lookup"><span data-stu-id="eeaef-112">Insufficient bandwidth</span></span>

- <span data-ttu-id="eeaef-113">VPN</span><span class="sxs-lookup"><span data-stu-id="eeaef-113">VPN</span></span>

- <span data-ttu-id="eeaef-114">最適化されていない内蔵音声デバイスの使用</span><span class="sxs-lookup"><span data-stu-id="eeaef-114">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="eeaef-115">問題のあるサブネットまたはネットワーク デバイス</span><span class="sxs-lookup"><span data-stu-id="eeaef-115">Problematic subnets or network devices</span></span>

<span data-ttu-id="eeaef-116">品質評価ガイドで提供されているガイダンスでは、通話品質ダッシュボード (CQD) をオンラインで使用して、説明されている各領域のレポートと調査を行うことができます。これには、オーディオに焦点を当てて、導入とインパクトを最大限に活用します。</span><span class="sxs-lookup"><span data-stu-id="eeaef-116">The guidance provided in the Quality of Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="eeaef-117">音声エクスペリエンスを改善するためにネットワークに対して行われた最適化は、ビデオおよびデスクトップ共有を改善することにも直接転用されます。</span><span class="sxs-lookup"><span data-stu-id="eeaef-117">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="eeaef-118">品質チャンピオンをいち早く紹介することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="eeaef-118">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="eeaef-119">推薦されたら、[経験レビューガイド](https://aka.ms/qerguide)のコンテンツについて理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="eeaef-119">After being nominated, they should start to familiarize themselves with the content in the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

<!--ENDOFSECTION-->
