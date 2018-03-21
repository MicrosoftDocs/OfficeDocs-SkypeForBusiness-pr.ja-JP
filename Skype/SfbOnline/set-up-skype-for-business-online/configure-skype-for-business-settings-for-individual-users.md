---
title: "管理者の個々 のユーザー設定のビジネスの Skype の構成"
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
description: "個々 のユーザーについては、ビジネスの Skype を次のように変更する方法について: オーディオおよびビデオ会議、通話の記録との会議。 "
ms.openlocfilehash: 3be7ff64d3dfe84ea05753de77f4b0420c6e5787
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2018
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="7f19e-103">管理者: 個々 のユーザーについては、ビジネスの Skype を構成します。</span><span class="sxs-lookup"><span data-stu-id="7f19e-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="7f19e-104">この資料では、管理者がユーザーの数が少ないためにビジネスの Skype をどのように構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f19e-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="7f19e-105">一括でこれらの手順を行うには、Windows PowerShell コマンドレットを使用することができますへのリンク掲載されています。</span><span class="sxs-lookup"><span data-stu-id="7f19e-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="7f19e-106">許可 (またはブロック) 外部ユーザーと通信するためにお客様のビジネスのすべてのメンバーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f19e-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="7f19e-107">[ビジネス ユーザー向けの外部の Skype に連絡を許可する](allow-users-to-contact-external-skype-for-business-users.md): 組織が使用できるように Skype をビジネス機能 (デスクトップの共有、オンラインなどは、ユーザーのファイルの場所) の高度な特定のユーザーと通信するために信頼できるビジネス (連合)。</span><span class="sxs-lookup"><span data-stu-id="7f19e-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="7f19e-108">特定のドメインとの通信をブロックする方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="7f19e-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="7f19e-109">[ビジネス ユーザー向けの Skype は、Skype 連絡先を追加](let-skype-for-business-users-add-skype-contacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="7f19e-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="7f19e-110">組織のビジネスを検索するのには、Skype では、無料のアプリを使用する IM ユーザーの Skype を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="7f19e-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="7f19e-111">1 人のユーザーの一般的な設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="7f19e-111">Configure general settings for one user</span></span>
<span data-ttu-id="7f19e-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="7f19e-112"></span></span>

<span data-ttu-id="7f19e-113">次の手順を実行する[管理者のアクセス許可](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)が必要です。</span><span class="sxs-lookup"><span data-stu-id="7f19e-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>
  
1. <span data-ttu-id="7f19e-114">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="7f19e-114">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="7f19e-115">Choose **Admin centers** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="7f19e-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="7f19e-116">[ **ユーザー**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="7f19e-116">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="7f19e-118">編集しユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7f19e-118">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="7f19e-119">右側のウィンドウで、[ **編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="7f19e-119">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="7f19e-121">[**全般**オプション] ページで、選択または、変更する機能の横にチェック ボックスをオフにし、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="7f19e-121">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="7f19e-122">**オプション**</span><span class="sxs-lookup"><span data-stu-id="7f19e-122">**Option**</span></span>|<span data-ttu-id="7f19e-123">**詳細**</span><span class="sxs-lookup"><span data-stu-id="7f19e-123">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7f19e-124">オーディオと HD ビデオ</span><span class="sxs-lookup"><span data-stu-id="7f19e-124">Audio and HD video</span></span>  <br/> |<span data-ttu-id="7f19e-125">させるにはこのユーザーがレコードのオーディオ会議、オーディオおよびビデオ会議、または (なし)、meeetings のスケジュールを設定することができません。</span><span class="sxs-lookup"><span data-stu-id="7f19e-125">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meeetings (none).</span></span>  <br/> |
|<span data-ttu-id="7f19e-126">レコードの会話と会議</span><span class="sxs-lookup"><span data-stu-id="7f19e-126">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="7f19e-127">このユーザーの許可を記録する」を選択します。</span><span class="sxs-lookup"><span data-stu-id="7f19e-127">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="7f19e-128">このオプションでは、ビジネスの基本の Skype で利用可能なできません。</span><span class="sxs-lookup"><span data-stu-id="7f19e-128">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="7f19e-129">準拠するため非アーカイブ機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="7f19e-129">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="7f19e-130">電子的に保存されている情報を保持するために法的に必要な場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7f19e-130">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="7f19e-131">このオプションを選択することは、[インプレース保持](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx)Exchange 管理センターで設定がある場合にキャプチャされていない機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="7f19e-131">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in in the Exchange admin center.</span></span> <span data-ttu-id="7f19e-132">次の機能をオフにします。</span><span class="sxs-lookup"><span data-stu-id="7f19e-132">It turns off the following features:</span></span> <br/>  <span data-ttu-id="7f19e-133">インスタント メッセージングを使用したファイルの転送</span><span class="sxs-lookup"><span data-stu-id="7f19e-133">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="7f19e-134">OneNote の共有ページ</span><span class="sxs-lookup"><span data-stu-id="7f19e-134">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="7f19e-135">PowerPoint のコメント</span><span class="sxs-lookup"><span data-stu-id="7f19e-135">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="7f19e-136">一括でこれらの設定を構成するには、PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="7f19e-136">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="7f19e-137">[Skype のビジネスをオンラインで管理するポリシー](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f19e-137">See [Managing policies in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="7f19e-138">ブロック外部との連絡</span><span class="sxs-lookup"><span data-stu-id="7f19e-138">Block external communications</span></span>
<span data-ttu-id="7f19e-139"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="7f19e-139"></span></span>

<span data-ttu-id="7f19e-140">すべてのユーザー、会社の[ビジネス ユーザー向けの Skype は、Skype 連絡先を追加](let-skype-for-business-users-add-skype-contacts.md)した後、次の手順を使用して特定の個人の外部との連絡を選択的にブロックできます。</span><span class="sxs-lookup"><span data-stu-id="7f19e-140">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="7f19e-141">**ユーザー**を選択し、ユーザー設定を無効にするを選択し、**編集**を選択し、![の編集](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)。</span><span class="sxs-lookup"><span data-stu-id="7f19e-141">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="7f19e-142">**外部との連絡**を選択し、必要に応じてオプションをオフにし、します。</span><span class="sxs-lookup"><span data-stu-id="7f19e-142">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
  - <span data-ttu-id="7f19e-143">**ビジネス ユーザー向けの外部の Skype**: このボックスをオフにしない場合は、ユーザーがフェデレーション ドメイン内のビジネス ユーザーの Skype で通信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="7f19e-143">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
  - <span data-ttu-id="7f19e-144">**外部 Skype ユーザー**: freeSkype アプリケーションを使用しているユーザーと通信できることをユーザーがしない場合はこのボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="7f19e-144">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="7f19e-145">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7f19e-145">Click **Save**.</span></span>
    
<span data-ttu-id="7f19e-146">一括でこれらの設定を構成するには、PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="7f19e-146">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="7f19e-147">[外部のユーザーや組織のビジネスのオンラインの Skype での通信を管理する](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f19e-147">See [Managing communications in Skype for Business Online with outside users and organizations](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="7f19e-148">1 人のユーザーのオーディオ会議設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="7f19e-148">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="7f19e-149"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="7f19e-149"></span></span>

1. <span data-ttu-id="7f19e-150">**ユーザー**を選択して、電話会議の設定を編集するユーザーを選択、し、[**編集**] をクリックし、![を編集](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)。</span><span class="sxs-lookup"><span data-stu-id="7f19e-150">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="7f19e-151">**オーディオ会議**を選択してオーディオ会議プロバイダーを選択して、または要求された情報を変更し、入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7f19e-151">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="7f19e-152">**電話会議の設定**</span><span class="sxs-lookup"><span data-stu-id="7f19e-152">**Audio conferencing setting**</span></span>|<span data-ttu-id="7f19e-153">**説明**</span><span class="sxs-lookup"><span data-stu-id="7f19e-153">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7f19e-154">**プロバイダー名**</span><span class="sxs-lookup"><span data-stu-id="7f19e-154">**Provider name**</span></span> <br/> |<span data-ttu-id="7f19e-155">リストから、プロバイダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7f19e-155">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="7f19e-156">**有料電話番号** (必須)</span><span class="sxs-lookup"><span data-stu-id="7f19e-156">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="7f19e-157">サード ・ パーティ製 ACP では、これらの電話番号は、オーディオ会議プロバイダーから入手したものです。</span><span class="sxs-lookup"><span data-stu-id="7f19e-157">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="7f19e-158">場合は、ユーザーは、Microsoft を使用してオーディオ会議プロバイダーとしては、これらをオーディオ会議ブリッジで設定されている番号となります。</span><span class="sxs-lookup"><span data-stu-id="7f19e-158">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="7f19e-159">ビジネスおよびマイクロソフトのチームの会議出席依頼の Skype に表示する数値書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="7f19e-159">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="7f19e-160">**フリー ダイヤル番号**</span><span class="sxs-lookup"><span data-stu-id="7f19e-160">**Toll-free number**</span></span> <br/> |<span data-ttu-id="7f19e-161">サード ・ パーティ製 ACP では、これらの電話番号は、オーディオ会議プロバイダーから入手したものです。</span><span class="sxs-lookup"><span data-stu-id="7f19e-161">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="7f19e-162">場合は、ユーザーは、Microsoft を使用してオーディオ会議プロバイダーとしては、これらをオーディオ会議ブリッジで設定されている番号となります。</span><span class="sxs-lookup"><span data-stu-id="7f19e-162">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="7f19e-163">ビジネスおよびマイクロソフトのチームの会議出席依頼の Skype に表示する数値書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="7f19e-163">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="7f19e-164">**会議 ID と暗証番号 (pin)**(必須)</span><span class="sxs-lookup"><span data-stu-id="7f19e-164">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="7f19e-165">参加者暗証番号 (pin)、または会議コード、このユーザーが自動的にスケジュールし、サード ・ パーティ製のオーディオ会議プロバイダーから提供されているミーティングに参加するために使用します。</span><span class="sxs-lookup"><span data-stu-id="7f19e-165">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="7f19e-166">場合は、ユーザーは、Microsoft を使用してオーディオ会議プロバイダーとしては、必要な必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7f19e-166">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="7f19e-167">一括でこれらの設定を構成するには、PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="7f19e-167">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="7f19e-168">「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7f19e-168">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="7f19e-169">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7f19e-169">Related topics</span></span> 

[<span data-ttu-id="7f19e-170">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="7f19e-170">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="7f19e-171">Skype for Business と Microsoft Teams のアドオン ライセンス</span><span class="sxs-lookup"><span data-stu-id="7f19e-171">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
## <a name="feedback"></a><span data-ttu-id="7f19e-172">フィードバックですか。</span><span class="sxs-lookup"><span data-stu-id="7f19e-172">Feedback?</span></span>
<span data-ttu-id="7f19e-173">製品に関するフィードバックを提供するには、かをお知らせいただいて、取り組み方は、 [Skype](https://www.skypefeedback.com)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f19e-173">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>