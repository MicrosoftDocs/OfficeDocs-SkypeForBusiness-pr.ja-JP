---
title: 通話プランの設定
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 57893158-1acd-44ac-acaf-19f58264a9e0
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- LIL_Placement
description: 'Office 365 通話プラン (PSTN 通話プラン) でのライセンスの購入とセットアップの方法、電話番号を取得する方法、緊急連絡先と電話番号をユーザーに追加して割り当てる方法、ユーザーに新しい電話番号を通知する方法について説明します。 '
ms.openlocfilehash: 9f01c73c8374a367beb03db0a14df5dada0c562d
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494707"
---
# <a name="set-up-calling-plans"></a><span data-ttu-id="db51f-103">通話プランの設定</span><span class="sxs-lookup"><span data-stu-id="db51f-103">Set up Calling Plans</span></span>

<span data-ttu-id="db51f-104">他の Skype for Business のユーザーとの通話は無料です。ただし、ユーザーが社外のスマートフォンに電話をかけることができるようにする場合は、Office 365 で国内通話プランまたは国際通話プランを取得します。</span><span class="sxs-lookup"><span data-stu-id="db51f-104">Calls to other Skype for Business users are free, but if you want your users to be able to call any phone numbers outside of your business, get a Voice calling plans for Office 365 Enterprise E5. There are Office 365 Domestic and Office 365 International Calling Plans.</span></span> <span data-ttu-id="db51f-105">ビジネス用の設定は簡単です。</span><span class="sxs-lookup"><span data-stu-id="db51f-105">It's easy to set up the Skype for Business PSTN Calling service for your business.</span></span> 

## <a name="step-1-find-out-if-calling-plans-are-available-in-your-countryregion"></a><span data-ttu-id="db51f-106">手順 1: お客様の国/地域で通話プランが使用できるかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="db51f-106">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="db51f-107">[電話会議および通話プランが利用可能な国と地域](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) で、お住まいの国と地域を選択し、電話会議、通話プラン、電話システム、有料または無料電話番号、通信クレジットについての情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="db51f-107">Go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span>
  
## <a name="step-2-buy-and-assign-licenses"></a><span data-ttu-id="db51f-108">手順 2: ライセンスを購入して割り当てる</span><span class="sxs-lookup"><span data-stu-id="db51f-108">Step 1: Buy and assign licenses</span></span>
1. <span data-ttu-id="db51f-109">Office 365 の電話システムがプランに含まれていない場合は、**電話システム** のアドオン ライセンスを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db51f-109">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="db51f-110">**電話システム** ライセンスを取得したら、[Office 365の通話プラン](calling-plans-for-office-365.md) を購入します。</span><span class="sxs-lookup"><span data-stu-id="db51f-110">After you have **Phone System** licenses, purchase [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span> <span data-ttu-id="db51f-111">ライセンスとプランの購入については、[Microsoft Teams アドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db51f-111">See [Skype for Business add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md), and buy the licenses and plan.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="db51f-112">Office 365の **電話システム** ライセンスと通話プランは一緒になっているため、通話プラン購入のオプションを確認するには、最初に **電話システム** ライセンスを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db51f-112">**Phone System** licenses and Calling Plans in Office 365 go together, so to see the option to purchase Calling Plans, you must first have the **Phone System** licenses.</span></span>
  
