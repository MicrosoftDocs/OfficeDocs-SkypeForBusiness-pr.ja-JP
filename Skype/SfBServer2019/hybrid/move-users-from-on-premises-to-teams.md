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
ms.openlocfilehash: 6bee0562b38ce3119306e23b11ea50ebdb8ac3e9
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2018
ms.locfileid: "27244033"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="fb9b3-103">移動ユーザーがチームを設置</span><span class="sxs-lookup"><span data-stu-id="fb9b3-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="fb9b3-104">会社のホームに移動した設置型のオンラインと、ユーザー モードでは TeamsUpgradePolicy に割り当てられます、ユーザーが Skype のユーザーに移動した場合の社内チームだけに、TeamsOnly を = します。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-104">When a user is moved from on premises to Teams Only, the user’s Skype for Business home is moved from on premises to online and the user is assigned TeamsUpgradePolicy with mode=TeamsOnly.</span></span>  <span data-ttu-id="fb9b3-105">ユーザー後から移動設置型 TeamsOnly モードにします。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-105">After a user is moved from on-premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="fb9b3-106">すべての着信を呼び出し、他のユーザー (ビジネスやチームのために、Skype から送信) かどうかのチャット ユーザーのチームのクライアントで着陸します。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-106">All incoming calls and chats from other users (whether sent from Skype for Business or Teams), will land in the user’s Teams client.</span></span>
- <span data-ttu-id="fb9b3-107">ユーザーは (オンラインまたは設置型) かどうかは、ビジネスの Skype を使用している他のユーザーと相互運用することになります。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-107">The user will be able to interoperate with other users who use Skype for Business (whether online or on premises).</span></span> 
- <span data-ttu-id="fb9b3-108">ユーザーはフェデレーション組織のユーザーと通信することになります。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-108">The user will be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="fb9b3-109">そのユーザーが予定されている新規の会議は、チームの会議です。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-109">New meetings scheduled by that user are Teams meetings.</span></span>
- <span data-ttu-id="fb9b3-110">ユーザーは、ビジネス会議のため、Skype にも参加できます。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-110">User can still join any Skype for Business meetings.</span></span>
- <span data-ttu-id="fb9b3-111">Skype にはオンライン ビジネスの未来に予定されているユーザーの既存の会議を設置型から移行されます。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-111">The user’s pre-existing meetings scheduled for the future will be migrated from on-premises to Skype for Business Online.</span></span>
- <span data-ttu-id="fb9b3-112">施設内に存在していた連絡先は、最初にユーザーがログオンした後にすぐにチームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-112">Contacts that existed on premises are available in Teams shortly after the user logs on for the first time.</span></span>
- <span data-ttu-id="fb9b3-113">ユーザーが呼び出しまたはビジネス用の Skype のチャットを開始できませんも、ビジネスの Skype の新しい会議をスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-113">Users cannot initiate calls or chats from Skype for Business, nor can they schedule new meetings in Skype for Business.</span></span> <span data-ttu-id="fb9b3-114">ビジネス クライアント用の Skype を開くしようとする場合は、チームを使用して、次のようにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-114">If they attempt to open the Skype for Business client, they will be redirected to use Teams as shown below.</span></span> <span data-ttu-id="fb9b3-115">チームのクライアントがインストールされていない場合が、ブラウザーを使用するチームの web バージョンに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-115">If the Teams client is not installed, they will be directed to the web version of Teams using their browser.</span></span><br><br>
    <span data-ttu-id="fb9b3-116">![チームにユーザーをリダイレクトするメッセージ](../media/go-to-teams-page.png)</span><span class="sxs-lookup"><span data-stu-id="fb9b3-116">![Message redirecting a user to Teams](../media/go-to-teams-page.png)</span></span>

