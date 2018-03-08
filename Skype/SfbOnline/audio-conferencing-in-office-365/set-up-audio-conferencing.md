---
title: "Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。"
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
description: "電話を使用して会議に参加する必要があるビジネスで他のユーザーのダイヤルインまたは音声会議を設定する方法について説明します。 "
ms.openlocfilehash: 44eaa0c7a90c0e9495eaffc81de4d9dcf9f06bbd
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a><span data-ttu-id="254ba-103">Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。</span><span class="sxs-lookup"><span data-stu-id="254ba-103">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>

<span data-ttu-id="254ba-p101">組織のユーザーは、電話を使用して、会議にコールインする必要があります。Skype for Business とチームを Microsoft には、電話会議機能にはこれだけが含まれます。ユーザーが会議に参加 Skype に Business または Microsoft チーム会議が、Skype を使用して for Business または Microsoft チームのアプリをモバイル デバイスや PC ではなく、電話を使用します。</span><span class="sxs-lookup"><span data-stu-id="254ba-p101">Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="254ba-p102">のみ、スケジュールや会議を計画しているユーザーの電話会議を設定する必要があります。ダイヤルイン会議の参加者には、またはその他のセットアップに割り当てられているライセンスを必要はありません。</span><span class="sxs-lookup"><span data-stu-id="254ba-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="254ba-109">音声会議についてよく寄せられる質問は、[電話会議のよく寄せられる質問](audio-conferencing-common-questions.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="254ba-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>
  
## <a name="step-1-buy-and-assign-licenses"></a><span data-ttu-id="254ba-110">手順 1: 購入して、ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="254ba-110">Step 1: Buy and assign licenses</span></span>
<span data-ttu-id="254ba-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="254ba-111"></span></span>

