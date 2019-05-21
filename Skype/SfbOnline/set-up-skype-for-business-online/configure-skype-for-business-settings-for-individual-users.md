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
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: 'Skype for Business の設定を変更する方法について説明します。たとえば、音声会議やビデオ会議、通話と会議の記録などがあります。 '
ms.openlocfilehash: 5be310e47a5094a0e424624cc711311865a5b842
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285306"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="b3e40-103">管理者: 個別のユーザーの Skype for Business の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="b3e40-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="b3e40-104">この記事では、管理者が Skype for Business を少数のユーザーに対して構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3e40-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="b3e40-105">これらの手順をまとめて実行するには、使用できる Windows PowerShell コマンドレットへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b3e40-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="b3e40-106">組織内のすべてのユーザーが外部ユーザーと通信できるようにする (またはブロックする) には、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3e40-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="b3e40-107">[ユーザーが外部の skype For business ユーザーに連絡できるよう](allow-users-to-contact-external-skype-for-business-users.md)にする: Skype for business の高度な機能 (デスクトップの共有、オンラインのユーザーの検索など) を使用して、特定の信頼できる (フェデレーションされた) ビジネスのユーザーと通信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b3e40-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="b3e40-108">この記事では、特定のドメインとの通信をブロックする方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="b3e40-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="b3e40-109">[Skype For business ユーザーが skype の連絡先を追加できるように](let-skype-for-business-users-add-skype-contacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="b3e40-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="b3e40-110">Skype for Business を使用して、無料のアプリである Skype を使用しているユーザーを検索したり、IM を送信したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="b3e40-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="b3e40-111">1人のユーザーの全般設定を構成する</span><span class="sxs-lookup"><span data-stu-id="b3e40-111">Configure general settings for one user</span></span>
<span data-ttu-id="b3e40-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="b3e40-112"></span></span>