<span data-ttu-id="fb9b3-117">すべてのユーザーを移動する前に必ずユーザーをクラウドに移行する[前提条件](move-users-between-on-premises-and-cloud.md#prerequisites)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-117">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span> <span data-ttu-id="fb9b3-118">必ず[チームと、ビジネス用の Skype を使用する組織の移行と相互運用性](/microsoftteams/migration-interop-guidance-for-teams-with-skype)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-118">Also be sure to review [Migration and interoperability guidance for organizations using Teams together with Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>

<span data-ttu-id="fb9b3-119">社内のチームからユーザーを移動する方法は 2 つです。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-119">There are two methods to move a user from on premises to Teams:</span></span>

- <span data-ttu-id="fb9b3-120">ビジネス サーバー 2015 CU8 の Skype より前のバージョンを使用している場合、移動には、2 つの手順が必要な場合は、1 つのステップとして実行するスクリプト化できる) が必要です。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-120">If you are using a version earlier than Skype for Business Server 2015 CU8, the move requires two steps (which can be scripted to be done together as a single step, if desired):</span></span>
    - <span data-ttu-id="fb9b3-121">[ビジネス上のサーバー (設置型) ビジネス オンラインの Skype に Skype からユーザーを移動](move-users-from-on-premises-to-skype-for-business-online.md)します。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-121">[Move the user from Skype for Business Server (on premises) to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span></span>
    - <span data-ttu-id="fb9b3-122">取引をオンラインでは、TeamsUpgradePolicy モードでのユーザーを割り当てるために、Skype でユーザーのホームとは、TeamsOnly を = します。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-122">Once the user is homed in Skype for Business Online, assign the user TeamsUpgradePolicy with mode= TeamsOnly.</span></span> <span data-ttu-id="fb9b3-123">TeamsOnly モードを許可するには、ビジネス オンラインの PowerShell ウィンドウで、Skype から次のコマンドレットを実行します。`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span><span class="sxs-lookup"><span data-stu-id="fb9b3-123">To grant TeamsOnly mode, run the following cmdlet from a Skype for Business Online PowerShell window: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span></span>
- <span data-ttu-id="fb9b3-124">Skype ビジネス サーバー 2015 CU8 またはそれ以降の管理ツールを使っている場合、上記のメソッドを使用することができますか、次のように 1 つの手順では、この移動を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-124">If you have admin tools from Skype for Business Server 2015 CU8 or later, you can use the method above, or you can do this move in one step as described below.</span></span> <span data-ttu-id="fb9b3-125">さらに、する、必要に応じてチームのみに移動する前にクライアントをビジネスの Skype 内で通知を提供するとともに必要に応じてビジネス クライアント用の Skype でサイレント モードでダウンロードしたチームのクライアントがあります。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-125">In addition, you can optionally provide a notification within the Skype for Business client prior to moving them to Teams Only as well as optionally have the Teams client silently downloaded by the Skype for Business client.</span></span>

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="fb9b3-126">設置型のビジネス用の Skype から直接チームのみにユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-126">Move a user directly from Skype for Business on premises to Teams Only</span></span>

<span data-ttu-id="fb9b3-127">CU8 を持つサーバー 2015 のビジネス用の Skype と Skype のビジネス サーバー 2019、設置管理ツールを使用すると、ビジネス Se の PowerShell で移動 CsUser コマンドレット、または、Skype のいずれかを使用して 1 つの手順でモードのチームだけに、設置型からユーザーを移動するにはした rver コントロール パネルで、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-127">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to move users from on premises to Teams Only mode in a single step using either the Move-CsUser cmdlet in PowerShell or the Skype for Business Server Control Panel, as described below.</span></span>

### <a name="move-to-teams-using-move-csuser"></a><span data-ttu-id="fb9b3-128">Csuser からの移動を使用するチームに移動します。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-128">Move to Teams using Move-CsUser</span></span>

<span data-ttu-id="fb9b3-129">Csuser からの移動を指定する場合は、オンプレミス Skype のビジネス管理シェルの PowerShell ウィンドウで実行できます。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-129">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="fb9b3-130">次の手順と必要なアクセス許可は、MoveToTeams スイッチを指定することもする必要があり、ユーザーも付与されているライセンス (ビジネス用の Skype の他のチームのことを確認する必要がありますが、ビジネス オンラインの Skype をユーザーの移動と同じオンライン)。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-130">The steps below and permissions required are the same as moving a user to Skype for Business Online, except that you must also specify the MoveToTeams switch and you must ensure that the user has also been granted a license for Teams (in addition to Skype for Business Online).</span></span>

