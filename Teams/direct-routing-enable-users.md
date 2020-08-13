---
title: ユーザーが直接ルーティングできるようにする
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
description: Microsoft Phone システムのダイレクトルーティングを有効にする方法について説明します。
ms.openlocfilehash: 5fc3955430e5aa441d3c1099a86011d2b0c760f0
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656148"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="8643d-103">ユーザーが直接ルーティング、音声、ボイスメールを使用できるようにする</span><span class="sxs-lookup"><span data-stu-id="8643d-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="8643d-104">この記事では、ユーザーが電話システムのダイレクトルーティングを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8643d-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="8643d-105">これは、次の手順の手順2で、直接ルーティングを構成します。</span><span class="sxs-lookup"><span data-stu-id="8643d-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="8643d-106">手順1</span><span class="sxs-lookup"><span data-stu-id="8643d-106">Step 1.</span></span> [<span data-ttu-id="8643d-107">SBC と Microsoft 電話システムを接続して接続を検証する</span><span class="sxs-lookup"><span data-stu-id="8643d-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="8643d-108">**手順2ユーザーが直接ルーティング、音声、ボイスメールを使用できるようにする**(この記事)</span><span class="sxs-lookup"><span data-stu-id="8643d-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**    (This article)</span></span>
- <span data-ttu-id="8643d-109">手順3</span><span class="sxs-lookup"><span data-stu-id="8643d-109">Step 3.</span></span> [<span data-ttu-id="8643d-110">音声ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="8643d-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="8643d-111">手順4。</span><span class="sxs-lookup"><span data-stu-id="8643d-111">Step 4.</span></span> [<span data-ttu-id="8643d-112">数値を別の形式に変換する</span><span class="sxs-lookup"><span data-stu-id="8643d-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="8643d-113">直接ルーティングを設定するために必要なすべての手順については、「[直接ルーティングを構成する](direct-routing-configure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8643d-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="8643d-114">ユーザーに対して直接ルーティングを有効にする準備ができたら、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8643d-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="8643d-115">Microsoft 365 または Office 365 でユーザーを作成し、電話システムのライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8643d-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="8643d-116">ユーザーが Skype for Business Online に所属していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8643d-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="8643d-117">電話番号を構成し、エンタープライズボイスとボイスメールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8643d-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="8643d-118">チーム専用モードをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8643d-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="8643d-119">ユーザーを作成してライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="8643d-119">Create a user and assign the license</span></span> 

<span data-ttu-id="8643d-120">Microsoft 365 または Office 365 で新規ユーザーを作成するには、2つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8643d-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="8643d-121">ただし、Microsoft は、ルーティングの問題を回避するためのオプションを組織で選ぶことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8643d-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="8643d-122">オンプレミスの Active Directory でユーザーを作成し、ユーザーをクラウドと同期します。</span><span class="sxs-lookup"><span data-stu-id="8643d-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="8643d-123">「[オンプレミスディレクトリと Azure Active Directory の統合」を](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)参照してください。</span><span class="sxs-lookup"><span data-stu-id="8643d-123">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="8643d-124">Microsoft 365 管理センターで直接ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="8643d-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="8643d-125">「 [Microsoft 365 または Office 365 にユーザーを個別に、または一括して追加する」を](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)参照してください。</span><span class="sxs-lookup"><span data-stu-id="8643d-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="8643d-126">Skype for business Online の展開 coexists が Skype for Business 2015 または Lync 2010 または2013オンプレミスの場合、サポートされているオプションは、オンプレミスの Active Directory でユーザーを作成し、ユーザーをクラウドに同期することだけです (オプション 1)。</span><span class="sxs-lookup"><span data-stu-id="8643d-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="8643d-127">ライセンス要件の詳細については、「[プランダイレクトルーティング](direct-routing-plan.md)の[ライセンスとその他の要件](direct-routing-plan.md#licensing-and-other-requirements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8643d-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online"></a><span data-ttu-id="8643d-128">ユーザーがオンラインになっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="8643d-128">Ensure that the user is homed online</span></span> 

<span data-ttu-id="8643d-129">直接ルーティングでは、ユーザーがオンラインである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8643d-129">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="8643d-130">RegistrarPool パラメーターを確認すると、infra.lync.com ドメインで値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8643d-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="8643d-131">リモート PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="8643d-131">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="8643d-132">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8643d-132">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
    ``` 

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="8643d-133">電話番号を設定し、エンタープライズボイスとボイスメールを有効にする</span><span class="sxs-lookup"><span data-stu-id="8643d-133">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="8643d-134">ユーザーを作成してライセンスを割り当てたら、次の手順では、ユーザーの電話番号とボイスメールを構成します。</span><span class="sxs-lookup"><span data-stu-id="8643d-134">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="8643d-135">電話番号を追加してボイスメールを有効にするには:</span><span class="sxs-lookup"><span data-stu-id="8643d-135">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="8643d-136">リモート PowerShell セッションに接続します。</span><span class="sxs-lookup"><span data-stu-id="8643d-136">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="8643d-137">コマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="8643d-137">Enter the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```

    <span data-ttu-id="8643d-138">たとえば、"Spencer Low" というユーザーの電話番号を追加するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8643d-138">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="8643d-139">使用される電話番号は、国コードを含む完全な電子電話番号として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8643d-139">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

      > [!NOTE]
      > <span data-ttu-id="8643d-140">ユーザーの電話番号がオンプレミスで管理されている場合は、オンプレミスの Skype for Business 管理シェルまたはコントロールパネルを使用して、ユーザーの電話番号を構成します。</span><span class="sxs-lookup"><span data-stu-id="8643d-140">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="8643d-141">ボイスメールに直接通話を送信するように設定する</span><span class="sxs-lookup"><span data-stu-id="8643d-141">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="8643d-142">ダイレクトルーティングを使うと、ユーザの通話を終了してユーザのボイスメールに直接送ることができます。</span><span class="sxs-lookup"><span data-stu-id="8643d-142">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="8643d-143">直接ボイスメールに通話を送信する場合は、符号化 = app: ボイスメールを要求 URI ヘッダーに接続します。</span><span class="sxs-lookup"><span data-stu-id="8643d-143">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="8643d-144">たとえば、"sip: user@yourdomain、不透明 = アプリ: ボイスメール" です。</span><span class="sxs-lookup"><span data-stu-id="8643d-144">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="8643d-145">この場合、Teams ユーザーは呼び出し通知を受信しません。通話はユーザーのボイスメールに直接接続されます。</span><span class="sxs-lookup"><span data-stu-id="8643d-145">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="8643d-146">Microsoft Teams で通話を確実に行うためにチームのみのモードをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="8643d-146">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="8643d-147">直接ルーティングを使うには、チームクライアントで着信通話を確実にするために、ユーザーが Teams 専用モードになっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8643d-147">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="8643d-148">ユーザーをチームのみのモードに配置するには、TeamsUpgradePolicy の "UpgradeToTeams" インスタンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8643d-148">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="8643d-149">詳細については、「 [IT 管理者向けのアップグレードガイダンス](upgrade-to-teams-on-prem-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8643d-149">For more information, see [Upgrade guidance for IT administrators](upgrade-to-teams-on-prem-overview.md).</span></span> <span data-ttu-id="8643d-150">組織で Skype for Business Server または Skype for Business Online を使用している場合は、skype と Teams の相互運用性については、次の記事を参照してください。 [skype For business との移行と相互運用性](migration-interop-guidance-for-teams-with-skype.md)。</span><span class="sxs-lookup"><span data-stu-id="8643d-150">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8643d-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="8643d-151">See also</span></span>

[<span data-ttu-id="8643d-152">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="8643d-152">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="8643d-153">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="8643d-153">Configure Direct Routing</span></span>](direct-routing-configure.md)
