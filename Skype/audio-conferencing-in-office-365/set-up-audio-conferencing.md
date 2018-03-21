---
title: "Skype for Business および Microsoft Teams の電話会議のセットアップ"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
- LIL_Placement
description: "電話を使用して会議に参加する必要のあるビジネスで、ユーザーのダイヤルインまたはオーディオ会議を設定する方法について説明します。 "
ms.openlocfilehash: fd427abf14d3d705bc9f846f32a27d9be62967e8
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a><span data-ttu-id="5adc0-103">Skype for Business および Microsoft Teams の電話会議のセットアップ</span><span class="sxs-lookup"><span data-stu-id="5adc0-103">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>

<span data-ttu-id="5adc0-104">自分の組織内のユーザーが、会議にダイヤル インするために電話機を使用する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="5adc0-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="5adc0-105">Skype ビジネスおよびマイクロソフトのチームには、これだけのオーディオ会議機能を搭載!</span><span class="sxs-lookup"><span data-stu-id="5adc0-105">Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="5adc0-106">人は、ビジネスまたはマイクロソフトのチームのアプリケーションをモバイル デバイスまたは PC 上で、Skype を使用する代わりに、電話を使用するビジネスまたはマイクロソフトのチームの会議、Skype を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="5adc0-106">People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="5adc0-107">のみ、スケジュールや会議を計画している人の電話会議を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5adc0-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="5adc0-108">ダイヤルイン会議の参加者、ライセンスを取得、またはその他の設定に割り当てられている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5adc0-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="5adc0-109">オーディオ会議についてよく寄せられる質問は、[オーディオ会議のよく寄せられる質問](audio-conferencing-common-questions.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5adc0-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>
  
## <a name="step-1-buy-and-assign-licenses"></a><span data-ttu-id="5adc0-110">手順 1: ライセンスを購入して割り当てる</span><span class="sxs-lookup"><span data-stu-id="5adc0-110">Step 1: Buy and assign licenses</span></span>
<span data-ttu-id="5adc0-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="5adc0-111"></span></span>

