---
title: Skype for Business から Microsoft Teams にアップグレードする
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 自分の組織での Skype for Business から Microsoft Teams へのアップグレード手順を進めるために、成功実績のあるフレームワークを使用する
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: bfe9fb437be2df1c069c79d3c5281dbb121b4204
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2019
ms.locfileid: "29349078"
---
# <a name="skype-for-business-to-microsoft-teams-upgrade"></a><span data-ttu-id="0472d-103">Skype for Business から Microsoft Teams へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="0472d-103">Skype for Business to Microsoft Teams upgrade</span></span>

<span data-ttu-id="0472d-104">Microsoft のインテリジェント コミュニケーションのビジョンをサポートしている Microsoft Teams は、チームワークの中心的なハブとして、チャット、会議、通話、コラボレーション、アプリ統合、およびファイル ストレージをまとめ上げます。</span><span class="sxs-lookup"><span data-stu-id="0472d-104">Supporting Microsoft’s intelligent communications vision, Microsoft Teams is the central hub for teamwork, bringing together chat, meetings, calling, collaboration, app integration, and file storage.</span></span> <span data-ttu-id="0472d-105">既存の Skype for Business ユーザーである場合は、Microsoft Teams にアップグレードへの案内を受け取ります。アップグレードすることによって、Teams の完全に一式揃ったコミュニケーションおよびコラボレーションの機能を、単一のクライアント エクスペリエンスで活用することができます。</span><span class="sxs-lookup"><span data-stu-id="0472d-105">As an existing Skype for Business customer, you’re invited to upgrade to Microsoft Teams, to experience this full suite of communication and collaboration capabilities in a single client experience.</span></span>

<span data-ttu-id="0472d-106">アップグレード手順には時間がかかる場合もありますので、各手順において、適宜サポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="0472d-106">Your upgrade journey might take some time, and we’re here to support you every step of the way.</span></span> <span data-ttu-id="0472d-107">お客様が Teams の使用を開始したばかりの場合でも、既に Teams を Skype for Business と併用してる場合でも、またはアップグレードの準備が整っている場合でも、Microsoft はお客様の組織に対して適正なレベルのガイダンスを提供して、お客様の組織がさらに先の手順に進んで Teams から提供される価値を実感し始められるようになるように、尽力しています。</span><span class="sxs-lookup"><span data-stu-id="0472d-107">Whether you’re just getting started with Teams, already using Teams alongside Skype for Business, or ready to upgrade, we’re working hard to bring you the right level of guidance for your organization and encourage you to take the next steps to begin realizing the value Teams can offer your organization.</span></span>

