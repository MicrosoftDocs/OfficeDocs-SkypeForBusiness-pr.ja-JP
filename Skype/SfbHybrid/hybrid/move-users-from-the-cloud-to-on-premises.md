---
title: クラウドからオンプレミスにユーザーを移動する
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
description: Skype for Business Online からオンプレミスにユーザーを移動する方法について学習します。
ms.openlocfilehash: fdc8a8fb4e8e6cb1e2426b067aefbfa25e808171
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110613"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a><span data-ttu-id="dd783-103">クラウドからオンプレミスにユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="dd783-103">Move users from the cloud to on-premises</span></span> 

<span data-ttu-id="dd783-104">必要に応じて、以前にオンプレミスからクラウドに移行されたユーザー (Skype for Business Online または Teams Only を使用する場合) をオンプレミスに移動できます。</span><span class="sxs-lookup"><span data-stu-id="dd783-104">If needed, you can move a user who was previously migrated from on-premises to the cloud (whether using Skype for Business Online or Teams Only) back to on-premises.</span></span> <span data-ttu-id="dd783-105">Skype for Business Online または TeamsOnly モードから Skype for Business Server のオンプレミス展開に戻す場合は、Move-CsUser コマンドレットまたは Skype for Business Server コントロール パネルのいずれかを使用します。どちらもオンプレミス ツールです。</span><span class="sxs-lookup"><span data-stu-id="dd783-105">To move users from either Skype for Business Online or TeamsOnly mode back to an on-premises deployment of Skype for Business Server, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> <span data-ttu-id="dd783-106">ユーザーをオンプレミス展開に戻す場合は、ユーザーを移動するプールを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd783-106">When you move a user back to an on-premises deployment, you must decide which pool to move the user to.</span></span>

