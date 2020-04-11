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
ms.openlocfilehash: dc771847db8dca52d22b4c1db1b8ae585b99f8e4
ms.sourcegitcommit: 2d44f1a673316daf0aca3149571b24a63ca72772
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2020
ms.locfileid: "43227501"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="b469e-103">クラウド ボイスメールのセットアップ</span><span class="sxs-lookup"><span data-stu-id="b469e-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="b469e-104">この記事は、社内のすべてのユーザーにクラウドボイスメール機能を設定する必要がある[Office 365 管理者](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)を対象としています。</span><span class="sxs-lookup"><span data-stu-id="b469e-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="b469e-105">クラウドボイスメールでは、Exchange メールボックスでのボイスメールメッセージのデポジットのみがサポートされ、サードパーティのメールシステムはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="b469e-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a><span data-ttu-id="b469e-106">クラウドのみの環境: クラウドボイスメールをセットアップする</span><span class="sxs-lookup"><span data-stu-id="b469e-106">Cloud-only environments: Set up Cloud Voicemail</span></span>

<span data-ttu-id="b469e-107">Skype for Business Online と通話プランのユーザーには、**電話システム**のライセンスと電話番号を割り当てた後で、クラウドボイスメールが自動的に設定され、ユーザーに提供されます。</span><span class="sxs-lookup"><span data-stu-id="b469e-107">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="b469e-108">電話システム機能がプランに含まれていない場合は、 **電話システム** アドオン ライセンスの購入が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="b469e-108">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="b469e-109">Exchange Online ライセンスの購入も必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b469e-109">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="b469e-110">「 [Microsoft Teams のアドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b469e-110">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="b469e-111">一般[法人向け Office 365 のライセンスの割り当てまたは削除](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、 [Microsoft Teams ライセンスの割り当て](assign-teams-licenses.md)、および組織内のユーザーへの Exchange Online ライセンスの割り当てまたは削除を行います。</span><span class="sxs-lookup"><span data-stu-id="b469e-111">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="b469e-112">これが完了すると、メンバーはボイスメール メッセージを受信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b469e-112">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="b469e-p103">ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。Windows PowerShell を使用し、下記の手順を実行することによって、所属する組織のトランスクリプションを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b469e-p103">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="b469e-115">オンプレミス環境での電話システム</span><span class="sxs-lookup"><span data-stu-id="b469e-115">Phone System with on-premises environments</span></span>

<span data-ttu-id="b469e-116">次の情報は、オンプレミスの通話プラン環境で動作するようにクラウドボイスメールを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b469e-116">The following information is about configuring Cloud Voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="b469e-117">電話システム機能がプランに含まれていない場合は、 **電話システム** アドオン ライセンスの購入が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="b469e-117">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="b469e-118">Exchange Online ライセンスの購入も必要になります。</span><span class="sxs-lookup"><span data-stu-id="b469e-118">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="b469e-119">「 [Microsoft Teams のアドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b469e-119">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="b469e-120">一般[法人向け Office 365 のライセンスの割り当てまたは削除](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、 [Microsoft Teams ライセンスの割り当て](assign-teams-licenses.md)、および組織内のユーザーへの Exchange Online ライセンスの割り当てまたは削除を行います。</span><span class="sxs-lookup"><span data-stu-id="b469e-120">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="b469e-121">ユーザーに展開されているオンプレミス PSTN 通話ソリューションと一致する指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="b469e-121">Follow instructions matching on-premises PSTN calling solution deployed for your users.</span></span> <span data-ttu-id="b469e-122">Cloud Connector Edition の場合は、「 [Skype For Business Cloud Connector エディションの構成](https://technet.microsoft.com/library/mt605228.aspx)」の「**電話システムの音声およびボイスメールサービスのユーザーを有効にする**」セクションの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b469e-122">For Cloud Connector Edition, follow instructions in the **Enable users for Phone System voice and voicemail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span> <span data-ttu-id="b469e-123">Skype for Business Server での PSTN 通話については、「[エンタープライズボイスオンプレミスのユーザーを有効にする](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b469e-123">For PSTN calling with Skype for Business Server, follow [Enable the users for Enterprise Voice on premises](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span></span> <span data-ttu-id="b469e-124">Teams のダイレクトルーティングの場合は、「**電話番号を設定し、エンタープライズボイスメールとボイスメールを有効に**する」のセクションに従って、[ [Direct ルーティングの構成](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b469e-124">For Teams Direct Routing, follow  the **Configure the phone number and enable enterprise voice and voicemail** section of [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span></span>

4. <span data-ttu-id="b469e-p106">ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。Windows PowerShell を使用し、下記の手順を実行することによって、所属する組織のトランスクリプションを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b469e-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="b469e-127">ボイスメールメッセージは、Exchange Online Protection を介してルーティングされる SMTP 経由で、ユーザーの Exchange メールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="b469e-127">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="b469e-128">これらのメッセージが正常に配信されるようにするには、exchange サーバーと Exchange Online Protection の間で Exchange コネクタが正しく構成されていることを確認します。[コネクタを使用して、メールフローを構成](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)します。</span><span class="sxs-lookup"><span data-stu-id="b469e-128">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

6. <span data-ttu-id="b469e-129">Skype for Business クライアントで、グリーティングのカスタマイズや、視覚ボイスメールなどのボイスメール機能を有効にするには、Exchange Web Services を使用した Office 365 から Exchange server メールボックスへの接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="b469e-129">To enable Voicemail features such as customizing greetings, and visual voicemail in Skype for Business clients, connectivity from Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="b469e-130">この接続を有効にするには、「 [exchange と Exchange Online 組織の間での Oauth 認証の構成](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)」で説明されている新しい exchange Oauth 認証プロトコルを構成するか、Exchange ハイブリッドウィザードを EXCHANGE 2013 cu5 以降以上で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b469e-130">To enable this connectivity you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="b469e-131">さらに、「skype for business [online と Exchange server の間の統合と oauth の構成](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)」で説明されているように、Skype For business Online と exchange server の間で統合と oauth を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b469e-131">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

> [!NOTE]
> <span data-ttu-id="b469e-132">代理人が委任者の代わりに着信に応答する場合、クラウドボイスメールでは通知を利用できません。</span><span class="sxs-lookup"><span data-stu-id="b469e-132">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="b469e-133">不在着信の通知は、ユーザーが受信できます。</span><span class="sxs-lookup"><span data-stu-id="b469e-133">Users can receive notifications for missed calls.</span></span>

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="b469e-134">組織内のボイスメール ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="b469e-134">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="b469e-135">Skype for Business のお客様の場合、Microsoft Teams の通話ポリシーでボイスメールを無効にすると、Skype for Business ユーザーのボイスメールサービスを無効にすることがあります。</span><span class="sxs-lookup"><span data-stu-id="b469e-135">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="b469e-136">既定では、すべての組織とユーザーに対して、ボイスメール トランスクリプションは有効に、トランスクリプション不適切表現マスキングは無効になっています。ただし、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) と [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) コマンドレットを使用してそれらを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="b469e-136">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="b469e-137">組織内のユーザーから受信したボイスメールメッセージは、Office 365 テナントがホストされている地域に transcribed されています。</span><span class="sxs-lookup"><span data-stu-id="b469e-137">Voicemail messages received by users in your organization are transcribed in the region where your Office 365 tenant is hosted.</span></span> <span data-ttu-id="b469e-138">テナントがホストされている地域は、ボイスメールメッセージを受信するユーザーが配置されている地域とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b469e-138">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="b469e-139">テナントがホストされている地域を表示するには、[[組織プロファイル](https://go.microsoft.com/fwlink/p/?linkid=2067339)] ページに移動し、[**データの場所**] の横にある [詳細の**表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b469e-139">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b469e-140">**New-csonlinevoicemailpolicy**コマンドレットを使って、書き起こしと議事録のプロファニティマスク用の新しいポリシーインスタンスを作成することはできません。また、 **new-csonlinevoicemailpolicy**コマンドレットを使用して既存のポリシーインスタンスを削除することもできません。</span><span class="sxs-lookup"><span data-stu-id="b469e-140">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="b469e-141">ボイスメール ポリシーを使用してユーザーのトランスクリプション設定を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="b469e-141">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="b469e-142">利用可能なボイスメールポリシーのすべてのインスタンスを表示するには、 [new-csonlinevoicemailpolicy](https://technet.microsoft.com/library/mt798311.aspx)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b469e-142">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="b469e-143">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="b469e-143">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="b469e-145">組織のトランスクリプションをオフにする</span><span class="sxs-lookup"><span data-stu-id="b469e-145">Turning off transcription for your organization</span></span>

<span data-ttu-id="b469e-p112">組織のトランスクリプションに関する既定の設定はオンになっており、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) を使用して無効にすることができます。これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="b469e-p112">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="b469e-148">組織のトランスクリプション不適切表現マスキングをオンにする。</span><span class="sxs-lookup"><span data-stu-id="b469e-148">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="b469e-149">組織では、トランスクリプション不適切表現マスキングは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="b469e-149">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="b469e-150">マスキングを有効にしなければならないビジネス上の要件がある場合は、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) を使用してトランスクリプション不適切表現マスキングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b469e-150">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="b469e-151">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="b469e-151">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="b469e-152">ユーザーのトランスクリプションをオフにする</span><span class="sxs-lookup"><span data-stu-id="b469e-152">Turning off transcription for a user</span></span>

