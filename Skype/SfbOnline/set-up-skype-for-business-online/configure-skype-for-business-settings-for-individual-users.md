---
title: "個々 のユーザーのビジネス設定の管理者を構成する Skype"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
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
description: "次のような Skype for Business 個々 のユーザーの設定を変更する方法について説明します。 音声とビデオ会議、通話の記録と会議します。 "
ms.openlocfilehash: 45b5e966a670dfc97d3edd27eae7811fad061638
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="d9821-103">管理者向け: ビジネス設定を個別のユーザー向けの Skype を構成します。</span><span class="sxs-lookup"><span data-stu-id="d9821-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="d9821-p101">この記事では、管理者が少数のユーザー向けの Skype を構成する方法について説明します。一括で次の手順を行うには、Windows PowerShell コマンドレットを使用することができますへのリンク掲載されています。</span><span class="sxs-lookup"><span data-stu-id="d9821-p101">This article explains how admins configure Skype for Business for a small number of users. To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="d9821-106">許可する (またはブロック) を外部ユーザーと通信するために、ビジネスのすべての参加者を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9821-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="d9821-p102">[外部の Skype for Business ユーザーの連絡先にユーザーを許可する]](allow-users-to-contact-external-skype-for-business-users.md): 組織に使用することができます (デスクトップの共有、ユーザーが [オンラインなどの外観) のビジネス機能の Skype を高度な特定のユーザーと通信するために信頼できる (フェデレーション) のビジネスします。また、特定のドメインとの通信をブロックする方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="d9821-p102">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business. The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="d9821-p103">[Skype の連絡先を追加する Skype for Business ユーザーができるように](let-skype-for-business-users-add-skype-contacts.md)します。組織がビジネスを検索し、Skype、無料のアプリを使用している IM ユーザーに Skype を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d9821-p103">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md). You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="d9821-111">単一ユーザーの [全般] 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="d9821-111">Configure general settings for one user</span></span>
<span data-ttu-id="d9821-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="d9821-112"></span></span>

<span data-ttu-id="d9821-113">次の手順を実行するのには、[管理者権限](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)が必要です。</span><span class="sxs-lookup"><span data-stu-id="d9821-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>
  
