---
title: ユーザーの設定を変更したときに送信されるメール
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
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'ユーザーのダイヤルイン会議の設定が変更された場合に、ユーザーにメールで自動的に送信される情報Microsoft Teams。 '
ms.openlocfilehash: a9ca30e7e701afca2e42eccfaef4f3d45660cd3a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120758"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="f2abf-103">Microsoft Teams で設定を変更したときにユーザーに送信されるメール</span><span class="sxs-lookup"><span data-stu-id="f2abf-103">Emails sent to users when their settings change in Microsoft Teams</span></span>

<span data-ttu-id="f2abf-104">電子メールは、電話会議プロバイダーとして Microsoft[](set-up-audio-conferencing-in-teams.md)を使用して電話会議が有効になっているユーザーに自動的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="f2abf-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing-in-teams.md) using Microsoft as the audio conferencing provider.</span></span>

<span data-ttu-id="f2abf-105">既定では、電話会議が有効になっているユーザーに送信される 4 種類のメールがあります。</span><span class="sxs-lookup"><span data-stu-id="f2abf-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="f2abf-106">ただし、ユーザーに送信されるメールの数を制限する場合は、オフにできます。</span><span class="sxs-lookup"><span data-stu-id="f2abf-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="f2abf-107">次の場合、Microsoft 365またはOffice 365電話会議は、ユーザーのメールにメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="f2abf-107">Audio Conferencing in Microsoft 365 or Office 365 will send email to your users' email when:</span></span>

