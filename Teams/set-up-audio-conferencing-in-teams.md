---
title: マイクロソフト チームの電話会議を設定します
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '電話会議に参加するのには、電話を使用する必要があるビジネス人のダイヤルインまたはオーディオ会議を設定する方法について説明します。 '
ms.openlocfilehash: 7ff24dd2b29eabbad46759471b69c3619e4e7b24
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204881"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a><span data-ttu-id="a64c7-103">マイクロソフト チームの電話会議を設定します</span><span class="sxs-lookup"><span data-stu-id="a64c7-103">Set up Audio Conferencing for Microsoft Teams</span></span>

<span data-ttu-id="a64c7-104">自分の組織内のユーザーが、会議にダイヤル インするために電話機を使用する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a64c7-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="a64c7-105">マイクロソフトのチームには、これだけの音声会議機能が含まれています!</span><span class="sxs-lookup"><span data-stu-id="a64c7-105">Microsoft Teams includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="a64c7-106">人は、チームのアプリケーションを使用して、モバイル デバイスまたは PC 上ではなく、電話を使用してチームのミーティング呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a64c7-106">People can call in to Teams meetings using a phone, instead of using the Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="a64c7-107">電話会議のセットアップは、ミーティングのスケジュールを設定するユーザーまたはミーティングを主催するユーザーにのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="a64c7-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="a64c7-108">ダイヤルインする会議参加者には、割り当てられたライセンスやその他のセットアップは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a64c7-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="a64c7-109">電話会議についてよく寄せられる質問については、「[電話会議についてよくある質問](audio-conferencing-common-questions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a64c7-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="a64c7-110">手順 1: 自分の国/地域で電話会議が使用可能かどうか確認する</span><span class="sxs-lookup"><span data-stu-id="a64c7-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="a64c7-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="a64c7-111"></span></span>

<span data-ttu-id="a64c7-112">「[国・地域別の電話会議と通話プランの利用可能状況](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)」を開き、ご自分の国または地域を選択して、電話会議についての情報に加えて、電話システム、通話プラン、有料・無料通話番号、コミュニケーション クレジットについての情報も取得してください。</span><span class="sxs-lookup"><span data-stu-id="a64c7-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="a64c7-113">手順 2: ライセンスを取得して割り当てる</span><span class="sxs-lookup"><span data-stu-id="a64c7-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="a64c7-114">電話会議では、ダイヤルイン会議をセットアップするユーザーごとにライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="a64c7-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="a64c7-115">オーディオ会議と、コストはどのくらいのために購入する必要がありますライセンスについては、[マイクロソフトのチームのアドオンのライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a64c7-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="a64c7-116">オーディオ会議は、アドオンと Office 365 エンタープライズ E5 のライセンスには含まれています。</span><span class="sxs-lookup"><span data-stu-id="a64c7-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="a64c7-117">オーディオ会議のライセンスを購入した後は、人、組織の会議やスケジュールを設定するのに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a64c7-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="a64c7-118">[ビジネス向けの Office 365 のユーザーにライセンスを割り当てる](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)に、ユーザーが組織内で会議をスケジュールまたは潜在顧客を購入するを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a64c7-118">See [Assign licenses to users in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="a64c7-119">また、前の手順でライセンスを割り当てた同じユーザーに、コミュニケーション クレジット ライセンス (費用はかかりません) を割り当てることをおすすめします。</span><span class="sxs-lookup"><span data-stu-id="a64c7-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="a64c7-120">コミュニケーション クレジットのセットアップ方法については、「[組織向けにコミュニケーション クレジットをセットアップする](set-up-communications-credits-for-your-organization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a64c7-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="a64c7-121">[1 分あたりの支払電話会議](audio-conferencing-pay-per-minute.md)を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a64c7-121">You can also set up [pay-per-minute Audio Conferencing](audio-conferencing-pay-per-minute.md).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="a64c7-122">手順 3: 会議ブリッジのサービス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="a64c7-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="a64c7-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="a64c7-123"></span></span>

<span data-ttu-id="a64c7-124">電話会議では、ユーザーの電話番号を使うことはできません。サービス番号を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a64c7-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="a64c7-125">会議ブリッジ用に、有料または無料のサービス番号のいずれかを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="a64c7-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="a64c7-126">有料サービス番号と無料サービス番号を取得する方法は 3 通りあります。</span><span class="sxs-lookup"><span data-stu-id="a64c7-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="a64c7-127">**マイクロソフトのチーム管理センターを使用**します。</span><span class="sxs-lookup"><span data-stu-id="a64c7-127">**Use the Microsoft Teams admin center**.</span></span> <span data-ttu-id="a64c7-128">一部の国/地域のマイクロソフトのチーム管理センターを使用して、会議用ブリッジのサービス番号を取得できます。</span><span class="sxs-lookup"><span data-stu-id="a64c7-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Microsoft Teams admin center.</span></span> <span data-ttu-id="a64c7-129">[取得サービスの電話番号](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a64c7-129">See [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span>
    
- <span data-ttu-id="a64c7-130">**ポートは、既存のサービスの番号**です。</span><span class="sxs-lookup"><span data-stu-id="a64c7-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="a64c7-131">ポートまたは現在のサービス プロバイダーまたは電話のキャリアからの既存の番号を Office 365 に転送。</span><span class="sxs-lookup"><span data-stu-id="a64c7-131">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="a64c7-132">この方法の詳細については、「[Office 365 に電話番号を移行](transfer-phone-numbers-to-office-365.md)」または「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a64c7-132">You can see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md) or [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="a64c7-133">**新しい番号の要求フォームを使用**します。</span><span class="sxs-lookup"><span data-stu-id="a64c7-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="a64c7-134">場合があります (国または地域) によってことはできません、マイクロソフトのチーム管理センターを使用して、新しいサービスの番号を取得するか、特定の電話番号または市外局番が必要です。</span><span class="sxs-lookup"><span data-stu-id="a64c7-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Microsoft Teams admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="a64c7-135">その場合は、フォームをダウンロードして記入してからマイクロソフトに返送する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a64c7-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="a64c7-136">詳細については「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a64c7-136">See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="a64c7-137">手順 4: 会議ブリッジにサービス番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="a64c7-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="a64c7-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="a64c7-138"></span></span>

<span data-ttu-id="a64c7-139">会議用ブリッジは、有料または無料の電話番号を取得するとは、会議出席依頼に使用できるように番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a64c7-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="a64c7-140">オーディオ会議ブリッジは、新しい電話番号を割り当てるにはこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a64c7-140">Follow these steps to assign a new phone number to your audio conferencing bridge.</span></span>

<span data-ttu-id="a64c7-141">![デバイスのロゴ-30x30.png](media/sfb-logo-30x30.png) **ビジネス管理センターに、Skype を使用する:**</span><span class="sxs-lookup"><span data-stu-id="a64c7-141">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="a64c7-142">**Microsoft 365 管理センター**を参照して > **管理センター** > **チーム** > **従来のポータル**です。</span><span class="sxs-lookup"><span data-stu-id="a64c7-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="a64c7-143">**音声**を選択して > **の電話番号**です。</span><span class="sxs-lookup"><span data-stu-id="a64c7-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="a64c7-144">電話番号を選択し、[**割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a64c7-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="a64c7-145">詳細については、[変更オーディオ会議ブリッジの電話番号](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a64c7-145">For more details, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="a64c7-146">手順 5: 会議ブリッジ用の既定言語と第 2 言語を設定する</span><span class="sxs-lookup"><span data-stu-id="a64c7-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="a64c7-147"><a name="__top"></a> [自動アテンダントの言語のマイクロソフトのチームでのオーディオ会議を設定](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)するにダイヤルするときの電話番号に電話会議の呼び出し元を呼びかけられるように設定するのには、会議自動アテンダントを使用する次に、します。</span><span class="sxs-lookup"><span data-stu-id="a64c7-147"><a name="__top"> </a> Next, you want to [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="a64c7-148">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **マイクロソフト チームの管理センターを使用**します。</span><span class="sxs-lookup"><span data-stu-id="a64c7-148">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="a64c7-149">**会議**には、ダッシュ ボードから > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="a64c7-149">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="a64c7-150">会議ブリッジの電話番号を選択して**編集**を、既定の言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="a64c7-150">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="a64c7-151">手順 6: 会議ブリッジを設定する</span><span class="sxs-lookup"><span data-stu-id="a64c7-151">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="a64c7-152"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="a64c7-152"></span></span>
    
<span data-ttu-id="a64c7-153">会議ブリッジをセットアップした後、使用する開始/終了の通知と PIN の長さが正しいかなど、既定の設定を確認します。正しくない場合は、変更することができます。</span><span class="sxs-lookup"><span data-stu-id="a64c7-153">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="a64c7-154">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **マイクロソフト チームの管理センターを使用**します。</span><span class="sxs-lookup"><span data-stu-id="a64c7-154">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="a64c7-155">**会議**には、ダッシュ ボードから > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="a64c7-155">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="a64c7-156">**ブリッジの設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a64c7-156">Select **Bridge settings**.</span></span> <span data-ttu-id="a64c7-157">[**ブリッジの設定**] ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="a64c7-157">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="a64c7-158">詳細については、[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a64c7-158">For more details, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="a64c7-159">手順 7: 会議を開催するユーザー向けにダイヤルインの電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="a64c7-159">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="a64c7-160">電話会議ブリッジを作成した後、ユーザー向けに有料番号と無料番号を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a64c7-160">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="a64c7-161">この操作を、会議を主催したり計画している組織内のすべてのユーザーに対して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a64c7-161">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="a64c7-162">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **マイクロソフト チームの管理センターを使用**します。</span><span class="sxs-lookup"><span data-stu-id="a64c7-162">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="a64c7-163">ダッシュ ボードで、[**ユーザー**] をクリックし、ボックスの一覧からユーザーを選択して**編集**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a64c7-163">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="a64c7-164">**オーディオ会議**の横の**編集**を選択して、**オーディオ会議**ウィンドウで、**有料電話番号**や**フリー ダイヤル**番号のリスト内の数値。</span><span class="sxs-lookup"><span data-stu-id="a64c7-164">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="a64c7-165">さらに詳細が必要な場合は、「[Microsoft を電話会議プロバイダーとして割り当てる](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a64c7-165">If you need more details, see [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="a64c7-166">手順 8: 会議の招集をセットアップする（オプション）</span><span class="sxs-lookup"><span data-stu-id="a64c7-166">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="a64c7-167"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="a64c7-167"></span></span>
 
<span data-ttu-id="a64c7-168">ユーザー向けに設定されているダイヤルイン番号は、会議の出席者に送信される会議招集に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="a64c7-168">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="a64c7-169">ただし、必要に応じて、独自のヘルプや法律のリンク、テキスト メッセージ、小さな会社のグラフィックを追加できます。</span><span class="sxs-lookup"><span data-stu-id="a64c7-169">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="a64c7-170">[ミーティングの招待状をカスタマイズする](customize-meeting-invitations.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a64c7-170">See [Customize meeting invitations](customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="a64c7-171">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a64c7-171">Related topics</span></span>

[<span data-ttu-id="a64c7-172">電話会議に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="a64c7-172">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="a64c7-173">Microsoft Teams での電話会議の電話番号</span><span class="sxs-lookup"><span data-stu-id="a64c7-173">Phone numbers for Audio Conferencing in Microsoft Teams</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
  
[<span data-ttu-id="a64c7-174">オンライン会議、電話会議のオプションを設定</span><span class="sxs-lookup"><span data-stu-id="a64c7-174">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