<span data-ttu-id="0472d-108">中核的なコンセプト、フレームワーク、アップグレード パスを含む、Skype for Business から Teams へのアップグレード手順の概要については、この[概要](https://aka.ms/UpgradeOverview)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0472d-108">View this [overview](https://aka.ms/UpgradeOverview) for an introduction to the Skype for Business to Teams upgrade journey, including core concepts, framework, and upgrade paths.</span></span>

> [!Tip]
> <span data-ttu-id="0472d-109">Skype for Business から Microsoft Teams へのアップグレードについては、次のセッションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0472d-109">Watch the following session to learn about the Upgrade from Skype for Business to Microsoft Teams:</span></span>
> - [<span data-ttu-id="0472d-110">アップグレードの概要</span><span class="sxs-lookup"><span data-stu-id="0472d-110">Introduction to Upgrade</span></span>](https://aka.ms/teams-upgrade-intro)
> - [<span data-ttu-id="0472d-111">アップグレードの計画</span><span class="sxs-lookup"><span data-stu-id="0472d-111">Plan your upgrade</span></span>](https://aka.ms/teams-upgrade-plan)
> - [<span data-ttu-id="0472d-112">共存および相互運用性</span><span class="sxs-lookup"><span data-stu-id="0472d-112">Coexistence and Interoperability</span></span>](https://aka.ms/teams-upgrade-coexistence-interop)
> - [<span data-ttu-id="0472d-113">管理者のエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="0472d-113">Administrator experience</span></span>](https://aka.ms/teams-upgrade-admin)

## <a name="upgrade-journey-framework"></a><span data-ttu-id="0472d-114">アップグレード手順のフレームワーク</span><span class="sxs-lookup"><span data-stu-id="0472d-114">Upgrade journey framework</span></span>

<span data-ttu-id="0472d-115">お客様のアップグレード手順から試行錯誤を取り除くために、変更を推進するための成功実績のあるフレームワーク、組み込まれたガイダンス、ヒント、あらゆるリソースを活用しています。</span><span class="sxs-lookup"><span data-stu-id="0472d-115">To help take the guesswork out of your upgrade journey, we’ve employed a proven success framework for driving change, incorporating guidance, tips, and resources throughout.</span></span> <span data-ttu-id="0472d-116">各手順は、その前の手順を踏まえたものであるため、最適な結果を得るには、順序どおりに手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0472d-116">Each step builds on the previous one and for optimal results, we recommend following the steps in order.</span></span>

<span data-ttu-id="0472d-117">下記で説明したように、正常なアップグレードは、まず適切なチームが一丸となってプロジェクト ステークホルダーの段階に入り、次に対象範囲、目標、タイムラインを確定させるプロジェクト定義の段階に移行することによって、実行されます。</span><span class="sxs-lookup"><span data-stu-id="0472d-117">As illustrated below, a successful upgrade begins by bringing the right team together in the Project Stakeholder stage and then moving to Project Definition where the scope, goals, and timeline are solidified.</span></span> <span data-ttu-id="0472d-118">これにより、アップグレード手順のための強固な基礎が作り上げられます。</span><span class="sxs-lookup"><span data-stu-id="0472d-118">This helps create a solid foundation for your upgrade journey.</span></span> <span data-ttu-id="0472d-119">ここでは、展開と実装に移る前に、技術面の準備状況の段階_および_ユーザー準備状況の段階の両方に対する準備を行うことが重要です。</span><span class="sxs-lookup"><span data-stu-id="0472d-119">From there, it’s critical to prepare for both the Technical Readiness _and_ User Readiness stages before moving on to Deployment and Implementation.</span></span> <span data-ttu-id="0472d-120">大規模なロールアウトを行う前に準備状況を検証するためのパイロットの計画</span><span class="sxs-lookup"><span data-stu-id="0472d-120">Plan for a pilot to validate readiness before a broad rollout.</span></span> <span data-ttu-id="0472d-121">オペレーショナル エクセレンスの段階において最大のメリットを得られるように、品質を監視し、ユーザーの導入を加速化するための計画を確立します。</span><span class="sxs-lookup"><span data-stu-id="0472d-121">For maximum benefit during the Operational Excellence stage, establish a plan that monitors for quality and accelerates user adoption.</span></span>

> [!Tip]
> <span data-ttu-id="0472d-122">アップグレード手順全体をナビゲートするには、関連ページで下記のグラフィックを探して、プロセスにおける現在地を特定してください。</span><span class="sxs-lookup"><span data-stu-id="0472d-122">To help you navigate through your upgrade journey, look for this graphic on related pages to identify where you are in the process.</span></span> <span data-ttu-id="0472d-123">![お客様のプロジェクトが、適切なプロジェクトチームで、正常に完了するようにセットアップされていることを確認します。プロジェクトの範囲、目標、およびタイムラインを定義します。技術面およびユーザーの準備状況の両方を確認します。ロールアウト計画を実施します。最大の結果を得られるように機運を維持します。](media/upgrade-banner-main.png "お客様のプロジェクトが、適切なプロジェクトチームで、正常に完了するようにセットアップされていることを確認します。プロジェクトの範囲、目標、およびタイムラインを定義します。技術面およびユーザーの準備状況の両方を確認します。ロールアウト計画を実施します。最大の結果を得られるように機運を維持します。")</span><span class="sxs-lookup"><span data-stu-id="0472d-123">![Ensure your project is set up for success with the right project team. Define your project scope, goals, and timeline. Confirm both technical and user readiness. Execute your rollout plan. Maintain momentum to maximize results.](media/upgrade-banner-main.png "Ensure your project is set up for success with the right project team. Define your project scope, goals, and timeline. Confirm both technical and user readiness. Execute your rollout plan. Maintain momentum to maximize results.")</span></span>

## <a name="to-get-started"></a><span data-ttu-id="0472d-124">最初に行う操作</span><span class="sxs-lookup"><span data-stu-id="0472d-124">To get started...</span></span>

<span data-ttu-id="0472d-125">顧客が求めるものはさまざまであり、画一的なものではないということは承知しています。</span><span class="sxs-lookup"><span data-stu-id="0472d-125">We understand that customers don’t come one-size-fits-all.</span></span> <span data-ttu-id="0472d-126">柔軟性を追加するために、フレームワークを Upgrade Basic と Upgrade Pro という 2 つのパスに編成しました。</span><span class="sxs-lookup"><span data-stu-id="0472d-126">For added flexibility, we’ve organized the framework into two paths: Upgrade Basic and Upgrade Pro.</span></span> <span data-ttu-id="0472d-127">お客様の組織のニーズに最も適した移行手順を選択してださい。</span><span class="sxs-lookup"><span data-stu-id="0472d-127">Choose the journey that best meets your organization’s needs.</span></span>

<span data-ttu-id="0472d-128">以下のオプションの 1 つを選択または両方を検討して、最適なパスを決定します。</span><span class="sxs-lookup"><span data-stu-id="0472d-128">Select one of the options below or explore both to determine the optimal path for you.</span></span> <span data-ttu-id="0472d-129">今後オンラインで詳細情報が提供されますので、お客様の組織が Teams への移行手順を進めていく中で再度チェックしてください。</span><span class="sxs-lookup"><span data-stu-id="0472d-129">More information will be coming online over time, so check back as your organization continues its journey to Teams.</span></span> <span data-ttu-id="0472d-130">お客様のアップグレード パスについて、またどのような内容のガイダンスを追加すれば役に立つかについて、Microsoft がより理解することができるように、お手数ですが<a href="https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR-5Km9f5gDtNpbRf-TAnN_NUMzhYOUlNR1QzS1hSS0ZXRzAxVEVVVjg1Mi4u" target="_blank">フィードバックを提供</a>してください。</span><span class="sxs-lookup"><span data-stu-id="0472d-130">To help us better understand your upgrade path and what additional guidance might be helpful, take a moment to <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR-5Km9f5gDtNpbRf-TAnN_NUMzhYOUlNR1QzS1hSS0ZXRzAxVEVVVjg1Mi4u" target="_blank">share your feedback</a>.</span></span>

<div class="mx-tableFixed">
<table>
<tbody>
<tr><td><a href="https://docs.microsoft.com/MicrosoftTeams/upgrade-basic"><img src="media/upgrade-to-teams-upgrade-basic-icon.png" alt="Designed for smaller organizations or those with simple deployments of Skype for Business (IM only or IM plus basic meeting functionality), the Upgrade Basic checklist steps you through activities designed to quickly move your entire organization to Teams."></a></td>
<td>
<a href="https://docs.microsoft.com/MicrosoftTeams/upgrade-pro"><img src="media/upgrade-to-teams-upgrade-pro-icon.png" alt="Designed for enterprise customers, or those with more tailored deployments such as hybrid or voice, the Upgrade Pro guide details technical and user readiness activities to better accommodate the unique attributes of an organization."></a></td></tr>
</tbody></table>
</div>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]
