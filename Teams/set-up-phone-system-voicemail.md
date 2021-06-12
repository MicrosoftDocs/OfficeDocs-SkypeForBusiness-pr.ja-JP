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
description: 'ユーザーのアカウントをクラウド ボイスメールする方法について学習します。 '
ms.openlocfilehash: c6fbd02e30c5be0280b05088a1cec281c2534039
ms.sourcegitcommit: 31c5b9cd3d4f500e1f9d7823052dae8f8c298b1e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2021
ms.locfileid: "52901914"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="7e6d3-103">クラウド ボイスメールのセットアップ</span><span class="sxs-lookup"><span data-stu-id="7e6d3-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="7e6d3-104">この記事は、Microsoft 365 または Office 365 管理者向けです。詳細については、「クラウド ボイスメール 機能を設定する管理者ロールについて」を参照してください。 [](/microsoft-365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="7e6d3-104">This article is for the Microsoft 365 or Office 365 admin as described in [About admin roles](/microsoft-365/admin/add-users/about-admin-roles) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="7e6d3-105">クラウド ボイスメールは、ボイスメール メッセージの受信をExchange、サード パーティのメール システムをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

> [!NOTE]
> <span data-ttu-id="7e6d3-106">代理人が委任者の代理で通話に応答すると、その代理人の通知クラウド ボイスメール。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-106">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="7e6d3-107">ユーザーは、着信を見逃した場合に通知を受け取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-107">Users can receive notifications for missed calls.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a><span data-ttu-id="7e6d3-108">クラウド専用環境: オンライン ユーザー向クラウド ボイスメールを電話システムする</span><span class="sxs-lookup"><span data-stu-id="7e6d3-108">Cloud-only environments: Set up Cloud Voicemail for Online Phone System users</span></span>

<span data-ttu-id="7e6d3-109">Online 電話システムの場合、クラウド ボイスメールにユーザーのライセンスを割り当てると、電話システム **が自動的** に設定され、プロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-109">For Online Phone System users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license to the users.</span></span> 

> [!NOTE]
> <span data-ttu-id="7e6d3-110">オンプレミスでSkype for Business 電話システム指定された電話番号を持つオンライン ユーザーの場合[、Set-CsUser -HostedVoicemail](/powershell/module/skype/set-csuser?view=skype-ps)を使用してホスト型ボイス メールを有効にする必要$True。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-110">For Online Skype for Business Phone System users with on-premises provided phone numbers, you may need to enable hosted voice mail with [Set-CsUser -HostedVoicemail $True](/powershell/module/skype/set-csuser?view=skype-ps).</span></span> 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="7e6d3-111">メールボックス ユーザークラウド ボイスメールのExchange Server設定</span><span class="sxs-lookup"><span data-stu-id="7e6d3-111">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="7e6d3-112">次の情報は、オンラインのユーザークラウド ボイスメールがメールボックスを持っているユーザーと一緒に作業電話システムを構成する方法についてExchange Server。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-112">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="7e6d3-113">ボイスメール メッセージは、ユーザーのメールボックスに配信されExchange経由でルーティングされた SMTP 経由でExchange Online Protection。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-113">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="7e6d3-114">これらのメッセージの正常な配信を有効にするには、Exchange コネクタがサーバーとサーバー間で正しく構成Exchange確認Exchange Online Protection。[コネクタを使用してメール アドレスを構成Flow。](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)</span><span class="sxs-lookup"><span data-stu-id="7e6d3-114">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

2. <span data-ttu-id="7e6d3-115">Skype for Business クライアントであいさつ応答メッセージやビジュアル ボイスメールのカスタマイズなどのボイスメール機能を有効にするには、Microsoft 365 または Office 365 から Exchange Web サービスを介した Exchange サーバー メールボックスへの接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-115">To enable Voicemail features such as customizing greetings and visual voicemail in Skype for Business clients, connectivity from Microsoft 365 or Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="7e6d3-116">この接続を有効にするには、「Exchange 組織と Exchange Online 組織間の[OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)認証の構成」で説明されている新しい Exchange Oauth 認証プロトコルを構成するか、Exchange 2013 CU5 以上から Exchange ハイブリッド ウィザードを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-116">To enable this connectivity, you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="7e6d3-117">さらに、Skype for Business Online と Exchange Server の間で統合と Oauth を構成する必要があります。詳細については[、「Skype for Business Online](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)と Exchange Server の間の統合と OAuth の構成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-117">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="7e6d3-118">ユーザーのクラウド ボイスメール設定Skype for Business Serverする</span><span class="sxs-lookup"><span data-stu-id="7e6d3-118">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="7e6d3-119">サーバー ユーザー Skype for Businessを構成クラウド ボイスメール、オンプレミス ユーザーの クラウド ボイスメール[サービスの計画に関するページを参照してください](/skypeforbusiness/hybrid/plan-cloud-voicemail)。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-119">To configure Skype for Business server users for Cloud Voicemail, please see [Plan Cloud Voicemail service for on-premises users](/skypeforbusiness/hybrid/plan-cloud-voicemail).</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="7e6d3-120">組織で保護されたボイスメールを有効にする</span><span class="sxs-lookup"><span data-stu-id="7e6d3-120">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="7e6d3-121">組織内のユーザーのボイスメール メッセージを他のユーザーが離れる場合、ボイスメールはメール メッセージの添付ファイルとしてユーザーのメールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-121">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="7e6d3-122">メール フロー ルールを使用してメッセージの暗号化を適用すると、これらのボイスメール メッセージが他の受信者に転送されるのを防ぐことが可能です。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-122">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="7e6d3-123">保護されたボイスメールを有効にした場合、ユーザーは、ボイスメール メールボックスを呼び出したり、Web 上の Outlook、Outlook、または Android または iOS の Outlook でメッセージを開いて、保護されたボイスメール メッセージをリッスンできます。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-123">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="7e6d3-124">保護されたボイスメール メッセージは、Skype for BusinessまたはMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-124">Protected voicemail messages can't be opened in Skype for Business or Microsoft Teams.</span></span>

