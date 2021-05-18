---
title: Skype for Business Online で設定が変更された場合にユーザーに送信されるメール
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Skype for Business Online でダイヤルイン会議の設定が変更された場合に、ユーザーにメールで自動的に送信される情報についてSkype for Businessします。 '
ms.openlocfilehash: 75ed80ef7d686ecb649bc1d21f30a43fd115f1a3
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237343"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a><span data-ttu-id="734cf-103">Skype for Business Online で設定が変更された場合にユーザーに送信されるメール</span><span class="sxs-lookup"><span data-stu-id="734cf-103">Emails sent to users when their settings change in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="734cf-104">Microsoft Teams で自動メール情報を探している場合は、「Microsoft Teams で設定が変更された場合にユーザーに送信されるメール」[を参照Microsoft Teams。](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams)</span><span class="sxs-lookup"><span data-stu-id="734cf-104">If you're looking for automatic email information in Microsoft Teams, see [Emails sent to users when their settings change in Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="734cf-105">電子メールは、電話会議プロバイダーとして Microsoft[](set-up-audio-conferencing.md)を使用して電話会議が有効になっているユーザーに自動的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="734cf-105">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing.md) using Microsoft as the audio conferencing provider.</span></span>
  
<span data-ttu-id="734cf-106">既定では、電話会議が有効になっているユーザーに送信される 4 種類のメールがあります。</span><span class="sxs-lookup"><span data-stu-id="734cf-106">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="734cf-107">ただし、ユーザーに送信されるメールの数を制限する場合は、オフにできます。</span><span class="sxs-lookup"><span data-stu-id="734cf-107">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="734cf-108">次の場合、Microsoft 365またはOffice 365電話会議は、ユーザーのメールにメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="734cf-108">Audio Conferencing in Microsoft 365 or Office 365 will send email to your users' email when:</span></span>
  
