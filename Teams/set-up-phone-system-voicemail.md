---
title: クラウド ボイスメールのセットアップ
author: dstrome
ms.author: dstrome
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'ユーザーにクラウドボイスメールをセットアップする方法について説明します。 '
ms.openlocfilehash: bff4de7ed77ae7168e6daacf258e73dbc17a736a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298672"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="818c3-103">クラウド ボイスメールのセットアップ</span><span class="sxs-lookup"><span data-stu-id="818c3-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="818c3-104">この記事は、社内のすべてのユーザーにクラウドボイスメール機能を設定する必要がある[Office 365 管理者](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)を対象としています。</span><span class="sxs-lookup"><span data-stu-id="818c3-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="818c3-105">クラウドボイスメールでは、Exchange メールボックスでのボイスメールメッセージのデポジットのみがサポートされ、サードパーティのメールシステムはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="818c3-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a><span data-ttu-id="818c3-106">クラウドのみの環境: クラウドボイスメールをセットアップする</span><span class="sxs-lookup"><span data-stu-id="818c3-106">Cloud-only environments: Set up Cloud Voicemail</span></span>

<span data-ttu-id="818c3-107">Skype for Business Online と通話プランのユーザーには、**電話システム**のライセンスと電話番号を割り当てた後で、クラウドボイスメールが自動的に設定され、ユーザーに提供されます。</span><span class="sxs-lookup"><span data-stu-id="818c3-107">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="818c3-108">電話システム機能がプランに含まれていない場合は、 **電話システム** アドオン ライセンスの購入が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="818c3-108">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="818c3-109">Exchange Online ライセンスの購入も必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="818c3-109">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="818c3-110">「 [Microsoft Teams のアドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="818c3-110">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="818c3-111">一般[法人向け Office 365 のライセンスの割り当てまたは削除](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、 [Microsoft Teams ライセンスの割り当て](assign-teams-licenses.md)、および組織内のユーザーへの Exchange Online ライセンスの割り当てまたは削除を行います。</span><span class="sxs-lookup"><span data-stu-id="818c3-111">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="818c3-112">これが完了すると、メンバーはボイスメール メッセージを受信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="818c3-112">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="818c3-p103">ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。Windows PowerShell を使用し、下記の手順を実行することによって、所属する組織のトランスクリプションを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="818c3-p103">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="818c3-115">オンプレミス環境での電話システム</span><span class="sxs-lookup"><span data-stu-id="818c3-115">Phone System with on-premises environments</span></span>

<span data-ttu-id="818c3-116">次の情報は、オンプレミスの通話プラン環境で動作するようにクラウドボイスメールを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="818c3-116">The following information is about configuring Cloud Voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="818c3-117">電話システム機能がプランに含まれていない場合は、 **電話システム** アドオン ライセンスの購入が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="818c3-117">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="818c3-118">Exchange Online ライセンスの購入も必要になります。</span><span class="sxs-lookup"><span data-stu-id="818c3-118">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="818c3-119">「 [Microsoft Teams のアドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="818c3-119">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="818c3-120">一般[法人向け Office 365 のライセンスの割り当てまたは削除](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、 [Microsoft Teams ライセンスの割り当て](assign-teams-licenses.md)、および組織内のユーザーへの Exchange Online ライセンスの割り当てまたは削除を行います。</span><span class="sxs-lookup"><span data-stu-id="818c3-120">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="818c3-121">ユーザーに展開されているオンプレミス PSTN 通話ソリューションと一致する指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="818c3-121">Follow instructions matching on-premises PSTN calling solution deployed for your users.</span></span> <span data-ttu-id="818c3-122">Cloud Connector Edition の場合は、「 [Skype For Business Cloud Connector エディションの構成](https://technet.microsoft.com/library/mt605228.aspx)」の「**電話システムの音声およびボイスメールサービスのユーザーを有効にする**」セクションの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="818c3-122">For Cloud Connector Edition, follow instructions in the **Enable users for Phone System voice and voicemail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span> <span data-ttu-id="818c3-123">Skype for Business Server での PSTN 通話については、「[エンタープライズボイスオンプレミスのユーザーを有効にする](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="818c3-123">For PSTN calling with Skype for Business Server, follow [Enable the users for Enterprise Voice on premises](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span></span> <span data-ttu-id="818c3-124">Teams のダイレクトルーティングの場合は、「**電話番号を設定し、エンタープライズボイスメールとボイスメールを有効に**する」のセクションに従って、[ [Direct ルーティングの構成](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)] を選びます。</span><span class="sxs-lookup"><span data-stu-id="818c3-124">For Teams Direct Routing, follow  the **Configure the phone number and enable enterprise voice and voicemail** section of [Configure Direct Routing](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span></span>

4. <span data-ttu-id="818c3-p106">ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。Windows PowerShell を使用し、下記の手順を実行することによって、所属する組織のトランスクリプションを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="818c3-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="818c3-127">ボイスメールメッセージは、Exchange Online Protection を介してルーティングされる SMTP 経由で、ユーザーの Exchange メールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="818c3-127">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="818c3-128">これらのメッセージが正常に配信されるようにするには、exchange サーバーと Exchange Online Protection の間で Exchange コネクタが正しく構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="818c3-128">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection.</span></span> <span data-ttu-id="818c3-129">[コネクタを使用して、メールフローを構成](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)します。</span><span class="sxs-lookup"><span data-stu-id="818c3-129">[Use Connectors to Configure Mail Flow](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

6. <span data-ttu-id="818c3-130">Skype for Business クライアントで、グリーティングのカスタマイズや、視覚ボイスメールなどのボイスメール機能を有効にするには、Exchange Web Services を使用した Office 365 から Exchange server メールボックスへの接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="818c3-130">To enable Voicemail features such as customizing greetings, and visual voicemail in Skype for Business clients, connectivity from Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="818c3-131">この接続を有効にするには、「 [exchange と Exchange Online 組織の間の oauth 認証を構成](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)する」で説明する新しい Exchange Oauth 認証プロトコルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="818c3-131">To enable this connectivity you must configure the new Exchange Oauth authentication protocol describe in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)</span></span> 

> [!NOTE]
> <span data-ttu-id="818c3-132">Exchange のハイブリッドウィザードは、Exchange 2013 CU5 以降以上で実行され、手順5と6の要件を自動的に処理します。</span><span class="sxs-lookup"><span data-stu-id="818c3-132">The Exchange Hybrid Wizard run from Exchange 2013 CU5 or greater will handle the requirements in steps 5 and 6 automatically.</span></span> 

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="818c3-133">組織内のボイスメール ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="818c3-133">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="818c3-134">Skype for Business のお客様の場合、Microsoft Teams の通話ポリシーでボイスメールを無効にすると、Skype for Business ユーザーのボイスメールサービスを無効にすることがあります。</span><span class="sxs-lookup"><span data-stu-id="818c3-134">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="818c3-135">既定では、すべての組織とユーザーに対して、ボイスメール トランスクリプションは有効に、トランスクリプション不適切表現マスキングは無効になっています。ただし、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) と [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) コマンドレットを使用してそれらを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="818c3-135">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="818c3-136">**New-csonlinevoicemailpolicy**コマンドレットを使用して、用語の書き起こしと議事録の作成のための新しいポリシーインスタンスを作成することはできません。また、 **new-csonlinevoicemailpolicy**コマンドレットを使用して既存のポリシーインスタンスを削除することはできません。.</span><span class="sxs-lookup"><span data-stu-id="818c3-136">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="818c3-137">ボイスメール ポリシーを使用してユーザーのトランスクリプション設定を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="818c3-137">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="818c3-138">利用可能なボイスメールポリシーのすべてのインスタンスを表示するには、 [new-csonlinevoicemailpolicy](https://technet.microsoft.com/library/mt798311.aspx)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="818c3-138">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="818c3-139">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="818c3-139">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="818c3-141">組織のトランスクリプションをオフにする</span><span class="sxs-lookup"><span data-stu-id="818c3-141">Turning off transcription for your organization</span></span>

<span data-ttu-id="818c3-p110">組織のトランスクリプションに関する既定の設定はオンになっており、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) を使用して無効にすることができます。これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="818c3-p110">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="818c3-144">組織のトランスクリプション不適切表現マスキングをオンにする。</span><span class="sxs-lookup"><span data-stu-id="818c3-144">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="818c3-145">組織では、トランスクリプション不適切表現マスキングは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="818c3-145">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="818c3-146">マスキングを有効にしなければならないビジネス上の要件がある場合は、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) を使用してトランスクリプション不適切表現マスキングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="818c3-146">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="818c3-147">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="818c3-147">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="818c3-148">ユーザーのトランスクリプションをオフにする</span><span class="sxs-lookup"><span data-stu-id="818c3-148">Turning off transcription for a user</span></span>

<span data-ttu-id="818c3-149">ユーザー ポリシーは組織の既定の設定より前に評価されます。</span><span class="sxs-lookup"><span data-stu-id="818c3-149">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="818c3-150">たとえば、すべてのユーザーに対してボイスメールの議事録が有効になっている場合は、 [new-csonlinevoicemailpolicy](https://technet.microsoft.com/library/mt798309.aspx)コマンドレットを使用して、特定のユーザーに対して議事録を無効にするポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="818c3-150">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="818c3-151">単一ユーザーに対するトランスクリプションを無効にするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="818c3-151">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="818c3-152">ユーザーのトランスクリプション不適切表現マスキングをオンにします。</span><span class="sxs-lookup"><span data-stu-id="818c3-152">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="818c3-153">特定のユーザーに対してトランスクリプション不適切表現マスキングを有効にするには、ポリシーを割り当てて、[Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) コマンドレットを使用して特定のユーザーに対するトランスクリプション不適切表現マスキングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="818c3-153">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="818c3-154">単一ユーザーに対するトランスクリプション不適切表現マスキングを有効にするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="818c3-154">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="818c3-p113">Office 365 のボイスメール サービスによってボイスメール ポリシーがキャッシュされ、4 時間ごとにキャッシュが更新されます。このため、ポリシーを変更した場合、変更が適用されるまでに最長で 4 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="818c3-p113">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="818c3-157">Skype for Business ボイスメールの機能に関するユーザーの理解を支援する</span><span class="sxs-lookup"><span data-stu-id="818c3-157">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="818c3-p114">ユーザーが Skype for Business ボイスメールを正しく使用できるように支援するためのトレーニング情報と記事が用意されています。以下の記事をユーザーに紹介してください。</span><span class="sxs-lookup"><span data-stu-id="818c3-p114">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>

- <span data-ttu-id="818c3-160">[Skype for Business ボイス メールの確認とオプション](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): この記事では、Skype for Business でボイスメールを再生し、ボイスメール応答メッセージを変更し、ボイスメールの設定を変更し、ボイスメールを異なる速度で再生する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="818c3-160">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="818c3-161">Skype for Business 2016 トレーニング</span><span class="sxs-lookup"><span data-stu-id="818c3-161">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="818c3-162">関連トピック</span><span class="sxs-lookup"><span data-stu-id="818c3-162">Related topics</span></span>
[<span data-ttu-id="818c3-163">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="818c3-163">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="818c3-164">Office 365 での電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="818c3-164">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="818c3-165">Skype for Business Server と Exchange Server の移行の計画</span><span class="sxs-lookup"><span data-stu-id="818c3-165">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/plan-um-migration)


