---
title: ダイヤル プランについて
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.dialplans.overview
- Calling Plans
description: 'Teams で利用できるダイヤル通話プランの種類 (PSTN 通話ダイヤルプラン) と、組織に合わせて選ぶ方法について説明します。  '
ms.openlocfilehash: ddd2de412d0ddd00135f9b095eb2d14c8fc4c922
ms.sourcegitcommit: 91f6db3cdb4f2b7761d2b21f0f4eef405edacd5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "45153579"
---
# <a name="what-are-dial-plans"></a><span data-ttu-id="f7c54-103">ダイヤル プランについて</span><span class="sxs-lookup"><span data-stu-id="f7c54-103">What are dial plans?</span></span>

<span data-ttu-id="f7c54-104">[] ダイヤル プランは、個別のユーザーによってダイヤルされた電話番号を、通話承認と通話ルーティングの目的で別の形式 (通常は E.164) に変換する、正規化ルールの名前付きのセットです。</span><span class="sxs-lookup"><span data-stu-id="f7c54-104">A dial plan is a named set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="f7c54-105">ダイヤル プランは、さまざまな形式で表される電話番号が別の 1 つの形式にどのように変換されるかを定義する 1 つ以上の正規化ルールで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f7c54-105">A dial plan consists of one or more normalization rules that define how phone numbers expressed in various formats are translated to an alternate format.</span></span> <span data-ttu-id="f7c54-106">同じダイヤル文字列が、ダイヤル プランによって異なる形で解釈、変換される可能性があるため、指定されたユーザーに割り当てられているダイヤル プランに応じて、同じダイヤル番号が異なる形で変換、ルーティングされることがあります。</span><span class="sxs-lookup"><span data-stu-id="f7c54-106">The same dial string may be interpreted and translated differently in different dial plans, so depending on which dial plan is assigned to a given user, the same dialed number may be translated and routed differently.</span></span> <span data-ttu-id="f7c54-107">最大1000のテナントダイヤルプランを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7c54-107">There can be a maximum of 1,000 tenant dial plans.</span></span>

