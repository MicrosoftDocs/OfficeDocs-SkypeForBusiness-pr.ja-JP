---
title: 電話システム ボイスメールをセットアップする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. '
ms.openlocfilehash: f5dcf6012dc9ac6659d35c29a31ee6a5ff40eec2
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "22135532"
---
# <a name="set-up-phone-system-voicemail"></a><span data-ttu-id="fd2bc-103">電話システム ボイスメールをセットアップする</span><span class="sxs-lookup"><span data-stu-id="fd2bc-103">Set up Phone System voicemail</span></span>

<span data-ttu-id="fd2bc-104">この資料では、 [Office 365 の管理者用](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)ビジネスでのすべてのユーザーの電話システム ボイスメール機能を設定したいのです。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-104">This article is for the [Office 365 admin](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Phone System voicemail feature for everyone in the business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fd2bc-p101">電話システム ボイスメールでは、ボイスメール メッセージの預かりで Exchange メールボックスのみをサポートし、サードパーティーの電子メール システムはサポートしません。フォールバック メカニズムとして、電話システム ボイスメールでは SMTP を使用してメッセージを再送信できます。このため、サードパーティーの電子メール システムのメールボックスを使っているユーザーは、受信するボイスメール メッセージでサービスの稼働時間が保証されたり、挨拶文やその他の設定の変更などのその他のボイスメール機能が提供されたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-p101">Phone System voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems. As a fallback mechanism, Phone System voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings.</span></span> 
  
## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a><span data-ttu-id="fd2bc-107">クラウドのみの環境: 電話システム ボイスメールのセットアップ</span><span class="sxs-lookup"><span data-stu-id="fd2bc-107">Cloud-only environments: Set up Phone System voicemail</span></span>

<span data-ttu-id="fd2bc-108">Skype for Business Online および通話プランのユーザーには電話システム ボイスメールが自動的にセットアップされ、ユーザーに **電話システム** ライセンスと電話番号を割り当てるとプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-108">For Skype for Business Online and Calling Plans users, Phone System voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="fd2bc-109">電話システム機能がプランに含まれていない場合は、 **電話システム** アドオン ライセンスの購入が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-109">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="fd2bc-110">Exchange Online ライセンスの購入も必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-110">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="fd2bc-111">[Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-111">See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="fd2bc-p103">[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[Skype for Business と Microsoft Teams のライセンスを割り当てる](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)、および Exchange Online ライセンスを組織のメンバーに割り当てます。これが完了すると、メンバーはボイスメール メッセージを受信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-p103">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), and the Exchange Online licenses to the people in your business. After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="fd2bc-p104">ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。Windows PowerShell を使用し、下記の手順を実行することによって、所属する組織のトランスクリプションを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-p104">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>
    
## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="fd2bc-116">オンプレミス環境での電話システム</span><span class="sxs-lookup"><span data-stu-id="fd2bc-116">Phone System with on-premises environments</span></span>

<span data-ttu-id="fd2bc-117">電話システム ボイスメールをオンプレミスの通話プラン環境で動作させる設定に関する情報は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-117">The following information is about configuring Phone System voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="fd2bc-118">電話システム機能がプランに含まれていない場合は、 **電話システム** アドオン ライセンスの購入が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-118">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="fd2bc-119">Exchange Online ライセンスの購入も必要になります。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-119">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="fd2bc-120">[Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-120">See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="fd2bc-121">[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[Skype for Business と Microsoft Teams のライセンスを割り当てる](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)、および Exchange Online ライセンスを組織のユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-121">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="fd2bc-122">[ビジネス クラウド コネクタのエディションについてを構成する Skype](https://technet.microsoft.com/en-us/library/mt605228.aspx)の**ユーザーの電話システムの音声と音声メール サービスを有効にする**] セクションの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-122">Follow the instructions in the **Enable users for Phone System voice and voice mail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span></span>
    
4. <span data-ttu-id="fd2bc-p106">ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。Windows PowerShell を使用し、下記の手順を実行することによって、所属する組織のトランスクリプションを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span> 
    
5. <span data-ttu-id="fd2bc-125">オンプレミスのメールボックスを持つ電話システム ユーザーのために Azure ボイスメール メッセージの配信を構成する方法については、「[Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/en-us/kb/3195158)」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-125">You can also see [Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/en-us/kb/3195158) to learn how to configure delivery of Azure voicemail messages for Phone System users who have a on-premises mailboxes.</span></span>
    
## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="fd2bc-126">組織内のボイスメール ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="fd2bc-126">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="fd2bc-127">ボイスメールの議事録が既定で有効にして、すべての組織とユーザーの既定での議事録の不適切なマスキングが無効になっています。ただし、[セット CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx)と[与える CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx)コマンドレットを使用して、それらを制御できます。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-127">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) cmdlets.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fd2bc-128">議事録と議事録の不適切な**新しい CsOnlineVoiceMailPolicy**コマンドレットを使用してマスクの新しいポリシー インスタンスを作成することはできません。 し、**削除 CsOnlineVoiceMailPolicy**コマンドレットを使用して、既存のポリシーのインスタンスを削除することはできません。.</span><span class="sxs-lookup"><span data-stu-id="fd2bc-128">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>
  
<span data-ttu-id="fd2bc-129">ボイスメール ポリシーを使用してユーザーのトランスクリプション設定を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-129">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="fd2bc-130">すべての利用可能なボイスメール ポリシーのインスタンスを表示するには、 [Get CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx)コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-130">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>
  
 <span data-ttu-id="fd2bc-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="fd2bc-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="fd2bc-133">組織のトランスクリプションをオフにする</span><span class="sxs-lookup"><span data-stu-id="fd2bc-133">Turning off transcription for your organization</span></span>

<span data-ttu-id="fd2bc-p108">組織のトランスクリプションに関する既定の設定はオンになっており、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) を使用して無効にすることができます。これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-p108">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). To do this, run:</span></span>
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="fd2bc-136">組織の議事録の不適切なマスキングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-136">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="fd2bc-137">組織の既定での議事録の不適切なマスキングが無効です。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-137">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="fd2bc-138">有効にするというビジネス要件がある場合は、議事録の不適切な[設定 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx)を使用して、マスキングを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-138">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span></span> <span data-ttu-id="fd2bc-139">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-139">To do this, run:</span></span>
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="fd2bc-140">ユーザーのトランスクリプションをオフにする</span><span class="sxs-lookup"><span data-stu-id="fd2bc-140">Turning off transcription for a user</span></span>

<span data-ttu-id="fd2bc-141">ユーザー ポリシーは組織の既定の設定より前に評価されます。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-141">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="fd2bc-142">などのすべてのユーザーは、ボイスメールの議事録が有効である場合は、[許可 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx)コマンドレットを使用して特定のユーザーの議事録作成を無効にするポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-142">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>
  
<span data-ttu-id="fd2bc-143">単一ユーザーに対するトランスクリプションを無効にするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-143">To disable transcription for a single user, run:</span></span>
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="fd2bc-144">ユーザーの議事録の不適切なマスキングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-144">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="fd2bc-145">議事録の不適切な特定のユーザーのマスキングを有効にするには、議事録の不適切な[補助金 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx)コマンドレットを使用して特定のユーザーのマスキングを有効にするポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-145">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) cmdlet.</span></span>
  