<span data-ttu-id="fb9b3-131">[管理者の資格情報が必要な](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)の説明に従って、オンプレミス環境と、Office 365 テナントの両方に十分な特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-131">You must have sufficient privileges in both the on-premises environment and the Office 365 tenant, as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="fb9b3-132">両方の環境で権限のある単一のアカウントを使用することができますか、または設置型の資格情報を持つビジネス サーバー管理シェル ウィンドウに、オンプレミス Skype を起動し、使用できます、 `-Credential` 、Office 365 の資格情報を指定するパラメーター必要な Office 365 管理者の役割を持つアカウント。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-132">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="fb9b3-133">Csuser からの移動を使用するモードのチームだけにユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-133">To move a user to Teams Only mode using Move-CsUser:</span></span>

- <span data-ttu-id="fb9b3-134">使用して移動するユーザーを指定します`Identity`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-134">Specify the user to move using the `Identity` parameter.</span></span>
- <span data-ttu-id="fb9b3-135">指定ターゲット パラメーターを指定する値"sipfed.online.lync。<span>com"します。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-135">Specify the     -Target     parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="fb9b3-136">指定の`MoveToTeams`を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-136">Specify the `MoveToTeams` switch.</span></span>
- <span data-ttu-id="fb9b3-137">設置型および Office 365 の両方のための十分なアクセス許可を持つ 1 つのアカウントがないを使用して、 `-credential` Office 365 のための十分な権限を持つアカウントを指定するパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-137">If you do not have one account with sufficient permissions in both on premises and Office 365, use the `-credential` parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="fb9b3-138">」On.microsoft で Office 365 にアクセス許可を持つアカウントが終わっていない場合。<span>com」、指定する必要があります、`-HostedMigrationOverrideUrl`で説明されているが[管理者の資格情報を必要](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)と正しい値を持つパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-138">If the account with permissions in Office 365 does not end in “on.microsoft.<span>com”, you must specify the `-HostedMigrationOverrideUrl` parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="fb9b3-139">次のコマンドレットのシーケンスでは、TeamsOnly にユーザーを移動する使用することができ、Office 365 の資格情報は別のアカウントであり、取得の資格情報のプロンプトへの入力として提供されたと仮定しています。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-139">The following cmdlet sequence can be used to move a user to TeamsOnly, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

    ```
    $cred=Get-Credential
    $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
    ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a><span data-ttu-id="fb9b3-140">ビジネス サーバーのコントロール パネルの Skype を使用するチームに移動します。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-140">Move to Teams using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="fb9b3-141">ビジネス サーバー管理のため、Skype を開くパネルのアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-141">Open the Skype for Business Server Control Panel app.</span></span>
2.  <span data-ttu-id="fb9b3-142">左側のナビゲーションでは、**ユーザー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-142">In the left navigation, choose **Users**.</span></span>
3.  <span data-ttu-id="fb9b3-143">チームに移動したいユーザーを検索するには、**検索**を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-143">Use **Find** to locate the user(s) you would like to move to Teams.</span></span>
4.  <span data-ttu-id="fb9b3-144">、ユーザーを選択して、**アクション**ドロップダウン リストの上からクリックして**チームを選択したユーザーを移動**します。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-144">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Teams**.</span></span>
5.  <span data-ttu-id="fb9b3-145">ウィザードで、[**次へ**] クリックします。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-145">In the wizard, click **Next**.</span></span>
6.  <span data-ttu-id="fb9b3-146">メッセージが表示されたらにサインイン、Office 365 で終了するアカウントを使用しています。 onmicrosoft.com 十分なアクセス許可とします。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-146">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7.  <span data-ttu-id="fb9b3-147">ユーザーを移動するのには**次へ**、し、[**次へ**1 つのより多くの時間をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-147">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="fb9b3-148">ウィザードではなく、メインのコントロール パネルの [アプリケーションの上部に成功または失敗に関連するステータス メッセージが提供されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-148">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a><span data-ttu-id="fb9b3-149">チームへの移行は今後のビジネス、オンプレミスのユーザーは、Skype に通知します。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-149">Notify your Skype for Business on-premises users of the upcoming move to Teams</span></span>

<span data-ttu-id="fb9b3-150">CU8 を持つサーバー 2015 のビジネス用の Skype と Skype のビジネス サーバー 2019、設置管理ツールを使用すると、設置の Skype の予定を移動して、チームのビジネス ユーザー向けに通知します。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-150">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to notify on-premises Skype for Business users of their upcoming move to Teams.</span></span> <span data-ttu-id="fb9b3-151">これらの通知を有効にすると、ユーザーは次のように (Win32、Mac、web、およびモバイル) のビジネス クライアント用の Skype に通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-151">When you enable these notifications, users will see a notification in their Skype for Business client (Win32, Mac, web, and mobile) as shown below.</span></span> <span data-ttu-id="fb9b3-152">インストールされている場合にチームのクライアントを起動する場合は、ユーザーが**それを実行してください**] をクリックしてそれ以外の場合、ユーザーは、自分のブラウザーのチームの web バージョンに移動します。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-152">If users click the **Try it** button, the Teams client will be launched if it is installed; otherwise, users will be navigated to the web version of Teams in their browser.</span></span> <span data-ttu-id="fb9b3-153">既定では、通知を有効にすると、Win32 の Skype ビジネス クライアントのサイレント モードでクライアントをダウンロード チーム チームのみのモードは、ユーザーを移動する前に利用可能なリッチ クライアントになるようただし、この現象も無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-153">By default, when notifications are enabled, Win32 Skype for Business clients silently download the Teams client so that the rich client is available prior to moving the user to Teams Only mode; however, you can also disable this behavior.</span></span>  <span data-ttu-id="fb9b3-154">設置型バージョンを使用して通知が構成されて`TeamsUpgradePolicy`、および Win32 クライアントのサイレント ダウンロードは、設置型を使用して制御`TeamsUpgradeConfiguration`コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-154">Notifications are configured using the on-premises version of `TeamsUpgradePolicy`, and silent download for Win32 clients is controlled via the on-premises `TeamsUpgradeConfiguration` cmdlet.</span></span>

![チームへの今後の移行の通知](../media/teams-upgrade-notification.png)

<span data-ttu-id="fb9b3-156">NotifySfBUsers と TeamsUpgradePolicy の新しいインスタンスを作成することではすぐにアップグレードするチームに、オンプレミスのユーザーに通知、true です。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-156">To notify on-premises users that they will soon be upgraded to Teams, create a new instance of TeamsUpgradePolicy with NotifySfBUsers=true.</span></span> <span data-ttu-id="fb9b3-157">ポリシーをユーザーに直接割り当てるか、サイト、プール、またはグローバル レベルでポリシーを設定することにより、通知を使用するユーザーにそのポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-157">Then assign that policy to the users who you want to notify, either by assigning the policy directly to the user or by setting the policy at the site, pool, or global level.</span></span> <span data-ttu-id="fb9b3-158">次のコマンドレットでは、作成し、ユーザー レベルのポリシーを付与します。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-158">The following cmdlets create and grant a user-level policy:</span></span>

```
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true 
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

