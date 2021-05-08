---
title: Microsoft Teams の電話会議を設定する
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
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '電話を使用して電話会議に参加する必要がある社内ユーザーのダイヤルイン会議または電話会議をセットアップする方法について説明します。 '
ms.openlocfilehash: ba022bd8af5a8b1eb2e445e6034b4d318dec72b5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117145"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a><span data-ttu-id="b2658-103">Microsoft Teams の電話会議を設定する</span><span class="sxs-lookup"><span data-stu-id="b2658-103">Set up Audio Conferencing for Microsoft Teams</span></span>

<span data-ttu-id="b2658-104">組織内のユーザーが、会議にダイヤル インするために電話機を使用する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="b2658-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="b2658-105">Microsoft Teams には、こういった状況に最適な、電話会議機能があります。</span><span class="sxs-lookup"><span data-stu-id="b2658-105">Microsoft Teams includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="b2658-106">ユーザーは、モバイル デバイスまたは PC 上で Microsoft Teams のアプリを使用する代わりに、電話機を使用して Teams 会議にダイヤル インすることができます。</span><span class="sxs-lookup"><span data-stu-id="b2658-106">People can call in to Teams meetings using a phone, instead of using the Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="b2658-p102">電話会議の設定は、会議のスケジュールを設定または会議を進行するユーザーに対してのみ必要です。ダイヤルインで参加するユーザーについては、ライセンスの割り当てや他の設定は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b2658-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="b2658-109">電話会議についてよく寄せられる質問については、 [電話会議についてよくある質問](audio-conferencing-common-questions.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2658-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="b2658-110">手順 1: 自分の国/地域で電話会議が使用可能かどうか確認する</span><span class="sxs-lookup"><span data-stu-id="b2658-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="b2658-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="b2658-111"><a name="__top"> </a></span></span>