<span data-ttu-id="fd2bc-146">議事録の不適切な単一のユーザー用のマスキングを有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-146">To enable transcription profanity masking for a single user, run:</span></span>
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="fd2bc-p111">Office 365 のボイスメール サービスによってボイスメール ポリシーがキャッシュされ、4 時間ごとにキャッシュが更新されます。このため、ポリシーを変更した場合、変更が適用されるまでに最長で 4 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-p111">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span> 
  
## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="fd2bc-149">Skype for Business ボイスメールの機能に関するユーザーの理解を支援する</span><span class="sxs-lookup"><span data-stu-id="fd2bc-149">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="fd2bc-p112">ユーザーが Skype for Business ボイスメールを正しく使用できるように支援するためのトレーニング情報と記事が用意されています。以下の記事をユーザーに紹介してください。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-p112">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>
  
- <span data-ttu-id="fd2bc-152">[Skype for Business ボイス メールの確認とオプション](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): この記事では、Skype for Business でボイスメールを再生し、ボイスメール応答メッセージを変更し、ボイスメールの設定を変更し、ボイスメールを異なる速度で再生する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fd2bc-152">[Check Skype for Business voicemail and options](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>
    
- [<span data-ttu-id="fd2bc-153">Skype for Business 2016 トレーニング</span><span class="sxs-lookup"><span data-stu-id="fd2bc-153">Skype for Business 2016 training</span></span>](http://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## <a name="related-topics"></a><span data-ttu-id="fd2bc-154">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fd2bc-154">Related topics</span></span>
[<span data-ttu-id="fd2bc-155">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="fd2bc-155">Set up Skype for Business Online</span></span>](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[<span data-ttu-id="fd2bc-156">Office 365 での電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="fd2bc-156">Here's what you get with Phone System in Office 365</span></span>](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)

  
 