2. <span data-ttu-id="db51f-113">まずライセンスを割り当て、組織内のユーザーに通話プランを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="db51f-113">First assign the licenses, and then assign a Calling Plan to the people in your organization.</span></span> <span data-ttu-id="db51f-114">[Assign Microsoft Teams ライセンスを割り当てる](assign-teams-licenses.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db51f-114">See [Assign Skype for Business and Microsoft Teams licenses](assign-teams-licenses.md).</span></span>
    
## <a name="step-3-get-phone-numbers"></a><span data-ttu-id="db51f-115">手順 3: 電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="db51f-115">Step 3: Get phone numbers for your users</span></span>
<span data-ttu-id="db51f-116">新しいユーザー番号を取得する方法には次の 3 通りあります。</span><span class="sxs-lookup"><span data-stu-id="db51f-116">There are three ways to get new user numbers:</span></span>

- <span data-ttu-id="db51f-117">**Skype for Business 管理センターを使用する。**</span><span class="sxs-lookup"><span data-stu-id="db51f-117">Open the **Skype for Business admin center**.</span></span> <span data-ttu-id="db51f-118">一部の国/地域では、Skype for Business 管理センターを使用してユーザーの電話番号を取得できます。詳細については [ユーザーの電話番号を取得する](/microsoftteams/getting-phone-numbers-for-your-users) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db51f-118">For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center, see [Getting service phone numbers](/microsoftteams/getting-phone-numbers-for-your-users).</span></span>
    
- <span data-ttu-id="db51f-119">**既存の番号を移行する。**</span><span class="sxs-lookup"><span data-stu-id="db51f-119">**Port your existing numbers.**</span></span> <span data-ttu-id="db51f-120">既存の番号を現在のサービス プロバイダーまたは電話会社から Office 365 に移行または転送します。</span><span class="sxs-lookup"><span data-stu-id="db51f-120">Port or transfer your existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="db51f-121">詳細については、[電話番号を Office 365 に移行する](transfer-phone-numbers-to-office-365.md) または [組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db51f-121">You can see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md) or [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="db51f-122">**新しい番号には申請書を使用します。**</span><span class="sxs-lookup"><span data-stu-id="db51f-122">**Use a request form for new numbers.**</span></span> <span data-ttu-id="db51f-123">国または地域によっては Skype for Business 管理センターを使用して新しい電話番号を取得することが出来ない場合があります。または、特定の電話番号またはエリアコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="db51f-123">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="db51f-124">その場合は、申請書をダウンロードして送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db51f-124">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="db51f-125">詳細については「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db51f-125">See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information.</span></span> 

## <a name="step-4-add-emergency-addresses-and-locations-for-your-organization"></a><span data-ttu-id="db51f-126">手順 4: 組織の緊急連絡先の住所と場所を追加する</span><span class="sxs-lookup"><span data-stu-id="db51f-126">Step 3: Add emergency addresses and locations for your organization</span></span>
<span data-ttu-id="db51f-127"><a name="bkmk_add_addresses"> </a> 緊急連絡先の住所は電話番号に関連付けられている必要があります。この関連付けが行われるかどうかは国と地域によって異なります。</span><span class="sxs-lookup"><span data-stu-id="db51f-127"><a name="bkmk_add_addresses"> </a>An emergency address must be associated with a phone number - but when this happens can vary between country/regions.</span></span> <span data-ttu-id="db51f-128">例えば米国では、電話番号をユーザーに割り当てるときに、緊急対応の住所を関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="db51f-128">For example, in the United States, you need to associate an emergency address when you assign the phone number to the user.</span></span> <span data-ttu-id="db51f-129">英国では、Office 365 から電話番号を取得するか、現在のサービス プロバイダーから電話番号を移すときに、緊急対応の住所をその電話番号に関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="db51f-129">In the United Kingdom, you need to associate an emergency address to the phone number when you are getting the phone numbers from Office 365 or transferring phone numbers from your current service provider.</span></span> 

<span data-ttu-id="db51f-130">**組織の緊急連絡先の住所を追加する**</span><span class="sxs-lookup"><span data-stu-id="db51f-130">**To add an emergency address for your organization**</span></span>

<span data-ttu-id="db51f-131">**Skype for Business 管理センターを使って** ![Skype for Business のロゴを表示したアイコン](media/sfb-logo-30x30.png)</span><span class="sxs-lookup"><span data-stu-id="db51f-131">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="db51f-132">Skype for Business 管理センターで、 **[音声]** > **[緊急連絡先]** > **[新しいアドレスの追加]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="db51f-132">In the Skype for Business admin center, go to  **Voice** > **Emergency locations** > **Add new address**.</span></span> <span data-ttu-id="db51f-133">詳細については [組織の緊急連絡先の住所を追加、削除する](/skypefor business/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="db51f-133">See,[Add or remove an emergency address for your organization](/skypefor business/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization).</span></span>

<span data-ttu-id="db51f-134">**組織の緊急連絡先の場所を追加する**</span><span class="sxs-lookup"><span data-stu-id="db51f-134">**To add an emergency location for your organization**</span></span> 

<span data-ttu-id="db51f-135">**Skype for Business 管理センターを使って** ![Skype for Business のロゴを表示したアイコン](media/sfb-logo-30x30.png)</span><span class="sxs-lookup"><span data-stu-id="db51f-135">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="db51f-136">Skype for Business 管理センターで、 **[Voice]** > **緊急連絡先** > **[新しいアドレスの追加]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="db51f-136">In the Skype for Business admin center, go to **Voice** > **Emergency locations** > **Add new address**.</span></span> <span data-ttu-id="db51f-137">詳細については [組織の緊急対応の場所を追加、変更、削除する](/skypefor business/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="db51f-137">[Add, change, or remove an emergency location for your organization](/skypefor business/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization)</span></span>

    
## <a name="step-5-assign-an-emergency-address-and-a-phone-number-to-a-user"></a><span data-ttu-id="db51f-138">手順 5: ユーザーに緊急連絡先の住所と電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="db51f-138">Step 5: Assign an emergency address and a phone number to a user</span></span>
<span data-ttu-id="db51f-139"><a name="bkmk_add_addresses"> </a> Office 365 の通話プランを設定する場合は、各ユーザーに電話番号と緊急連絡先を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="db51f-139"><a name="bkmk_add_addresses"> </a>When you set up Calling Plans in Office 365, you will need to assign a phone number and emergency address to each of your users.</span></span> <span data-ttu-id="db51f-140">電話番号に関連付けるには、先に緊急連絡先の住所を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db51f-140">The emergency address must be created before you can associate it with a phone number.</span></span> 

<span data-ttu-id="db51f-141">**ユーザーの緊急連絡先の住所を追加する方法**</span><span class="sxs-lookup"><span data-stu-id="db51f-141">**To add an emergency address for a user**</span></span> 

<span data-ttu-id="db51f-142">**Skype for Business 管理センターを使って** ![Skype for Business のロゴを表示したアイコン](media/sfb-logo-30x30.png)</span><span class="sxs-lookup"><span data-stu-id="db51f-142">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="db51f-143">Skype for Business 管理センターで、**[音声]** > **[音声ユーザー]** > **[緊急連絡先の場所]** > **[番号の割当て]** > **[場所の変更]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="db51f-143">In the Skype for Business admin center, go to **Voice** > **Voice users** > **Emergency location** > **Assign number** > **Change location**.</span></span> <span data-ttu-id="db51f-144">詳細については [ユーザーの緊急連絡先の住所の割り当てまたは変更](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="db51f-144">See [Assign or change an emergency address for a user](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user).</span></span>

   > [!NOTE]
   > <span data-ttu-id="db51f-145">電話番号を割り当てるときに、緊急連絡先の住所を割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="db51f-145">You can also assign an emergency address when you assign a phone number.</span></span>

<span data-ttu-id="db51f-146">**ユーザーに電話番号を割り当てる方法**</span><span class="sxs-lookup"><span data-stu-id="db51f-146">**Assign a phone number to a user.**</span></span>

<span data-ttu-id="db51f-147">**Skype for Business 管理センターを使って** ![Skype for Business のロゴを表示したアイコン](media/sfb-logo-30x30.png)</span><span class="sxs-lookup"><span data-stu-id="db51f-147">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="db51f-148">Skype for Business 管理センターで、**[音声]** > **[音声ユーザー]** > **[番号の割当て]** > **[場所の変更]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="db51f-148">In the Skype for Business admin center, go to **Voice** > **Voice users** > **Assign number** > **Change location**.</span></span> <span data-ttu-id="db51f-149">詳細については [ユーザーの電話番号を割り当て、変更、または削除する](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="db51f-149">See [Assign, change, or remove a phone number for a user](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user).</span></span>

## <a name="step-6-tell-your-users-about-their-new-phone-numbers"></a><span data-ttu-id="db51f-150">手順 6: 新しい電話番号をユーザーに通知する</span><span class="sxs-lookup"><span data-stu-id="db51f-150">Step 5: Tell your users about their new phone numbers</span></span>
<span data-ttu-id="db51f-151"><a name="bkmk_add_addresses"> </a></span><span class="sxs-lookup"><span data-stu-id="db51f-151"></span></span>

<span data-ttu-id="db51f-152">メールを送信するか、会社の適切な連絡方法を使用して、ユーザーに新しい電話番号を伝えることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="db51f-152">We recommend sending mail or using your business's preferred communication method to tell the people about their new phone numbers.</span></span> 

<span data-ttu-id="db51f-153">次に、ユーザーの **Skype for Business** アプリに電話番号がどのように表示されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="db51f-153">Here's how they can see that phone number in their **Skype for Business** app:</span></span>
  
1. <span data-ttu-id="db51f-154">デスクトップで Skype for Business にサインインします。</span><span class="sxs-lookup"><span data-stu-id="db51f-154">Sign in to Skype for Business on your desktop.</span></span>
    
2. <span data-ttu-id="db51f-155"> **Settings** > **Tools** > **Options** を選択します。</span><span class="sxs-lookup"><span data-stu-id="db51f-155">Choose **Settings** > **Tools** > **Options**.</span></span> 
    
     ![[ツール] メニューの [オプション] のスクリーンショット](media/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. <span data-ttu-id="db51f-157">[**電話**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="db51f-157">Then choose **Phones**.</span></span> 
    
    ![スマートフォンのオプションを選択するスクリーンショット](media/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
<span data-ttu-id="db51f-p113">**Microsoft Teams** では、ユーザーは左側のナビゲーションで [**通話**] をクリックすると、自分の電話番号を表示できます。電話番号はダイヤル パッドの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="db51f-p113">In **Microsoft Teams**, users can see their phone number by clicking **Calls** in the left navigation. The phone number is shown above the dial pad.</span></span>

![左側のナビゲーションの [通話] を選択するスクリーンショット。](media/teams-phone-number.png)

## <a name="what-else-do-you-need-to-know"></a><span data-ttu-id="db51f-162">その他の情報</span><span class="sxs-lookup"><span data-stu-id="db51f-162">What else do you need to know?</span></span>
<span data-ttu-id="db51f-163"><a name="bkmk_add_addresses"> </a></span><span class="sxs-lookup"><span data-stu-id="db51f-163"></span></span>

- <span data-ttu-id="db51f-p114">緊急対応の住所は、行政上の住所、所在地住所、または現住所と呼ばれることがあります。緊急対応の住所は、組織の事業所の場所を示す所在地住所または行政上の住所のことです。</span><span class="sxs-lookup"><span data-stu-id="db51f-p114">An emergency address is often referred to as a civic address, street address, or a physical address. It is the street or civic address of a place of business for your organization.</span></span>
    
- <span data-ttu-id="db51f-166">緊急対応の場所は検証されません。緊急対応の住所だけが検証されます。</span><span class="sxs-lookup"><span data-stu-id="db51f-166">Emergency locations aren't validated, only emergency addresses are.</span></span>
    
- <span data-ttu-id="db51f-167">緊急対応の住所の詳細については、「[緊急対応の場所、アドレス、通話ルーティングの概要](what-are-emergency-locations-addresses-and-call-routing.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="db51f-167">If you want to know more about emergency addresses, see [What are emergency locations, addresses and call routing?](what-are-emergency-locations-addresses-and-call-routing.md)</span></span>
    
## <a name="do-you-want-to-automate-assigning-phone-numbers"></a><span data-ttu-id="db51f-168">電話番号の割り当てを自動化したい場合</span><span class="sxs-lookup"><span data-stu-id="db51f-168">Do you want to automate assigning phone numbers?</span></span>
<span data-ttu-id="db51f-169"><a name="bkmk_add_addresses"> </a></span><span class="sxs-lookup"><span data-stu-id="db51f-169"></span></span>

<span data-ttu-id="db51f-170">Windows PowerShell を使うことができる場合は、次のコマンドレットを使用して、ユーザーへの電話番号の割り当てを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="db51f-170">If you know Windows PowerShell, you can use the following cmdlets to automate assigning phone numbers to your users.</span></span> 
  
- <span data-ttu-id="db51f-171">[Get-CsOnlineTelephoneNumber](https://technet.microsoft.com/library/mt243818.aspx): Business Voice Directory から電話番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="db51f-171">[Get-CsOnlineTelephoneNumber](https://technet.microsoft.com/library/mt243818.aspx): Retrieves the telephone numbers from the Business Voice Directory.</span></span>
    
- <span data-ttu-id="db51f-172">[Set-CsOnlineVoiceUser](https://technet.microsoft.com/library/mt243817.aspx): 電話番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="db51f-172">[Set-CsOnlineVoiceUser](https://technet.microsoft.com/library/mt243817.aspx): Sets the telephone numbers.</span></span>
    
<span data-ttu-id="db51f-173">詳しくは、「[クイック リファレンス: Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://technet.microsoft.com/library/dn362776%28v=ocs.15%29.aspx)」ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="db51f-173">To learn more, see [Quick reference: Using Windows PowerShell to do common Skype for Business Online management tasks](https://technet.microsoft.com/library/dn362776%28v=ocs.15%29.aspx).</span></span>
  
   > [!NOTE]
   > <span data-ttu-id="db51f-174">さらに多くの電話番号を取得する必要がある場合は、 [ビジネス製品に関するサポート (管理者向けヘルプ) に問い合わせる](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="db51f-174">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>


## <a name="related-topics"></a><span data-ttu-id="db51f-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="db51f-175">Related topics</span></span>
[<span data-ttu-id="db51f-176">電話番号の移行に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="db51f-176">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="db51f-177">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="db51f-177">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="db51f-178">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="db51f-178">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="db51f-179">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="db51f-179">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

<span data-ttu-id="db51f-180">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="db51f-180">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 