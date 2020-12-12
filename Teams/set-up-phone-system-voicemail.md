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
ms.openlocfilehash: 81e5f83b251a0bd648cb2ab2afd69f35357fc49f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662212"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="e5419-103">クラウド ボイスメールのセットアップ</span><span class="sxs-lookup"><span data-stu-id="e5419-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="e5419-104">この記事は、Microsoft 365 または Office 365 管理者向け[](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)です。「組織のすべてのユーザーにクラウド ボイスメール機能を設定する管理者ロールについて」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5419-104">This article is for the Microsoft 365 or Office 365 admin as described in [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="e5419-105">クラウド ボイスメールは、Exchange メールボックスへのボイスメール メッセージの受信のみをサポートし、サードパーティのメール システムをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="e5419-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

> [!NOTE]
> <span data-ttu-id="e5419-106">代理人が委任者の代わりに通話に応答すると、クラウド ボイスメールでは通知を利用できません。</span><span class="sxs-lookup"><span data-stu-id="e5419-106">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="e5419-107">ユーザーは、着信を逃した場合の通知を受け取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e5419-107">Users can receive notifications for missed calls.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a><span data-ttu-id="e5419-108">クラウド専用環境: オンライン電話システム ユーザー向けクラウド ボイスメールをセットアップする</span><span class="sxs-lookup"><span data-stu-id="e5419-108">Cloud-only environments: Set up Cloud Voicemail for Online Phone System users</span></span>

<span data-ttu-id="e5419-109">オンライン電話システム ユーザーの場合、ユーザーに電話システム ライセンスを割り当てると、クラウド ボイスメールが自動的にセットアップ **され、ユーザー** 用にプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="e5419-109">For Online Phone System users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license to the users.</span></span> 

> [!NOTE]
> <span data-ttu-id="e5419-110">オンプレミスで提供された電話番号を持つ Online Skype for Business Phone System ユーザーの場合 [、Set-CsUser -HostedVoicemail](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)$True を使用してホストボイス メールを有効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e5419-110">For Online Skype for Business Phone System users with on-premises provided phone numbers, you may need to enable hosted voice mail with [Set-CsUser -HostedVoicemail $True](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps).</span></span> 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="e5419-111">メールボックス ユーザー向けクラウド ボイスメールExchange Serverセットアップする</span><span class="sxs-lookup"><span data-stu-id="e5419-111">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="e5419-112">次の情報は、電話システム用にオンラインでメールボックスを持っているユーザーと作業するためにクラウド ボイスメールをExchange Server。</span><span class="sxs-lookup"><span data-stu-id="e5419-112">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="e5419-113">ボイスメール メッセージは、Exchange Online Protection 経由でルーティングされる SMTP 経由でユーザーの Exchange メールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="e5419-113">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="e5419-114">これらのメッセージを正常に配信するには、Exchange サーバーと Exchange Online Protection の間で Exchange コネクタが正しく構成されていることを確認してください。 [コネクタを使用してメール フローを構成します](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="e5419-114">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

2. <span data-ttu-id="e5419-115">Skype for Business クライアントで応答メッセージやビジュアル ボイスメールをカスタマイズするなどのボイスメール機能を有効にするには、Microsoft 365 または Office 365 から Exchange Web Services 経由の Exchange サーバー メールボックスへの接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="e5419-115">To enable Voicemail features such as customizing greetings and visual voicemail in Skype for Business clients, connectivity from Microsoft 365 or Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="e5419-116">この接続を有効にするには、「Exchange と Exchange Online 組織間の [OAuth](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)認証の構成」で説明されている新しい Exchange Oauth 認証プロトコルを構成するか、Exchange 2013 CU5 以上から Exchange ハイブリッド ウィザードを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5419-116">To enable this connectivity, you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="e5419-117">さらに、「Skype for Business Online と Exchange Server の統合と OAuth の構成」で説明されている Skype for Business Online と Exchange サーバー間の統合と [Oauth を構成する必要があります](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)。</span><span class="sxs-lookup"><span data-stu-id="e5419-117">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="e5419-118">Skype for Business Server ユーザーのクラウド ボイスメールをセットアップする</span><span class="sxs-lookup"><span data-stu-id="e5419-118">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="e5419-119">クラウド ボイスメール用に Skype for Business サーバー ユーザーを構成するには、「オンプレミス ユーザー向けクラウド ボイスメール サービスを計画する」 [を参照してください](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)。</span><span class="sxs-lookup"><span data-stu-id="e5419-119">To configure Skype for Business server users for Cloud Voicemail, please see [Plan Cloud Voicemail service for on-premises users](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail).</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="e5419-120">組織内で保護されたボイスメールを有効にする</span><span class="sxs-lookup"><span data-stu-id="e5419-120">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="e5419-121">ユーザーが組織内のユーザーのボイスメール メッセージを離れる場合、ボイスメールはメール メッセージの添付ファイルとしてユーザーのメールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="e5419-121">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="e5419-122">メール フロー ルールを使用してメッセージの暗号化を適用すると、それらのボイスメール メッセージが他の受信者に転送されるのを防ぐ方法があります。</span><span class="sxs-lookup"><span data-stu-id="e5419-122">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="e5419-123">保護されたボイスメールを有効にした場合、ユーザーは、ボイスメール メールボックスに通話するか、Outlook、Outlook on the web、または Outlook for Android または iOS でメッセージを開いて、保護されたボイスメール メッセージを聞き取ります。</span><span class="sxs-lookup"><span data-stu-id="e5419-123">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="e5419-124">保護されたボイスメール メッセージは、Skype for Business または Microsoft Teams で開くことができません。</span><span class="sxs-lookup"><span data-stu-id="e5419-124">Protected voicemail messages can't be opened in Skype for Business or Microsoft Teams.</span></span>

