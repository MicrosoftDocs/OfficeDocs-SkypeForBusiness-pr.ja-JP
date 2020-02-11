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
description: '概要: ユーザー設定を移行し、ユーザーを Teams に移動する方法について説明します。'
ms.openlocfilehash: af5281faffa9bd9439e045dc40f67283bb740cb5
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888776"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="f7f72-103">オンプレミスから Teams へのユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="f7f72-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="f7f72-104">オンプレミスから Teams のみにユーザーを移動すると、ユーザーの Skype for Business ホームはオンプレミスからオンラインに移行され、ユーザーは TeamsUpgradePolicy を mode = TeamsOnly で割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f7f72-104">When a user is moved from on premises to Teams Only, the user’s Skype for Business home is moved from on premises to online and the user is assigned TeamsUpgradePolicy with mode=TeamsOnly.</span></span>  <span data-ttu-id="f7f72-105">オンプレミスから TeamsOnly モードにユーザーを移動した後:</span><span class="sxs-lookup"><span data-stu-id="f7f72-105">After a user is moved from on-premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="f7f72-106">他のユーザーからのすべての着信呼び出しとチャット (Skype for Business または Teams から送信された場合を除く) は、ユーザーの Teams クライアントに着陸します。</span><span class="sxs-lookup"><span data-stu-id="f7f72-106">All incoming calls and chats from other users (whether sent from Skype for Business or Teams), will land in the user’s Teams client.</span></span>
- <span data-ttu-id="f7f72-107">ユーザーは、Skype for Business (オンラインまたはオンプレミス) を使用している他のユーザーと相互運用することができます。</span><span class="sxs-lookup"><span data-stu-id="f7f72-107">The user will be able to interoperate with other users who use Skype for Business (whether online or on premises).</span></span>
- <span data-ttu-id="f7f72-108">ユーザーは、フェデレーション組織のユーザーと通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f7f72-108">The user will be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="f7f72-109">そのユーザーによってスケジュールされた新しい会議は Teams 会議です。</span><span class="sxs-lookup"><span data-stu-id="f7f72-109">New meetings scheduled by that user are Teams meetings.</span></span>
- <span data-ttu-id="f7f72-110">ユーザーは、引き続き Skype for Business 会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="f7f72-110">User can still join any Skype for Business meetings.</span></span>
- <span data-ttu-id="f7f72-111">今後予定されているユーザーの既存の会議は、オンプレミスから Teams に移行されます。</span><span class="sxs-lookup"><span data-stu-id="f7f72-111">The user’s pre-existing meetings scheduled for the future will be migrated from on-premises to Teams.</span></span>
- <span data-ttu-id="f7f72-112">社内に存在していた連絡先は、ユーザーが初めてログオンした直後に Teams で利用できます。</span><span class="sxs-lookup"><span data-stu-id="f7f72-112">Contacts that existed on premises are available in Teams shortly after the user logs on for the first time.</span></span>
- <span data-ttu-id="f7f72-113">ユーザーは、Skype for business から通話やチャットを開始することはできません。また、Skype for Business で新しい会議をスケジュールすることもできません。</span><span class="sxs-lookup"><span data-stu-id="f7f72-113">Users cannot initiate calls or chats from Skype for Business, nor can they schedule new meetings in Skype for Business.</span></span> <span data-ttu-id="f7f72-114">ユーザーが Skype for Business クライアントを開こうとすると、以下に示すように Teams を使用するようにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="f7f72-114">If they attempt to open the Skype for Business client, they will be redirected to use Teams as shown below.</span></span> <span data-ttu-id="f7f72-115">Teams クライアントがインストールされていない場合は、ブラウザーを使用して、チームの web バージョンに転送されます。</span><span class="sxs-lookup"><span data-stu-id="f7f72-115">If the Teams client is not installed, they will be directed to the web version of Teams using their browser.</span></span><br><br>
    <span data-ttu-id="f7f72-116">![ユーザーを Teams にリダイレクトするメッセージ](../media/go-to-teams-page.png)</span><span class="sxs-lookup"><span data-stu-id="f7f72-116">![Message redirecting a user to Teams](../media/go-to-teams-page.png)</span></span>

