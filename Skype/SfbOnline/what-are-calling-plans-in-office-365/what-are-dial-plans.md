---
title: ダイヤル プランについて
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: 'ダイヤルの通話プラン (PSTN の呼び出しのダイヤル プラン) の種類は、Office 365 を使用し、組織のいずれかを選択する方法について説明します。  '
ms.openlocfilehash: 27e65cb0651171f7e0a5d0262db0072b4d620851
ms.sourcegitcommit: b45077dd1b5d366fa9a30698aa66ed4b13264eee
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/25/2018
ms.locfileid: "21145295"
---
# <a name="what-are-dial-plans"></a><span data-ttu-id="a1d54-103">ダイヤル プランについて</span><span class="sxs-lookup"><span data-stu-id="a1d54-103">What are dial plans?</span></span>

<span data-ttu-id="a1d54-104">[] ダイヤル プランは、個別のユーザーによってダイヤルされた電話番号を、通話承認と通話ルーティングの目的で別の形式 (通常は E.164) に変換する、正規化ルールの名前付きのセットです。</span><span class="sxs-lookup"><span data-stu-id="a1d54-104">A dial plan is a named set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>
  
<span data-ttu-id="a1d54-p101">ダイヤル プランは、さまざまな形式で表される電話番号が別の 1 つの形式にどのように変換されるかを定義する 1 つ以上の正規化ルールで構成されます。同じダイヤル文字列が、ダイヤル プランによって異なる形で解釈、変換される可能性があるため、指定されたユーザーに割り当てられているダイヤル プランに応じて、同じダイヤル番号が異なる形で変換、ルーティングされることがあります。</span><span class="sxs-lookup"><span data-stu-id="a1d54-p101">A dial plan consists of one or more normalization rules that define how phone numbers expressed in various formats are translated to an alternate format. The same dial string may be interpreted and translated differently in different dial plans, so depending on which dial plan is assigned to a given user, the same dialed number may be translated and routed differently.</span></span>
  
