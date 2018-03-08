---
title: "ダイヤル プランとは"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "ダイヤル プラン (PSTN 通話ダイヤル プラン) の呼び出しの種類は、Office 365 を使用して、組織のいずれかを選択する方法について説明します。  "
ms.openlocfilehash: c4915b17ee7870725bd6e41e834d08a0e2b63f7d
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="what-are-dial-plans"></a><span data-ttu-id="44115-103">ダイヤル プランとは</span><span class="sxs-lookup"><span data-stu-id="44115-103">What are dial plans?</span></span>

<span data-ttu-id="44115-104">ダイヤル プランでは、翻訳正規化ルールの名前付きセットは、承認および通話をルーティングする機能のために、他の形式 (通常、E.164) に、個々 のユーザーの電話番号をダイヤルします。</span><span class="sxs-lookup"><span data-stu-id="44115-104">A dial plan is a named set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>
  
<span data-ttu-id="44115-p101">1 つまたは複数の正規化ルールを他の形式にさまざまな形式で表した電話番号を変換する方法を定義するダイヤル プランで構成されます。同じダイヤル文字列が解釈され、さまざまなダイヤル プランで複数の翻訳、数値の翻訳およびルーティングが異なる場合がありますによってどのダイヤル プランは、特定のユーザーに割り当てられているが、同じダイヤルようにします。</span><span class="sxs-lookup"><span data-stu-id="44115-p101">A dial plan consists of one or more normalization rules that define how phone numbers expressed in various formats are translated to an alternate format. The same dial string may be interpreted and translated differently in different dial plans, so depending on which dial plan is assigned to a given user, the same dialed number may be translated and routed differently.</span></span>
  