<span data-ttu-id="7e6d3-125">メッセージの暗号化の詳細については、「電子メールの暗号化」 [を参照してください](/microsoft-365/compliance/email-encryption?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-125">For more information about message encryption, see [Email encryption](/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="7e6d3-126">保護されたボイスメールを設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-126">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="7e6d3-127">グローバル管理者 https://admin.microsoft.com アクセス許可を持つアカウントを使用して に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-127">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="7e6d3-128">[すべて **表示] を** 選択し、[管理センター]**に移動**  >  **Exchange。**</span><span class="sxs-lookup"><span data-stu-id="7e6d3-128">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="7e6d3-129">[管理センター Exchangeで、[メール フロールール **] を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-129">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="7e6d3-130">[追加 **+** **]** を選択し、[**メッセージにOffice 365 Message Encryption保護を適用する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-130">Select **+** **Add**, and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="7e6d3-131">新しいメール フロー ルールの名前を指定し、[このルールを適用する場合] で、[メッセージのプロパティにメッセージの種類を含める] [ボイス メール]  >    >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-131">Provide a name for the new mail flow rule and then under **Apply this rule if**, select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="7e6d3-132">**[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-132">Select **OK**.</span></span>
6. <span data-ttu-id="7e6d3-133">[**次の操作を行う**] で **、[Office 365 Message Encryption保護** と権限保護をメッセージに適用する] を選択し、[1 つ選択]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-133">Under **Do the following**, select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="7e6d3-134">[RMS **テンプレート] で**、[転送しない **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-134">Under **RMS template**, select **Do not forward**.</span></span> <span data-ttu-id="7e6d3-135">**[OK] を選択** し、[保存]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-135">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="7e6d3-136">RMS テンプレート **の一覧が** 空の場合は、Message Encryption を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-136">If the **RMS template** list is empty, you need to set up Message Encryption.</span></span> <span data-ttu-id="7e6d3-137">Message Encryption の設定の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-137">For more information about setting up Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="7e6d3-138">新しい Message Encryption 機能を設定する</span><span class="sxs-lookup"><span data-stu-id="7e6d3-138">Set up new Message Encryption capabilities</span></span>](/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="7e6d3-139">Azure Information Protection のテンプレートの構成と管理</span><span class="sxs-lookup"><span data-stu-id="7e6d3-139">Configuring and managing templates for Azure Information Protection</span></span>](/information-protection/deploy-use/configure-policy-templates)
    > - <span data-ttu-id="7e6d3-140">[メールの [転送しない] オプション](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="7e6d3-140">[Do Not Forward option for emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="7e6d3-141">ユーザーがボイスメール機能Teams学習する</span><span class="sxs-lookup"><span data-stu-id="7e6d3-141">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="7e6d3-142">ボイスメール設定の管理に関するユーザー向け情報と、その他の通話機能については、以下の情報Teams。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-142">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="7e6d3-143">[で通話設定を管理Teams。](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="7e6d3-143">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="7e6d3-144">この記事では、すべてのエンド ユーザーと通話機能を管理Teams説明します。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-144">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="7e6d3-145">Skype for Business ボイスメールの機能に関するユーザーの理解を支援する</span><span class="sxs-lookup"><span data-stu-id="7e6d3-145">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="7e6d3-p109">ユーザーが Skype for Business ボイスメールを正しく使用できるように支援するためのトレーニング情報と記事が用意されています。以下の記事をユーザーに紹介してください。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-p109">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>

- <span data-ttu-id="7e6d3-148">[Skype for Business ボイス メールの確認とオプション](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): この記事では、Skype for Business でボイスメールを再生し、ボイスメール応答メッセージを変更し、ボイスメールの設定を変更し、ボイスメールを異なる速度で再生する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e6d3-148">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="7e6d3-149">Skype for Business 2016 トレーニング</span><span class="sxs-lookup"><span data-stu-id="7e6d3-149">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="7e6d3-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e6d3-150">Related topics</span></span>
[<span data-ttu-id="7e6d3-151">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="7e6d3-151">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="7e6d3-152">電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="7e6d3-152">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="7e6d3-153">Skype for Business Server と Exchange Server の移行の計画</span><span class="sxs-lookup"><span data-stu-id="7e6d3-153">Plan for Skype for Business Server and Exchange Server migration</span></span>](/SkypeForBusiness/hybrid/plan-um-migration)
