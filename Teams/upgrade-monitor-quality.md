---
title: ユーザー エクスペリエンスの品質 |Microsoft Teams |QoS |通話品質
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 管理者は、Microsoft Teams の品質と使用状況を監視するために必要なタスクとアクティビティについて学習できます。
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
ms.openlocfilehash: d57f01887961ad0c458b13db20ba79023272bcdf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808997"
---
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="7c18d-103">QoE のレビュー ガイド</span><span class="sxs-lookup"><span data-stu-id="7c18d-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="7c18d-104">![アップグレードの優れた運用段階を強調表示した図](media/upgrade-banner-op-excellence.png "アップグレードのプロセスのステージ。"オペレーショナル・アペレーショナル" ステージに重点を置いた")</span><span class="sxs-lookup"><span data-stu-id="7c18d-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="7c18d-105">この記事は、Skype for Business から Teams へのアップグレードが完了するとすぐに開始される、アップグレードの旅の"オペレーショナル・ディカリスト" ステージの一部です。</span><span class="sxs-lookup"><span data-stu-id="7c18d-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

## <a name="improve-and-monitor-call-quality"></a><span data-ttu-id="7c18d-106">通話品質の向上と監視</span><span class="sxs-lookup"><span data-stu-id="7c18d-106">Improve and monitor call quality</span></span>

<span data-ttu-id="7c18d-107">[Teams の](monitor-call-quality-qos.md) 通話品質の向上と監視には、以下に示す、ユーザー エクスペリエンスの向上に最も大きな影響を与える主要な領域の修復ガイダンスを評価して提供する一連のアクティビティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7c18d-107">[Improve and monitor call quality for Teams](monitor-call-quality-qos.md) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="7c18d-108">![レビュー中に調べる重要な領域の図。](media/plan-my-service-management-image2.png "エクスペリエンスの品質レビュー中に調べる重要な領域は、音声、信頼性、ユーザーアンケートの結果です。")</span><span class="sxs-lookup"><span data-stu-id="7c18d-108">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="7c18d-109">ガイドに記載されている領域を継続的に評価して修復することで、ユーザー エクスペリエンスに悪影響を与える可能性を減らします。</span><span class="sxs-lookup"><span data-stu-id="7c18d-109">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="7c18d-110">展開で生じる多くのユーザー エクスペリエンスに関する問題は、次のカテゴリにグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="7c18d-110">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="7c18d-111">不完全なファイアウォールまたはプロキシの構成</span><span class="sxs-lookup"><span data-stu-id="7c18d-111">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="7c18d-112">貧弱な Wi-Fi の有効範囲</span><span class="sxs-lookup"><span data-stu-id="7c18d-112">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="7c18d-113">不十分な帯域幅</span><span class="sxs-lookup"><span data-stu-id="7c18d-113">Insufficient bandwidth</span></span>

- <span data-ttu-id="7c18d-114">VPN</span><span class="sxs-lookup"><span data-stu-id="7c18d-114">VPN</span></span>

- <span data-ttu-id="7c18d-115">最適化されていない内蔵音声デバイスの使用</span><span class="sxs-lookup"><span data-stu-id="7c18d-115">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="7c18d-116">問題のあるサブネットまたはネットワーク デバイス</span><span class="sxs-lookup"><span data-stu-id="7c18d-116">Problematic subnets or network devices</span></span>

<span data-ttu-id="7c18d-117">[Teams](monitor-call-quality-qos.md)の通話品質の向上と監視に関するガイダンスでは、導入と影響を最大化するためにオーディオに重点を置いて、説明された各領域を報告および調査するための主要ツールとして通話品質ダッシュボード (CQD) Online を使用する方法に重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="7c18d-117">The guidance provided in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md) focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="7c18d-118">音声エクスペリエンスを改善するためにネットワークに対して行われた最適化は、ビデオおよびデスクトップ共有を改善することにも直接転用されます。</span><span class="sxs-lookup"><span data-stu-id="7c18d-118">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="7c18d-119">早い段階で品質チャンピオンを指名することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7c18d-119">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="7c18d-120">指名を受け、Teams の通話品質の向上と監視のコンテンツに慣れ [始める必要があります](monitor-call-quality-qos.md)。</span><span class="sxs-lookup"><span data-stu-id="7c18d-120">After being nominated, they should start to familiarize themselves with the content in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md).</span></span>

<!--ENDOFSECTION-->