1. <span data-ttu-id="d9821-114">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="d9821-114">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="d9821-115">**管理センター**] を選びます > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="d9821-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="d9821-116">**ユーザー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9821-116">Choose **Users**.</span></span>
    
    ![Skype for Business 管理センター] では、ユーザーを選択します。](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="d9821-118">編集するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d9821-118">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="d9821-119">右のパネルで [**編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d9821-119">In the right panel, choose **Edit**.</span></span>
    
    ![[編集] アイコンを選択します。](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="d9821-121">[**全般**] オプション ページで、選択や、変更する機能の横にあるチェック ボックスをオフにし、[**保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d9821-121">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="d9821-122">**オプション**</span><span class="sxs-lookup"><span data-stu-id="d9821-122">**Option**</span></span>|<span data-ttu-id="d9821-123">**詳細情報**</span><span class="sxs-lookup"><span data-stu-id="d9821-123">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d9821-124">音声とビデオの HD</span><span class="sxs-lookup"><span data-stu-id="d9821-124">Audio and HD video</span></span>  <br/> |<span data-ttu-id="d9821-125">このレコードの音声会議に人、会議の音声とビデオを許可する、または任意 meeetings (なし) をスケジュールすることを許可しないです。</span><span class="sxs-lookup"><span data-stu-id="d9821-125">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meeetings (none).</span></span>  <br/> |
|<span data-ttu-id="d9821-126">会話および会議のレコーディング</span><span class="sxs-lookup"><span data-stu-id="d9821-126">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="d9821-127">この人を記録することを許可する] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d9821-127">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="d9821-128">このオプションは、Skype for Business の基本的なで利用可能なはできません。</span><span class="sxs-lookup"><span data-stu-id="d9821-128">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="d9821-129">コンプライアンスのため、アーカイブされていない機能はオフにする</span><span class="sxs-lookup"><span data-stu-id="d9821-129">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="d9821-130">電子的に保存されている情報の保管を法律で要請されている場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d9821-130">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="d9821-p104">このオプションを選択するを[インプレース](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx)で Exchange 管理センターの設定があるときにキャプチャされない機能をオフにします。次の機能をオフにします。</span><span class="sxs-lookup"><span data-stu-id="d9821-p104">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in in the Exchange admin center. It turns off the following features: </span></span><br/>  <span data-ttu-id="d9821-133">インスタント メッセージングを使用したファイルの転送</span><span class="sxs-lookup"><span data-stu-id="d9821-133">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="d9821-134">OneNote の共有ページ</span><span class="sxs-lookup"><span data-stu-id="d9821-134">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="d9821-135">PowerPoint のコメント</span><span class="sxs-lookup"><span data-stu-id="d9821-135">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="d9821-p105">一括でこれらの設定を構成するには、PowerShell を使用します。[Skype for Business Online の管理ポリシー](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9821-p105">To configure these settings in bulk, use PowerShell. See [Managing policies in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="d9821-138">外部通信をブロック</span><span class="sxs-lookup"><span data-stu-id="d9821-138">Block external communications</span></span>
<span data-ttu-id="d9821-139"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="d9821-139"></span></span>

<span data-ttu-id="d9821-140">社内の全員の[Skype for Business ユーザーが Skype の連絡先を追加する](let-skype-for-business-users-add-skype-contacts.md)には、選択的に次の手順を使用して特定のユーザーに対して外部通信をブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="d9821-140">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="d9821-141">**ユーザー**を選択し、設定を無効にするには、ユーザーを選択し、[**編集**] を選んで![編集](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)します。</span><span class="sxs-lookup"><span data-stu-id="d9821-141">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="d9821-142">**外部通信**] を選択し、[必要に応じてオプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d9821-142">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
  - <span data-ttu-id="d9821-143">**外部の Skype for Business ユーザー**: ユーザーにフェデレーション ドメインのビジネス ユーザーの Skype との通信を行わない場合このボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d9821-143">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
  - <span data-ttu-id="d9821-144">**外部の Skype ユーザー**: freeSkype アプリを使用しているユーザーと通信できるようにするユーザーをたくない場合このボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d9821-144">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="d9821-145">{[**保存**] をクリックします。}</span><span class="sxs-lookup"><span data-stu-id="d9821-145">Click **Save**.</span></span>
    
<span data-ttu-id="d9821-p106">一括でこれらの設定を構成するには、PowerShell を使用します。[Skype for Business Online 組織外のユーザーとの組織との通信を管理する](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9821-p106">To configure these settings in bulk, use PowerShell. See [Managing communications in Skype for Business Online with outside users and organizations](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="d9821-148">単一ユーザーの電話会議の設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="d9821-148">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="d9821-149"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="d9821-149"></span></span>

1. <span data-ttu-id="d9821-150">**ユーザー**を選び、[ユーザーが電話会議の設定を編集する、[**編集**] を選びます![編集](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)します。</span><span class="sxs-lookup"><span data-stu-id="d9821-150">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="d9821-151">**電話会議**を選択電話会議プロバイダーを選び、または必要な情報を変更して入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9821-151">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="d9821-152">**電話会議の設定**</span><span class="sxs-lookup"><span data-stu-id="d9821-152">**Audio conferencing setting**</span></span>|<span data-ttu-id="d9821-153">**{Description}**</span><span class="sxs-lookup"><span data-stu-id="d9821-153">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d9821-154">**プロバイダー名**</span><span class="sxs-lookup"><span data-stu-id="d9821-154">**Provider name**</span></span> <br/> |<span data-ttu-id="d9821-155">リストから、プロバイダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d9821-155">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="d9821-156">**有料電話番号**(必須)</span><span class="sxs-lookup"><span data-stu-id="d9821-156">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="d9821-p107">サードパーティ ACP には、これらの電話番号は、電話会議プロバイダーから受け取ったものです。ユーザーが電話会議プロバイダーとして Microsoft を使用している場合は、電話会議ブリッジに設定されている数値これらがされます。[数値の書式を設定して、ビジネスや Microsoft チーム会議出席依頼の Skype で表示されるようにしたいとします。</span><span class="sxs-lookup"><span data-stu-id="d9821-p107">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="d9821-160">**フリー ダイヤル番号**</span><span class="sxs-lookup"><span data-stu-id="d9821-160">**Toll-free number**</span></span> <br/> |<span data-ttu-id="d9821-p108">サードパーティ ACP には、これらの電話番号は、電話会議プロバイダーから受け取ったものです。ユーザーが電話会議プロバイダーとして Microsoft を使用している場合は、電話会議ブリッジに設定されている数値これらがされます。[数値の書式を設定して、ビジネスや Microsoft チーム会議出席依頼の Skype で表示されるようにしたいとします。</span><span class="sxs-lookup"><span data-stu-id="d9821-p108">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="d9821-164">**電話会議 ID と PIN**(必須)</span><span class="sxs-lookup"><span data-stu-id="d9821-164">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="d9821-p109">PIN の参加者または会議コード、このユーザーによってスケジュールされ、は、サードパーティ電話会議プロバイダーから提供を会議に参加するために使用します。ユーザーが電話会議プロバイダーとして Microsoft を使用している場合は、必要なこの、られません。</span><span class="sxs-lookup"><span data-stu-id="d9821-p109">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="d9821-p110">一括でこれらの設定を構成するには、PowerShell を使用します。[携帯電話への招待に含まれる数値の設定](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9821-p110">To configure these settings in bulk, use PowerShell. See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="d9821-169">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d9821-169">Related topics</span></span> 

[<span data-ttu-id="d9821-170">Skype for Business Online をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="d9821-170">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="d9821-171">Skype Business および Microsoft チーム アドオン ライセンスを許可します。</span><span class="sxs-lookup"><span data-stu-id="d9821-171">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
