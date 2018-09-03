---
title: Skype for Business と Microsoft Teams の電話会議のセットアップ
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '電話機を使用して電話会議に参加する必要のある社内のユーザー向けに、ダイヤルインまたは電話会議をセットアップする方法を説明します。 '
ms.openlocfilehash: 02c04afa0a1079a53123ee56094dc6ddc764038c
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780533"
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a><span data-ttu-id="fc4aa-103">Skype for Business と Microsoft Teams の電話会議のセットアップ</span><span class="sxs-lookup"><span data-stu-id="fc4aa-103">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>

<span data-ttu-id="fc4aa-104">組織内のユーザーが、会議を呼び出すために電話機を使用する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="fc4aa-105">Skype for Business と Microsoft Teams には、このような状況に最適な電話会議の機能があります。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-105">Skype for Business and Microsoft Teams include the Audio Conferencing feature for just this situation!</span></span> <span data-ttu-id="fc4aa-106">ユーザーは、モバイル デバイスや PC 上の Skype for Business アプリや Microsoft Teams アプリを使用しなくても、電話機を使用して Skype for Business 会議や Microsoft Teams 会議を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-106">People can call into Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="fc4aa-107">必要なのは、会議を計画したり主催しようとしているユーザー向けに電話会議をセットアップすることだけです。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-107">You only need to set up dial-in conferencing for users who plan to schedule or lead meetings.</span></span> <span data-ttu-id="fc4aa-108">ダイヤルインする会議参加者には、割り当てられたライセンスやその他のセットアップは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="fc4aa-109">電話会議についてよく寄せられる質問については、「[電話会議についてよくある質問](/MicrosoftTeams/audio-conferencing-common-questions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](/MicrosoftTeams/audio-conferencing-common-questions).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="fc4aa-110">手順 1: 自分の国/地域で電話会議が使用可能かどうか確認する</span><span class="sxs-lookup"><span data-stu-id="fc4aa-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="fc4aa-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="fc4aa-111"><a name="__top"> </a></span></span>


<span data-ttu-id="fc4aa-112">「[国・地域別の電話会議と通話プランの利用可能状況](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)」を開き、ご自分の国または地域を選択して、電話会議についての情報に加えて、電話システム、通話プラン、有料・無料通話番号、コミュニケーション クレジットについての情報も取得してください。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="fc4aa-113">手順 2: ライセンスを取得して割り当てる</span><span class="sxs-lookup"><span data-stu-id="fc4aa-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="fc4aa-114">電話会議では、ダイヤルイン会議をセットアップするユーザーごとにライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="fc4aa-115">電話会議のために購入する必要のあるライセンスの種類と必要コストについては、「[Skype for Business と Microsoft Teams のアドイン ライセンス付与](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
        
2. <span data-ttu-id="fc4aa-116">電話会議ライセンスを購入した後は、それらのライセンスを、会議を計画したり開催しようとしている組織内のユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-116">After you buy the Audio Conferencing licenses, you will ned to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="fc4aa-117">会議を計画したり主催しようとしてるユーザーに対して購入した「[法人向け Office 365 ライセンスの割り当てと削除](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-117">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="fc4aa-118">また、前の手順でライセンスを割り当てた同じユーザーに、コミュニケーション クレジット ライセンス (費用はかかりません) を割り当てることをおすすめします。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-118">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="fc4aa-119">コミュニケーション クレジットのセットアップ方法については、「[組織向けにコミュニケーション クレジットをセットアップする](/microsoftteams/set-up-communications-credits-for-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-119">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
    
> [!NOTE]
> <span data-ttu-id="fc4aa-120">分毎課金の電話会議をセットアップすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-120">You can also set up pay-per-minute Audio Conferencing.</span></span> <span data-ttu-id="fc4aa-121">[こちら](/microsoftteams/audio-conferencing-pay-per-minute)を開いて、それらの使用方法の詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-121">Go [here](/microsoftteams/audio-conferencing-pay-per-minute) to find out more about how to use them.</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="fc4aa-122">手順 3: 会議ブリッジのサービス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="fc4aa-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="fc4aa-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="fc4aa-123"><a name="__top"> </a></span></span>