<span data-ttu-id="b3e40-113">これらの手順を実行するには、[管理者権限](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)が必要です。</span><span class="sxs-lookup"><span data-stu-id="b3e40-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="b3e40-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="b3e40-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="b3e40-115">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="b3e40-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="b3e40-116">[**管理センター**]  >  [**Skype for Business**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3e40-116">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="b3e40-117">[ **ユーザー**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b3e40-117">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="b3e40-119">編集するユーザーを選びます。</span><span class="sxs-lookup"><span data-stu-id="b3e40-119">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="b3e40-120">右側のウィンドウで、[ **編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b3e40-120">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="b3e40-122">[**全般**] オプションページで、変更する機能の横のチェックボックスをオンまたはオフにして、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3e40-122">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="b3e40-123">**オプション**</span><span class="sxs-lookup"><span data-stu-id="b3e40-123">**Option**</span></span>|<span data-ttu-id="b3e40-124">**詳細**</span><span class="sxs-lookup"><span data-stu-id="b3e40-124">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b3e40-125">オーディオと HD ビデオ</span><span class="sxs-lookup"><span data-stu-id="b3e40-125">Audio and HD video</span></span>  <br/> |<span data-ttu-id="b3e40-126">このユーザーが音声会議、音声会議、ビデオ会議を記録したり、会議のスケジュールを設定したりできないようにします (なし)。</span><span class="sxs-lookup"><span data-stu-id="b3e40-126">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="b3e40-127">会話と会議を記録する</span><span class="sxs-lookup"><span data-stu-id="b3e40-127">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="b3e40-128">このユーザーが記録できる内容を選びます。</span><span class="sxs-lookup"><span data-stu-id="b3e40-128">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="b3e40-129">このオプションは、Skype for Business Basic では使用できません。</span><span class="sxs-lookup"><span data-stu-id="b3e40-129">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="b3e40-130">コンプライアンスのため、アーカイブされていない機能をオフにする</span><span class="sxs-lookup"><span data-stu-id="b3e40-130">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="b3e40-131">電子的に保存された情報を維持する必要がある場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b3e40-131">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="b3e40-132">このオプションを選択すると、Exchange 管理センターで[インプレースホールド](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx)が設定されているときにキャプチャされていない機能は無効になります。</span><span class="sxs-lookup"><span data-stu-id="b3e40-132">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in the Exchange admin center.</span></span> <span data-ttu-id="b3e40-133">次の機能がオフになります。</span><span class="sxs-lookup"><span data-stu-id="b3e40-133">It turns off the following features:</span></span> <br/>  <span data-ttu-id="b3e40-134">インスタント メッセージングを使用したファイルの転送</span><span class="sxs-lookup"><span data-stu-id="b3e40-134">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="b3e40-135">OneNote の共有ページ</span><span class="sxs-lookup"><span data-stu-id="b3e40-135">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="b3e40-136">PowerPoint のコメント</span><span class="sxs-lookup"><span data-stu-id="b3e40-136">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="b3e40-137">これらの設定をまとめて構成するには、PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="b3e40-137">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="b3e40-138">「 [Windows PowerShell 用にコンピューターをセットアップする」を](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3e40-138">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="b3e40-139">外部通信をブロックする</span><span class="sxs-lookup"><span data-stu-id="b3e40-139">Block external communications</span></span>
<span data-ttu-id="b3e40-140"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="b3e40-140"></span></span>

<span data-ttu-id="b3e40-141">[Skype For business ユーザー](let-skype-for-business-users-add-skype-contacts.md)が会社のすべてのユーザーに skype 連絡先を追加できるようにすると、次の手順を使用して、特定のユーザーの外部通信を個別にブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="b3e40-141">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="b3e40-142">[**ユーザー**] を選び、設定を無効にするユーザーを選択して\*\*\*\* ![、[](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)編集] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b3e40-142">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="b3e40-143">[**外部通信**] を選択し、必要に応じてオプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="b3e40-143">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="b3e40-144">**外部の skype For business ユーザー**: フェデレーションドメインの Skype for business ユーザーとの通信を可能にしない場合は、このボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="b3e40-144">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="b3e40-145">**外部の Skype ユーザー**: freeSkype アプリを使用しているユーザーとの通信を可能にしない場合は、このボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="b3e40-145">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="b3e40-146">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3e40-146">Click **Save**.</span></span>
    
<span data-ttu-id="b3e40-147">これらの設定をまとめて構成するには、PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="b3e40-147">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="b3e40-148">「 [Windows PowerShell 用にコンピューターをセットアップする」を](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3e40-148">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="b3e40-149">1人のユーザーの電話会議の設定を編集する</span><span class="sxs-lookup"><span data-stu-id="b3e40-149">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="b3e40-150"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="b3e40-150"></span></span>

1. <span data-ttu-id="b3e40-151">[**ユーザー**] を選び、電話会議の設定を編集するユーザーを選び、[編集\*\*\*\* ![] を](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)選びます。</span><span class="sxs-lookup"><span data-stu-id="b3e40-151">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="b3e40-152">[**電話会議**] を選び、電話会議プロバイダーを選んで、要求された情報を入力または変更し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3e40-152">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="b3e40-153">**電話会議の設定**</span><span class="sxs-lookup"><span data-stu-id="b3e40-153">**Audio conferencing setting**</span></span>|<span data-ttu-id="b3e40-154">**説明**</span><span class="sxs-lookup"><span data-stu-id="b3e40-154">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b3e40-155">**プロバイダー名**</span><span class="sxs-lookup"><span data-stu-id="b3e40-155">**Provider name**</span></span> <br/> |<span data-ttu-id="b3e40-156">リストからプロバイダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b3e40-156">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="b3e40-157">**有料電話番号** (必須)</span><span class="sxs-lookup"><span data-stu-id="b3e40-157">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="b3e40-158">サードパーティ ACP の場合、これらの電話番号は、電話会議プロバイダーから受け取った電話番号です。</span><span class="sxs-lookup"><span data-stu-id="b3e40-158">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="b3e40-159">ユーザーが、Microsoft を電話会議プロバイダーとして使用している場合は、これらは電話会議ブリッジで設定されている番号となります。</span><span class="sxs-lookup"><span data-stu-id="b3e40-159">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="b3e40-160">Skype for Business および Microsoft Teams の会議出席依頼に表示する番号の書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="b3e40-160">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="b3e40-161">**フリー ダイヤル番号**</span><span class="sxs-lookup"><span data-stu-id="b3e40-161">**Toll-free number**</span></span> <br/> |<span data-ttu-id="b3e40-162">サードパーティ ACP の場合、これらの電話番号は、電話会議プロバイダーから受け取った電話番号です。</span><span class="sxs-lookup"><span data-stu-id="b3e40-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="b3e40-163">ユーザーが、Microsoft を電話会議プロバイダーとして使用している場合は、これらは電話会議ブリッジで設定されている番号となります。</span><span class="sxs-lookup"><span data-stu-id="b3e40-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="b3e40-164">Skype for Business および Microsoft Teams の会議出席依頼に表示する番号の書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="b3e40-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="b3e40-165">**会議 ID と PIN**任意</span><span class="sxs-lookup"><span data-stu-id="b3e40-165">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="b3e40-166">このユーザーによってスケジュールされ、サードパーティの電話会議プロバイダーから提供された会議に参加するために使用される、参加者の PIN (会議コード) です。</span><span class="sxs-lookup"><span data-stu-id="b3e40-166">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="b3e40-167">ユーザーが Microsoft を電話会議プロバイダーとして使用している場合は、この操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b3e40-167">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="b3e40-168">これらの設定をまとめて構成するには、PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="b3e40-168">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="b3e40-169">「[招待に含まれている電話番号を設定する](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3e40-169">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="b3e40-170">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b3e40-170">Related topics</span></span> 

[<span data-ttu-id="b3e40-171">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="b3e40-171">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="b3e40-172">Skype for Business と Microsoft Teams のアドオン ライセンス</span><span class="sxs-lookup"><span data-stu-id="b3e40-172">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
