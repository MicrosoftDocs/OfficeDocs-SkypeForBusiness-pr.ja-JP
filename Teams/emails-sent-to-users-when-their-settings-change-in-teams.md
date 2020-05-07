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
description: 'Microsoft Teams でダイヤルイン会議の設定が変更されたときに、メールで自動的にユーザーに送信される情報について説明します。 '
ms.openlocfilehash: 4c4668e671b65a7927434a5ad7c9028d673d47b3
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042864"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="7b65e-103">Microsoft Teams で設定を変更したときにユーザーに送信されるメール</span><span class="sxs-lookup"><span data-stu-id="7b65e-103">Emails sent to users when their settings change in Microsoft Teams</span></span>

<span data-ttu-id="7b65e-104">Microsoft を電話会議プロバイダーとして使用する電話[会議用に有効になっ](set-up-audio-conferencing-in-teams.md)ているユーザーには、メールが自動的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="7b65e-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing-in-teams.md) using Microsoft as the audio conferencing provider.</span></span>

<span data-ttu-id="7b65e-105">既定では、電話会議が有効になっているユーザーに送信されるメールには4種類のメールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="7b65e-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="7b65e-106">ただし、ユーザーに送信されるメールの数を制限する場合は、オフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="7b65e-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="7b65e-107">Office 365 の電話会議では、次の場合にユーザーのメールにメールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="7b65e-107">Audio Conferencing in Office 365 will send email to your users' email when:</span></span>

