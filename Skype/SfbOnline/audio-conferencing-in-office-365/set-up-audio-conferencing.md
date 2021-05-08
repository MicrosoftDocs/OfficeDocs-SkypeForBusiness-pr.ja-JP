---
title: 会議の電話会議を設定Skype for Business
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
- O365P_DialInConfDesc
description: '電話を使用して電話会議に参加する必要がある社内ユーザーのダイヤルイン会議または電話会議をセットアップする方法について説明します。 '
ms.openlocfilehash: ce5d80b8be0fe2e6983229be8185bcdf02e06ab6
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237643"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a><span data-ttu-id="1f1b1-103">会議の電話会議を設定Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1f1b1-103">Set up Audio Conferencing for Skype for Business</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="1f1b1-104">組織内のユーザーが、会議にダイヤル インするために電話機を使用する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="1f1b1-105">Skype for Business、この状況に合った電話会議機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-105">Skype for Business includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="1f1b1-106">モバイル デバイスや PC で Skype for Business アプリを使用する代わりに、電話を使ってSkype for Business会議にコールインできます。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-106">People can call in to Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="1f1b1-p102">電話会議の設定は、会議のスケジュールを設定または会議を進行するユーザーに対してのみ必要です。ダイヤルインで参加するユーザーについては、ライセンスの割り当てや他の設定は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="1f1b1-109">電話会議についてよく寄せられる質問については、 [電話会議についてよくある質問](/MicrosoftTeams/audio-conferencing-common-questions) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](/MicrosoftTeams/audio-conferencing-common-questions).</span></span>

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="1f1b1-110">手順 1: 自分の国/地域で電話会議が使用可能かどうか確認する</span><span class="sxs-lookup"><span data-stu-id="1f1b1-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="1f1b1-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="1f1b1-111"><a name="__top"> </a></span></span>

