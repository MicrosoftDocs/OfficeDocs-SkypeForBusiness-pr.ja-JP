---
title: 移動ユーザーが社内のクラウドに
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: Skype からの社内のビジネス オンラインへのユーザーを移動する方法について説明します。
ms.openlocfilehash: 7032e7f2968b7861a7fac199fd8ba949980fe770
ms.sourcegitcommit: f091c351bec56219a8c91b8c12b9c1f5c5983c95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2019
ms.locfileid: "29530944"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a><span data-ttu-id="75222-103">移動ユーザーが社内のクラウドに</span><span class="sxs-lookup"><span data-stu-id="75222-103">Move users from the cloud to on premises</span></span> 

<span data-ttu-id="75222-104">必要な場合、戻すことができます、ユーザーが以前に移行から社内のクラウドに移行する (Skype を使用して、ビジネスをオンラインまたはチームのみ) かどうかを施設内にします。</span><span class="sxs-lookup"><span data-stu-id="75222-104">If needed, you can move a user who was previously migrated from on premises to the cloud (whether using Skype for Business Online or Teams Only) back to on premises.</span></span> <span data-ttu-id="75222-105">移動するユーザーまたは TeamsOnly のビジネスのオンライン モードのいずれかの Skype から Skype の設置型展開ビジネス サーバーの設置型のツールは、両方とも、ビジネス サーバー コントロール パネルの移動 CsUser コマンドレット、または、Skype のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="75222-105">To move users from either Skype for Business Online or TeamsOnly mode back to an on-premises deployment of Skype for Business Server, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> <span data-ttu-id="75222-106">設置型の展開に戻る、ユーザーを移動するときにユーザーを移動するには、どのプールを決める必要があります。</span><span class="sxs-lookup"><span data-stu-id="75222-106">When you move a user back to an on-premises deployment, you must decide which pool to move the user to.</span></span>

