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
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'ユーザー用にクラウド ボイスメールを設定する方法について学習します。 '
ms.openlocfilehash: 4ed61a825ce4e583c71f052020692e4478324003
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117065"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="307b4-103">クラウド ボイスメールのセットアップ</span><span class="sxs-lookup"><span data-stu-id="307b4-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="307b4-104">この記事は、Microsoft 365 または Office 365 管理者向け[](/microsoft-365/admin/add-users/about-admin-roles)です。「組織のすべてのユーザーにクラウド ボイスメール機能を設定する管理者ロールについて」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="307b4-104">This article is for the Microsoft 365 or Office 365 admin as described in [About admin roles](/microsoft-365/admin/add-users/about-admin-roles) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="307b4-105">クラウド ボイスメールは、ボイスメール メッセージの受信のみを Exchange メールボックスにサポートし、サードパーティのメール システムをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="307b4-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

> [!NOTE]
> <span data-ttu-id="307b4-106">代理人が委任者の代わりに通話に応答すると、クラウド ボイスメールでは通知を利用できません。</span><span class="sxs-lookup"><span data-stu-id="307b4-106">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="307b4-107">ユーザーは、着信を逃した場合の通知を受け取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="307b4-107">Users can receive notifications for missed calls.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a><span data-ttu-id="307b4-108">クラウド専用環境: オンライン電話システム ユーザー向けクラウド ボイスメールをセットアップする</span><span class="sxs-lookup"><span data-stu-id="307b4-108">Cloud-only environments: Set up Cloud Voicemail for Online Phone System users</span></span>

<span data-ttu-id="307b4-109">オンライン電話システム ユーザーの場合、ユーザーに電話システム ライセンスを割り当てると、クラウド ボイスメールが自動的にセットアップされ **、ユーザー用** にプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="307b4-109">For Online Phone System users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license to the users.</span></span> 