<span data-ttu-id="1f1b1-112">「[国・地域別の電話会議と通話プランの利用可能状況](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)」を開き、ご自分の国または地域を選択して、電話会議についての情報に加えて、電話システム、通話プラン、有料・無料通話番号、コミュニケーション クレジットについての情報も取得してください。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="1f1b1-113">手順 2: ライセンスを取得して割り当てる</span><span class="sxs-lookup"><span data-stu-id="1f1b1-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="1f1b1-114">電話会議では、ダイヤルイン会議をセットアップするユーザーごとにライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="1f1b1-115">電話会議で購入する必要があるライセンスと、その料金については、「追加機能のライセンスSkype for Business[を参照してください](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="1f1b1-116">電話会議は Office 365 Enterprise E5 ライセンスにアドオンとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="1f1b1-117">電話会議ライセンスを購入した後は、それらのライセンスを、会議を計画または開催しようとしている組織内のユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="1f1b1-118">「[会議をスケジュールまたは開催Microsoft 365 Apps for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)組織内のユーザーに購入したユーザーのライセンスを割り当てるまたは削除する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-118">See [Assign or remove licenses for Microsoft 365 Apps for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="1f1b1-119">また、前の手順でライセンスを割り当てた同じユーザーに、コミュニケーション クレジット ライセンス (費用はかかりません) を割り当てることをおすすめします。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="1f1b1-120">コミュニケーション クレジットのセットアップ方法については、「[組織向けにコミュニケーション クレジットをセットアップする](/microsoftteams/set-up-communications-credits-for-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
    
> [!NOTE]
> <span data-ttu-id="1f1b1-121">[分毎課金の電話会議](/microsoftteams/audio-conferencing-pay-per-minute)をセットアップすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-121">You can also set up [pay-per-minute Audio Conferencing](/microsoftteams/audio-conferencing-pay-per-minute).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="1f1b1-122">手順 3: 会議ブリッジのサービス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="1f1b1-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="1f1b1-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="1f1b1-123"><a name="__top"> </a></span></span>

<span data-ttu-id="1f1b1-124">電話会議では、ユーザーの電話番号を使うことはできません。サービス番号を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="1f1b1-125">会議ブリッジ用に、有料または無料のサービス番号のいずれかを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="1f1b1-126">有料サービス番号と無料サービス番号を取得する方法は 3 通りあります。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="1f1b1-127">**管理センター Skype for Business使用します**。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-127">**Use the Skype for Business admin center**.</span></span> <span data-ttu-id="1f1b1-128">一部の国/地域では、管理センターで会議ブリッジのサービス番号Skype for Business取得できます。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center.</span></span> <span data-ttu-id="1f1b1-129">「[サービス電話番号の取得](/microsoftteams/getting-service-phone-numbers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="1f1b1-130">**既存のサービス番号を移行する**。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="1f1b1-131">既存の番号を現在のサービス プロバイダーまたは電話会社から Microsoft 365 または Office 365 に移行または転送します。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-131">To port or transfer existing numbers from your current service provider or phone carrier to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="1f1b1-132">この方法の詳細については、「[Teams に電話番号を移行する](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)」または「[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-132">You can see [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="1f1b1-133">**申請書を使用して新しい番号を求める**。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="1f1b1-134">(お客様の国/地域によっては) Skype for Business 管理センターを使用して新しいサービス番号を取得できない場合や、特定の電話番号または市番が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="1f1b1-135">その場合は、申請書をダウンロードして送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="1f1b1-136">詳細については「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-136">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="1f1b1-137">手順 4: 会議ブリッジにサービス番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="1f1b1-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="1f1b1-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="1f1b1-138"><a name="__top"> </a></span></span>

<span data-ttu-id="1f1b1-139">会議ブリッジ用に有料電話番号と無料電話番号のいずれかまたは両方を取得したら、それらの番号を割り当てて、会議の招集に使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="1f1b1-140">電話会議ブリッジに新規の電話番号を割り当てるには:</span><span class="sxs-lookup"><span data-stu-id="1f1b1-140">To assign a new phone number to your audio conferencing bridge:</span></span>

<span data-ttu-id="1f1b1-141">![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="1f1b1-141">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="1f1b1-142">**[Microsoft 365 管理センター]** > **[管理センター]** > **[Teams]** > **[従来のポータル]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="1f1b1-143">**[音声]**  >  **[電話番号]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="1f1b1-144">電話番号を選択し、**[割り当て]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="1f1b1-145">詳細については、「[電話会議ブリッジの電話番号を変更する](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-145">For more details, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="1f1b1-146">手順 5: 会議ブリッジ用の既定言語と第 2 言語を設定する</span><span class="sxs-lookup"><span data-stu-id="1f1b1-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="1f1b1-147"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="1f1b1-147"><a name="__top"> </a></span></span>

<span data-ttu-id="1f1b1-148">次に、電話会議[](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)の電話番号にダイヤルインするときに、電話会議の自動応答が発信者にあいさつするために使用する電話会議の自動応答言語を設定します。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-148">Next, you want to [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="1f1b1-149">![Microsoft Teams ロゴを示すアイコン](../images/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**:</span><span class="sxs-lookup"><span data-stu-id="1f1b1-149">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="1f1b1-150">ダッシュボードから **[会議]** > **[会議ブリッジ]** の順に開きます。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-150">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="1f1b1-151">会議ブリッジ電話番号を選択して **[編集]** をクリックし、既定の言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-151">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

<span data-ttu-id="1f1b1-152">![[管理センターを使用Skype for Business ](../images/sfb-logo-30x30.png) **ロゴを示Skype for Businessアイコン**:</span><span class="sxs-lookup"><span data-stu-id="1f1b1-152">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**:</span></span>

1. <span data-ttu-id="1f1b1-153">[管理センター] に移動し、[>**ポータル**  >  **] Teams**  >  **管理センターに移動します**。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-153">Go to the admin center > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="1f1b1-154">[電話 **会議 Microsoft**  >  **Bridge] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-154">Select **Audio conferencing** > **Microsoft bridge**.</span></span> 
3. <span data-ttu-id="1f1b1-155">会議ブリッジの電話番号を選択し、[ **言語の設定**] を選択して、既定の言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-155">Select the conferencing bridge phone number, select **Set languages**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="1f1b1-156">手順 6: 会議ブリッジを設定する</span><span class="sxs-lookup"><span data-stu-id="1f1b1-156">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="1f1b1-157"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="1f1b1-157"><a name="__top"> </a></span></span>
    
<span data-ttu-id="1f1b1-158">会議ブリッジをセットアップした後、使用する開始/終了の通知と PIN の長さが正しいかなど、既定の設定を確認します。正しくない場合は、変更することができます。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-158">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="1f1b1-159">![Microsoft Teams ロゴを示すアイコン](../images/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**:</span><span class="sxs-lookup"><span data-stu-id="1f1b1-159">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="1f1b1-160">ダッシュボードから **[会議]** > **[会議ブリッジ]** の順に開きます。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-160">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="1f1b1-161">**[ブリッジの設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-161">Select **Bridge settings**.</span></span> <span data-ttu-id="1f1b1-162">[**ブリッジの設定**] ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-162">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="1f1b1-163">詳細については、[電話会議ブリッジの設定を変更する](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-163">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

<span data-ttu-id="1f1b1-164">![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="1f1b1-164">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="1f1b1-165">**[Microsoft 365 管理センター]** > **[管理センター]** > **[Teams]** > **[従来のポータル]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-165">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="1f1b1-166">[電話 **会議]**  >  **[Microsoft ブリッジの設定] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-166">Select **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="1f1b1-167">[**Microsoft ブリッジの設定** ] ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-167">This will open the **Microsoft bridge settings** page.</span></span> 

<span data-ttu-id="1f1b1-168">詳細については、[電話会議ブリッジの設定を変更する](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-168">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="1f1b1-169">手順 7: 会議を開催するユーザー向けにダイヤルインの電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="1f1b1-169">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="1f1b1-170">電話会議ブリッジを作成した後、ユーザー向けに有料番号と無料番号を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-170">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="1f1b1-171">この操作を、会議を主催したり計画している組織内のすべてのユーザーに対して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-171">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="1f1b1-172">![Microsoft Teams ロゴを示すアイコン](../images/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**:</span><span class="sxs-lookup"><span data-stu-id="1f1b1-172">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="1f1b1-173">ダッシュボードから **[ユーザー]** をクリックし、リストからユーザーを選択して **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-173">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="1f1b1-174">**[電話会議]** の次にある **[編集]** をクリックしてから **[電話会議]** ウィンドウで **[有料番号]** と **[無料番号]** の番号リストから、番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-174">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="1f1b1-175">![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="1f1b1-175">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="1f1b1-176">[レガシ **ポータルMicrosoft 365管理**  >  **センター Teams**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-176">Go to the **Microsoft 365 admin center** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="1f1b1-177">[**電話会議ユーザー]**  >  **を選択** し、一覧からユーザーを選択し、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-177">Select **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**.</span></span> 

<span data-ttu-id="1f1b1-178">さらに詳細が必要な場合は、「[Microsoft を電話会議プロバイダーとして割り当てる](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-178">If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="1f1b1-179">手順 8: 会議の招集をセットアップする（オプション）</span><span class="sxs-lookup"><span data-stu-id="1f1b1-179">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="1f1b1-180"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="1f1b1-180"><a name="__top"> </a></span></span>
 
<span data-ttu-id="1f1b1-181">ユーザー向けに設定されているダイヤルイン番号は、会議の出席者に送信される会議招集に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-181">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="1f1b1-182">ただし、必要に応じて、独自のヘルプや法律のリンク、テキスト メッセージ、小さな会社のグラフィックを追加できます。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-182">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="1f1b1-183">「[会議への招待状をカスタマイズする](../set-up-skype-for-business-online/customize-meeting-invitations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f1b1-183">See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="1f1b1-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f1b1-184">Related topics</span></span>

[<span data-ttu-id="1f1b1-185">電話会議に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="1f1b1-185">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
  
[<span data-ttu-id="1f1b1-186">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="1f1b1-186">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="1f1b1-187">電話会議の電話番号</span><span class="sxs-lookup"><span data-stu-id="1f1b1-187">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="1f1b1-188">オンライン会議、電話会議のオプションを設定</span><span class="sxs-lookup"><span data-stu-id="1f1b1-188">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