<span data-ttu-id="f7c54-108">テナントのダイヤル プランを作成および管理する場合は「[ダイヤル プランを作成および管理する](create-and-manage-dial-plans.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f7c54-108">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage tenant dial plans.</span></span>

## <a name="tenant-dial-plan-scope"></a><span data-ttu-id="f7c54-109">テナント ダイヤル プランのスコープ</span><span class="sxs-lookup"><span data-stu-id="f7c54-109">Tenant dial plan scope</span></span>

<span data-ttu-id="f7c54-110">ダイヤル プランのスコープによって、ダイヤル プランを適用できる階層レベルが決まります。</span><span class="sxs-lookup"><span data-stu-id="f7c54-110">A dial plan's scope determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="f7c54-111">クライアントは、ユーザーが Teams にサインインしたときに自動的に提供されるプロビジョニング設定を通じて、適切なダイヤルプランを取得します。</span><span class="sxs-lookup"><span data-stu-id="f7c54-111">Clients get the appropriate dial plan through provisioning settings that are automatically provided when users sign in to Teams.</span></span> <span data-ttu-id="f7c54-112">管理者は、Microsoft Teams 管理センターまたはリモート PowerShell を使用して、ダイヤルプランのスコープレベルを管理して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f7c54-112">As an admin, you can manage and assign dial plan scope levels by using the Microsoft Teams admin center or Remote PowerShell.</span></span>

<span data-ttu-id="f7c54-113">Teams には、サービス範囲とテナント範囲 (組織向け) という2種類のダイヤルプランがあります。</span><span class="sxs-lookup"><span data-stu-id="f7c54-113">In Teams, there are two types of dial plans: service-scoped and tenant-scoped (which is for your organization).</span></span> <span data-ttu-id="f7c54-114">電話システムを利用できる国または地域ごとに、サービス範囲のダイヤルプランが定義されます。</span><span class="sxs-lookup"><span data-stu-id="f7c54-114">A service-scoped dial plan is defined for every country or region where Phone System is available.</span></span> <span data-ttu-id="f7c54-115">各ユーザーには、ユーザーに割り当てられている使用場所と一致するサービス国のダイヤルプランが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f7c54-115">Each user is automatically assigned the service country dial plan that matches the usage location assigned to the user.</span></span> <span data-ttu-id="f7c54-116">サービス国のダイヤルプランを変更することはできませんが、テナントのスコープを設定したダイヤルプランを作成することができます。これにより、サービス国のダイヤルプランが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="f7c54-116">You can't change the service country dial plan, but you can create tenant scoped dial plans, which augment the service country dial plan.</span></span> <span data-ttu-id="f7c54-117">お客様は、お客様がプロビジョニングされた「有効なダイヤルプラン」を取得します。これは、サービス国のダイヤルプランと適切にスコープ指定されたテナントダイヤルプランの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="f7c54-117">As clients are provisioned, they obtain an "effective dial plan," which is a combination of the service country dial plan and the appropriately scoped tenant dial plan.</span></span> <span data-ttu-id="f7c54-118">したがって、テナントダイヤルプランでは、サービス国のダイヤルプランに既に存在する可能性があるため、すべての正規化ルールを定義する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f7c54-118">Therefore, it's not necessary to define all normalization rules in tenant dial plans as they might already exist in the service country dial plan.</span></span>

<span data-ttu-id="f7c54-119">テナントのダイヤルプランは、さらに2つのスコープ (テナントスコープまたはユーザースコープ) に分けることができます。</span><span class="sxs-lookup"><span data-stu-id="f7c54-119">Tenant dial plans can be further broken into two scopes - tenant-scope or user-scope.</span></span> <span data-ttu-id="f7c54-120">テナントがユーザー範囲のダイヤルプランを定義して割り当てる場合、そのユーザーは、ユーザーのサービス国ダイヤルプランと割り当てられたユーザーダイヤルプランの有効なダイヤルプランでプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="f7c54-120">If a tenant defines and assigns a user-scoped dial plan, that user will be provisioned with an effective dial plan of the user's service country dial plan and the assigned user dial plan.</span></span> <span data-ttu-id="f7c54-121">テナントがテナント範囲のダイヤルプランを定義していても、ユーザーを対象範囲としたダイヤルプランが割り当てられていない場合、そのユーザーは、ユーザーのサービス国ダイヤルプランとテナントダイヤルプランの有効なダイヤルプランでプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="f7c54-121">If a tenant defines a tenant-scoped dial plan but doesn't assign a user-scoped dial plan, then that user will be provisioned with an effective dial plan of the user's service country dial plan and the tenant dial plan.</span></span>

<span data-ttu-id="f7c54-122">Teams のダイヤルプランの継承モデルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f7c54-122">The following is the inheritance model of dial plans in Teams.</span></span>

![チームでのダイヤルプランの継承方法](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

<span data-ttu-id="f7c54-124">次に、考えられる有効なダイヤル プランを示します。</span><span class="sxs-lookup"><span data-stu-id="f7c54-124">The following are the possible effective dial plans:</span></span>

 <span data-ttu-id="f7c54-125">**サービス国**テナントを対象としたダイヤルプランが定義されておらず、テナントのユーザーを対象範囲としたダイヤルプランがプロビジョニングされたユーザーに割り当てられていない場合、ユーザーは使用場所に関連付けられたサービス国にマッピングされた有効なダイヤルプランを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f7c54-125">**Service Country** If no tenant scoped dial plan is defined and no tenant user scoped dial plan is assigned to the provisioned user, the user will receive an effective dial plan mapped to the service country associated with their usage location.</span></span>

 <span data-ttu-id="f7c54-126">**テナントのグローバルサービス国**テナントのユーザーダイヤルプランが定義されていても、ユーザーに割り当てられていない場合、プロビジョニングされたユーザーには、結合されたテナントダイヤルプランと、その使用場所に関連付けられたサービス国のダイヤルプランで構成される有効なダイヤルプランが適用されます。</span><span class="sxs-lookup"><span data-stu-id="f7c54-126">**Tenant Global - Service Country** If a tenant user dial plan is defined but not assigned to a user, the provisioned user will receive an effective dial plan consisting of a merged tenant dial plan and the service country dial plan associated with their usage location.</span></span>

 <span data-ttu-id="f7c54-127">**テナントのユーザーサービス国**テナントのユーザーダイヤルプランが定義され、ユーザーに割り当てられている場合、プロビジョニングされたユーザーには、結合されたテナントのユーザーダイヤルプランと、その使用場所に関連付けられたサービス国のダイヤルプランで構成される有効なダイヤルプランが取得されます。</span><span class="sxs-lookup"><span data-stu-id="f7c54-127">**Tenant User - Service Country** If a tenant user dial plan is defined and assigned to a user, the provisioned user will receive an effective dial plan consisting of the merged tenant user dial plan and the service country dial plan associated with their usage location.</span></span>

<span data-ttu-id="f7c54-128">テナントのダイヤル プランを作成する場合は「[ダイヤル プランを作成および管理する](create-and-manage-dial-plans.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f7c54-128">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.</span></span>

> [!NOTE]
> <span data-ttu-id="f7c54-129">ダイヤルプランの正規化ルールがダイヤル番号に適用されていない場合でも、ダイヤルされた文字列は "+ CC" の先頭に正規化されます。これは、ダイヤルユーザーの使用場所の国コードです。</span><span class="sxs-lookup"><span data-stu-id="f7c54-129">In the scenario where no dial plan normalization rules apply to a dialed number, the dialed string is still normalized to prepend "+CC" where CC is the country code of the dialing user's usage location.</span></span> <span data-ttu-id="f7c54-130">これは、通話プラン、ダイレクトルーティング、PSTN 会議のダイヤルアウトシナリオに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f7c54-130">This applies to Calling Plans, Direct Routing and PSTN Conference dial-out scenarios.</span></span>

## <a name="planning-for-tenant-dial-plans"></a><span data-ttu-id="f7c54-131">テナント ダイヤル プランの計画</span><span class="sxs-lookup"><span data-stu-id="f7c54-131">Planning for tenant dial plans</span></span>

<span data-ttu-id="f7c54-132">カスタム ダイヤル プランを計画するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7c54-132">To plan custom dial plans, follow these steps:</span></span>

- <span data-ttu-id="f7c54-p106">**手順 1** ユーザーのダイヤル エクスペリエンスを高めるためにカスタム ダイヤル プランが必要かどうかを決定します。通常は、内線または省略された国内ダイヤルなど、E.164 以外のダイヤルに対応する場合に必要となります。</span><span class="sxs-lookup"><span data-stu-id="f7c54-p106">**Step 1** Decide whether a custom dial plan is needed to enhance the user dialing experience. Typically, the need for one would be to support non-E.164 dialing, such as extensions or abbreviated national dialing.</span></span>

- <span data-ttu-id="f7c54-p107">**手順 2** テナント グローバルまたはテナント ユーザー スコープのダイヤル プランのどちらが必要か、または両方とも必要であるかを決定します。ユーザーに複数のローカル ダイヤル要件がある場合は、ユーザー スコープのダイヤル プランが必要となります。</span><span class="sxs-lookup"><span data-stu-id="f7c54-p107">**Step 2** Determine whether tenant global or tenant user scoped dial plans are needed, or both. User scoped dial plans are needed if users have different local dialing requirements.</span></span>

- <span data-ttu-id="f7c54-p108">**手順 3** 各必須ダイヤル プランに対応する有効な番号バターンを特定します。サービス レベル国のダイヤル プランで定義されていない番号パターンのみが必要となります。</span><span class="sxs-lookup"><span data-stu-id="f7c54-p108">**Step 3** Identify valid number patterns for each required dial plan. Only the number patterns that are not defined in the service level country dial plans are required.</span></span>

- <span data-ttu-id="f7c54-p109">**手順 4** ダイヤル プランの名前付けについて組織全体のスキームを策定します。標準的な名前付けスキームを採用することにより、組織全体にわたり一貫した方針を実現でき、メンテナンスや更新作業が簡素化されます。</span><span class="sxs-lookup"><span data-stu-id="f7c54-p109">**Step 4** Develop an organization-wide scheme for naming dial plans. Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>


## <a name="creating-your-new-tenant-dial-plan"></a><span data-ttu-id="f7c54-141">テナント ダイヤル プランの新規作成</span><span class="sxs-lookup"><span data-stu-id="f7c54-141">Creating your new tenant dial plan</span></span>

<span data-ttu-id="f7c54-142">ダイヤル プランを新規作成する場合、必要な情報を把握しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7c54-142">When you create a new dial plan, you must put in the information that is required.</span></span>

### <a name="name-and-simple-name"></a><span data-ttu-id="f7c54-143">名前と簡易名</span><span class="sxs-lookup"><span data-stu-id="f7c54-143">Name and simple name</span></span>

<span data-ttu-id="f7c54-144">ユーザーダイヤルプランの場合は、ダイヤルプランを割り当てるユーザーを識別するわかりやすい名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7c54-144">For user dial plans, you should specify a descriptive name that identifies the users to which the dial plan will be assigned.</span></span> <span data-ttu-id="f7c54-145">ダイヤルプランの簡易名には、ダイヤルプラン名から派生した文字列が事前に入力されています。</span><span class="sxs-lookup"><span data-stu-id="f7c54-145">The dial plan Simple Name is pre-populated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="f7c54-146">[単純名] フィールドは編集可能で、ダイヤル プラン用のより説明的な名前付け規則を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="f7c54-146">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="f7c54-147">[単純名] の値は空にすることはできず、一意でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="f7c54-147">The Simple Name value cannot be empty and must be unique.</span></span> <span data-ttu-id="f7c54-148">最適な方法は、組織全体の名前付け規則を作成してから、その規則の一貫性をすべてのサイトとユーザーに使用することです。</span><span class="sxs-lookup"><span data-stu-id="f7c54-148">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

### <a name="description"></a><span data-ttu-id="f7c54-149">説明</span><span class="sxs-lookup"><span data-stu-id="f7c54-149">Description</span></span>

<span data-ttu-id="f7c54-150">地理的な場所または対応するダイヤル プランが適用されるユーザーのグループに関する一般的で認識可能な名前を入力することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f7c54-150">We recommend that you type the common, recognizable name of the geographic location or group of users to which the corresponding dial plan applies.</span></span>

### <a name="external-access-prefix"></a><span data-ttu-id="f7c54-151">外部アクセス プレフィックス</span><span class="sxs-lookup"><span data-stu-id="f7c54-151">External access prefix</span></span>
<span data-ttu-id="f7c54-152"><a name="bkexternalprefix"> </a></span><span class="sxs-lookup"><span data-stu-id="f7c54-152"><a name="bkexternalprefix"> </a></span></span>

<span data-ttu-id="f7c54-153">ユーザーが外線につなぐために 1 つ以上の追加の先頭数字 (9 など) をダイヤルする必要がある場合は、最大 4 文字 (#、\*、0～9) の外部アクセス プレフィックスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f7c54-153">You can specify an external access prefix of up to four characters (#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

> [!NOTE]
> <span data-ttu-id="f7c54-154">外部アクセス プレフィックスを指定する場合、プレフィックスを適応させるための正規化ルールを追加で作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f7c54-154">If you specify an external access prefix, you don't need to create an additional normalization rule to accommodate the prefix.</span></span>

<span data-ttu-id="f7c54-155">テナントのダイヤル プランを作成する場合は「[ダイヤル プランを作成および管理する](create-and-manage-dial-plans.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f7c54-155">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.</span></span>

## <a name="normalization-rules"></a><span data-ttu-id="f7c54-156">正規化ルール</span><span class="sxs-lookup"><span data-stu-id="f7c54-156">Normalization rules</span></span>
<span data-ttu-id="f7c54-157"><a name="bknormalizationrule"> </a></span><span class="sxs-lookup"><span data-stu-id="f7c54-157"><a name="bknormalizationrule"> </a></span></span>

<span data-ttu-id="f7c54-p111">正規化ルールによって、さまざまな形式で表される電話番号をどのように変換するかが定義されます。ダイヤル元のロケールに応じて、同じ番号文字列が異なる方法で解釈および変換される場合があります。正規化ルールは、ユーザーが省略された内線または外線番号をダイヤルできるようにする必要がある場合に、必須となることがあります。</span><span class="sxs-lookup"><span data-stu-id="f7c54-p111">Normalization rules define how phone numbers expressed in various formats are to be translated. The same number string may be interpreted and translated differently, depending on the locale from which it is dialed. Normalization rules may be necessary if users need to be able to dial abbreviated internal or external numbers.</span></span>

<span data-ttu-id="f7c54-161">1 つ以上の正規化ルールをダイヤル プランに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7c54-161">One or more normalization rules must be assigned to the dial plan.</span></span> <span data-ttu-id="f7c54-162">正規化ルールは上から下の順に照合されるため、テナント ダイヤル プランにおける順序が重要になります。</span><span class="sxs-lookup"><span data-stu-id="f7c54-162">Normalization rules are matched from top to bottom, so the order in which they appear in a tenant dial plan is important.</span></span> <span data-ttu-id="f7c54-163">たとえば、テナント ダイヤル プランに 10 個の正規化ルールがある場合、ダイヤルされた番号の一致ロジックは 1 番目のルールから試行され、一致がみられない場合は 2 番目、というように順次実行されます。</span><span class="sxs-lookup"><span data-stu-id="f7c54-163">For example, if a tenant dial plan has 10 normalization rules, the dialed number matching logic will be tried starting with the first normalization rule, if there isn't a match then the second, and so forth.</span></span> <span data-ttu-id="f7c54-164">一致がみられた場合、そのルールが使用され、定義済みのそれ以外のルールとの照合は実行されません。</span><span class="sxs-lookup"><span data-stu-id="f7c54-164">If a match is made, that rule is used and there is no effort to match any other rules that are defined.</span></span> <span data-ttu-id="f7c54-165">特定のテナントダイヤルプランには、最大で50の正規化ルールを適用できます。</span><span class="sxs-lookup"><span data-stu-id="f7c54-165">There can be a maximum of 50 normalization rules in a given tenant dial plan.</span></span>

### <a name="determining-the-required-normalization-rules"></a><span data-ttu-id="f7c54-166">必要な正規化ルールの指定</span><span class="sxs-lookup"><span data-stu-id="f7c54-166">Determining the required normalization rules</span></span>

<span data-ttu-id="f7c54-167">テナントのダイヤルプランは、特定のユーザーのサービス国のダイヤルプランに実質的に統合される可能性があるため、どのテナントダイヤルプランの正規化ルールが必要かを判断するために、サービス国のダイヤルプランの正規化ルールを評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7c54-167">Because any tenant dial plan is effectively merged with a given user's service country dial plan, it is likely that the service country dial plan's normalization rules need to be evaluated in order to determine which tenant dial plan normalization rules are needed.</span></span> <span data-ttu-id="f7c54-168">この目的で **Get-CsEffectiveTenantDialPlan** コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7c54-168">The **Get-CsEffectiveTenantDialPlan** cmdlet can be used for this purpose.</span></span> <span data-ttu-id="f7c54-169">コマンドレットは入力パラメータとしてユーザー ID を必要とし、ユーザーに適用可能なすべての正規化ルールを返します。</span><span class="sxs-lookup"><span data-stu-id="f7c54-169">The cmdlet takes the user's identity as the input parameter and will return all normalization rules that are applicable to the user.</span></span>

### <a name="creating-normalization-rules"></a><span data-ttu-id="f7c54-170">正規化ルールの作成</span><span class="sxs-lookup"><span data-stu-id="f7c54-170">Creating normalization rules</span></span>
<span data-ttu-id="f7c54-171"><a name="createrule"> </a></span><span class="sxs-lookup"><span data-stu-id="f7c54-171"><a name="createrule"> </a></span></span>

<span data-ttu-id="f7c54-172">正規化ルールは、.NET Framework の正規表現を使って、サーバーがダイヤル文字列を E.i 形式に変換するために使用する数値一致パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7c54-172">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format.</span></span> <span data-ttu-id="f7c54-173">正規化ルールは、一致に対する正規表現と、一致が見つかったときに行う変換を指定することで作成できます。</span><span class="sxs-lookup"><span data-stu-id="f7c54-173">Normalization rules can be created by specifying the regular expression for the match and the translation to be done when a match is found.</span></span> <span data-ttu-id="f7c54-174">作業が完了したら、テスト番号を入力して、正規化ルールが正常に機能することを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f7c54-174">When you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="f7c54-175">.NET Framework の正規表現を使用する場合の詳細については、「[.NET Framework の正規表現](https://go.microsoft.com/fwlink/p/?linkId=140927)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7c54-175">For details about using .NET Framework regular expressions, see [.NET Framework Regular Expressions](https://go.microsoft.com/fwlink/p/?linkId=140927).</span></span>

<span data-ttu-id="f7c54-176">テナントのダイヤル プランの正規化ルールを作成および管理する場合は「[ダイヤル プランを作成および管理する](create-and-manage-dial-plans.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f7c54-176">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage normalization rules for your tenant dial plans.</span></span>

### <a name="sample-normalization-rules"></a><span data-ttu-id="f7c54-177">正規化ルールのサンプル</span><span class="sxs-lookup"><span data-stu-id="f7c54-177">Sample normalization rules</span></span>

<span data-ttu-id="f7c54-p115">次の表に, .NET Framework の正規表現として記述される正規化ルールのサンプルを示します。これらのサンプルは例示するためのもので、独自の正規化ルールを作成する際の規定リファレンスとして提示するものではありません。</span><span class="sxs-lookup"><span data-stu-id="f7c54-p115">The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

<span data-ttu-id="f7c54-180"><a name="regularexpression"> </a> 
 **.Net Framework の正規表現を使用した正規化ルール**</span><span class="sxs-lookup"><span data-stu-id="f7c54-180"><a name="regularexpression"> </a>
**Normalization rules using .NET Framework regular expressions**</span></span>

| <span data-ttu-id="f7c54-181">ルール名</span><span class="sxs-lookup"><span data-stu-id="f7c54-181">Rule name</span></span><br/> | <span data-ttu-id="f7c54-182">説明</span><span class="sxs-lookup"><span data-stu-id="f7c54-182">Description</span></span><br/> | <span data-ttu-id="f7c54-183">番号のパターン</span><span class="sxs-lookup"><span data-stu-id="f7c54-183">Number pattern</span></span><br/> | <span data-ttu-id="f7c54-184">変換</span><span class="sxs-lookup"><span data-stu-id="f7c54-184">Translation</span></span><br/> | <span data-ttu-id="f7c54-185">例</span><span class="sxs-lookup"><span data-stu-id="f7c54-185">Example</span></span><br/> |
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f7c54-186">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="f7c54-186">4digitExtension</span></span>  <br/> |<span data-ttu-id="f7c54-187">4 桁の内線番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="f7c54-187">Translates 4-digit extensions.</span></span>  <br/> |<span data-ttu-id="f7c54-188">^(\\d{4})$</span><span class="sxs-lookup"><span data-stu-id="f7c54-188">^(\\d{4})$</span></span>  <br/> |<span data-ttu-id="f7c54-189">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="f7c54-189">+1425555$1</span></span>  <br/> |<span data-ttu-id="f7c54-190">0100 は +14255550100 に変換されます</span><span class="sxs-lookup"><span data-stu-id="f7c54-190">0100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="f7c54-191">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="f7c54-191">5digitExtension</span></span>  <br/> |<span data-ttu-id="f7c54-192">5 桁の内線番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="f7c54-192">Translates 5-digit extensions.</span></span>  <br/> |<span data-ttu-id="f7c54-193">^5(\\d{4})$</span><span class="sxs-lookup"><span data-stu-id="f7c54-193">^5(\\d{4})$</span></span>  <br/> |<span data-ttu-id="f7c54-194">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="f7c54-194">+1425555$1</span></span>  <br/> |<span data-ttu-id="f7c54-195">50100 は +14255550100 に変換されます</span><span class="sxs-lookup"><span data-stu-id="f7c54-195">50100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="f7c54-196">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="f7c54-196">7digitcallingRedmond</span></span>  <br/> |<span data-ttu-id="f7c54-197">7 桁の番号をレドモンドの電話番号に変換します。</span><span class="sxs-lookup"><span data-stu-id="f7c54-197">Translates 7-digit numbers to Redmond local numbers.</span></span>  <br/> |<span data-ttu-id="f7c54-198">^(\\d{7})$</span><span class="sxs-lookup"><span data-stu-id="f7c54-198">^(\\d{7})$</span></span>  <br/> |<span data-ttu-id="f7c54-199">+1425$1</span><span class="sxs-lookup"><span data-stu-id="f7c54-199">+1425$1</span></span>  <br/> |<span data-ttu-id="f7c54-200">5550100 は +14255550100 に変換されます</span><span class="sxs-lookup"><span data-stu-id="f7c54-200">5550100 is translated to +14255550100</span></span>  <br/>|
|<span data-ttu-id="f7c54-201">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="f7c54-201">RedmondOperator</span></span>  <br/> |<span data-ttu-id="f7c54-202">0 をレドモンドのオペレーター呼び出し番号に変換します。</span><span class="sxs-lookup"><span data-stu-id="f7c54-202">Translates 0 to Redmond Operator.</span></span>  <br/> |<span data-ttu-id="f7c54-203">^0$</span><span class="sxs-lookup"><span data-stu-id="f7c54-203">^0$</span></span>  <br/> |<span data-ttu-id="f7c54-204">+14255550100</span><span class="sxs-lookup"><span data-stu-id="f7c54-204">+14255550100</span></span>  <br/> |<span data-ttu-id="f7c54-205">0 は +14255550100 に変換されます</span><span class="sxs-lookup"><span data-stu-id="f7c54-205">0 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="f7c54-206">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="f7c54-206">RedmondSitePrefix</span></span>  <br/> |<span data-ttu-id="f7c54-207">オンネット プレフィックス (6) およびレドモンドのサイト コード (222) 付きの番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="f7c54-207">Translates numbers with on-net prefix (6) and Redmond site code (222).</span></span>  <br/> |<span data-ttu-id="f7c54-208">^6222(\\d{4})$</span><span class="sxs-lookup"><span data-stu-id="f7c54-208">^6222(\\d{4})$</span></span>  <br/> |<span data-ttu-id="f7c54-209">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="f7c54-209">+1425555$1</span></span>  <br/> |<span data-ttu-id="f7c54-210">62220100 は +14255550100 に変換されます</span><span class="sxs-lookup"><span data-stu-id="f7c54-210">62220100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="f7c54-211">5digitRange</span><span class="sxs-lookup"><span data-stu-id="f7c54-211">5digitRange</span></span>  <br/> |<span data-ttu-id="f7c54-212">3 から 7 を含むその範囲で始まる 5 桁の内線番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="f7c54-212">Translates 5-digit extensions starting with the digit range between 3-7 inclusive.</span></span>  <br/> |<span data-ttu-id="f7c54-213">^([3-7]\\d{4})$</span><span class="sxs-lookup"><span data-stu-id="f7c54-213">^([3-7]\\d{4})$</span></span>  <br/> |<span data-ttu-id="f7c54-214">+ 142555 $ 1</span><span class="sxs-lookup"><span data-stu-id="f7c54-214">+142555$1</span></span> <br/> |<span data-ttu-id="f7c54-215">54567 は +14255554567 に変換されます</span><span class="sxs-lookup"><span data-stu-id="f7c54-215">54567 is translated to +14255554567</span></span>  <br/> |
|<span data-ttu-id="f7c54-216">PrefixAdded</span><span class="sxs-lookup"><span data-stu-id="f7c54-216">PrefixAdded</span></span>  <br/> |<span data-ttu-id="f7c54-217">1 桁目と 3 桁目に制限を付けて、9 桁の番号の前に国番号を追加します。</span><span class="sxs-lookup"><span data-stu-id="f7c54-217">Adds a country prefix in front of a 9 digit number with restrictions on the first and third digits.</span></span>  <br/> |<span data-ttu-id="f7c54-218">^([2-9]\\d\\d[2-9]\\d{6})$</span><span class="sxs-lookup"><span data-stu-id="f7c54-218">^([2-9]\\d\\d[2-9]\\d{6})$</span></span>  <br/> |<span data-ttu-id="f7c54-219">1$1</span><span class="sxs-lookup"><span data-stu-id="f7c54-219">1$1</span></span>  <br/> |<span data-ttu-id="f7c54-220">4255554567 は 14255554567 に変換されます</span><span class="sxs-lookup"><span data-stu-id="f7c54-220">4255554567 is translated to 14255554567</span></span>  <br/> |
|<span data-ttu-id="f7c54-221">NoTranslation</span><span class="sxs-lookup"><span data-stu-id="f7c54-221">NoTranslation</span></span>  <br/> |<span data-ttu-id="f7c54-222">5 桁と一致しますが、変換は行いません。</span><span class="sxs-lookup"><span data-stu-id="f7c54-222">Match 5 digits but no translation.</span></span>  <br/> |<span data-ttu-id="f7c54-223">^(\\d{5})$</span><span class="sxs-lookup"><span data-stu-id="f7c54-223">^(\\d{5})$</span></span>  <br/> |<span data-ttu-id="f7c54-224">$1</span><span class="sxs-lookup"><span data-stu-id="f7c54-224">$1</span></span>  <br/> |<span data-ttu-id="f7c54-225">34567 は 34567 に変換されます</span><span class="sxs-lookup"><span data-stu-id="f7c54-225">34567 is translated to 34567</span></span>  <br/> |

 <span data-ttu-id="f7c54-226">**上に示す正規化ルールに基づくレドモンドのダイヤル プラン**</span><span class="sxs-lookup"><span data-stu-id="f7c54-226">**Redmond dial plan based on normalization rules shown above.**</span></span>

 <span data-ttu-id="f7c54-227">次の表に、前の表に示される正規化ルールに基づく、レドモンド、ワシントン、米国のサンプル ダイヤル プランを示します。</span><span class="sxs-lookup"><span data-stu-id="f7c54-227">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

| <span data-ttu-id="f7c54-228">レドモンドのダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="f7c54-228">Redmond dial plan</span></span><br/> |
|:-----------------------|                                                                                                                      
| <span data-ttu-id="f7c54-229">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="f7c54-229">5digitExtension</span></span> <br/> |                                                                                                                                    
| <span data-ttu-id="f7c54-230">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="f7c54-230">7digitcallingRedmond</span></span> <br/> |
| <span data-ttu-id="f7c54-231">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="f7c54-231">RedmondSitePrefix</span></span> <br/> |
| <span data-ttu-id="f7c54-232">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="f7c54-232">RedmondOperator</span></span> <br/> |

> [!NOTE]
> <span data-ttu-id="f7c54-233">上の表に示した正規化ルール名にスペースは含まれていませんが、これは選択肢の1つです。</span><span class="sxs-lookup"><span data-stu-id="f7c54-233">The normalization rules names shown in the preceding table don't include spaces, but this is a matter of choice.</span></span> <span data-ttu-id="f7c54-234">たとえば、表に最初に示されている名前は、「5 digit extension」と「5-digit Extension」のどちらの形式で記述しても有効になります。</span><span class="sxs-lookup"><span data-stu-id="f7c54-234">The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f7c54-235">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7c54-235">Related topics</span></span>

[<span data-ttu-id="f7c54-236">ダイヤル プランを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="f7c54-236">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)

[<span data-ttu-id="f7c54-237">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="f7c54-237">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="f7c54-238">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="f7c54-238">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="f7c54-239">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="f7c54-239">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

<span data-ttu-id="f7c54-240">[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="f7c54-240">[Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