> [!Important]
> <span data-ttu-id="dd783-107">ユーザーが以前 TeamsOnly モードで、CU8 を使用して Skype for Business Server 2015 より前のバージョンを使用している場合は、そのユーザーの TeamsUpgradePolicy の TeamsOnly モードの割り当てを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd783-107">If the user was previously in TeamsOnly mode, and you are using an earlier version than Skype for Business Server 2015 with CU8, then you must also remove the TeamsOnly mode assignment of TeamsUpgradePolicy for that user.</span></span> <span data-ttu-id="dd783-108">オンプレミスのユーザーは mode= TeamsOnly を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd783-108">On-premises users must not have mode= TeamsOnly.</span></span>  <span data-ttu-id="dd783-109">以降のバージョンの Skype for Business Server では、この割り当てが自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="dd783-109">Subsequent versions of Skype for Business Server automatically remove this assignment.</span></span> <span data-ttu-id="dd783-110">詳細については [、「Grant-CsTeamsUpgradePolicy」を参照してください](/powershell/module/skype/grant-csteamsupgradepolicy)。</span><span class="sxs-lookup"><span data-stu-id="dd783-110">For more details, see [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dd783-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="dd783-111">Prerequisites</span></span>

- <span data-ttu-id="dd783-112">「Configure Azure AD Connect」の説明に従って、組織は AD Azure AD Connect を適切に構成し、ユーザーに関連 [するすべての属性を同期している必要があります](configure-azure-ad-connect.md)。</span><span class="sxs-lookup"><span data-stu-id="dd783-112">The organization must have Azure AD Connect properly configured and be syncing all relevant attributes for the user, as described in [Configure Azure AD Connect](configure-azure-ad-connect.md).</span></span>
- <span data-ttu-id="dd783-113">オンラインからオンプレミスに移動するユーザーは、オンプレミスの Active Directory に既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd783-113">The user being moved from online back to on-premises must already exist in the on-premises Active Directory.</span></span>
- <span data-ttu-id="dd783-114">「Skype for Business ハイブリッドの構成」の説明に従って [、Skype for Business ハイブリッドを構成する必要があります](configure-federation-with-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="dd783-114">Skype for Business hybrid must be configured, as described in [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).</span></span>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="dd783-115">ユーザーをオンプレミスに戻す</span><span class="sxs-lookup"><span data-stu-id="dd783-115">Moving users back to on-premises</span></span>

<span data-ttu-id="dd783-116">ユーザーをクラウドからオンプレミスに戻したら、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="dd783-116">Once you move a user from the cloud back to on-premises:</span></span>

- <span data-ttu-id="dd783-117">ユーザーは、その機能のために Skype for Business Server の展開を操作します。</span><span class="sxs-lookup"><span data-stu-id="dd783-117">The user interacts with your Skype for Business Server deployment for its functionality.</span></span> 
- <span data-ttu-id="dd783-118">Skype for Business Online または Teams に存在していた連絡先は、Skype for Business Server に移行されます。</span><span class="sxs-lookup"><span data-stu-id="dd783-118">Any contacts that existed in either Skype for Business Online or Teams are migrated  to Skype for Business Server.</span></span> <span data-ttu-id="dd783-119">2 つの連絡先セットが結合され、オンプレミスに移行されます。</span><span class="sxs-lookup"><span data-stu-id="dd783-119">The two sets of contacts are merged and then migrated back to on-premises.</span></span>  <span data-ttu-id="dd783-120">さらに、Teams に既存の連絡先は Teams に残ります。</span><span class="sxs-lookup"><span data-stu-id="dd783-120">In addition, contacts that are pre-existing in Teams remain in Teams.</span></span>
- <span data-ttu-id="dd783-121">ユーザーが Teams も使用している場合、Skype for Business ユーザーと相互運用する機能も、フェデレーション組織のユーザーと通信する機能もありません。</span><span class="sxs-lookup"><span data-stu-id="dd783-121">If the user also uses Teams, they will not have the ability to interoperate with Skype for Business users, nor will they be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="dd783-122">Skype for Business Online の会議 *は、* オンプレミスに自動的に移行されません。</span><span class="sxs-lookup"><span data-stu-id="dd783-122">Meetings in Skype for Business Online are *not* automatically migrated back to on-premises.</span></span> <span data-ttu-id="dd783-123">ユーザーは、会議のスケジュールを変更するか、必要に応じて会議移行ツール [を使用する必要があります](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)。</span><span class="sxs-lookup"><span data-stu-id="dd783-123">Users should either reschedule their meetings or, if desired, use the [Meeting Migration Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).</span></span>

### <a name="move-users-with-move-csuser"></a><span data-ttu-id="dd783-124">ユーザーをユーザーに移動Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="dd783-124">Move users with Move-CsUser</span></span>

<span data-ttu-id="dd783-125">Move-CsUserは、オンプレミスの Skype for Business Management Shell PowerShell ウィンドウから利用できます。</span><span class="sxs-lookup"><span data-stu-id="dd783-125">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="dd783-126">「必須の管理資格情報」の説明に従って、オンプレミス環境とクラウド サービス組織 (Microsoft 365 または Office 365) の両方で十分な特権を持っている [必要](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)があります。</span><span class="sxs-lookup"><span data-stu-id="dd783-126">You must have sufficient privileges in both the on-premises environment as well as the cloud service organization (Microsoft 365 or Office 365), as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="dd783-127">両方の環境で特権を持つ 1 つのアカウントを使用するか、オンプレミスの資格情報を使用してオンプレミスの Skype for Business Server 管理シェル ウィンドウを起動し、パラメーターを使用して、必要な管理役割を持つ `-Credential` Microsoft 365 または Office 365 アカウントの資格情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="dd783-127">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="dd783-128">Move-CsUser を使用してユーザーをオンプレミスに移動するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dd783-128">To move a user to on-premises using Move-CsUser:</span></span>

- <span data-ttu-id="dd783-129">Identity パラメーターを使用して移動するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="dd783-129">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="dd783-130">ユーザーをホストする必要なオンプレミス プールの完全修飾ドメイン名を指定して、-Target パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="dd783-130">Specify the -Target parameter with the fully qualified domain name of the desired on-premises pool that will host the user.</span></span>
- <span data-ttu-id="dd783-131">オンプレミスとクラウド サービス (Microsoft 365 または Office 365) の両方に十分なアクセス許可を持つアカウントが 1 つない場合は、-credential パラメーターを使用して、Microsoft 365 または Office 365 で十分なアクセス許可を持つアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="dd783-131">If you do not have one account with sufficient permissions in both on-premises and the cloud service (Microsoft 365 or Office 365), use the -credential parameter to supply an account with sufficient permissions in Microsoft 365 or Office 365.</span></span>
- <span data-ttu-id="dd783-132">Microsoft 365 または Office 365 のアクセス許可を持つアカウントが "on.microsoft.com" で終了しない場合は、-HostedMigrationOverrideUrl パラメーターを指定し、「必須の[](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)管理資格情報」で説明したように正しい値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd783-132">If the account with permissions in Microsoft 365 or Office 365 does not end in “on.microsoft.com”, you must specify the -HostedMigrationOverrideUrl parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="dd783-133">次のコマンドレット シーケンスを使用して、ユーザーを Skype for Business Server に移動し、Microsoft 365 または Office 365 資格情報が別のアカウントであり、Get-Credential プロンプトの入力として提供されたと見なします。</span><span class="sxs-lookup"><span data-stu-id="dd783-133">The following cmdlet sequence can be used to move a user to Skype for Business Server, and assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a><span data-ttu-id="dd783-134">Skype for Business Server コントロール パネルを使用してユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="dd783-134">Move users with the Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="dd783-135">Skype for Business Server コントロール パネル アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="dd783-135">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="dd783-136">左側のナビゲーションで、[ユーザー] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="dd783-136">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="dd783-137">[ **検索]** を使用して、オンプレミスに戻すユーザーを探します。</span><span class="sxs-lookup"><span data-stu-id="dd783-137">Use **Find** to locate the user(s) you would like to move back to on-premises.</span></span>
4. <span data-ttu-id="dd783-138">ユーザーを選択し、リストの上にある[アクション] ドロップダウンから [選択したユーザーをオンプレミスに移動する]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dd783-138">Select the user(s), and then from the **Action** dropdown above the list, choose **Move selected users to on-premises**.</span></span>
5. <span data-ttu-id="dd783-139">ウィザードで、ユーザーをホストするユーザー プールを選択し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="dd783-139">In the wizard, select the user pool that will host the user and click **Next**.</span></span>
6. <span data-ttu-id="dd783-140">メッセージが表示されたら、Microsoft 365 または Office 365 に .onmicrosoft.com で終了し、十分なアクセス許可を持つアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="dd783-140">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="dd783-141">[ **次へ]** をクリックし、[ **次** へ] をクリックしてもう 1 回ユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="dd783-141">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="dd783-142">成功または失敗に関する状態メッセージは、ウィザードではなく、メインのコントロール パネル アプリの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd783-142">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

### <a name="removing-teamsonly-mode"></a><span data-ttu-id="dd783-143">TeamsOnly モードの削除</span><span class="sxs-lookup"><span data-stu-id="dd783-143">Removing TeamsOnly mode</span></span>

<span data-ttu-id="dd783-144">CU8 で Skype for Business 2015 より前のバージョンを使用している場合、ユーザーが TeamsOnly モードでオンプレミスに戻される場合は、ユーザーをオンプレミスに移動する前に UpgradeToTeams インスタンスを削除する必要があります。 `TeamsUpgradePolicy`</span><span class="sxs-lookup"><span data-stu-id="dd783-144">If you are using a version earlier than Skype for Business 2015 with CU8 and the user is being moved back to on-premises in TeamsOnly mode, you must remove the UpgradeToTeams instance of `TeamsUpgradePolicy` before you move the user on-premises.</span></span> <span data-ttu-id="dd783-145">別のモードでポリシーを明示的に付与するか、そのユーザーがグローバル ポリシーを使用する既存のポリシー割り当てを削除します (テナントのグローバル ポリシーが UpgradeToTeams ではない限り)。</span><span class="sxs-lookup"><span data-stu-id="dd783-145">You can either explicitly grant a policy with a different mode or simply remove the existing policy assignment for that user to use the global policy (as long as your tenant’s global policy is not UpgradeToTeams).</span></span>

<span data-ttu-id="dd783-146">TeamsUpgradePolicy のユーザーの割り当てを削除するには、Skype for Business Online PowerShell ウィンドウから次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="dd783-146">To remove the user’s assignment of TeamsUpgradePolicy, run the following cmdlet from a Skype for Business Online PowerShell window:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

<span data-ttu-id="dd783-147">または、mode=TeamsOnly を持つ TeamsUpgradePolicy の別のインスタンスを割り当てるには、コマンドレットで PolicyName パラメーターの値として目的のインスタンスの名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="dd783-147">Alternatively, to assign another instance of TeamsUpgradePolicy that does not have mode=TeamsOnly, you can specify the name of the desired instance as the value of PolicyName parameter in the cmdlet.</span></span> <span data-ttu-id="dd783-148">TeamsUpgradePolicy の使用可能なインスタンスの一覧を表示するには、Get-CsTeamsUpgradePolicy を実行します。</span><span class="sxs-lookup"><span data-stu-id="dd783-148">To see a list of available instances of TeamsUpgradePolicy, run Get-CsTeamsUpgradePolicy.</span></span>


## <a name="see-also"></a><span data-ttu-id="dd783-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd783-149">See also</span></span>

[<span data-ttu-id="dd783-150">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="dd783-150">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)