<span data-ttu-id="254ba-112">この手順を実行するを[Office 365 の管理者の役割](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)があります。</span><span class="sxs-lookup"><span data-stu-id="254ba-112">You must be an [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform this step.</span></span>
  
1. <span data-ttu-id="254ba-p103">Office 365 で音声会議が住んでいる国/地域で利用可能なかどうかを確認します。[電話会議とプランの呼び出しの国と地域の空き時間情報](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="254ba-p103">Find out if Audio Conferencing in Office 365 is available in your country/region. [Country and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> 
    
2. <span data-ttu-id="254ba-p104">音声会議、およびコストはどの程度を購入する必要があります。 ライセンスについて説明します。[Skype for Business や Microsoft チーム アドオンのライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を表示し、ライセンスを購入します。</span><span class="sxs-lookup"><span data-stu-id="254ba-p104">Learn which licenses you need to buy for Audio Conferencing, and how much they will cost. See [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md), and buy the licenses.</span></span> 
    
3. <span data-ttu-id="254ba-117">ユーザーが会議をスケジュールまたは潜在顧客] に、組織のユーザーを購入した[の割り当てまたは一般法人向け Office 365 のライセンスを削除](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)します。</span><span class="sxs-lookup"><span data-stu-id="254ba-117">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
4. <span data-ttu-id="254ba-p105">**電話会議**アドオン ライセンスとの通信クレジット ライセンスを購入した場合も割り当てます。手順については、[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="254ba-p105">If you purchased **Audio Conferencing** add-on licenses and Communications Credits licenses, assign them too. For instructions, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
    
## <a name="step-2-decide-on-your-audio-conferencing-provider"></a><span data-ttu-id="254ba-120">手順 2: は、電話会議プロバイダーを決定します。</span><span class="sxs-lookup"><span data-stu-id="254ba-120">Step 2: Decide on your audio conferencing provider</span></span>
<span data-ttu-id="254ba-121"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="254ba-121"></span></span>

<span data-ttu-id="254ba-p106">電話会議プロバイダーは、*電話会議ブリッジ*を提供します。会議ブリッジにダイヤルイン電話番号、Pin や会議の会議 Id を設定します。Microsoft またはサード パーティの電話会議プロバイダーを使用するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="254ba-p106">An audio conferencing provider supplies an *audio conferencing bridge*. The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings. Decide whether to use Microsoft or a third-party audio conferencing provider:</span></span>
  
> [!NOTE]
> <span data-ttu-id="254ba-125">Microsoft チームのユーザーには、サードパーティ電話会議プロバイダーをユーザーことはできません。</span><span class="sxs-lookup"><span data-stu-id="254ba-125">Microsoft Teams users can't user a third-party audio conferencing provider.</span></span> 
  
- <span data-ttu-id="254ba-126">**電話会議プロバイダーとして Microsoft**: 電話会議の最も簡単に解決するには、場合は、電話会議プロバイダーとして Microsoft を選択します。</span><span class="sxs-lookup"><span data-stu-id="254ba-126">**Microsoft as your audio conferencing provider**: If you want the easiest solution for audio conferencing, choose Microsoft as your audio conferencing provider.</span></span>
    
- <span data-ttu-id="254ba-p107">**電話会議プロバイダーとしてサードパーティ**: 国、Office 365 で音声会議は使用できません、サービスの品質がない理由により、その場所では、とても便利なまたは既存の契約がある場合は、サード パーティの音声を] を選びます。会議のプロバイダーします。プロバイダーを見つけるには、 [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530)へ移動します。</span><span class="sxs-lookup"><span data-stu-id="254ba-p107">**Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider. To find a provider, go to [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).</span></span>
    
> [!TIP]
> <span data-ttu-id="254ba-p108">自分の組織では、自分の電話会議プロバイダーとして Microsoft を使用している一部のユーザーと他のユーザーをサードパーティ プロバイダーを使用していることができます。設定および管理するためのより複雑になります。</span><span class="sxs-lookup"><span data-stu-id="254ba-p108">In your organization, you can have some people who use Microsoft as their audio conferencing provider, and others who use a third-party provider. But this will be more complicated for you to set up and manage.</span></span> 
  
<span data-ttu-id="254ba-131">オーディオ プロバイダーとして Microsoft およびサードパーティ プロバイダー間の詳細な比較] は、「[電話会議プロバイダーを比較する](compare-audio-conferencing-providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="254ba-131">For a detailed comparison between Microsoft as your audio provider and a third-party provider, see [Compare audio conferencing providers](compare-audio-conferencing-providers.md).</span></span> 
  
## <a name="step-3-assign-the-audio-conferencing-provider-to-people-who-lead-or-schedule-meetings"></a><span data-ttu-id="254ba-132">手順 3: 潜在顧客、または会議をスケジュールしてきた相手に電話会議プロバイダーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="254ba-132">Step 3: Assign the audio conferencing provider to people who lead or schedule meetings</span></span>
<span data-ttu-id="254ba-133"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="254ba-133"></span></span>

<span data-ttu-id="254ba-p109">電話会議プロバイダーを決定したら、潜在顧客、または会議をスケジュールした組織内のユーザーに、プロバイダーを割り当てる必要があります。{次のいずれかを行います。}</span><span class="sxs-lookup"><span data-stu-id="254ba-p109">Now that you've decided on your audio conferencing provider, you need to assign the provider to people in your organization who lead or schedule meetings. Do one of the following:</span></span> 
  
- <span data-ttu-id="254ba-136">[電話会議プロバイダーとして Microsoft を割り当てます](assign-microsoft-as-the-audio-conferencing-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="254ba-136">[Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
    
- <span data-ttu-id="254ba-137">[電話会議プロバイダーとしてサードパーティを割り当てます](assign-a-third-party-as-the-audio-conferencing-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="254ba-137">[Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md).</span></span>
    
## <a name="step-4-set-up-meeting-invitations"></a><span data-ttu-id="254ba-138">手順 4: 会議出席依頼を設定します。</span><span class="sxs-lookup"><span data-stu-id="254ba-138">Step 4: Set up meeting invitations</span></span>
<span data-ttu-id="254ba-139"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="254ba-139"></span></span>

<span data-ttu-id="254ba-140">次の手順**オプション**ですが、それらを実行するなどの多くの管理者。</span><span class="sxs-lookup"><span data-stu-id="254ba-140">The following steps are **optional**, but a lot of admins like to do them:</span></span>
  
1. <span data-ttu-id="254ba-p110">[会議の出席依頼をカスタマイズ](../set-up-skype-for-business-online/customize-meeting-invitations.md)します。ユーザーに設定されているダイヤルイン番号は、出席者に送信された会議出席依頼に自動的に追加されます。ただし、独自のヘルプ、法的なリンク、テキスト メッセージで、小規模企業のグラフィックを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="254ba-p110">[Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md). The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to attendees. However, you can add your own help and legal links, a text message, and small company graphic.</span></span>
    
2. <span data-ttu-id="254ba-p111">[会議の開催者の招待に収録されている電話会議の電話番号を設定](set-the-phone-numbers-included-on-invites.md)します。これは、電話番号をユーザーがスケジュールされている会議が表示されます。</span><span class="sxs-lookup"><span data-stu-id="254ba-p111">[Set the Audio Conferencing phone numbers for meeting organizers that are included on invites](set-the-phone-numbers-included-on-invites.md). This is the phone number that will show up in the meeting that is scheduled by the user.</span></span>
    
3. <span data-ttu-id="254ba-p112">[電話会議の自動応答の言語を設定する](set-auto-attendant-languages-for-audio-conferencing.md)のに、電話会議の電話番号にダイヤルインしたときに、発信者をあいさつ電話会議の自動応答を使用します。この手順は、オーディオ プロバイダーとして Microsoft を使っている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="254ba-p112">[Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md) that the audio conferencing auto attendant uses to greet a caller when they dial in to an Audio Conferencing phone number. This step only applies if you're using Microsoft as your audio provider.</span></span>
    
4. <span data-ttu-id="254ba-148">[電話会議の会議の PIN の長さを設定](set-the-pin-length-for-audio-conferencing-meetings.md)します。</span><span class="sxs-lookup"><span data-stu-id="254ba-148">[Set the length of the PIN for Audio Conferencing meetings](set-the-pin-length-for-audio-conferencing-meetings.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="254ba-p113">この機能はまだ中国の 21 vianet 顧客に利用可能な Office 365 を使って操作します。詳細については、 [21 vianet が運営する Office 365 について](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE)参照してください。</span><span class="sxs-lookup"><span data-stu-id="254ba-p113">This feature is not yet available to customers using Office 365 operated by 21Vianet in China. To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).</span></span> 
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="254ba-151">関連トピック</span><span class="sxs-lookup"><span data-stu-id="254ba-151">Related topics</span></span>

[<span data-ttu-id="254ba-152">音声会議よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="254ba-152">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="254ba-153">Skype for Business Online をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="254ba-153">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="254ba-154">電話会議の電話番号</span><span class="sxs-lookup"><span data-stu-id="254ba-154">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="254ba-155">オンライン会議と電話会議のオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="254ba-155">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)

