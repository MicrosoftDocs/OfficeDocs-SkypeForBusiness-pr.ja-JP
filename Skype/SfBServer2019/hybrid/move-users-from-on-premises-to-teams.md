---
title: 移動ユーザーがチームを設置
ms.author: crowe
author: CarolynRowe
manager: serdars--
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: '概要: は、ユーザー設定を移行し、チームにユーザーを移動する方法を説明します。'
ms.openlocfilehash: af0867bfdc2e12a248baf7cc07746845154d27fd
ms.sourcegitcommit: bb3f235265cddae9578ec1bf605c4edc7f14fb30
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "25851484"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="4d0f0-103">移動ユーザーがチームを設置</span><span class="sxs-lookup"><span data-stu-id="4d0f0-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="4d0f0-104">ビジネス サーバー 2019 の Skype では、チームがこの資料で説明したように、オンプレミス ユーザーを移行できます。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-104">With Skype for Business Server 2019, you can migrate your on-premises users to Teams as described in this article.</span></span>

<span data-ttu-id="4d0f0-105">注意してくださいチームにユーザーを移動した後です。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-105">Be aware that after moving your users to Teams:</span></span> 
 
- <span data-ttu-id="4d0f0-106">会議は、ビジネス オンラインでは、Skype に移行し、その連絡先は、チームに移行します。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-106">Their meetings are migrated to Skype for Business Online, and their contacts are migrated to Teams.</span></span> 
- <span data-ttu-id="4d0f0-107">Skype のビジネスのリッチ クライアント (ユーザーの求められませんサインインするたびに)、または (1 回だけダウンロードしてサインインする必要があります) Skype 会議アプリケーションを通じて、Skype の会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-107">They can join Skype meetings through the Skype for Business rich client (users are not prompted for sign-in each time) or through the Skype Meetings App (requires a one-time download and sign-in).</span></span> <span data-ttu-id="4d0f0-108">ユーザーは、Skype のチーム内でのビジネス会議のリンクをクリックすると、会議が適切なアプリケーションの起動します。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-108">When a user clicks on a Skype for Business meeting link within Teams, the meeting will launch in the appropriate app.</span></span>

- <span data-ttu-id="4d0f0-109">携帯電話] で、ユーザーは既存の Skype のネイティブのアプリケーションだけを使用してビジネス ・ ミーティングに参加することになります。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-109">On Mobile, your users will be able to join existing Skype for Business meetings using the native app only.</span></span>

> [!NOTE]
> <span data-ttu-id="4d0f0-110">TeamsOnly モードにユーザーを移動すると後、は、オンライン ビジネスの Skype のユーザーが配置されています。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-110">After a user is moved to TeamsOnly mode, the user is homed in Skype for Business Online.</span></span>

## <a name="prerequisites-for-moving-on-premises-users-to-teams"></a><span data-ttu-id="4d0f0-111">オンプレミス ユーザーをチームに移動するための前提条件</span><span class="sxs-lookup"><span data-stu-id="4d0f0-111">Prerequisites for moving on-premises users to Teams</span></span> 

