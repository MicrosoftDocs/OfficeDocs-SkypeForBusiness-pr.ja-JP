---
title: Microsoft Teams で設定を変更したときにユーザーに送信されるメール
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Microsoft Teams でダイヤルイン会議の設定を変更したときにユーザーに自動的に送信される情報について説明します。 '
ms.openlocfilehash: b1bd7764f7780267d9f2a98a3203f49d2c0e938e
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016166"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="30440-103">Microsoft Teams で設定を変更したときにユーザーに送信されるメール</span><span class="sxs-lookup"><span data-stu-id="30440-103">Emails sent to users when their settings change in Microsoft Teams</span></span>

<span data-ttu-id="30440-104">Microsoft を電話会議プロバイダーとして使用して[電話会議を利用できる](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)ようになっているユーザーに、メールが自動的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="30440-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) using Microsoft as the audio conferencing provider.</span></span>
  
<span data-ttu-id="30440-105">既定では、電話会議が有効になっているユーザーに送信される電子メールの 4 つの種類があります。</span><span class="sxs-lookup"><span data-stu-id="30440-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="30440-106">ただし、ユーザーに送信するメールの数を制限する場合は、オフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="30440-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="30440-107">Office 365 のオーディオ会議は、ユーザーの電子メールを送信時に電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="30440-107">Audio Conferencing in Office 365 will send email to your users' email when:</span></span>
  
