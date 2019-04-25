---
title: ビジネス用の Skype の電話会議を設定します。
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '電話会議に参加するのには、電話を使用する必要があるビジネス人のダイヤルインまたはオーディオ会議を設定する方法について説明します。 '
ms.openlocfilehash: d57eedec13d9bd1c01ec9365fd42c0a4dfdc2d96
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229313"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a><span data-ttu-id="0a289-103">ビジネス用の Skype の電話会議を設定します。</span><span class="sxs-lookup"><span data-stu-id="0a289-103">Set up Audio Conferencing for Skype for Business</span></span>

<span data-ttu-id="0a289-104">自分の組織内のユーザーが、会議にダイヤル インするために電話機を使用する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="0a289-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="0a289-105">ビジネス用の Skype には、これだけの音声会議機能が含まれています!</span><span class="sxs-lookup"><span data-stu-id="0a289-105">Skype for Business includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="0a289-106">人は、モバイル デバイスまたは PC 上のアプリケーションをビジネス用の Skype を使用する代わりに、電話を使用してビジネス ・ ミーティング、Skype を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="0a289-106">People can call in to Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="0a289-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span><span class="sxs-lookup"><span data-stu-id="0a289-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="0a289-109">電話会議についてよく寄せられる質問については、「[電話会議についてよくある質問](/MicrosoftTeams/audio-conferencing-common-questions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a289-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](/MicrosoftTeams/audio-conferencing-common-questions).</span></span>

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="0a289-110">手順 1: 自分の国/地域で電話会議が使用可能かどうか確認する</span><span class="sxs-lookup"><span data-stu-id="0a289-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="0a289-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="0a289-111"><a name="__top"> </a></span></span>