<span data-ttu-id="4d0f0-112">このセクションでは、オンプレミス ユーザーをチームに移動するための前提条件について説明します。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-112">This section describes the prerequisites for moving your on-premises users to Teams.</span></span> <span data-ttu-id="4d0f0-113">しなきゃいけません：</span><span class="sxs-lookup"><span data-stu-id="4d0f0-113">You must:</span></span>
- <span data-ttu-id="4d0f0-114">[ハイブリッド接続の設定](#set-up-hybrid-connectivity)(まだ行っていないため) 場合</span><span class="sxs-lookup"><span data-stu-id="4d0f0-114">[Set up hybrid connectivity](#set-up-hybrid-connectivity) (if you have not already done so)</span></span>
- <span data-ttu-id="4d0f0-115">[チームへの移行のユーザーに通知](#notify-your-users-of-the-move-to-teams)(省略可能)</span><span class="sxs-lookup"><span data-stu-id="4d0f0-115">[Notify your users of the move to Teams](#notify-your-users-of-the-move-to-teams) (optional)</span></span>
- [<span data-ttu-id="4d0f0-116">ユーザーが有効なライセンスを持っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-116">Ensure that your users have a valid license</span></span>](#make-sure-your-users-have-a-valid-license)
- [<span data-ttu-id="4d0f0-117">音声の構成要件に注意してください。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-117">Be aware of voice configuration requirements</span></span>](#voice-configuration-requirements)
- <span data-ttu-id="4d0f0-118">[チームのアップグレード ・ ポリシーを設定](#assign-a-teams-upgrade-policy)(省略可能)</span><span class="sxs-lookup"><span data-stu-id="4d0f0-118">[Assign a Teams Upgrade policy](#assign-a-teams-upgrade-policy) (optional)</span></span>

## <a name="set-up-hybrid-connectivity"></a><span data-ttu-id="4d0f0-119">ハイブリッド接続を設定します。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-119">Set up hybrid connectivity</span></span>
<span data-ttu-id="4d0f0-120">されていない場合に、ユーザーを移行する前に、ビジネス オンラインの Skype、Skype ビジネス サーバー設置環境の間のハイブリッドの接続を構成していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-120">Before you migrate your users, if you have not already done so, you must ensure that you have configured hybrid connectivity between your Skype for Business Server on-premises environment and Skype for Business Online.</span></span> <span data-ttu-id="4d0f0-121">ハイブリッド接続は、Active Directory の同期など、フェデレーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-121">Hybrid connectivity requires Active Directory synchronization, configuring federation, and so on.</span></span> <span data-ttu-id="4d0f0-122">詳細については、[ハイブリッドの接続を計画](plan-hybrid-connectivity.md)し、[ハイブリッド接続の構成](configure-hybrid-connectivity.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-122">For more information, see [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span>

## <a name="notify-your-users-of-the-move-to-teams"></a><span data-ttu-id="4d0f0-123">チームへの移行のユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-123">Notify your users of the move to Teams</span></span> 
<span data-ttu-id="4d0f0-124">これは、いずれかを考慮する必要がありますが、オプションの手順です。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-124">This is an optional step, but one that you should consider.</span></span> <span data-ttu-id="4d0f0-125">チームの保留中のアップグレードをユーザーに通知、設置型の TeamsUpgradePolicy、TeamsUpgradeConfiguration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-125">To notify users of the pending Teams upgrade, you can use the on-premises TeamsUpgradePolicy and TeamsUpgradeConfiguration cmdlets.</span></span> <span data-ttu-id="4d0f0-126">(Win32 クライアントのみ) をアップグレードする前にバック グラウンドでサイレントのチームの自動ダウンロードを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-126">You can also configure silent auto-download of Teams in the background prior to upgrade (Win32 clients only).</span></span> 

<span data-ttu-id="4d0f0-127">などのチームにアップグレード中は、ユーザーに通知をするには、-NotifySbUser パラメーターを使用して設置 TeamsUpgradePolicy コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-127">For example, to notify users that they are being upgraded to Teams, use the on-premises TeamsUpgradePolicy cmdlet with the -NotifySbUser parameter.</span></span> <span data-ttu-id="4d0f0-128">グローバル、サイト、プール、またはユーザー レベルでポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-128">You can set the policy on a global, site, pool, or user level.</span></span> <span data-ttu-id="4d0f0-129">次のコマンドを作成し、ユーザー レベル ポリシーを付与します。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-129">The following command creates and grants a user-level policy:</span></span>
 
```
New-CsTeamsUpgradePolicy -Identity UpgradeNotice -NotifySfbUser $true 
Grant-CsTeamsUpgradePolicy -Identity user01 -PolicyName “UpgradeNotice”
```

<span data-ttu-id="4d0f0-130">Get csTeamsUpgradePolicy コマンドレットを使用して、このポリシーを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-130">You can check this policy by using the Get-csTeamsUpgradePolicy cmdlet.</span></span>

<span data-ttu-id="4d0f0-131">間もなくチームへの移行の通知がユーザーに表示します。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-131">Your users will see a notification of the impending move to Teams.</span></span> <span data-ttu-id="4d0f0-132">通知は、(適切なバージョン) と、Win32、Mac、モバイル、および Web クライアントで発生します。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-132">The notification occurs on Win32, Mac, Mobile, and Web Clients (with the right version).</span></span>

<span data-ttu-id="4d0f0-133">(Win32 クライアント) のチームの DownloadTeams パラメーターを使用してオンプレミス TeamsUpgradeConfiguration コマンドレットを使用して、アップグレード中のユーザーの自動ダウンロードを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-133">You can specify automatic download of Teams (for Win32 clients) for users being upgraded by using the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="4d0f0-134">テナント レベルでは、このポリシーを設定して、グローバル、サイトに適用することができ、レベルをプールします。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-134">You set this policy at the tenant level, and it can be applied on a global, site, and pool level.</span></span> <span data-ttu-id="4d0f0-135">たとえば、次のコマンドでは、サイト レベルでポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-135">For example, the following command sets the policy at the site level:</span></span>

```
New-CsTeamsUpgradeConfiguration -Identity “site:redmond1” 
```

<span data-ttu-id="4d0f0-136">既定では、DownloadTeams の値は true の場合、ですが、NotifySfbUser を特定のユーザーのチームを有効にする場合は True に設定することもする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-136">By default, the value of DownloadTeams is True, but you must also set NotifySfbUser to True to enable Teams for a given user.</span></span> 

## <a name="make-sure-your-users-have-a-valid-license"></a><span data-ttu-id="4d0f0-137">ユーザーが有効なライセンスを持っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-137">Make sure your users have a valid license</span></span>  
<span data-ttu-id="4d0f0-138">移行する前に、オンプレミス ユーザー必要がある有効なライセンスでは、次のように。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-138">Before migration, the on-premises user must be given a valid license, as follows:</span></span>

-   <span data-ttu-id="4d0f0-139">チームのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-139">User must have a Teams license.</span></span>
-   <span data-ttu-id="4d0f0-140">ユーザーがオンプレミス エンタープライズ VoIP を使用するように構成されている場合を移動するとき、オンラインでのボイスのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-140">If the user is configured to use on-premises Enterprise Voice, they must have an online voice license when moving.</span></span> 
-   <span data-ttu-id="4d0f0-141">設置型では、ダイヤルイン会議のユーザーを構成する場合 (クラウド PBX) の電話システムのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-141">If the user is configured for on-premises dial-in conferencing, they must have a license for Phone System (Cloud PBX).</span></span>

## <a name="voice-configuration-requirements"></a><span data-ttu-id="4d0f0-142">音声の構成要件</span><span class="sxs-lookup"><span data-stu-id="4d0f0-142">Voice configuration requirements</span></span>

<span data-ttu-id="4d0f0-143">オンプレミス ユーザーが設置型の音声を使用している場合、2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-143">If your on-premises users have on-premises voice, you have two options:</span></span>

-  <span data-ttu-id="4d0f0-144">**テレフォニー機能を持つユーザーを移行します。**</span><span class="sxs-lookup"><span data-stu-id="4d0f0-144">**Migrate users with telephony capabilities.**</span></span> <span data-ttu-id="4d0f0-145">ユーザーとチームのクライアントを使用して呼び出しを受信できます。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-145">Users can make and receive calls using the Teams client.</span></span>  <span data-ttu-id="4d0f0-146">Microsoft の計画を呼び出すか、直接ルーティングではチームに、テレフォニー サービスを接続するを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-146">You can choose either Microsoft Calling Plan or Direct Routing to connect the telephony services to Teams.</span></span>  

    -  <span data-ttu-id="4d0f0-147">クラウドをすべて音声ソリューションを提供する Microsoft の計画を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-147">Microsoft Calling Plan provides an all-in-the-cloud voice solution.</span></span> <span data-ttu-id="4d0f0-148">Microsoft の計画を呼び出すことの詳細については、(リンク準備中) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-148">For more information about Microsoft Calling Plan, see (link coming soon).</span></span> 
    -  <span data-ttu-id="4d0f0-149">直接ルーティングでは、事実上、PSTN トランクを使用することができ、お客様が所有する電話装置とマイクロソフトの電話システムとの間の相互運用性を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-149">Direct Routing lets you use virtually any PSTN trunk,  and you can configure interoperability between customer-owned telephony equipment and Microsoft Phone System.</span></span>  <span data-ttu-id="4d0f0-150">詳細については、[直接ルーティングを計画](https://docs.microsoft.com/MicrosoftTeams/direct-routing-plan)し、[直接ルーティングの構成](https://docs.microsoft.com/MicrosoftTeams/direct-routing-configure)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-150">For more information, see [Plan Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-plan) and [Configure Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-configure).</span></span>

-  <span data-ttu-id="4d0f0-151">**テレフォニー機能のないユーザーを移行します。**</span><span class="sxs-lookup"><span data-stu-id="4d0f0-151">**Migrate users without telephony capabilities.**</span></span> <span data-ttu-id="4d0f0-152">テレフォニー機能を維持せずにユーザーを移行する場合は、ユーザーは、クラウドで適切なライセンスを持っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-152">If you migrate users without preserving  telephony capabilities, make sure users have appropriate licenses in the cloud.</span></span> 

## <a name="assign-a-teams-upgrade-policy"></a><span data-ttu-id="4d0f0-153">チームのアップグレード ・ ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-153">Assign a Teams Upgrade policy</span></span>  
<span data-ttu-id="4d0f0-154">着信メッセージと呼び出しのルーティングを制御するのにようにユーザー ポリシーを管理するのには、オンライン ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-154">You can use online tools to manage user policies, such as to control routing of incoming messages and calls.</span></span> <span data-ttu-id="4d0f0-155">詳細については、(リンク準備中) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-155">For more information, see (link coming soon).</span></span>

## <a name="move-on-premises-users-to-teams"></a><span data-ttu-id="4d0f0-156">オンプレミス ユーザーをチームに移動します。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-156">Move on-premises users to Teams</span></span>

<span data-ttu-id="4d0f0-157">PowerShell コマンドレットを使用するか、ビジネス サーバー 2019 のコントロール パネルの Skype を使用して、チームに、オンプレミスのユーザーを移動できます。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-157">You can move your on-premises users to Teams by using PowerShell cmdlets or by using the Skype for Business Server 2019 Control Panel.</span></span>

### <a name="move-users-by-using-powershell"></a><span data-ttu-id="4d0f0-158">PowerShell を使用してユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="4d0f0-158">Move users by using PowerShell</span></span>
<span data-ttu-id="4d0f0-159">チームにユーザーを移動するには、PowerShell を使用して、コマンドレットを使用する移動 CsUser moveToTeams パラメーターを使用して次のように。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-159">To move your users to Teams by using PowerShell, you’ll use the Move-CsUser cmdlet with the moveToTeams parameter as follows:</span></span>

```
Move-CsUser -Identity user0 -Target sipfed.online.lync.com -moveToTeams -credentials $cred. 
```

<span data-ttu-id="4d0f0-160">($cred = 資格情報の取得。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-160">($cred = get-Credentials.</span></span> <span data-ttu-id="4d0f0-161">入力してください Office 365 管理者の資格情報です。)</span><span class="sxs-lookup"><span data-stu-id="4d0f0-161">You must provide Office 365 admin credentials.)</span></span>

> [!NOTE]
> <span data-ttu-id="4d0f0-162">このコマンドは、TeamsOnly モードを TeamsUpgradePolicy を設定します。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-162">This command sets the TeamsUpgradePolicy to TeamsOnly mode.</span></span> 
 
<span data-ttu-id="4d0f0-163">チームへの移行が成功した後、ビジネス クライアント用のユーザーの Skype には、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-163">After the move to Teams is successful, the user’s Skype for Business client will display the following message:</span></span> 

![チーム メッセージ移行に成功しました](../media/teams-upgrade-complete-message.png)

<span data-ttu-id="4d0f0-165">ビジネス用の Skype がミーティングに参加する以外のユーザーに利用可能な不要になったされることに注意します。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-165">Note that Skype for Business will no longer be available to the user except to join a meeting.</span></span> 

<span data-ttu-id="4d0f0-166">まれに、チームにユーザーを移動する場合、ダイヤルイン会議をオーバーライドし、音声機能をクラウドにする場合があります。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-166">In rare cases, when moving your users to Teams, you might want to override dial-in conferencing and cloud voice functionality.</span></span> <span data-ttu-id="4d0f0-167">Csuser からの移動コマンドを使用して次のパラメーターを使用してこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-167">You can do this by using the following parameters with the Move-CsUser command:</span></span>
- <span data-ttu-id="4d0f0-168">**BypassAudioConferencingCheck:** ユーザーのダイヤルイン会議機能を備えた、設置型の場合は、ユーザーには、AudioConf ライセンスを移行する前に Office 365 に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-168">**BypassAudioConferencingCheck:** If a user has dial-in conferencing enabled for on-premises, the user must also have an AudioConf license assigned in Office 365 before migrating.</span></span> <span data-ttu-id="4d0f0-169">クラウドへの移行、ユーザーがクラウドでの音声会議を準備します。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-169">Once migrated to the cloud, the user will be provisioned for audio conferencing in the cloud.</span></span> <span data-ttu-id="4d0f0-170">場合は、何らかの理由により、ユーザーをクラウドに移動するが、音声会議機能を使用するは、このパラメーターを指定することによってオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-170">If, for some reason, you want to move a user to the cloud, but not use the audio conferencing functionality, you can override it by specifying this parameter.</span></span>
- <span data-ttu-id="4d0f0-171">**ByPassEnterpriseVoice:** ユーザーのエンタープライズ VoIP の設置型の有効な場合は、ユーザーに Office 365 に移行する前に割り当てられたエンタープライズ VoIP のライセンスは必要です。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-171">**ByPassEnterpriseVoice:** If a user has Enterprise Voice enabled for on-premises, the user must have an Enterprise Voice license assigned in Office 365 before migrating.</span></span> <span data-ttu-id="4d0f0-172">クラウドへの移行後の雲の中の音声をユーザーが準備されます。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-172">After migration to the cloud, the user will be provisioned for voice in the cloud.</span></span> <span data-ttu-id="4d0f0-173">場合は、何らかの理由により、ユーザーをクラウドに移行するが、クラウドの音声機能を使用して、このパラメーターを指定することでクラウドの音声をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-173">If, for some reason, you want to move a user to the cloud but not use cloud voice functionality, you can override cloud voice by specifying this parameter.</span></span>
 
### <a name="move-users-by-using-the-skype-for-business-server-control-panel"></a><span data-ttu-id="4d0f0-174">ビジネス サーバーのコントロール パネルの Skype を使用して、ユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="4d0f0-174">Move users by using the Skype for Business Server Control Panel</span></span> 

<span data-ttu-id="4d0f0-175">チームにユーザーを移動するには、ビジネス コントロール パネルに、Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-175">To move users to Teams by using the Skype for Business Control Panel:</span></span>

1. <span data-ttu-id="4d0f0-176">ビジネス コントロール パネルの Skype を開くし、Office 365 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-176">Open the Skype for Business Control Panel and sign in to your Office 365 account.</span></span>

2. <span data-ttu-id="4d0f0-177">左側のナビゲーションでは、**ユーザー**を選択し、移行するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-177">Select **Users** in the left navigation, and select the users to migrate.</span></span> 
     
3. <span data-ttu-id="4d0f0-178">[**操作**] メニューで、**チームを選択したユーザーの移動**を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-178">On the **Action** menu, choose **Move selected users to Teams**.</span></span> 

    ![移行を確認するのには次へをクリックすると](../media/migration-confirmation.png)
    
4. <span data-ttu-id="4d0f0-180">[**次**への移行を確認] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-180">Click **Next** to confirm your migration.</span></span> 

<span data-ttu-id="4d0f0-181">チームにユーザーを移動すると後、は、次のような確認が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-181">After the user is moved to Teams, you will see  confirmations like the following:</span></span>

<span data-ttu-id="4d0f0-182">![移動ユーザーの確認](../media/move-user-confirmation.png)
</span><span class="sxs-lookup"><span data-stu-id="4d0f0-182">![Move users confirmation](../media/move-user-confirmation.png)
</span></span><br/><br/>
<span data-ttu-id="4d0f0-183">![ユーザーが移動されているメッセージ](../media/users-moved-successfully.png)</span><span class="sxs-lookup"><span data-stu-id="4d0f0-183">![Message that users have been moved](../media/users-moved-successfully.png)</span></span>

<span data-ttu-id="4d0f0-184">移動が正常に終了しない場合は、次のようなメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d0f0-184">If the move was not successful, you will see a message like the following:</span></span>

![メッセージにユーザーを移動できませんでした](../media/users-not-moved.png)
