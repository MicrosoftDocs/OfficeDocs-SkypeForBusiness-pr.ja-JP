---
title: ユーザーに直接ルーティングを有効にする
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Microsoft Phone System Direct Routing を有効にする方法について説明します。
ms.openlocfilehash: 972bd8d5e01a050a67978560b8de272439fda40d
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421312"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="c4c11-103">ユーザーに直接ルーティング、音声、ボイスメールを有効にする</span><span class="sxs-lookup"><span data-stu-id="c4c11-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="c4c11-104">この記事では、ユーザーが電話システムダイレクト ルーティングを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4c11-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="c4c11-105">これは、ダイレクト ルーティングを構成するための次の手順の手順 2 です。</span><span class="sxs-lookup"><span data-stu-id="c4c11-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="c4c11-106">手順 1.</span><span class="sxs-lookup"><span data-stu-id="c4c11-106">Step 1.</span></span> [<span data-ttu-id="c4c11-107">SBC を Microsoft Phone System に接続し、接続を検証する</span><span class="sxs-lookup"><span data-stu-id="c4c11-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="c4c11-108">**手順 2.ユーザーに直接ルーティング、音声、ボイスメールを有効にする**   (この記事)</span><span class="sxs-lookup"><span data-stu-id="c4c11-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="c4c11-109">手順 3.</span><span class="sxs-lookup"><span data-stu-id="c4c11-109">Step 3.</span></span> [<span data-ttu-id="c4c11-110">音声ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="c4c11-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="c4c11-111">手順 4.</span><span class="sxs-lookup"><span data-stu-id="c4c11-111">Step 4.</span></span> [<span data-ttu-id="c4c11-112">数値を別の形式に翻訳する</span><span class="sxs-lookup"><span data-stu-id="c4c11-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="c4c11-113">ダイレクト ルーティングを設定するために必要なすべての手順については、「ダイレクト ルーティングを構成する」を [参照してください](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="c4c11-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="c4c11-114">ユーザーに直接ルーティングを有効にする準備ができたら、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c4c11-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="c4c11-115">Microsoft 365 または Office 365 でユーザーを作成し、電話システム ライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="c4c11-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="c4c11-116">ユーザーが Skype for Business Online にホームとして登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4c11-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="c4c11-117">電話番号を構成し、エンタープライズボイスメールとボイスメールを有効にする。</span><span class="sxs-lookup"><span data-stu-id="c4c11-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="c4c11-118">Teams Only モードをユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="c4c11-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="c4c11-119">ユーザーを作成してライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c4c11-119">Create a user and assign the license</span></span> 

<span data-ttu-id="c4c11-120">Microsoft 365 または Office 365 で新しいユーザーを作成するには、2 つのOfficeがあります。</span><span class="sxs-lookup"><span data-stu-id="c4c11-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="c4c11-121">ただし、ルーティングの問題を回避するには、組織で 1 つのオプションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4c11-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="c4c11-122">オンプレミスの Active Directory でユーザーを作成し、ユーザーをクラウドと同期します。</span><span class="sxs-lookup"><span data-stu-id="c4c11-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="c4c11-123">「 [オンプレミスのディレクトリを Azure Active Directory と統合する」を参照してください](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。</span><span class="sxs-lookup"><span data-stu-id="c4c11-123">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="c4c11-124">Microsoft 365 管理センターでユーザーを直接作成します。</span><span class="sxs-lookup"><span data-stu-id="c4c11-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="c4c11-125">「Microsoft [365 または Office 365](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)にユーザーを個別または一括で追加する - 管理者向けヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4c11-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="c4c11-126">Skype for Business Online 展開が Skype for Business 2015 または Lync 2010 または 2013 オンプレミスと共存している場合、サポートされる唯一のオプションは、オンプレミスの Active Directory でユーザーを作成し、ユーザーをクラウドと同期することだけです (オプション 1)。</span><span class="sxs-lookup"><span data-stu-id="c4c11-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="c4c11-127">ライセンス要件の詳細については、「プラン ダイレクト ルーティング」のライセンスと他[の](direct-routing-plan.md#licensing-and-other-requirements)[要件を参照してください](direct-routing-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="c4c11-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a><span data-ttu-id="c4c11-128">ユーザーがオンラインで自宅にいて、電話番号がオンプレミスから同期されていない (Skype for Business Server エンタープライズ VoIP でユーザーを Teams ダイレクト ルーティングに移行できる)</span><span class="sxs-lookup"><span data-stu-id="c4c11-128">Ensure that the user is homed online and phone number is not being synced from on-premises (applicable for Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing)</span></span>

<span data-ttu-id="c4c11-129">直接ルーティングを使用するには、ユーザーをオンラインで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4c11-129">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="c4c11-130">RegistrarPool パラメーター (ドメイン内に値が必要) を調infra.lync.comできます。</span><span class="sxs-lookup"><span data-stu-id="c4c11-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="c4c11-131">OnPremLineUriManuallySet パラメーターも True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4c11-131">OnPremLineUriManuallySet parameter should also to be set to True.</span></span> <span data-ttu-id="c4c11-132">これは、電話番号を構成し、Skype for Business Online PowerShell を使用してエンタープライズボイスメールとボイスメールを有効にすることで実現されます。</span><span class="sxs-lookup"><span data-stu-id="c4c11-132">This is achieved by configuring the phone number and enable enterprise voice and voicemail using Skype for Business Online PowerShell.</span></span>

1. <span data-ttu-id="c4c11-133">Skype for Business Online PowerShell セッションに接続します。</span><span class="sxs-lookup"><span data-stu-id="c4c11-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="c4c11-134">コマンドを発行します。</span><span class="sxs-lookup"><span data-stu-id="c4c11-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="c4c11-135">OnPremLineUriManuallySet が False に設定され、LineUri に <E.164 電話番号> が設定されている場合は、Skype for Business Online PowerShell を使用して電話番号を構成する前に、オンプレミスの Skype for Business 管理シェルを使用してパラメーターをクリーンアップしてください。</span><span class="sxs-lookup"><span data-stu-id="c4c11-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, please clean the parameters using on-premises Skype for Business Management Shell, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="c4c11-136">Skype for Business 管理シェルからコマンドを発行します。</span><span class="sxs-lookup"><span data-stu-id="c4c11-136">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   <span data-ttu-id="c4c11-137">変更が 365 に同期Office、期待される出力は `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` 次の結果です。</span><span class="sxs-lookup"><span data-stu-id="c4c11-137">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="c4c11-138">電話番号を構成し、エンタープライズボイスメールとボイスメールを有効にする</span><span class="sxs-lookup"><span data-stu-id="c4c11-138">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="c4c11-139">ユーザーを作成し、ライセンスを割り当てしたら、次の手順では、ユーザーの電話番号とボイスメールを構成します。</span><span class="sxs-lookup"><span data-stu-id="c4c11-139">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="c4c11-140">電話番号を追加してボイスメールを有効にするには:</span><span class="sxs-lookup"><span data-stu-id="c4c11-140">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="c4c11-141">Skype for Business Online PowerShell セッションに接続します。</span><span class="sxs-lookup"><span data-stu-id="c4c11-141">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="c4c11-142">コマンドを発行します。</span><span class="sxs-lookup"><span data-stu-id="c4c11-142">Issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    <span data-ttu-id="c4c11-143">たとえば、ユーザー "Spencer Low" の電話番号を追加するには、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="c4c11-143">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    <span data-ttu-id="c4c11-144">ユーザー "Spencer Low" と "Stacy Quinn" が一意の拡張子を持つ同じベース番号を共有する場合は、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="c4c11-144">If the users "Spencer Low" and "Stacy Quinn" share the same base number with unique extensions, enter the following</span></span>
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="c4c11-145">使用する電話番号が国コードを含む完全な E.164 電話番号として構成されていることをお勧めしますが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="c4c11-145">It's recommended, but not required, that the phone number used is configured as a full E.164 phone number with country code.</span></span> <span data-ttu-id="c4c11-146">ベース番号に対する参照が複数の結果を返す場合にユーザーを参照するために使用される内線番号を使用して電話番号を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="c4c11-146">It is supported to configure phone numbers with extensions which will be used to lookup users when the lookup against the base number returns more than one result.</span></span> <span data-ttu-id="c4c11-147">これにより、会社は同じ基本番号と一意の内線番号を持つ電話番号を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c4c11-147">This allows companies to configure phone numbers with the same base number and unique extensions.</span></span> <span data-ttu-id="c4c11-148">参照を成功するには、招待には、次のように、拡張子が付く完全な番号を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4c11-148">For lookup to be successful, the invite must include the full number with extension as follows:</span></span>
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > <span data-ttu-id="c4c11-149">ユーザーの電話番号がオンプレミスで管理されている場合は、オンプレミスの Skype for Business 管理シェルまたはコントロール パネルを使用して、ユーザーの電話番号を構成します。</span><span class="sxs-lookup"><span data-stu-id="c4c11-149">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="c4c11-150">ボイスメールに通話を直接送信する構成</span><span class="sxs-lookup"><span data-stu-id="c4c11-150">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="c4c11-151">直接ルーティングを使用すると、ユーザーへの通話を終了し、ユーザーのボイスメールに直接送信することができます。</span><span class="sxs-lookup"><span data-stu-id="c4c11-151">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="c4c11-152">通話をボイスメールに直接送信する場合は、OPAQUE=app:voicemail を Request URI ヘッダーに添付します。</span><span class="sxs-lookup"><span data-stu-id="c4c11-152">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="c4c11-153">たとえば、"sip:user@yourdomain.com;opaque=app:voicemail" などです。</span><span class="sxs-lookup"><span data-stu-id="c4c11-153">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="c4c11-154">この場合、Teams ユーザーは通話通知を受け取り、通話はユーザーのボイスメールに直接接続されます。</span><span class="sxs-lookup"><span data-stu-id="c4c11-154">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="c4c11-155">Teams Only モードをユーザーに割り当て、通話が確実に Microsoft Teams に着信する</span><span class="sxs-lookup"><span data-stu-id="c4c11-155">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="c4c11-156">直接ルーティングでは、ユーザーが Teams クライアントに着信通話を確実に発信するには、Teams Only モードである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4c11-156">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="c4c11-157">ユーザーを Teams のみモードにする場合は、TeamsUpgradePolicy の "UpgradeToTeams" インスタンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4c11-157">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="c4c11-158">詳細については [、IT 管理者向けアップグレード戦略を参照してください](upgrade-to-teams-on-prem-implement.md)。</span><span class="sxs-lookup"><span data-stu-id="c4c11-158">For more information, see [Upgrade strategies for IT administrators](upgrade-to-teams-on-prem-implement.md).</span></span> <span data-ttu-id="c4c11-159">組織で Skype for Business Server または Skype for Business Online を使用している場合、Skype と Teams の相互運用性については、次の記事を参照してください [。Skype for Business](migration-interop-guidance-for-teams-with-skype.md)との移行と相互運用性。</span><span class="sxs-lookup"><span data-stu-id="c4c11-159">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c4c11-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4c11-160">See also</span></span>

[<span data-ttu-id="c4c11-161">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="c4c11-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="c4c11-162">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="c4c11-162">Configure Direct Routing</span></span>](direct-routing-configure.md)
