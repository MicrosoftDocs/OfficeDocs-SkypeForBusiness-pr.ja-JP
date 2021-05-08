---
title: 管理者個々のユーザー Skype for Business設定を構成する
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- LIL_Placement
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
description: '電話会議、ビデオ会議Skype for Business、通話や会議の記録など、個々のユーザーの通話設定を変更する方法について説明します。 '
ms.openlocfilehash: 0123f285101b8d7190dd7450ddb876a136de13ce
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237533"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="9ae08-103">管理者: 個別のユーザーの Skype for Business の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="9ae08-103">Admins: Configure Skype for Business settings for individual users</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="9ae08-104">管理Microsoft Teamsセンターは、管理センター (レガシ ポータルSkype for Business置き換えました。</span><span class="sxs-lookup"><span data-stu-id="9ae08-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="9ae08-105">現在、管理センター Skype for Business管理センターにTeams設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9ae08-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="9ae08-106">グローバル管理者の[Azure AD 管理者](/azure/active-directory/roles/permissions-reference)ロールが割り当てられている必要があります。または、Skype for Business 管理センターでSkype for Business機能を管理するには、Teams必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ae08-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="9ae08-107">詳細については、「[Microsoft Teams 管理センターで Skype for Business の設定を管理する](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ae08-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="9ae08-108">この記事では、管理者がユーザー数の少ないSkype for Businessを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ae08-108">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="9ae08-109">これらの手順を一括で実行するために、使用できるWindows PowerShellへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9ae08-109">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="9ae08-110">社外のユーザーとの通信を許可 (またはブロック) するには、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ae08-110">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="9ae08-111">ユーザーが外部[の Skype for Business](allow-users-to-contact-external-skype-for-business-users.md)ユーザーと連絡を取る : 組織で高度な Skype for Business 機能 (デスクトップの共有、オンラインのユーザーの検索など) を使用して、特定の信頼された (フェデレーション) ビジネスのユーザーと通信することができます。</span><span class="sxs-lookup"><span data-stu-id="9ae08-111">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="9ae08-112">この記事では、特定のドメインとの通信をブロックする方法も説明します。</span><span class="sxs-lookup"><span data-stu-id="9ae08-112">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="9ae08-113">[ユーザー Skype for Business連絡先 をSkypeできます](let-skype-for-business-users-add-skype-contacts.md)。</span><span class="sxs-lookup"><span data-stu-id="9ae08-113">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="9ae08-114">組織で無料アプリである Skype for Businessを使用するユーザーを検索および IM Skype使用できます。</span><span class="sxs-lookup"><span data-stu-id="9ae08-114">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="9ae08-115">1 人のユーザーの一般的な設定を構成する</span><span class="sxs-lookup"><span data-stu-id="9ae08-115">Configure general settings for one user</span></span>
<span data-ttu-id="9ae08-116"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="9ae08-116"><a name="__toc325019204"> </a></span></span>

<span data-ttu-id="9ae08-117">これらの手順を [実行するには、管理者アクセス](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="9ae08-117">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="9ae08-118">![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="9ae08-118">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="9ae08-119">仕事用または学校用のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="9ae08-119">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="9ae08-120">[**管理センター**]  >  [**Skype for Business**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ae08-120">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="9ae08-121">[ **ユーザー**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9ae08-121">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="9ae08-123">編集するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ae08-123">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="9ae08-124">右側のウィンドウで、[ **編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9ae08-124">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="9ae08-126">[全般 **オプション]** ページで、変更する機能の横にあるチェック ボックスをオンまたはオフにして、[保存] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="9ae08-126">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="9ae08-127">**オプション**</span><span class="sxs-lookup"><span data-stu-id="9ae08-127">**Option**</span></span>|<span data-ttu-id="9ae08-128">**詳細**</span><span class="sxs-lookup"><span data-stu-id="9ae08-128">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9ae08-129">オーディオと HD ビデオ</span><span class="sxs-lookup"><span data-stu-id="9ae08-129">Audio and HD video</span></span>  <br/> |<span data-ttu-id="9ae08-130">このユーザーが音声会議、音声会議、ビデオ会議を記録したり、会議のスケジュールを設定したり (なし) 許可したりしません。</span><span class="sxs-lookup"><span data-stu-id="9ae08-130">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="9ae08-131">会話と会議を記録する</span><span class="sxs-lookup"><span data-stu-id="9ae08-131">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="9ae08-132">このユーザーが記録できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ae08-132">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="9ae08-133">このオプションは、Basic ではSkype for Businessできません。</span><span class="sxs-lookup"><span data-stu-id="9ae08-133">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="9ae08-134">コンプライアンスのために、アーカイブされていない機能をオフにする</span><span class="sxs-lookup"><span data-stu-id="9ae08-134">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="9ae08-135">電子的に保存された情報を法的に保持する必要がある場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ae08-135">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="9ae08-136">このオプションを選択すると、管理センターでインセット ホールドが設定されている場合[](/exchange/security-and-compliance/in-place-and-litigation-holds)にキャプチャされない機能Exchangeオフになります。</span><span class="sxs-lookup"><span data-stu-id="9ae08-136">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](/exchange/security-and-compliance/in-place-and-litigation-holds) set up in the Exchange admin center.</span></span> <span data-ttu-id="9ae08-137">次の機能がオフになります。</span><span class="sxs-lookup"><span data-stu-id="9ae08-137">It turns off the following features:</span></span> <br/>  <span data-ttu-id="9ae08-138">インスタント メッセージングを使用したファイルの転送</span><span class="sxs-lookup"><span data-stu-id="9ae08-138">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="9ae08-139">OneNote の共有ページ</span><span class="sxs-lookup"><span data-stu-id="9ae08-139">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="9ae08-140">PowerPoint のコメント</span><span class="sxs-lookup"><span data-stu-id="9ae08-140">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="9ae08-141">これらの設定を一括で構成するには、PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="9ae08-141">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="9ae08-142">「[コンピューターのセットアップ」を参照Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="9ae08-142">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="9ae08-143">外部通信をブロックする</span><span class="sxs-lookup"><span data-stu-id="9ae08-143">Block external communications</span></span>
<span data-ttu-id="9ae08-144"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="9ae08-144"><a name="__toc325019206"> </a></span></span>

<span data-ttu-id="9ae08-145">ユーザーが[会社](let-skype-for-business-users-add-skype-contacts.md)Skype for Businessの連絡先Skype追加した後、次の手順を使用して、特定の個人の外部通信を選択的にブロックできます。</span><span class="sxs-lookup"><span data-stu-id="9ae08-145">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="9ae08-146">[ **ユーザー]** を選択し、設定を無効にするユーザーを選択し、[編集] を **選択** ![ します ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) 。</span><span class="sxs-lookup"><span data-stu-id="9ae08-146">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="9ae08-147">[外部 **通信] を** 選択し、必要に応じてオプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="9ae08-147">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="9ae08-148">**外部Skype for Business** ユーザー: フェデレーション ドメイン内のユーザーと通信できない場合は、このSkype for Businessオフにします。</span><span class="sxs-lookup"><span data-stu-id="9ae08-148">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="9ae08-149">**外部Skype** ユーザー: FreeSkype アプリを使用しているユーザーとユーザーが通信できない場合は、このボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="9ae08-149">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="9ae08-150">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ae08-150">Click **Save**.</span></span>
    
<span data-ttu-id="9ae08-151">これらの設定を一括で構成するには、PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="9ae08-151">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="9ae08-152">「[コンピューターのセットアップ」を参照Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="9ae08-152">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="9ae08-153">1 人のユーザーの電話会議設定を編集する</span><span class="sxs-lookup"><span data-stu-id="9ae08-153">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="9ae08-154"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="9ae08-154"><a name="__toc314837483"> </a></span></span>

1. <span data-ttu-id="9ae08-155">[ **ユーザー]** を選択し、編集する電話会議設定を持つユーザーを選択し、[編集] を **選択** ![ します ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) 。</span><span class="sxs-lookup"><span data-stu-id="9ae08-155">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="9ae08-156">[ **電話会議] を選択** し、電話会議プロバイダーを選択し、要求された情報を入力または変更して、[保存] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="9ae08-156">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="9ae08-157">**電話会議の設定**</span><span class="sxs-lookup"><span data-stu-id="9ae08-157">**Audio conferencing setting**</span></span>|<span data-ttu-id="9ae08-158">**説明**</span><span class="sxs-lookup"><span data-stu-id="9ae08-158">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9ae08-159">**プロバイダー名**</span><span class="sxs-lookup"><span data-stu-id="9ae08-159">**Provider name**</span></span> <br/> |<span data-ttu-id="9ae08-160">一覧からプロバイダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ae08-160">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="9ae08-161">**有料電話番号** (必須)</span><span class="sxs-lookup"><span data-stu-id="9ae08-161">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="9ae08-162">サード パーティの ACP の場合、これらの電話番号は電話会議プロバイダーから受け取った電話番号です。</span><span class="sxs-lookup"><span data-stu-id="9ae08-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="9ae08-163">ユーザーが、Microsoft を電話会議プロバイダーとして使用している場合は、これらは電話会議ブリッジで設定されている番号となります。</span><span class="sxs-lookup"><span data-stu-id="9ae08-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="9ae08-164">会議出席依頼に表示する番号を書式設定Skype for Business Microsoft Teams表示します。</span><span class="sxs-lookup"><span data-stu-id="9ae08-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="9ae08-165">**フリー ダイヤル番号**</span><span class="sxs-lookup"><span data-stu-id="9ae08-165">**Toll-free number**</span></span> <br/> |<span data-ttu-id="9ae08-166">サード パーティの ACP の場合、これらの電話番号は電話会議プロバイダーから受け取った電話番号です。</span><span class="sxs-lookup"><span data-stu-id="9ae08-166">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="9ae08-167">ユーザーが、Microsoft を電話会議プロバイダーとして使用している場合は、これらは電話会議ブリッジで設定されている番号となります。</span><span class="sxs-lookup"><span data-stu-id="9ae08-167">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="9ae08-168">会議出席依頼に表示する番号を書式設定Skype for Business Microsoft Teams表示します。</span><span class="sxs-lookup"><span data-stu-id="9ae08-168">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="9ae08-169">**会議 ID と PIN** (必須)</span><span class="sxs-lookup"><span data-stu-id="9ae08-169">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="9ae08-170">このユーザーによってスケジュールされ、サードパーティの電話会議プロバイダーから提供される会議に参加するために使用される、参加者の PIN または電話会議コード。</span><span class="sxs-lookup"><span data-stu-id="9ae08-170">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="9ae08-171">ユーザーが電話会議プロバイダーとして Microsoft を使用している場合、これは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9ae08-171">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="9ae08-172">これらの設定を一括で構成するには、PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="9ae08-172">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="9ae08-173">「[招待に含まれる電話番号を設定する」を参照](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)[してください Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="9ae08-173">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="9ae08-174">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9ae08-174">Related topics</span></span> 

[<span data-ttu-id="9ae08-175">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="9ae08-175">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="9ae08-176">Skype for Business と Microsoft Teams のアドオン ライセンス</span><span class="sxs-lookup"><span data-stu-id="9ae08-176">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