<span data-ttu-id="b2658-112">「[国・地域別の電話会議と通話プランの利用可能状況](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)」を開き、ご自分の国または地域を選択して、電話会議についての情報に加えて、電話システム、通話プラン、有料・無料通話番号、コミュニケーション クレジットについての情報も取得してください。</span><span class="sxs-lookup"><span data-stu-id="b2658-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="b2658-113">手順 2: ライセンスを取得して割り当てる</span><span class="sxs-lookup"><span data-stu-id="b2658-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="b2658-114">電話会議では、ダイヤルイン会議をセットアップするユーザーごとにライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="b2658-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="b2658-115">電話会議のために購入する必要のあるライセンスの種類と必要コストについては、「[Microsoft Teams のアドオン ライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2658-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="b2658-116">電話会議は Office 365 Enterprise E5 ライセンスにアドオンとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="b2658-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="b2658-117">電話会議ライセンスを購入した後は、それらのライセンスを、会議を計画または開催しようとしている組織内のユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2658-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="b2658-118">「[Microsoft 365 または一般法人向け Office 365 のユーザーにライセンスを割り当てる](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」を参照して、会議をスケジュールまたは主催することになる組織内のユーザーのために購入したライセンス割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b2658-118">See [Assign licenses to users in Microsoft 365 or Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="b2658-119">また、前の手順でライセンスを割り当てた同じユーザーに、コミュニケーション クレジット ライセンス (費用はかかりません) を割り当てることをおすすめします。</span><span class="sxs-lookup"><span data-stu-id="b2658-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="b2658-120">コミュニケーション クレジットのセットアップ方法については、「[組織向けにコミュニケーション クレジットをセットアップする](set-up-communications-credits-for-your-organization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2658-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="b2658-121">[分毎課金の電話会議](audio-conferencing-pay-per-minute.md)をセットアップすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b2658-121">You can also set up [pay-per-minute Audio Conferencing](audio-conferencing-pay-per-minute.md).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="b2658-122">手順 3: 会議ブリッジのサービス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="b2658-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="b2658-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="b2658-123"><a name="__top"> </a></span></span>

<span data-ttu-id="b2658-124">電話会議では、ユーザーの電話番号を使うことはできません。サービス番号を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2658-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="b2658-125">会議ブリッジ用に、有料または無料のサービス番号のいずれかを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="b2658-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="b2658-126">有料サービス番号と無料サービス番号を取得する方法は 3 通りあります。</span><span class="sxs-lookup"><span data-stu-id="b2658-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="b2658-127">**Microsoft Teams 管理センターを使用** する。</span><span class="sxs-lookup"><span data-stu-id="b2658-127">**Use the Microsoft Teams admin center**.</span></span> <span data-ttu-id="b2658-128">いくつかの国/地域では、Microsoft Teams 管理センターを使用して、会議ブリッジ用にサービス番号を取得できます。</span><span class="sxs-lookup"><span data-stu-id="b2658-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Microsoft Teams admin center.</span></span> <span data-ttu-id="b2658-129">「[サービス電話番号の取得](./getting-service-phone-numbers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2658-129">See [Getting service phone numbers](./getting-service-phone-numbers.md).</span></span>
    
- <span data-ttu-id="b2658-130">**既存のサービス番号を移行する**。</span><span class="sxs-lookup"><span data-stu-id="b2658-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="b2658-131">既存の番号を現在のサービス プロバイダーまたは電話会社から Microsoft 365 または Office 365 に移行または転送します。</span><span class="sxs-lookup"><span data-stu-id="b2658-131">To port or transfer existing numbers from your current service provider or phone carrier to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="b2658-132">この方法の詳細については、「[Teams に電話番号を移行する](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)」または「[組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2658-132">You can see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="b2658-133">**申請書を使用して新しい番号を求める**。</span><span class="sxs-lookup"><span data-stu-id="b2658-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="b2658-134">国または地域によっては Microsoft Teams 管理センターを使用して新しい電話番号を取得することができない場合があります。あるいは、特定の電話番号またはエリアコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="b2658-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Microsoft Teams admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="b2658-135">その場合は、申請書をダウンロードして送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2658-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="b2658-136">詳細については「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2658-136">See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="b2658-137">手順 4: 会議ブリッジにサービス番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="b2658-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="b2658-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="b2658-138"><a name="__top"> </a></span></span>

<span data-ttu-id="b2658-139">会議ブリッジ用に有料電話番号と無料電話番号のいずれかまたは両方を取得したら、それらの番号を割り当てて、会議の招集に使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2658-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="b2658-140">電話会議ブリッジに新規の電話番号を割り当てるには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b2658-140">Follow these steps to assign a new phone number to your audio conferencing bridge.</span></span>

<span data-ttu-id="b2658-141">![Skype for Business のロゴを表示したアイコン](media/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="b2658-141">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="b2658-142">**[Microsoft 365 管理センター]** > **[管理センター]** > **[Teams]** > **[従来のポータル]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="b2658-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="b2658-143">**[音声]**  >  **[電話番号]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b2658-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="b2658-144">電話番号を選択し、**[割り当て]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2658-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="b2658-145">詳細については、「[電話会議ブリッジの電話番号を変更する](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2658-145">For more details, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="b2658-146">手順 5: 会議ブリッジの既定の言語と代替言語を設定する</span><span class="sxs-lookup"><span data-stu-id="b2658-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="b2658-147"><a name="__top"> </a> 次に、電話会議の電話番号にダイヤルインした時に、呼び出しをしたユーザーに挨拶するために会議の自動応答で使用する、[Microsoft Teams の電話会議の自動応答の言語を設定](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)します。</span><span class="sxs-lookup"><span data-stu-id="b2658-147"><a name="__top"> </a> Next, you want to [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="b2658-148">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**:</span><span class="sxs-lookup"><span data-stu-id="b2658-148">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="b2658-149">ダッシュボードから **[会議]** > **[会議ブリッジ]** の順に開きます。</span><span class="sxs-lookup"><span data-stu-id="b2658-149">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="b2658-150">会議ブリッジ電話番号を選択して **[編集]** をクリックし、既定の言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="b2658-150">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="b2658-151">手順 6: 会議ブリッジを設定する</span><span class="sxs-lookup"><span data-stu-id="b2658-151">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="b2658-152"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="b2658-152"><a name="__top"> </a></span></span>
    
<span data-ttu-id="b2658-153">会議ブリッジをセットアップした後、使用する開始/終了の通知と PIN の長さが正しいかなど、既定の設定を確認します。正しくない場合は、変更することができます。</span><span class="sxs-lookup"><span data-stu-id="b2658-153">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="b2658-154">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**:</span><span class="sxs-lookup"><span data-stu-id="b2658-154">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="b2658-155">ダッシュボードから **[会議]** > **[会議ブリッジ]** の順に開きます。</span><span class="sxs-lookup"><span data-stu-id="b2658-155">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="b2658-156">**[ブリッジの設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b2658-156">Select **Bridge settings**.</span></span> <span data-ttu-id="b2658-157">[**ブリッジの設定**] ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="b2658-157">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="b2658-158">詳細については、[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2658-158">For more details, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="b2658-159">手順 7: 会議を開催するユーザー向けにダイヤルインの電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="b2658-159">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="b2658-160">電話会議ブリッジを作成した後、ユーザー向けに有料番号と無料番号を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2658-160">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="b2658-161">この操作を、会議を主催したり計画している組織内のすべてのユーザーに対して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2658-161">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="b2658-162">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**:</span><span class="sxs-lookup"><span data-stu-id="b2658-162">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="b2658-163">ダッシュボードから **[ユーザー]** をクリックし、リストからユーザーを選択して **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b2658-163">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="b2658-164">**[電話会議]** の次にある **[編集]** をクリックしてから **[電話会議]** ウィンドウで **[有料番号]** と **[無料番号]** の番号リストから、番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="b2658-164">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="b2658-165">さらに詳細が必要な場合は、「[Microsoft を電話会議プロバイダーとして割り当てる](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2658-165">If you need more details, see [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="b2658-166">手順 8: 会議の招集をセットアップする（オプション）</span><span class="sxs-lookup"><span data-stu-id="b2658-166">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="b2658-167"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="b2658-167"><a name="__top"> </a></span></span>
 
<span data-ttu-id="b2658-168">ユーザー向けに設定されているダイヤルイン番号は、会議の出席者に送信される会議招集に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="b2658-168">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="b2658-169">ただし、必要に応じて、独自のヘルプや法律のリンク、テキスト メッセージ、小さな会社のグラフィックを追加できます。</span><span class="sxs-lookup"><span data-stu-id="b2658-169">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="b2658-170">「[会議への招待状をカスタマイズする](meeting-settings-in-teams.md#customize-meeting-invitations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2658-170">See [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="b2658-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2658-171">Related topics</span></span>

[<span data-ttu-id="b2658-172">電話会議に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="b2658-172">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="b2658-173">Microsoft Teams での電話会議の電話番号</span><span class="sxs-lookup"><span data-stu-id="b2658-173">Phone numbers for Audio Conferencing in Microsoft Teams</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
  
[<span data-ttu-id="b2658-174">オンライン会議、電話会議のオプションを設定</span><span class="sxs-lookup"><span data-stu-id="b2658-174">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)