<span data-ttu-id="fc4aa-124">電話会議では、ユーザーの電話番号を使うことはできません。サービス番号を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="fc4aa-125">会議ブリッジ用に、有料または無料のサービス番号のいずれかを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="fc4aa-126">有料サービス番号と無料サービス番号を取得する方法は 3 通りあります。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="fc4aa-127">**Skype for Business 管理センターを使用する。**</span><span class="sxs-lookup"><span data-stu-id="fc4aa-127">**Use the Skype for Business admin center**</span></span> <span data-ttu-id="fc4aa-128">いくつかの国/地域では、Skype for Business 管理センターを使用して、会議ブリッジ用にサービス番号を取得できます。「[サービス電話番号の取得](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center, see [Getting service phone numbers](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span>
    
- <span data-ttu-id="fc4aa-129">**既存のサービス番号を移行する。**</span><span class="sxs-lookup"><span data-stu-id="fc4aa-129">**** Port or transfer existing service numbers</span></span> <span data-ttu-id="fc4aa-130">現在のサービス プロバイダーまたは電話通信会社から、Office 365 に既存の番号を移行します。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-130">Port or transfer your existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="fc4aa-131">この方法の詳細については、「[Office 365 に電話番号を移行](/microsoftteams/transfer-phone-numbers-to-office-365)」または「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-131">You can see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="fc4aa-132">**新規の番号を取得するには、リクエスト フォームを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="fc4aa-132">**Use a request form for new numbers.**</span></span> <span data-ttu-id="fc4aa-133">国や地域によっては、Skype for Business 管理センターを使用して新規のサービス番号を取得できない場合や、特定の電話番号や地域コードが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-133">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="fc4aa-134">その場合は、フォームをダウンロードして記入し、当社に返送していただく必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-134">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="fc4aa-135">詳細については「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-135">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="fc4aa-136">手順 4: 会議ブリッジにサービス番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="fc4aa-136">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="fc4aa-137"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="fc4aa-137"><a name="__top"> </a></span></span>

<span data-ttu-id="fc4aa-138">会議ブリッジ用に有料電話番号と無料電話番号のいずれかまたは両方を取得したら、それらの番号を割り当てて、会議の招集に使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-138">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invites.</span></span>  

<span data-ttu-id="fc4aa-139">電話会議ブリッジに新規の電話番号を割り当てるには:</span><span class="sxs-lookup"><span data-stu-id="fc4aa-139">To assign a new phone number to your audio conferencing bridge:</span></span>

<span data-ttu-id="fc4aa-140">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business 管理センターを使用する:**</span><span class="sxs-lookup"><span data-stu-id="fc4aa-140">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

 <span data-ttu-id="fc4aa-141">[**Office 365 管理センター**]  >  [**管理センター**]  >  [**Skype for Business**]  >  [**音声**]  >  [**電話番号**] の順に開き、電話番号を選択して [**割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-141">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Voice** > **Phone numbers**, select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="fc4aa-142">詳細については、「[電話会議ブリッジの電話番号を変更する](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-142">For more details, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="fc4aa-143">手順 5: 会議ブリッジ用の既定言語と第 2 言語を設定する</span><span class="sxs-lookup"><span data-stu-id="fc4aa-143">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="fc4aa-144"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="fc4aa-144"><a name="__top"> </a></span></span>

<span data-ttu-id="fc4aa-145">次に、電話会議の電話番号にダイヤルインした時に、呼び出しをしたユーザーに挨拶をするのに会議の自動応答で使用する「[電話会議の自動応答の言語を設定](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)」します。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-145">Next, you want to [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the conferencing auto attendant uses to greet a caller when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="fc4aa-146">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Microsoft Teams と Skype for Business 管理センターを使用する: **</span><span class="sxs-lookup"><span data-stu-id="fc4aa-146">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

<span data-ttu-id="fc4aa-147">ダッシュボードから、[**会議**]  >  [**会議ブリッジ**] の順に開き、会議ブリッジ電話番号を選択して [**編集**] をクリックし、既定言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-147">From the Dashboard, go to **Meetings** > **Conference bridges**, select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

<span data-ttu-id="fc4aa-148">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business 管理センターを使用する:**</span><span class="sxs-lookup"><span data-stu-id="fc4aa-148">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="fc4aa-149">[**Office 365 管理センター**]  >  [**管理センター**]  >  [**Skype for Business**]  >  [**電話会議**]  >  [**Microsoft ブリッジの設定**] の順に開き、会議ブリッジ電話番号を選択して [**言語の設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-149">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** > **Microsoft bridge settings**,  select the conferencing bridge phone number, and then click **Set languages**.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="fc4aa-150">手順 6: 会議ブリッジを設定する</span><span class="sxs-lookup"><span data-stu-id="fc4aa-150">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="fc4aa-151"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="fc4aa-151"><a name="__top"> </a></span></span>
    
<span data-ttu-id="fc4aa-152">会議ブリッジをセットアップした後、使用する開始/終了の通知と PIN の長さが正しいかなど、既定の設定を確認します。正しくない場合は、変更することができます。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-152">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="fc4aa-153">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Microsoft Teams と Skype for Business 管理センターを使用する: **</span><span class="sxs-lookup"><span data-stu-id="fc4aa-153">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

<span data-ttu-id="fc4aa-154">ダッシュボードから、[**会議**]  >  [**会議ブリッジ**]  >  [**ブリッジの設定**] の順に開きます。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-154">From the Dashboard, go to **Meetings** > **Conference bridges** > **Bridge settings**.</span></span> <span data-ttu-id="fc4aa-155">[**ブリッジの設定**] ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-155">This will open the **Bridge settings** pane.</span></span> <span data-ttu-id="fc4aa-156">詳細については、「[電話会議ブリッジの設定を変更する](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-156">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

<span data-ttu-id="fc4aa-157">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business 管理センターを使用する:**</span><span class="sxs-lookup"><span data-stu-id="fc4aa-157">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="fc4aa-158">[**Office 365 管理センター**]  >  [**管理センター**]  >  [**Skype for Business**]  >  [**電話会議**]  >  [**Microsoft ブリッジの設定**] の順に開きます。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-158">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="fc4aa-159">[**Microsoft ブリッジの設定** ] ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-159">This will open the **Microsoft bridge settings** page.</span></span> <span data-ttu-id="fc4aa-160">詳細については、[電話会議ブリッジの設定を変更する](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-160">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="fc4aa-161">手順 7: 会議を開催するユーザー向けにダイヤルインの電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="fc4aa-161">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="fc4aa-162">電話会議ブリッジを作成した後、ユーザー向けに有料番号と無料番号を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-162">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="fc4aa-163">この操作を、会議を主催したり計画している組織内のすべてのユーザーに対して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-163">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> <span data-ttu-id="fc4aa-164">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-164">To do this:</span></span>

<span data-ttu-id="fc4aa-165">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Microsoft Teams と Skype for Business 管理センターを使用する: **</span><span class="sxs-lookup"><span data-stu-id="fc4aa-165">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

<span data-ttu-id="fc4aa-166">ダッシュボードから、[**ユーザー**] をクリックしてリストからユーザーを選択し、[**編集**] をクリック、[**電話会議**] の次にある [**編集**] をクリックして、[**電話会議**] ウィンドウで [**有料番号**] と [**無料番号**] の番号リストから、番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-166">From the Dashboard, click **Users**, select the user from the list, click **Edit**, click **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="fc4aa-167">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business 管理センターを使用する:**</span><span class="sxs-lookup"><span data-stu-id="fc4aa-167">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="fc4aa-168">[**Office 365 管理センター**]  >  [**Skype for Business**]  >  [**電話会議**]  >  [**ユーザー**] の順に開き、リストからユーザーを選択して [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-168">Go to the **Office 365 admin center** > **Skype for Business** > **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**.</span></span> <span data-ttu-id="fc4aa-169">さらに詳細が必要な場合は、「[Microsoft を電話会議プロバイダーとして割り当てる](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-169">If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="fc4aa-170">手順 8: 会議の招集をセットアップする（オプション）</span><span class="sxs-lookup"><span data-stu-id="fc4aa-170">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="fc4aa-171"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="fc4aa-171"><a name="__top"> </a></span></span>
 
<span data-ttu-id="fc4aa-172">ユーザー向けに設定されているダイヤルイン番号は、会議の出席者に送信される会議招集に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-172">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="fc4aa-173">ただし、必要に応じて、独自のヘルプや法律のリンク、テキスト メッセージ、小さな会社のグラフィックを追加できます。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-173">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="fc4aa-174">「[会議出席依頼をカスタマイズする](../set-up-skype-for-business-online/customize-meeting-invitations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc4aa-174">[Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md)</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="fc4aa-175">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fc4aa-175">Related topics</span></span>

[<span data-ttu-id="fc4aa-176">電話会議に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="fc4aa-176">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
  
[<span data-ttu-id="fc4aa-177">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="fc4aa-177">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="fc4aa-178">電話会議の電話番号</span><span class="sxs-lookup"><span data-stu-id="fc4aa-178">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="fc4aa-179">オンライン会議、電話会議のオプションを設定</span><span class="sxs-lookup"><span data-stu-id="fc4aa-179">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
