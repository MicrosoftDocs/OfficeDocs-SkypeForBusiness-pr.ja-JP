---
title: Skype のビジネス サーバーのダイヤルイン会議を構成します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: '概要: は、Skype のビジネス サーバーのダイヤルイン会議を構成する方法については、このトピックを読みます。'
ms.openlocfilehash: dbd851f416fb3bc91a556753ce33d2ef80976ff2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881508"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="fc44c-103">Skype のビジネス サーバーのダイヤルイン会議を構成します。</span><span class="sxs-lookup"><span data-stu-id="fc44c-103">Configure dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="fc44c-104">**の概要:** Skype のビジネス サーバーのダイヤルイン会議を構成する方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc44c-104">**Summary:** Read this topic to learn how to configure dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="fc44c-105">会議ワークロードおよびダイヤルイン会議の選択を含むトポロジを作成した後は、ダイヤルイン会議を構成する追加の手順を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc44c-105">After you have created a topology that includes the conferencing workload and selected dial-in conferencing, you must perform additional steps to configure dial-in conferencing.</span></span> <span data-ttu-id="fc44c-106">確認すること、このトピックを読む前に読んだ[ビジネス サーバーの Skype では、ダイヤルイン会議の計画](../../plan-your-deployment/conferencing/dial-in-conferencing.md)、[ビジネス サーバーの Skype での会議のためのハードウェアおよびソフトウェア要件](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)、および[展開フローチャートとチェックリストダイヤルイン会議](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing)。</span><span class="sxs-lookup"><span data-stu-id="fc44c-106">Before you read this topic, be sure you have read [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [Hardware and software requirements for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md), and the [Deployment flowchart and checklist for dial-in conferencing](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing).</span></span> 
  
<span data-ttu-id="fc44c-107">ダイヤルイン会議を構成するには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc44c-107">To configure dial-in conferencing, you must perform the following tasks:</span></span>
  
