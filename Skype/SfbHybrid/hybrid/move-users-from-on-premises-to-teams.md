---
title: Skype for Business Server 2019 から Teams にユーザーを移動する
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
description: '概要: ユーザー設定を移行し、ユーザーを Teams に移動する方法について学習します。'
ms.openlocfilehash: 4a57d802d6405652724ce28ed2d26221dcc8db0f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110653"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="f8cc2-103">オンプレミスから Teams にユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="f8cc2-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="f8cc2-104">ユーザーがオンプレミスから Teams Only に移動すると、ユーザーの Skype for Business ホームはオンプレミスからオンラインに移動され、ユーザーには mode=TeamsOnly を使用して TeamsUpgradePolicy が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-104">When a user is moved from on premises to Teams Only, the user’s Skype for Business home is moved from on premises to online and the user is assigned TeamsUpgradePolicy with mode=TeamsOnly.</span></span>  <span data-ttu-id="f8cc2-105">ユーザーをオンプレミスから TeamsOnly モードに移動した後は、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-105">After a user is moved from on-premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="f8cc2-106">他のユーザーからのすべての着信呼び出しとチャット (Skype for Business または Teams から送信された場合) は、ユーザーの Teams クライアントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-106">All incoming calls and chats from other users (whether sent from Skype for Business or Teams), will land in the user’s Teams client.</span></span>
- <span data-ttu-id="f8cc2-107">ユーザーは、Skype for Business を使用する他のユーザー (オンラインでもオンプレミスでも) と相互運用できます。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-107">The user will be able to interoperate with other users who use Skype for Business (whether online or on premises).</span></span>
- <span data-ttu-id="f8cc2-108">ユーザーはフェデレーション組織のユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-108">The user will be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="f8cc2-109">そのユーザーがスケジュールした新しい会議は Teams 会議です。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-109">New meetings scheduled by that user are Teams meetings.</span></span>
- <span data-ttu-id="f8cc2-110">ユーザーは引き続き Skype for Business 会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-110">User can still join any Skype for Business meetings.</span></span>
- <span data-ttu-id="f8cc2-111">将来予定されているユーザーの既存の会議は、オンプレミスから Teams に移行されます。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-111">The user’s pre-existing meetings scheduled for the future will be migrated from on-premises to Teams.</span></span>
- <span data-ttu-id="f8cc2-112">オンプレミスに存在していた連絡先は、ユーザーが初めてログオンした直後に Teams で利用できます。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-112">Contacts that existed on-premises are available in Teams shortly after the user logs on for the first time.</span></span>
- <span data-ttu-id="f8cc2-113">ユーザーは、Skype for Business から通話やチャットを開始したり、Skype for Business で新しい会議をスケジュールしたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-113">Users cannot initiate calls or chats from Skype for Business, nor can they schedule new meetings in Skype for Business.</span></span> <span data-ttu-id="f8cc2-114">Skype for Business クライアントを開く場合、以下に示すように Teams を使用するためにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-114">If they attempt to open the Skype for Business client, they will be redirected to use Teams as shown below.</span></span> <span data-ttu-id="f8cc2-115">Teams クライアントがインストールされていない場合は、ブラウザーを使用して Web バージョンの Teams に送信されます。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-115">If the Teams client is not installed, they will be directed to the web version of Teams using their browser.</span></span><br><br>
    <span data-ttu-id="f8cc2-116">![Teams にユーザーをリダイレクトするメッセージ](../media/go-to-teams-page.png)</span><span class="sxs-lookup"><span data-stu-id="f8cc2-116">![Message redirecting a user to Teams](../media/go-to-teams-page.png)</span></span>