- <span data-ttu-id="30440-108">**電話会議のライセンスが割り当てられているか、電話会議プロバイダーを Microsoft に変更している場合。**</span><span class="sxs-lookup"><span data-stu-id="30440-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>
    
     <span data-ttu-id="30440-109">この電子メールには、会議、音声会議、ユーザーの指示およびリンク ビジネス オンライン会議の更新ツールの既存の会議を更新するために使用されるため、Skype を使用するのには、暗証番号 (pin) の既定の会議電話番号、会議 ID が含まれています、ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="30440-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="30440-110">[ビジネスおよびマイクロソフトのチームのライセンスの割り当ての Skype](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)または[オーディオ会議プロバイダーとしての Microsoft の割り当て](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30440-110">See [Assign Skype for Business and Microsoft Teams licenses](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="30440-111">会議 Id を動的に組織を有効になっている、会議 Id を表す一意のすべてのユーザーの会議をスケジュールするがあります。</span><span class="sxs-lookup"><span data-stu-id="30440-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="30440-112">[組織で電話会議の動的な Id](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)を設定できます。</span><span class="sxs-lookup"><span data-stu-id="30440-112">You can set up [Audio Conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 
  
    <span data-ttu-id="30440-113">このメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="30440-113">Here is an example of this email:</span></span>
    
     ![Skype for Business のライセンス認証](media/audio-conferencing-user-enabled.png)
  
    <span data-ttu-id="30440-115">ライセンスの詳細については、「[Skype for Business と Microsoft Teams のアドオン ライセンス](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="30440-115">You can find out more about licensing by seeing [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
    
- <span data-ttu-id="30440-116">**ユーザーの会議 ID または既定の電話会議の電話番号が変更された場合。**</span><span class="sxs-lookup"><span data-stu-id="30440-116">**The conference ID or default conference phone number of a user changes.**</span></span>
    
    <span data-ttu-id="30440-117">この電子メールには、会議 ID、既定の会議の電話番号、指示およびリンク ビジネス オンライン会議の更新ツールを使用して、ユーザーの既存の会議を更新するため、Skype を使用するのにが含まれています。</span><span class="sxs-lookup"><span data-stu-id="30440-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="30440-118">ですが、この電子メールにはユーザーの電話会議暗証番号 (pin) にはが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="30440-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="30440-119">[](reset-a-conference-id-for-a-user-in-teams.md)Reset a conference organizer's PIN</span><span class="sxs-lookup"><span data-stu-id="30440-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
    <span data-ttu-id="30440-120">このメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="30440-120">Here is an example of this email:</span></span>
    
     ![ダイヤルイン会議情報が変更されました。](media/audio-conferencing-info-change.png)
  
- <span data-ttu-id="30440-122">**ユーザーの電話会議の PIN がリセットされる場合。**</span><span class="sxs-lookup"><span data-stu-id="30440-122">**The audio conferencing PIN of a user is reset.**</span></span>
    
    <span data-ttu-id="30440-123">この電子メールには、電話会議の開催者の暗証番号 (pin) では、既存の会議 ID、およびユーザーの既定の会議電話番号が含まれています。</span><span class="sxs-lookup"><span data-stu-id="30440-123">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="30440-124">[オーディオ会議の PIN のリセット](reset-the-audio-conferencing-pin-in-teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30440-124">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
  
    <span data-ttu-id="30440-125">このメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="30440-125">Here is an example of this email:</span></span>
    
     ![ダイヤルイン会議 PIN が変更されました。](media/audio-conferencing-pin-has-changed.png)
  
- <span data-ttu-id="30440-127">**ユーザーのライセンスが削除されたか、電話会議プロバイダーが Microsoft から他のプロバイダーに変更または、なしに設定された場合**</span><span class="sxs-lookup"><span data-stu-id="30440-127">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>
    
    <span data-ttu-id="30440-128">これは、**オーディオ会議**のライセンスが削除されると、ユーザー、またはサード ・ パーティ製のオーディオ会議プロバイダーをマイクロソフトからユーザーの電話会議プロバイダーを変更する場合、プロバイダーを **[なし]** に設定する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="30440-128">This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**.</span></span> <span data-ttu-id="30440-129">この電子メールには、説明および既定の会議電話番号] または [会議 ID などの特定の情報、オーディオ会議を削除するのには会議の更新ツールのオンライン ビジネスの Skype を使用するユーザーの情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="30440-129">This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.</span></span>
    
    <span data-ttu-id="30440-130">「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="30440-130">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
    <span data-ttu-id="30440-131">このメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="30440-131">Here is an example of this email:</span></span>
    
     ![ダイヤルイン会議がオフになっています。](media/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="30440-133">ユーザーに送信されるメールのメッセージを変更する</span><span class="sxs-lookup"><span data-stu-id="30440-133">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="30440-134">ユーザーの電子メール アドレスなど*の*連絡先情報に記載されている表示名を自動的に送信される電子メールには、変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="30440-134">You can make changes to the email that is automatically sent to users including the email address and the display name that is included in the *From* contact information.</span></span> <span data-ttu-id="30440-135">既定では、電子メールの送信者は、Office 365 からなりますが、電子メール アドレスを変更し、Windows PowerShell を使用して名前を表示できます。</span><span class="sxs-lookup"><span data-stu-id="30440-135">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> <span data-ttu-id="30440-136">詳細については[マイクロソフト チームの PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30440-136">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="30440-137">ユーザーにメールが送信されないようにする場合</span><span class="sxs-lookup"><span data-stu-id="30440-137">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="30440-138">ユーザーに e メールを送信を無効にするとは、ユーザーにライセンスが割り当てられているを取得するときにも電子メールが送信されません。</span><span class="sxs-lookup"><span data-stu-id="30440-138">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="30440-139">会議 ID は、ここでは既定の会議の電話番号、および、さらに、オーディオ会議の暗証番号 (pin) をユーザーに送信されません。</span><span class="sxs-lookup"><span data-stu-id="30440-139">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="30440-140">このような場合は、別の電子メールを送信することによって、またはそれらを呼び出すことによってユーザーに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30440-140">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>
  
<span data-ttu-id="30440-141">既定では、メールはユーザーに送信されますが、Microsoft Teams または Windows PowerShell を使用して、電話会議についてのメールをユーザーが受け取らないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="30440-141">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams or Windows PowerShell.</span></span> 

<span data-ttu-id="30440-142">![teams-logo-30x30.png](media/teams-logo-30x30.png) \*\*Microsoft Teams と Skype for Business 管理センターを使用する: \*\*</span><span class="sxs-lookup"><span data-stu-id="30440-142">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="30440-143">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="30440-143">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="30440-144">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30440-144">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="30440-145">[**ブリッジの設定**] ペインで、[**ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="30440-145">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="30440-146">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30440-146">Click **Save**.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
<span data-ttu-id="30440-147">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="30440-147">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="30440-148">詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="30440-148">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="30440-149">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="30440-149">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="30440-150">既定では、メールの送信者は Office 365 ですが、Windows PowerShell を使用してメール アドレスと表示名を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="30440-150">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> 

<span data-ttu-id="30440-p109">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="30440-p109">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="30440-154">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="30440-154">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="30440-155">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="30440-155">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="30440-156">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="30440-156">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
  
## <a name="related-topics"></a><span data-ttu-id="30440-157">関連トピック</span><span class="sxs-lookup"><span data-stu-id="30440-157">Related topics</span></span>

[<span data-ttu-id="30440-158">電話会議の設定が変更されたときのメールの自動送信を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="30440-158">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)
  
[<span data-ttu-id="30440-159">電話会議の情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="30440-159">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