- <span data-ttu-id="f2abf-108">**電話会議ライセンスが割り当てられるか、電話会議プロバイダーを Microsoft に変更するときに割り当てられます。**</span><span class="sxs-lookup"><span data-stu-id="f2abf-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>

     <span data-ttu-id="f2abf-109">このメールには、会議 ID、会議の既定の電話会議電話番号、ユーザーの電話会議 PIN、ユーザーの既存の会議を更新するために使用される Skype for Business Online 会議更新ツールを使用する手順とリンクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f2abf-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="f2abf-110">「[アドオン ライセンスMicrosoft Teams割り当てる](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」または「Microsoft を電話会議プロバイダーとして割り[当てる」を参照してください](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。</span><span class="sxs-lookup"><span data-stu-id="f2abf-110">See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

    > [!NOTE]
    > <span data-ttu-id="f2abf-111">組織で動的な会議 ID が有効になっている場合、スケジュールを設定したユーザーのすべての会議に固有の会議 ID が割り当てらされます。</span><span class="sxs-lookup"><span data-stu-id="f2abf-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="f2abf-112">組織で [電話会議の動的な ID を設定できます](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)。</span><span class="sxs-lookup"><span data-stu-id="f2abf-112">You can set up [Audio Conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 

    <span data-ttu-id="f2abf-113">このメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f2abf-113">Here is an example of this email:</span></span>

     ![Skype for Businessライセンスの確認](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    <span data-ttu-id="f2abf-115">ライセンスの詳細については、「Microsoft Teams[ライセンス」を参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="f2abf-115">To find out more about licensing, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

- <span data-ttu-id="f2abf-116">**ユーザーの会議 ID または既定の電話会議電話番号が変更されます。**</span><span class="sxs-lookup"><span data-stu-id="f2abf-116">**The conference ID or default conference phone number of a user changes.**</span></span>

    <span data-ttu-id="f2abf-117">このメールには、会議 ID、既定の電話会議電話番号、およびユーザーの既存の会議を更新するために使用される Skype for Business Online 会議更新ツールを使用する手順とリンクが含まれている。</span><span class="sxs-lookup"><span data-stu-id="f2abf-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="f2abf-118">ただし、このメールにはユーザーの電話会議 PIN は含めになっていません。</span><span class="sxs-lookup"><span data-stu-id="f2abf-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="f2abf-119">「[ユーザーの会議通話 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2abf-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>

    <span data-ttu-id="f2abf-120">このメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f2abf-120">Here is an example of this email:</span></span>

     ![ダイヤルイン会議情報が変更されました。](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- <span data-ttu-id="f2abf-122">**ユーザーの電話会議 PIN がリセットされます。**</span><span class="sxs-lookup"><span data-stu-id="f2abf-122">**The audio conferencing PIN of a user is reset.**</span></span>

    <span data-ttu-id="f2abf-123">このメールには、開催者の電話会議 PIN、既存の会議 ID、ユーザーの既定の電話会議電話番号が含まれている。</span><span class="sxs-lookup"><span data-stu-id="f2abf-123">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="f2abf-124">「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2abf-124">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
     <span data-ttu-id="f2abf-125">このメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f2abf-125">Here is an example of this email:</span></span>
    
     ![ダイヤルイン会議 PIN が変更されました。](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- <span data-ttu-id="f2abf-127">**ユーザーのライセンスが削除される、または電話会議プロバイダーが Microsoft から他のプロバイダーまたはなしに変更された場合。**</span><span class="sxs-lookup"><span data-stu-id="f2abf-127">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>

    <span data-ttu-id="f2abf-128">これは、電話会議ライセンス **が** ユーザーから削除された場合、または電話会議プロバイダーを [なし] に設定した場合に **発生します**。</span><span class="sxs-lookup"><span data-stu-id="f2abf-128">This happens when the **Audio Conferencing** license is removed from a user or when setting the audio conferencing provider to **None**.</span></span>

    <span data-ttu-id="f2abf-129">「[一Microsoft 365ライセンスの割り当てまたは削除」を参照してください](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="f2abf-129">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

    <span data-ttu-id="f2abf-130">このメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f2abf-130">Here is an example of this email:</span></span>

     ![ダイヤルイン会議は無効になります。](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="f2abf-132">送信されるメール メッセージに変更を加える</span><span class="sxs-lookup"><span data-stu-id="f2abf-132">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="f2abf-133">ユーザーに自動的に送信されるメールを変更できます。</span><span class="sxs-lookup"><span data-stu-id="f2abf-133">You can make changes to the email that is automatically sent to users.</span></span> <span data-ttu-id="f2abf-134">既定では、メールの送信者は Microsoft 365 または Office 365 から送信されますが、Windows PowerShell を使用して表示名を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f2abf-134">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the display name using Windows PowerShell.</span></span> <span data-ttu-id="f2abf-135">詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2abf-135">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="f2abf-136">メールを送信したくない場合は、どうしますか?</span><span class="sxs-lookup"><span data-stu-id="f2abf-136">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="f2abf-137">ユーザーへのメール送信を無効にすると、ユーザーにライセンスが割り当てられた場合でも、電子メールは送信されません。</span><span class="sxs-lookup"><span data-stu-id="f2abf-137">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="f2abf-138">この場合、会議 ID、既定の会議電話番号、さらに重要な点として、電話会議 PIN はユーザーに送信されません。</span><span class="sxs-lookup"><span data-stu-id="f2abf-138">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="f2abf-139">この場合は、ユーザーに別のメールを送信するか、ユーザーに電話で通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2abf-139">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>

<span data-ttu-id="f2abf-140">既定では、メールはユーザーに送信されますが、電話会議のメールを受信したくない場合は、Microsoft Teams または Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2abf-140">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams or Windows PowerShell.</span></span> 

<span data-ttu-id="f2abf-141">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="f2abf-141">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="f2abf-142">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f2abf-142">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="f2abf-143">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2abf-143">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="f2abf-144">[**ブリッジの設定**] ペインで、[**ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="f2abf-144">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="f2abf-145">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2abf-145">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="f2abf-146">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="f2abf-146">**Using Windows PowerShell**</span></span>

<span data-ttu-id="f2abf-147">詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2abf-147">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f2abf-148">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="f2abf-148">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="f2abf-149">既定では、メールの送信者は Microsoft 365 または Office 365 から送信されますが、Windows PowerShell を使用してメール アドレスと表示名を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f2abf-149">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> 

<span data-ttu-id="f2abf-150">Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。</span><span class="sxs-lookup"><span data-stu-id="f2abf-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f2abf-151">このWindows PowerShell、1 つの管理Microsoft 365またはOffice 365を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="f2abf-151">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="f2abf-152">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2abf-152">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="f2abf-153">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="f2abf-153">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - <span data-ttu-id="f2abf-154">[Windows PowerShell で Office 365 を管理するための最善の方法](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="f2abf-154">[Best ways to manage Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

<span data-ttu-id="f2abf-155">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2abf-155">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="related-topics"></a><span data-ttu-id="f2abf-156">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f2abf-156">Related topics</span></span>

[<span data-ttu-id="f2abf-157">電話会議の設定が変更されたときのメールの自動送信を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="f2abf-157">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[<span data-ttu-id="f2abf-158">電話会議の情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="f2abf-158">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)