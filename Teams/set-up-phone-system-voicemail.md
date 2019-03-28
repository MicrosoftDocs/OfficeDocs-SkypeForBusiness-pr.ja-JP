---
title: クラウドのボイスメールを設定します
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'ユーザーのクラウドのボイスメールを設定する方法について説明します。 '
ms.openlocfilehash: 8219934b8e95962f0e9ea81f4965ad9e5c55fb34
ms.sourcegitcommit: 5b33cfc828906917f76b0d2a9ae402c9336388a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30934773"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="690ca-103">クラウドのボイスメールを設定します</span><span class="sxs-lookup"><span data-stu-id="690ca-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="690ca-104">この資料では、すべてのユーザーのビジネスでのクラウドのボイスメール機能を設定する必要のある[Office 365 の管理者用](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)の。</span><span class="sxs-lookup"><span data-stu-id="690ca-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="690ca-105">クラウド ボイスメールでは、Exchange のメールボックスにのみデポジットのボイスメール メッセージをサポートし、任意のサード ・ パーティ製の電子メール システムをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="690ca-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> <span data-ttu-id="690ca-106">クラウド ボイスメールがサード ・ パーティ製の電子メール システムにメールボックスを持つユーザーがない保証されたサービスの稼働時間や変更など、他のボイスメール機能とボイスメール メッセージに表示されますが、SMTP を使用してメッセージを再送、フォールバック メカニズムとして、あいさつ文とその他の設定です。</span><span class="sxs-lookup"><span data-stu-id="690ca-106">As a fallback mechanism, Cloud Voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a><span data-ttu-id="690ca-107">クラウドのみの環境: クラウドのボイスメールを設定します</span><span class="sxs-lookup"><span data-stu-id="690ca-107">Cloud-only environments: Set up Cloud Voicemail</span></span>

<span data-ttu-id="690ca-108">オンライン ビジネスの計画を呼び出すユーザーの Skype は、クラウドのボイスメールが自動的に設定し、についてと電話番号の**電話システム**のライセンスを割り当てるには、ユーザーの準備します。</span><span class="sxs-lookup"><span data-stu-id="690ca-108">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="690ca-109">電話システム機能がプランに含まれていない場合は、 **電話システム** アドオン ライセンスの購入が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="690ca-109">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="690ca-110">Exchange Online ライセンスの購入も必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="690ca-110">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="690ca-111">[マイクロソフト チームのアドオンのライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="690ca-111">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="690ca-112">[割り当てまたはビジネス向けの Office 365 のライセンスを削除](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)、およびお客様のビジネス ユーザーに Exchange Online ライセンスです。</span><span class="sxs-lookup"><span data-stu-id="690ca-112">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="690ca-113">After you do that, they will be able to receive voicemail messages!</span><span class="sxs-lookup"><span data-stu-id="690ca-113">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="690ca-p104">ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。Windows PowerShell を使用し、下記の手順を実行することによって、所属する組織のトランスクリプションを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="690ca-p104">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="690ca-116">オンプレミス環境での電話システム</span><span class="sxs-lookup"><span data-stu-id="690ca-116">Phone System with on-premises environments</span></span>

<span data-ttu-id="690ca-117">次の情報は、設置計画を呼び出す環境で動作するクラウドのボイス メールを構成する方法です。</span><span class="sxs-lookup"><span data-stu-id="690ca-117">The following information is about configuring Cloud Voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="690ca-118">電話システム機能がプランに含まれていない場合は、 **電話システム** アドオン ライセンスの購入が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="690ca-118">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="690ca-119">Exchange Online ライセンスの購入も必要になります。</span><span class="sxs-lookup"><span data-stu-id="690ca-119">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="690ca-120">[マイクロソフト チームのアドオンのライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="690ca-120">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="690ca-121">[割り当てまたはビジネス向けの Office 365 のライセンスを削除](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)、およびお客様のビジネス ユーザーに Exchange Online ライセンスです。</span><span class="sxs-lookup"><span data-stu-id="690ca-121">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="690ca-122">[ビジネス クラウド コネクタのエディションについてを構成する Skype](https://technet.microsoft.com/library/mt605228.aspx)の**電話システムの音声とボイスメール サービスのユーザーを有効にする**] セクションの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="690ca-122">Follow the instructions in the **Enable users for Phone System voice and voicemail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span>

4. <span data-ttu-id="690ca-p106">ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。Windows PowerShell を使用し、下記の手順を実行することによって、所属する組織のトランスクリプションを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="690ca-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="690ca-125">オンプレミスのメールボックスを持つ電話システム ユーザーのために Azure ボイスメール メッセージの配信を構成する方法については、「[Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/kb/3195158)」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="690ca-125">You can also see [Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/kb/3195158) to learn how to configure delivery of Azure voicemail messages for Phone System users who have a on-premises mailboxes.</span></span>

6. <span data-ttu-id="690ca-126">参照してください次のドキュメントに記載されている手順に従います:[ハイブリッド構成ウィザード](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)</span><span class="sxs-lookup"><span data-stu-id="690ca-126">Please also read and follow the steps outlined in the following document: [Hybrid Configuration wizard](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)</span></span>

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="690ca-127">組織内のボイスメール ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="690ca-127">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="690ca-128">既定では、すべての組織とユーザーに対して、ボイスメール トランスクリプションは有効に、トランスクリプション不適切表現マスキングは無効になっています。ただし、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) と [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) コマンドレットを使用してそれらを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="690ca-128">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="690ca-129">議事録と議事録の不適切な**新しい CsOnlineVoiceMailPolicy**コマンドレットを使用してマスクの新しいポリシー インスタンスを作成することはできません。 し、**削除 CsOnlineVoiceMailPolicy**コマンドレットを使用して、既存のポリシーのインスタンスを削除することはできません。.</span><span class="sxs-lookup"><span data-stu-id="690ca-129">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="690ca-130">ボイスメール ポリシーを使用してユーザーのトランスクリプション設定を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="690ca-130">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="690ca-131">すべての利用可能なボイスメール ポリシーのインスタンスを表示するには、 [Get CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx)コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="690ca-131">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="690ca-132">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="690ca-132">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="690ca-134">組織のトランスクリプションをオフにする</span><span class="sxs-lookup"><span data-stu-id="690ca-134">Turning off transcription for your organization</span></span>

<span data-ttu-id="690ca-p108">組織のトランスクリプションに関する既定の設定はオンになっており、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) を使用して無効にすることができます。これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="690ca-p108">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="690ca-137">組織のトランスクリプション不適切表現マスキングをオンにする。</span><span class="sxs-lookup"><span data-stu-id="690ca-137">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="690ca-138">組織では、トランスクリプション不適切表現マスキングは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="690ca-138">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="690ca-139">マスキングを有効にしなければならないビジネス上の要件がある場合は、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) を使用してトランスクリプション不適切表現マスキングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="690ca-139">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="690ca-140">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="690ca-140">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="690ca-141">ユーザーのトランスクリプションをオフにする</span><span class="sxs-lookup"><span data-stu-id="690ca-141">Turning off transcription for a user</span></span>

