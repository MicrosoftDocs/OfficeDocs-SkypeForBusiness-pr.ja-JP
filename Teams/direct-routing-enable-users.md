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
description: システム ダイレクト ルーティングを使用してユーザー Microsoft 電話する方法について説明します。
ms.openlocfilehash: 86132778226702577068d9502ae46cba949667c6
ms.sourcegitcommit: 5df33e7fe912426e3e158b3be7334e05dc3803a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "53345713"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="be044-103">ダイレクト ルーティング、音声、ボイスメールのユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="be044-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="be044-104">この記事では、直接ルーティングでユーザーを有効にする電話システム説明します。</span><span class="sxs-lookup"><span data-stu-id="be044-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="be044-105">これは、ダイレクト ルーティングを構成するための次の手順の手順 2 です。</span><span class="sxs-lookup"><span data-stu-id="be044-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="be044-106">手順 1.</span><span class="sxs-lookup"><span data-stu-id="be044-106">Step 1.</span></span> [<span data-ttu-id="be044-107">Connect システムを使用して SBC Microsoft 電話し、接続を検証する</span><span class="sxs-lookup"><span data-stu-id="be044-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="be044-108">**手順 2.ダイレクト ルーティング、音声、ボイスメールのユーザーを有効にする**   (この記事)</span><span class="sxs-lookup"><span data-stu-id="be044-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="be044-109">手順 3.</span><span class="sxs-lookup"><span data-stu-id="be044-109">Step 3.</span></span> [<span data-ttu-id="be044-110">音声ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="be044-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="be044-111">手順 4.</span><span class="sxs-lookup"><span data-stu-id="be044-111">Step 4.</span></span> [<span data-ttu-id="be044-112">数値を別の形式に変換する</span><span class="sxs-lookup"><span data-stu-id="be044-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="be044-113">ダイレクト ルーティングを設定するために必要なすべての手順については、「ダイレクト ルーティングの構成 [」を参照してください](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="be044-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="be044-114">ユーザーが直接ルーティングを有効にする準備ができたら、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="be044-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="be044-115">ユーザーを管理者またはMicrosoft 365作成Office 365ライセンスを割り電話システムします。</span><span class="sxs-lookup"><span data-stu-id="be044-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="be044-116">ユーザーがオンラインでホームSkype for Businessします。</span><span class="sxs-lookup"><span data-stu-id="be044-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="be044-117">電話番号を構成し、エンタープライズ音声とボイスメールを有効にする。</span><span class="sxs-lookup"><span data-stu-id="be044-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="be044-118">ユーザーにTeamsのみモードを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="be044-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="be044-119">ユーザーを作成してライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="be044-119">Create a user and assign the license</span></span>

<span data-ttu-id="be044-120">新しいユーザーを作成するには、2 つのオプションMicrosoft 365またはOffice 365。</span><span class="sxs-lookup"><span data-stu-id="be044-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="be044-121">ただし、ルーティングの問題を回避するために、組織で 1 つのオプションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be044-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="be044-122">オンプレミスの Active Directory にユーザーを作成し、そのユーザーをクラウドと同期します。</span><span class="sxs-lookup"><span data-stu-id="be044-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="be044-123">「[オンプレミスのディレクトリを Azure Active Directory」を参照してください](/azure/active-directory/connect/active-directory-aadconnect)。</span><span class="sxs-lookup"><span data-stu-id="be044-123">See [Integrate your on-premises directories with Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="be044-124">ユーザーを作成するには、Microsoft 365 管理センター。</span><span class="sxs-lookup"><span data-stu-id="be044-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="be044-125">「[ユーザーを個別に、または一括でユーザーを追加する」Microsoft 365または Office 365 - 管理者向けヘルプ を参照してください](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。</span><span class="sxs-lookup"><span data-stu-id="be044-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="be044-126">Skype for Business Online の展開がオンプレミスの Skype for Business 2015 または Lync 2010 または 2013 と共存している場合、サポートされている唯一のオプションは、オンプレミスの Active Directory にユーザーを作成し、ユーザーをクラウドと同期することだけです (オプション 1)。</span><span class="sxs-lookup"><span data-stu-id="be044-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="be044-127">ライセンス要件の詳細については、「直接ルーティングの計画」の「ライセンスと[他の](direct-routing-plan.md#licensing-and-other-requirements)[要件」を参照してください](direct-routing-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="be044-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online"></a><span data-ttu-id="be044-128">ユーザーがオンラインでホームに設定されている</span><span class="sxs-lookup"><span data-stu-id="be044-128">Ensure that the user is homed online</span></span> 

<span data-ttu-id="be044-129">この手順は、有効なユーザー Skype for Business Server エンタープライズ VoIP直接ルーティングに移行Teams適用されます。</span><span class="sxs-lookup"><span data-stu-id="be044-129">This step is applicable to Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing.</span></span>

<span data-ttu-id="be044-130">ダイレクト ルーティングでは、ユーザーをオンラインでホームに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be044-130">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="be044-131">RegistrarPool パラメーターを確認すると確認できます。このパラメーターには、infra.lync.com があります。</span><span class="sxs-lookup"><span data-stu-id="be044-131">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="be044-132">また、ユーザーを直接ルーティングに移行するときに、LineURI の管理をオンプレミスからオンラインに変更Teamsです。</span><span class="sxs-lookup"><span data-stu-id="be044-132">It's also recommended, but not required, to change management of the LineURI from on-premises to online when migrating users to Teams Direct Routing.</span></span> 

1. <span data-ttu-id="be044-133">Connect Online PowerShell Skype for Businessセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="be044-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="be044-134">コマンドを発行します。</span><span class="sxs-lookup"><span data-stu-id="be044-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="be044-135">OnPremLineUriManuallySet が False に設定され、LineUri に <E.164 電話番号> が設定されている場合、電話番号はオンプレミスに割り当て済みであり、O365 に同期されます。</span><span class="sxs-lookup"><span data-stu-id="be044-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, the phone number was assigned on-premises and synchronized to O365.</span></span> <span data-ttu-id="be044-136">電話番号をオンラインで管理する場合は、Skype for Business Online PowerShell を使用して電話番号を構成する前に、オンプレミスの Skype for Business Management Shell を使用してパラメーターをクリーンアップし、O365 と同期します。</span><span class="sxs-lookup"><span data-stu-id="be044-136">If you want manage the phone number online, clean the parameter using on-premises Skype for Business Management Shell and synchronize to O365, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="be044-137">管理Skype for Businessコマンドを発行します。</span><span class="sxs-lookup"><span data-stu-id="be044-137">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > <span data-ttu-id="be044-138">EnterpriseVoiceEnabled を False に設定する必要はありません。レガシ Skype for Business 電話が使用され、テナント ハイブリッド構成が UseOnPremDialPlan $True で設定されている場合、ダイヤル プランの正規化の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="be044-138">Do not set EnterpriseVoiceEnabled to False as there is no requirement to do so and this can lead to dial plan normalization issues if legacy Skype for Business phones are in use and the Tenant hybrid configuration is set with UseOnPremDialPlan $True.</span></span> 
    
   <span data-ttu-id="be044-139">変更が同期された後、 のOffice 365の出力は `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` 次の結果です。</span><span class="sxs-lookup"><span data-stu-id="be044-139">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > <span data-ttu-id="be044-140">オンプレミスの電話属性を削除する前に、すべてのユーザーの電話属性をオンライン[で管理Skype for Businessがあります](/skypeforbusiness/hybrid/decommission-on-prem-overview)。</span><span class="sxs-lookup"><span data-stu-id="be044-140">All user's phone attributes must be managed online before you [decomission your on-premises Skype for Business environment](/skypeforbusiness/hybrid/decommission-on-prem-overview).</span></span> 

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online"></a><span data-ttu-id="be044-141">電話番号を構成し、エンタープライズ音声とボイスメールをオンラインで有効にする</span><span class="sxs-lookup"><span data-stu-id="be044-141">Configure the phone number and enable enterprise voice and voicemail online</span></span> 

<span data-ttu-id="be044-142">ユーザーを作成し、ライセンスを割り当てた後、次の手順では、ユーザーのオンライン電話設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="be044-142">After you have created the user and assigned a license, the next step is to configure the user's online phone settings.</span></span> 

 
1. <span data-ttu-id="be044-143">Connect Online PowerShell Skype for Businessセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="be044-143">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="be044-144">ユーザーの電話番号をオンプレミスで管理する場合は、次のコマンドを発行します。</span><span class="sxs-lookup"><span data-stu-id="be044-144">If managing the user's phone number on-premises, issue the command:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
3. <span data-ttu-id="be044-145">ユーザーの電話番号をオンラインで管理する場合は、次のコマンドを発行します。</span><span class="sxs-lookup"><span data-stu-id="be044-145">If managing the user's phone number online, issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    <span data-ttu-id="be044-146">たとえば、ユーザー "Spencer Low" の電話番号を追加するには、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="be044-146">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    <span data-ttu-id="be044-147">ユーザー "Spencer Low" と "Stacy Quinn" が一意の拡張子を持つ同じ基本番号を共有している場合は、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="be044-147">If the users "Spencer Low" and "Stacy Quinn" share the same base number with unique extensions, enter the following</span></span>
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1001" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1002" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="be044-148">使用する電話番号が国コードを含む完全な E.164 電話番号として構成されていることをお勧めしますが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="be044-148">It's recommended, but not required, that the phone number used is configured as a full E.164 phone number with country code.</span></span> <span data-ttu-id="be044-149">ベース番号に対する検索で複数の結果が返された場合にユーザーを参照するために使用される内線番号を使用して電話番号を構成できます。</span><span class="sxs-lookup"><span data-stu-id="be044-149">It is supported to configure phone numbers with extensions which will be used to lookup users when the lookup against the base number returns more than one result.</span></span> <span data-ttu-id="be044-150">これにより、会社は同じ基本番号と一意の内線番号を持つ電話番号を構成できます。</span><span class="sxs-lookup"><span data-stu-id="be044-150">This allows companies to configure phone numbers with the same base number and unique extensions.</span></span> <span data-ttu-id="be044-151">ルックアップを成功するには、次のように、招待に拡張子を含む完全な番号を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="be044-151">For lookup to be successful, the invite must include the full number with extension as follows:</span></span>
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > <span data-ttu-id="be044-152">ユーザーの電話番号がオンプレミスで管理されている場合は、オンプレミスの Skype for Business Management Shell またはコントロール パネルを使用して、ユーザーの電話番号を構成します。</span><span class="sxs-lookup"><span data-stu-id="be044-152">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="be044-153">ボイスメールへの通話の直接送信の構成</span><span class="sxs-lookup"><span data-stu-id="be044-153">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="be044-154">ダイレクト ルーティングを使用すると、ユーザーへの呼び出しを終了し、ユーザーのボイスメールに直接送信できます。</span><span class="sxs-lookup"><span data-stu-id="be044-154">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="be044-155">通話をボイスメールに直接送信する場合は、opaque=app:voicemail を Request URI ヘッダーにアタッチします。</span><span class="sxs-lookup"><span data-stu-id="be044-155">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="be044-156">たとえば、"sip:user@yourdomain.com;opaque=app:voicemail" などです。</span><span class="sxs-lookup"><span data-stu-id="be044-156">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="be044-157">この場合、ユーザー Teams通知を受信しない場合、通話はユーザーのボイスメールに直接接続されます。</span><span class="sxs-lookup"><span data-stu-id="be044-157">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="be044-158">ユーザーにTeamsモードを割り当て、通話が確実に着信Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="be044-158">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="be044-159">直接ルーティングでは、ユーザーが着信Teamsクライアントに着信通話が確実に着信Teams必要があります。</span><span class="sxs-lookup"><span data-stu-id="be044-159">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="be044-160">ユーザーを [のみ] Teamsするには、TeamsUpgradePolicy の "UpgradeToTeams" インスタンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="be044-160">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="be044-161">詳細については、「IT 管理者向け [アップグレード戦略」を参照してください](upgrade-to-teams-on-prem-implement.md)。</span><span class="sxs-lookup"><span data-stu-id="be044-161">For more information, see [Upgrade strategies for IT administrators](upgrade-to-teams-on-prem-implement.md).</span></span> <span data-ttu-id="be044-162">組織で Skype for Business Server または Skype for Business Online を使用している場合、Skype と Teams の間の相互運用性については、Skype for Business の移行と相互運用性に関する記事[を参照してください](migration-interop-guidance-for-teams-with-skype.md)。</span><span class="sxs-lookup"><span data-stu-id="be044-162">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="be044-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="be044-163">See also</span></span>

[<span data-ttu-id="be044-164">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="be044-164">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="be044-165">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="be044-165">Configure Direct Routing</span></span>](direct-routing-configure.md)