- <span data-ttu-id="734cf-109">**電話会議ライセンスが割り当てられるか、電話会議プロバイダーを Microsoft に変更するときに割り当てられます。**</span><span class="sxs-lookup"><span data-stu-id="734cf-109">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>
    
     <span data-ttu-id="734cf-110">このメールには、会議 ID、会議の既定の電話会議電話番号、ユーザーの電話会議 PIN、ユーザーの既存の会議を更新するために使用される Skype for Business Online 会議更新ツールを使用する手順とリンクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="734cf-110">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="734cf-111">「[ライセンスを割りSkype for Business割り当てる」](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)または[「Microsoft を電話会議プロバイダーとして割り当てる」を参照してください](assign-microsoft-as-the-audio-conferencing-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="734cf-111">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="734cf-112">組織で動的な会議 ID が有効になっている場合、スケジュールを設定したユーザーのすべての会議に固有の会議 ID が割り当てらされます。</span><span class="sxs-lookup"><span data-stu-id="734cf-112">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="734cf-113">組織で [電話会議の動的な ID を設定できます](./reset-a-conference-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="734cf-113">You can set up [Audio Conferencing dynamic IDs in your organization](./reset-a-conference-id-for-a-user.md).</span></span> 
  
    <span data-ttu-id="734cf-114">このメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="734cf-114">Here is an example of this email:</span></span>
    
     ![Skype for Businessライセンスの確認](../images/audio-conferencing-user-enabled.png)
  
    <span data-ttu-id="734cf-116">追加ライセンスの詳細については、「Skype for Businessライセンス」をSkype for Business[参照してください](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="734cf-116">You can find out more about Skype for Business licensing by seeing [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
- <span data-ttu-id="734cf-117">**ユーザーの会議 ID または既定の電話会議電話番号が変更されます。**</span><span class="sxs-lookup"><span data-stu-id="734cf-117">**The conference ID or default conference phone number of a user changes.**</span></span>
    
    <span data-ttu-id="734cf-118">このメールには、会議 ID、既定の電話会議電話番号、およびユーザーの既存の会議を更新するために使用される Skype for Business Online 会議更新ツールを使用する手順とリンクが含まれている。</span><span class="sxs-lookup"><span data-stu-id="734cf-118">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="734cf-119">ただし、このメールにはユーザーの電話会議 PIN は含めになっていません。</span><span class="sxs-lookup"><span data-stu-id="734cf-119">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="734cf-120">「[ユーザーの会議通話 ID をリセットする](reset-a-conference-id-for-a-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="734cf-120">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="734cf-121">組織で動的な会議 ID が有効になっている場合、スケジュールを設定したユーザーのすべての会議に固有の会議 ID が割り当てらされます。</span><span class="sxs-lookup"><span data-stu-id="734cf-121">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="734cf-122">組織で [電話会議の動的な ID を設定できます](./reset-a-conference-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="734cf-122">You can set up [Audio Conferencing dynamic IDs in your organization](./reset-a-conference-id-for-a-user.md).</span></span> 
  
    <span data-ttu-id="734cf-123">このメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="734cf-123">Here is an example of this email:</span></span>
    
     ![ダイヤルイン会議情報が変更されました。](../images/audio-conferencing-info-change.png)
  
- <span data-ttu-id="734cf-125">**ユーザーの電話会議 PIN がリセットされます。**</span><span class="sxs-lookup"><span data-stu-id="734cf-125">**The audio conferencing PIN of a user is reset.**</span></span>
    
    <span data-ttu-id="734cf-126">このメールには、開催者の電話会議 PIN、既存の会議 ID、ユーザーの既定の電話会議電話番号が含まれている。</span><span class="sxs-lookup"><span data-stu-id="734cf-126">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="734cf-127">「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="734cf-127">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="734cf-128">組織で動的な会議 ID が有効になっている場合、スケジュールを設定したユーザーのすべての会議に固有の会議 ID が割り当てらされます。</span><span class="sxs-lookup"><span data-stu-id="734cf-128">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="734cf-129">組織で [電話会議の動的な ID を設定できます](./reset-a-conference-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="734cf-129">You can set up [Audio Conferencing dynamic IDs in your organization](./reset-a-conference-id-for-a-user.md).</span></span> 
  
    <span data-ttu-id="734cf-130">このメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="734cf-130">Here is an example of this email:</span></span>
    
     ![ダイヤルイン会議 PIN が変更されました。](../images/audio-conferencing-pin-has-changed.png)
  
- <span data-ttu-id="734cf-132">**ユーザーのライセンスが削除される、または電話会議プロバイダーが Microsoft から他のプロバイダーまたはなしに変更された場合。**</span><span class="sxs-lookup"><span data-stu-id="734cf-132">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>
    
    <span data-ttu-id="734cf-133">これは、電話会議ライセンスがユーザーから削除された場合、またはユーザーの電話会議プロバイダーを Microsoft からサードパーティの電話会議プロバイダーに変更する場合、またはプロバイダーを [なし] に設定するときに発生 **します**。</span><span class="sxs-lookup"><span data-stu-id="734cf-133">This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**.</span></span> <span data-ttu-id="734cf-134">このメールには、ユーザーが Skype for Business Online Meeting Update Tool を使用して、既定の電話会議の電話番号や会議 ID などの電話会議固有の情報を削除する手順と情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="734cf-134">This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.</span></span>
    
    <span data-ttu-id="734cf-135">「ライセンス[の割り当てまたは削除」をMicrosoft 365 Apps for business。](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="734cf-135">See [Assign or remove licenses for Microsoft 365 Apps for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
    <span data-ttu-id="734cf-136">このメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="734cf-136">Here is an example of this email:</span></span>
    
     ![ダイヤルイン会議は無効になります。](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="734cf-138">送信されるメール メッセージに変更を加える</span><span class="sxs-lookup"><span data-stu-id="734cf-138">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="734cf-139">[From] 連絡先情報に含まれるメール アドレスや表示名など、ユーザーに自動的に送信されるメール *を変更できます* 。</span><span class="sxs-lookup"><span data-stu-id="734cf-139">You can make changes to the email that is automatically sent to users including the email address and the display name that is included in the *From* contact information.</span></span> <span data-ttu-id="734cf-140">既定では、メールの送信者は Microsoft 365 または Office 365 から送信されますが、Windows PowerShell コマンドレットと[Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10))コマンドレットを使用して、メール アドレスと表示名を変更できます。</span><span class="sxs-lookup"><span data-stu-id="734cf-140">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet.</span></span> <span data-ttu-id="734cf-141">ユーザーにメールを送信するメール アドレスを変更するには、次の条件を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="734cf-141">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="734cf-142">_SendEmailFromAddress_ パラメーターにメール アドレスを入力する</span><span class="sxs-lookup"><span data-stu-id="734cf-142">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="734cf-143">_SendEmailFromDisplayName_ パラメーターにメールの表示名を入力する</span><span class="sxs-lookup"><span data-stu-id="734cf-143">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="734cf-144">_SendEmailOverride パラメーターを_ True に _設定します_。</span><span class="sxs-lookup"><span data-stu-id="734cf-144">Set the  _SendEmailOverride_ parameter to  _True_.</span></span>
    
<span data-ttu-id="734cf-145">次のコマンドを実行して、メールの送信先のメール アドレスやメールの表示名など、ユーザーに送信されたメールを変更できます。</span><span class="sxs-lookup"><span data-stu-id="734cf-145">You can make changes to the email sent to users, such as the email address that the email is sent from and the display name for the email, by running:</span></span>
  
```PowerShell
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  <span data-ttu-id="734cf-146">メール アドレス情報を変更する場合は、環境の受信メール ポリシーで、アドレスから指定されたカスタムからのメールを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="734cf-146">If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address.</span></span> <span data-ttu-id="734cf-147">[From] 連絡先情報を上書 *き* する場合は、メールがユーザーに正しく送信されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="734cf-147">If you decide to override the *From* contact information, you should verify that the emails are correctly sent to users.</span></span> <span data-ttu-id="734cf-148">これを行うには、組織内の 1 人のユーザーでこれをテストします。</span><span class="sxs-lookup"><span data-stu-id="734cf-148">You can do this by testing this with one user in your organization.</span></span>
  
<span data-ttu-id="734cf-149">会議 ID をリセットする[](/previous-versions//mt228132(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="734cf-149">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="734cf-150">メールを送信したくない場合は、どうしますか?</span><span class="sxs-lookup"><span data-stu-id="734cf-150">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="734cf-151">ユーザーへのメール送信を無効にすると、ユーザーにライセンスが割り当てられた場合でも、電子メールは送信されません。</span><span class="sxs-lookup"><span data-stu-id="734cf-151">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="734cf-152">この場合、会議 ID、既定の会議電話番号、さらに重要な点として、電話会議 PIN はユーザーに送信されません。</span><span class="sxs-lookup"><span data-stu-id="734cf-152">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="734cf-153">この場合は、ユーザーに別のメールを送信するか、ユーザーに電話で通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="734cf-153">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>
  
<span data-ttu-id="734cf-154">既定では、メールはユーザーに送信されますが、電話会議のメールを受信したくない場合は、Skype for Business 管理センターまたは Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="734cf-154">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use the Skype for Business admin center or Windows PowerShell.</span></span> 
 
<span data-ttu-id="734cf-155">![管理センターを使用Skype for Business ](../images/sfb-logo-30x30.png) **ロゴをSkype for Businessアイコン**  </span><span class="sxs-lookup"><span data-stu-id="734cf-155">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png)  **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="734cf-156">**Skype for Business 管理センター** の左側のナビゲーション ウィンドウで、[**電話会議**]  >  [**Microsoft ブリッジ設定**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="734cf-156">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="734cf-157">**[Microsoft Bridge の設定] ページ** で、[電話会議の設定が変更された場合にユーザーにメールを自動的に送信する]**をオンまたはオフにします**。</span><span class="sxs-lookup"><span data-stu-id="734cf-157">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing settings change**.</span></span> 
    
3. <span data-ttu-id="734cf-158">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="734cf-158">Click **Save**.</span></span> 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
<span data-ttu-id="734cf-159">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="734cf-159">**Using Windows PowerShell**</span></span>
  
1. <span data-ttu-id="734cf-160">次のコマンドを実行して、すべてのユーザーのメール送信を無効にします。</span><span class="sxs-lookup"><span data-stu-id="734cf-160">Run the following to disable sending all of your users email:</span></span>
    
   ```PowerShell
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

<span data-ttu-id="734cf-161">会議 ID をリセットする[](/previous-versions//mt228132(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="734cf-161">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="734cf-162">このようなメールについて知っておくべきその他のこと</span><span class="sxs-lookup"><span data-stu-id="734cf-162">What else should you know about this email?</span></span>

- <span data-ttu-id="734cf-163">ユーザーへのメールの自動送信を有効または無効にする方法の詳細については、「電話会議の設定が変更された場合にメールの送信を有効または無効にする」 [を参照してください](enable-or-disable-sending-emails-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="734cf-163">For more on enabling and disabling automatically sending email to your users, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
    
- <span data-ttu-id="734cf-164">ユーザーがオーディオ情報を失い、すべてのオーディオ情報をユーザーに送信できる必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="734cf-164">Sometimes users lose their audio information and you need to be able to send them all of their audio information to them.</span></span> <span data-ttu-id="734cf-165">これを行うには、Skype for Business 管理センターを使用し、ユーザーの電話会議プロパティの下にある [電子メールで電話会議情報を送信する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="734cf-165">You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the audio conferencing properties for a user.</span></span> <span data-ttu-id="734cf-166">「[電話会議の情報が記載された電子メールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="734cf-166">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span> <span data-ttu-id="734cf-167">ただし、この情報には電話会議 PIN は含まれます。</span><span class="sxs-lookup"><span data-stu-id="734cf-167">However, this information doesn't include the audio conferencing PIN.</span></span>
    
    <span data-ttu-id="734cf-168">送信されるこの電子メールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="734cf-168">Here is an example of this email that will be sent to them:</span></span>
    
     ![ダイヤルイン会議のメール](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="734cf-170">Windows PowerShell での管理方法について</span><span class="sxs-lookup"><span data-stu-id="734cf-170">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="734cf-171">既定では、メールの送信者は Microsoft 365 または Office 365 から送信されますが、Windows PowerShell コマンドレットと[Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10))コマンドレットを使用して、メール アドレスと表示名を変更できます。</span><span class="sxs-lookup"><span data-stu-id="734cf-171">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet.</span></span>
    
- <span data-ttu-id="734cf-172">Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。</span><span class="sxs-lookup"><span data-stu-id="734cf-172">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="734cf-173">このWindows PowerShell、1 つの管理Microsoft 365またはOffice 365を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="734cf-173">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="734cf-174">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="734cf-174">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="734cf-175">PowerShell で使用する必要があるMicrosoft 365またはOffice 365理由</span><span class="sxs-lookup"><span data-stu-id="734cf-175">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="734cf-176">[アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="734cf-176">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="734cf-177">Windows PowerShell多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターのみを使用する場合に、速度、シンプルさ、生産性に多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="734cf-177">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="734cf-178">次のトピックで、これらの利点を説明します。</span><span class="sxs-lookup"><span data-stu-id="734cf-178">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="734cf-179">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="734cf-179">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="734cf-180">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="734cf-180">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="734cf-181">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="734cf-181">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="734cf-p115">Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="734cf-p115">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="734cf-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="734cf-184">Related topics</span></span>

[<span data-ttu-id="734cf-185">電話会議の設定が変更されたときのメールの自動送信を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="734cf-185">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[<span data-ttu-id="734cf-186">電話会議の情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="734cf-186">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)