> [!NOTE]
> <span data-ttu-id="307b4-110">オンプレミスで提供された電話番号を持つ Online Skype for Business Phone System ユーザーの場合 [、Set-CsUser -HostedVoicemail](/powershell/module/skype/set-csuser?view=skype-ps)$True を使用してホストボイス メールを有効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="307b4-110">For Online Skype for Business Phone System users with on-premises provided phone numbers, you may need to enable hosted voice mail with [Set-CsUser -HostedVoicemail $True](/powershell/module/skype/set-csuser?view=skype-ps).</span></span> 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="307b4-111">メールボックス ユーザー向けクラウド ボイスメールExchange Serverセットアップする</span><span class="sxs-lookup"><span data-stu-id="307b4-111">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="307b4-112">次の情報は、電話システム用にオンラインでメールボックスを持っているユーザーと作業するためにクラウド ボイスメールをExchange Server。</span><span class="sxs-lookup"><span data-stu-id="307b4-112">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="307b4-113">ボイスメール メッセージは、Exchange Online Protection 経由でルーティングされる SMTP 経由でユーザーの Exchange メールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="307b4-113">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="307b4-114">これらのメッセージを正常に配信するには、Exchange サーバーと Exchange Online Protection の間で Exchange コネクタが正しく構成されていることを確認してください。 [コネクタを使用してメール フローを構成します](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="307b4-114">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

2. <span data-ttu-id="307b4-115">Skype for Business クライアントで応答メッセージやビジュアル ボイスメールをカスタマイズするなどのボイスメール機能を有効にするには、Microsoft 365 または Office 365 から Exchange Web Services 経由の Exchange サーバー メールボックスへの接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="307b4-115">To enable Voicemail features such as customizing greetings and visual voicemail in Skype for Business clients, connectivity from Microsoft 365 or Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="307b4-116">この接続を有効にするには、「Exchange と Exchange Online 組織間の [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)認証の構成」で説明されている新しい Exchange Oauth 認証プロトコルを構成するか、Exchange 2013 CU5 以上から Exchange ハイブリッド ウィザードを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="307b4-116">To enable this connectivity, you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="307b4-117">さらに、「Skype for Business Online と Exchange Server の統合と OAuth の構成」で説明されている Skype for Business Online と Exchange サーバー間の統合と [Oauth を構成する必要があります](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)。</span><span class="sxs-lookup"><span data-stu-id="307b4-117">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="307b4-118">Skype for Business Server ユーザーのクラウド ボイスメールをセットアップする</span><span class="sxs-lookup"><span data-stu-id="307b4-118">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="307b4-119">クラウド ボイスメール用に Skype for Business サーバー ユーザーを構成するには、「オンプレミス ユーザー向けクラウド ボイスメール サービスを計画する」 [を参照してください](/skypeforbusiness/hybrid/plan-cloud-voicemail)。</span><span class="sxs-lookup"><span data-stu-id="307b4-119">To configure Skype for Business server users for Cloud Voicemail, please see [Plan Cloud Voicemail service for on-premises users](/skypeforbusiness/hybrid/plan-cloud-voicemail).</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="307b4-120">組織内で保護されたボイスメールを有効にする</span><span class="sxs-lookup"><span data-stu-id="307b4-120">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="307b4-121">ユーザーが組織内のユーザーのボイスメール メッセージを離れる場合、ボイスメールはメール メッセージの添付ファイルとしてユーザーのメールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="307b4-121">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="307b4-122">メール フロー ルールを使用してメッセージの暗号化を適用すると、それらのボイスメール メッセージが他の受信者に転送されるのを防ぐ方法があります。</span><span class="sxs-lookup"><span data-stu-id="307b4-122">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="307b4-123">保護されたボイスメールを有効にした場合、ユーザーは、ボイスメール メールボックスに通話するか、Outlook、Outlook on the web、または Outlook for Android または iOS でメッセージを開いて、保護されたボイスメール メッセージを聞き取ります。</span><span class="sxs-lookup"><span data-stu-id="307b4-123">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="307b4-124">保護されたボイスメール メッセージは、Skype for Business または Microsoft Teams で開くことができません。</span><span class="sxs-lookup"><span data-stu-id="307b4-124">Protected voicemail messages can't be opened in Skype for Business or Microsoft Teams.</span></span>

<span data-ttu-id="307b4-125">メッセージの暗号化の詳細については、「メールの暗号化 [」を参照してください](/microsoft-365/compliance/email-encryption?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="307b4-125">For more information about message encryption, see [Email encryption](/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="307b4-126">保護されたボイスメールを設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="307b4-126">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="307b4-127">グローバル管理者権限 https://admin.microsoft.com を持つアカウントに移動してサインインします。</span><span class="sxs-lookup"><span data-stu-id="307b4-127">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="307b4-128">[すべて **表示] を選** び、管理センターの Exchange **に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="307b4-128">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="307b4-129">Exchange 管理センターで、[メール フロー ルール **] を選択**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="307b4-129">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="307b4-130">[ **+** **追加]** を選択し **、[365 Message Encryption Office権限** の保護をメッセージに適用する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="307b4-130">Select **+** **Add**, and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="307b4-131">新しいメール フロー ルールの名前を入力し、[このルールを適用する場合] の [メッセージのプロパティにメッセージの種類を含めるボイス メール  >  **]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="307b4-131">Provide a name for the new mail flow rule and then under **Apply this rule if**, select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="307b4-132">**[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="307b4-132">Select **OK**.</span></span>
6. <span data-ttu-id="307b4-133">[ **次の操作を行** う] で **、[365 Message Encryption** とOffice保護を適用する] を選択し、[Select **one]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="307b4-133">Under **Do the following**, select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="307b4-134">**[RMS テンプレート] で 、[** 転送しない **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="307b4-134">Under **RMS template**, select **Do not forward**.</span></span> <span data-ttu-id="307b4-135">**[OK] を選択** し、[保存 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="307b4-135">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="307b4-136">RMS テンプレート **の一覧が** 空の場合は、Message Encryption を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="307b4-136">If the **RMS template** list is empty, you need to set up Message Encryption.</span></span> <span data-ttu-id="307b4-137">Message Encryption の設定の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="307b4-137">For more information about setting up Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="307b4-138">新しい Message Encryption 機能をセットアップする</span><span class="sxs-lookup"><span data-stu-id="307b4-138">Set up new Message Encryption capabilities</span></span>](/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="307b4-139">Azure Information Protection のテンプレートの構成と管理</span><span class="sxs-lookup"><span data-stu-id="307b4-139">Configuring and managing templates for Azure Information Protection</span></span>](/information-protection/deploy-use/configure-policy-templates)
    > - <span data-ttu-id="307b4-140">[メールの [転送しない] オプション](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="307b4-140">[Do Not Forward option for emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)</span></span>

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="307b4-141">組織内のボイスメール ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="307b4-141">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="307b4-142">Skype for Business のお客様の場合、Microsoft Teams 通話ポリシーを通じてボイスメールを無効にすると、Skype for Business ユーザーのボイスメール サービスも無効になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="307b4-142">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="307b4-143">既定では、すべての組織とユーザーに対して、ボイスメール トランスクリプションは有効に、トランスクリプション不適切表現マスキングは無効になっています。ただし、[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) と [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) コマンドレットを使用してそれらを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="307b4-143">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) and [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlets.</span></span>

<span data-ttu-id="307b4-144">組織内のユーザーによって受信されたボイスメール メッセージは、Microsoft 365 または Office 365 組織がホストされている地域で変換されます。</span><span class="sxs-lookup"><span data-stu-id="307b4-144">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="307b4-145">テナントがホストされている地域は、ボイスメール メッセージを受信するユーザーと同じ地域ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="307b4-145">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="307b4-146">テナントがホストされている地域を表示するには、[組織プロファイル][](https://go.microsoft.com/fwlink/p/?linkid=2067339)ページに移動し、[データの場所] の横にある [詳細の表示]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="307b4-146">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="307b4-147">**New-CsOnlineVoiceMailPolicy** コマンドレットを使用してトランスクリプションとトランスクリプション不適切なマスクの新しいポリシー インスタンスを作成したり **、Remove-CsOnlineVoiceMailPolicy** コマンドレットを使用して既存のポリシー インスタンスを削除したりできない。</span><span class="sxs-lookup"><span data-stu-id="307b4-147">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="307b4-148">ボイスメール ポリシーを使用してユーザーのトランスクリプション設定を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="307b4-148">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="307b4-149">使用可能なすべてのボイスメール ポリシー インスタンスを表示するには [、Get-CsOnlineVoicemailPolicy コマンドレットを使用](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) します。</span><span class="sxs-lookup"><span data-stu-id="307b4-149">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet.</span></span>

```PowerShell
PS C:\> Get-CsOnlineVoicemailPolicy


Identity                            : Global
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:Default
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionProfanityMaskingEnabled
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : True
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionDisabled
EnableTranscription                 : False
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True
```
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="307b4-150">組織のトランスクリプションをオフにする</span><span class="sxs-lookup"><span data-stu-id="307b4-150">Turning off transcription for your organization</span></span>

<span data-ttu-id="307b4-p110">組織のトランスクリプションに関する既定の設定はオンになっており、[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) を使用して無効にすることができます。これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="307b4-p110">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy). To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="307b4-153">組織のトランスクリプション不適切表現マスキングをオンにする。</span><span class="sxs-lookup"><span data-stu-id="307b4-153">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="307b4-154">組織では、トランスクリプション不適切表現マスキングは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="307b4-154">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="307b4-155">マスキングを有効にしなければならないビジネス上の要件がある場合は、[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) を使用してトランスクリプション不適切表現マスキングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="307b4-155">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="307b4-156">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="307b4-156">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="307b4-157">ユーザーのトランスクリプションをオフにする</span><span class="sxs-lookup"><span data-stu-id="307b4-157">Turning off transcription for a user</span></span>

<span data-ttu-id="307b4-158">ユーザー ポリシーは組織の既定の設定より前に評価されます。</span><span class="sxs-lookup"><span data-stu-id="307b4-158">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="307b4-159">たとえば、すべてのユーザーに対してボイスメール トランスクリプションが有効になっている場合 [、Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) コマンドレットを使用して、特定のユーザーのトランスクリプションを無効にするポリシーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="307b4-159">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="307b4-160">単一ユーザーに対するトランスクリプションを無効にするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="307b4-160">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="307b4-161">ユーザーのトランスクリプション不適切表現マスキングをオンにします。</span><span class="sxs-lookup"><span data-stu-id="307b4-161">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="307b4-162">特定のユーザーに対してトランスクリプション不適切表現マスキングを有効にするには、ポリシーを割り当てて、[Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) コマンドレットを使用して特定のユーザーに対するトランスクリプション不適切表現マスキングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="307b4-162">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="307b4-163">単一ユーザーに対するトランスクリプション不適切表現マスキングを有効にするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="307b4-163">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="307b4-164">Microsoft 365 および Office 365 のボイスメール サービスは、ボイスメール ポリシーをキャッシュし、4 時間ごとにキャッシュを更新します。</span><span class="sxs-lookup"><span data-stu-id="307b4-164">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 4 hours.</span></span> <span data-ttu-id="307b4-165">このため、ポリシーを変更した場合、変更が適用されるまでに最長で 4 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="307b4-165">So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="307b4-166">ユーザーが Teams ボイスメール機能を学ぶのを支援する</span><span class="sxs-lookup"><span data-stu-id="307b4-166">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="307b4-167">ボイスメールの設定と Teams のその他の通話機能の管理に関するユーザー向け情報は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="307b4-167">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="307b4-168">[Teams で通話設定を管理します](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)。</span><span class="sxs-lookup"><span data-stu-id="307b4-168">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="307b4-169">この記事では、すべてのエンド ユーザーの Teams 通話機能を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="307b4-169">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="307b4-170">Skype for Business ボイスメールの機能に関するユーザーの理解を支援する</span><span class="sxs-lookup"><span data-stu-id="307b4-170">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="307b4-p115">ユーザーが Skype for Business ボイスメールを正しく使用できるように支援するためのトレーニング情報と記事が用意されています。以下の記事をユーザーに紹介してください。</span><span class="sxs-lookup"><span data-stu-id="307b4-p115">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>

- <span data-ttu-id="307b4-173">[Skype for Business ボイス メールの確認とオプション](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): この記事では、Skype for Business でボイスメールを再生し、ボイスメール応答メッセージを変更し、ボイスメールの設定を変更し、ボイスメールを異なる速度で再生する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="307b4-173">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="307b4-174">Skype for Business 2016 トレーニング</span><span class="sxs-lookup"><span data-stu-id="307b4-174">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="307b4-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="307b4-175">Related topics</span></span>
[<span data-ttu-id="307b4-176">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="307b4-176">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="307b4-177">電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="307b4-177">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="307b4-178">Skype for Business Server と Exchange Server の移行の計画</span><span class="sxs-lookup"><span data-stu-id="307b4-178">Plan for Skype for Business Server and Exchange Server migration</span></span>](/SkypeForBusiness/hybrid/plan-um-migration)