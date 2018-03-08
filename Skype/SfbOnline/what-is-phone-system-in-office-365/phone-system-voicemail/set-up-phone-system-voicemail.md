---
title: "電話システムでボイス メールを設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: "Skype for Business のユーザーの電話システム (クラウド PBX) ボイス メールを設定する方法について説明します。 "
ms.openlocfilehash: 2db9325b48bf84c1fc44adbfa1097a3eddd55f9b
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-up-phone-system-voicemail"></a><span data-ttu-id="e00c8-103">電話システムでボイス メールを設定します。</span><span class="sxs-lookup"><span data-stu-id="e00c8-103">Set up Phone System voicemail</span></span>

<span data-ttu-id="e00c8-104">この記事では、 [Office 365 管理者](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)向け会社のすべてのユーザーに対して、電話システムでボイス メール機能を設定したいです。</span><span class="sxs-lookup"><span data-stu-id="e00c8-104">This article is for the [Office 365 admin](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Phone System voicemail feature for everyone in the business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e00c8-p101">電話システムのボイス メールでは、Exchange メールボックスでのみデポジット ボイス メール メッセージをサポートし、任意のサード パーティのメール システムをサポートしていません。電話システムでボイス メール、代替メカニズムとしてなし保証されたサービスの稼働時間の変更など、その他のボイスメール機能とボイス メール メッセージを受信するサード パーティのメール システムにメールボックスを持つユーザーは、SMTP を使用してメッセージを再送信できます。あいさつのその他の設定します。</span><span class="sxs-lookup"><span data-stu-id="e00c8-p101">Phone System voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems. As a fallback mechanism, Phone System voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings.</span></span> 
  
## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a><span data-ttu-id="e00c8-107">クラウドのみが混在する環境: 電話システムでボイス メールを設定します。</span><span class="sxs-lookup"><span data-stu-id="e00c8-107">Cloud-only environments: Set up Phone System voicemail</span></span>

<span data-ttu-id="e00c8-108">Skype for Business Online とプランの呼び出しのユーザーには、電話システムでボイス メールが自動的にセットアップと電話番号の**電話システムで**のライセンスの割り当て後に、ユーザーのプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="e00c8-108">For Skype for Business Online and Calling Plans users, Phone System voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="e00c8-p102">電話システムでこの機能は、現在のプランに含まれていない場合、は、**電話システムで**アドオン ライセンスを購入する必要があります。Exchange Online のライセンスを購入する必要もあります。[Skype for Business や Microsoft チーム アドオンのライセンス](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e00c8-p102">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses. You may also need to purchase an Exchange Online license. See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="e00c8-p103">[割り当てたり一般法人向け Office 365 のライセンスを削除する](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)とビジネスでのユーザーに Exchange Online ライセンスします。後、ボイス メール メッセージを受信できるようにれます。</span><span class="sxs-lookup"><span data-stu-id="e00c8-p103">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), and the Exchange Online licenses to the people in your business. After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="e00c8-p104">ボイス メールのトラン スクリプトのサポートは、2017年 3 月におけるが追加されているし、すべての組織とユーザーに対する既定で有効にします。Windows PowerShell を使用して、次の手順に従うと、組織のトラン スクリプトを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="e00c8-p104">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>
    
## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="e00c8-116">オンプレミス環境との電話システム</span><span class="sxs-lookup"><span data-stu-id="e00c8-116">Phone System with on-premises environments</span></span>

<span data-ttu-id="e00c8-117">社内環境の計画の呼び出しを操作する電話システムでボイス メールの構成については、次の情報です。</span><span class="sxs-lookup"><span data-stu-id="e00c8-117">The following information is about configuring Phone System voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="e00c8-p105">電話システムでこの機能は、現在のプランに含まれていない場合、は、**電話システムで**アドオン ライセンスを購入する必要があります。Exchange Online のライセンスを購入する必要があります。[Skype for Business や Microsoft チーム アドオンのライセンス](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e00c8-p105">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses. You also need to purchase an Exchange Online license. See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="e00c8-121">[割り当てたり一般法人向け Office 365 のライセンスを削除する](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)とビジネスでのユーザーに Exchange Online ライセンスします。</span><span class="sxs-lookup"><span data-stu-id="e00c8-121">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="e00c8-122">**ユーザーの電話システムでの音声とボイス メールのサービスを有効にする** [Skype for Business クラウド コネクタ Edition ガイドを構成する](https://technet.microsoft.com/en-us/library/mt605228.aspx)セクションの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="e00c8-122">Follow the instructions in the **Enable users for Phone System voice and voice mail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span></span>
    
4. <span data-ttu-id="e00c8-p106">ボイス メールのトラン スクリプトのサポートは、2017年 3 月におけるが追加されているし、すべての組織とユーザーに対する既定で有効にします。Windows PowerShell を使用して、次の手順に従うと、組織のトラン スクリプトを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="e00c8-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span> 
    
5. <span data-ttu-id="e00c8-125">電話システムでユーザーをオンプレミスのメールボックスに対して Azure ボイス メール メッセージの配信を構成する方法については、 [Exchange Server のサポート Azure PBX ボイス メール](https://support.microsoft.com/en-us/kb/3195158)を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="e00c8-125">You can also see [Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/en-us/kb/3195158) to learn how to configure delivery of Azure voicemail messages for Phone System users who have a on-premises mailboxes.</span></span>
    
## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="e00c8-126">組織のボイスメール ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="e00c8-126">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="e00c8-127">既定ではすべての組織とユーザーのボイス メールのトラン スクリプトが有効になっています。ただし、[セット CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx)と[許可を付与する CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx)コマンドレットを使用して制御できます。</span><span class="sxs-lookup"><span data-stu-id="e00c8-127">Voicemail transcription is enabled by default for all organizations and users; however, you can control it by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) cmdlets.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e00c8-128">**新規 CsOnlineVoiceMailPolicy**コマンドレットを使用して議事録を新しいポリシー インスタンスを作成することはできず、**削除 CsOnlineVoiceMailPolicy**コマンドレットを使用して、既存のポリシーのインスタンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="e00c8-128">You can't create a new policy instance for transcription using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>
  
<span data-ttu-id="e00c8-p107">ボイス メールのポリシーを使用して、ユーザーのトラン スクリプトの設定を管理できます。ボイス メールが利用可能なポリシーのすべてのインスタンスを表示するには、 [Get CsOnlineVoicemailPolicy](https://technet.microsoft.com/en-us/library/mt798311.aspx)コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e00c8-p107">You can manage the transcription settings for your users using voicemail policies. To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/en-us/library/mt798311.aspx) cmdlet.</span></span>
  
 <span data-ttu-id="e00c8-131">**\\> Get CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="e00c8-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get CsOnlineVoiceMailPolicy 結果] ウィンドウ。](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="e00c8-133">組織のトラン スクリプトを無効にします。</span><span class="sxs-lookup"><span data-stu-id="e00c8-133">Turning off transcription for your organization</span></span>

<span data-ttu-id="e00c8-p108">既定のトラン スクリプト上にあるため、組織の[設定 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx)で無効にすることです。これを行うには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e00c8-p108">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). To do this, run:</span></span>
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="e00c8-136">ユーザーのトラン スクリプトを無効にします。</span><span class="sxs-lookup"><span data-stu-id="e00c8-136">Turning off transcription for a user</span></span>

<span data-ttu-id="e00c8-p109">ユーザー ポリシーは、組織の既定の設定をする前に評価されます。たとえば、すべてのユーザーのボイス メールのトラン スクリプトが有効な場合は、[許可を付与する CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx)コマンドレットを使用して特定のユーザーのトラン スクリプトを無効にするポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e00c8-p109">User policies are evaluated before the organizational default settings. For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) cmdlet.</span></span>
  
<span data-ttu-id="e00c8-139">1 人のユーザーのトラン スクリプトを無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e00c8-139">To disable transcription for a single user, run:</span></span>
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="e00c8-p110">Office 365 でボイス メール サービスでは、ボイス メールのポリシーをキャッシュし、4 時間ごとにキャッシュを更新します。したがって、ポリシーの変更を行うを適用する最大 4 時間がかかる場合ことができます。</span><span class="sxs-lookup"><span data-stu-id="e00c8-p110">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span> 
  
## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="e00c8-142">Skype をビジネス ボイスメール機能について説明しやすくします。</span><span class="sxs-lookup"><span data-stu-id="e00c8-142">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="e00c8-p111">トレーニング情報やビジネス ボイスメール Skype に成功するユーザーのために記事があります。対象とする、次の記事。</span><span class="sxs-lookup"><span data-stu-id="e00c8-p111">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>
  
- <span data-ttu-id="e00c8-145">[Skype for Business ボイス メールとオプションにチェック](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Skype for Business でボイス メールを聞く、ボイス メールのあいさつ文を変更する、ボイス メールの設定を変更、および速度が異なるボイス メールを聞く方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="e00c8-145">[Check Skype for Business voicemail and options](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>
    
- [<span data-ttu-id="e00c8-146">Skype for Business 2016 のトレーニング</span><span class="sxs-lookup"><span data-stu-id="e00c8-146">Skype for Business 2016 training</span></span>](http://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## <a name="related-topics"></a><span data-ttu-id="e00c8-147">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e00c8-147">Related topics</span></span>
[<span data-ttu-id="e00c8-148">Skype for Business Online をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="e00c8-148">Set up Skype for Business Online</span></span>](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[<span data-ttu-id="e00c8-149">ここではされた電話システムで Office 365 での表示</span><span class="sxs-lookup"><span data-stu-id="e00c8-149">Here's what you get with Phone System in Office 365</span></span>](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)