- [<span data-ttu-id="fc44c-108">Configure dial plans</span><span class="sxs-lookup"><span data-stu-id="fc44c-108">Configure dial plans</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [<span data-ttu-id="fc44c-109">Configure dial-in conferencing regions</span><span class="sxs-lookup"><span data-stu-id="fc44c-109">Configure dial-in conferencing regions</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [<span data-ttu-id="fc44c-110">Configure dial-in access numbers</span><span class="sxs-lookup"><span data-stu-id="fc44c-110">Configure dial-in access numbers</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [<span data-ttu-id="fc44c-111">Configure conferencing policies</span><span class="sxs-lookup"><span data-stu-id="fc44c-111">Configure conferencing policies</span></span>](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [<span data-ttu-id="fc44c-112">Assign a Line URI to a user account</span><span class="sxs-lookup"><span data-stu-id="fc44c-112">Assign a Line URI to a user account</span></span>](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
<span data-ttu-id="fc44c-113">また、以下のオプションのタスクを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="fc44c-113">In addition, you may perform the following optional tasks.</span></span> <span data-ttu-id="fc44c-114">これらの省略可能なタスクの詳細については、 [Skype のビジネス サーバーにダイヤルイン会議の管理](../../manage/conferencing/dial-in-conferencing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc44c-114">For more information about these optional tasks, see [Manage dial-in conferencing in Skype for Business Server](../../manage/conferencing/dial-in-conferencing.md).</span></span>
  
- <span data-ttu-id="fc44c-115">ダイヤルイン会議の PIN ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="fc44c-115">Manage PIN policies for dial-in conferencing</span></span>
    
- <span data-ttu-id="fc44c-116">DTMF コマンドの主要なマッピングの管理</span><span class="sxs-lookup"><span data-stu-id="fc44c-116">Manage key mapping for DTMF commands</span></span>
    
- <span data-ttu-id="fc44c-117">電話会議ディレクトリの作成</span><span class="sxs-lookup"><span data-stu-id="fc44c-117">Create conference directories</span></span>
    
- <span data-ttu-id="fc44c-118">電話会議への入退出のアナウンスの管理</span><span class="sxs-lookup"><span data-stu-id="fc44c-118">Manage conference join and leave announcements</span></span>
    
- <span data-ttu-id="fc44c-119">ダイヤルイン会議の設定のテスト</span><span class="sxs-lookup"><span data-stu-id="fc44c-119">Test dial-in conferencing settings</span></span>
    
- <span data-ttu-id="fc44c-120">ダイヤルイン ユーザーへのようこそメールの送信</span><span class="sxs-lookup"><span data-stu-id="fc44c-120">Send welcome mail to dial-in users</span></span>
    
## <a name="configure-dial-plans"></a><span data-ttu-id="fc44c-121">ダイヤル プランを構成する</span><span class="sxs-lookup"><span data-stu-id="fc44c-121">Configure dial plans</span></span>
<span data-ttu-id="fc44c-122"><a name="BKMK_ConfigureDialPlans"> </a></span><span class="sxs-lookup"><span data-stu-id="fc44c-122"></span></span>

<span data-ttu-id="fc44c-123">ダイヤルイン会議を展開するときは、作成またはルーティングのダイヤルインのアクセス電話番号を 1 つまたは複数のダイヤル プランを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc44c-123">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="fc44c-124">ダイヤル プランごとに少なくとも 1 つの正規化規則--E.164 形式の完全な電話番号に電話の拡張機能を変換するルールが含まれていることも確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc44c-124">You must also make sure that each dial plan contains at least one normalization rule--a rule that converts telephone extensions into complete phone numbers in E.164 format.</span></span> 
  
<span data-ttu-id="fc44c-p104">ダイヤルイン会議のユーザーは、自らの暗証番号 (PIN) と電話番号を入力することで、認証されたエンタープライズ ユーザーとして会議に参加します。内線番号を総合的な電話番号に変化する正規化ルールを管理者が定義する必要があり、その結果、ユーザーは内線番号のみを入力したときに認証を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="fc44c-p104">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number. You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>
  
<span data-ttu-id="fc44c-127">ダイヤルイン会議のダイヤル プランをセットアップするには</span><span class="sxs-lookup"><span data-stu-id="fc44c-127">To set up dial plans for dial-in conferencing:</span></span>
  
- <span data-ttu-id="fc44c-128">エンタープライズ VoIP を展開するかどうかに関係なく、グローバル ダイヤル プランを変更して、ダイヤルイン会議の地域を追加し、正規化ルールによりダイヤルイン アクセス番号が正確に変換されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fc44c-128">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="fc44c-129">詳細についてを参照してください[を作成するまたはビジネス サーバーの Skype のダイヤル プランを変更する](../../deploy/deploy-enterprise-voice/dial-plans.md)です。</span><span class="sxs-lookup"><span data-stu-id="fc44c-129">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="fc44c-130">エンタープライズ VoIP が展開されていない場合は、ダイヤルイン会議のアクセス電話番号に対応するダイヤル プランを作成します。</span><span class="sxs-lookup"><span data-stu-id="fc44c-130">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="fc44c-131">ダイヤルイン会議の地域を忘れないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="fc44c-131">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="fc44c-132">詳細についてを参照してください[を作成するまたはビジネス サーバーの Skype のダイヤル プランを変更する](../../deploy/deploy-enterprise-voice/dial-plans.md)です。</span><span class="sxs-lookup"><span data-stu-id="fc44c-132">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="fc44c-133">エンタープライズ VoIP が展開されている場合は、必要に応じてエンタープライズ VoIP を変更して地域を含め、ダイヤルイン アクセス番号のための適切な正規化ルールを使用します。</span><span class="sxs-lookup"><span data-stu-id="fc44c-133">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="fc44c-134">また、ダイヤルイン アクセス番号のみのために使用する、専用のダイヤル プランを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="fc44c-134">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="fc44c-135">詳細についてを参照してください[を作成するまたはビジネス サーバーの Skype のダイヤル プランを変更する](../../deploy/deploy-enterprise-voice/dial-plans.md)です。</span><span class="sxs-lookup"><span data-stu-id="fc44c-135">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
<span data-ttu-id="fc44c-136">正規化ルールを作成する方法についてを参照してください[を作成するまたはビジネス用の Skype の正規化ルールを変更する](../../deploy/deploy-enterprise-voice/normalization-rules.md)です。</span><span class="sxs-lookup"><span data-stu-id="fc44c-136">For details about creating normalization rules, see [Create or modify a normalization rule in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span></span>
  
## <a name="configure-dial-in-conferencing-regions"></a><span data-ttu-id="fc44c-137">ダイヤルイン会議の地域の構成</span><span class="sxs-lookup"><span data-stu-id="fc44c-137">Configure dial-in conferencing regions</span></span>
<span data-ttu-id="fc44c-138"><a name="BKMK_ConfigureDialInRegions"> </a></span><span class="sxs-lookup"><span data-stu-id="fc44c-138"></span></span>

<span data-ttu-id="fc44c-p108">ダイヤル プランをセットアップするときに、そのダイヤル プランに適用されるダイヤルイン会議の地域を指定します。ダイヤルイン会議の地域は、ダイヤルイン会議アクセス番号を適切なダイヤル プランに関連付けます。ダイヤルイン アクセス番号を作成するときには、アクセス番号と適切なダイヤル プランを関連付ける地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc44c-p108">When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan. The dial-in conferencing region associates dial-in conferencing access numbers with the appropriate dial plan. When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span> 
  
<span data-ttu-id="fc44c-142">すべてのダイヤル プランに地域を指定することは重要であるため、すべてのダイヤル プランに会議の地域があることを確認するようにお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fc44c-142">Because it important to specify a region for all dial plans, we recommend that you verify that all dial plans have conferencing regions.</span></span> 
  
<span data-ttu-id="fc44c-143">すべてのダイヤルイン会議のダイヤル プランで地域が設定されているかどうかを確認するには、**Get-CsDialPlan** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fc44c-143">To verify whether the region is set for all dial-in conferencing dial plans, use the **Get-CsDialPlan** cmdlet.</span></span> <span data-ttu-id="fc44c-144">ダイヤル プランに地域がない場合は、**Set-CsDialPlan** コマンドレットを使用して地域を設定できます。</span><span class="sxs-lookup"><span data-stu-id="fc44c-144">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="fc44c-145">既存のダイヤル プラン内の領域を更新するのには Skype ビジネス サーバーのコントロール パネルを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="fc44c-145">You can also use Skype for Business Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="fc44c-146">Skype のビジネス サーバーのコントロール パネルの使用に関する詳細についてを参照してください[を作成するまたはビジネス サーバーの Skype のダイヤル プランを変更する](../../deploy/deploy-enterprise-voice/dial-plans.md)です。</span><span class="sxs-lookup"><span data-stu-id="fc44c-146">For details about using Skype for Business Server Control Panel, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="fc44c-147">ダイヤル プランで地域プロパティが設定されているかどうかを確認するには</span><span class="sxs-lookup"><span data-stu-id="fc44c-147">To verify whether dial plans have the region property set</span></span>

1. <span data-ttu-id="fc44c-148">RTCUniversalServerAdmins グループのメンバーか、**Cs-VoiceAdministrator**、**Cs-ServerAdministrator**、または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="fc44c-148">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="fc44c-149">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc44c-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="fc44c-150">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fc44c-150">Run the following at the command prompt:</span></span>
    
   ```
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   <span data-ttu-id="fc44c-151">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fc44c-151">For example:</span></span>
    
   ```
   Get-CsDialPlan
   ```

   <span data-ttu-id="fc44c-152">この例では、組織で構成されているすべてのダイヤル プランが戻されます。</span><span class="sxs-lookup"><span data-stu-id="fc44c-152">In this example, all the dial plans configured for your organization are returned.</span></span>
    
4. <span data-ttu-id="fc44c-153">戻されたダイヤル プランを確認して、ダイヤルイン会議の地域が含まれていないものを識別します。</span><span class="sxs-lookup"><span data-stu-id="fc44c-153">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> 
    
<span data-ttu-id="fc44c-154">詳細については、 [Get CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc44c-154">For more information, see [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps).</span></span>
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="fc44c-155">ダイヤル プランの地域プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="fc44c-155">To set the region property for a dial plan</span></span>

1. <span data-ttu-id="fc44c-156">RTCUniversalServerAdmins グループのメンバーか、**Cs-VoiceAdministrator**、**Cs-ServerAdministrator**、または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="fc44c-156">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="fc44c-157">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc44c-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="fc44c-158">ダイヤルイン会議の地域が含まれていないダイヤル プランで、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="fc44c-158">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
   ```
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   <span data-ttu-id="fc44c-159">例:</span><span class="sxs-lookup"><span data-stu-id="fc44c-159">For example:</span></span>
    
   ```
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   <span data-ttu-id="fc44c-160">この例では、Redmond という Identity を持つダイヤル プランを変更して、DialinConferencingRegion プロパティを "US West Coast" に設定します。</span><span class="sxs-lookup"><span data-stu-id="fc44c-160">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> 
    
<span data-ttu-id="fc44c-161">詳細については、[一連の CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc44c-161">For more information, see [Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps).</span></span>
  
## <a name="configure-dial-in-access-numbers"></a><span data-ttu-id="fc44c-162">ダイヤルイン アクセス番号を構成する</span><span class="sxs-lookup"><span data-stu-id="fc44c-162">Configure dial-in access numbers</span></span>
<span data-ttu-id="fc44c-163"><a name="BKMK_ConfigureDialInAccessNumbers"> </a></span><span class="sxs-lookup"><span data-stu-id="fc44c-163"></span></span>

<span data-ttu-id="fc44c-164">ダイヤルイン会議を展開するときには、ユーザーが公衆交換電話網 (PSTN) からダイヤルして電話会議のオーディオ部分に参加するための電話番号を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc44c-164">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="fc44c-165">それらのダイヤルイン アクセス番号は、ミーティングの招待状と [ダイヤルイン会議の設定] Web ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc44c-165">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
  
<span data-ttu-id="fc44c-166">ダイヤルイン アクセス番号を作成する前に、まずダイヤルイン会議の域を計画し、その地域のダイヤル プランを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc44c-166">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="fc44c-167">領域に関する詳細については、 [Skype のビジネス サーバーにダイヤルイン会議の計画](../../plan-your-deployment/conferencing/dial-in-conferencing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc44c-167">For details about regions, see [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md).</span></span> <span data-ttu-id="fc44c-168">ダイヤルイン会議の計画をダイヤルすると、構成の詳細について参照してください[を作成するまたはビジネス サーバーの Skype のダイヤル プランを変更する](../../deploy/deploy-enterprise-voice/dial-plans.md)です。</span><span class="sxs-lookup"><span data-stu-id="fc44c-168">For details about configuring dial plans for dial-in conferencing, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="fc44c-p112">新しいダイヤルイン アクセス番号は、そのアクセス番号の Active Directory ドメイン サービス (AD DS) レプリケーションが完了するまで使用できません。レプリケーションが完了するまでに数時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="fc44c-p112">You cannot use a new dial-in access number until Active Directory Domain Services (AD DS) replication of that access number is complete. Replication can take several hours to complete.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fc44c-171">ダイヤルイン アクセス番号を作成した後は、Active Directory の連絡先オブジェクトの表示名を変更し、ユーザーが正しいアクセス番号を識別しやすくすることができます。</span><span class="sxs-lookup"><span data-stu-id="fc44c-171">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="fc44c-172">表示名を変更するには、[セット CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fc44c-172">To modify the display name, use the [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="fc44c-173">Active Directory のオブジェクトは手動で変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="fc44c-173">You should not modify Active Directory objects manually.</span></span>
  
### <a name="to-create-a-dial-in-access-number"></a><span data-ttu-id="fc44c-174">ダイヤルイン アクセス番号を作成するには</span><span class="sxs-lookup"><span data-stu-id="fc44c-174">To create a dial-in access number</span></span>

1. <span data-ttu-id="fc44c-175">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="fc44c-175">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="fc44c-176">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="fc44c-176">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="fc44c-177">左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc44c-177">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="fc44c-178">[**ダイヤルイン アクセス番号**] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fc44c-178">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="fc44c-179">[**新規**] をクリックして、[**新規ダイヤルイン アクセス番号**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="fc44c-179">Click **New** to open **New Dial-in Access Number**.</span></span>
    
   - <span data-ttu-id="fc44c-180">リストでダイヤルイン アクセス番号のいずれかをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc44c-180">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="fc44c-p114">検索フィールドを使用してダイヤルイン アクセス番号のリストの列の内容を検索しても、結果が予想どおりにならない場合があります。代わりに、対象の列を基にしてリストを並べ替えて、表示または変更するダイヤルイン アクセス番号を特定してください。</span><span class="sxs-lookup"><span data-stu-id="fc44c-p114">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="fc44c-p115">[**表示番号**] に、公衆交換電話網 (PSTN) 電話を使用するユーザーが会議に参加するときにダイヤルする、電話番号を入力します。この番号は、会議出席依頼とダイヤルイン会議設定 Web ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc44c-p115">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference. This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="fc44c-185">[**表示名**] に、ダイヤルイン アクセス番号の説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="fc44c-185">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="fc44c-186">これは、ビジネスの検索結果の Skype でダイヤルイン アクセス番号に関連付けられている名前です。</span><span class="sxs-lookup"><span data-stu-id="fc44c-186">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span> <span data-ttu-id="fc44c-187">この名前は、ユーザーがアクセス番号を呼び出すとき、クライアントで表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc44c-187">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="fc44c-p117">[**回線 URI**] に、ダイヤルイン アクセス番号の E.164 番号を、電話番号の前に + 記号を付加し、スペースを含めない電話 URI 形式で入力します。たとえば、tel:+14255550200 のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fc44c-p117">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces. For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fc44c-190">同じ回線 URI を、別のダイヤルイン会議アクセス番号で再利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fc44c-190">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="fc44c-191">[**SIP URI**] で、次の操作を行ってください。</span><span class="sxs-lookup"><span data-stu-id="fc44c-191">In **SIP URI**, do the following:</span></span>
    
   - <span data-ttu-id="fc44c-192">テキスト ボックスで、このダイヤルイン会議アクセス番号の一意の SIP URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="fc44c-192">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="fc44c-193">この SIP URI などのさまざまな場所が通知メッセージ、および以前のバージョンの Lync クライアントの呼び出しに限定されません。</span><span class="sxs-lookup"><span data-stu-id="fc44c-193">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="fc44c-p119">同じ SIP URI を、別のダイヤルイン会議アクセス番号で再利用することはできません。SIP URI を、アクセス番号の作成後に変更することはできません。SIP URI を変更する唯一の方法は、アクセス番号を削除して再作成することです。</span><span class="sxs-lookup"><span data-stu-id="fc44c-p119">The same SIP URI cannot be reused by another dial-in conferencing access number. The SIP URI cannot be modified after the access number is created. The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   - <span data-ttu-id="fc44c-197">ドロップダウン リスト ボックスで、このダイヤルイン アクセス番号をサポートする会議アテンダント アプリケーションのドメインをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc44c-197">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="fc44c-198">[**プール**] で、このダイヤルイン アクセス番号をサポートする会議アテンダントのインスタンスを実行するプールをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc44c-198">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fc44c-199">アクセス番号の作成後にプールを変更する必要がある場合は、[Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) コマンドレットを使用するか、またはアクセス番号をいったん削除して作成し直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc44c-199">If you need to change the pool after you create the access number, you must use the [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="fc44c-200">[**第 1 言語**] で、このダイヤルイン アクセス番号の案内を再生するときに使用される言語をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc44c-200">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="fc44c-p120">第 1 言語とは、会議アテンダントが着信への応答に使用する言語のことです。サポートされている言語は、各アクセス電話番号と共に、ダイヤルイン会議の設定 Web ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc44c-p120">The primary language is the language that the Conferencing Attendant uses to answer the call. Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="fc44c-203">(オプション) [**第 2 言語 (4 つまで)**] で、[**追加**] をクリックして、このダイヤルイン アクセス番号への発信者用にサポートする 1 つ以上の追加言語を選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc44c-203">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="fc44c-p121">ダイヤルイン アクセス番号ごとに最大 4 つの第 2 言語を選択できます。ユーザーは、会議にダイヤルインする際に会議 ID を入力する前に、第 2 言語を選択できます。</span><span class="sxs-lookup"><span data-stu-id="fc44c-p121">You can choose up to four secondary languages for each dial-in access number. Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="fc44c-206">ダイヤルイン アクセス番号、**関連付けられた領域**の下の領域を追加するには、[**追加**] をクリックして、このダイヤルイン アクセス番号をダイヤル プランに関連付けられ、 **[ok]** をクリックし、1 つまたは複数の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc44c-206">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="fc44c-207">ダイヤルイン アクセス番号から地域を削除するには、[**関連付けられている地域**] で削除する地域をクリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc44c-207">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="fc44c-208">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc44c-208">Click **Commit**.</span></span>
    
## <a name="configure-conferencing-policies"></a><span data-ttu-id="fc44c-209">会議ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="fc44c-209">Configure conferencing policies</span></span>
<span data-ttu-id="fc44c-210"><a name="BKMK_ConfigureConferencingPolicies"> </a></span><span class="sxs-lookup"><span data-stu-id="fc44c-210"></span></span>

<span data-ttu-id="fc44c-p122">会議ポリシーは、参加者向けの会議機能を指定するユーザー アカウント設定です。会議ポリシーは、サイト スコープまたはユーザー スコープで作成できます。会議ポリシー設定には、会議の予約と参加の多くの側面が含まれます。複数の会議ポリシー設定で、参加者向けのダイヤルイン会議をサポートしています。ダイヤルイン会議を構成する際に、これらのフィールドが組織に適切に設定されていることを確認し、必要に応じて変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc44c-p122">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span> 
  
<span data-ttu-id="fc44c-216">会議ポリシーを構成する方法の詳細については、 [Skype ビジネス サーバーの会議ポリシーの管理](../../manage/conferencing/conferencing-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc44c-216">For more information about configuring conferencing policies, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  
## <a name="assign-a-line-uri-to-a-user-account"></a><span data-ttu-id="fc44c-217">ユーザー アカウントに回線 URI を割り当てる</span><span class="sxs-lookup"><span data-stu-id="fc44c-217">Assign a Line URI to a user account</span></span>
<span data-ttu-id="fc44c-218"><a name="BKMK_AssignaLineURI"> </a></span><span class="sxs-lookup"><span data-stu-id="fc44c-218"></span></span>

<span data-ttu-id="fc44c-219">ダイヤルイン ユーザーは各自の電話番号または内線番号、それに PIN を入力し、認証されたユーザーとして会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="fc44c-219">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="fc44c-220">テレフォニー ビジネス サーバーのユーザー アカウントの Skype で指定された**行の URI**は、認証に必要です。</span><span class="sxs-lookup"><span data-stu-id="fc44c-220">The telephony **Line URI** specified on Skype for Business Server user accounts is required for authentication.</span></span>
  
<span data-ttu-id="fc44c-221">このトピックの手順は、[**回線 URI**] を 1 つのユーザー アカウントに対して割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc44c-221">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="fc44c-222">[**回線 URI**] を複数のユーザー アカウントに対して割り当てる必要がある場合は、**Set-CsUser** コマンドレットを使用するスクリプトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fc44c-222">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="fc44c-223">**回線 URI**を複数のユーザー アカウントに割り当てるには、サンプル スクリプトの使用に関する詳細については、[複数のユーザーに回線 Uri を割り当てる](https://go.microsoft.com/fwlink/p/?linkId=196945)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc44c-223">For details about using a sample script to assign **Line URI** to multiple user accounts, see [Assign Line URIs to Multiple Users](https://go.microsoft.com/fwlink/p/?linkId=196945).</span></span>
  
1. <span data-ttu-id="fc44c-224">RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**Cs-UserAdministrator** または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="fc44c-224">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>
    
2.  <span data-ttu-id="fc44c-225">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="fc44c-225">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="fc44c-226">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc44c-226">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="fc44c-227">検索フィールドで、ダイヤルイン会議の構成を行うユーザーの名前を入力するか、[**フィルターの追加**] をクリックして検索フィールドを指定し、次に [**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc44c-227">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>
    
5. <span data-ttu-id="fc44c-228">ユーザーの名前をダブルクリックして、[**Skype for Business Server ユーザーの編集**] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="fc44c-228">Double-click the user name to open the **Edit Skype for Business Server User** dialog box.</span></span>
    
6. <span data-ttu-id="fc44c-229">[**テレフォニー**] の下の [**回線 URI**] フィールドで、正規化された一意の電話番号 (たとえば、tel:+14255550200) を入力します。</span><span class="sxs-lookup"><span data-stu-id="fc44c-229">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fc44c-230">[**回線 URI**] を指定できるのは、[**テレフォニー**] が [**PC 間のみ**]、[**エンタープライズ VoIP**]、[**リモート通話コントロール**]、または [**リモート通話コントロールのみ**] に設定されている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="fc44c-230">You can specify **Line URI** only if **Telephony** is set to **PC-to-PC only**, **Enterprise Voice**, **Remote call control** or **Remote call control only**.</span></span> 
  
7. <span data-ttu-id="fc44c-231">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc44c-231">Click **Commit**.</span></span>
    