<span data-ttu-id="b469e-153">ユーザー ポリシーは組織の既定の設定より前に評価されます。</span><span class="sxs-lookup"><span data-stu-id="b469e-153">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="b469e-154">たとえば、すべてのユーザーに対してボイスメールの議事録が有効になっている場合は、 [new-csonlinevoicemailpolicy](https://technet.microsoft.com/library/mt798309.aspx)コマンドレットを使用して、特定のユーザーに対して議事録を無効にするポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b469e-154">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="b469e-155">単一ユーザーに対するトランスクリプションを無効にするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="b469e-155">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="b469e-156">ユーザーのトランスクリプション不適切表現マスキングをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b469e-156">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="b469e-157">特定のユーザーに対してトランスクリプション不適切表現マスキングを有効にするには、ポリシーを割り当てて、[Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) コマンドレットを使用して特定のユーザーに対するトランスクリプション不適切表現マスキングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b469e-157">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="b469e-158">単一ユーザーに対するトランスクリプション不適切表現マスキングを有効にするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="b469e-158">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="b469e-p115">Office 365 のボイスメール サービスによってボイスメール ポリシーがキャッシュされ、4 時間ごとにキャッシュが更新されます。このため、ポリシーを変更した場合、変更が適用されるまでに最長で 4 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b469e-p115">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="b469e-161">チームのボイスメール機能についてユーザーが理解できるようにする</span><span class="sxs-lookup"><span data-stu-id="b469e-161">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="b469e-162">ボイスメールの設定と Teams のその他の通話機能の管理については、次の情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="b469e-162">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="b469e-163">[Teams で通話設定を管理](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)します。</span><span class="sxs-lookup"><span data-stu-id="b469e-163">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="b469e-164">この記事では、すべてのエンドユーザーチームの通話機能を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b469e-164">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="b469e-165">Skype for Business ボイスメールの機能に関するユーザーの理解を支援する</span><span class="sxs-lookup"><span data-stu-id="b469e-165">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="b469e-p117">ユーザーが Skype for Business ボイスメールを正しく使用できるように支援するためのトレーニング情報と記事が用意されています。以下の記事をユーザーに紹介してください。</span><span class="sxs-lookup"><span data-stu-id="b469e-p117">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>

- <span data-ttu-id="b469e-168">[Skype for Business ボイス メールの確認とオプション](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): この記事では、Skype for Business でボイスメールを再生し、ボイスメール応答メッセージを変更し、ボイスメールの設定を変更し、ボイスメールを異なる速度で再生する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b469e-168">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="b469e-169">Skype for Business 2016 トレーニング</span><span class="sxs-lookup"><span data-stu-id="b469e-169">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="b469e-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="b469e-170">Related topics</span></span>
[<span data-ttu-id="b469e-171">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="b469e-171">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="b469e-172">Office 365 での電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="b469e-172">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="b469e-173">Skype for Business Server と Exchange Server の移行の計画</span><span class="sxs-lookup"><span data-stu-id="b469e-173">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)