<span data-ttu-id="f7f72-117">ユーザーを移動する前に、ユーザーをクラウドに移動するための[前提条件](move-users-between-on-premises-and-cloud.md#prerequisites)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="f7f72-117">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span> <span data-ttu-id="f7f72-118">また[、Teams と Skype For business を併用している組織の移行と相互運用性のガイダンス](/microsoftteams/migration-interop-guidance-for-teams-with-skype)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="f7f72-118">Also be sure to review [Migration and interoperability guidance for organizations using Teams together with Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>


> [!NOTE]
> <span data-ttu-id="f7f72-119">連絡先を Teams に移行するには、オンプレミスの SfB アカウントで統合連絡先ストアを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f72-119">Unified Contact Store should be disabled on the on-prem SfB account for the contact to be moved to Teams.</span></span>


<span data-ttu-id="f7f72-120">オンプレミスから Teams にユーザーを移動するには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="f7f72-120">There are two methods to move a user from on premises to Teams:</span></span>

- <span data-ttu-id="f7f72-121">Skype for Business Server 2015 CU8 より前のバージョンを使用している場合は、次の2つの手順を実行する必要があります (必要に応じて、1つの手順として一緒にスクリプトを作成することもできます)。</span><span class="sxs-lookup"><span data-stu-id="f7f72-121">If you are using a version earlier than Skype for Business Server 2015 CU8, the move requires two steps (which can be scripted to be done together as a single step, if desired):</span></span>
  - <span data-ttu-id="f7f72-122">[ユーザーを skype For Business Server (オンプレミス) から skype for Business Online に移動](move-users-from-on-premises-to-skype-for-business-online.md)します。</span><span class="sxs-lookup"><span data-stu-id="f7f72-122">[Move the user from Skype for Business Server (on premises) to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span></span>
  - <span data-ttu-id="f7f72-123">ユーザーが Skype for Business Online に所属したら、user TeamsUpgradePolicy を mode = TeamsOnly として割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f7f72-123">Once the user is homed in Skype for Business Online, assign the user TeamsUpgradePolicy with mode= TeamsOnly.</span></span> <span data-ttu-id="f7f72-124">TeamsOnly モードを許可するには、Skype for Business Online PowerShell ウィンドウから次のコマンドレットを実行します。`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span><span class="sxs-lookup"><span data-stu-id="f7f72-124">To grant TeamsOnly mode, run the following cmdlet from a Skype for Business Online PowerShell window: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span></span>
- <span data-ttu-id="f7f72-125">Skype for Business Server 2015 CU8 以降の管理ツールがある場合は、上記の方法を使用することができます。または、次に示す手順でこの操作を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="f7f72-125">If you have admin tools from Skype for Business Server 2015 CU8 or later, you can use the method above, or you can do this move in one step as described below.</span></span> <span data-ttu-id="f7f72-126">また、必要に応じて Skype for business クライアントで通知を提供することもできます。これは、必要に応じて、Skype for business クライアントによって Teams クライアントが自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="f7f72-126">In addition, you can optionally provide a notification within the Skype for Business client prior to moving them to Teams Only as well as optionally have the Teams client silently downloaded by the Skype for Business client.</span></span>

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="f7f72-127">オンプレミスの Skype for Business から Teams のみにユーザーを直接移動する</span><span class="sxs-lookup"><span data-stu-id="f7f72-127">Move a user directly from Skype for Business on premises to Teams Only</span></span>

<span data-ttu-id="f7f72-128">Skype for business Server 2015 with CU8 のオンプレミスの管理ツールと、Skype for Business Server 2019 では、ユーザーをオンプレミスから Teams のみモードに移行するために、PowerShell または Skype for Business Se での移動-CsUser コマンドレットを使用することができます。以下に示すように、rver コントロールパネル。</span><span class="sxs-lookup"><span data-stu-id="f7f72-128">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to move users from on premises to Teams Only mode in a single step using either the Move-CsUser cmdlet in PowerShell or the Skype for Business Server Control Panel, as described below.</span></span>

### <a name="move-to-teams-using-move-csuser"></a><span data-ttu-id="f7f72-129">「Move-CsUser を使用して Teams に移動する」</span><span class="sxs-lookup"><span data-stu-id="f7f72-129">Move to Teams using Move-CsUser</span></span>

<span data-ttu-id="f7f72-130">Move-CsUser は、オンプレミスの Skype for Business 管理シェル PowerShell ウィンドウから入手できます。</span><span class="sxs-lookup"><span data-stu-id="f7f72-130">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="f7f72-131">次に示す手順および必要なアクセス許可は、ユーザーを Skype for Business Online に移動する場合と同じですが、ユーザーには MoveToTeams スイッチも指定する必要があります。また、ユーザーにも Teams のライセンスが付与されていることを確認する必要があります (Skype for Business に加えて)。オンライン)。</span><span class="sxs-lookup"><span data-stu-id="f7f72-131">The steps below and permissions required are the same as moving a user to Skype for Business Online, except that you must also specify the MoveToTeams switch and you must ensure that the user has also been granted a license for Teams (in addition to Skype for Business Online).</span></span>

<span data-ttu-id="f7f72-132">[必要な管理者の資格情報](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)で説明されているように、オンプレミス環境と Office 365 テナントの両方に十分な特権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f72-132">You must have sufficient privileges in both the on-premises environment and the Office 365 tenant, as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="f7f72-133">両方の環境で権限を持つ単一のアカウントを使用するか、オンプレミスの資格情報を使用してオンプレミスの Skype for Business Server 管理シェルウィンドウを開始`-Credential`することができます。また、パラメーターを使用して、必要な office 365 管理者の役割を持つ office 365 アカウントの資格情報を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f7f72-133">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="f7f72-134">ユーザーを、CsUser を使用して Teams 専用モードに移行するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f7f72-134">To move a user to Teams Only mode using Move-CsUser:</span></span>

- <span data-ttu-id="f7f72-135">`Identity`パラメーターを使用して移動するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f72-135">Specify the user to move using the `Identity` parameter.</span></span>
- <span data-ttu-id="f7f72-136">値が "sipfed" の-Target パラメーターを指定します。<span>com "。</span><span class="sxs-lookup"><span data-stu-id="f7f72-136">Specify the     -Target     parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="f7f72-137">`MoveToTeams`スイッチを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f72-137">Specify the `MoveToTeams` switch.</span></span>
- <span data-ttu-id="f7f72-138">オンプレミスと Office 365 の両方に十分な権限を持つアカウントがない場合は、 `-credential`パラメーターを使用して、office 365 に十分な権限を持つアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f72-138">If you do not have one account with sufficient permissions in both on premises and Office 365, use the `-credential` parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="f7f72-139">Office 365 のアクセス許可を持つアカウントが "onmicrosoft" で終了していない場合。<span>com "では、「 `-HostedMigrationOverrideUrl` [必要な管理者の資格情報](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)」に説明されているように、適切な値を指定してパラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f72-139">If the account with permissions in Office 365 does not end in “onmicrosoft.<span>com”, you must specify the `-HostedMigrationOverrideUrl` parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="f7f72-140">次のコマンドレットシーケンスを使用して、ユーザーを TeamsOnly に移動できます。また、Office 365 資格情報が別のアカウントであると仮定して、資格情報の取得を求めるメッセージの入力として指定します。</span><span class="sxs-lookup"><span data-stu-id="f7f72-140">The following cmdlet sequence can be used to move a user to TeamsOnly, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f7f72-141">Skype for Business Server コントロールパネルを使用して Teams に移動する</span><span class="sxs-lookup"><span data-stu-id="f7f72-141">Move to Teams using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f7f72-142">Skype for Business Server コントロールパネルアプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7f72-142">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="f7f72-143">左側のナビゲーションで、[**ユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7f72-143">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="f7f72-144">[**検索**] を使用して、Teams に移動するユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="f7f72-144">Use **Find** to locate the user(s) you would like to move to Teams.</span></span>
4. <span data-ttu-id="f7f72-145">ユーザーを選択し、リストの上にある**アクション**ドロップダウンから、[**選択したユーザーを Teams に移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7f72-145">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Teams**.</span></span>
5. <span data-ttu-id="f7f72-146">ウィザードで、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7f72-146">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="f7f72-147">メッセージが表示された場合は、onmicrosoft.com で終了し、十分な権限があるアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f7f72-147">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="f7f72-148">[**次へ**] をクリックし、[**次**へ] をもう一度クリックして、ユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="f7f72-148">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="f7f72-149">成功または失敗に関するステータスメッセージは、ウィザードではなく、メインコントロールパネルアプリの上部に表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f7f72-149">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a><span data-ttu-id="f7f72-150">今後 Teams に移行するために、Skype for Business のオンプレミスユーザーに通知する</span><span class="sxs-lookup"><span data-stu-id="f7f72-150">Notify your Skype for Business on-premises users of the upcoming move to Teams</span></span>

<span data-ttu-id="f7f72-151">Skype for business Server 2015 と CU8 のオンプレミスの管理ツール、および Skype for Business Server 2019 では、今後 Teams への移行の際に社内の Skype for Business ユーザーに通知することができます。</span><span class="sxs-lookup"><span data-stu-id="f7f72-151">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to notify on-premises Skype for Business users of their upcoming move to Teams.</span></span> <span data-ttu-id="f7f72-152">これらの通知を有効にすると、ユーザーには、次に示すように、Skype for Business クライアント (Win32、Mac、web、およびモバイル) に通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7f72-152">When you enable these notifications, users will see a notification in their Skype for Business client (Win32, Mac, web, and mobile) as shown below.</span></span> <span data-ttu-id="f7f72-153">ユーザーが [**試す**] ボタンをクリックすると、Teams クライアントがインストールされている場合は起動されます。そうしないと、ユーザーはブラウザー内の Teams の web バージョンに移動します。</span><span class="sxs-lookup"><span data-stu-id="f7f72-153">If users click the **Try it** button, the Teams client will be launched if it is installed; otherwise, users will be navigated to the web version of Teams in their browser.</span></span> <span data-ttu-id="f7f72-154">既定では、通知が有効になっている場合、Win32 Skype for Business クライアントは、ユーザーを Teams のみモードに移行する前に、リッチクライアントが使用可能になるように Teams クライアントをダウンロードします。ただし、この動作を無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f7f72-154">By default, when notifications are enabled, Win32 Skype for Business clients silently download the Teams client so that the rich client is available prior to moving the user to Teams Only mode; however, you can also disable this behavior.</span></span>  <span data-ttu-id="f7f72-155">通知はの`TeamsUpgradePolicy`社内バージョンを使用して構成され、Win32 クライアントのサイレントダウンロードは社内`TeamsUpgradeConfiguration`のコマンドレットによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="f7f72-155">Notifications are configured using the on-premises version of `TeamsUpgradePolicy`, and silent download for Win32 clients is controlled via the on-premises `TeamsUpgradeConfiguration` cmdlet.</span></span>

> [!TIP]
> <span data-ttu-id="f7f72-156">CU8 を使用して Skype for Business 2015 で動作するために、一部のサーバーで再起動が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="f7f72-156">Some servers may need to reboot for this to work in Skype for Business 2015 with CU8.</span></span>

![Teams への今後の移行の通知](../media/teams-upgrade-notification.png)

<span data-ttu-id="f7f72-158">すぐに Teams にアップグレードすることをオンプレミスのユーザーに通知するには、NotifySfBUsers = true を使用して TeamsUpgradePolicy の新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7f72-158">To notify on-premises users that they will soon be upgraded to Teams, create a new instance of TeamsUpgradePolicy with NotifySfBUsers=true.</span></span> <span data-ttu-id="f7f72-159">そのポリシーをユーザーに直接割り当てるか、サイト、プール、またはグローバルレベルでポリシーを設定することによって、そのポリシーを通知するユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f7f72-159">Then assign that policy to the users who you want to notify, either by assigning the policy directly to the user or by setting the policy at the site, pool, or global level.</span></span> <span data-ttu-id="f7f72-160">次のコマンドレットは、ユーザーレベルのポリシーを作成して付与します。</span><span class="sxs-lookup"><span data-stu-id="f7f72-160">The following cmdlets create and grant a user-level policy:</span></span>

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

<span data-ttu-id="f7f72-161">Skype for Business Win32 クライアントを使用した Teams の自動ダウンロードは、TeamsUpgradeConfiguration コマンドレットで DownloadTeams パラメーターを使用して制御されます。</span><span class="sxs-lookup"><span data-stu-id="f7f72-161">Automatic download of Teams via the Skype for Business Win32 client is controlled via the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="f7f72-162">この構成は、グローバル、サイト、およびプールレベルで作成します。</span><span class="sxs-lookup"><span data-stu-id="f7f72-162">You create this configuration on a global, site, and pool level.</span></span> <span data-ttu-id="f7f72-163">たとえば、次のコマンドを実行すると、サイト Redmond1 というの構成が作成されます。</span><span class="sxs-lookup"><span data-stu-id="f7f72-163">For example, the following command creates the configuration for the site Redmond1:</span></span>

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

<span data-ttu-id="f7f72-164">既定では、DownloadTeams の値は True です。ただし、指定されたユーザーの NotifySfbUser = True の場合に*のみ*無視されます。</span><span class="sxs-lookup"><span data-stu-id="f7f72-164">By default, the value of DownloadTeams is True; however, it is *only* honored if NotifySfbUser = True for a given user.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7f72-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7f72-165">See also</span></span>

[<span data-ttu-id="f7f72-166">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="f7f72-166">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[<span data-ttu-id="f7f72-167">CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="f7f72-167">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[<span data-ttu-id="f7f72-168">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="f7f72-168">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="f7f72-169">Skype for Business との共存</span><span class="sxs-lookup"><span data-stu-id="f7f72-169">Coexistence with Skype for Business</span></span>](/microsoftteams/coexistence-chat-calls-presence)
