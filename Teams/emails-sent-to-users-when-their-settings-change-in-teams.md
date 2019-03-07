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
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Microsoft Teams でダイヤルイン会議の設定を変更したときにユーザーに自動的に送信される情報について説明します。 '
ms.openlocfilehash: 6081f531bb7cbae180997dedd9e9892e9829ae1b
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462813"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="701c0-103">Microsoft Teams で設定を変更したときにユーザーに送信されるメール</span><span class="sxs-lookup"><span data-stu-id="701c0-103">Emails sent to users when their settings change in Microsoft Teams</span></span>

<span data-ttu-id="701c0-104">Microsoft を電話会議プロバイダーとして使用して[電話会議を利用できる](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)ようになっているユーザーに、メールが自動的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="701c0-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) using Microsoft as the audio conferencing provider.</span></span>

<span data-ttu-id="701c0-105">既定では、電話会議を利用できるユーザーに対して送信されるメールには、4 つの種類があります。</span><span class="sxs-lookup"><span data-stu-id="701c0-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="701c0-106">ただし、ユーザーに送信されるメールの数を制限する場合は、この設定をオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="701c0-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="701c0-107">Office 365 の電話会議は、次の場合にユーザーにメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="701c0-107">Audio Conferencing in Office 365 will send email to your users' email when:</span></span>

