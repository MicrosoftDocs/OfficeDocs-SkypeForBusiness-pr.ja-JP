---
title: 管理者が個々のユーザー向けに Skype for Business の設定を構成する
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
description: 'Skype for Business の設定を変更する方法について説明します。たとえば、音声会議やビデオ会議、通話と会議の記録などがあります。 '
ms.openlocfilehash: cf54637bda51a7994121035b3db1585213c56c00
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753422"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="a83df-103">管理者: 個別のユーザーの Skype for Business の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="a83df-103">Admins: Configure Skype for Business settings for individual users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a83df-104">Microsoft Teams 管理センターは、Skype for Business 管理センター (従来のポータル) に代わるものです。</span><span class="sxs-lookup"><span data-stu-id="a83df-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="a83df-105">Skype for Business を管理するためのすべての設定が Teams 管理センターになりました。</span><span class="sxs-lookup"><span data-stu-id="a83df-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="a83df-106">Teams 管理センターで Skype for Business の機能を管理するには、グローバル管理者または Skype for Business 管理者の [AZURE AD 管理者の役割](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a83df-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="a83df-107">詳細については、「 [Microsoft Teams 管理センターで Skype For business の設定を管理](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a83df-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="a83df-108">この記事では、管理者が Skype for Business を少数のユーザーに対して構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a83df-108">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="a83df-109">これらの手順をまとめて実行するには、使用できる Windows PowerShell コマンドレットへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a83df-109">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="a83df-110">組織内のすべてのユーザーが外部ユーザーと通信できるようにする (またはブロックする) には、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a83df-110">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="a83df-111">[ユーザーが外部の skype For business ユーザーに連絡できるよう](allow-users-to-contact-external-skype-for-business-users.md)にする: Skype for business の高度な機能 (デスクトップの共有、オンラインのユーザーの検索など) を使用して、特定の信頼できる (フェデレーションされた) ビジネスのユーザーと通信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a83df-111">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="a83df-112">この記事では、特定のドメインとの通信をブロックする方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="a83df-112">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="a83df-113">[Skype For business ユーザーが skype の連絡先を追加できるように](let-skype-for-business-users-add-skype-contacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="a83df-113">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="a83df-114">Skype for Business を使用して、無料のアプリである Skype を使用しているユーザーを検索したり、IM を送信したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a83df-114">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="a83df-115">1人のユーザーの全般設定を構成する</span><span class="sxs-lookup"><span data-stu-id="a83df-115">Configure general settings for one user</span></span>
<span data-ttu-id="a83df-116"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="a83df-116"><a name="__toc325019204"> </a></span></span>

<span data-ttu-id="a83df-117">これらの手順を実行するには、 [管理者権限](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) が必要です。</span><span class="sxs-lookup"><span data-stu-id="a83df-117">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="a83df-118">![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="a83df-118">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="a83df-119">職場または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="a83df-119">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="a83df-120">[**管理センター**]  >  [**Skype for Business**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="a83df-120">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="a83df-121">[ **ユーザー**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a83df-121">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="a83df-123">編集するユーザーを選びます。</span><span class="sxs-lookup"><span data-stu-id="a83df-123">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="a83df-124">右側のウィンドウで、[ **編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a83df-124">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="a83df-126">[ **全般** ] オプションページで、変更する機能の横のチェックボックスをオンまたはオフにして、[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a83df-126">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="a83df-127">**オプション**</span><span class="sxs-lookup"><span data-stu-id="a83df-127">**Option**</span></span>|<span data-ttu-id="a83df-128">**詳細**</span><span class="sxs-lookup"><span data-stu-id="a83df-128">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a83df-129">オーディオと HD ビデオ</span><span class="sxs-lookup"><span data-stu-id="a83df-129">Audio and HD video</span></span>  <br/> |<span data-ttu-id="a83df-130">このユーザーが音声会議、音声会議、ビデオ会議を記録したり、会議のスケジュールを設定したりできないようにします (なし)。</span><span class="sxs-lookup"><span data-stu-id="a83df-130">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="a83df-131">会話と会議を記録する</span><span class="sxs-lookup"><span data-stu-id="a83df-131">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="a83df-132">このユーザーが記録できる内容を選びます。</span><span class="sxs-lookup"><span data-stu-id="a83df-132">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="a83df-133">このオプションは、Skype for Business Basic では使用できません。</span><span class="sxs-lookup"><span data-stu-id="a83df-133">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="a83df-134">コンプライアンスのため、アーカイブされていない機能をオフにする</span><span class="sxs-lookup"><span data-stu-id="a83df-134">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="a83df-135">電子的に保存された情報を維持する必要がある場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a83df-135">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="a83df-136">このオプションを選択すると、Exchange 管理センターで [インプレースホールド](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) が設定されているときにキャプチャされていない機能は無効になります。</span><span class="sxs-lookup"><span data-stu-id="a83df-136">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) set up in the Exchange admin center.</span></span> <span data-ttu-id="a83df-137">次の機能がオフになります。</span><span class="sxs-lookup"><span data-stu-id="a83df-137">It turns off the following features:</span></span> <br/>  <span data-ttu-id="a83df-138">インスタント メッセージングを使用したファイルの転送</span><span class="sxs-lookup"><span data-stu-id="a83df-138">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="a83df-139">OneNote の共有ページ</span><span class="sxs-lookup"><span data-stu-id="a83df-139">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="a83df-140">PowerPoint のコメント</span><span class="sxs-lookup"><span data-stu-id="a83df-140">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="a83df-141">これらの設定をまとめて構成するには、PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="a83df-141">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="a83df-142">「 [Windows PowerShell 用にコンピューターをセットアップする」を](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="a83df-142">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="a83df-143">外部通信をブロックする</span><span class="sxs-lookup"><span data-stu-id="a83df-143">Block external communications</span></span>
<span data-ttu-id="a83df-144"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="a83df-144"><a name="__toc325019206"> </a></span></span>

<span data-ttu-id="a83df-145">[Skype For business ユーザー](let-skype-for-business-users-add-skype-contacts.md)が会社のすべてのユーザーに skype 連絡先を追加できるようにすると、次の手順を使用して、特定のユーザーの外部通信を個別にブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="a83df-145">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="a83df-146">[ **ユーザー**] を選び、設定を無効にするユーザーを選択して、 **[編集] を選び** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) ます。</span><span class="sxs-lookup"><span data-stu-id="a83df-146">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="a83df-147">[ **外部通信**] を選択し、必要に応じてオプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a83df-147">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="a83df-148">**外部の skype For business ユーザー**: フェデレーションドメインの Skype for business ユーザーとの通信を可能にしない場合は、このボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a83df-148">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="a83df-149">**外部の Skype ユーザー**: freeSkype アプリを使用しているユーザーとの通信を可能にしない場合は、このボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a83df-149">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="a83df-150">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a83df-150">Click **Save**.</span></span>
    
<span data-ttu-id="a83df-151">これらの設定をまとめて構成するには、PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="a83df-151">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="a83df-152">「 [Windows PowerShell 用にコンピューターをセットアップする」を](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="a83df-152">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="a83df-153">1人のユーザーの電話会議の設定を編集する</span><span class="sxs-lookup"><span data-stu-id="a83df-153">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="a83df-154"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="a83df-154"><a name="__toc314837483"> </a></span></span>

1. <span data-ttu-id="a83df-155">[ **ユーザー**] を選び、電話会議の設定を編集するユーザーを選び、[編集 **] を選び** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) ます。</span><span class="sxs-lookup"><span data-stu-id="a83df-155">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="a83df-156">[ **電話会議**] を選び、電話会議プロバイダーを選んで、要求された情報を入力または変更し、[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a83df-156">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="a83df-157">**電話会議の設定**</span><span class="sxs-lookup"><span data-stu-id="a83df-157">**Audio conferencing setting**</span></span>|<span data-ttu-id="a83df-158">**説明**</span><span class="sxs-lookup"><span data-stu-id="a83df-158">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a83df-159">**プロバイダー名**</span><span class="sxs-lookup"><span data-stu-id="a83df-159">**Provider name**</span></span> <br/> |<span data-ttu-id="a83df-160">リストからプロバイダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a83df-160">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="a83df-161">**有料電話番号** (必須)</span><span class="sxs-lookup"><span data-stu-id="a83df-161">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="a83df-162">サードパーティ ACP の場合、これらの電話番号は、電話会議プロバイダーから受け取った電話番号です。</span><span class="sxs-lookup"><span data-stu-id="a83df-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="a83df-163">ユーザーが、Microsoft を電話会議プロバイダーとして使用している場合は、これらは電話会議ブリッジで設定されている番号となります。</span><span class="sxs-lookup"><span data-stu-id="a83df-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="a83df-164">Skype for Business および Microsoft Teams の会議出席依頼に表示する番号の書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="a83df-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="a83df-165">**フリー ダイヤル番号**</span><span class="sxs-lookup"><span data-stu-id="a83df-165">**Toll-free number**</span></span> <br/> |<span data-ttu-id="a83df-166">サードパーティ ACP の場合、これらの電話番号は、電話会議プロバイダーから受け取った電話番号です。</span><span class="sxs-lookup"><span data-stu-id="a83df-166">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="a83df-167">ユーザーが、Microsoft を電話会議プロバイダーとして使用している場合は、これらは電話会議ブリッジで設定されている番号となります。</span><span class="sxs-lookup"><span data-stu-id="a83df-167">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="a83df-168">Skype for Business および Microsoft Teams の会議出席依頼に表示する番号の書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="a83df-168">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="a83df-169">**会議 ID と PIN** (必須)</span><span class="sxs-lookup"><span data-stu-id="a83df-169">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="a83df-170">このユーザーによってスケジュールされ、サードパーティの電話会議プロバイダーから提供された会議に参加するために使用される、参加者の PIN (会議コード) です。</span><span class="sxs-lookup"><span data-stu-id="a83df-170">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="a83df-171">ユーザーが Microsoft を電話会議プロバイダーとして使用している場合は、この操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a83df-171">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="a83df-172">これらの設定をまとめて構成するには、PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="a83df-172">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="a83df-173">「[招待に含まれている電話番号を設定する](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)」を[参照してください。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="a83df-173">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="a83df-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="a83df-174">Related topics</span></span> 

[<span data-ttu-id="a83df-175">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="a83df-175">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="a83df-176">Skype for Business と Microsoft Teams のアドオン ライセンス</span><span class="sxs-lookup"><span data-stu-id="a83df-176">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