- <span data-ttu-id="7b65e-108">**電話会議ライセンスが割り当てられているか、電話会議プロバイダーを Microsoft に変更する場合。**</span><span class="sxs-lookup"><span data-stu-id="7b65e-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>

     <span data-ttu-id="7b65e-109">このメールには、会議 ID、会議用の既定の会議電話番号、ユーザー用の電話会議の PIN、およびユーザーの既存の会議を更新するために使用される Skype for Business Online Meeting Update Tool を使用するための手順とリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7b65e-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="7b65e-110">「 [Microsoft Teams のアドオンライセンスを割り当てる](teams-add-on-licensing/assign-teams-add-on-licenses.md)」または「 [microsoft を電話会議プロバイダーとして割り当てる](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b65e-110">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

    > [!NOTE]
    > <span data-ttu-id="7b65e-111">組織で動的会議 Id が有効になっている場合、スケジュールされているすべてのユーザーの会議には、固有の会議 Id が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="7b65e-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="7b65e-112">[組織内の電話会議の動的 id](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="7b65e-112">You can set up [Audio Conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 

    <span data-ttu-id="7b65e-113">このメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7b65e-113">Here is an example of this email:</span></span>

     ![Skype for Business のライセンスを確認する](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    <span data-ttu-id="7b65e-115">ライセンスの詳細については、「 [Microsoft Teams のアドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b65e-115">To find out more about licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

- <span data-ttu-id="7b65e-116">**会議 ID またはユーザーの既定の会議の電話番号が変更されます。**</span><span class="sxs-lookup"><span data-stu-id="7b65e-116">**The conference ID or default conference phone number of a user changes.**</span></span>

    <span data-ttu-id="7b65e-117">このメールには、会議 ID、既定の会議電話番号、およびユーザーの既存の会議を更新するために使用される Skype for Business Online Meeting 更新ツールを使用するための手順とリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7b65e-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="7b65e-118">ただし、このメールには、ユーザーの電話会議の PIN は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="7b65e-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="7b65e-119">「[ユーザーの会議通話 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b65e-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>

    <span data-ttu-id="7b65e-120">このメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7b65e-120">Here is an example of this email:</span></span>

     ![ダイヤルイン会議情報が変更されました。](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- <span data-ttu-id="7b65e-122">**ユーザーの電話会議の PIN がリセットされます。**</span><span class="sxs-lookup"><span data-stu-id="7b65e-122">**The audio conferencing PIN of a user is reset.**</span></span>

    <span data-ttu-id="7b65e-123">このメールには、開催者の電話会議の PIN、既存の会議 ID、ユーザー用の既定の会議電話番号が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7b65e-123">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="7b65e-124">「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b65e-124">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
     <span data-ttu-id="7b65e-125">このメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7b65e-125">Here is an example of this email:</span></span>
    
     ![ダイヤルイン会議の PIN が変更されました。](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- <span data-ttu-id="7b65e-127">**ユーザーのライセンスが削除されるか、電話会議プロバイダーが Microsoft から別のプロバイダーまたは [なし] に変更されたとき。**</span><span class="sxs-lookup"><span data-stu-id="7b65e-127">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>

    <span data-ttu-id="7b65e-128">この問題は、電話**会議**のライセンスがユーザーから削除された場合、または電話会議プロバイダーを **[なし**] に設定した場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="7b65e-128">This happens when the **Audio Conferencing** license is removed from a user or when setting the audio conferencing provider to **None**.</span></span>

    <span data-ttu-id="7b65e-129">「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7b65e-129">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

    <span data-ttu-id="7b65e-130">このメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7b65e-130">Here is an example of this email:</span></span>

     ![ダイヤルイン会議が無効になっています。](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="7b65e-132">送信されたメールメッセージに変更を加える</span><span class="sxs-lookup"><span data-stu-id="7b65e-132">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="7b65e-133">ユーザーに自動的に送信されるメールに変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="7b65e-133">You can make changes to the email that is automatically sent to users.</span></span> <span data-ttu-id="7b65e-134">既定では、メールの送信者は Office 365 から送信されますが、Windows PowerShell を使用して表示名を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="7b65e-134">By default, the sender of the emails will be from Office 365, but you can change the display name using Windows PowerShell.</span></span> <span data-ttu-id="7b65e-135">詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7b65e-135">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="7b65e-136">メールを送信したくない場合はどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="7b65e-136">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="7b65e-137">ユーザーへのメールの送信を無効にすると、ユーザーにライセンスが割り当てられてもメールは送信されません。</span><span class="sxs-lookup"><span data-stu-id="7b65e-137">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="7b65e-138">この場合、会議 ID、既定の会議電話番号、さらに重要なのは、電話会議の PIN はユーザーに送信されません。</span><span class="sxs-lookup"><span data-stu-id="7b65e-138">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="7b65e-139">この問題が発生した場合は、個別のメールを送信するか、または電話をかけて、ユーザーに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b65e-139">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>

<span data-ttu-id="7b65e-140">既定では、メールはユーザーに送信されますが、電話会議のメールを受信しないようにするには、Microsoft Teams または Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="7b65e-140">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams or Windows PowerShell.</span></span> 

<span data-ttu-id="7b65e-141">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="7b65e-141">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="7b65e-142">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="7b65e-142">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="7b65e-143">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b65e-143">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="7b65e-144">[**ブリッジの設定**] ペインで、[**ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="7b65e-144">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="7b65e-145">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b65e-145">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="7b65e-146">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="7b65e-146">**Using Windows PowerShell**</span></span>

<span data-ttu-id="7b65e-147">詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7b65e-147">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="7b65e-148">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="7b65e-148">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="7b65e-149">既定では、メールの送信者は Office 365 から送信されますが、Windows PowerShell を使用してメールアドレスと表示名を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="7b65e-149">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> 

<span data-ttu-id="7b65e-p108">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b65e-p108">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="7b65e-153">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="7b65e-153">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="7b65e-154">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="7b65e-154">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

<span data-ttu-id="7b65e-155">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7b65e-155">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="related-topics"></a><span data-ttu-id="7b65e-156">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7b65e-156">Related topics</span></span>

[<span data-ttu-id="7b65e-157">電話会議の設定が変更されたときのメールの自動送信を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="7b65e-157">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[<span data-ttu-id="7b65e-158">電話会議の情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="7b65e-158">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