<span data-ttu-id="5adc0-112">この手順を実行するのには、 [Office 365 の管理者の役割](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5adc0-112">You must be an [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform this step.</span></span>
  
1. <span data-ttu-id="5adc0-113">Office 365 のオーディオ会議は、国/地域で利用可能なかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5adc0-113">Find out if Audio Conferencing in Office 365 is available in your country/region.</span></span> <span data-ttu-id="5adc0-114">[オーディオ会議や予定を呼び出すための国および地域の可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)です。</span><span class="sxs-lookup"><span data-stu-id="5adc0-114">[Country and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> 
    
2. <span data-ttu-id="5adc0-115">オーディオ会議、およびかかる費用は購入する必要がありますライセンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5adc0-115">Learn which licenses you need to buy for Audio Conferencing, and how much they will cost.</span></span> <span data-ttu-id="5adc0-116">[Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してくださいし、ライセンスを購入します。</span><span class="sxs-lookup"><span data-stu-id="5adc0-116">See [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md), and buy the licenses.</span></span> 
    
3. <span data-ttu-id="5adc0-117">[割り当てまたはビジネスのための Office 365 のライセンスを削除する](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)人に、組織の会議のスケジュール、または潜在顧客を購入しました。</span><span class="sxs-lookup"><span data-stu-id="5adc0-117">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
4. <span data-ttu-id="5adc0-118">**オーディオ会議**のアドオン ライセンスおよび通信のクレジットのライセンスを購入した場合も割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5adc0-118">If you purchased **Audio Conferencing** add-on licenses and Communications Credits licenses, assign them too.</span></span> <span data-ttu-id="5adc0-119">手順については、[ビジネスおよびマイクロソフトのチームのライセンスを Skype を割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5adc0-119">For instructions, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
    
## <a name="step-2-decide-on-your-audio-conferencing-provider"></a><span data-ttu-id="5adc0-120">手順 2: は、オーディオ会議プロバイダーを決定します。</span><span class="sxs-lookup"><span data-stu-id="5adc0-120">Step 2: Decide on your audio conferencing provider</span></span>
<span data-ttu-id="5adc0-121"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="5adc0-121"></span></span>

<span data-ttu-id="5adc0-122">オーディオ会議プロバイダーは、*オーディオ会議用ブリッジ*を提供します。</span><span class="sxs-lookup"><span data-stu-id="5adc0-122">An audio conferencing provider supplies an *audio conferencing bridge*.</span></span> <span data-ttu-id="5adc0-123">会議用ブリッジは、ダイヤルインの電話番号、Pin、および会議の会議 Id を設定します。</span><span class="sxs-lookup"><span data-stu-id="5adc0-123">The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings.</span></span> <span data-ttu-id="5adc0-124">Microsoft またはサード パーティ製のオーディオ会議プロバイダーを使用するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="5adc0-124">Decide whether to use Microsoft or a third-party audio conferencing provider:</span></span>
  
> [!NOTE]
> <span data-ttu-id="5adc0-125">マイクロソフトのチームのユーザーには、サード ・ パーティ製のオーディオ会議プロバイダーのユーザーことはできません。</span><span class="sxs-lookup"><span data-stu-id="5adc0-125">Microsoft Teams users can't user a third-party audio conferencing provider.</span></span> 
  
- <span data-ttu-id="5adc0-126">**オーディオ会議プロバイダーとして Microsoft**: オーディオ会議の最も簡単なソリューションをする場合は、オーディオ会議プロバイダーとして Microsoft を選択します。</span><span class="sxs-lookup"><span data-stu-id="5adc0-126">**Microsoft as your audio conferencing provider**: If you want the easiest solution for audio conferencing, choose Microsoft as your audio conferencing provider.</span></span>
    
- <span data-ttu-id="5adc0-127">**オーディオ会議プロバイダーとして、サード パーティ製**: サード ・ パーティ製のオーディオを選択する場合、Office 365 での音声会議を使用できないための場所では、優れたサービスの品質はありません、既存の契約がある国で、会議プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="5adc0-127">**Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider.</span></span> <span data-ttu-id="5adc0-128">プロバイダーを検索するには、[マイクロソフトの特定](http://go.microsoft.com/fwlink/?LinkId=797530)に移動します。</span><span class="sxs-lookup"><span data-stu-id="5adc0-128">To find a provider, go to [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).</span></span>
    
> [!TIP]
> <span data-ttu-id="5adc0-129">組織内で、電話会議プロバイダーとして Microsoft を使用している人とサードパーティを使用している人が混在している場合があります。</span><span class="sxs-lookup"><span data-stu-id="5adc0-129">In your organization, you can have some people who use Microsoft as their audio conferencing provider, and others who use a third-party provider.</span></span> <span data-ttu-id="5adc0-130">設定および管理するために複雑になります。</span><span class="sxs-lookup"><span data-stu-id="5adc0-130">But this will be more complicated for you to set up and manage.</span></span> 
  
<span data-ttu-id="5adc0-131">オーディオのプロバイダーは、Microsoft およびサード パーティ プロバイダーの間で詳細に比較は、[オーディオ会議プロバイダーの比較](compare-audio-conferencing-providers.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5adc0-131">For a detailed comparison between Microsoft as your audio provider and a third-party provider, see [Compare audio conferencing providers](compare-audio-conferencing-providers.md).</span></span> 
  
## <a name="step-3-assign-the-audio-conferencing-provider-to-people-who-lead-or-schedule-meetings"></a><span data-ttu-id="5adc0-132">手順 3: オーディオ会議プロバイダーをリードしたり、会議をスケジュールするユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="5adc0-132">Step 3: Assign the audio conferencing provider to people who lead or schedule meetings</span></span>
<span data-ttu-id="5adc0-133"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="5adc0-133"></span></span>

<span data-ttu-id="5adc0-134">オーディオ会議プロバイダーを決定したら、これでは、プロバイダーをリードしたり、会議をスケジュールする、組織内のユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5adc0-134">Now that you've decided on your audio conferencing provider, you need to assign the provider to people in your organization who lead or schedule meetings.</span></span> <span data-ttu-id="5adc0-135">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5adc0-135">Do one of the following:</span></span> 
  
- <span data-ttu-id="5adc0-136">[オーディオ会議プロバイダーとしてマイクロソフトを割り当てます](assign-microsoft-as-the-audio-conferencing-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="5adc0-136">[Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
    
- <span data-ttu-id="5adc0-137">[オーディオ会議プロバイダーとしてサードパーティ製の割り当て](assign-a-third-party-as-the-audio-conferencing-provider.md)を。</span><span class="sxs-lookup"><span data-stu-id="5adc0-137">[Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md).</span></span>
    
## <a name="step-4-set-up-meeting-invitations"></a><span data-ttu-id="5adc0-138">手順 4: 会議出席依頼の設定</span><span class="sxs-lookup"><span data-stu-id="5adc0-138">Step 4: Set up meeting invitations</span></span>
<span data-ttu-id="5adc0-139"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="5adc0-139"></span></span>

<span data-ttu-id="5adc0-140">次の手順**オプション**ですが、管理者の多くがそれらを行いたいです。</span><span class="sxs-lookup"><span data-stu-id="5adc0-140">The following steps are **optional**, but a lot of admins like to do them:</span></span>
  
1. <span data-ttu-id="5adc0-141">[ミーティングの招待状をカスタマイズ](../set-up-skype-for-business-online/customize-meeting-invitations.md)します。</span><span class="sxs-lookup"><span data-stu-id="5adc0-141">[Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span> <span data-ttu-id="5adc0-142">ユーザーに設定されているダイヤルの番号は、出席者に送信される会議出席依頼に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="5adc0-142">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to attendees.</span></span> <span data-ttu-id="5adc0-143">ただし、独自のヘルプおよび法律上のリンク、テキスト メッセージ、および小規模な会社のグラフィックを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="5adc0-143">However, you can add your own help and legal links, a text message, and small company graphic.</span></span>
    
2. <span data-ttu-id="5adc0-144">[ミーティングの開催者の招待に収録されている電話会議の電話番号を設定](set-the-phone-numbers-included-on-invites.md)します。</span><span class="sxs-lookup"><span data-stu-id="5adc0-144">[Set the Audio Conferencing phone numbers for meeting organizers that are included on invites](set-the-phone-numbers-included-on-invites.md).</span></span> <span data-ttu-id="5adc0-145">これは、ユーザーがスケジュールされている会議で表示される電話番号です。</span><span class="sxs-lookup"><span data-stu-id="5adc0-145">This is the phone number that will show up in the meeting that is scheduled by the user.</span></span>
    
3. <span data-ttu-id="5adc0-146">[オーディオ会議の自動応答の言語設定](set-auto-attendant-languages-for-audio-conferencing.md)で、電話会議の電話番号にダイヤルするときに、呼び出し元を呼びかけられるように設定するのには、オーディオ会議自動アテンダントを使用します。</span><span class="sxs-lookup"><span data-stu-id="5adc0-146">[Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md) that the audio conferencing auto attendant uses to greet a caller when they dial in to an Audio Conferencing phone number.</span></span> <span data-ttu-id="5adc0-147">この手順は、Microsoft のオーディオのプロバイダーとして使用する場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="5adc0-147">This step only applies if you're using Microsoft as your audio provider.</span></span>
    
4. <span data-ttu-id="5adc0-148">[オーディオ会議の会議の暗証番号 (pin) の長さを設定](set-the-pin-length-for-audio-conferencing-meetings.md)します。</span><span class="sxs-lookup"><span data-stu-id="5adc0-148">[Set the length of the PIN for Audio Conferencing meetings](set-the-pin-length-for-audio-conferencing-meetings.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="5adc0-149">この機能はまだ顧客に利用可能な Office 365 を使用して運用している中国で 21Vianet。</span><span class="sxs-lookup"><span data-stu-id="5adc0-149">This feature is not yet available to customers using Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="5adc0-150">詳細については、 [21Vianet によって運営されて Office 365 について](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5adc0-150">To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).</span></span> 
  
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="5adc0-151">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="5adc0-151">Related topics</span></span>

[<span data-ttu-id="5adc0-152">電話会議に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="5adc0-152">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="5adc0-153">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="5adc0-153">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="5adc0-154">電話会議の電話番号</span><span class="sxs-lookup"><span data-stu-id="5adc0-154">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="5adc0-155">オンライン会議、電話会議のオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="5adc0-155">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)