<span data-ttu-id="f8cc2-117">ユーザーを移動する前に、必ず前提条件を確認 [して](move-users-between-on-premises-and-cloud.md#prerequisites) 、ユーザーをクラウドに移動してください。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-117">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span> <span data-ttu-id="f8cc2-118">また、Teams と Skype for Business を組み合わせて使用する組織の移行と相互運用性に関する [ガイダンスも必ず確認してください](/microsoftteams/migration-interop-guidance-for-teams-with-skype)。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-118">Also be sure to review [Migration and interoperability guidance for organizations using Teams together with Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>


> [!NOTE]
> <span data-ttu-id="f8cc2-119">連絡先を Teams に移動するには、統合連絡先ストアを On-prem SfB アカウントで無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-119">Unified Contact Store should be disabled on the on-prem SfB account for the contact to be moved to Teams.</span></span>


<span data-ttu-id="f8cc2-120">ユーザーをオンプレミスから Teams に移動するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-120">There are two methods to move a user from on premises to Teams:</span></span>

- <span data-ttu-id="f8cc2-121">Skype for Business Server 2015 CU8 より前のバージョンを使用している場合、移動には 2 つの手順が必要です (必要に応じて、1 つの手順として一緒にスクリプトを実行できます)。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-121">If you are using a version earlier than Skype for Business Server 2015 CU8, the move requires two steps (which can be scripted to be done together as a single step, if desired):</span></span>
  - <span data-ttu-id="f8cc2-122">[ユーザーを Skype for Business Server (オンプレミス) から Skype for Business Online に移動します](move-users-from-on-premises-to-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-122">[Move the user from Skype for Business Server (on premises) to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span></span>
  - <span data-ttu-id="f8cc2-123">ユーザーが Skype for Business Online に参加したら、mode= TeamsOnly を使用してユーザー TeamsUpgradePolicy を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-123">Once the user is homed in Skype for Business Online, assign the user TeamsUpgradePolicy with mode= TeamsOnly.</span></span> <span data-ttu-id="f8cc2-124">TeamsOnly モードを付与するには、Skype for Business Online PowerShell ウィンドウから次のコマンドレットを実行します。 `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span><span class="sxs-lookup"><span data-stu-id="f8cc2-124">To grant TeamsOnly mode, run the following cmdlet from a Skype for Business Online PowerShell window: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span></span>
- <span data-ttu-id="f8cc2-125">Skype for Business Server 2015 CU8 以降の管理ツールがある場合は、上記の方法を使用するか、以下で説明するように 1 つの手順でこの移動を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-125">If you have admin tools from Skype for Business Server 2015 CU8 or later, you can use the method above, or you can do this move in one step as described below.</span></span> <span data-ttu-id="f8cc2-126">さらに、必要に応じて、Skype for Business クライアント内で通知を Teams Only に移動する前に通知を提供し、必要に応じて Teams クライアントを Skype for Business クライアントによってサイレント ダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-126">In addition, you can optionally provide a notification within the Skype for Business client prior to moving them to Teams Only as well as optionally have the Teams client silently downloaded by the Skype for Business client.</span></span>

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="f8cc2-127">オンプレミスの Skype for Business から Teams 専用にユーザーを直接移動する</span><span class="sxs-lookup"><span data-stu-id="f8cc2-127">Move a user directly from Skype for Business on premises to Teams Only</span></span>

<span data-ttu-id="f8cc2-128">Skype for Business Server 2015 と CU8 のオンプレミス管理ツール、および Skype for Business Server 2019 では、以下で説明するように、PowerShell の Move-CsUser コマンドレットまたは Skype for Business Server コントロール パネルのいずれかを使用して、オンプレミスから Teams Only モードにユーザーを移動できます。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-128">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to move users from on premises to Teams Only mode in a single step using either the Move-CsUser cmdlet in PowerShell or the Skype for Business Server Control Panel, as described below.</span></span>

### <a name="move-to-teams-using-move-csuser"></a><span data-ttu-id="f8cc2-129">サーバーを使用して Teams に移動Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="f8cc2-129">Move to Teams using Move-CsUser</span></span>

<span data-ttu-id="f8cc2-130">Move-CsUserは、オンプレミスの Skype for Business Management Shell PowerShell ウィンドウから利用できます。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-130">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="f8cc2-131">以下の手順と必要なアクセス許可は、ユーザーを Skype for Business Online に移動する場合と同じですが、MoveToTeams スイッチも指定する必要があります。また、ユーザーに Teams のライセンス (Skype for Business Online に加えて) も付与されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-131">The steps below and permissions required are the same as moving a user to Skype for Business Online, except that you must also specify the MoveToTeams switch and you must ensure that the user has also been granted a license for Teams (in addition to Skype for Business Online).</span></span>

<span data-ttu-id="f8cc2-132">「必須の管理資格情報」の説明に従って、オンプレミス環境とクラウド サービス (Microsoft 365 または Office 365) の両方で十分な特権を持っている [必要があります](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-132">You must have sufficient privileges in both the on-premises environment and the cloud service (Microsoft 365 or Office 365), as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="f8cc2-133">両方の環境で特権を持つ 1 つのアカウントを使用するか、オンプレミスの資格情報を使用してオンプレミスの Skype for Business Server 管理シェル ウィンドウを起動し、パラメーターを使用して、必要な管理役割を持つ `-Credential` Microsoft 365 または Office 365 アカウントの資格情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-133">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="f8cc2-134">Move-CsUser を使用してユーザーを Teams Only モードに移動するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-134">To move a user to Teams Only mode using Move-CsUser:</span></span>

- <span data-ttu-id="f8cc2-135">パラメーターを使用して移動するユーザーを `Identity` 指定します。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-135">Specify the user to move using the `Identity` parameter.</span></span>
- <span data-ttu-id="f8cc2-136">値 "sipfed.online.lync" で -Target パラメーターを指定します。 <span>com」</span><span class="sxs-lookup"><span data-stu-id="f8cc2-136">Specify the     -Target     parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="f8cc2-137">スイッチを指定 `MoveToTeams` します。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-137">Specify the `MoveToTeams` switch.</span></span>
- <span data-ttu-id="f8cc2-138">オンプレミスとクラウド サービス (Microsoft 365 または Office 365) の両方に十分なアクセス許可を持つアカウントが 1 つない場合は、パラメーターを使用して、Office 365 で十分なアクセス許可を持つ `-credential` アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-138">If you do not have one account with sufficient permissions in both on premises and the cloud service (Microsoft 365 or Office 365), use the `-credential` parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="f8cc2-139">Microsoft 365 または microsoft 365 または Office 365 のアクセス許可を持つアカウントが "onmicrosoft" で終了しない場合。 <span>com」の説明に従って、パラメーターを正しい値で指定 `-HostedMigrationOverrideUrl` [する必要があります](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-139">If the account with permissions in Microsoft 365 or Office 365 does not end in “onmicrosoft.<span>com”, you must specify the `-HostedMigrationOverrideUrl` parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="f8cc2-140">次のコマンドレット シーケンスを使用して、ユーザーを TeamsOnly に移動し、Microsoft 365 または Office 365 資格情報が別のアカウントであり、Get-Credential プロンプトの入力として提供されたと見なします。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-140">The following cmdlet sequence can be used to move a user to TeamsOnly, and assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> <span data-ttu-id="f8cc2-141">異なるパラメーターが必要な状況が異なるので、ほとんどの場合の既定のコマンドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-141">As there are different circumstances requiring different parameters, the default command for most cases is:</span></span>

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f8cc2-142">Skype for Business Server コントロール パネルを使用して Teams に移動する</span><span class="sxs-lookup"><span data-stu-id="f8cc2-142">Move to Teams using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f8cc2-143">Skype for Business Server コントロール パネル アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-143">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="f8cc2-144">左側のナビゲーションで、[ユーザー] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-144">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="f8cc2-145">[ **検索]** を使用して、Teams に移動するユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-145">Use **Find** to locate the user(s) you would like to move to Teams.</span></span>
4. <span data-ttu-id="f8cc2-146">ユーザーを選択し、リストの上にある **[** アクション] ドロップダウンから [選択したユーザーを Teams に移動する] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-146">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Teams**.</span></span>
5. <span data-ttu-id="f8cc2-147">ウィザードで、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-147">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="f8cc2-148">メッセージが表示されたら、Microsoft 365 または Office 365 に .onmicrosoft.com で終了し、十分なアクセス許可を持つアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-148">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="f8cc2-149">[ **次へ]** をクリックし、[ **次** へ] をクリックしてもう 1 回ユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-149">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="f8cc2-150">成功または失敗に関する状態メッセージは、ウィザードではなく、メインのコントロール パネル アプリの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-150">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a><span data-ttu-id="f8cc2-151">Skype for Business オンプレミス ユーザーに Teams への今後の移行を通知する</span><span class="sxs-lookup"><span data-stu-id="f8cc2-151">Notify your Skype for Business on-premises users of the upcoming move to Teams</span></span>

<span data-ttu-id="f8cc2-152">Skype for Business Server 2015 と CU8、Skype for Business Server 2019 のオンプレミス管理ツールを使用すると、オンプレミスの Skype for Business ユーザーに Teams への移行を通知できます。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-152">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to notify on-premises Skype for Business users of their upcoming move to Teams.</span></span> <span data-ttu-id="f8cc2-153">これらの通知を有効にした場合、ユーザーは Skype for Business クライアント (Win32、Mac、Web、およびモバイル) に以下のように通知を表示します。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-153">When you enable these notifications, users will see a notification in their Skype for Business client (Win32, Mac, web, and mobile) as shown below.</span></span> <span data-ttu-id="f8cc2-154">ユーザーが [ **試す] ボタンを** クリックすると、Teams クライアントがインストールされている場合は起動されます。それ以外の場合、ユーザーはブラウザーで Web バージョンの Teams に移動します。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-154">If users click the **Try it** button, the Teams client will be launched if it is installed; otherwise, users will be navigated to the web version of Teams in their browser.</span></span> <span data-ttu-id="f8cc2-155">既定では、通知が有効な場合、Win32 Skype for Business クライアントは Teams クライアントをサイレント モードでダウンロードして、リッチ クライアントを Teams Only モードに移行する前にリッチ クライアントを使用できます。ただし、この動作を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-155">By default, when notifications are enabled, Win32 Skype for Business clients silently download the Teams client so that the rich client is available prior to moving the user to Teams Only mode; however, you can also disable this behavior.</span></span>  <span data-ttu-id="f8cc2-156">通知は、オンプレミスバージョンの Win32 クライアント用にサイレント ダウンロードを使用して構成され、オンプレミスコマンドレット `TeamsUpgradePolicy` を介して制御 `TeamsUpgradeConfiguration` されます。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-156">Notifications are configured using the on-premises version of `TeamsUpgradePolicy`, and silent download for Win32 clients is controlled via the on-premises `TeamsUpgradeConfiguration` cmdlet.</span></span>

> [!TIP]
> <span data-ttu-id="f8cc2-157">一部のサーバーでは、CU8 を使用して Skype for Business 2015 で動作するために再起動が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-157">Some servers may need to reboot for this to work in Skype for Business 2015 with CU8.</span></span>

![Teams への今後の移行の通知](../media/teams-upgrade-notification.png)

<span data-ttu-id="f8cc2-159">オンプレミスのユーザーに Teams へのアップグレードが近い場合に通知するには、NotifySfBUsers=true を使用して TeamsUpgradePolicy の新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-159">To notify on-premises users that they will soon be upgraded to Teams, create a new instance of TeamsUpgradePolicy with NotifySfBUsers=true.</span></span> <span data-ttu-id="f8cc2-160">次に、ポリシーをユーザーに直接割り当てるか、サイト、プール、またはグローバル レベルでポリシーを設定して、通知するユーザーにポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-160">Then assign that policy to the users who you want to notify, either by assigning the policy directly to the user or by setting the policy at the site, pool, or global level.</span></span> <span data-ttu-id="f8cc2-161">次のコマンドレットは、ユーザー レベルのポリシーを作成して付与します。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-161">The following cmdlets create and grant a user-level policy:</span></span>

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

<span data-ttu-id="f8cc2-162">Skype for Business Win32 クライアントを介した Teams の自動ダウンロードは、DownloadTeams パラメーターを使用して、オンプレミスの TeamsUpgradeConfiguration コマンドレットを介して制御されます。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-162">Automatic download of Teams via the Skype for Business Win32 client is controlled via the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="f8cc2-163">この構成は、グローバル レベル、サイト レベル、およびプール レベルで作成します。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-163">You create this configuration on a global, site, and pool level.</span></span> <span data-ttu-id="f8cc2-164">たとえば、次のコマンドは、サイト Redmond1 の構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-164">For example, the following command creates the configuration for the site Redmond1:</span></span>

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

<span data-ttu-id="f8cc2-165">既定では、DownloadTeams の値は True です。ただし、指定した *ユーザーに* 対して NotifySfbUser = True の場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="f8cc2-165">By default, the value of DownloadTeams is True; however, it is *only* honored if NotifySfbUser = True for a given user.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8cc2-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8cc2-166">See also</span></span>

[<span data-ttu-id="f8cc2-167">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="f8cc2-167">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)

[<span data-ttu-id="f8cc2-168">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="f8cc2-168">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy
)

[<span data-ttu-id="f8cc2-169">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="f8cc2-169">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="f8cc2-170">Skype for Business と共存する</span><span class="sxs-lookup"><span data-stu-id="f8cc2-170">Coexistence with Skype for Business</span></span>](/microsoftteams/coexistence-chat-calls-presence)