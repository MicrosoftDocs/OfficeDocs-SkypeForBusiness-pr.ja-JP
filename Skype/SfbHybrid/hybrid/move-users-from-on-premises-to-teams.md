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
ms.openlocfilehash: 1d2542d3c5b67e935449b4f6fee60506b9232adc
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52306021"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="cdc3a-103">オンプレミスから Teams にユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="cdc3a-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="cdc3a-104">ユーザーをオンプレミスから Teams のみに移動すると、ユーザーの Skype for Business ホームはオンプレミスからオンラインに移動され、ユーザーには mode=TeamsOnly で TeamsUpgradePolicy が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-104">When a user is moved from on premises to Teams Only, the user’s Skype for Business home is moved from on premises to online and the user is assigned TeamsUpgradePolicy with mode=TeamsOnly.</span></span>  <span data-ttu-id="cdc3a-105">ユーザーをオンプレミスから TeamsOnly モードに移動した後は、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-105">After a user is moved from on-premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="cdc3a-106">(Skype for Business または Teams から送信された) 他のユーザーからの着信通話とチャットはすべて、ユーザーのクライアントにTeamsされます。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-106">All incoming calls and chats from other users (whether sent from Skype for Business or Teams), will land in the user’s Teams client.</span></span>
- <span data-ttu-id="cdc3a-107">ユーザーは、オンラインかオンプレミスかを問Skype for Business他のユーザーと相互運用できます。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-107">The user will be able to interoperate with other users who use Skype for Business (whether online or on premises).</span></span>
- <span data-ttu-id="cdc3a-108">ユーザーはフェデレーション組織のユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-108">The user will be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="cdc3a-109">そのユーザーがスケジュールした新しい会議は、Teamsされます。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-109">New meetings scheduled by that user are Teams meetings.</span></span>
- <span data-ttu-id="cdc3a-110">ユーザーは引き続き任意の会議Skype for Businessできます。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-110">User can still join any Skype for Business meetings.</span></span>
- <span data-ttu-id="cdc3a-111">将来予定されているユーザーの既存の会議は、オンプレミスから既存の会議に移行Teams。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-111">The user’s pre-existing meetings scheduled for the future will be migrated from on-premises to Teams.</span></span>
- <span data-ttu-id="cdc3a-112">オンプレミスに存在していた連絡先は、ユーザーが初Teamsログオンした直後に、このサイトで利用できます。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-112">Contacts that existed on-premises are available in Teams shortly after the user logs on for the first time.</span></span>
- <span data-ttu-id="cdc3a-113">ユーザーは、ユーザーから通話やチャットを開始Skype for Business、また、会議で新しい会議をスケジュールSkype for Business。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-113">Users cannot initiate calls or chats from Skype for Business, nor can they schedule new meetings in Skype for Business.</span></span> <span data-ttu-id="cdc3a-114">クライアントを開くSkype for Business、次に示すようにTeamsリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-114">If they attempt to open the Skype for Business client, they will be redirected to use Teams as shown below.</span></span> <span data-ttu-id="cdc3a-115">クライアントがTeams場合は、ブラウザーを使用して web バージョンTeamsされます。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-115">If the Teams client is not installed, they will be directed to the web version of Teams using their browser.</span></span><br><br>
    <span data-ttu-id="cdc3a-116">![ユーザーをユーザーにリダイレクトするTeams](../media/go-to-teams-page.png)</span><span class="sxs-lookup"><span data-stu-id="cdc3a-116">![Message redirecting a user to Teams](../media/go-to-teams-page.png)</span></span>