<span data-ttu-id="fb9b3-159">ビジネス Win32 クライアントの Skype を使用してチームの自動ダウンロードは、DownloadTeams パラメーターを使用して、オンプレミスの TeamsUpgradeConfiguration コマンドレットを使用して制御されます。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-159">Automatic download of Teams via the Skype for Business Win32 client is controlled via the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="fb9b3-160">このグローバル構成、サイト、およびプールのレベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-160">You create this configuration on a global, site, and pool level.</span></span> <span data-ttu-id="fb9b3-161">たとえば、次のコマンドでは、サイト Redmond1 の構成が作成されます。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-161">For example, the following command creates the configuration for the site Redmond1:</span></span>

`New-CsTeamsUpgradeConfiguration -Identity “site:redmond1”`

<span data-ttu-id="fb9b3-162">既定では、DownloadTeams の値は、True です。ただしは*のみ*場合は優先順位を付ける NotifySfbUser 特定のユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="fb9b3-162">By default, the value of DownloadTeams is True; however, it is *only* honored if NotifySfbUser = True for a given user.</span></span>


## <a name="see-also"></a><span data-ttu-id="fb9b3-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb9b3-163">See also</span></span>

[<span data-ttu-id="fb9b3-164">Csuser からの移動</span><span class="sxs-lookup"><span data-stu-id="fb9b3-164">Move-CsUser</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)

[<span data-ttu-id="fb9b3-165">許可 CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="fb9b3-165">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy
)

[<span data-ttu-id="fb9b3-166">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="fb9b3-166">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="fb9b3-167">Skype for Business と共存する</span><span class="sxs-lookup"><span data-stu-id="fb9b3-167">Coexistence with Skype for Business</span></span>](/microsoftteams/coexistence-chat-calls-presence)
