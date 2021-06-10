---
title: ユーザーを 2019 Skype for Business Serverから 2019 年Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: '概要: ユーザー設定を移行し、ユーザーをユーザーに移動する方法についてTeams。'
ms.openlocfilehash: b9b21dafc2290dfff5522f5d54c0872121294dd9
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856306"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="e2ce2-103">オンプレミスから Teams にユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="e2ce2-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="e2ce2-104">ユーザーをオンプレミスから Teams のみに移動すると、ユーザーの Skype for Business ホームはオンプレミスからオンラインに移動され、ユーザーには mode=TeamsOnly で TeamsUpgradePolicy が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-104">When a user is moved from on premises to Teams Only, the user’s Skype for Business home is moved from on premises to online and the user is assigned TeamsUpgradePolicy with mode=TeamsOnly.</span></span>  <span data-ttu-id="e2ce2-105">ユーザーをオンプレミスから TeamsOnly モードに移動した後は、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-105">After a user is moved from on-premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="e2ce2-106">(Skype for Business または Teams から送信された) 他のユーザーからの着信通話とチャットはすべて、ユーザーのクライアントにTeamsされます。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-106">All incoming calls and chats from other users (whether sent from Skype for Business or Teams), will land in the user’s Teams client.</span></span>
- <span data-ttu-id="e2ce2-107">ユーザーは、オンラインかオンプレミスかを問Skype for Business他のユーザーと相互運用できます。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-107">The user will be able to interoperate with other users who use Skype for Business (whether online or on premises).</span></span>
- <span data-ttu-id="e2ce2-108">ユーザーはフェデレーション組織のユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-108">The user will be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="e2ce2-109">そのユーザーがスケジュールした新しい会議は、Teamsされます。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-109">New meetings scheduled by that user are Teams meetings.</span></span>
- <span data-ttu-id="e2ce2-110">ユーザーは引き続き任意の会議Skype for Businessできます。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-110">User can still join any Skype for Business meetings.</span></span>
- <span data-ttu-id="e2ce2-111">将来予定されているユーザーの既存の会議は、オンプレミスから既存の会議に移行Teams。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-111">The user’s pre-existing meetings scheduled for the future will be migrated from on-premises to Teams.</span></span>
- <span data-ttu-id="e2ce2-112">オンプレミスに存在していた連絡先は、ユーザーが初Teamsログオンした直後に、このサイトで利用できます。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-112">Contacts that existed on-premises are available in Teams shortly after the user logs on for the first time.</span></span>
- <span data-ttu-id="e2ce2-113">ユーザーは、ユーザーから通話やチャットを開始Skype for Business、また、会議で新しい会議をスケジュールSkype for Business。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-113">Users cannot initiate calls or chats from Skype for Business, nor can they schedule new meetings in Skype for Business.</span></span> <span data-ttu-id="e2ce2-114">クライアントを開くSkype for Business、次に示すようにTeamsリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-114">If they attempt to open the Skype for Business client, they will be redirected to use Teams as shown below.</span></span> <span data-ttu-id="e2ce2-115">クライアントがTeams場合は、ブラウザーを使用して web バージョンTeamsされます。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-115">If the Teams client is not installed, they will be directed to the web version of Teams using their browser.</span></span><br><br>
    <span data-ttu-id="e2ce2-116">![ユーザーをユーザーにリダイレクトするTeams](../media/go-to-teams-page.png)</span><span class="sxs-lookup"><span data-stu-id="e2ce2-116">![Message redirecting a user to Teams](../media/go-to-teams-page.png)</span></span>

