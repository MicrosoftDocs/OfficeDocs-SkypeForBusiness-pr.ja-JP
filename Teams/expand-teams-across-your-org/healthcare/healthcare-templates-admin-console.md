---
title: 管理センターで Teams の医療テンプレートを使用する
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 管理センターで Microsoft Teams テンプレートを使用すると、設定、チャネル、アプリの定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 102c9db47ba9a79acf64338d2fab0cb1ddc49392
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790429"
---
# <a name="use-teams-healthcare-templates-in-the-admin-center"></a><span data-ttu-id="47a42-103">管理センターで Teams の医療テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="47a42-103">Use Teams healthcare templates in the admin center</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="47a42-104">Microsoft Teams のテンプレートを使用すると、設定、チャネル、プリインストールされているアプリに定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="47a42-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="47a42-105">医療機関の場合、テンプレートは、ユーザーが効率的にチームを効果的に活用できるようにするための構造を提供するため、特に強力です。</span><span class="sxs-lookup"><span data-stu-id="47a42-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to best leverage Teams effectively.</span></span> <span data-ttu-id="47a42-106">テンプレートを使用すると、管理者は組織全体で一貫したチームを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="47a42-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="47a42-107">この記事は、医療組織全体で複数のチームの計画、展開、管理を担当している場合に使います。</span><span class="sxs-lookup"><span data-stu-id="47a42-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your Healthcare organization.</span></span>

<span data-ttu-id="47a42-108">現時点では、さまざまな状況に応じて利用できる、2つのファーストパーティの医療用テンプレートが提供されています。</span><span class="sxs-lookup"><span data-stu-id="47a42-108">We currently offer two first-party healthcare templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="47a42-109">チームテンプレート全般の詳細については、「 [管理センターでチームテンプレートの概要](../../get-started-with-teams-templates-in-the-admin-console.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47a42-109">To learn more about team templates in general, see [Get started with Teams templates in the admin center](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="collaborate-on-patient-care"></a><span data-ttu-id="47a42-110">治療での共同作業</span><span class="sxs-lookup"><span data-stu-id="47a42-110">Collaborate on patient care</span></span>

 <span data-ttu-id="47a42-111">ワード、ポッド、または部門内での医療通信と共同作業を合理化します。</span><span class="sxs-lookup"><span data-stu-id="47a42-111">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="47a42-112">このテンプレートを使用すると、患者の管理や操作上のニーズを容易にすることができます。</span><span class="sxs-lookup"><span data-stu-id="47a42-112">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="47a42-113">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="47a42-113">Base template type</span></span> |<span data-ttu-id="47a42-114">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="47a42-114">baseTemplateId</span></span>| <span data-ttu-id="47a42-115">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="47a42-115">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="47a42-116">治療での共同作業</span><span class="sxs-lookup"><span data-stu-id="47a42-116">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="47a42-117">チャネル</span><span class="sxs-lookup"><span data-stu-id="47a42-117">Channels:</span></span><ul><li><span data-ttu-id="47a42-118">一般</span><span class="sxs-lookup"><span data-stu-id="47a42-118">General</span></span></li><li><span data-ttu-id="47a42-119">お知らせ</span><span class="sxs-lookup"><span data-stu-id="47a42-119">Announcements</span></span></li><li><span data-ttu-id="47a42-120">Huddles</span><span class="sxs-lookup"><span data-stu-id="47a42-120">Huddles</span></span></li><li><span data-ttu-id="47a42-121">切り下げ</span><span class="sxs-lookup"><span data-stu-id="47a42-121">Rounds</span></span></li><li><span data-ttu-id="47a42-122">割り当てる</span><span class="sxs-lookup"><span data-stu-id="47a42-122">Staffing</span></span></li><li><span data-ttu-id="47a42-123">トレーニング</span><span class="sxs-lookup"><span data-stu-id="47a42-123">Training</span></span></li></ul> <span data-ttu-id="47a42-124">アプリ</span><span class="sxs-lookup"><span data-stu-id="47a42-124">Apps:</span></span> <ul><li><span data-ttu-id="47a42-125">ウィキ</span><span class="sxs-lookup"><span data-stu-id="47a42-125">Wiki</span></span></li>|
||||

## <a name="hospital"></a><span data-ttu-id="47a42-126">病院</span><span class="sxs-lookup"><span data-stu-id="47a42-126">Hospital</span></span>

<span data-ttu-id="47a42-127">病院内の複数の wards、ポッド、部門間のコミュニケーションとコラボレーションを合理化します。</span><span class="sxs-lookup"><span data-stu-id="47a42-127">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="47a42-128">このテンプレートには、病院の操作に使用する基本チャネルのセットが含まれており、それを自己拡張して専門分野や臨時のものを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="47a42-128">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="47a42-129">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="47a42-129">Base template type</span></span> |<span data-ttu-id="47a42-130">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="47a42-130">baseTemplateId</span></span> | <span data-ttu-id="47a42-131">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="47a42-131">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="47a42-132">病院</span><span class="sxs-lookup"><span data-stu-id="47a42-132">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="47a42-133">チャネル</span><span class="sxs-lookup"><span data-stu-id="47a42-133">Channels:</span></span> <ul><li><span data-ttu-id="47a42-134">一般</span><span class="sxs-lookup"><span data-stu-id="47a42-134">General</span></span><li><span data-ttu-id="47a42-135">お知らせ</span><span class="sxs-lookup"><span data-stu-id="47a42-135">Announcements</span></span></li><li><span data-ttu-id="47a42-136">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="47a42-136">Compliance</span></span></li><li><span data-ttu-id="47a42-137">Custodial</span><span class="sxs-lookup"><span data-stu-id="47a42-137">Custodial</span></span></li><li><span data-ttu-id="47a42-138">人事</span><span class="sxs-lookup"><span data-stu-id="47a42-138">Human resources</span></span></li><li><span data-ttu-id="47a42-139">薬</span><span class="sxs-lookup"><span data-stu-id="47a42-139">Pharmacy</span></span></li></ul> <span data-ttu-id="47a42-140">アプリ</span><span class="sxs-lookup"><span data-stu-id="47a42-140">Apps:</span></span> <ul><li><span data-ttu-id="47a42-141">ウィキ</span><span class="sxs-lookup"><span data-stu-id="47a42-141">Wiki</span></span></li></ul>|
||||

## <a name="related-topics"></a><span data-ttu-id="47a42-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="47a42-142">Related topics</span></span>

[<span data-ttu-id="47a42-143">Teams のテンプレートの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="47a42-143">Get started with Teams templates</span></span>](../../get-started-with-teams-templates-in-the-admin-console.md)