<span data-ttu-id="690ca-142">ユーザー ポリシーは組織の既定の設定より前に評価されます。</span><span class="sxs-lookup"><span data-stu-id="690ca-142">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="690ca-143">などのすべてのユーザーは、ボイスメールの議事録が有効である場合は、[許可 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx)コマンドレットを使用して特定のユーザーの議事録作成を無効にするポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="690ca-143">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="690ca-144">単一ユーザーに対するトランスクリプションを無効にするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="690ca-144">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="690ca-145">ユーザーのトランスクリプション不適切表現マスキングをオンにします。</span><span class="sxs-lookup"><span data-stu-id="690ca-145">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="690ca-146">特定のユーザーに対してトランスクリプション不適切表現マスキングを有効にするには、ポリシーを割り当てて、[Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) コマンドレットを使用して特定のユーザーに対するトランスクリプション不適切表現マスキングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="690ca-146">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="690ca-147">単一ユーザーに対するトランスクリプション不適切表現マスキングを有効にするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="690ca-147">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="690ca-p111">Office 365 のボイスメール サービスによってボイスメール ポリシーがキャッシュされ、4 時間ごとにキャッシュが更新されます。このため、ポリシーを変更した場合、変更が適用されるまでに最長で 4 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="690ca-p111">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="690ca-150">Skype for Business ボイスメールの機能に関するユーザーの理解を支援する</span><span class="sxs-lookup"><span data-stu-id="690ca-150">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="690ca-p112">ユーザーが Skype for Business ボイスメールを正しく使用できるように支援するためのトレーニング情報と記事が用意されています。以下の記事をユーザーに紹介してください。</span><span class="sxs-lookup"><span data-stu-id="690ca-p112">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>

- <span data-ttu-id="690ca-153">[Skype for Business ボイス メールの確認とオプション](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): この記事では、Skype for Business でボイスメールを再生し、ボイスメール応答メッセージを変更し、ボイスメールの設定を変更し、ボイスメールを異なる速度で再生する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="690ca-153">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="690ca-154">Skype for Business 2016 トレーニング</span><span class="sxs-lookup"><span data-stu-id="690ca-154">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="690ca-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="690ca-155">Related topics</span></span>
[<span data-ttu-id="690ca-156">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="690ca-156">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="690ca-157">Office 365 での電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="690ca-157">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)


