---
title: クラウド ボイスメールのセットアップ
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
ms.openlocfilehash: a4d992ac4f42dca1bffe7a4c3d7ae01400b8e635
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865007"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="c677e-103">クラウド ボイスメールのセットアップ</span><span class="sxs-lookup"><span data-stu-id="c677e-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="c677e-104">この資料では、すべてのユーザーのビジネスでのクラウドのボイスメール機能を設定する必要のある[Office 365 の管理者用](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)の。</span><span class="sxs-lookup"><span data-stu-id="c677e-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="c677e-105">クラウド ボイスメールでは、Exchange のメールボックスにのみデポジットのボイスメール メッセージをサポートし、任意のサード ・ パーティ製の電子メール システムをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c677e-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a><span data-ttu-id="c677e-106">クラウドのみの環境: クラウドのボイスメールを設定します</span><span class="sxs-lookup"><span data-stu-id="c677e-106">Cloud-only environments: Set up Cloud Voicemail</span></span>

<span data-ttu-id="c677e-107">オンライン ビジネスの計画を呼び出すユーザーの Skype は、クラウドのボイスメールが自動的に設定し、についてと電話番号の**電話システム**のライセンスを割り当てるには、ユーザーの準備します。</span><span class="sxs-lookup"><span data-stu-id="c677e-107">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="c677e-108">電話システム機能がプランに含まれていない場合は、 **電話システム** アドオン ライセンスの購入が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="c677e-108">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="c677e-109">Exchange Online ライセンスの購入も必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c677e-109">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="c677e-110">[マイクロソフト チームのアドオンのライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c677e-110">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="c677e-111">[割り当てまたはビジネス向けの Office 365 のライセンスを削除](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)、およびお客様のビジネス ユーザーに Exchange Online ライセンスです。</span><span class="sxs-lookup"><span data-stu-id="c677e-111">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="c677e-112">これが完了すると、メンバーはボイスメール メッセージを受信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c677e-112">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="c677e-p103">ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。Windows PowerShell を使用し、下記の手順を実行することによって、所属する組織のトランスクリプションを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c677e-p103">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="c677e-115">オンプレミス環境での電話システム</span><span class="sxs-lookup"><span data-stu-id="c677e-115">Phone System with on-premises environments</span></span>

<span data-ttu-id="c677e-116">次の情報は、設置計画を呼び出す環境で動作するクラウドのボイス メールを構成する方法です。</span><span class="sxs-lookup"><span data-stu-id="c677e-116">The following information is about configuring Cloud Voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="c677e-117">電話システム機能がプランに含まれていない場合は、 **電話システム** アドオン ライセンスの購入が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="c677e-117">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="c677e-118">Exchange Online ライセンスの購入も必要になります。</span><span class="sxs-lookup"><span data-stu-id="c677e-118">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="c677e-119">[マイクロソフト チームのアドオンのライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c677e-119">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="c677e-120">[割り当てまたはビジネス向けの Office 365 のライセンスを削除](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)、およびお客様のビジネス ユーザーに Exchange Online ライセンスです。</span><span class="sxs-lookup"><span data-stu-id="c677e-120">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="c677e-121">設置 PSTN のユーザーに展開するソリューションの呼び出しに一致する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c677e-121">Follow instructions matching on-premises PSTN calling solution deployed for your users.</span></span> <span data-ttu-id="c677e-122">クラウド コネクタのエディションの[ビジネス クラウド コネクタのエディションについてを構成する Skype](https://technet.microsoft.com/library/mt605228.aspx)の**電話システムの音声とボイスメール サービスのユーザーを有効にする**セクション内の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="c677e-122">For Cloud Connector Edition, follow instructions in the **Enable users for Phone System voice and voicemail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span> <span data-ttu-id="c677e-123">Skype でビジネスのサーバーの呼び出しの PSTN、[設置型のエンタープライズ VoIP に対してユーザーを有効にする](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises)に従ってください。</span><span class="sxs-lookup"><span data-stu-id="c677e-123">For PSTN calling with Skype for Business Server, follow [Enable the users for Enterprise Voice on premises](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span></span> <span data-ttu-id="c677e-124">チーム直接ルーティングでは、[直接ルーティングを構成する](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)の**と電話番号の構成と有効にするエンタープライズ ボイス ボイスメール**のセクションに従ってください。</span><span class="sxs-lookup"><span data-stu-id="c677e-124">For Teams Direct Routing, follow  the **Configure the phone number and enable enterprise voice and voicemail** section of [Configure Direct Routing](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span></span>

4. <span data-ttu-id="c677e-p106">ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。Windows PowerShell を使用し、下記の手順を実行することによって、所属する組織のトランスクリプションを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c677e-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="c677e-127">ボイスメール メッセージは、Exchange のオンライン保護を経由してルーティングする SMTP 経由でのユーザーの Exchange メールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="c677e-127">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="c677e-128">これらのメッセージが正常に配信を有効にするには、Exchange コネクタは、Exchange サーバーと Exchange のオンライン保護との間に正しく構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c677e-128">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection.</span></span> <span data-ttu-id="c677e-129">[メール フローを構成するコネクタを使用](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)します。</span><span class="sxs-lookup"><span data-stu-id="c677e-129">[Use Connectors to Configure Mail Flow](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

6. <span data-ttu-id="c677e-130">ビジネス クライアント用のあいさつ文や、Skype でボイスメールをビジュアルのカスタマイズなど、ボイスメールの機能を有効にするには、Office 365 から Exchange Web サービス経由で Exchange サーバーのメールボックスに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c677e-130">To enable Voicemail features such as customizing greetings, and visual voicemail in Skype for Business clients, connectivity from Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="c677e-131">この接続を有効にするのには、 [Exchange および Exchange Online 組織間で認証を構成する OAuth](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)の認証プロトコルについて説明する新しい Exchange の Oauth を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c677e-131">To enable this connectivity you must configure the new Exchange Oauth authentication protocol describe in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)</span></span> 

> [!NOTE]
> <span data-ttu-id="c677e-132">Exchange 2013 CU5 から実行またはそれ以上の Exchange ハイブリッドのウィザードは、手順 5 と 6 の要件を自動的に処理します。</span><span class="sxs-lookup"><span data-stu-id="c677e-132">The Exchange Hybrid Wizard run from Exchange 2013 CU5 or greater will handle the requirements in steps 5 and 6 automatically.</span></span> 

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="c677e-133">組織内のボイスメール ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="c677e-133">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="c677e-134">お客様の Skype は、マイクロソフトのチームがポリシーを呼び出すことによってボイス メールを無効にする可能性がありますも無効にするビジネス ユーザー向けに、Skype のボイスメール サービス。</span><span class="sxs-lookup"><span data-stu-id="c677e-134">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="c677e-135">既定では、すべての組織とユーザーに対して、ボイスメール トランスクリプションは有効に、トランスクリプション不適切表現マスキングは無効になっています。ただし、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) と [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) コマンドレットを使用してそれらを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="c677e-135">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c677e-136">議事録と議事録の不適切な**新しい CsOnlineVoiceMailPolicy**コマンドレットを使用してマスクの新しいポリシー インスタンスを作成することはできません。 し、**削除 CsOnlineVoiceMailPolicy**コマンドレットを使用して、既存のポリシーのインスタンスを削除することはできません。.</span><span class="sxs-lookup"><span data-stu-id="c677e-136">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="c677e-137">ボイスメール ポリシーを使用してユーザーのトランスクリプション設定を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="c677e-137">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="c677e-138">すべての利用可能なボイスメール ポリシーのインスタンスを表示するには、 [Get CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx)コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="c677e-138">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="c677e-139">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="c677e-139">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="c677e-141">組織のトランスクリプションをオフにする</span><span class="sxs-lookup"><span data-stu-id="c677e-141">Turning off transcription for your organization</span></span>