> [!Important]
> <span data-ttu-id="75222-107">TeamsOnly モードで、ユーザーが以前にあったと CU8 のビジネス サーバー 2015 の Skype より以前のバージョンを使用している場合、そのユーザーの TeamsUpgradePolicy の TeamsOnly のモードの割り当ても削除しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="75222-107">If the user was previously in TeamsOnly mode, and you are using an earlier version than Skype for Business Server 2015 with CU8, then you must also remove the TeamsOnly mode assignment of TeamsUpgradePolicy for that user.</span></span> <span data-ttu-id="75222-108">オンプレミス ユーザーはモード = TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="75222-108">On-premises users must not have mode= TeamsOnly.</span></span>  <span data-ttu-id="75222-109">ビジネス サーバーの Skype の以降のバージョンは、この割り当てを自動的に削除します。</span><span class="sxs-lookup"><span data-stu-id="75222-109">Subsequent versions of Skype for Business Server automatically remove this assignment.</span></span> <span data-ttu-id="75222-110">詳細については、[補助金 CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75222-110">For more details, see [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="75222-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="75222-111">Prerequisites</span></span>

- <span data-ttu-id="75222-112">組織では、Azure AD 接続が正しく構成されている必要があり、[構成の Azure AD 接続](configure-azure-ad-connect.md)の説明に従って、ユーザーのすべての関連属性が同期します。</span><span class="sxs-lookup"><span data-stu-id="75222-112">The organization must have Azure AD Connect properly configured and be syncing all relevant attributes for the user, as described in [Configure Azure AD Connect](configure-azure-ad-connect.md).</span></span>
- <span data-ttu-id="75222-113">移動中のユーザーにオンライン バックアップからの社内は、オンプレミスの Active Directory に存在していなければなりません。</span><span class="sxs-lookup"><span data-stu-id="75222-113">The user being moved from online back to on premises must already exist in the on-premises Active Directory.</span></span>
- <span data-ttu-id="75222-114">[ビジネスのハイブリッド構成の Skype](configure-federation-with-skype-for-business-online.md)の説明に従って、Skype のビジネスのハイブリッドを構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="75222-114">Skype for Business hybrid must be configured, as described in [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).</span></span>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="75222-115">移動ユーザーが社内にバックアップします。</span><span class="sxs-lookup"><span data-stu-id="75222-115">Moving users back to on premises</span></span>

<span data-ttu-id="75222-116">移動すると、ユーザー、クラウドから戻る設置。</span><span class="sxs-lookup"><span data-stu-id="75222-116">Once you move a user from the cloud back to on-premises:</span></span>

- <span data-ttu-id="75222-117">ビジネス サーバー配置では、機能のため、Skype では、ユーザーが操作します。</span><span class="sxs-lookup"><span data-stu-id="75222-117">The user interacts with your Skype for Business Server deployment for its functionality.</span></span> 
- <span data-ttu-id="75222-118">ビジネス オンラインまたはチームのいずれかの Skype で存在していた取引先担当者は、ビジネスのサーバーを Skype に移行されます。</span><span class="sxs-lookup"><span data-stu-id="75222-118">Any contacts that existed in either Skype for Business Online or Teams are migrated  to Skype for Business Server.</span></span> <span data-ttu-id="75222-119">連絡先の 2 つのセットがマージされ、社内に移行されます。</span><span class="sxs-lookup"><span data-stu-id="75222-119">The two sets of contacts are merged and then migrated back to on premises.</span></span>  <span data-ttu-id="75222-120">さらに、チームで既存の連絡先は、チーム内に残ります。</span><span class="sxs-lookup"><span data-stu-id="75222-120">In addition, contacts that are pre-existing in Teams remain in Teams.</span></span>
- <span data-ttu-id="75222-121">ユーザーには、チームが使用しても、ビジネス ユーザーは、Skype で相互運用することはありませんもになる、フェデレーション組織のユーザーと通信すること。</span><span class="sxs-lookup"><span data-stu-id="75222-121">If the user also uses Teams, they will not have the ability to interoperate with Skype for Business users, nor will they be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="75222-122">ビジネス オンラインの Skype での会議では、自動的に移行*されません*に設置型の。</span><span class="sxs-lookup"><span data-stu-id="75222-122">Meetings in Skype for Business Online are *not* automatically migrated back to on premises.</span></span> <span data-ttu-id="75222-123">ユーザーがいずれかのスケジュールを変更、会議や、必要な場合は、[会議の移行ツール](https://support.office.com/en-us/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)を使用します。</span><span class="sxs-lookup"><span data-stu-id="75222-123">Users should either reschedule their meetings or, if desired, use the [Meeting Migration Tool](https://support.office.com/en-us/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).</span></span>

### <a name="move-users-with-move-csuser"></a><span data-ttu-id="75222-124">Csuser からの移動でユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="75222-124">Move users with Move-CsUser</span></span>

<span data-ttu-id="75222-125">Csuser からの移動を指定する場合は、オンプレミス Skype のビジネス管理シェルの PowerShell ウィンドウで実行できます。</span><span class="sxs-lookup"><span data-stu-id="75222-125">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="75222-126">[管理者の資格情報が必要な](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)の説明に従って、Office 365 テナントだけでなく、オンプレミス環境に十分な特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="75222-126">You must have sufficient privileges in both the on-premises environment as well as the Office 365 tenant, as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="75222-127">両方の環境で権限のある単一のアカウントを使用することができますか、または設置型の資格情報を持つビジネス サーバー管理シェル ウィンドウに、オンプレミス Skype を起動し、使用できます、 `-Credential` 、Office 365 の資格情報を指定するパラメーター必要な Office 365 管理者の役割を持つアカウント。</span><span class="sxs-lookup"><span data-stu-id="75222-127">You can either use a single account that has privileges in both environments, or you can start an on-premise Skype for Business Server Management Shell window with on-premise credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="75222-128">Csuser からの移動を使用して社内のユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="75222-128">To move a user to on premises using Move-CsUser:</span></span>

- <span data-ttu-id="75222-129">Id パラメーターを使用して移動するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="75222-129">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="75222-130">指定ターゲット パラメーターを指定するユーザーをホストする目的で設置型プールの完全修飾ドメイン名を持つ。</span><span class="sxs-lookup"><span data-stu-id="75222-130">Specify the -Target parameter with the fully qualified domain name of the desired on-premises pool that will host the user.</span></span>
- <span data-ttu-id="75222-131">設置型および Office 365 の両方のための十分なアクセス許可を持つ 1 つのアカウントがないを使用して、Office 365 のための十分な権限を持つアカウントを指定するには、資格情報パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="75222-131">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="75222-132">Office 365 にアクセス許可を持つアカウントは、"on.microsoft.com"で終わっていない場合、は、[ために必要な管理者資格情報](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)で説明するよう、適切な値を持つ、- HostedMigrationOverrideUrl パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75222-132">If the account with permissions in Office 365 does not end in “on.microsoft.com”, you must specify the -HostedMigrationOverrideUrl parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="75222-133">次のコマンドレットのシーケンスは、Skype をビジネスのサーバーのユーザーを移動するために使用して、Office 365 の資格情報は別のアカウントであり、取得の資格情報のプロンプトへの入力として提供されたと仮定しています。</span><span class="sxs-lookup"><span data-stu-id="75222-133">The following cmdlet sequence can be used to move a user to Skype for Business Server, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a><span data-ttu-id="75222-134">ビジネス サーバーのコントロール パネルの Skype でユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="75222-134">Move users with the Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="75222-135">ビジネス サーバー管理のため、Skype を開くパネルのアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="75222-135">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="75222-136">左側のナビゲーションでは、**ユーザー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="75222-136">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="75222-137">設置型に移動するには、ユーザーを検索するには、**検索**を使用します。</span><span class="sxs-lookup"><span data-stu-id="75222-137">Use **Find** to locate the user(s) you would like to move back to on premises.</span></span>
4. <span data-ttu-id="75222-138">、ユーザーを選択してから、**アクション**」ドロップ ダウン リストの上、クリックして**設置型を選択したユーザーを移動**します。</span><span class="sxs-lookup"><span data-stu-id="75222-138">Select the user(s), and then from the **Action** dropdown above the list, choose **Move selected users to on-premises**.</span></span>
5. <span data-ttu-id="75222-139">ウィザードでは、ユーザーをホストし、[**次へ**] をクリックするユーザーのプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="75222-139">In the wizard, select the user pool that will host the user and click **Next**.</span></span>
6. <span data-ttu-id="75222-140">メッセージが表示されたらにサインイン、Office 365 で終了するアカウントを使用しています。 onmicrosoft.com 十分なアクセス許可とします。</span><span class="sxs-lookup"><span data-stu-id="75222-140">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="75222-141">ユーザーを移動するのには**次へ**、し、[**次へ**1 つのより多くの時間をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75222-141">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="75222-142">ウィザードではなく、メインのコントロール パネルの [アプリケーションの上部に成功または失敗に関連するステータス メッセージが提供されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="75222-142">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

### <a name="removing-teamsonly-mode"></a><span data-ttu-id="75222-143">TeamsOnly モードを削除します。</span><span class="sxs-lookup"><span data-stu-id="75222-143">Removing TeamsOnly mode</span></span>

<span data-ttu-id="75222-144">CU8 を持つビジネス 2015年の Skype より前のバージョンを使用して、ユーザーに移動 TeamsOnly モードでの設置型の場合は、UpgradeToTeams のインスタンスを削除する必要があります`TeamsUpgradePolicy`の社内ユーザーを移動する前にします。</span><span class="sxs-lookup"><span data-stu-id="75222-144">If you are using a version earlier than Skype for Business 2015 with CU8 and the user is being moved back to on premises in TeamsOnly mode, you must remove the UpgradeToTeams instance of `TeamsUpgradePolicy` before you move the user on premises.</span></span> <span data-ttu-id="75222-145">別のモードのポリシーを明示的に許可するかである限り、テナントのグローバル ポリシーは、UpgradeToTeams ではありません) は、グローバル ポリシーを使用するには、そのユーザーの既存のポリシーの割り当てを削除するだけです。</span><span class="sxs-lookup"><span data-stu-id="75222-145">You can either explicitly grant a policy with a different mode or simply remove the existing policy assignment for that user to use the global policy (as long as your tenant’s global policy is not UpgradeToTeams).</span></span>

<span data-ttu-id="75222-146">TeamsUpgradePolicy のユーザーの割り当てを削除するのには、Skype のビジネス オンライン PowerShell ウィンドウから次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="75222-146">To remove the user’s assignment of TeamsUpgradePolicy, run the following cmdlet from a Skype for Business Online PowerShell window:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

<span data-ttu-id="75222-147">または、TeamsUpgradePolicy の別のインスタンスを割り当てることがないモード = TeamsOnly、コマンドレットのグループのパラメーターの値として適切なインスタンスの名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="75222-147">Alternatively, to assign another instance of TeamsUpgradePolicy that does not have mode=TeamsOnly, you can specify the name of the desired instance as the value of PolicyName parameter in the cmdlet.</span></span> <span data-ttu-id="75222-148">TeamsUpgradePolicy の使用可能なインスタンスの一覧を表示するには、Get CsTeamsUpgradePolicy を実行します。</span><span class="sxs-lookup"><span data-stu-id="75222-148">To see a list of available instances of TeamsUpgradePolicy, run Get-CsTeamsUpgradePolicy.</span></span>


## <a name="see-also"></a><span data-ttu-id="75222-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="75222-149">See also</span></span>

<span data-ttu-id="75222-150">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="75222-150">[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)</span></span>