<span data-ttu-id="e2ce2-117">ユーザーを移動する前に、必ず前提条件を確認 [して](move-users-between-on-premises-and-cloud.md#prerequisites) 、ユーザーをクラウドに移動してください。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-117">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span> <span data-ttu-id="e2ce2-118">また、移行を使用している組織の移行と相互運用性のガイダンスと、Teams[を確認Skype for Business。](/microsoftteams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="e2ce2-118">Also be sure to review [Migration and interoperability guidance for organizations using Teams together with Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>


> [!NOTE]
> <span data-ttu-id="e2ce2-119">連絡先をサーバーに移動するには、統合連絡先ストアを on-prem SfB アカウントで無効Teams。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-119">Unified Contact Store should be disabled on the on-prem SfB account for the contact to be moved to Teams.</span></span>

> [!IMPORTANT]
><span data-ttu-id="e2ce2-120">Move-CsUser を使用してユーザーをオンプレミスからクラウドに移動すると、ユーザーに TeamsOnly モードが自動的に割り当てられると、スイッチが実際に指定されたかどうかに関係なく、オンプレミスの会議が自動的に Teams 会議に変換されます。 `-MoveToTeams`</span><span class="sxs-lookup"><span data-stu-id="e2ce2-120">When moving a user from on-premises to the cloud with Move-CsUser, users are now automatically assigned TeamsOnly mode and their meetings from on-premises are automatically converted to Teams meetings, regardless of whether the `-MoveToTeams` switch is actually specified.</span></span> <span data-ttu-id="e2ce2-121">(これには、切り替え前の Lync Server 2013 からの移行が含 `-MoveToTeams` まれます)。 以前は、このスイッチが指定されていない場合、ユーザーは Skype for Business Server オンプレミスのホームから Skype for Business Online に移行し、モードは変更されません。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-121">(This includes migrations from Lync Server 2013, which never had the `-MoveToTeams` switch.)  Previously if this switch was not specified, users transitioned from being homed in Skype for Business Server on-premises to Skype for Business Online, and their mode remained unchanged.</span></span> <span data-ttu-id="e2ce2-122">これは最近、オンラインの退職に備えてSkype for Businessされています。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-122">This has recently been changed in preparation for retirement of Skype for Business Online.</span></span>


## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="e2ce2-123">オンプレミスからユーザーを直接Skype for Businessに移動Teamsのみ</span><span class="sxs-lookup"><span data-stu-id="e2ce2-123">Move a user directly from Skype for Business on premises to Teams Only</span></span>

<span data-ttu-id="e2ce2-124">Skype for Business Server および Lync Server 2013 のオンプレミス管理ツールを使用すると、以下で説明するように、PowerShell の Move-CsUser コマンドレットまたは Skype for Business Server コントロール パネルを使用して、1 つの手順でユーザーをオンプレミスから TeamsOnly モードに移動できます。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-124">The on-premises admin tools in Skype for Business Server and Lync Server 2013 enable you to move users from on premises to TeamsOnly mode in a single step using either the Move-CsUser cmdlet in PowerShell or the Skype for Business Server Control Panel, as described below.</span></span> <span data-ttu-id="e2ce2-125">スイッチを指定する必要がなくなりました。また、使用する Skype for Business Server または Lync Server のバージョンに関係なく、オンプレミスから Teams Only に直接移動する動作が自動的に実行されます `-MoveToTeams` 。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-125">It is no longer required to specify the `-MoveToTeams` switch and the behavior to move directly from on premises to Teams Only is now automatic, regardless of which version of Skype for Business Server or Lync Server is used.</span></span> 

<span data-ttu-id="e2ce2-126">「必須の管理資格情報」の説明に従って、オンプレミス環境とクラウド サービス (Microsoft 365 または Office 365) の両方で十分な特権を持っている[必要があります](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-126">You must have sufficient privileges in both the on-premises environment and the cloud service (Microsoft 365 or Office 365), as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="e2ce2-127">両方の環境で特権を持つ 1 つのアカウントを使用するか、オンプレミスの資格情報を使用してオンプレミスの Skype for Business Server 管理シェル ウィンドウを起動し、パラメーターを使用して必要な管理役割を持つ Microsoft 365 の資格情報を指定できます。 `-Credential`</span><span class="sxs-lookup"><span data-stu-id="e2ce2-127">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 with the necessary administrative role.</span></span>

<span data-ttu-id="e2ce2-128">さらに、ユーザーにオンラインのライセンスが付与Teams必要があります (Skype for Businessします)。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-128">In addition, you must ensure the user has been granted a license for Teams (in addition to Skype for Business Online).</span></span> <span data-ttu-id="e2ce2-129">オンライン ライセンスのSkype for Business無効にしない。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-129">Do not disable the Skype for Business Online license.</span></span>

### <a name="move-to-teams-using-move-csuser"></a><span data-ttu-id="e2ce2-130">[ファイルを使用してTeamsに移動Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="e2ce2-130">Move to Teams using Move-CsUser</span></span>

<span data-ttu-id="e2ce2-131">Move-CsUserは、オンプレミスの管理シェル PowerShell ウィンドウSkype for Business Server Lync Server 管理シェル PowerShell ウィンドウから使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-131">Move-CsUser is available from an on-premises Skype for Business Server Management Shell PowerShell window or from a Lync Server Management Shell PowerShell window.</span></span> <span data-ttu-id="e2ce2-132">Move-CsUser を使用してユーザーを TeamsOnly モードに移動するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-132">To move a user to TeamsOnly mode using Move-CsUser:</span></span>
- <span data-ttu-id="e2ce2-133">パラメーターを使用して移動するユーザーを `Identity` 指定します。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-133">Specify the user to move using the `Identity` parameter.</span></span>
- <span data-ttu-id="e2ce2-134">`-Target`"sipfed.online.lync" という値のパラメーターを指定します。 <span>com」</span><span class="sxs-lookup"><span data-stu-id="e2ce2-134">Specify the `-Target` parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="e2ce2-135">オンプレミスとクラウド サービス (Microsoft 365) の両方に十分なアクセス許可を持つアカウントが 1 つない場合は、パラメーターを使用して、Microsoft 365 で十分なアクセス許可を持つアカウント `-credential` を指定します。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-135">If you do not have one account with sufficient permissions in both on premises and the cloud service (Microsoft 365), use the `-credential` parameter to supply an account with sufficient permissions in Microsoft 365.</span></span>
- <span data-ttu-id="e2ce2-136">アクセス許可を持つアカウントが Microsoft 365 "onmicrosoft" で終了しない場合。 <span>com」の説明に従って、パラメーターを正しい値で指定 `-HostedMigrationOverrideUrl` [する必要があります](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-136">If the account with permissions in Microsoft 365 does not end in “onmicrosoft.<span>com”, you must specify the `-HostedMigrationOverrideUrl` parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="e2ce2-137">次のコマンドレット シーケンスを使用して、ユーザーを TeamsOnly に移動し、Microsoft 365 資格情報が別のアカウントであり、Get-Credential プロンプトの入力として提供されたと見なします。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-137">The following cmdlet sequence can be used to move a user to TeamsOnly, and assumes the Microsoft 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span> <span data-ttu-id="e2ce2-138">動作は、スイッチが指定されている `-MoveToTeams` かどうかに関して同じです。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-138">The behavior is the same whether `-MoveToTeams` switch is specified or not.</span></span>

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> <span data-ttu-id="e2ce2-139">異なるパラメーターが必要な状況が異なるので、ほとんどの場合の既定のコマンドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-139">As there are different circumstances requiring different parameters, the default command for most cases is:</span></span>

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a><span data-ttu-id="e2ce2-140">[コントロール パネル] Teamsを使用Skype for Business Serverに移動する</span><span class="sxs-lookup"><span data-stu-id="e2ce2-140">Move to Teams using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e2ce2-141">コントロール パネル アプリSkype for Business Server開きます。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-141">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="e2ce2-142">左側のナビゲーションで、[ユーザー] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-142">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="e2ce2-143">[**検索]** を使用して、ユーザーに移動するユーザーをTeams。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-143">Use **Find** to locate the user(s) you would like to move to Teams.</span></span>
4. <span data-ttu-id="e2ce2-144">ユーザーを選択し、リストの上にある [アクション] ドロップダウンから 、[選択したユーザーを Teams に移動する] または **[** 選択したユーザーをオンラインにSkype for Business **します**。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-144">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Teams** or **Move selected users to Skype for Business Online**.</span></span>   <span data-ttu-id="e2ce2-145">どちらのオプションでも、ユーザーは TeamsOnly に直接移動します。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-145">Either option now moves users directly to TeamsOnly.</span></span>
5. <span data-ttu-id="e2ce2-146">ウィザードで、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-146">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="e2ce2-147">メッセージが表示されたら、.Microsoft 365で終わり、十分なアクセス許可を持つアカウントを使用して、onmicrosoft.com にサインインします。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-147">If prompted, sign in to Microsoft 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="e2ce2-148">[ **次へ]** をクリックし、[ **次** へ] をクリックしてもう 1 回ユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-148">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="e2ce2-149">成功または失敗に関する状態メッセージは、ウィザードではなく、メインのコントロール パネル アプリの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-149">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>
    
    
## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a><span data-ttu-id="e2ce2-150">今後のSkype for Businessをオンプレミス のユーザーに通知Teams</span><span class="sxs-lookup"><span data-stu-id="e2ce2-150">Notify your Skype for Business on-premises users of the upcoming move to Teams</span></span>

<span data-ttu-id="e2ce2-151">cu8 と Skype for Business Server 2015 のオンプレミス管理ツール、および Skype for Business Server 2019 では、Teams への移行についてオンプレミス Skype for Business ユーザーに通知できます。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-151">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to notify on-premises Skype for Business users of their upcoming move to Teams.</span></span> <span data-ttu-id="e2ce2-152">これらの通知を有効にした場合、ユーザーは次に示すように、Skype for Business クライアント (Win32、Mac、Web、およびモバイル) に通知を表示します。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-152">When you enable these notifications, users will see a notification in their Skype for Business client (Win32, Mac, web, and mobile) as shown below.</span></span> <span data-ttu-id="e2ce2-153">ユーザーが [**試す**] ボタンをクリックするとTeamsクライアントがインストールされている場合に起動されます。それ以外の場合、ユーザーはブラウザーで web バージョンTeams移動されます。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-153">If users click the **Try it** button, the Teams client will be launched if it is installed; otherwise, users will be navigated to the web version of Teams in their browser.</span></span> <span data-ttu-id="e2ce2-154">既定では、通知を有効にすると、Win32 Skype for Business クライアントは Teams クライアントをサイレント モードでダウンロードして、リッチ クライアントを TeamsOnly モードに移行する前に利用できます。ただし、この動作を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-154">By default, when notifications are enabled, Win32 Skype for Business clients silently download the Teams client so that the rich client is available prior to moving the user to TeamsOnly mode; however, you can also disable this behavior.</span></span>  <span data-ttu-id="e2ce2-155">通知は、オンプレミスバージョンの Win32 クライアント用にサイレント ダウンロードを使用して構成され、オンプレミスコマンドレット `TeamsUpgradePolicy` を介して制御 `TeamsUpgradeConfiguration` されます。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-155">Notifications are configured using the on-premises version of `TeamsUpgradePolicy`, and silent download for Win32 clients is controlled via the on-premises `TeamsUpgradeConfiguration` cmdlet.</span></span>

> [!TIP]
> <span data-ttu-id="e2ce2-156">一部のサーバーでは、CU8 を使用して 2015 年 2015 年Skype for Business再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-156">Some servers may need to reboot for this to work in Skype for Business 2015 with CU8.</span></span>

![今後の移行に関する通知Teams](../media/teams-upgrade-notification.png)

<span data-ttu-id="e2ce2-158">すぐに Teams にアップグレードされる予定のオンプレミス ユーザーに通知するには、NotifySfBUsers=true を使用して TeamsUpgradePolicy の新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-158">To notify on-premises users that they will soon be upgraded to Teams, create a new instance of TeamsUpgradePolicy with NotifySfBUsers=true.</span></span> <span data-ttu-id="e2ce2-159">次に、ポリシーをユーザーに直接割り当てるか、サイト、プール、またはグローバル レベルでポリシーを設定して、通知するユーザーにポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-159">Then assign that policy to the users who you want to notify, either by assigning the policy directly to the user or by setting the policy at the site, pool, or global level.</span></span> <span data-ttu-id="e2ce2-160">次のコマンドレットは、ユーザー レベルのポリシーを作成して付与します。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-160">The following cmdlets create and grant a user-level policy:</span></span>

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

<span data-ttu-id="e2ce2-161">Teams Win32 クライアントSkype for Businessの自動ダウンロードは、DownloadTeams パラメーターを使用して、オンプレミスの TeamsUpgradeConfiguration コマンドレットを介して制御されます。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-161">Automatic download of Teams via the Skype for Business Win32 client is controlled via the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="e2ce2-162">この構成は、グローバル レベル、サイト レベル、およびプール レベルで作成します。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-162">You create this configuration on a global, site, and pool level.</span></span> <span data-ttu-id="e2ce2-163">たとえば、次のコマンドは、サイト Redmond1 の構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-163">For example, the following command creates the configuration for the site Redmond1:</span></span>

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

<span data-ttu-id="e2ce2-164">既定では、DownloadTeams の値は True です。ただし、指定した *ユーザーに* 対して NotifySfbUser = True の場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="e2ce2-164">By default, the value of DownloadTeams is True; however, it is *only* honored if NotifySfbUser = True for a given user.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2ce2-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2ce2-165">See also</span></span>

[<span data-ttu-id="e2ce2-166">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="e2ce2-166">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)

[<span data-ttu-id="e2ce2-167">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="e2ce2-167">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy
)

[<span data-ttu-id="e2ce2-168">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="e2ce2-168">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="e2ce2-169">Skype for Business と共存する</span><span class="sxs-lookup"><span data-stu-id="e2ce2-169">Coexistence with Skype for Business</span></span>](/microsoftteams/coexistence-chat-calls-presence)