<span data-ttu-id="c677e-p110">組織のトランスクリプションに関する既定の設定はオンになっており、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) を使用して無効にすることができます。これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c677e-p110">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="c677e-144">組織のトランスクリプション不適切表現マスキングをオンにする。</span><span class="sxs-lookup"><span data-stu-id="c677e-144">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="c677e-145">組織では、トランスクリプション不適切表現マスキングは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="c677e-145">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="c677e-146">マスキングを有効にしなければならないビジネス上の要件がある場合は、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) を使用してトランスクリプション不適切表現マスキングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c677e-146">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="c677e-147">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c677e-147">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="c677e-148">ユーザーのトランスクリプションをオフにする</span><span class="sxs-lookup"><span data-stu-id="c677e-148">Turning off transcription for a user</span></span>

<span data-ttu-id="c677e-149">ユーザー ポリシーは組織の既定の設定より前に評価されます。</span><span class="sxs-lookup"><span data-stu-id="c677e-149">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="c677e-150">などのすべてのユーザーは、ボイスメールの議事録が有効である場合は、[許可 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx)コマンドレットを使用して特定のユーザーの議事録作成を無効にするポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c677e-150">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="c677e-151">単一ユーザーに対するトランスクリプションを無効にするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c677e-151">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="c677e-152">ユーザーのトランスクリプション不適切表現マスキングをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c677e-152">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="c677e-153">特定のユーザーに対してトランスクリプション不適切表現マスキングを有効にするには、ポリシーを割り当てて、[Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) コマンドレットを使用して特定のユーザーに対するトランスクリプション不適切表現マスキングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c677e-153">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="c677e-154">単一ユーザーに対するトランスクリプション不適切表現マスキングを有効にするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c677e-154">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="c677e-p113">Office 365 のボイスメール サービスによってボイスメール ポリシーがキャッシュされ、4 時間ごとにキャッシュが更新されます。このため、ポリシーを変更した場合、変更が適用されるまでに最長で 4 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c677e-p113">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="c677e-157">Skype for Business ボイスメールの機能に関するユーザーの理解を支援する</span><span class="sxs-lookup"><span data-stu-id="c677e-157">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="c677e-p114">ユーザーが Skype for Business ボイスメールを正しく使用できるように支援するためのトレーニング情報と記事が用意されています。以下の記事をユーザーに紹介してください。</span><span class="sxs-lookup"><span data-stu-id="c677e-p114">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>

- <span data-ttu-id="c677e-160">[Skype for Business ボイス メールの確認とオプション](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): この記事では、Skype for Business でボイスメールを再生し、ボイスメール応答メッセージを変更し、ボイスメールの設定を変更し、ボイスメールを異なる速度で再生する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c677e-160">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="c677e-161">Skype for Business 2016 トレーニング</span><span class="sxs-lookup"><span data-stu-id="c677e-161">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="c677e-162">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c677e-162">Related topics</span></span>
[<span data-ttu-id="c677e-163">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="c677e-163">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="c677e-164">Office 365 での電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="c677e-164">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="c677e-165">Skype for Business Server と Exchange Server の移行の計画</span><span class="sxs-lookup"><span data-stu-id="c677e-165">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/plan-um-migration)


