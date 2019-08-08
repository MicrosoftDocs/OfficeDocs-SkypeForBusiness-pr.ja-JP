---
title: Skype for Business Server でエンタープライズ Voip のユーザーを有効にする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: '概要: Skype for Business Server のエンタープライズボイスを使用して、ユーザーが通話を発信および受信できるようにする方法について説明します。'
ms.openlocfilehash: cf9aab0f104582c57e745c95ae5cf8f24f07b3a5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240332"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="3c4f9-103">Skype for Business Server でエンタープライズ Voip のユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="3c4f9-103">Enable users for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="3c4f9-104">**概要:** Skype for Business Server のエンタープライズボイスを使用して、ユーザーが通話を発信および受信できるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-104">**Summary:** Learn how to enable users to make and receive calls by using Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="3c4f9-105">職場で企業の音声または通話を展開した後、次の手順を使用して、ユーザーがエンタープライズ Voip を使用して電話をかけることができるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-105">After you deploy Enterprise Voice or Call Via Work, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>
  
> [!NOTE]
> <span data-ttu-id="3c4f9-106">次の手順では、最初の操作は、Skype for Business Server コントロールパネルを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-106">Of the following procedures, only the first can be performed by using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="3c4f9-107">残りの手順については、Skype for Business Server 管理シェルのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-107">For the remaining procedures, you can use only Skype for Business Server Management Shell.</span></span> 
  
- <span data-ttu-id="3c4f9-108">エンタープライズ Voip のユーザーアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-108">Enable the user account for Enterprise Voice.</span></span>
    
- <span data-ttu-id="3c4f9-109">(オプション) ユーザー アカウントにユーザー固有の音声ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-109">(Optional) Assign the user account a user-specific voice policy.</span></span>
    
- <span data-ttu-id="3c4f9-110">(オプション) ユーザー アカウントにユーザー固有のダイヤル プランを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-110">(Optional) Assign the user account a user-specific dial plan.</span></span>
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="3c4f9-111">エンタープライズ Voip のユーザーアカウントを有効にするには</span><span class="sxs-lookup"><span data-stu-id="3c4f9-111">To enable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="3c4f9-112">RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="3c4f9-113">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="3c4f9-114">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3c4f9-115">[**ユーザーの検索**] ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か先頭の部分の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="3c4f9-116">表で、エンタープライズ Voip を有効にするユーザーアカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="3c4f9-117">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-117">On the **Edit** menu, click **Show details**.</span></span>
    
7. <span data-ttu-id="3c4f9-118">[ **Skype For Business Server ユーザーの編集**] ページの [**テレフォニー**] で、[**エンタープライズ voip**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-118">On the **Edit Skype for Business Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="3c4f9-119">[**回線 URI**] をクリックし、正規化された一意の電話番号 (たとえば、tel:+14255550200) を入力します。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
9. <span data-ttu-id="3c4f9-120">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-120">Click **Commit**.</span></span>
    
<span data-ttu-id="3c4f9-121">エンタープライズ Voip のユーザーを有効にするには、そのユーザーに、グローバル (既定で割り当てられている) か、またはユーザー固有かにかかわらず、ボイスポリシーとダイヤルプランが割り当てられていることを確認します。既定では、すべてのユーザーにグローバルボイスポリシーとダイヤルプランが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="3c4f9-122">ユーザー アカウントが属しているサイトにサイト レベルの音声ポリシーとダイヤル プランが存在する場合は、それらのサイト ポリシーがユーザーに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-122">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="3c4f9-123">ユーザーごとの音声ポリシーまたはダイヤル プランをユーザーに適用するには、**Grant-CsVoicePolicy** および **Grant-CsDialPlan** コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-123">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="3c4f9-124">詳細については、このトピックの以下の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-124">For details, see the following procedures in this topic.</span></span>
## <a name="voice-policy-assignment"></a><span data-ttu-id="3c4f9-125">音声ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="3c4f9-125">Voice Policy Assignment</span></span>

<span data-ttu-id="3c4f9-126">グローバルおよびサイトレベルのボイスポリシーは、エンタープライズ Voip が有効になっているすべてのユーザーアカウントに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-126">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="3c4f9-127">特定のユーザーまたはグループに適用する音声ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-127">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="3c4f9-128">このようなユーザーごとのポリシーは、ユーザーまたはグループに明示的に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-128">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="3c4f9-129">エンタープライズ Voip を有効にしているすべてのユーザーに対して、グローバルまたはサイトのボイスポリシーを使用する場合は、このセクションをスキップして、このトピックの後半の「[プランの割り当て](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment)を続行する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-129">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to [Dial Plan Assignment](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) section later in this topic.</span></span>
  
### <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="3c4f9-130">ユーザー固有の音声ポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="3c4f9-130">To assign a user-specific voice policy</span></span>

1. <span data-ttu-id="3c4f9-131">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3c4f9-132">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="3c4f9-133">既存のユーザー音声ポリシーをユーザーに割り当てるには、コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-133">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
   ```
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="3c4f9-134">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-134">For example:</span></span>
    
   ```
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    <span data-ttu-id="3c4f9-135">この例では、表示名が Bob 友野のユーザーに、 **VoicePolicyJapan**という名前のボイスポリシーが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-135">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>
    
## <a name="dial-plan-assignment"></a><span data-ttu-id="3c4f9-136">ダイヤル プランの割り当て</span><span class="sxs-lookup"><span data-stu-id="3c4f9-136">Dial Plan Assignment</span></span>
<span data-ttu-id="3c4f9-137"><a name="BKMK_DialPlanAssignment"> </a></span><span class="sxs-lookup"><span data-stu-id="3c4f9-137"></span></span>

<span data-ttu-id="3c4f9-138">ダイヤルイン会議のエンタープライズボイスまたはユーザーのいずれかのユーザーアカウント構成を完了するには、ユーザーにダイヤルプランを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-138">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="3c4f9-139">既存のユーザーごとのダイヤル プランを明示的に割り当てないと、ユーザー アカウントでは、グローバル ダイヤル プランまたは存在する場合はサイト レベルのダイヤル プランが自動的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-139">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="3c4f9-140">エンタープライズ Voip を有効にしているすべてのユーザーに対してグローバルまたはサイトダイヤルプランを使用する場合は、このセクションをスキップできます。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-140">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>
  
### <a name="to-assign-a-user-specific-dial-plan"></a><span data-ttu-id="3c4f9-141">ユーザー固有のダイヤル プランを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="3c4f9-141">To assign a user-specific dial plan</span></span>

1. <span data-ttu-id="3c4f9-142">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3c4f9-143">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-143">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="3c4f9-144">ユーザー固有のダイヤル プランを割り当てるには、コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-144">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
   ```
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="3c4f9-145">例:</span><span class="sxs-lookup"><span data-stu-id="3c4f9-145">For example:</span></span>
    
   ```
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    <span data-ttu-id="3c4f9-146">この例では、"Bob 友野" という名前のユーザーにダイヤルプランが割り当てられ\*\*\*\* ています。</span><span class="sxs-lookup"><span data-stu-id="3c4f9-146">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>
    

