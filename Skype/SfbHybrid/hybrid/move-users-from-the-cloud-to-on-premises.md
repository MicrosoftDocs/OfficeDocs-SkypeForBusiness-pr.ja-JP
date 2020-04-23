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
description: Skype for Business Online からオンプレミスにユーザーを移動する方法について説明します。
ms.openlocfilehash: 0add74a2480f4caed493e6e448427aa2462db714
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779673"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a><span data-ttu-id="403ed-103">クラウドからオンプレミスにユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="403ed-103">Move users from the cloud to on-premises</span></span> 

<span data-ttu-id="403ed-104">必要に応じて、オンプレミスからクラウドに移行されたユーザー (Skype for Business Online または Teams のみを使用しているかどうか) をオンプレミスに移行できます。</span><span class="sxs-lookup"><span data-stu-id="403ed-104">If needed, you can move a user who was previously migrated from on-premises to the cloud (whether using Skype for Business Online or Teams Only) back to on-premises.</span></span> <span data-ttu-id="403ed-105">Skype for business Online または TeamsOnly モードから、Skype for business Server のオンプレミス展開にユーザーを戻すには、両方のユーザーコマンドレットまたは Skype for Business Server コントロールパネルを使用します。これらは両方ともオンプレミスのツールです。</span><span class="sxs-lookup"><span data-stu-id="403ed-105">To move users from either Skype for Business Online or TeamsOnly mode back to an on-premises deployment of Skype for Business Server, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> <span data-ttu-id="403ed-106">ユーザーをオンプレミス展開に戻した場合は、移動先のプールを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="403ed-106">When you move a user back to an on-premises deployment, you must decide which pool to move the user to.</span></span>

