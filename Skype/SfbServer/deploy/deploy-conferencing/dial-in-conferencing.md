---
title: Skype for Business Server でのダイヤルイン会議の構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: '概要: Skype for Business Server でダイヤルイン会議を構成する方法については、このトピックを参照してください。'
ms.openlocfilehash: 5f618e22cc45585baddf1e8d6090b9e211dc5681
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103853"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="51e29-103">Skype for Business Server でのダイヤルイン会議の構成</span><span class="sxs-lookup"><span data-stu-id="51e29-103">Configure dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="51e29-104">**概要:** Skype for Business Server でダイヤルイン会議を構成する方法については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="51e29-104">**Summary:** Read this topic to learn how to configure dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="51e29-105">会議ワークロードと選択されたダイヤルイン会議を含むトポロジを作成したら、ダイヤルイン会議を構成するための追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51e29-105">After you have created a topology that includes the conferencing workload and selected dial-in conferencing, you must perform additional steps to configure dial-in conferencing.</span></span> <span data-ttu-id="51e29-106">このトピックを読む前に[、「Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md)でのダイヤルイン会議の計画」、Skype for Business [Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)での会議のハードウェアとソフトウェアの要件[](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing)、およびダイヤルイン会議の展開フローチャートとチェックリストを参照してください。</span><span class="sxs-lookup"><span data-stu-id="51e29-106">Before you read this topic, be sure you have read [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [Hardware and software requirements for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md), and the [Deployment flowchart and checklist for dial-in conferencing](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing).</span></span> 
  
<span data-ttu-id="51e29-107">ダイヤルイン会議を構成するには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51e29-107">To configure dial-in conferencing, you must perform the following tasks:</span></span>
  
- [<span data-ttu-id="51e29-108">ダイヤル プランを構成する</span><span class="sxs-lookup"><span data-stu-id="51e29-108">Configure dial plans</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [<span data-ttu-id="51e29-109">ダイヤルイン会議地域の構成</span><span class="sxs-lookup"><span data-stu-id="51e29-109">Configure dial-in conferencing regions</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [<span data-ttu-id="51e29-110">ダイヤルイン アクセス番号を構成する</span><span class="sxs-lookup"><span data-stu-id="51e29-110">Configure dial-in access numbers</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [<span data-ttu-id="51e29-111">会議ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="51e29-111">Configure conferencing policies</span></span>](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [<span data-ttu-id="51e29-112">ユーザー アカウントに回線 URI を割り当てる</span><span class="sxs-lookup"><span data-stu-id="51e29-112">Assign a Line URI to a user account</span></span>](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
<span data-ttu-id="51e29-113">さらに、次のオプション タスクを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="51e29-113">In addition, you may perform the following optional tasks.</span></span> <span data-ttu-id="51e29-114">これらのオプション タスクの詳細については [、「Manage dial-in conferencing in Skype for Business Server」を参照してください](../../manage/conferencing/dial-in-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="51e29-114">For more information about these optional tasks, see [Manage dial-in conferencing in Skype for Business Server](../../manage/conferencing/dial-in-conferencing.md).</span></span>
  
- <span data-ttu-id="51e29-115">ダイヤルイン会議の PIN ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="51e29-115">Manage PIN policies for dial-in conferencing</span></span>
    
- <span data-ttu-id="51e29-116">DTMF コマンドのキー マッピングを管理する</span><span class="sxs-lookup"><span data-stu-id="51e29-116">Manage key mapping for DTMF commands</span></span>
    
- <span data-ttu-id="51e29-117">会議ディレクトリの作成</span><span class="sxs-lookup"><span data-stu-id="51e29-117">Create conference directories</span></span>
    
- <span data-ttu-id="51e29-118">会議への参加と退会のお知らせを管理する</span><span class="sxs-lookup"><span data-stu-id="51e29-118">Manage conference join and leave announcements</span></span>
    
- <span data-ttu-id="51e29-119">ダイヤルイン会議の設定をテストする</span><span class="sxs-lookup"><span data-stu-id="51e29-119">Test dial-in conferencing settings</span></span>
    
- <span data-ttu-id="51e29-120">ダイヤルイン ユーザーにウェルカム メールを送信する</span><span class="sxs-lookup"><span data-stu-id="51e29-120">Send welcome mail to dial-in users</span></span>
    
## <a name="configure-dial-plans"></a><span data-ttu-id="51e29-121">ダイヤル プランを構成する</span><span class="sxs-lookup"><span data-stu-id="51e29-121">Configure dial plans</span></span>
<span data-ttu-id="51e29-122"><a name="BKMK_ConfigureDialPlans"> </a></span><span class="sxs-lookup"><span data-stu-id="51e29-122"><a name="BKMK_ConfigureDialPlans"> </a></span></span>

<span data-ttu-id="51e29-123">ダイヤルイン会議を展開するときは、ダイヤルインのアクセス電話番号をルーティングするために、1 つ以上のダイヤル プランを作成または変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51e29-123">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="51e29-124">また、各ダイヤル プランに少なくとも 1 つの正規化ルール (内線番号を E.164 形式の完全な電話番号に変換するルール) が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="51e29-124">You must also make sure that each dial plan contains at least one normalization rule--a rule that converts telephone extensions into complete phone numbers in E.164 format.</span></span> 
  
<span data-ttu-id="51e29-125">ダイヤルイン会議のユーザーは、自分の暗証番号 (PIN) と電話番号を入力して、認証済みのエンタープライズ ユーザーとして会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="51e29-125">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number.</span></span> <span data-ttu-id="51e29-126">内線番号を完全な電話番号に変換する正規化ルールが必要なのは、内線番号だけの入力でユーザーを認証できるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="51e29-126">You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>
  
<span data-ttu-id="51e29-127">ダイヤルイン会議のダイヤル プランを設定するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="51e29-127">To set up dial plans for dial-in conferencing:</span></span>
  
- <span data-ttu-id="51e29-128">エンタープライズ VoIP を展開するかどうかに関係ない場合は、グローバル ダイヤル プランを変更してダイヤルイン会議地域を追加し、正規化ルールによってダイヤルイン アクセス番号が正確に変換されるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="51e29-128">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="51e29-129">詳細な手順については、「Create or modify a [dial plan in Skype for Business Server」を参照してください](../../deploy/deploy-enterprise-voice/dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="51e29-129">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="51e29-130">ダイヤルイン会議のアクセスエンタープライズ VoIP展開しなかった場合は、ダイヤルイン会議アクセス番号のダイヤル プランを作成します。</span><span class="sxs-lookup"><span data-stu-id="51e29-130">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="51e29-131">ダイヤルイン会議の地域を忘れないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="51e29-131">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="51e29-132">詳細な手順については、「Create or modify a [dial plan in Skype for Business Server」を参照してください](../../deploy/deploy-enterprise-voice/dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="51e29-132">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="51e29-133">このサービスを展開エンタープライズ VoIP、必要にエンタープライズ VoIP必要に応じてダイヤル プランを変更し、ダイヤルイン アクセス番号に適切な正規化ルールを使用します。</span><span class="sxs-lookup"><span data-stu-id="51e29-133">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="51e29-134">また、ダイヤルイン アクセス番号のみのために使用する、専用のダイヤル プランを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="51e29-134">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="51e29-135">詳細な手順については、「Create or modify a [dial plan in Skype for Business Server」を参照してください](../../deploy/deploy-enterprise-voice/dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="51e29-135">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
<span data-ttu-id="51e29-136">正規化ルールの作成の詳細については、「Skype for Business で正規化ルールを [作成または変更する」を参照してください](../../deploy/deploy-enterprise-voice/normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="51e29-136">For details about creating normalization rules, see [Create or modify a normalization rule in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span></span>
  
## <a name="configure-dial-in-conferencing-regions"></a><span data-ttu-id="51e29-137">ダイヤルイン会議地域の構成</span><span class="sxs-lookup"><span data-stu-id="51e29-137">Configure dial-in conferencing regions</span></span>
<span data-ttu-id="51e29-138"><a name="BKMK_ConfigureDialInRegions"> </a></span><span class="sxs-lookup"><span data-stu-id="51e29-138"><a name="BKMK_ConfigureDialInRegions"> </a></span></span>

<span data-ttu-id="51e29-139">ダイヤル プランを設定する際に、そのダイヤル プランに適用されるダイヤルイン会議の地域を指定します。</span><span class="sxs-lookup"><span data-stu-id="51e29-139">When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan.</span></span> <span data-ttu-id="51e29-140">ダイヤルイン会議地域は、ダイヤルイン会議アクセス番号を適切なダイヤル プランに関連付ける。</span><span class="sxs-lookup"><span data-stu-id="51e29-140">The dial-in conferencing region associates dial-in conferencing access numbers with the appropriate dial plan.</span></span> <span data-ttu-id="51e29-141">ダイヤルイン アクセス番号を作成するときに、アクセス番号を該当するダイヤル プランに関連付ける地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="51e29-141">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span> 
  
<span data-ttu-id="51e29-142">すべてのダイヤル プランに地域を指定することが重要なので、すべてのダイヤル プランに電話会議地域が設定されているのを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="51e29-142">Because it important to specify a region for all dial plans, we recommend that you verify that all dial plans have conferencing regions.</span></span> 
  
<span data-ttu-id="51e29-143">すべてのダイヤルイン会議ダイヤル プランに地域が設定されているかどうかを確認するには **、Get-CsDialPlan コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="51e29-143">To verify whether the region is set for all dial-in conferencing dial plans, use the **Get-CsDialPlan** cmdlet.</span></span> <span data-ttu-id="51e29-144">ダイヤル プランに地域がない場合は、**Set-CsDialPlan** コマンドレットを使用して地域を設定できます。</span><span class="sxs-lookup"><span data-stu-id="51e29-144">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="51e29-145">Skype for Business Server コントロール パネルを使用して、既存のダイヤル プランの地域を更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="51e29-145">You can also use Skype for Business Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="51e29-146">Skype for Business Server コントロール パネルの使用の詳細については、「Create or modify a dial plan [in Skype for Business Server」を参照してください](../../deploy/deploy-enterprise-voice/dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="51e29-146">For details about using Skype for Business Server Control Panel, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="51e29-147">ダイヤル プランで地域プロパティが設定されているかどうかを確認するには</span><span class="sxs-lookup"><span data-stu-id="51e29-147">To verify whether dial plans have the region property set</span></span>

1. <span data-ttu-id="51e29-148">RTCUniversalServerAdmins グループのメンバーか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="51e29-148">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="51e29-149">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="51e29-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="51e29-150">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="51e29-150">Run the following at the command prompt:</span></span>
    
   ```powershell
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   <span data-ttu-id="51e29-151">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="51e29-151">For example:</span></span>
    
   ```powershell
   Get-CsDialPlan
   ```

   <span data-ttu-id="51e29-152">この例では、組織で構成されているすべてのダイヤル プランが戻されます。</span><span class="sxs-lookup"><span data-stu-id="51e29-152">In this example, all the dial plans configured for your organization are returned.</span></span>
    
4. <span data-ttu-id="51e29-153">戻されたダイヤル プランを確認して、ダイヤルイン会議の地域が含まれていないものを識別します。</span><span class="sxs-lookup"><span data-stu-id="51e29-153">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> 
    
<span data-ttu-id="51e29-154">詳細については [、「Get-CsDialPlan」を参照してください](/powershell/module/skype/get-csdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="51e29-154">For more information, see [Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps).</span></span>
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="51e29-155">ダイヤル プランの地域プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="51e29-155">To set the region property for a dial plan</span></span>

1. <span data-ttu-id="51e29-156">RTCUniversalServerAdmins グループのメンバーか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="51e29-156">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="51e29-157">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="51e29-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="51e29-158">ダイヤルイン会議の地域が含まれていないダイヤル プランで、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="51e29-158">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
   ```powershell
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   <span data-ttu-id="51e29-159">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="51e29-159">For example:</span></span>
    
   ```powershell
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   <span data-ttu-id="51e29-160">この例では、Redmond という ID を持つダイヤル プランを変更して、DialinConferencingRegion プロパティを "US West Coast" に設定します。</span><span class="sxs-lookup"><span data-stu-id="51e29-160">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> 
    
<span data-ttu-id="51e29-161">詳細については [、「Set-CsDialPlan」を参照してください](/powershell/module/skype/set-csdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="51e29-161">For more information, see [Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps).</span></span>
  
## <a name="configure-dial-in-access-numbers"></a><span data-ttu-id="51e29-162">ダイヤルイン アクセス番号を構成する</span><span class="sxs-lookup"><span data-stu-id="51e29-162">Configure dial-in access numbers</span></span>
<span data-ttu-id="51e29-163"><a name="BKMK_ConfigureDialInAccessNumbers"> </a></span><span class="sxs-lookup"><span data-stu-id="51e29-163"><a name="BKMK_ConfigureDialInAccessNumbers"> </a></span></span>

<span data-ttu-id="51e29-p110">ダイヤルイン会議を展開するときには、ユーザーが公衆交換電話網 (PSTN) からダイヤルして電話会議のオーディオ部分に参加するための電話番号を設定する必要があります。 それらのダイヤルイン アクセス番号は、ミーティングの招待状と [ダイヤルイン会議の設定] Web ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="51e29-p110">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences. These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
  
<span data-ttu-id="51e29-166">ダイヤルイン アクセス番号を作成する前に、まずダイヤルイン会議の域を計画し、その地域のダイヤル プランを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51e29-166">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="51e29-167">地域の詳細については [、「Plan for dial-in conferencing in Skype for Business Server」を参照してください](../../plan-your-deployment/conferencing/dial-in-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="51e29-167">For details about regions, see [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md).</span></span> <span data-ttu-id="51e29-168">ダイヤルイン会議のダイヤル プランの構成の詳細については、「Create or modify a dial plan [in Skype for Business Server」を参照してください](../../deploy/deploy-enterprise-voice/dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="51e29-168">For details about configuring dial plans for dial-in conferencing, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="51e29-169">新しいダイヤルイン アクセス番号は、そのアクセス番号の Active Directory ドメイン サービス (AD DS) レプリケーションが完了するまで使用できません。</span><span class="sxs-lookup"><span data-stu-id="51e29-169">You cannot use a new dial-in access number until Active Directory Domain Services (AD DS) replication of that access number is complete.</span></span> <span data-ttu-id="51e29-170">レプリケーションが完了するまでに数時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="51e29-170">Replication can take several hours to complete.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="51e29-171">ダイヤルイン アクセス番号を作成した後は、Active Directory の連絡先オブジェクトの表示名を変更し、ユーザーが正しいアクセス番号を識別しやすくすることができます。</span><span class="sxs-lookup"><span data-stu-id="51e29-171">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="51e29-172">表示名を変更するには [、Set-CsDialInConferencingAccessNumber コマンドレットを使用](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) します。</span><span class="sxs-lookup"><span data-stu-id="51e29-172">To modify the display name, use the [Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="51e29-173">Active Directory のオブジェクトは手動で変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="51e29-173">You should not modify Active Directory objects manually.</span></span>
  
### <a name="to-create-a-dial-in-access-number"></a><span data-ttu-id="51e29-174">ダイヤルイン アクセス番号を作成するには</span><span class="sxs-lookup"><span data-stu-id="51e29-174">To create a dial-in access number</span></span>

1. <span data-ttu-id="51e29-175">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="51e29-175">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="51e29-176">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="51e29-176">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="51e29-177">左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51e29-177">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="51e29-178">[ダイヤル **イン アクセス番号] ページで** 、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="51e29-178">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="51e29-179">[ **新規] を** クリックして[ **新しいダイヤルイン アクセス番号] を開きます**。</span><span class="sxs-lookup"><span data-stu-id="51e29-179">Click **New** to open **New Dial-in Access Number**.</span></span>
    
   - <span data-ttu-id="51e29-180">一覧でダイヤルイン アクセス番号のいずれかをクリックし、[編集]をクリックし、[詳細の表示]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="51e29-180">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="51e29-181">検索フィールドを使用して、ダイヤルイン アクセス番号の一覧にある列の内容を検索すると、期待した結果が得られるとは思いません。</span><span class="sxs-lookup"><span data-stu-id="51e29-181">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="51e29-182">代わりに、リストを関心のある列で並べ替え、表示または変更するダイヤルイン アクセス番号を識別します。</span><span class="sxs-lookup"><span data-stu-id="51e29-182">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="51e29-183">[ **表示番号]** に、公衆交換電話網 (PSTN) 電話ユーザーが電話会議に参加するためにダイヤルする電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="51e29-183">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> <span data-ttu-id="51e29-184">この番号は、会議出席依頼とダイヤルイン会議の設定 Web ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="51e29-184">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="51e29-185">[ **表示名]** に、ダイヤルイン アクセス番号の説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="51e29-185">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="51e29-186">これは、Skype for Business 検索結果のダイヤルイン アクセス番号に関連付けられている名前です。</span><span class="sxs-lookup"><span data-stu-id="51e29-186">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span> <span data-ttu-id="51e29-187">この名前は、ユーザーがアクセス番号を呼び出す際にクライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="51e29-187">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="51e29-188">[ **行 URI]** に、ダイヤルイン アクセス番号の E.164 番号を TEL URI 形式で入力します。この番号の前に + 記号を付け、スペースを除きます。</span><span class="sxs-lookup"><span data-stu-id="51e29-188">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="51e29-189">たとえば、tel:+14255550200。</span><span class="sxs-lookup"><span data-stu-id="51e29-189">For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="51e29-190">同じ回線 URI を別のダイヤルイン会議アクセス番号で再利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="51e29-190">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="51e29-191">**SIP URI で、** 次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="51e29-191">In **SIP URI**, do the following:</span></span>
    
   - <span data-ttu-id="51e29-192">テキスト ボックスに、このダイヤルイン会議アクセス番号の一意の SIP URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="51e29-192">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="51e29-193">この SIP URI は、呼び出し通知メッセージや以前のバージョンの Lync クライアントなど、さまざまな場所に表示されます。ただし、これらに限定されません。</span><span class="sxs-lookup"><span data-stu-id="51e29-193">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="51e29-194">同じ SIP URI を別のダイヤルイン会議アクセス番号で再利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="51e29-194">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="51e29-195">SIP URI は、アクセス番号の作成後に変更できません。</span><span class="sxs-lookup"><span data-stu-id="51e29-195">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="51e29-196">SIP URI を変更する唯一の方法は、アクセス番号を削除して再作成する方法です。</span><span class="sxs-lookup"><span data-stu-id="51e29-196">The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   - <span data-ttu-id="51e29-197">ドロップダウン リスト ボックスで、このダイヤルイン アクセス番号をサポートする会議応答アプリケーションのドメインをクリックします。</span><span class="sxs-lookup"><span data-stu-id="51e29-197">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="51e29-198">[ **プール]** で、このダイヤルイン アクセス番号をサポートする会議アテンダントのインスタンスを実行しているプールをクリックします。</span><span class="sxs-lookup"><span data-stu-id="51e29-198">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="51e29-199">アクセス番号の作成後にプールを変更する必要がある場合は [、Move-CsApplicationEndpoint](/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) コマンドレットを使用するか、アクセス番号を削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51e29-199">If you need to change the pool after you create the access number, you must use the [Move-CsApplicationEndpoint](/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="51e29-200">[ **プライマリ言語]** で、このダイヤルイン アクセス番号のプロンプトを再生する言語をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51e29-200">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="51e29-201">プライマリ言語は、会議アテンダントが通話に応答するために使用する言語です。</span><span class="sxs-lookup"><span data-stu-id="51e29-201">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="51e29-202">サポートされている言語は、[ダイヤルイン会議の設定] Web ページの各アクセス電話番号と一緒に表示されます。</span><span class="sxs-lookup"><span data-stu-id="51e29-202">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="51e29-203">(省略可能)[セカンダリ言語 (最大 **4 言語)]** で、[追加] をクリックし、このダイヤルイン アクセス番号の発信者をサポートする 1 つ以上の追加言語を選択し **、[OK]** をクリックします。 </span><span class="sxs-lookup"><span data-stu-id="51e29-203">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="51e29-204">ダイヤルイン アクセス番号ごとに最大 4 つのセカンダリ言語を選択できます。</span><span class="sxs-lookup"><span data-stu-id="51e29-204">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="51e29-205">ユーザーは、会議にダイヤルインするときに会議 ID を入力する前に、第 2 言語を選択できます。</span><span class="sxs-lookup"><span data-stu-id="51e29-205">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="51e29-206">ダイヤルイン アクセス番号の地域を追加するには、[関連付けられた地域] で、[追加] をクリックし、このダイヤルイン アクセス番号のダイヤル プランに関連付けられている 1 つ以上の地域をクリックし **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51e29-206">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="51e29-207">ダイヤルイン アクセス番号から地域を削除するには、[関連付けられた地域] で、削除する地域をクリックし、[削除] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="51e29-207">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="51e29-208">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51e29-208">Click **Commit**.</span></span>
    
## <a name="configure-conferencing-policies"></a><span data-ttu-id="51e29-209">会議ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="51e29-209">Configure conferencing policies</span></span>
<span data-ttu-id="51e29-210"><a name="BKMK_ConfigureConferencingPolicies"> </a></span><span class="sxs-lookup"><span data-stu-id="51e29-210"><a name="BKMK_ConfigureConferencingPolicies"> </a></span></span>

<span data-ttu-id="51e29-p122">会議ポリシーは、参加者向けの会議機能を指定するユーザー アカウント設定です。 会議ポリシーは、サイト スコープまたはユーザー スコープで作成できます。 会議ポリシー設定には、会議の予約と参加の多くの側面が含まれます。 複数の会議ポリシー設定で、参加者向けのダイヤルイン会議をサポートしています。 ダイヤルイン会議を構成する際に、これらのフィールドが組織に適切に設定されていることを確認し、必要に応じて変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51e29-p122">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span> 
  
<span data-ttu-id="51e29-216">会議ポリシーの構成の詳細については、「Skype for Business Server での会議ポリシーの管理 [」を参照してください](../../manage/conferencing/conferencing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="51e29-216">For more information about configuring conferencing policies, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  
## <a name="assign-a-line-uri-to-a-user-account"></a><span data-ttu-id="51e29-217">ユーザー アカウントに回線 URI を割り当てる</span><span class="sxs-lookup"><span data-stu-id="51e29-217">Assign a Line URI to a user account</span></span>
<span data-ttu-id="51e29-218"><a name="BKMK_AssignaLineURI"> </a></span><span class="sxs-lookup"><span data-stu-id="51e29-218"><a name="BKMK_AssignaLineURI"> </a></span></span>

<span data-ttu-id="51e29-219">ダイヤルイン ユーザーは各自の電話番号または内線番号、それに PIN を入力し、認証されたユーザーとして会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="51e29-219">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="51e29-220">認証 **には、Skype** for Business Server ユーザー アカウントで指定されたテレフォニー回線 URI が必要です。</span><span class="sxs-lookup"><span data-stu-id="51e29-220">The telephony **Line URI** specified on Skype for Business Server user accounts is required for authentication.</span></span>
  
<span data-ttu-id="51e29-221">このトピックの手順は、**[回線 URI]** を 1 つのユーザー アカウントに対して割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="51e29-221">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="51e29-222">**[回線 URI]** を複数のユーザー アカウントに対して割り当てる必要がある場合は、**Set-CsUser** コマンドレットを使用するスクリプトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="51e29-222">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="51e29-223">サンプル スクリプトを使用して複数のユーザー アカウントに **回線 URI** を割り当てる方法の詳細については、「複数のユーザーに回線 URI を割り当てる」 [を参照してください](https://go.microsoft.com/fwlink/p/?linkId=196945)。</span><span class="sxs-lookup"><span data-stu-id="51e29-223">For details about using a sample script to assign **Line URI** to multiple user accounts, see [Assign Line URIs to Multiple Users](https://go.microsoft.com/fwlink/p/?linkId=196945).</span></span>
  
1. <span data-ttu-id="51e29-224">RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**Cs-UserAdministrator** または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="51e29-224">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>
    
2.  <span data-ttu-id="51e29-225">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="51e29-225">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="51e29-226">左側のナビゲーション バーで **[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51e29-226">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="51e29-227">検索フィールドで、ダイヤルイン会議の構成を行うユーザーの名前を入力するか、**[フィルターの追加]** をクリックして検索フィールドを指定し、次に **[検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51e29-227">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>
    
5. <span data-ttu-id="51e29-228">ユーザー名をダブルクリックして **、[Skype for Business Server ユーザーの編集] ダイアログ ボックスを** 開きます。</span><span class="sxs-lookup"><span data-stu-id="51e29-228">Double-click the user name to open the **Edit Skype for Business Server User** dialog box.</span></span>
    
6. <span data-ttu-id="51e29-229">**[テレフォニー]** の下の **"回線 URI"** フィールドで、正規化された一意の電話番号 (たとえば、tel:+14255550200) を入力します。</span><span class="sxs-lookup"><span data-stu-id="51e29-229">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="51e29-230">回線 **URI** を指定できるのは、**テレ** フォニーが **PC** 間のみ、エンタープライズ VoIP、リモート通話制御、またはリモート通話 **制御のみに設定されている場合のみです**。 </span><span class="sxs-lookup"><span data-stu-id="51e29-230">You can specify **Line URI** only if **Telephony** is set to **PC-to-PC only**, **Enterprise Voice**, **Remote call control** or **Remote call control only**.</span></span> 
  
7. <span data-ttu-id="51e29-231">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51e29-231">Click **Commit**.</span></span>