<span data-ttu-id="44115-107">参照してください[作成ダイヤル プランの管理と](create-and-manage-dial-plans.md)を作成し、[ダイヤル プランのテナントを管理します。</span><span class="sxs-lookup"><span data-stu-id="44115-107">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage tenant dial plans.</span></span>
  
## <a name="tenant-dial-plan-scope"></a><span data-ttu-id="44115-108">テナント ダイヤル プランの範囲</span><span class="sxs-lookup"><span data-stu-id="44115-108">Tenant dial plan scope</span></span>

<span data-ttu-id="44115-p102">ダイヤル プランの範囲では、ダイヤル プランに適用できる階層のレベルを決定します。スコープが Skype for Business Server 2015 でオンプレミスの展開とは異なるします。クライアントでは、プロビジョニングにログオン ユーザー Skype for Business Online を自動的に指定されている設定を使用して、適切なダイヤル プランを取得します。管理者は、管理し、リモート PowerShell を使用して、ダイヤル プランの範囲のレベルを割り当てることがことができます。</span><span class="sxs-lookup"><span data-stu-id="44115-p102">A dial plan's scope determines the hierarchical level at which the dial plan can be applied. The scopes are different than in a Skype for Business Server 2015 on-premises deployment. Clients obtain the appropriate dial plan through provisioning settings that are automatically provided when users log on to Skype for Business Online. As an administrator, you can manage and assign dial plan scope levels by using Remote PowerShell.</span></span>
  
<span data-ttu-id="44115-p103">Skype for Business Online で、ダイヤル プランのサービスのスコープとスコープ (つまり、組織の) テナントの 2 種類があります。Office 365 の電話システムを利用できる国/地域のスコープ サービス ダイヤル プランが定義されています。各ユーザーは、サービスの国ダイヤル プランのユーザーに割り当てられている Office 365 の利用場所に一致すると自動的に割り当てられます。サービス国のダイヤル プランを変更することはできませんが、テナント スコープ ダイヤル プランで、強化サービス国ダイヤル プランを作成することができます。クライアントがプロビジョニングは、"効果的なダイヤル プラン]"これは、サービスの国ダイヤル プランと適切にスコープ テナント ダイヤル プランの組み合わせを取得します。このため、サービスの国ダイヤル プランで既に存在する可能性がありますテナント ダイヤル プランですべての正規化のルールを定義する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="44115-p103">In Skype for Business Online, there are two types of dial plans - service scoped and tenant (which is for your organization) scoped. A service scoped dial plan is defined for every country/region where the Office 365 Phone System is available. Each user is automatically assigned the service country dial plan that matches the Office 365 Usage Location assigned to the user. You can't change the service country dial plan, but you can create tenant scoped dial plans, which augment the service country dial plan. As clients are provisioned, they obtain an "effective dial plan," which is a combination of the service country dial plan and the appropriately scoped tenant dial plan. Therefore, it's not necessary to define all normalization rules in tenant dial plans as they might already exist in the service country dial plan.</span></span>
  
<span data-ttu-id="44115-p104">テナント スコープまたはユーザー スコープの 2 つの範囲には、テナント ダイヤル プランをさらに分割することができます。テナントが定義され、ユーザー スコープ ダイヤル プランを割り当てられる場合は、ユーザーのサービス国ダイヤル プランと、割り当てられているユーザーのダイヤル プランの効果的なダイヤル プランとそのユーザーをプロビジョニングするされます。テナント スコープ テナント ダイヤル プランを定義しないユーザー スコープ ダイヤル プランを割り当てる場合は、そのユーザーが、ユーザーのサービス国ダイヤル プランとテナント ダイヤル プランの効果的なダイヤル プラン準備されます。</span><span class="sxs-lookup"><span data-stu-id="44115-p104">Tenant dial plans can be further broken into two scopes - tenant scope or user scope. If a tenant defines and assigns a user scoped dial plan, then that user will be provisioned with an effective dial plan of the user's service country dial plan and the assigned user dial plan. If a tenant defines a tenant scoped dial plan but doesn't assign a user scoped dial plan, then that user will be provisioned with an effective dial plan of the user's service country dial plan and the tenant dial plan.</span></span>
  
<span data-ttu-id="44115-122">Skype for Business Online でダイヤル プランの継承モデルは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="44115-122">The following is the inheritance model of dial plans in Skype for Business Online.</span></span>
  
![どのダイヤル プランは、skype for Business Online 継承されます。](../images/b2744f33-ebbd-4c23-bfba-1747312ab178.png)
  
<span data-ttu-id="44115-124">考えられる効果的なダイヤル プランを次に示します。</span><span class="sxs-lookup"><span data-stu-id="44115-124">The following are the possible effective dial plans:</span></span>
  
 <span data-ttu-id="44115-125">**サービスの国**テナント スコープ ダイヤル プランが定義されていない場合は、テナント スコープ ユーザー ダイヤル プランがプロビジョニングされるユーザーに割り当てられていないユーザーには、Office 365 の利用場所に関連付けられているサービス国に対応付けられて効果的なダイヤル プランが表示されます。</span><span class="sxs-lookup"><span data-stu-id="44115-125">**Service Country** If no tenant scoped dial plan is defined and no tenant user scoped dial plan is assigned to the provisioned user, the user will receive an effective dial plan mapped to the service country associated with their Office 365 Usage Location.</span></span>
  
 <span data-ttu-id="44115-126">**テナント グローバル - サービスの国**テナントのユーザーのダイヤル プランが定義されているが、ユーザーに割り当てられていない場合は、結合テナント ダイヤル プランと、Office 365 の利用場所に関連付けられているサービス国ダイヤル プランで構成される有効なダイヤル プランをプロビジョニングされるユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="44115-126">**Tenant Global - Service Country** If a tenant user dial plan is defined but not assigned to a user, the provisioned user will receive an effective dial plan consisting of a merged tenant dial plan and the service country dial plan associated with their Office 365 Usage Location.</span></span>
  
 <span data-ttu-id="44115-127">**テナントのユーザーのサービスの国**テナントのユーザーのダイヤル プランを定義するユーザーに割り当てられている場合、差し込み印刷のテナントのユーザーのダイヤル プランと、Office 365 の利用場所に関連付けられているサービス国ダイヤル プランで構成される有効なダイヤル プランをプロビジョニングされるユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="44115-127">**Tenant User - Service Country** If a tenant user dial plan is defined and assigned to a user, the provisioned user will receive an effective dial plan consisting of the merged tenant user dial plan and the service country dial plan associated with their Office 365 Usage Location.</span></span>
  
<span data-ttu-id="44115-128">参照してください[作成ダイヤル プランの管理と](create-and-manage-dial-plans.md)ダイヤル プランを作成するには、テナントにします。</span><span class="sxs-lookup"><span data-stu-id="44115-128">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.</span></span>
  
## <a name="planning-for-tenant-dial-plans"></a><span data-ttu-id="44115-129">テナント ダイヤル プランの計画</span><span class="sxs-lookup"><span data-stu-id="44115-129">Planning for tenant dial plans</span></span>

<span data-ttu-id="44115-130">ユーザー設定のダイヤル プランを計画するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="44115-130">To plan custom dial plans, follow these steps:</span></span>
  
- <span data-ttu-id="44115-p105">**手順 1**プランがユーザーの操作環境のダイヤルを強化するために必要なカスタム ダイヤルするかどうかを決定します。一般的に、いずれかの必要性は E.164 ではないダイヤル後などの拡張機能をサポートするまたは国内のダイヤルの省略形します。</span><span class="sxs-lookup"><span data-stu-id="44115-p105">**Step 1** Decide whether a custom dial plan is needed to enhance the user dialing experience. Typically, the need for one would be to support non-E.164 dialing, such as extensions or abbreviated national dialing.</span></span>
    
- <span data-ttu-id="44115-p106">**手順 2**テナント全体またはテナント スコープ ユーザー ダイヤル プランの必要かどうか、または両方を確認します。ユーザーがローカルのさまざまなダイヤル要件がある場合は、ユーザー スコープ ダイヤル プランが必要です。</span><span class="sxs-lookup"><span data-stu-id="44115-p106">**Step 2** Determine whether tenant global or tenant user scoped dial plans are needed, or both. User scoped dial plans are needed if users have different local dialing requirements.</span></span>
    
- <span data-ttu-id="44115-p107">**手順 3**各必要なダイヤル プランの有効な数字のパターンを特定します。ダイヤル プランのサービス レベルの国で定義されていない数値パターンのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="44115-p107">**Step 3** Identify valid number patterns for each required dial plan. Only the number patterns that are not defined in the service level country dial plans are required.</span></span>
    
- <span data-ttu-id="44115-p108">**手順 4**ダイヤル プランの名前を付けるため、組織全体のパターンを作成します。標準の命名が採用して組織全体の整合性を確保し、保守と更新プログラムを簡単に使用するとします。</span><span class="sxs-lookup"><span data-stu-id="44115-p108">**Step 4** Develop an organization-wide scheme for naming dial plans. Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>
    
<span data-ttu-id="44115-139">[FastTrack](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice)があり、その他のリソース パートナー テナント ダイヤル プランを実装するのに使用できることができます。</span><span class="sxs-lookup"><span data-stu-id="44115-139">The [FastTrack](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice) has additional resources and partners that can assist you with implementing tenant dial plans.</span></span>
  
## <a name="creating-your-new-tenant-dial-plan"></a><span data-ttu-id="44115-140">新しいテナント ダイヤル プランを作成します。</span><span class="sxs-lookup"><span data-stu-id="44115-140">Creating your new tenant dial plan</span></span>

<span data-ttu-id="44115-141">新しいダイヤル プランを作成するときに実行に必要な情報を出力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44115-141">When you create a new dial plan, you must put in the information that is required.</span></span>
  
### <a name="name-and-simple-name"></a><span data-ttu-id="44115-142">名前と簡単な名前</span><span class="sxs-lookup"><span data-stu-id="44115-142">Name and simple name</span></span>

<span data-ttu-id="44115-p109">ユーザー ダイヤル プランでは、ダイヤル プランをユーザーに識別するわかりやすい名前を割り当てるを指定する必要があります。ダイヤル プランの単純な名前は、ダイヤル プラン名から派生した文字列に設定されました。単純な名前フィールドは、その場で、ダイヤル プランの場合は、わかりやすい名前付け規則を作成するのには、編集可能なです。単純な名前の値が空にすることはできず、一意である必要があります。組織全体の名前付け規則を作成して、すべてのユーザーとサイト全体で一貫してこの規則を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="44115-p109">For user dial plans, you should specify a descriptive name that identifies to the users the dial plan will be assigned. The dial plan Simple Name is prepopulated with a string that is derived from the dial plan name. The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans. The Simple Name value cannot be empty and must be unique. A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>
  
### <a name="description"></a><span data-ttu-id="44115-148">説明</span><span class="sxs-lookup"><span data-stu-id="44115-148">Description</span></span>

<span data-ttu-id="44115-149">地理的な場所の一般的なわかりやすい名前を入力すること、またはに対応するダイヤル プランのユーザーのグループに適用されるをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="44115-149">We recommend that you type the common, recognizable name of the geographic location or group of users to which the corresponding dial plan applies.</span></span>
  
### <a name="external-access-prefix"></a><span data-ttu-id="44115-150">外部アクセス プレフィックス</span><span class="sxs-lookup"><span data-stu-id="44115-150">External access prefix</span></span>

> [!CAUTION]
> <span data-ttu-id="44115-151">外部アクセス プレフィックスは現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="44115-151">External access prefix isn't currently supported.</span></span> 
  
<span data-ttu-id="44115-152">最大 4 文字を外部アクセス プレフィックスを指定できます (#, \*、および 0 ~ 9) ユーザーがダイヤルの 1 つまたは複数追加桁 (たとえば、9) を外部の行を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44115-152">You can specify an external access prefix of up to four characters (#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>
  
> [!NOTE]
> <span data-ttu-id="44115-153">場合は、外部アクセス プレフィックスを指定すると、プレフィックスを対応するために、追加の正規化ルールを作成するのには必要ありません。</span><span class="sxs-lookup"><span data-stu-id="44115-153">If you specify an external access prefix, you don't need to create an additional normalization rule to accommodate the prefix.</span></span> 
  
<span data-ttu-id="44115-154">参照してください[作成ダイヤル プランの管理と](create-and-manage-dial-plans.md)ダイヤル プランを作成するには、テナントにします。</span><span class="sxs-lookup"><span data-stu-id="44115-154">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.</span></span>
  
## <a name="normalization-rules"></a><span data-ttu-id="44115-155">正規化規則</span><span class="sxs-lookup"><span data-stu-id="44115-155">Normalization rules</span></span>

<span data-ttu-id="44115-p110">正規化ルールは、さまざまな形式で表した電話番号の変換方法を定義します。同じ数の文字列を解釈され、ダイヤルしたロケールによって異なる方法で、翻訳可能性があります。正規化ルールをユーザーが内部または外部の省略形の番号をダイヤルする必要がある場合に必要なことがあります。</span><span class="sxs-lookup"><span data-stu-id="44115-p110">Normalization rules define how phone numbers expressed in various formats are to be translated. The same number string may be interpreted and translated differently, depending on the locale from which it is dialed. Normalization rules may be necessary if users need to be able to dial abbreviated internal or external numbers.</span></span>
  
<span data-ttu-id="44115-p111">ダイヤル プランには、1 つまたは複数の正規化ルールを割り当てる必要があります。正規化ルールは、テナント ダイヤル プランで表示される順序は重要な上から下から一致します。たとえば、テナント ダイヤル プランに 10 正規化ルールがある場合は、ダイヤルイン番号一致するロジックが行われます正規化の最初のルールを開始し、2 番目、一致するものがない場合などです。一致する場合は、そのルールを使用して定義されているその他のルールに一致するには、残存作業時間がありません。指定されたテナント ダイヤル プランで最大 25 の正規化ルールがあります。</span><span class="sxs-lookup"><span data-stu-id="44115-p111">One or more normalization rules must be assigned to the dial plan. Normalization rules are matched from top to bottom, so the order in which they appear in a tenant dial plan is important. For example, if a tenant dial plan has 10 normalization rules, the dialed number matching logic will be tried starting with the first normalization rule, if there isn't a match then the second, and so forth. If a match is made, that rule is used and there is no effort to match any other rules that are defined. There can be a maximum of 25 normalization rules in a given tenant dial plan.</span></span>
  
### <a name="determining-the-required-normalization-rules"></a><span data-ttu-id="44115-164">必要な正規化ルールを特定します。</span><span class="sxs-lookup"><span data-stu-id="44115-164">Determining the required normalization rules</span></span>

<span data-ttu-id="44115-p112">そのテナント ダイヤル プランの結合し、効果的に特定のユーザーのサービスの国ダイヤル プランは、サービス国ダイヤル プランの正規化ルールは、どのテナント ダイヤル正規化ルールが必要なプランを決定するために評価される必要がある可能性があります。このため、 **Get CsEffectiveTenantDialPlan**コマンドレットを使用できます。コマンドレットが入力パラメーターと、ユーザーの id は、ユーザーに適用されるすべての正規化のルールが返されます。</span><span class="sxs-lookup"><span data-stu-id="44115-p112">Because any tenant dial plan is effectively merged with a given user's service country dial plan it, it is likely that the service country dial plan's normalization rules need to be evaluated in order to determine which tenant dial plan normalization rules are needed. The **Get-CsEffectiveTenantDialPlan** cmdlet can be used for this purpose. The cmdlet takes the user's identity as the input parameter and will return all normalization rules that are applicable to the user.</span></span>
  
### <a name="creating-normalization-rules"></a><span data-ttu-id="44115-168">正規化ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="44115-168">Creating normalization rules</span></span>

<span data-ttu-id="44115-p113">正規化ルールでは、.NET Framework 正規表現を使用してサーバーを使用してダイヤル リバース番号の検索を実行するため、E.164 形式の文字列を変換する数値の一致パターンを指定します。一致の正規表現と一致する場合でもへの変換を指定して、正規化のルールを作成することができます。完了したら、正規化ルールが期待どおりに動作することを確認するテスト数を入力できます。</span><span class="sxs-lookup"><span data-stu-id="44115-p113">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format for the purpose of performing reverse number lookup. Normalization rules can be created by specifying the regular expression for the match and the translation to be done when a match is found. When you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>
  
<span data-ttu-id="44115-172">詳細については、.NET Framework 正規表現を使用して、 [.NET Framework 正規表現](https://go.microsoft.com/fwlink/p/?linkId=140927)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44115-172">For details about using .NET Framework regular expressions, see [.NET Framework Regular Expressions](https://go.microsoft.com/fwlink/p/?linkId=140927).</span></span>
  
<span data-ttu-id="44115-173">参照してください[作成ダイヤル プランの管理と](create-and-manage-dial-plans.md)テナントに対応するルール ダイヤル プランを作成および管理正規化します。</span><span class="sxs-lookup"><span data-stu-id="44115-173">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage normalization rules for your tenant dial plans.</span></span>
  
### <a name="sample-normalization-rules"></a><span data-ttu-id="44115-174">サンプルの正規化ルール</span><span class="sxs-lookup"><span data-stu-id="44115-174">Sample normalization rules</span></span>

<span data-ttu-id="44115-p114">次の表では、.NET Framework 正規表現として記述されているサンプルの正規化ルールが表示されます。サンプルのみの例は、独自の正規化ルールを作成するための規定参照を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="44115-p114">The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>
  
 <span data-ttu-id="44115-177">**.NET Framework 正規表現を使用して正規化ルール**</span><span class="sxs-lookup"><span data-stu-id="44115-177">**Normalization rules using .NET Framework regular expressions**</span></span>
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="44115-178">**ルールの名前**</span><span class="sxs-lookup"><span data-stu-id="44115-178">**Rule name**</span></span> <br/> |<span data-ttu-id="44115-179">**{Description}**</span><span class="sxs-lookup"><span data-stu-id="44115-179">**Description**</span></span> <br/> |<span data-ttu-id="44115-180">**番号のパターン**</span><span class="sxs-lookup"><span data-stu-id="44115-180">**Number pattern**</span></span> <br/> |<span data-ttu-id="44115-181">**翻訳**</span><span class="sxs-lookup"><span data-stu-id="44115-181">**Translation**</span></span> <br/> |<span data-ttu-id="44115-182">**{例}**</span><span class="sxs-lookup"><span data-stu-id="44115-182">**Example**</span></span> <br/> |
|<span data-ttu-id="44115-183">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="44115-183">4digitExtension</span></span>  <br/> |<span data-ttu-id="44115-184">4 桁の拡張子に変換します。</span><span class="sxs-lookup"><span data-stu-id="44115-184">Translates 4-digit extensions.</span></span>  <br/> |<span data-ttu-id="44115-185">^ (\\d {4}) $</span><span class="sxs-lookup"><span data-stu-id="44115-185">^(\\d{4})$</span></span>  <br/> |<span data-ttu-id="44115-186">+ 1425555$ 1</span><span class="sxs-lookup"><span data-stu-id="44115-186">+1425555$1</span></span>  <br/> |<span data-ttu-id="44115-187">0100 は、+14255550100 に変換します。</span><span class="sxs-lookup"><span data-stu-id="44115-187">0100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="44115-188">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="44115-188">5digitExtension</span></span>  <br/> |<span data-ttu-id="44115-189">5 桁の拡張子に変換します。</span><span class="sxs-lookup"><span data-stu-id="44115-189">Translates 5-digit extensions.</span></span>  <br/> |<span data-ttu-id="44115-190">^5 (\\d {4}) $</span><span class="sxs-lookup"><span data-stu-id="44115-190">^5(\\d{4})$</span></span>  <br/> |<span data-ttu-id="44115-191">+ 1425555$ 1</span><span class="sxs-lookup"><span data-stu-id="44115-191">+1425555$1</span></span>  <br/> |<span data-ttu-id="44115-192">50100 は、+14255550100 に変換します。</span><span class="sxs-lookup"><span data-stu-id="44115-192">50100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="44115-193">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="44115-193">7digitcallingRedmond</span></span>  <br/> |<span data-ttu-id="44115-194">Redmond ローカル番号に 7 桁の数値に変換します。</span><span class="sxs-lookup"><span data-stu-id="44115-194">Translates 7-digit numbers to Redmond local numbers.</span></span>  <br/> |<span data-ttu-id="44115-195">^ (\\d 7 {0}) $</span><span class="sxs-lookup"><span data-stu-id="44115-195">^(\\d{7})$</span></span>  <br/> |<span data-ttu-id="44115-196">+1425$ 1</span><span class="sxs-lookup"><span data-stu-id="44115-196">+1425$1</span></span>  <br/> |<span data-ttu-id="44115-197">5550100 は、+14255550100 に変換します。</span><span class="sxs-lookup"><span data-stu-id="44115-197">5550100 is translated to +14255550100</span></span>  <br/>|
|<span data-ttu-id="44115-198">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="44115-198">RedmondOperator</span></span>  <br/> |<span data-ttu-id="44115-199">Redmond 演算子を 0 に変換します。</span><span class="sxs-lookup"><span data-stu-id="44115-199">Translates 0 to Redmond Operator.</span></span>  <br/> |<span data-ttu-id="44115-200">^0$</span><span class="sxs-lookup"><span data-stu-id="44115-200">^0$</span></span>  <br/> |<span data-ttu-id="44115-201">+14255550100</span><span class="sxs-lookup"><span data-stu-id="44115-201">+14255550100</span></span>  <br/> |<span data-ttu-id="44115-202">0 は、+14255550100 に変換します。</span><span class="sxs-lookup"><span data-stu-id="44115-202">0 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="44115-203">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="44115-203">RedmondSitePrefix</span></span>  <br/> |<span data-ttu-id="44115-204">ネットワーク上のプレフィックス (6) とレドモンド サイト コード (222) の数値に変換します。</span><span class="sxs-lookup"><span data-stu-id="44115-204">Translates numbers with on-net prefix (6) and Redmond site code (222).</span></span>  <br/> |<span data-ttu-id="44115-205">^6222 (\\d {4}) $</span><span class="sxs-lookup"><span data-stu-id="44115-205">^6222(\\d{4})$</span></span>  <br/> |<span data-ttu-id="44115-206">+ 1425555$ 1</span><span class="sxs-lookup"><span data-stu-id="44115-206">+1425555$1</span></span>  <br/> |<span data-ttu-id="44115-207">62220100 は、+14255550100 に変換します。</span><span class="sxs-lookup"><span data-stu-id="44115-207">62220100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="44115-208">5digitRange</span><span class="sxs-lookup"><span data-stu-id="44115-208">5digitRange</span></span>  <br/> |<span data-ttu-id="44115-209">3 ~ 7 の包括的な数字の範囲から始まる 5 桁の拡張子に変換します。</span><span class="sxs-lookup"><span data-stu-id="44115-209">Translates 5-digit extensions starting with the digit range between 3-7 inclusive.</span></span>  <br/> |<span data-ttu-id="44115-210">^ ([3 ~ 7]\\d {4}) $</span><span class="sxs-lookup"><span data-stu-id="44115-210">^([3-7]\\d{4})$</span></span>  <br/> |<span data-ttu-id="44115-211">+ 142570$ 1</span><span class="sxs-lookup"><span data-stu-id="44115-211">+142570$1</span></span>  <br/> |<span data-ttu-id="44115-212">54567 は、+14255554567 に変換します。</span><span class="sxs-lookup"><span data-stu-id="44115-212">54567 is translated to +14255554567</span></span>  <br/> |
|<span data-ttu-id="44115-213">PrefixAdded</span><span class="sxs-lookup"><span data-stu-id="44115-213">PrefixAdded</span></span>  <br/> |<span data-ttu-id="44115-214">最初と 3 桁の制限付き 9 の数字の前にある国接頭辞を追加します。</span><span class="sxs-lookup"><span data-stu-id="44115-214">Adds a country prefix in front of a 9 digit number with restrictions on the first and third digits.</span></span>  <br/> |<span data-ttu-id="44115-215">^ ([2 ~ 9]\\d\\d [2 ~ 9]\\d 6 {0}) $</span><span class="sxs-lookup"><span data-stu-id="44115-215">^([2-9]\\d\\d[2-9]\\d{6})$</span></span>  <br/> |<span data-ttu-id="44115-216">1$ 1</span><span class="sxs-lookup"><span data-stu-id="44115-216">1$1</span></span>  <br/> |<span data-ttu-id="44115-217">4255554567 は、14255554567 に変換します。</span><span class="sxs-lookup"><span data-stu-id="44115-217">4255554567 is translated to 14255554567</span></span>  <br/> |
|<span data-ttu-id="44115-218">NoTranslation</span><span class="sxs-lookup"><span data-stu-id="44115-218">NoTranslation</span></span>  <br/> |<span data-ttu-id="44115-219">5 桁の数字は変換がないと一致します。</span><span class="sxs-lookup"><span data-stu-id="44115-219">Match 5 digits but no translation.</span></span>  <br/> |<span data-ttu-id="44115-220">^ (\\d {5}) $</span><span class="sxs-lookup"><span data-stu-id="44115-220">^(\\d{5})$</span></span>  <br/> |<span data-ttu-id="44115-221">$1</span><span class="sxs-lookup"><span data-stu-id="44115-221">$1</span></span>  <br/> |<span data-ttu-id="44115-222">34567 は、34567 に変換します。</span><span class="sxs-lookup"><span data-stu-id="44115-222">34567 is translated to 34567</span></span>  <br/> |
   
 <span data-ttu-id="44115-223">**Redmond ダイヤル プランの上に示す正規化ルールに基づいています。**</span><span class="sxs-lookup"><span data-stu-id="44115-223">**Redmond dial plan based on normalization rules shown above.**</span></span>
  
<span data-ttu-id="44115-p115">次の表は、レドモンド、Washington、米国、前の表に示すように、正規化ルールに基づいてダイヤル プランの例を示します。|:-----| |**ダイヤル プランのレドモンド**</span><span class="sxs-lookup"><span data-stu-id="44115-p115">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table. |:-----| |**Redmond dial plan**</span></span> <br/> <span data-ttu-id="44115-226">| | 5digitExtension</span><span class="sxs-lookup"><span data-stu-id="44115-226">| |5digitExtension</span></span> <br/> <span data-ttu-id="44115-227">| | 7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="44115-227">| |7digitcallingRedmond</span></span> <br/> <span data-ttu-id="44115-228">| |RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="44115-228">| |RedmondSitePrefix</span></span> <br/> <span data-ttu-id="44115-229">| |RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="44115-229">| |RedmondOperator</span></span> <br/> |
   
> [!NOTE]
> <span data-ttu-id="44115-p116">上の表に示すように、正規化ルール名が、スペースを含めませんが選択肢の問題です。たとえば、テーブルの最初の名前が書き込まれている「5 桁の拡張子」または「5 桁の内線番号」も有効であるとします。</span><span class="sxs-lookup"><span data-stu-id="44115-p116">The normalization rules names shown in the preceding table do not include spaces, but this is a matter of choice. The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="44115-232">関連トピック</span><span class="sxs-lookup"><span data-stu-id="44115-232">Related topics</span></span>
[<span data-ttu-id="44115-233">作成してダイヤル プランを管理します。</span><span class="sxs-lookup"><span data-stu-id="44115-233">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)

[<span data-ttu-id="44115-234">Skype Business および Microsoft チーム アドオン ライセンスを許可します。</span><span class="sxs-lookup"><span data-stu-id="44115-234">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

[<span data-ttu-id="44115-235">電話番号のよく寄せられる質問を転送します。</span><span class="sxs-lookup"><span data-stu-id="44115-235">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="44115-236">さまざまなプランの呼び出し用の電話番号</span><span class="sxs-lookup"><span data-stu-id="44115-236">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="44115-237">組織の電話番号を管理します。</span><span class="sxs-lookup"><span data-stu-id="44115-237">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="44115-238">緊急の呼び出し元の条項および条件</span><span class="sxs-lookup"><span data-stu-id="44115-238">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="44115-239">Skype for Business Online: 緊急発信免責事項のラベル</span><span class="sxs-lookup"><span data-stu-id="44115-239">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)