> [!Important]
> <span data-ttu-id="403ed-107">以前は TeamsOnly モードでユーザーが以前のバージョンを使用していて、CU8 で Skype for business Server 2015 より前のバージョンを使用している場合は、そのユーザーの TeamsUpgradePolicy の TeamsOnly モードの割り当ても削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="403ed-107">If the user was previously in TeamsOnly mode, and you are using an earlier version than Skype for Business Server 2015 with CU8, then you must also remove the TeamsOnly mode assignment of TeamsUpgradePolicy for that user.</span></span> <span data-ttu-id="403ed-108">オンプレミスのユーザーは、mode = TeamsOnly を持たない必要があります。</span><span class="sxs-lookup"><span data-stu-id="403ed-108">On-premises users must not have mode= TeamsOnly.</span></span>  <span data-ttu-id="403ed-109">今後のバージョンの Skype for Business Server では、この割り当てが自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="403ed-109">Subsequent versions of Skype for Business Server automatically remove this assignment.</span></span> <span data-ttu-id="403ed-110">詳細については、「 [CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="403ed-110">For more details, see [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="403ed-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="403ed-111">Prerequisites</span></span>

- <span data-ttu-id="403ed-112">「 [AZURE Ad connect を構成](configure-azure-ad-connect.md)する」の説明に従って、組織では、Azure ad connect が適切に構成されており、ユーザーの関連するすべての属性を同期している必要があります。</span><span class="sxs-lookup"><span data-stu-id="403ed-112">The organization must have Azure AD Connect properly configured and be syncing all relevant attributes for the user, as described in [Configure Azure AD Connect](configure-azure-ad-connect.md).</span></span>
- <span data-ttu-id="403ed-113">オンラインからオンプレミスに移行するユーザーは、オンプレミスの Active Directory に既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="403ed-113">The user being moved from online back to on-premises must already exist in the on-premises Active Directory.</span></span>
- <span data-ttu-id="403ed-114">「 [Configure skype For business hybrid](configure-federation-with-skype-for-business-online.md)」で説明されているように、Skype for business ハイブリッドを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="403ed-114">Skype for Business hybrid must be configured, as described in [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).</span></span>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="403ed-115">オンプレミスへのユーザーの移行</span><span class="sxs-lookup"><span data-stu-id="403ed-115">Moving users back to on-premises</span></span>

<span data-ttu-id="403ed-116">クラウドからオンプレミスにユーザーを戻すと、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="403ed-116">Once you move a user from the cloud back to on-premises:</span></span>

- <span data-ttu-id="403ed-117">ユーザーは、その機能を利用するために Skype for Business Server の展開と対話します。</span><span class="sxs-lookup"><span data-stu-id="403ed-117">The user interacts with your Skype for Business Server deployment for its functionality.</span></span> 
- <span data-ttu-id="403ed-118">Skype for business Online または Teams のいずれかに存在していた連絡先は、Skype for Business Server に移行されます。</span><span class="sxs-lookup"><span data-stu-id="403ed-118">Any contacts that existed in either Skype for Business Online or Teams are migrated  to Skype for Business Server.</span></span> <span data-ttu-id="403ed-119">2つの連絡先セットが統合され、オンプレミスに移行されます。</span><span class="sxs-lookup"><span data-stu-id="403ed-119">The two sets of contacts are merged and then migrated back to on-premises.</span></span>  <span data-ttu-id="403ed-120">また、Teams の既存の連絡先は Teams に残ります。</span><span class="sxs-lookup"><span data-stu-id="403ed-120">In addition, contacts that are pre-existing in Teams remain in Teams.</span></span>
- <span data-ttu-id="403ed-121">ユーザーが Teams も使用している場合、Skype for Business ユーザーとの相互運用を行うことはできません。また、フェデレーション組織でユーザーと通信することもできません。</span><span class="sxs-lookup"><span data-stu-id="403ed-121">If the user also uses Teams, they will not have the ability to interoperate with Skype for Business users, nor will they be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="403ed-122">Skype for Business Online の会議は、オンプレミスに自動的に移行される*ことはありません*。</span><span class="sxs-lookup"><span data-stu-id="403ed-122">Meetings in Skype for Business Online are *not* automatically migrated back to on-premises.</span></span> <span data-ttu-id="403ed-123">ユーザーは会議を再スケジュールするか、必要に応じて[会議移行ツール](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="403ed-123">Users should either reschedule their meetings or, if desired, use the [Meeting Migration Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).</span></span>

### <a name="move-users-with-move-csuser"></a><span data-ttu-id="403ed-124">Move-CsUser を使用してユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="403ed-124">Move users with Move-CsUser</span></span>

<span data-ttu-id="403ed-125">Move-CsUser は、オンプレミスの Skype for Business 管理シェル PowerShell ウィンドウから入手できます。</span><span class="sxs-lookup"><span data-stu-id="403ed-125">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="403ed-126">[必要な管理者の資格情報](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)で説明されているように、オンプレミス環境と Office 365 組織の両方に十分な特権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="403ed-126">You must have sufficient privileges in both the on-premises environment as well as the Office 365 organization, as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="403ed-127">両方の環境で権限を持つ単一のアカウントを使用するか、オンプレミスの資格情報を使用してオンプレミスの Skype for Business Server 管理シェルウィンドウを開始`-Credential`することができます。また、パラメーターを使用して、必要な office 365 管理者の役割を持つ office 365 アカウントの資格情報を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="403ed-127">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="403ed-128">Move-CsUser を使用してユーザーをオンプレミスに移動するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="403ed-128">To move a user to on-premises using Move-CsUser:</span></span>

- <span data-ttu-id="403ed-129">Identity パラメーターを使用して移動するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="403ed-129">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="403ed-130">-Target パラメーターに、ユーザーをホストする必要があるオンプレミスプールの完全修飾ドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="403ed-130">Specify the -Target parameter with the fully qualified domain name of the desired on-premises pool that will host the user.</span></span>
- <span data-ttu-id="403ed-131">オンプレミスと Office 365 の両方に十分な権限を持つアカウントが1つもない場合は、-credential パラメーターを使用して、Office 365 に十分な権限を持つアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="403ed-131">If you do not have one account with sufficient permissions in both on-premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="403ed-132">Office 365 のアクセス許可を持つアカウントが "on.microsoft.com" で終わっていない場合は、「[必要な管理者の資格情報](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)」に説明されているように、正しい値を指定して-HostedMigrationOverrideUrl パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="403ed-132">If the account with permissions in Office 365 does not end in “on.microsoft.com”, you must specify the -HostedMigrationOverrideUrl parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="403ed-133">次のコマンドレットシーケンスを使用して、ユーザーを Skype for Business Server に移動できます。また、Office 365 資格情報が別のアカウントであると仮定して、資格情報の取得を求めるプロンプトの入力として指定します。</span><span class="sxs-lookup"><span data-stu-id="403ed-133">The following cmdlet sequence can be used to move a user to Skype for Business Server, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a><span data-ttu-id="403ed-134">Skype for Business Server コントロールパネルを使用してユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="403ed-134">Move users with the Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="403ed-135">Skype for Business Server コントロールパネルアプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="403ed-135">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="403ed-136">左側のナビゲーションで、[**ユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="403ed-136">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="403ed-137">[**検索**] を使用して、オンプレミスに戻したいユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="403ed-137">Use **Find** to locate the user(s) you would like to move back to on-premises.</span></span>
4. <span data-ttu-id="403ed-138">ユーザーを選択し、リストの上にある**アクション**ドロップダウンから、[**選択したユーザーをオンプレミスに移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="403ed-138">Select the user(s), and then from the **Action** dropdown above the list, choose **Move selected users to on-premises**.</span></span>
5. <span data-ttu-id="403ed-139">ウィザードで、ユーザーをホストするユーザープールを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="403ed-139">In the wizard, select the user pool that will host the user and click **Next**.</span></span>
6. <span data-ttu-id="403ed-140">メッセージが表示された場合は、onmicrosoft.com で終了し、十分な権限があるアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="403ed-140">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="403ed-141">[**次へ**] をクリックし、[**次**へ] をもう一度クリックして、ユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="403ed-141">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="403ed-142">成功または失敗に関するステータスメッセージは、ウィザードではなく、メインコントロールパネルアプリの上部に表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="403ed-142">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

### <a name="removing-teamsonly-mode"></a><span data-ttu-id="403ed-143">TeamsOnly モードを削除する</span><span class="sxs-lookup"><span data-stu-id="403ed-143">Removing TeamsOnly mode</span></span>

<span data-ttu-id="403ed-144">CU8 を使用して Skype for Business 2015 より前のバージョンを使用していて、ユーザーを TeamsOnly モードでオンプレミスに戻した場合は、ユーザーをオンプレ`TeamsUpgradePolicy`ミスで移動する前に、の UpgradeToTeams インスタンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="403ed-144">If you are using a version earlier than Skype for Business 2015 with CU8 and the user is being moved back to on-premises in TeamsOnly mode, you must remove the UpgradeToTeams instance of `TeamsUpgradePolicy` before you move the user on-premises.</span></span> <span data-ttu-id="403ed-145">別のモードでポリシーを明示的に付与するか、グローバルポリシーを使用するようにそのユーザーの既存のポリシー割り当てを削除することができます (テナントのグローバルポリシーが Teams にアップグレードされていない場合)。</span><span class="sxs-lookup"><span data-stu-id="403ed-145">You can either explicitly grant a policy with a different mode or simply remove the existing policy assignment for that user to use the global policy (as long as your tenant’s global policy is not UpgradeToTeams).</span></span>

<span data-ttu-id="403ed-146">TeamsUpgradePolicy のユーザーの割り当てを削除するには、Skype for Business Online PowerShell ウィンドウから次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="403ed-146">To remove the user’s assignment of TeamsUpgradePolicy, run the following cmdlet from a Skype for Business Online PowerShell window:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

<span data-ttu-id="403ed-147">また、mode = TeamsOnly を持たない TeamsUpgradePolicy の別のインスタンスを割り当てるには、コマンドレットの PolicyName パラメーターの値として目的のインスタンスの名前を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="403ed-147">Alternatively, to assign another instance of TeamsUpgradePolicy that does not have mode=TeamsOnly, you can specify the name of the desired instance as the value of PolicyName parameter in the cmdlet.</span></span> <span data-ttu-id="403ed-148">TeamsUpgradePolicy の使用可能なインスタンスの一覧を表示するには、CsTeamsUpgradePolicy を実行します。</span><span class="sxs-lookup"><span data-stu-id="403ed-148">To see a list of available instances of TeamsUpgradePolicy, run Get-CsTeamsUpgradePolicy.</span></span>


## <a name="see-also"></a><span data-ttu-id="403ed-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="403ed-149">See also</span></span>

[<span data-ttu-id="403ed-150">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="403ed-150">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)
