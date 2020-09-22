---
title: 管理コンソールで Teams の医療テンプレートを使用する
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 管理コンソールで Microsoft Teams テンプレートを使用すると、設定、チャネル、アプリの定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 93de98eb61f503467f7b9de218a10982402eeb41
ms.sourcegitcommit: af9f96010460f9323db84912fe143aa0750ac798
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171091"
---
# <a name="use-teams-healthcare-templates-in-the-admin-console"></a><span data-ttu-id="6a8e2-103">管理コンソールで Teams の医療テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="6a8e2-103">Use Teams healthcare templates in the admin console</span></span>

[!INCLUDE [template](../../includes/preview-feature.md)]

<span data-ttu-id="6a8e2-104">Microsoft Teams のテンプレートを使用すると、設定、チャネル、プリインストールされているアプリに定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="6a8e2-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="6a8e2-105">医療機関の場合、テンプレートは、ユーザーが効率的にチームを効果的に活用できるようにするための構造を提供するため、特に強力です。</span><span class="sxs-lookup"><span data-stu-id="6a8e2-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to best leverage Teams effectively.</span></span> <span data-ttu-id="6a8e2-106">テンプレートを使用すると、管理者は組織全体で一貫したチームを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="6a8e2-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="6a8e2-107">この記事は、医療組織全体で複数のチームの計画、展開、管理を担当している場合に使います。</span><span class="sxs-lookup"><span data-stu-id="6a8e2-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your Healthcare organization.</span></span>

<span data-ttu-id="6a8e2-108">現時点では、さまざまな状況に応じて利用できる、2つのファーストパーティの医療用テンプレートが提供されています。</span><span class="sxs-lookup"><span data-stu-id="6a8e2-108">We currently offer two first-party healthcare templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="6a8e2-109">チームテンプレート全般の詳細については、「 [管理コンソールで Teams テンプレートの概要](../../get-started-with-teams-templates-in-the-admin-console.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a8e2-109">To learn more about team templates in general, please see [Get started with Teams templates in the admin console](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="collaborate-on-patient-care"></a><span data-ttu-id="6a8e2-110">治療での共同作業</span><span class="sxs-lookup"><span data-stu-id="6a8e2-110">Collaborate on patient care</span></span>

 <span data-ttu-id="6a8e2-111">ワード、ポッド、または部門内での医療通信と共同作業を合理化します。</span><span class="sxs-lookup"><span data-stu-id="6a8e2-111">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="6a8e2-112">このテンプレートを使用すると、患者の管理や、補助の運用ニーズを簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6a8e2-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span>

| <span data-ttu-id="6a8e2-113">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="6a8e2-113">Base template type</span></span> |<span data-ttu-id="6a8e2-114">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="6a8e2-114">baseTemplateId</span></span>| <span data-ttu-id="6a8e2-115">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="6a8e2-115">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="6a8e2-116">治療での共同作業</span><span class="sxs-lookup"><span data-stu-id="6a8e2-116">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="6a8e2-117">チャネル</span><span class="sxs-lookup"><span data-stu-id="6a8e2-117">Channels:</span></span><ul><li><span data-ttu-id="6a8e2-118">一般</span><span class="sxs-lookup"><span data-stu-id="6a8e2-118">General</span></span></li><li><span data-ttu-id="6a8e2-119">お知らせ</span><span class="sxs-lookup"><span data-stu-id="6a8e2-119">Announcements</span></span></li><li><span data-ttu-id="6a8e2-120">Huddles</span><span class="sxs-lookup"><span data-stu-id="6a8e2-120">Huddles</span></span></li><li><span data-ttu-id="6a8e2-121">切り下げ</span><span class="sxs-lookup"><span data-stu-id="6a8e2-121">Rounds</span></span></li><li><span data-ttu-id="6a8e2-122">割り当てる</span><span class="sxs-lookup"><span data-stu-id="6a8e2-122">Staffing</span></span></li><li><span data-ttu-id="6a8e2-123">トレーニング</span><span class="sxs-lookup"><span data-stu-id="6a8e2-123">Training</span></span></li></ul> <span data-ttu-id="6a8e2-124">アプリ</span><span class="sxs-lookup"><span data-stu-id="6a8e2-124">Apps:</span></span> <ul><li><span data-ttu-id="6a8e2-125">ウィキ</span><span class="sxs-lookup"><span data-stu-id="6a8e2-125">Wiki</span></span></li>|
||||

## <a name="hospital"></a><span data-ttu-id="6a8e2-126">病院</span><span class="sxs-lookup"><span data-stu-id="6a8e2-126">Hospital</span></span>

<span data-ttu-id="6a8e2-127">病院内の複数の wards、ポッド、部門間のコミュニケーションとコラボレーションを合理化します。</span><span class="sxs-lookup"><span data-stu-id="6a8e2-127">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="6a8e2-128">このテンプレートには、病院の操作のための基本チャネルのセットが含まれています。また、特別な機能を追加して、専門分野を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="6a8e2-128">This template includes a set of base channels for hospital operations, and can be self extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="6a8e2-129">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="6a8e2-129">Base template type</span></span> |<span data-ttu-id="6a8e2-130">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="6a8e2-130">baseTemplateId</span></span> | <span data-ttu-id="6a8e2-131">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="6a8e2-131">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="6a8e2-132">病院</span><span class="sxs-lookup"><span data-stu-id="6a8e2-132">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="6a8e2-133">チャネル</span><span class="sxs-lookup"><span data-stu-id="6a8e2-133">Channels:</span></span> <ul><li><span data-ttu-id="6a8e2-134">一般</span><span class="sxs-lookup"><span data-stu-id="6a8e2-134">General</span></span><li><span data-ttu-id="6a8e2-135">お知らせ</span><span class="sxs-lookup"><span data-stu-id="6a8e2-135">Announcements</span></span></li><li><span data-ttu-id="6a8e2-136">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="6a8e2-136">Compliance</span></span></li><li><span data-ttu-id="6a8e2-137">Custodial</span><span class="sxs-lookup"><span data-stu-id="6a8e2-137">Custodial</span></span></li><li><span data-ttu-id="6a8e2-138">人事</span><span class="sxs-lookup"><span data-stu-id="6a8e2-138">Human resources</span></span></li><li><span data-ttu-id="6a8e2-139">薬</span><span class="sxs-lookup"><span data-stu-id="6a8e2-139">Pharmacy</span></span></li></ul> <span data-ttu-id="6a8e2-140">アプリ</span><span class="sxs-lookup"><span data-stu-id="6a8e2-140">Apps:</span></span> <ul><li><span data-ttu-id="6a8e2-141">ウィキ</span><span class="sxs-lookup"><span data-stu-id="6a8e2-141">Wiki</span></span></li></ul>|
||||

## <a name="related-topics"></a><span data-ttu-id="6a8e2-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a8e2-142">Related topics</span></span>

[<span data-ttu-id="6a8e2-143">Teams のテンプレートの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="6a8e2-143">Get started with Teams templates</span></span>](../../get-started-with-teams-templates-in-the-admin-console.md)
