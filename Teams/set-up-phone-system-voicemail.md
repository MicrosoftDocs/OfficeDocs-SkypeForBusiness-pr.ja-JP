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
description: 'ユーザーにクラウドボイスメールをセットアップする方法について説明します。 '
ms.openlocfilehash: df8e6d5962e3bff2148165466400e90ee3a4607d
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031073"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="57a41-103">クラウド ボイスメールのセットアップ</span><span class="sxs-lookup"><span data-stu-id="57a41-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="57a41-104">この記事は、Microsoft 365 または Office 365 管理者を対象としています。詳しくは、「クラウドボイスメール機能をセットアップして、社内のすべてのユーザーを対象にしています [」で説明](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) しています。</span><span class="sxs-lookup"><span data-stu-id="57a41-104">This article is for the Microsoft 365 or Office 365 admin as described in [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="57a41-105">クラウドボイスメールでは、Exchange メールボックスでのボイスメールメッセージのデポジットのみがサポートされ、サードパーティのメールシステムはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="57a41-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

> [!NOTE]
> <span data-ttu-id="57a41-106">代理人が委任者の代わりに着信に応答する場合、クラウドボイスメールでは通知を利用できません。</span><span class="sxs-lookup"><span data-stu-id="57a41-106">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="57a41-107">不在着信の通知は、ユーザーが受信できます。</span><span class="sxs-lookup"><span data-stu-id="57a41-107">Users can receive notifications for missed calls.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a><span data-ttu-id="57a41-108">クラウドのみの環境: オンライン電話システムユーザーにクラウドボイスメールをセットアップする</span><span class="sxs-lookup"><span data-stu-id="57a41-108">Cloud-only environments: Set up Cloud Voicemail for Online Phone System users</span></span>

<span data-ttu-id="57a41-109">オンライン電話システムを利用している場合は、 **電話システム** のライセンスをユーザーに割り当てた後で、クラウドボイスメールが自動的に設定され、ユーザーに提供されます。</span><span class="sxs-lookup"><span data-stu-id="57a41-109">For Online Phone System users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license to the users.</span></span> 

> [!NOTE]
> <span data-ttu-id="57a41-110">オンプレミスの電話番号を提供するオンラインの Skype for Business 電話システムユーザーの場合は、 [HostedVoicemail $True](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)を使用して、ホストされているボイスメールを有効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="57a41-110">For Online Skype for Business Phone System users with on-premises provided phone numbers, you may need to enable hosted voice mail with [Set-CsUser -HostedVoicemail $True](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps).</span></span> 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="57a41-111">Exchange Server メールボックスユーザーにクラウドボイスメールをセットアップする</span><span class="sxs-lookup"><span data-stu-id="57a41-111">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="57a41-112">以下の情報は、電話システムに接続しているが、Exchange Server にメールボックスがあるユーザーと連携するようにクラウドボイスメールを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="57a41-112">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="57a41-113">ボイスメールメッセージは、Exchange Online Protection を介してルーティングされる SMTP 経由で、ユーザーの Exchange メールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="57a41-113">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="57a41-114">これらのメッセージが正常に配信されるようにするには、exchange サーバーと Exchange Online Protection の間で Exchange コネクタが正しく構成されていることを確認します。 [コネクタを使用して、メールフローを構成](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)します。</span><span class="sxs-lookup"><span data-stu-id="57a41-114">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

2. <span data-ttu-id="57a41-115">Skype for Business クライアントでの応答メッセージや視覚ボイスメールのカスタマイズなどのボイスメール機能を有効にするには、Exchange Web Services 経由で Microsoft 365 または Office 365 から Exchange server メールボックスに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57a41-115">To enable Voicemail features such as customizing greetings and visual voicemail in Skype for Business clients, connectivity from Microsoft 365 or Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="57a41-116">この接続を有効にするには、「 [exchange と Exchange Online の間の Oauth 認証を構成](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)する」で説明されている新しい exchange Oauth 認証プロトコルを構成するか、または EXCHANGE 2013 cu5 以降以上から Exchange ハイブリッドウィザードを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57a41-116">To enable this connectivity, you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="57a41-117">さらに、「skype for business [online と Exchange server の間の統合と oauth の構成](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)」で説明されているように、Skype For business Online と exchange server の間で統合と oauth を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57a41-117">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="57a41-118">Skype for Business Server ユーザー用にクラウドボイスメールをセットアップする</span><span class="sxs-lookup"><span data-stu-id="57a41-118">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="57a41-119">クラウドボイスメール用に Skype for Business server ユーザーを構成するには、「 [オンプレミスユーザー向けのクラウドボイスメールサービスの計画](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57a41-119">To configure Skype for Business server users for Cloud Voicemail, please see [Plan Cloud Voicemail service for on-premises users](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail).</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="57a41-120">組織で保護されたボイスメールを有効にする</span><span class="sxs-lookup"><span data-stu-id="57a41-120">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="57a41-121">組織内のユーザーに対してボイスメールメッセージを残した場合、ボイスメールは、メールメッセージの添付ファイルとしてユーザーのメールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="57a41-121">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="57a41-122">メールフロールールを使ってメッセージの暗号化を適用すると、これらのボイスメールメッセージが他の受信者に転送されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="57a41-122">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="57a41-123">保護されたボイスメールを有効にすると、ユーザーはボイスメールメールボックスを使用するか、outlook、Outlook on the web、または Android 用 Outlook または iOS 版 Outlook でメッセージを開くことによって、保護されたボイスメールメッセージを聞くことができます。</span><span class="sxs-lookup"><span data-stu-id="57a41-123">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="57a41-124">保護されたボイスメールメッセージを Skype for Business で開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="57a41-124">Protected voicemail messages can't be opened in Skype for Business.</span></span>

<span data-ttu-id="57a41-125">メッセージの暗号化の詳細については、「 [メールの暗号化](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57a41-125">For more information about message encryption, see [Email encryption](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="57a41-126">保護されたボイスメールを設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="57a41-126">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="57a41-127">https://admin.microsoft.comグローバル管理者の権限を持つアカウントを使用して、に移動してサインインします。</span><span class="sxs-lookup"><span data-stu-id="57a41-127">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="57a41-128">[ **すべて表示** ] を選択し、[ **管理センター** の Exchange] に移動し  >  **Exchange** ます。</span><span class="sxs-lookup"><span data-stu-id="57a41-128">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="57a41-129">Exchange 管理センターで、[ **メールフロー** ルール] を選択し  >  **Rules** ます。</span><span class="sxs-lookup"><span data-stu-id="57a41-129">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="57a41-130">[追加] を選択し **+** **Add** 、[ **Office 365 メッセージの暗号化と権限の保護をメッセージに適用する** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="57a41-130">Select **+** **Add** , and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="57a41-131">新しいメールフロールールの名前を指定し、[ **このルールを適用\*\*\*\*する** 条件] で [メッセージの種類] ボックスに「  >  **Include the message type**  >  **ボイスメール** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="57a41-131">Provide a name for the new mail flow rule and then under **Apply this rule if** , select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="57a41-132">[ **OK]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="57a41-132">Select **OK**.</span></span>
6. <span data-ttu-id="57a41-133">[ **実行する処理** ] で、[ **Office 365 メッセージの暗号化と著作権の保護をメッセージに適用する** ] を選択し、[ **1 つ選択** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="57a41-133">Under **Do the following** , select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="57a41-134">[ **RMS テンプレート** ] で、[ **転送しない** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="57a41-134">Under **RMS template** , select **Do not forward**.</span></span> <span data-ttu-id="57a41-135">[ **OK]** 、[ **保存** ] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="57a41-135">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="57a41-136">**RMS テンプレート** の一覧が空の場合は、メッセージの暗号化を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57a41-136">If the **RMS template** list is empty, you need to set up Message Encryption.</span></span> <span data-ttu-id="57a41-137">メッセージの暗号化の設定の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57a41-137">For more information about setting up Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="57a41-138">新しいメッセージの暗号化機能を設定する</span><span class="sxs-lookup"><span data-stu-id="57a41-138">Set up new Message Encryption capabilities</span></span>](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="57a41-139">Azure Information Protection 用のテンプレートの構成と管理</span><span class="sxs-lookup"><span data-stu-id="57a41-139">Configuring and managing templates for Azure Information Protection</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - <span data-ttu-id="57a41-140">[メールの [転送しない] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="57a41-140">[Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)</span></span>

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="57a41-141">組織内のボイスメール ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="57a41-141">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="57a41-142">Skype for Business のお客様の場合、Microsoft Teams の通話ポリシーでボイスメールを無効にすると、Skype for Business ユーザーのボイスメールサービスを無効にすることがあります。</span><span class="sxs-lookup"><span data-stu-id="57a41-142">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="57a41-143">既定では、すべての組織とユーザーに対して、ボイスメール トランスクリプションは有効に、トランスクリプション不適切表現マスキングは無効になっています。ただし、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) と [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) コマンドレットを使用してそれらを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="57a41-143">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="57a41-144">組織内のユーザーから受信したボイスメールメッセージは、Microsoft 365 または Office 365 組織がホストされている地域に transcribed されています。</span><span class="sxs-lookup"><span data-stu-id="57a41-144">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="57a41-145">テナントがホストされている地域は、ボイスメールメッセージを受信するユーザーが配置されている地域とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="57a41-145">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="57a41-146">テナントがホストされている地域を表示するには、[ [組織プロファイル](https://go.microsoft.com/fwlink/p/?linkid=2067339)] ページに移動し、[ **データの場所** ] の横にある [詳細の **表示** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57a41-146">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="57a41-147">**New-csonlinevoicemailpolicy** コマンドレットを使って、書き起こしと議事録のプロファニティマスク用の新しいポリシーインスタンスを作成することはできません。また、 **new-csonlinevoicemailpolicy** コマンドレットを使用して既存のポリシーインスタンスを削除することもできません。</span><span class="sxs-lookup"><span data-stu-id="57a41-147">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="57a41-148">ボイスメール ポリシーを使用してユーザーのトランスクリプション設定を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="57a41-148">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="57a41-149">利用可能なボイスメールポリシーのすべてのインスタンスを表示するには、 [new-csonlinevoicemailpolicy](https://technet.microsoft.com/library/mt798311.aspx) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="57a41-149">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="57a41-150">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="57a41-150">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="57a41-152">組織のトランスクリプションをオフにする</span><span class="sxs-lookup"><span data-stu-id="57a41-152">Turning off transcription for your organization</span></span>

<span data-ttu-id="57a41-p110">組織のトランスクリプションに関する既定の設定はオンになっており、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) を使用して無効にすることができます。これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="57a41-p110">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="57a41-155">組織のトランスクリプション不適切表現マスキングをオンにする。</span><span class="sxs-lookup"><span data-stu-id="57a41-155">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="57a41-156">組織では、トランスクリプション不適切表現マスキングは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="57a41-156">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="57a41-157">マスキングを有効にしなければならないビジネス上の要件がある場合は、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) を使用してトランスクリプション不適切表現マスキングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="57a41-157">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="57a41-158">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="57a41-158">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="57a41-159">ユーザーのトランスクリプションをオフにする</span><span class="sxs-lookup"><span data-stu-id="57a41-159">Turning off transcription for a user</span></span>

<span data-ttu-id="57a41-160">ユーザー ポリシーは組織の既定の設定より前に評価されます。</span><span class="sxs-lookup"><span data-stu-id="57a41-160">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="57a41-161">たとえば、すべてのユーザーに対してボイスメールの議事録が有効になっている場合は、 [new-csonlinevoicemailpolicy](https://technet.microsoft.com/library/mt798309.aspx) コマンドレットを使用して、特定のユーザーに対して議事録を無効にするポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="57a41-161">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="57a41-162">単一ユーザーに対するトランスクリプションを無効にするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="57a41-162">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="57a41-163">ユーザーのトランスクリプション不適切表現マスキングをオンにします。</span><span class="sxs-lookup"><span data-stu-id="57a41-163">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="57a41-164">特定のユーザーに対してトランスクリプション不適切表現マスキングを有効にするには、ポリシーを割り当てて、[Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) コマンドレットを使用して特定のユーザーに対するトランスクリプション不適切表現マスキングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="57a41-164">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="57a41-165">単一ユーザーに対するトランスクリプション不適切表現マスキングを有効にするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="57a41-165">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="57a41-166">Microsoft 365 および Office 365 のボイスメールサービスは、ボイスメールポリシーをキャッシュし、4時間ごとにキャッシュを更新します。</span><span class="sxs-lookup"><span data-stu-id="57a41-166">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 4 hours.</span></span> <span data-ttu-id="57a41-167">このため、ポリシーを変更した場合、変更が適用されるまでに最長で 4 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="57a41-167">So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="57a41-168">チームのボイスメール機能についてユーザーが理解できるようにする</span><span class="sxs-lookup"><span data-stu-id="57a41-168">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="57a41-169">ボイスメールの設定と Teams のその他の通話機能の管理については、次の情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="57a41-169">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="57a41-170">[Teams で通話設定を管理](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)します。</span><span class="sxs-lookup"><span data-stu-id="57a41-170">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="57a41-171">この記事では、すべてのエンドユーザーチームの通話機能を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="57a41-171">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="57a41-172">Skype for Business ボイスメールの機能に関するユーザーの理解を支援する</span><span class="sxs-lookup"><span data-stu-id="57a41-172">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="57a41-p115">ユーザーが Skype for Business ボイスメールを正しく使用できるように支援するためのトレーニング情報と記事が用意されています。以下の記事をユーザーに紹介してください。</span><span class="sxs-lookup"><span data-stu-id="57a41-p115">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>

- <span data-ttu-id="57a41-175">[Skype for Business ボイス メールの確認とオプション](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): この記事では、Skype for Business でボイスメールを再生し、ボイスメール応答メッセージを変更し、ボイスメールの設定を変更し、ボイスメールを異なる速度で再生する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="57a41-175">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="57a41-176">Skype for Business 2016 トレーニング</span><span class="sxs-lookup"><span data-stu-id="57a41-176">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="57a41-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="57a41-177">Related topics</span></span>
[<span data-ttu-id="57a41-178">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="57a41-178">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="57a41-179">電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="57a41-179">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="57a41-180">Skype for Business Server と Exchange Server の移行の計画</span><span class="sxs-lookup"><span data-stu-id="57a41-180">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