- <span data-ttu-id="701c0-108">**電話会議のライセンスが割り当てられているか、電話会議プロバイダーを Microsoft に変更している場合。**</span><span class="sxs-lookup"><span data-stu-id="701c0-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>

     <span data-ttu-id="701c0-109">このメールには会議 ID、既定の電話会議の電話番号、ユーザーの電話会議 PIN、およびユーザーのために既存の会議を更新するために使用される Skype for Business Online Meeting Update Tool の操作手順とリンクが記載されています。</span><span class="sxs-lookup"><span data-stu-id="701c0-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="701c0-110">[マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)または[オーディオ会議プロバイダーとしての Microsoft の割り当て](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="701c0-110">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

    > [!NOTE]
    > <span data-ttu-id="701c0-111">所属する組織で、動的な会議 ID が有効になっている場合、すべてのユーザーの会議に固有の会議 ID が設定されます。</span><span class="sxs-lookup"><span data-stu-id="701c0-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="701c0-112">[組織での電話会議の動的 ID ](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)をセットアップすることができます。</span><span class="sxs-lookup"><span data-stu-id="701c0-112">You can set up [Audio Conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 

    <span data-ttu-id="701c0-113">このメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="701c0-113">Here is an example of this email:</span></span>

     ![Skype for Business のライセンス認証](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    <span data-ttu-id="701c0-115">ライセンスの詳細については、[マイクロソフトのチームのアドオンのライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="701c0-115">To find out more about licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

- <span data-ttu-id="701c0-116">**ユーザーの会議 ID または既定の電話会議の電話番号が変更された場合。**</span><span class="sxs-lookup"><span data-stu-id="701c0-116">**The conference ID or default conference phone number of a user changes.**</span></span>

    <span data-ttu-id="701c0-117">このメールには会議 ID、既定の電話会議の電話番号、およびユーザーのために既存の会議を更新するために使用される Skype for Business Online Meeting Update Tool の操作手順とリンクが記載されています。</span><span class="sxs-lookup"><span data-stu-id="701c0-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="701c0-118">ただし、このメールにはユーザーの電話会議 PIN は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="701c0-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="701c0-119">「[ユーザーのために会議 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="701c0-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>

    <span data-ttu-id="701c0-120">このメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="701c0-120">Here is an example of this email:</span></span>

     ![ダイヤルイン会議情報が変更されました。](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- <span data-ttu-id="701c0-122">**ユーザーの電話会議の PIN がリセットされる場合。**</span><span class="sxs-lookup"><span data-stu-id="701c0-122">**The audio conferencing PIN of a user is reset.**</span></span>

    <span data-ttu-id="701c0-123">このメールには、ユーザーに向けた組織の電話会議 PIN、既存の会議 ID、および既定の電話会議の電話番号が記載されます。</span><span class="sxs-lookup"><span data-stu-id="701c0-123">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="701c0-124">「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="701c0-124">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
     <span data-ttu-id="701c0-125">このメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="701c0-125">Here is an example of this email:</span></span>
    
     ![ダイヤルイン会議 PIN が変更されました。](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- <span data-ttu-id="701c0-127">**ユーザーのライセンスが削除されたか、電話会議プロバイダーが Microsoft から他のプロバイダーに変更または、なしに設定された場合**</span><span class="sxs-lookup"><span data-stu-id="701c0-127">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>

    <span data-ttu-id="701c0-128">これは、**電話会議**ライセンスがユーザーから削除された場合、ユーザーの電話会議プロバイダーを Microsoft からサードパーティの電話会議プロバイダーに変更する場合、またはプロバイダーを [**なし**] に設定する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="701c0-128">This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**.</span></span> <span data-ttu-id="701c0-129">このメールには、ユーザーが Skype for Business Online Meeting Update Tool を使用して、既定の電話会議番号や会議 ID などの電話会議固有の情報を削除するための操作指示および情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="701c0-129">This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.</span></span>

    <span data-ttu-id="701c0-130">「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="701c0-130">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

    <span data-ttu-id="701c0-131">このメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="701c0-131">Here is an example of this email:</span></span>

     ![ダイヤルイン会議がオフになっています。](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="701c0-133">ユーザーに送信されるメールのメッセージを変更する</span><span class="sxs-lookup"><span data-stu-id="701c0-133">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="701c0-134">自動的にユーザーに送信されるメールの、*差出人*の連絡先情報に含まれるメール アドレスや表示名を、変更することができます。</span><span class="sxs-lookup"><span data-stu-id="701c0-134">You can make changes to the email that is automatically sent to users including the email address and the display name that is included in the *From* contact information.</span></span> <span data-ttu-id="701c0-135">既定では、メールの送信者は Office 365 ですが、Windows PowerShell を使用してメール アドレスと表示名を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="701c0-135">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> <span data-ttu-id="701c0-136">詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="701c0-136">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="701c0-137">ユーザーにメールが送信されないようにする場合</span><span class="sxs-lookup"><span data-stu-id="701c0-137">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="701c0-138">ユーザーへのメールの送信を無効にすると、ユーザーにライセンスが割り当てられたときでもメールは送信されません。</span><span class="sxs-lookup"><span data-stu-id="701c0-138">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="701c0-139">この場合、会議 ID、既定の電話会議の電話番号、およびより重要であるユーザーの電話会議の PIN はユーザーに送信されません。</span><span class="sxs-lookup"><span data-stu-id="701c0-139">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="701c0-140">このような場合は、ユーザーに別個のメールを送信するか、電話をすることによって伝える必要があります。</span><span class="sxs-lookup"><span data-stu-id="701c0-140">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>

<span data-ttu-id="701c0-141">既定では、メールはユーザーに送信されますが、Microsoft Teams または Windows PowerShell を使用して、電話会議についてのメールをユーザーが受け取らないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="701c0-141">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams or Windows PowerShell.</span></span> 

<span data-ttu-id="701c0-142">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**</span><span class="sxs-lookup"><span data-stu-id="701c0-142">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="701c0-143">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="701c0-143">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="701c0-144">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="701c0-144">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="701c0-145">[**ブリッジの設定**] ペインで、[**ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="701c0-145">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="701c0-146">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="701c0-146">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="701c0-147">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="701c0-147">**Using Windows PowerShell**</span></span>

<span data-ttu-id="701c0-148">詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="701c0-148">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="701c0-149">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="701c0-149">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="701c0-150">既定では、メールの送信者は Office 365 ですが、Windows PowerShell を使用してメール アドレスと表示名を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="701c0-150">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> 

<span data-ttu-id="701c0-p109">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="701c0-p109">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="701c0-154">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="701c0-154">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="701c0-155">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="701c0-155">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

<span data-ttu-id="701c0-156">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="701c0-156">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="related-topics"></a><span data-ttu-id="701c0-157">関連トピック</span><span class="sxs-lookup"><span data-stu-id="701c0-157">Related topics</span></span>

[<span data-ttu-id="701c0-158">電話会議の設定が変更されたときのメールの自動送信を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="701c0-158">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[<span data-ttu-id="701c0-159">電話会議の情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="701c0-159">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
