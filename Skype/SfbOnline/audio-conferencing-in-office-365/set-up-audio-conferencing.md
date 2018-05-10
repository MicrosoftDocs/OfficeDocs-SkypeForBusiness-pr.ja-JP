---
title: Skype for Business および Microsoft Teams の電話会議のセットアップ
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
description: '電話を使用して会議に参加する必要のあるビジネスで、ユーザーのダイヤルインまたはオーディオ会議を設定する方法について説明します。 '
ms.openlocfilehash: d91a3637a0f7d35d319368017e0f9c6611faf2a7
ms.sourcegitcommit: 4e9574c8a9eac270135684aa4a8b77621aa46403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2018
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a><span data-ttu-id="84cb4-103">Skype for Business および Microsoft Teams の電話会議のセットアップ</span><span class="sxs-lookup"><span data-stu-id="84cb4-103">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>

<span data-ttu-id="84cb4-104">自分の組織内のユーザーが、会議にダイヤル インするために電話機を使用する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="84cb4-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="84cb4-105">Skype ビジネスおよびマイクロソフトのチームには、これだけのオーディオ会議機能を搭載!</span><span class="sxs-lookup"><span data-stu-id="84cb4-105">Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="84cb4-106">人は、ビジネスまたはマイクロソフトのチームのアプリケーションをモバイル デバイスまたは PC 上で、Skype を使用する代わりに、電話を使用するビジネスまたはマイクロソフトのチームの会議、Skype を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="84cb4-106">People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="84cb4-107">のみ、スケジュールや会議を計画している人の電話会議を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84cb4-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="84cb4-108">ダイヤルイン会議の参加者、ライセンスを取得、またはその他の設定に割り当てられている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="84cb4-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="84cb4-109">オーディオ会議についてよく寄せられる質問は、[オーディオ会議のよく寄せられる質問](audio-conferencing-common-questions.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84cb4-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="84cb4-110">オーディオ会議は、国/地域で利用可能なかどうかを調べる手順 1。</span><span class="sxs-lookup"><span data-stu-id="84cb4-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="84cb4-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="84cb4-111"></span></span>


<span data-ttu-id="84cb4-112">[オーディオ会議や予定を呼び出すことで可用性を国や地域](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)に移動し、国または地域およびフリー ダイヤル電話システムでは、計画を呼び出すには、有料の電話に関する情報だけでなく、オーディオ会議、情報の可用性を取得するを選択数字、および通信のクレジットです。</span><span class="sxs-lookup"><span data-stu-id="84cb4-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="84cb4-113">手順 2: を取得し、ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="84cb4-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="84cb4-114">オーディオ会議では、ダイヤルイン会議の設定はユーザーごとにライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="84cb4-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="84cb4-115">オーディオ会議と、コストはどのくらいのために購入する必要がありますライセンスについては、 [Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84cb4-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
        
2. <span data-ttu-id="84cb4-116">オーディオ会議のライセンスを購入した後は、人、組織の会議やスケジュールを設定するのに割り当てるには、勤務時間内です。</span><span class="sxs-lookup"><span data-stu-id="84cb4-116">After you buy the Audio Conferencing licenses, you will ned to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="84cb4-117">[割り当てまたはビジネス向けの Office 365 のライセンスを削除](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)する、ユーザーが組織内で会議をスケジュールまたは潜在顧客を購入したを参照してください。</span><span class="sxs-lookup"><span data-stu-id="84cb4-117">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="84cb4-118">また (しないコストは何も) 通信のクレジットのライセンスを割り当てることをお勧め同じ人に前の手順でライセンスを割り当てられました。</span><span class="sxs-lookup"><span data-stu-id="84cb4-118">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="84cb4-119">通信のクレジットを設定する方法については、[組織の通信のクレジットの設定](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84cb4-119">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="84cb4-120">1 分あたりの支払電話会議を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="84cb4-120">You can also set up pay-per-minute Audio Conferencing.</span></span> <span data-ttu-id="84cb4-121">移動[ここで](../skype-for-business-and-microsoft-teams-add-on-licensing/audio-conferencing-pay-per-minute.md)それらを使用する方法の詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="84cb4-121">Go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/audio-conferencing-pay-per-minute.md) to find out more about how to use them.</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="84cb4-122">手順 3: 会議用ブリッジは、サービス番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="84cb4-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="84cb4-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="84cb4-123"></span></span>

<span data-ttu-id="84cb4-124">オーディオ会議では、ユーザーの電話番号を使うことはできません。サービス番号を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84cb4-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="84cb4-125">用、会議用ブリッジは、有料または無料のサービスの番号のいずれかを取得できます。</span><span class="sxs-lookup"><span data-stu-id="84cb4-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="84cb4-126">Get 有料電話番号とサービスのフリー ダイヤル番号に 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="84cb4-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="84cb4-127">**ビジネス管理センターは、Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="84cb4-127">**Use the Skype for Business admin center.**</span></span> <span data-ttu-id="84cb4-128">国や地域によっては、ビジネス管理センターは、Skype を使用して、会議用ブリッジのサービス番号を取得、[取得サービスの電話番号](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84cb4-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center, see [Getting service phone numbers](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span>
    
- <span data-ttu-id="84cb4-129">**既存のサービスの番号を移植します。**</span><span class="sxs-lookup"><span data-stu-id="84cb4-129">**Port your existing service numbers.**</span></span> <span data-ttu-id="84cb4-130">ポートまたは現在のサービス プロバイダーまたは電話のキャリアからの既存の番号を Office 365 に転送。</span><span class="sxs-lookup"><span data-stu-id="84cb4-130">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="84cb4-131">[Office 365 に電話番号を転送](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)または詳細については[、組織の電話番号の管理](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)作業を行いやすくことがわかります。</span><span class="sxs-lookup"><span data-stu-id="84cb4-131">You can see [Transfer phone numbers to Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) or [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="84cb4-132">**新しい番号の要求フォームを使用します。**</span><span class="sxs-lookup"><span data-stu-id="84cb4-132">**Use a request form for new numbers.**</span></span> <span data-ttu-id="84cb4-133">場合があります (国または地域) によってことはできませんビジネス管理センターでは、Skype を使用して、新しいサービスの番号を取得するか、特定の電話番号または市外局番が必要です。</span><span class="sxs-lookup"><span data-stu-id="84cb4-133">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="84cb4-134">その場合は、フォームをダウンロードして記入してからマイクロソフトに返送する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84cb4-134">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="84cb4-135">詳細については[、組織の電話番号の管理](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84cb4-135">See [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="84cb4-136">手順 4: 会議用ブリッジにサービス番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="84cb4-136">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="84cb4-137"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="84cb4-137"></span></span>

<span data-ttu-id="84cb4-138">会議用ブリッジは、有料または無料の電話番号を取得すると、番号を割り当てる、ミーティングの招待で使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="84cb4-138">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invites.</span></span>  

<span data-ttu-id="84cb4-139">オーディオ会議ブリッジには、新しい電話番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="84cb4-139">To assign a new phone number to your audio conferencing bridge:</span></span>

<span data-ttu-id="84cb4-140">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターに、Skype を使用する:**</span><span class="sxs-lookup"><span data-stu-id="84cb4-140">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 <span data-ttu-id="84cb4-141">**Office 365 管理センター**を参照して > **管理センター** > **ビジネス用の Skype** > **音声** > **の電話番号**、電話番号を選択し、**割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84cb4-141">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Voice** > **Phone numbers**, select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="84cb4-142">詳細については[、オーディオ会議ブリッジに新しい電話番号を割り当てる](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84cb4-142">For more details, see [Assign a new phone number to your audio conferencing bridge](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="84cb4-143">手順 5: 会議用ブリッジの第 2 言語と既定を設定します。</span><span class="sxs-lookup"><span data-stu-id="84cb4-143">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="84cb4-144"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="84cb4-144"></span></span>

<span data-ttu-id="84cb4-145">次に、[オーディオ会議の自動応答の言語設定](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)にダイヤルするときの電話番号に電話会議の呼び出し元を呼びかけられるように設定するのには、会議自動アテンダントを使用します。</span><span class="sxs-lookup"><span data-stu-id="84cb4-145">Next, you want to [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the conferencing auto attendant uses to greet a caller when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="84cb4-146">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **ビジネス管理センターは、マイクロソフトのチームと Skype を使用して:**</span><span class="sxs-lookup"><span data-stu-id="84cb4-146">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

<span data-ttu-id="84cb4-147">**会議**には、ダッシュ ボードから > **会議ブリッジ**、会議ブリッジの電話番号を選択**を編集**] をクリック、し、既定の言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="84cb4-147">From the Dashboard, go to **Meetings** > **Conference bridges**, select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

<span data-ttu-id="84cb4-148">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターに、Skype を使用する:**</span><span class="sxs-lookup"><span data-stu-id="84cb4-148">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

<span data-ttu-id="84cb4-149">**Office 365 管理センター**を参照して > **管理センター** > **ビジネス用の Skype** > **電話会議** > **ブリッジの設定をマイクロソフト**では、会議ブリッジの電話番号を選択し、**言語の設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84cb4-149">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** > **Microsoft bridge settings**,  select the conferencing bridge phone number, and then click **Set languages**.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="84cb4-150">ブリッジの設定、会議を設定する手順 6。</span><span class="sxs-lookup"><span data-stu-id="84cb4-150">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="84cb4-151"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="84cb4-151"></span></span>
    
<span data-ttu-id="84cb4-152">会議用ブリッジの設定後、開始/終了の通知、暗証番号 (pin) の長さなどの既定の設定が使用するものことを確認します正しくない場合は、変更することができます。</span><span class="sxs-lookup"><span data-stu-id="84cb4-152">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="84cb4-153">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **ビジネス管理センターは、マイクロソフトのチームと Skype を使用して:**</span><span class="sxs-lookup"><span data-stu-id="84cb4-153">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

<span data-ttu-id="84cb4-154">**会議**には、ダッシュ ボードから > **会議ブリッジ** > **ブリッジの設定**です。</span><span class="sxs-lookup"><span data-stu-id="84cb4-154">From the Dashboard, go to **Meetings** > **Conference bridges** > **Bridge settings**.</span></span> <span data-ttu-id="84cb4-155">**ブリッジの設定**ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="84cb4-155">This will open the **Bridge settings** pane.</span></span> <span data-ttu-id="84cb4-156">詳細については[、オーディオ会議ブリッジの設定を変更](../audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84cb4-156">For more details, see [Change the settings for an Audio Conferencing bridge](../audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

<span data-ttu-id="84cb4-157">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターに、Skype を使用する:**</span><span class="sxs-lookup"><span data-stu-id="84cb4-157">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

<span data-ttu-id="84cb4-158">**Office 365 管理センター**を参照して > **管理センター** > **ビジネス用の Skype** > **電話会議** > **Microsoft ブリッジの設定**です。</span><span class="sxs-lookup"><span data-stu-id="84cb4-158">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="84cb4-159">**Microsoft ブリッジの設定**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="84cb4-159">This will open the **Microsoft bridge settings** page.</span></span> <span data-ttu-id="84cb4-160">詳細については[、オーディオ会議ブリッジの設定を変更](../audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84cb4-160">For more details, see [Change the settings for an Audio Conferencing bridge](../audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="84cb4-161">会議をリードするユーザーの手順 7: 割り当てのダイヤルインの電話番号</span><span class="sxs-lookup"><span data-stu-id="84cb4-161">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="84cb4-162">オーディオ会議ブリッジを作成した後、ユーザーの通話およびフリー ダイヤル番号を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84cb4-162">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="84cb4-163">潜在顧客または会議をスケジュールする、組織内のユーザーのすべてのこの操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="84cb4-163">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> <span data-ttu-id="84cb4-164">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="84cb4-164">To do this:</span></span>

<span data-ttu-id="84cb4-165">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **ビジネス管理センターは、マイクロソフトのチームと Skype を使用して:**</span><span class="sxs-lookup"><span data-stu-id="84cb4-165">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

<span data-ttu-id="84cb4-166">ダッシュ ボードを**ユーザー**] をクリックして、リストからユーザーを選択、[**編集**] をクリックして、**オーディオ会議**を**編集**] をクリックして、**オーディオ会議**ウィンドウで、**有料電話番号**と**番号フリー ダイヤル**番号をリストします。</span><span class="sxs-lookup"><span data-stu-id="84cb4-166">From the Dashboard, click **Users**, select the user from the list, click **Edit**, click **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="84cb4-167">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターに、Skype を使用する:**</span><span class="sxs-lookup"><span data-stu-id="84cb4-167">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

<span data-ttu-id="84cb4-168">**Office 365 管理センター**を参照して > **ビジネス用の Skype** > **オーディオ会議** > **ユーザー**のリストからユーザーを選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84cb4-168">Go to the **Office 365 admin center** > **Skype for Business** > **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**.</span></span> <span data-ttu-id="84cb4-169">詳細については、必要な場合は、[オーディオ会議プロバイダーとしてのマイクロソフトの割り当て](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84cb4-169">If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="84cb4-170">手順 8: を設定するミーティングの招待状 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="84cb4-170">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="84cb4-171"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="84cb4-171"></span></span>
 
<span data-ttu-id="84cb4-172">ユーザーに設定されているダイヤルの番号は、会議の出席者に送信される会議出席依頼に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="84cb4-172">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="84cb4-173">ただし、する場合は、独自のヘルプおよび法律上のリンク、テキスト メッセージ、および小規模な会社のグラフィックを追加できます。</span><span class="sxs-lookup"><span data-stu-id="84cb4-173">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="84cb4-174">[ミーティングの招待状をカスタマイズする](../set-up-skype-for-business-online/customize-meeting-invitations.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84cb4-174">See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="84cb4-175">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="84cb4-175">Related topics</span></span>

[<span data-ttu-id="84cb4-176">電話会議に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="84cb4-176">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="84cb4-177">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="84cb4-177">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="84cb4-178">電話会議の電話番号</span><span class="sxs-lookup"><span data-stu-id="84cb4-178">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="84cb4-179">オンライン会議、電話会議のオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="84cb4-179">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