<span data-ttu-id="cdc3a-117">ユーザーを移動する前に、必ず前提条件を確認 [して](move-users-between-on-premises-and-cloud.md#prerequisites) 、ユーザーをクラウドに移動してください。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-117">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span> <span data-ttu-id="cdc3a-118">また、移行を使用している組織の移行と相互運用性のガイダンスと、Teams[を確認Skype for Business。](/microsoftteams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="cdc3a-118">Also be sure to review [Migration and interoperability guidance for organizations using Teams together with Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>


> [!NOTE]
> <span data-ttu-id="cdc3a-119">連絡先をサーバーに移動するには、統合連絡先ストアを on-prem SfB アカウントで無効Teams。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-119">Unified Contact Store should be disabled on the on-prem SfB account for the contact to be moved to Teams.</span></span>


<span data-ttu-id="cdc3a-120">現在、*オンプレミスから* ユーザーにユーザーを移動する方法は 2 Teams。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-120">There are *currently* two methods to move a user from on premises to Teams:</span></span>

- <span data-ttu-id="cdc3a-121">Skype for Business Server 2015 CU8 より前のバージョンを使用している場合、移動には 2 つの手順が必要です (必要に応じて、スクリプトを 1 つの手順としてまとめて実行できます)。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-121">If you are using a version earlier than Skype for Business Server 2015 CU8, the move requires two steps (which can be scripted to be done together as a single step, if desired):</span></span>
  - <span data-ttu-id="cdc3a-122">[ユーザーを (オンプレミスSkype for Business Server) から [オンライン] にSkype for Businessします](move-users-from-on-premises-to-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-122">[Move the user from Skype for Business Server (on premises) to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span></span>
  - <span data-ttu-id="cdc3a-123">ユーザーがオンラインでホームSkype for Business、mode= TeamsOnly を使用してユーザー TeamsUpgradePolicy を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-123">Once the user is homed in Skype for Business Online, assign the user TeamsUpgradePolicy with mode= TeamsOnly.</span></span> <span data-ttu-id="cdc3a-124">TeamsOnly モードを付与するには、次のコマンドレットを [オンライン PowerShell] ウィンドウからSkype for Business実行します。`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span><span class="sxs-lookup"><span data-stu-id="cdc3a-124">To grant TeamsOnly mode, run the following cmdlet from a Skype for Business Online PowerShell window: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span></span>
- <span data-ttu-id="cdc3a-125">Skype for Business Server 2015 CU8 以降の管理ツールがある場合は、上記の方法を使用するか、以下で説明するように 1 つの手順でこの移動を実行できます。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-125">If you have admin tools from Skype for Business Server 2015 CU8 or later, you can use the method above, or you can do this move in one step as described below.</span></span> <span data-ttu-id="cdc3a-126">さらに、必要に応じて、Skype for Business クライアント内で通知を Teams のみに移動する前に、Skype for Business クライアントによって Teams クライアントをサイレント ダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-126">In addition, you can optionally provide a notification within the Skype for Business client prior to moving them to Teams Only as well as optionally have the Teams client silently downloaded by the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="cdc3a-127">Skype for Business Online の今後の退職に備えて、Microsoft は組織が近い将来、Teamsに移行する方法を簡素化します。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-127">In preparation for the upcoming retirement of Skype for Business Online, Microsoft will be simplifying how organizations move to Teams in the near future.</span></span> <span data-ttu-id="cdc3a-128">ユーザーをオンプレミスから Teams に移動する場合、ユーザーをオンプレミスから `-MoveToTeams` TeamsOnly に直接移動するスイッチをすぐに指定する必要がなくなりました `Move-CsUser` 。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-128">When moving a user from on-premises to Teams, it will soon no longer be required to specify the `-MoveToTeams` switch in `Move-CsUser` to move users directly from on-premises to TeamsOnly.</span></span> <span data-ttu-id="cdc3a-129">現在、このスイッチを指定しない場合、ユーザーはオンプレミスの Skype for Business Server にホームから Skype for Business に移行し、モードは変更されません。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-129">Currently if this switch is not specified, users transition from being homed in Skype for Business Server on-premises to Skype for Business Online, and their mode remains unchanged.</span></span> <span data-ttu-id="cdc3a-130">退職後、ユーザーをオンプレミスからクラウドに移動すると、ユーザーには TeamsOnly モードが自動的に割り当てされ、スイッチが実際に指定されたかどうかに関係なく、ユーザーの会議は Teams 会議に自動的に変換されます。 `Move-CsUser` `-MoveToTeams switch had been specified`</span><span class="sxs-lookup"><span data-stu-id="cdc3a-130">After retirement, when moving a user from on-premises to the cloud with `Move-CsUser`, users will automatically be assigned TeamsOnly mode and their meetings from on-premises will be automtically converted to Teams meetings, just as if the `-MoveToTeams switch had been specified`, regardless of whether the switch is actually specified.</span></span> <span data-ttu-id="cdc3a-131">この機能は、2021 年 7 月 31 日の実際の使用が解除される前にリリースされる予定です。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-131">We expect to release this functionality before the actual retirement of July 31, 2021.</span></span>

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="cdc3a-132">オンプレミスからユーザーを直接Skype for Businessに移動Teamsのみ</span><span class="sxs-lookup"><span data-stu-id="cdc3a-132">Move a user directly from Skype for Business on premises to Teams Only</span></span>

<span data-ttu-id="cdc3a-133">Skype for Business Server 2015 と CU8、および Skype for Business Server 2019 のオンプレミス管理ツールを使用すると、以下で説明するように、PowerShell の Move-CsUser コマンドレットまたは Skype for Business Server コントロール パネルを使用して、1 つの手順でユーザーをオンプレミスから Teams Only モードに移動できます。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-133">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to move users from on premises to Teams Only mode in a single step using either the Move-CsUser cmdlet in PowerShell or the Skype for Business Server Control Panel, as described below.</span></span>

### <a name="move-to-teams-using-move-csuser"></a><span data-ttu-id="cdc3a-134">[ファイルを使用してTeamsに移動Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="cdc3a-134">Move to Teams using Move-CsUser</span></span>

<span data-ttu-id="cdc3a-135">Move-CsUser管理シェル PowerShell ウィンドウからSkype for Business使用できます。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-135">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="cdc3a-136">以下の手順と必要なアクセス許可は、ユーザーを Skype for Business Online に移動する場合と同じですが、MoveToTeams スイッチも指定する必要があります。また、ユーザーに Teams のライセンス (Skype for Business Online に加えて) も付与されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-136">The steps below and permissions required are the same as moving a user to Skype for Business Online, except that you must also specify the MoveToTeams switch and you must ensure that the user has also been granted a license for Teams (in addition to Skype for Business Online).</span></span>

<span data-ttu-id="cdc3a-137">「必須の管理資格情報」の説明に従って、オンプレミス環境とクラウド サービス (Microsoft 365 または Office 365) の両方で十分な特権を持っている[必要があります](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-137">You must have sufficient privileges in both the on-premises environment and the cloud service (Microsoft 365 or Office 365), as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="cdc3a-138">両方の環境で特権を持つ 1 つのアカウントを使用するか、オンプレミスの資格情報を使用してオンプレミスの Skype for Business Server 管理シェル ウィンドウを起動し、パラメーターを使用して、必要な管理役割を持つ Microsoft 365 アカウントまたは Office 365 アカウントの資格情報を指定できます。 `-Credential`</span><span class="sxs-lookup"><span data-stu-id="cdc3a-138">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="cdc3a-139">Move-CsUser を使用Teamsモードにユーザーを移動するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-139">To move a user to Teams Only mode using Move-CsUser:</span></span>

- <span data-ttu-id="cdc3a-140">パラメーターを使用して移動するユーザーを `Identity` 指定します。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-140">Specify the user to move using the `Identity` parameter.</span></span>
- <span data-ttu-id="cdc3a-141">値 "sipfed.online.lync" で -Target パラメーターを指定します。 <span>com」</span><span class="sxs-lookup"><span data-stu-id="cdc3a-141">Specify the     -Target     parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="cdc3a-142">スイッチを指定 `MoveToTeams` します。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-142">Specify the `MoveToTeams` switch.</span></span>
- <span data-ttu-id="cdc3a-143">オンプレミスとクラウド サービス (Microsoft 365 または Office 365) の両方に十分なアクセス許可を持つアカウントが 1 つない場合は、パラメーターを使用して、Office 365 で十分なアクセス許可を持つアカウント `-credential` を指定します。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-143">If you do not have one account with sufficient permissions in both on premises and the cloud service (Microsoft 365 or Office 365), use the `-credential` parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="cdc3a-144">アクセス許可を持つアカウントが Microsoft 365またはOffice 365"onmicrosoft" で終了しない場合。 <span>com」の説明に従って、パラメーターを正しい値で指定 `-HostedMigrationOverrideUrl` [する必要があります](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-144">If the account with permissions in Microsoft 365 or Office 365 does not end in “onmicrosoft.<span>com”, you must specify the `-HostedMigrationOverrideUrl` parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="cdc3a-145">次のコマンドレット シーケンスを使用して、ユーザーを TeamsOnly に移動し、Microsoft 365 または Office 365 資格情報が別のアカウントであり、Get-Credential プロンプトの入力として提供されたと見なします。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-145">The following cmdlet sequence can be used to move a user to TeamsOnly, and assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> <span data-ttu-id="cdc3a-146">異なるパラメーターが必要な状況が異なるので、ほとんどの場合の既定のコマンドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-146">As there are different circumstances requiring different parameters, the default command for most cases is:</span></span>

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a><span data-ttu-id="cdc3a-147">[コントロール パネル] Teamsを使用Skype for Business Serverに移動する</span><span class="sxs-lookup"><span data-stu-id="cdc3a-147">Move to Teams using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="cdc3a-148">コントロール パネル アプリSkype for Business Server開きます。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-148">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="cdc3a-149">左側のナビゲーションで、[ユーザー] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-149">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="cdc3a-150">[**検索]** を使用して、ユーザーに移動するユーザーをTeams。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-150">Use **Find** to locate the user(s) you would like to move to Teams.</span></span>
4. <span data-ttu-id="cdc3a-151">ユーザーを選択し、リストの上にある [アクション] ドロップダウンから [選択したユーザーをユーザーに移動する]**を** Teams。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-151">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Teams**.</span></span>
5. <span data-ttu-id="cdc3a-152">ウィザードで、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-152">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="cdc3a-153">メッセージが表示されたら、.Microsoft 365でOffice 365で、十分なアクセス許可を持つアカウントを使用して、Microsoft 365 または onmicrosoft.com にサインインします。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-153">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="cdc3a-154">[ **次へ]** をクリックし、[ **次** へ] をクリックしてもう 1 回ユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-154">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="cdc3a-155">成功または失敗に関する状態メッセージは、ウィザードではなく、メインのコントロール パネル アプリの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-155">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a><span data-ttu-id="cdc3a-156">今後のSkype for Businessをオンプレミス のユーザーに通知Teams</span><span class="sxs-lookup"><span data-stu-id="cdc3a-156">Notify your Skype for Business on-premises users of the upcoming move to Teams</span></span>

<span data-ttu-id="cdc3a-157">cu8 と Skype for Business Server 2015 のオンプレミス管理ツール、および Skype for Business Server 2019 では、Teams への移行についてオンプレミス Skype for Business ユーザーに通知できます。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-157">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to notify on-premises Skype for Business users of their upcoming move to Teams.</span></span> <span data-ttu-id="cdc3a-158">これらの通知を有効にした場合、ユーザーは次に示すように、Skype for Business クライアント (Win32、Mac、Web、およびモバイル) に通知を表示します。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-158">When you enable these notifications, users will see a notification in their Skype for Business client (Win32, Mac, web, and mobile) as shown below.</span></span> <span data-ttu-id="cdc3a-159">ユーザーが [**試す**] ボタンをクリックするとTeamsクライアントがインストールされている場合に起動されます。それ以外の場合、ユーザーはブラウザーで web バージョンTeams移動されます。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-159">If users click the **Try it** button, the Teams client will be launched if it is installed; otherwise, users will be navigated to the web version of Teams in their browser.</span></span> <span data-ttu-id="cdc3a-160">既定では、通知が有効になっている場合、Win32 Skype for Business クライアントは Teams クライアントをサイレント モードでダウンロードし、リッチ クライアントを使用してユーザーを Teams のみモードに移行します。ただし、この動作を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-160">By default, when notifications are enabled, Win32 Skype for Business clients silently download the Teams client so that the rich client is available prior to moving the user to Teams Only mode; however, you can also disable this behavior.</span></span>  <span data-ttu-id="cdc3a-161">通知は、オンプレミスバージョンの Win32 クライアント用にサイレント ダウンロードを使用して構成され、オンプレミスコマンドレット `TeamsUpgradePolicy` を介して制御 `TeamsUpgradeConfiguration` されます。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-161">Notifications are configured using the on-premises version of `TeamsUpgradePolicy`, and silent download for Win32 clients is controlled via the on-premises `TeamsUpgradeConfiguration` cmdlet.</span></span>

> [!TIP]
> <span data-ttu-id="cdc3a-162">一部のサーバーでは、CU8 を使用して 2015 年 2015 年Skype for Business再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-162">Some servers may need to reboot for this to work in Skype for Business 2015 with CU8.</span></span>

![今後の移行に関する通知Teams](../media/teams-upgrade-notification.png)

<span data-ttu-id="cdc3a-164">すぐに Teams にアップグレードされる予定のオンプレミス ユーザーに通知するには、NotifySfBUsers=true を使用して TeamsUpgradePolicy の新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-164">To notify on-premises users that they will soon be upgraded to Teams, create a new instance of TeamsUpgradePolicy with NotifySfBUsers=true.</span></span> <span data-ttu-id="cdc3a-165">次に、ポリシーをユーザーに直接割り当てるか、サイト、プール、またはグローバル レベルでポリシーを設定して、通知するユーザーにポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-165">Then assign that policy to the users who you want to notify, either by assigning the policy directly to the user or by setting the policy at the site, pool, or global level.</span></span> <span data-ttu-id="cdc3a-166">次のコマンドレットは、ユーザー レベルのポリシーを作成して付与します。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-166">The following cmdlets create and grant a user-level policy:</span></span>

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

<span data-ttu-id="cdc3a-167">Teams Win32 クライアントSkype for Businessの自動ダウンロードは、DownloadTeams パラメーターを使用して、オンプレミスの TeamsUpgradeConfiguration コマンドレットを介して制御されます。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-167">Automatic download of Teams via the Skype for Business Win32 client is controlled via the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="cdc3a-168">この構成は、グローバル レベル、サイト レベル、およびプール レベルで作成します。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-168">You create this configuration on a global, site, and pool level.</span></span> <span data-ttu-id="cdc3a-169">たとえば、次のコマンドは、サイト Redmond1 の構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-169">For example, the following command creates the configuration for the site Redmond1:</span></span>

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

<span data-ttu-id="cdc3a-170">既定では、DownloadTeams の値は True です。ただし、指定した *ユーザーに* 対して NotifySfbUser = True の場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="cdc3a-170">By default, the value of DownloadTeams is True; however, it is *only* honored if NotifySfbUser = True for a given user.</span></span>

## <a name="see-also"></a><span data-ttu-id="cdc3a-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="cdc3a-171">See also</span></span>

[<span data-ttu-id="cdc3a-172">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="cdc3a-172">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)

[<span data-ttu-id="cdc3a-173">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="cdc3a-173">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy
)

[<span data-ttu-id="cdc3a-174">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="cdc3a-174">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="cdc3a-175">Skype for Business と共存する</span><span class="sxs-lookup"><span data-stu-id="cdc3a-175">Coexistence with Skype for Business</span></span>](/microsoftteams/coexistence-chat-calls-presence)