<span data-ttu-id="e5419-125">メッセージの暗号化の詳細については、「メールの暗号化 [」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="e5419-125">For more information about message encryption, see [Email encryption](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="e5419-126">保護されたボイスメールを設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e5419-126">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="e5419-127">グローバル管理者権限 https://admin.microsoft.com を持つアカウントに移動してサインインします。</span><span class="sxs-lookup"><span data-stu-id="e5419-127">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="e5419-128">[すべて **表示] を選** び、管理センターの Exchange **に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="e5419-128">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="e5419-129">Exchange 管理センターで、[メール フロー ルール **] を選択**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="e5419-129">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="e5419-130">[ **+** **追加]** を選択し **、[365 Message Encryption Office権限** の保護をメッセージに適用する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5419-130">Select **+** **Add**, and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="e5419-131">新しいメール フロー ルールの名前を入力し、[このルールを適用する場合] の [メッセージのプロパティにメッセージの種類を含めるボイス メール  >  **]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e5419-131">Provide a name for the new mail flow rule and then under **Apply this rule if**, select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="e5419-132">**[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e5419-132">Select **OK**.</span></span>
6. <span data-ttu-id="e5419-133">[ **次の操作を行** う] で **、[365 Message Encryption** とOffice保護を適用する] を選択し、[Select **one]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5419-133">Under **Do the following**, select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="e5419-134">**[RMS テンプレート] で 、[** 転送しない **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e5419-134">Under **RMS template**, select **Do not forward**.</span></span> <span data-ttu-id="e5419-135">**[OK] を選択** し、[保存 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e5419-135">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="e5419-136">RMS テンプレート **の一覧が** 空の場合は、Message Encryption を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5419-136">If the **RMS template** list is empty, you need to set up Message Encryption.</span></span> <span data-ttu-id="e5419-137">Message Encryption の設定の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5419-137">For more information about setting up Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="e5419-138">新しい Message Encryption 機能をセットアップする</span><span class="sxs-lookup"><span data-stu-id="e5419-138">Set up new Message Encryption capabilities</span></span>](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="e5419-139">Azure Information Protection のテンプレートの構成と管理</span><span class="sxs-lookup"><span data-stu-id="e5419-139">Configuring and managing templates for Azure Information Protection</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - <span data-ttu-id="e5419-140">[メールの [転送しない] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="e5419-140">[Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)</span></span>

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="e5419-141">組織内のボイスメール ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="e5419-141">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="e5419-142">Skype for Business のお客様の場合、Microsoft Teams 通話ポリシーを通じてボイスメールを無効にすると、Skype for Business ユーザーのボイスメール サービスも無効になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e5419-142">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="e5419-143">既定では、すべての組織とユーザーに対して、ボイスメール トランスクリプションは有効に、トランスクリプション不適切表現マスキングは無効になっています。ただし、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) と [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) コマンドレットを使用してそれらを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="e5419-143">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="e5419-144">組織内のユーザーによって受信されたボイスメール メッセージは、Microsoft 365 または Office 365 組織がホストされている地域で変換されます。</span><span class="sxs-lookup"><span data-stu-id="e5419-144">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="e5419-145">テナントがホストされている地域は、ボイスメール メッセージを受信するユーザーと同じ地域ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e5419-145">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="e5419-146">テナントがホストされている地域を表示するには、[組織プロファイル][](https://go.microsoft.com/fwlink/p/?linkid=2067339)ページに移動し、[データの場所] の横にある [**詳細の表示**]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e5419-146">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5419-147">**New-CsOnlineVoiceMailPolicy** コマンドレットを使用してトランスクリプションとトランスクリプション不適切なマスクの新しいポリシー インスタンスを作成したり **、Remove-CsOnlineVoiceMailPolicy** コマンドレットを使用して既存のポリシー インスタンスを削除したりできない。</span><span class="sxs-lookup"><span data-stu-id="e5419-147">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="e5419-148">ボイスメール ポリシーを使用してユーザーのトランスクリプション設定を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="e5419-148">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="e5419-149">使用可能なすべてのボイスメール ポリシー インスタンスを表示するには [、Get-CsOnlineVoicemailPolicy コマンドレットを使用](https://technet.microsoft.com/library/mt798311.aspx) します。</span><span class="sxs-lookup"><span data-stu-id="e5419-149">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="e5419-150">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="e5419-150">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="e5419-152">組織のトランスクリプションをオフにする</span><span class="sxs-lookup"><span data-stu-id="e5419-152">Turning off transcription for your organization</span></span>

<span data-ttu-id="e5419-p110">組織のトランスクリプションに関する既定の設定はオンになっており、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) を使用して無効にすることができます。これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="e5419-p110">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="e5419-155">組織のトランスクリプション不適切表現マスキングをオンにする。</span><span class="sxs-lookup"><span data-stu-id="e5419-155">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="e5419-156">組織では、トランスクリプション不適切表現マスキングは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="e5419-156">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="e5419-157">マスキングを有効にしなければならないビジネス上の要件がある場合は、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) を使用してトランスクリプション不適切表現マスキングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e5419-157">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="e5419-158">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="e5419-158">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="e5419-159">ユーザーのトランスクリプションをオフにする</span><span class="sxs-lookup"><span data-stu-id="e5419-159">Turning off transcription for a user</span></span>

<span data-ttu-id="e5419-160">ユーザー ポリシーは組織の既定の設定より前に評価されます。</span><span class="sxs-lookup"><span data-stu-id="e5419-160">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="e5419-161">たとえば、すべてのユーザーに対してボイスメール トランスクリプションが有効になっている場合 [、Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) コマンドレットを使用して、特定のユーザーのトランスクリプションを無効にするポリシーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="e5419-161">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="e5419-162">単一ユーザーに対するトランスクリプションを無効にするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="e5419-162">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="e5419-163">ユーザーのトランスクリプション不適切表現マスキングをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e5419-163">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="e5419-164">特定のユーザーに対してトランスクリプション不適切表現マスキングを有効にするには、ポリシーを割り当てて、[Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) コマンドレットを使用して特定のユーザーに対するトランスクリプション不適切表現マスキングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e5419-164">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="e5419-165">単一ユーザーに対するトランスクリプション不適切表現マスキングを有効にするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="e5419-165">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="e5419-166">Microsoft 365 および Office 365 のボイスメール サービスは、ボイスメール ポリシーをキャッシュし、4 時間ごとにキャッシュを更新します。</span><span class="sxs-lookup"><span data-stu-id="e5419-166">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 4 hours.</span></span> <span data-ttu-id="e5419-167">このため、ポリシーを変更した場合、変更が適用されるまでに最長で 4 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e5419-167">So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="e5419-168">ユーザーが Teams ボイスメール機能を学ぶのを支援する</span><span class="sxs-lookup"><span data-stu-id="e5419-168">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="e5419-169">ユーザーがボイスメールの設定を管理する方法と、Teams のその他の通話機能に関する次の情報があります。</span><span class="sxs-lookup"><span data-stu-id="e5419-169">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="e5419-170">[Teams で通話設定を管理します](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)。</span><span class="sxs-lookup"><span data-stu-id="e5419-170">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="e5419-171">この記事では、すべてのエンド ユーザーの Teams 通話機能を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5419-171">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="e5419-172">Skype for Business ボイスメールの機能に関するユーザーの理解を支援する</span><span class="sxs-lookup"><span data-stu-id="e5419-172">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="e5419-p115">ユーザーが Skype for Business ボイスメールを正しく使用できるように支援するためのトレーニング情報と記事が用意されています。以下の記事をユーザーに紹介してください。</span><span class="sxs-lookup"><span data-stu-id="e5419-p115">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>

- <span data-ttu-id="e5419-175">[Skype for Business ボイス メールの確認とオプション](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): この記事では、Skype for Business でボイスメールを再生し、ボイスメール応答メッセージを変更し、ボイスメールの設定を変更し、ボイスメールを異なる速度で再生する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5419-175">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="e5419-176">Skype for Business 2016 トレーニング</span><span class="sxs-lookup"><span data-stu-id="e5419-176">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="e5419-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5419-177">Related topics</span></span>
[<span data-ttu-id="e5419-178">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="e5419-178">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="e5419-179">電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="e5419-179">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="e5419-180">Skype for Business Server と Exchange Server の移行の計画</span><span class="sxs-lookup"><span data-stu-id="e5419-180">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