<span data-ttu-id="0a289-112">「[国・地域別の電話会議と通話プランの利用可能状況](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)」を開き、ご自分の国または地域を選択して、電話会議についての情報に加えて、電話システム、通話プラン、有料・無料通話番号、コミュニケーション クレジットについての情報も取得してください。</span><span class="sxs-lookup"><span data-stu-id="0a289-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="0a289-113">手順 2: ライセンスを取得して割り当てる</span><span class="sxs-lookup"><span data-stu-id="0a289-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="0a289-114">電話会議では、ダイヤルイン会議をセットアップするユーザーごとにライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="0a289-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="0a289-115">オーディオ会議と、コストはどのくらいのために購入する必要がありますライセンスについては、 [Skype をビジネスでアドオン ライセンスを許可する](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a289-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="0a289-116">オーディオ会議は、アドオンと Office 365 エンタープライズ E5 のライセンスには含まれています。</span><span class="sxs-lookup"><span data-stu-id="0a289-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="0a289-117">オーディオ会議のライセンスを購入した後は、人、組織の会議やスケジュールを設定するのに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a289-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="0a289-118">会議を計画したり主催しようとしてるユーザーに対して購入した「[法人向け Office 365 ライセンスの割り当てと削除](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a289-118">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="0a289-119">また、前の手順でライセンスを割り当てた同じユーザーに、コミュニケーション クレジット ライセンス (費用はかかりません) を割り当てることをおすすめします。</span><span class="sxs-lookup"><span data-stu-id="0a289-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="0a289-120">コミュニケーション クレジットのセットアップ方法については、「[組織向けにコミュニケーション クレジットをセットアップする](/microsoftteams/set-up-communications-credits-for-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a289-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
    
> [!NOTE]
> <span data-ttu-id="0a289-121">[1 分あたりの支払電話会議](/microsoftteams/audio-conferencing-pay-per-minute)を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="0a289-121">You can also set up [pay-per-minute Audio Conferencing](/microsoftteams/audio-conferencing-pay-per-minute).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="0a289-122">手順 3: 会議ブリッジのサービス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="0a289-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="0a289-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="0a289-123"></span></span>

<span data-ttu-id="0a289-124">電話会議では、ユーザーの電話番号を使うことはできません。サービス番号を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a289-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="0a289-125">会議ブリッジ用に、有料または無料のサービス番号のいずれかを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="0a289-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="0a289-126">有料サービス番号と無料サービス番号を取得する方法は 3 通りあります。</span><span class="sxs-lookup"><span data-stu-id="0a289-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="0a289-127">**ビジネス管理センターの Skype を使用**します。</span><span class="sxs-lookup"><span data-stu-id="0a289-127">**Use the Skype for Business admin center**.</span></span> <span data-ttu-id="0a289-128">一部の国/地域のビジネス管理センターは、Skype を使用して、会議用ブリッジのサービス番号を取得できます。</span><span class="sxs-lookup"><span data-stu-id="0a289-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center.</span></span> <span data-ttu-id="0a289-129">[取得サービスの電話番号](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a289-129">See [Getting service phone numbers](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span>
    
- <span data-ttu-id="0a289-130">**ポートは、既存のサービスの番号**です。</span><span class="sxs-lookup"><span data-stu-id="0a289-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="0a289-131">ポートまたは現在のサービス プロバイダーまたは電話のキャリアからの既存の番号を Office 365 に転送。</span><span class="sxs-lookup"><span data-stu-id="0a289-131">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="0a289-132">この方法の詳細については、「[Office 365 に電話番号を移行](/microsoftteams/transfer-phone-numbers-to-office-365)」または「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a289-132">You can see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="0a289-133">**新しい番号の要求フォームを使用**します。</span><span class="sxs-lookup"><span data-stu-id="0a289-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="0a289-134">場合があります (国または地域) によってことはできませんビジネス管理センターでは、Skype を使用して、新しいサービスの番号を取得するか、特定の電話番号または市外局番が必要です。</span><span class="sxs-lookup"><span data-stu-id="0a289-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="0a289-135">その場合は、フォームをダウンロードして記入してからマイクロソフトに返送する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a289-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="0a289-136">詳細については「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a289-136">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="0a289-137">手順 4: 会議ブリッジにサービス番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="0a289-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="0a289-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="0a289-138"></span></span>

<span data-ttu-id="0a289-139">会議用ブリッジは、有料または無料の電話番号を取得するとは、会議出席依頼に使用できるように番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a289-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="0a289-140">電話会議ブリッジに新規の電話番号を割り当てるには:</span><span class="sxs-lookup"><span data-stu-id="0a289-140">To assign a new phone number to your audio conferencing bridge:</span></span>

<span data-ttu-id="0a289-141">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターに、Skype を使用する:**</span><span class="sxs-lookup"><span data-stu-id="0a289-141">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="0a289-142">**Microsoft 365 管理センター**を参照して > **管理センター** > **チーム** > **従来のポータル**です。</span><span class="sxs-lookup"><span data-stu-id="0a289-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="0a289-143">**音声**を選択して > **の電話番号**です。</span><span class="sxs-lookup"><span data-stu-id="0a289-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="0a289-144">電話番号を選択し、[**割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a289-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="0a289-145">詳細については、「[電話会議ブリッジの電話番号を変更する](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a289-145">For more details, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="0a289-146">手順 5: 会議ブリッジ用の既定言語と第 2 言語を設定する</span><span class="sxs-lookup"><span data-stu-id="0a289-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="0a289-147"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="0a289-147"></span></span>

<span data-ttu-id="0a289-148">次に、[オーディオ会議の自動応答の言語設定](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)にダイヤルするときの電話番号に電話会議の呼び出し元を呼びかけられるように設定するのには、会議自動アテンダントを使用します。</span><span class="sxs-lookup"><span data-stu-id="0a289-148">Next, you want to [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="0a289-149">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **マイクロソフト チームの管理センターを使用**します。</span><span class="sxs-lookup"><span data-stu-id="0a289-149">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="0a289-150">**会議**には、ダッシュ ボードから > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="0a289-150">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="0a289-151">会議ブリッジの電話番号を選択して**編集**を、既定の言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a289-151">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

<span data-ttu-id="0a289-152">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用**します。</span><span class="sxs-lookup"><span data-stu-id="0a289-152">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**:</span></span>

1. <span data-ttu-id="0a289-153">**Office 365 管理センター**を参照して > **管理センター** > **チーム** > **従来のポータル**です。</span><span class="sxs-lookup"><span data-stu-id="0a289-153">Go to the **Office 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="0a289-154">**オーディオ会議**を選択して > **マイクロソフトのブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="0a289-154">Select **Audio conferencing** > **Microsoft bridge**.</span></span> 
3. <span data-ttu-id="0a289-155">会議ブリッジの電話番号を選択、**言語を設定**すると、選択し、既定の言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a289-155">Select the conferencing bridge phone number, select **Set languages**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="0a289-156">手順 6: 会議ブリッジを設定する</span><span class="sxs-lookup"><span data-stu-id="0a289-156">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="0a289-157"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="0a289-157"></span></span>
    
<span data-ttu-id="0a289-158">会議ブリッジをセットアップした後、使用する開始/終了の通知と PIN の長さが正しいかなど、既定の設定を確認します。正しくない場合は、変更することができます。</span><span class="sxs-lookup"><span data-stu-id="0a289-158">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="0a289-159">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **マイクロソフト チームの管理センターを使用**します。</span><span class="sxs-lookup"><span data-stu-id="0a289-159">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="0a289-160">**会議**には、ダッシュ ボードから > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="0a289-160">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="0a289-161">**ブリッジの設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a289-161">Select **Bridge settings**.</span></span> <span data-ttu-id="0a289-162">[**ブリッジの設定**] ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="0a289-162">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="0a289-163">詳細については、[電話会議ブリッジの設定を変更する](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a289-163">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

<span data-ttu-id="0a289-164">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターに、Skype を使用する:**</span><span class="sxs-lookup"><span data-stu-id="0a289-164">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="0a289-165">**Microsoft 365 管理センター**を参照して > **管理センター** > **チーム** > **従来のポータル**です。</span><span class="sxs-lookup"><span data-stu-id="0a289-165">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="0a289-166">**オーディオ会議**を選択して > **Microsoft ブリッジ設定**します。</span><span class="sxs-lookup"><span data-stu-id="0a289-166">Select **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="0a289-167">[**Microsoft ブリッジの設定** ] ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="0a289-167">This will open the **Microsoft bridge settings** page.</span></span> 

<span data-ttu-id="0a289-168">詳細については、[電話会議ブリッジの設定を変更する](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a289-168">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="0a289-169">手順 7: 会議を開催するユーザー向けにダイヤルインの電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="0a289-169">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="0a289-170">電話会議ブリッジを作成した後、ユーザー向けに有料番号と無料番号を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a289-170">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="0a289-171">この操作を、会議を主催したり計画している組織内のすべてのユーザーに対して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a289-171">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="0a289-172">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **マイクロソフト チームの管理センターを使用**します。</span><span class="sxs-lookup"><span data-stu-id="0a289-172">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="0a289-173">ダッシュ ボードで、[**ユーザー**] をクリックし、ボックスの一覧からユーザーを選択して**編集**を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a289-173">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="0a289-174">**オーディオ会議**の横の**編集**を選択して、**オーディオ会議**ウィンドウで、**有料電話番号**や**フリー ダイヤル**番号のリスト内の数値。</span><span class="sxs-lookup"><span data-stu-id="0a289-174">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="0a289-175">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターに、Skype を使用する:**</span><span class="sxs-lookup"><span data-stu-id="0a289-175">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="0a289-176">**Microsoft 365 管理センター**を参照して > **チーム** > **従来のポータル**です。</span><span class="sxs-lookup"><span data-stu-id="0a289-176">Go to the **Microsoft 365 admin center** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="0a289-177">**オーディオ会議**を選択して > **ユーザー**の一覧からユーザーを選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a289-177">Select **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**.</span></span> 

<span data-ttu-id="0a289-178">さらに詳細が必要な場合は、「[Microsoft を電話会議プロバイダーとして割り当てる](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a289-178">If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="0a289-179">手順 8: 会議の招集をセットアップする（オプション）</span><span class="sxs-lookup"><span data-stu-id="0a289-179">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="0a289-180"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="0a289-180"></span></span>
 
<span data-ttu-id="0a289-181">ユーザー向けに設定されているダイヤルイン番号は、会議の出席者に送信される会議招集に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="0a289-181">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="0a289-182">ただし、必要に応じて、独自のヘルプや法律のリンク、テキスト メッセージ、小さな会社のグラフィックを追加できます。</span><span class="sxs-lookup"><span data-stu-id="0a289-182">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="0a289-183">[ミーティングの招待状をカスタマイズする](../set-up-skype-for-business-online/customize-meeting-invitations.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a289-183">See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="0a289-184">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0a289-184">Related topics</span></span>

[<span data-ttu-id="0a289-185">電話会議に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="0a289-185">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
  
[<span data-ttu-id="0a289-186">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="0a289-186">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="0a289-187">電話会議の電話番号</span><span class="sxs-lookup"><span data-stu-id="0a289-187">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="0a289-188">オンライン会議、電話会議のオプションを設定</span><span class="sxs-lookup"><span data-stu-id="0a289-188">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