<span data-ttu-id="a1d54-107">テナントのダイヤル プランを作成および管理する場合は「[ダイヤル プランを作成および管理する](create-and-manage-dial-plans.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a1d54-107">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage tenant dial plans.</span></span>
  
## <a name="tenant-dial-plan-scope"></a><span data-ttu-id="a1d54-108">テナント ダイヤル プランのスコープ</span><span class="sxs-lookup"><span data-stu-id="a1d54-108">Tenant dial plan scope</span></span>

<span data-ttu-id="a1d54-p102">ダイヤル プランのスコープによって、ダイヤル プランを適用できる階層レベルが決まります。このスコープは、Skype for Business Server 2015 オンプレミス環境のものとは異なります。クライアントは、ユーザーが Skype for Business Online にログオンした際に自動的に提供されるプロビジョニング設定から、適切なダイヤル プランを入手します。管理者として、リモート PowerShell を使ってダイヤル プラン スコープ レベルの管理と割り当てを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a1d54-p102">A dial plan's scope determines the hierarchical level at which the dial plan can be applied. The scopes are different than in a Skype for Business Server 2015 on-premises deployment. Clients obtain the appropriate dial plan through provisioning settings that are automatically provided when users log on to Skype for Business Online. As an administrator, you can manage and assign dial plan scope levels by using Remote PowerShell.</span></span>
  
<span data-ttu-id="a1d54-p103">Skype for Business Online には、サービス スコープおよび (組織向けの) テナント スコープの 2 種類のダイヤル プランがあります。サービス スコープのダイヤル プランは、Office 365 電話システムを利用できるすべての国または地域に対して定義されます。各ユーザーには、割り当てられた Office 365 の利用場所と一致するサービス国のダイヤル プランが自動的に割り当てられます。サービス国のダイヤル プランは変更できませんが、サービス国のダイヤル プランを強化するテナント スコープのダイヤル プランは作成できます。クライアントはプロビジョニングされると、サービス国のダイヤル プランと適切なスコープのテナント ダイヤル プランの組み合わせとなる「有効なダイヤル プラン」を入手します。したがって、テナント ダイヤル プランですべての正規化ルールを定義する必要はありません。サービス国のダイヤル プランにすでに存在する可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="a1d54-p103">In Skype for Business Online, there are two types of dial plans - service scoped and tenant (which is for your organization) scoped. A service scoped dial plan is defined for every country/region where the Office 365 Phone System is available. Each user is automatically assigned the service country dial plan that matches the Office 365 Usage Location assigned to the user. You can't change the service country dial plan, but you can create tenant scoped dial plans, which augment the service country dial plan. As clients are provisioned, they obtain an "effective dial plan," which is a combination of the service country dial plan and the appropriately scoped tenant dial plan. Therefore, it's not necessary to define all normalization rules in tenant dial plans as they might already exist in the service country dial plan.</span></span>
  
<span data-ttu-id="a1d54-p104">テナント ダイヤル プランは、さらに 2 つのスコープ (テナント スコープとユーザー スコープ) に分けることができます。テナントがユーザー スコープのダイヤル プランを定義して割り当てる場合、そのユーザーは、ユーザーのサービス国のダイヤル プランと割り当てられたユーザー ダイヤル プランによる有効なダイヤル プランでプロビジョニングされます。テナントがテナント スコープのダイヤル プランを定義しても、ユーザー スコープのダイヤル プランを割り当てないと、そのユーザーは、ユーザーのサービス国のダイヤル プランとテナント ダイヤル プランによる有効なダイヤル プランでプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="a1d54-p104">Tenant dial plans can be further broken into two scopes - tenant scope or user scope. If a tenant defines and assigns a user scoped dial plan, then that user will be provisioned with an effective dial plan of the user's service country dial plan and the assigned user dial plan. If a tenant defines a tenant scoped dial plan but doesn't assign a user scoped dial plan, then that user will be provisioned with an effective dial plan of the user's service country dial plan and the tenant dial plan.</span></span>
  
<span data-ttu-id="a1d54-122">Skype for Business Online でのダイヤル プランの継承モデルは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a1d54-122">The following is the inheritance model of dial plans in Skype for Business Online.</span></span>
  
![How dial plans are inherited in Skype for Business Online.](../images/b2744f33-ebbd-4c23-bfba-1747312ab178.png)
  
<span data-ttu-id="a1d54-124">次に、考えられる有効なダイヤル プランを示します。</span><span class="sxs-lookup"><span data-stu-id="a1d54-124">The following are the possible effective dial plans:</span></span>
  
 <span data-ttu-id="a1d54-125">**サービス国** テナント スコープのダイヤル プランが定義されておらず、テナント ユーザー スコープのダイヤル プランがプロビジョニングされたユーザーに割り当てられていない場合、ユーザーは Office 365 の利用場所に関連付けられたサービス国にマッピングされた有効なダイヤル プランを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a1d54-125">**Service Country** If no tenant scoped dial plan is defined and no tenant user scoped dial plan is assigned to the provisioned user, the user will receive an effective dial plan mapped to the service country associated with their Office 365 Usage Location.</span></span>
  
 <span data-ttu-id="a1d54-126">**テナント グローバル - サービス国** テナント ユーザーのダイヤル プランが定義されているのにユーザーに割り当てられていない場合、プロビジョニングされたユーザーは結合したテナント ダイヤル プランと Office 365 の利用場所に関連付けられたサービス国のダイヤル プランで構成される有効なダイヤル プランを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a1d54-126">**Tenant Global - Service Country** If a tenant user dial plan is defined but not assigned to a user, the provisioned user will receive an effective dial plan consisting of a merged tenant dial plan and the service country dial plan associated with their Office 365 Usage Location.</span></span>
  
 <span data-ttu-id="a1d54-127">**テナント ユーザー - サービス国** テナント ユーザーのダイヤル プランが定義されていてユーザーに割り当てられている場合、プロビジョニングされたユーザーは結合したテナント ユーザーのダイヤル プランと Office 365 の利用場所に関連付けられたサービス国のダイヤル プランで構成される有効なダイヤル プランを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a1d54-127">**Tenant User - Service Country** If a tenant user dial plan is defined and assigned to a user, the provisioned user will receive an effective dial plan consisting of the merged tenant user dial plan and the service country dial plan associated with their Office 365 Usage Location.</span></span>
  
<span data-ttu-id="a1d54-128">テナントのダイヤル プランを作成する場合は「[ダイヤル プランを作成および管理する](create-and-manage-dial-plans.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a1d54-128">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.</span></span>
  
## <a name="planning-for-tenant-dial-plans"></a><span data-ttu-id="a1d54-129">テナント ダイヤル プランの計画</span><span class="sxs-lookup"><span data-stu-id="a1d54-129">Planning for tenant dial plans</span></span>

<span data-ttu-id="a1d54-130">カスタム ダイヤル プランを計画するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1d54-130">To plan custom dial plans, follow these steps:</span></span>
  
- <span data-ttu-id="a1d54-p105">**手順 1** ユーザーのダイヤル エクスペリエンスを高めるためにカスタム ダイヤル プランが必要かどうかを決定します。通常は、内線または省略された国内ダイヤルなど、E.164 以外のダイヤルに対応する場合に必要となります。</span><span class="sxs-lookup"><span data-stu-id="a1d54-p105">**Step 1** Decide whether a custom dial plan is needed to enhance the user dialing experience. Typically, the need for one would be to support non-E.164 dialing, such as extensions or abbreviated national dialing.</span></span>
    
- <span data-ttu-id="a1d54-p106">**手順 2** テナント グローバルまたはテナント ユーザー スコープのダイヤル プランのどちらが必要か、または両方とも必要であるかを決定します。ユーザーに複数のローカル ダイヤル要件がある場合は、ユーザー スコープのダイヤル プランが必要となります。</span><span class="sxs-lookup"><span data-stu-id="a1d54-p106">**Step 2** Determine whether tenant global or tenant user scoped dial plans are needed, or both. User scoped dial plans are needed if users have different local dialing requirements.</span></span>
    
- <span data-ttu-id="a1d54-p107">**手順 3** 各必須ダイヤル プランに対応する有効な番号バターンを特定します。サービス レベル国のダイヤル プランで定義されていない番号パターンのみが必要となります。</span><span class="sxs-lookup"><span data-stu-id="a1d54-p107">**Step 3** Identify valid number patterns for each required dial plan. Only the number patterns that are not defined in the service level country dial plans are required.</span></span>
    
- <span data-ttu-id="a1d54-p108">**手順 4** ダイヤル プランの名前付けについて組織全体のスキームを策定します。標準的な名前付けスキームを採用することにより、組織全体にわたり一貫した方針を実現でき、メンテナンスや更新作業が簡素化されます。</span><span class="sxs-lookup"><span data-stu-id="a1d54-p108">**Step 4** Develop an organization-wide scheme for naming dial plans. Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>
    
<span data-ttu-id="a1d54-139">[FastTrack](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice) は、さらなるリソースとパートナーで、テナント ダイヤル プランの実装をサポートします。</span><span class="sxs-lookup"><span data-stu-id="a1d54-139">The [FastTrack](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice) has additional resources and partners that can assist you with implementing tenant dial plans.</span></span>
  
## <a name="creating-your-new-tenant-dial-plan"></a><span data-ttu-id="a1d54-140">テナント ダイヤル プランの新規作成</span><span class="sxs-lookup"><span data-stu-id="a1d54-140">Creating your new tenant dial plan</span></span>

<span data-ttu-id="a1d54-141">ダイヤル プランを新規作成する場合、必要な情報を把握しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1d54-141">When you create a new dial plan, you must put in the information that is required.</span></span>
  
### <a name="name-and-simple-name"></a><span data-ttu-id="a1d54-142">名前と簡易名</span><span class="sxs-lookup"><span data-stu-id="a1d54-142">Name and simple name</span></span>

<span data-ttu-id="a1d54-p109">ユーザー ダイヤル プランでは、ダイヤル プランが割り当てられるユーザーを識別する説明的な名前を指定する必要があります。ダイヤル プランの簡易名には、ダイヤル プランの名前から生成された文字列が事前に設定されています。[単純名] フィールドは編集可能で、ダイヤル プラン用のより説明的な名前付け規則を作成することができます。[単純名] の値は空にすることはできず、一意でなければなりません。最適な方法は、組織全体の名前付け規則を作成してから、その規則の一貫性をすべてのサイトとユーザーに使用することです。</span><span class="sxs-lookup"><span data-stu-id="a1d54-p109">For user dial plans, you should specify a descriptive name that identifies to the users the dial plan will be assigned. The dial plan Simple Name is prepopulated with a string that is derived from the dial plan name. The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans. The Simple Name value cannot be empty and must be unique. A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>
  
### <a name="description"></a><span data-ttu-id="a1d54-148">説明</span><span class="sxs-lookup"><span data-stu-id="a1d54-148">Description</span></span>

<span data-ttu-id="a1d54-149">地理的な場所または対応するダイヤル プランが適用されるユーザーのグループに関する一般的で認識可能な名前を入力することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a1d54-149">We recommend that you type the common, recognizable name of the geographic location or group of users to which the corresponding dial plan applies.</span></span>
  
### <a name="external-access-prefix"></a><span data-ttu-id="a1d54-150">外部アクセス プレフィックス</span><span class="sxs-lookup"><span data-stu-id="a1d54-150">External access prefix</span></span>

> [!CAUTION]
> <span data-ttu-id="a1d54-151">外部アクセス プレフィックスは現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a1d54-151">External access prefix isn't currently supported.</span></span> 
  
<span data-ttu-id="a1d54-152">ユーザーが外線につなぐために 1 つ以上の追加の先頭数字 (9 など) をダイヤルする必要がある場合は、最大 4 文字 (#、\*、0～9) の外部アクセス プレフィックスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a1d54-152">You can specify an external access prefix of up to four characters (#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a1d54-153">外部アクセス プレフィックスを指定する場合、プレフィックスを適応させるための正規化ルールを追加で作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a1d54-153">If you specify an external access prefix, you don't need to create an additional normalization rule to accommodate the prefix.</span></span> 
  
<span data-ttu-id="a1d54-154">テナントのダイヤル プランを作成する場合は「[ダイヤル プランを作成および管理する](create-and-manage-dial-plans.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a1d54-154">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.</span></span>
  
## <a name="normalization-rules"></a><span data-ttu-id="a1d54-155">正規化ルール</span><span class="sxs-lookup"><span data-stu-id="a1d54-155">Normalization rules</span></span>

<span data-ttu-id="a1d54-p110">正規化ルールによって、さまざまな形式で表される電話番号をどのように変換するかが定義されます。ダイヤル元のロケールに応じて、同じ番号文字列が異なる方法で解釈および変換される場合があります。正規化ルールは、ユーザーが省略された内線または外線番号をダイヤルできるようにする必要がある場合に、必須となることがあります。</span><span class="sxs-lookup"><span data-stu-id="a1d54-p110">Normalization rules define how phone numbers expressed in various formats are to be translated. The same number string may be interpreted and translated differently, depending on the locale from which it is dialed. Normalization rules may be necessary if users need to be able to dial abbreviated internal or external numbers.</span></span>
  
<span data-ttu-id="a1d54-p111">1 つ以上の正規化ルールをダイヤル プランに割り当てる必要があります。正規化ルールは上から下の順に照合されるため、テナント ダイヤル プランにおける順序が重要になります。たとえば、テナント ダイヤル プランに 10 個の正規化ルールがある場合、ダイヤルされた番号の一致ロジックは 1 番目のルールから試行され、一致がみられない場合は 2 番目、というように順次実行されます。一致がみられた場合、そのルールが使用され、定義済みのそれ以外のルールとの照合は実行されません。指定されたテナント ダイヤル プランには、最大で 25 個の正規化ルールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="a1d54-p111">One or more normalization rules must be assigned to the dial plan. Normalization rules are matched from top to bottom, so the order in which they appear in a tenant dial plan is important. For example, if a tenant dial plan has 10 normalization rules, the dialed number matching logic will be tried starting with the first normalization rule, if there isn't a match then the second, and so forth. If a match is made, that rule is used and there is no effort to match any other rules that are defined. There can be a maximum of 25 normalization rules in a given tenant dial plan.</span></span>
  
### <a name="determining-the-required-normalization-rules"></a><span data-ttu-id="a1d54-164">必要な正規化ルールの指定</span><span class="sxs-lookup"><span data-stu-id="a1d54-164">Determining the required normalization rules</span></span>

<span data-ttu-id="a1d54-p112">すべてのテナント ダイヤル プランは指定されたユーザーのサービス国のダイヤル プランと有効に結合されるため、サービス国のダイヤル プランの正規化ルールが、必要となるテナント ダイヤル プランの正規化ルールを特定するために評価される必要があります。この目的で **Get-CsEffectiveTenantDialPlan** コマンドレットを使用できます。コマンドレットは入力パラメータとしてユーザー ID を必要とし、ユーザーに適用可能なすべての正規化ルールを返します。</span><span class="sxs-lookup"><span data-stu-id="a1d54-p112">Because any tenant dial plan is effectively merged with a given user's service country dial plan it, it is likely that the service country dial plan's normalization rules need to be evaluated in order to determine which tenant dial plan normalization rules are needed. The **Get-CsEffectiveTenantDialPlan** cmdlet can be used for this purpose. The cmdlet takes the user's identity as the input parameter and will return all normalization rules that are applicable to the user.</span></span>
  
### <a name="creating-normalization-rules"></a><span data-ttu-id="a1d54-168">正規化ルールの作成</span><span class="sxs-lookup"><span data-stu-id="a1d54-168">Creating normalization rules</span></span>

<span data-ttu-id="a1d54-p113">正規化ルールでは、リバース番号検索でダイヤル文字列を E.164 形式に変換するためにサーバーによって使用される番号一致パターンを指定するために, .NET Framework の正規表現が使用されます。正規化ルールは、一致に対する正規表現と、一致が見つかったときに行う変換を指定することで作成できます。作業が完了したら、テスト番号を入力して、正規化ルールが正常に機能することを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a1d54-p113">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format for the purpose of performing reverse number lookup. Normalization rules can be created by specifying the regular expression for the match and the translation to be done when a match is found. When you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>
  
<span data-ttu-id="a1d54-172">.NET Framework の正規表現を使用する場合の詳細については、「[.NET Framework の正規表現](https://go.microsoft.com/fwlink/p/?linkId=140927)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1d54-172">For details about using .NET Framework regular expressions, see [.NET Framework Regular Expressions](https://go.microsoft.com/fwlink/p/?linkId=140927).</span></span>
  
<span data-ttu-id="a1d54-173">テナントのダイヤル プランの正規化ルールを作成および管理する場合は「[ダイヤル プランを作成および管理する](create-and-manage-dial-plans.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a1d54-173">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage normalization rules for your tenant dial plans.</span></span>
  
### <a name="sample-normalization-rules"></a><span data-ttu-id="a1d54-174">正規化ルールのサンプル</span><span class="sxs-lookup"><span data-stu-id="a1d54-174">Sample normalization rules</span></span>

<span data-ttu-id="a1d54-p114">次の表に, .NET Framework の正規表現として記述される正規化ルールのサンプルを示します。これらのサンプルは例示するためのもので、独自の正規化ルールを作成する際の規定リファレンスとして提示するものではありません。</span><span class="sxs-lookup"><span data-stu-id="a1d54-p114">The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>
  
 <span data-ttu-id="a1d54-177">**.NET Framework の正規表現を使用した正規化ルール**</span><span class="sxs-lookup"><span data-stu-id="a1d54-177">**Normalization rules using .NET Framework regular expressions**</span></span>
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a1d54-178">**ルール名**</span><span class="sxs-lookup"><span data-stu-id="a1d54-178">**Rule name**</span></span> <br/> |<span data-ttu-id="a1d54-179">**説明**</span><span class="sxs-lookup"><span data-stu-id="a1d54-179">**Description**</span></span> <br/> |<span data-ttu-id="a1d54-180">**番号パターン**</span><span class="sxs-lookup"><span data-stu-id="a1d54-180">**Number pattern**</span></span> <br/> |<span data-ttu-id="a1d54-181">**変換**</span><span class="sxs-lookup"><span data-stu-id="a1d54-181">**Translation**</span></span> <br/> |<span data-ttu-id="a1d54-182">**例**</span><span class="sxs-lookup"><span data-stu-id="a1d54-182">**Example**</span></span> <br/> |
|<span data-ttu-id="a1d54-183">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="a1d54-183">4digitExtension</span></span>  <br/> |<span data-ttu-id="a1d54-184">4 桁の内線番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="a1d54-184">Translates 4-digit extensions.</span></span>  <br/> |<span data-ttu-id="a1d54-185">^ (\\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="a1d54-185">^(\\d{4})$</span></span>  <br/> |<span data-ttu-id="a1d54-186">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="a1d54-186">+1425555$1</span></span>  <br/> |<span data-ttu-id="a1d54-187">0100 は +14255550100 に変換されます</span><span class="sxs-lookup"><span data-stu-id="a1d54-187">0100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="a1d54-188">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="a1d54-188">5digitExtension</span></span>  <br/> |<span data-ttu-id="a1d54-189">5 桁の内線番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="a1d54-189">Translates 5-digit extensions.</span></span>  <br/> |<span data-ttu-id="a1d54-190">^5 (\\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="a1d54-190">^5(\\d{4})$</span></span>  <br/> |<span data-ttu-id="a1d54-191">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="a1d54-191">+1425555$1</span></span>  <br/> |<span data-ttu-id="a1d54-192">50100 は +14255550100 に変換されます</span><span class="sxs-lookup"><span data-stu-id="a1d54-192">50100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="a1d54-193">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="a1d54-193">7digitcallingRedmond</span></span>  <br/> |<span data-ttu-id="a1d54-194">7 桁の番号をレドモンドの電話番号に変換します。</span><span class="sxs-lookup"><span data-stu-id="a1d54-194">Translates 7-digit numbers to Redmond local numbers.</span></span>  <br/> |<span data-ttu-id="a1d54-195">^ (\\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="a1d54-195">^(\\d{7})$</span></span>  <br/> |<span data-ttu-id="a1d54-196">+1425$1</span><span class="sxs-lookup"><span data-stu-id="a1d54-196">+1425$1</span></span>  <br/> |<span data-ttu-id="a1d54-197">5550100 は +14255550100 に変換されます</span><span class="sxs-lookup"><span data-stu-id="a1d54-197">5550100 is translated to +14255550100</span></span>  <br/>|
|<span data-ttu-id="a1d54-198">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="a1d54-198">RedmondOperator</span></span>  <br/> |<span data-ttu-id="a1d54-199">0 をレドモンドのオペレーター呼び出し番号に変換します。</span><span class="sxs-lookup"><span data-stu-id="a1d54-199">Translates 0 to Redmond Operator.</span></span>  <br/> |<span data-ttu-id="a1d54-200">^0$</span><span class="sxs-lookup"><span data-stu-id="a1d54-200">^0$</span></span>  <br/> |<span data-ttu-id="a1d54-201">+14255550100</span><span class="sxs-lookup"><span data-stu-id="a1d54-201">+14255550100</span></span>  <br/> |<span data-ttu-id="a1d54-202">0 は +14255550100 に変換されます</span><span class="sxs-lookup"><span data-stu-id="a1d54-202">0 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="a1d54-203">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="a1d54-203">RedmondSitePrefix</span></span>  <br/> |<span data-ttu-id="a1d54-204">オンネット プレフィックス (6) およびレドモンドのサイト コード (222) 付きの番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="a1d54-204">Translates numbers with on-net prefix (6) and Redmond site code (222).</span></span>  <br/> |<span data-ttu-id="a1d54-205">^6222 (\\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="a1d54-205">^6222(\\d{4})$</span></span>  <br/> |<span data-ttu-id="a1d54-206">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="a1d54-206">+1425555$1</span></span>  <br/> |<span data-ttu-id="a1d54-207">62220100 は +14255550100 に変換されます</span><span class="sxs-lookup"><span data-stu-id="a1d54-207">62220100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="a1d54-208">5digitRange</span><span class="sxs-lookup"><span data-stu-id="a1d54-208">5digitRange</span></span>  <br/> |<span data-ttu-id="a1d54-209">3 から 7 を含むその範囲で始まる 5 桁の内線番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="a1d54-209">Translates 5-digit extensions starting with the digit range between 3-7 inclusive.</span></span>  <br/> |<span data-ttu-id="a1d54-210">^ ([3-7]\\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="a1d54-210">^([3-7]\\d{4})$</span></span>  <br/> |<span data-ttu-id="a1d54-211">+ 142555$ 1</span><span class="sxs-lookup"><span data-stu-id="a1d54-211">+142555$1</span></span> <br/> |<span data-ttu-id="a1d54-212">54567 は +14255554567 に変換されます</span><span class="sxs-lookup"><span data-stu-id="a1d54-212">54567 is translated to +14255554567</span></span>  <br/> |
|<span data-ttu-id="a1d54-213">PrefixAdded</span><span class="sxs-lookup"><span data-stu-id="a1d54-213">PrefixAdded</span></span>  <br/> |<span data-ttu-id="a1d54-214">1 桁目と 3 桁目に制限を付けて、9 桁の番号の前に国番号を追加します。</span><span class="sxs-lookup"><span data-stu-id="a1d54-214">Adds a country prefix in front of a 9 digit number with restrictions on the first and third digits.</span></span>  <br/> |<span data-ttu-id="a1d54-215">^ ([2-9]\\d\\d [2-9]\\d{6}) $</span><span class="sxs-lookup"><span data-stu-id="a1d54-215">^([2-9]\\d\\d[2-9]\\d{6})$</span></span>  <br/> |<span data-ttu-id="a1d54-216">1$1</span><span class="sxs-lookup"><span data-stu-id="a1d54-216">1$1</span></span>  <br/> |<span data-ttu-id="a1d54-217">4255554567 は 14255554567 に変換されます</span><span class="sxs-lookup"><span data-stu-id="a1d54-217">4255554567 is translated to 14255554567</span></span>  <br/> |
|<span data-ttu-id="a1d54-218">NoTranslation</span><span class="sxs-lookup"><span data-stu-id="a1d54-218">NoTranslation</span></span>  <br/> |<span data-ttu-id="a1d54-219">5 桁と一致しますが、変換は行いません。</span><span class="sxs-lookup"><span data-stu-id="a1d54-219">Match 5 digits but no translation.</span></span>  <br/> |<span data-ttu-id="a1d54-220">^ (\\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="a1d54-220">^(\\d{5})$</span></span>  <br/> |<span data-ttu-id="a1d54-221">$1</span><span class="sxs-lookup"><span data-stu-id="a1d54-221">$1</span></span>  <br/> |<span data-ttu-id="a1d54-222">34567 は 34567 に変換されます</span><span class="sxs-lookup"><span data-stu-id="a1d54-222">34567 is translated to 34567</span></span>  <br/> |
   
 <span data-ttu-id="a1d54-223">**上に示す正規化ルールに基づくレドモンドのダイヤル プラン**</span><span class="sxs-lookup"><span data-stu-id="a1d54-223">**Redmond dial plan based on normalization rules shown above.**</span></span>
  
<span data-ttu-id="a1d54-224">次の表に、前の表に示される正規化ルールに基づく、レドモンド、ワシントン、米国のサンプル ダイヤル プランを示します。</span><span class="sxs-lookup"><span data-stu-id="a1d54-224">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>
<span data-ttu-id="a1d54-225">|:-----| |**レドモンドのダイヤル プラン**</span><span class="sxs-lookup"><span data-stu-id="a1d54-225">|:-----| |**Redmond dial plan**</span></span> <br/> <span data-ttu-id="a1d54-226">| | 5digitExtension</span><span class="sxs-lookup"><span data-stu-id="a1d54-226">| |5digitExtension</span></span> <br/> <span data-ttu-id="a1d54-227">| | 7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="a1d54-227">| |7digitcallingRedmond</span></span> <br/> <span data-ttu-id="a1d54-228">| |RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="a1d54-228">| |RedmondSitePrefix</span></span> <br/> <span data-ttu-id="a1d54-229">| |RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="a1d54-229">| |RedmondOperator</span></span> <br/> |
   
> [!NOTE]
> <span data-ttu-id="a1d54-p116">前の表に示した正規化ルールの名前にはスペースが含まれていませんが、必要に応じて含めることもできます。たとえば、表に最初に示されている名前は、「5 digit extension」と「5-digit Extension」のどちらの形式で記述しても有効になります。</span><span class="sxs-lookup"><span data-stu-id="a1d54-p116">The normalization rules names shown in the preceding table do not include spaces, but this is a matter of choice. The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="a1d54-232">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="a1d54-232">Related topics</span></span>
[<span data-ttu-id="a1d54-233">ダイヤル プランを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="a1d54-233">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)

[<span data-ttu-id="a1d54-234">Skype for Business と Microsoft Teams のアドオン ライセンス</span><span class="sxs-lookup"><span data-stu-id="a1d54-234">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

[<span data-ttu-id="a1d54-235">電話番号の移行に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="a1d54-235">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="a1d54-236">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="a1d54-236">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

<span data-ttu-id="a1d54-237">[[Skype for Business 新しい電話番号の申請](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="a1d54-237">[Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)</span></span>

[<span data-ttu-id="a1d54-238">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="a1d54-238">Emergency calling terms and conditions</span></span>](../legal-and-regulatory/emergency-calling-terms-and-conditions.md)

<span data-ttu-id="a1d54-239">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="a1d54-239">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
