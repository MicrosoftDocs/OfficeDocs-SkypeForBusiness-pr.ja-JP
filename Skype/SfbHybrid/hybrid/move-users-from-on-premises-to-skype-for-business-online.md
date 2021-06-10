---
title: ユーザーをオンプレミスから Skype for Business Online に移動する
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
description: ユーザーをオンラインに移動するSkype for Businessします。
ms.openlocfilehash: 883db98a424c254e6792fd651594b02201a311f9
ms.sourcegitcommit: 2591c96d8613660220c5af71fc945e27b31175d7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52863198"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="72da7-103">ユーザーをオンプレミスから Skype for Business Online に移動する</span><span class="sxs-lookup"><span data-stu-id="72da7-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="72da7-104">オンプレミスからオンラインにユーザーを移動した後Skype for Businessユーザーは、その機能のために Skype for Business Online を操作します。</span><span class="sxs-lookup"><span data-stu-id="72da7-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="72da7-105">オンプレミスに存在していた連絡先は Skype for Business Online で利用できます。また、ユーザーが将来開催する既存の会議は更新され、リンクは Skype for Business Online を指します。</span><span class="sxs-lookup"><span data-stu-id="72da7-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="72da7-106">ユーザーが電話会議を有効にしている場合、会議にはダイヤルイン座標も含まれます。</span><span class="sxs-lookup"><span data-stu-id="72da7-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="72da7-107">ユーザーをオンプレミス環境から Skype for Business Online に移動するには、Move-CsUser コマンドレットまたは Skype for Business Server コントロール パネルのいずれかを使用します。どちらもオンプレミス ツールです。</span><span class="sxs-lookup"><span data-stu-id="72da7-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="72da7-108">ユーザーを移動する前に、必ず前提条件を確認 [して](move-users-between-on-premises-and-cloud.md#prerequisites) 、ユーザーをクラウドに移動してください。</span><span class="sxs-lookup"><span data-stu-id="72da7-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="72da7-109">Skype for Business Online の今後の退職に備えて、Microsoft は組織の移行方法を簡略化Teams。</span><span class="sxs-lookup"><span data-stu-id="72da7-109">In preparation for the upcoming retirement of Skype for Business Online, Microsoft has simplified how organizations move to Teams.</span></span> <span data-ttu-id="72da7-110">ユーザーをオンプレミスからクラウドに移行する場合、ユーザーには TeamsOnly モードが自動的に割り当てられると、スイッチが実際に指定されたかどうかに関係なく、スイッチが指定された場合と同様に、ユーザーの会議が自動的に Teams 会議に変換されます。 `-MoveToTeams`</span><span class="sxs-lookup"><span data-stu-id="72da7-110">When moving users from on-premises to the cloud, users are now automatically assigned TeamsOnly mode and their meetings from on-premises are automtically converted to Teams meetings, just as if the `-MoveToTeams` switch had been specified, regardless of whether the switch was actually specified.</span></span>  <span data-ttu-id="72da7-111">Skype for Business Online が終了する前に、ユーザーをオンプレミスから Skype for Business Online に移行する必要がある組織は、ユーザーが *TeamsOnly* に移動した後にユーザーのモードを更新することで、2 つの手順でこれを実現できます。</span><span class="sxs-lookup"><span data-stu-id="72da7-111">Prior to retirement of Skype for Business Online, organizations that require moving users from on-premises to Skype for Business Online can achieve this in two steps by updating the user's mode *after the user is moved to TeamsOnly*.</span></span> <span data-ttu-id="72da7-112">ただし、近い将来、クラウドに存在するユーザーに TeamsOnly 以外のモードを割り当てなくなりました。</span><span class="sxs-lookup"><span data-stu-id="72da7-112">However in the near future, it will no longer be possible to assign a mode other than TeamsOnly to users homed in the cloud.</span></span>  
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="72da7-113">ユーザーをユーザーに移動Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="72da7-113">Move users with Move-CsUser</span></span> 

<span data-ttu-id="72da7-114">Move-CsUser管理シェル PowerShell ウィンドウからSkype for Business使用できます。</span><span class="sxs-lookup"><span data-stu-id="72da7-114">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="72da7-115">「必須の管理資格情報」の説明に従って、オンプレミス環境と組織の両方で十分Microsoft 365[必要があります](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。</span><span class="sxs-lookup"><span data-stu-id="72da7-115">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="72da7-116">両方の環境で特権を持つ 1 つのアカウントを使用するか、オンプレミスの資格情報を使用してオンプレミスの Skype for Business Server 管理シェル ウィンドウを起動し、パラメーターを使用して、必要な管理役割を持つ Microsoft 365 アカウントの資格情報を指定できます。 `-Credential`</span><span class="sxs-lookup"><span data-stu-id="72da7-116">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="72da7-117">Move-CsUser を使用してユーザーをオンラインに移動するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="72da7-117">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="72da7-118">Identity パラメーターを使用して移動するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="72da7-118">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="72da7-119">値 "sipfed.online.lync" で -Target パラメーターを指定します。 <span>com」</span><span class="sxs-lookup"><span data-stu-id="72da7-119">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="72da7-120">オンプレミスと Microsoft 365 の両方で十分なアクセス許可を持つアカウントが 1 つない場合は、-credential パラメーターを使用して、Microsoft 365 で十分なアクセス許可を持つアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="72da7-120">If you do not have one account with sufficient permissions in both on premises and Microsoft 365, use the -credential parameter to supply an account with sufficient permissions in Microsoft 365.</span></span>
- <span data-ttu-id="72da7-121">アクセス許可が設定されているアカウントMicrosoft 365.onmicrosoft で終了しない場合。 <span>com"の場合は、-HostedMigrationOverrideUrl パラメーターを指定し、「必須の管理資格情報」の説明に従って正しい値[を指定する必要があります](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。</span><span class="sxs-lookup"><span data-stu-id="72da7-121">If the account with permissions in Microsoft 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="72da7-122">次のコマンドレット シーケンスを使用して、ユーザーを [オンライン] Skype for Businessに移動し、テナントの既定のモードをユーザーに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="72da7-122">The following cmdlet sequence can be used to move a user to Skype for Business Online and assigns the tenant default mode to the user.</span></span> <span data-ttu-id="72da7-123">この資格情報は、Microsoft 365アカウントであり、ユーザープロンプトの入力として提供Get-Credentialします。</span><span class="sxs-lookup"><span data-stu-id="72da7-123">It assumes the Microsoft 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
# From an on-premises Skype for Business Server or Lync Server 2013 management shell window, run:
 
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
 
# And then from a Teams PowerShell window, remove TeamsOnly mode by running: 
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName $null
```

<span data-ttu-id="72da7-124">管理者アカウントが MFA (多要素認証) が有効になっている場合は、-Credential パラメーターを指定しません。</span><span class="sxs-lookup"><span data-stu-id="72da7-124">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="72da7-125">管理者に資格情報の入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="72da7-125">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel-and-teams-admin-center"></a><span data-ttu-id="72da7-126">コントロール パネルと管理センター Skype for Business Serverを使用してユーザー Teams移動する</span><span class="sxs-lookup"><span data-stu-id="72da7-126">Move users with Skype for Business Server Control Panel and Teams Admin Center</span></span>

1. <span data-ttu-id="72da7-127">コントロール パネル アプリSkype for Business Server開きます。</span><span class="sxs-lookup"><span data-stu-id="72da7-127">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="72da7-128">左側のナビゲーションで、[ユーザー] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="72da7-128">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="72da7-129">[**検索]** を使用して、[オンライン] に移動するユーザーをSkype for Businessします。</span><span class="sxs-lookup"><span data-stu-id="72da7-129">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="72da7-130">ユーザーを選択し、リストの上にある [アクション] ドロップダウンから、[選択したユーザーを **Skype for Business Online** に移動する] または [選択したユーザーをユーザーに移動する] **Teams を選択します**。</span><span class="sxs-lookup"><span data-stu-id="72da7-130">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online** or **Move selected users to Teams**.</span></span> <span data-ttu-id="72da7-131">どちらのオプションでも、最初はユーザーを TeamsOnly モードに移動しますが、移動後に別のモードを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="72da7-131">Either option will initially move the user to TeamsOnly mode but after the move you can assign another mode.</span></span> 
5. <span data-ttu-id="72da7-132">ウィザードで、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="72da7-132">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="72da7-133">メッセージが表示されたら、.Microsoft 365で終わり、十分なアクセス許可を持つアカウントを使用して、onmicrosoft.com にサインインします。</span><span class="sxs-lookup"><span data-stu-id="72da7-133">If prompted, sign in to Microsoft 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="72da7-134">[ **次へ]** をクリックし、[ **次** へ] をクリックしてもう 1 回ユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="72da7-134">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="72da7-135">成功または失敗に関する状態メッセージは、ウィザードではなく、メインのコントロール パネル アプリの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="72da7-135">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>
9. <span data-ttu-id="72da7-136">[管理センター Teams開き、左側のナビゲーションで [ユーザー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72da7-136">Open the Teams Admin Center and select "Users" in the left hand navigation.</span></span> 
10. <span data-ttu-id="72da7-137">リストビューで目的のユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="72da7-137">Click on the desired user in the listview.</span></span> 
11. <span data-ttu-id="72da7-138">[アップグレード]**という** セクションの [**編集] をTeamsします**。</span><span class="sxs-lookup"><span data-stu-id="72da7-138">Click the **Edit** in the section that says **Teams upgrade**.</span></span>
12. <span data-ttu-id="72da7-139">右側のフライアウトで、目的の共存モードを選択し、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="72da7-139">In the right-hand flyout, select the desired coexistence mode and click **Apply**.</span></span>
 

## <a name="see-also"></a><span data-ttu-id="72da7-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="72da7-140">See also</span></span>

[<span data-ttu-id="72da7-141">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="72da7-141">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)
