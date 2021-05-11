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
ms.openlocfilehash: e4536b13b6a9c05757bfcbf629fcc8301f94ed86
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305981"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="87175-103">ユーザーをオンプレミスから Skype for Business Online に移動する</span><span class="sxs-lookup"><span data-stu-id="87175-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="87175-104">オンプレミスからオンラインにユーザーを移動した後Skype for Businessユーザーは、その機能のために Skype for Business Online を操作します。</span><span class="sxs-lookup"><span data-stu-id="87175-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="87175-105">オンプレミスに存在していた連絡先は Skype for Business Online で利用できます。また、ユーザーが将来開催する既存の会議は更新され、リンクは Skype for Business Online を指します。</span><span class="sxs-lookup"><span data-stu-id="87175-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="87175-106">ユーザーが電話会議を有効にしている場合、会議にはダイヤルイン座標も含まれます。</span><span class="sxs-lookup"><span data-stu-id="87175-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="87175-107">ユーザーをオンプレミス環境から Skype for Business Online に移動するには、Move-CsUser コマンドレットまたは Skype for Business Server コントロール パネルのいずれかを使用します。どちらもオンプレミス ツールです。</span><span class="sxs-lookup"><span data-stu-id="87175-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="87175-108">ユーザーを移動する前に、必ず前提条件を確認 [して](move-users-between-on-premises-and-cloud.md#prerequisites) 、ユーザーをクラウドに移動してください。</span><span class="sxs-lookup"><span data-stu-id="87175-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="87175-109">Skype for Business Online の今後の退職に備えて、Microsoft は近い将来、組織が Teams に移行する方法を簡素化し、Skype for Business Online に移行できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="87175-109">In preparation for the upcoming retirement of Skype for Business Online, Microsoft will be simplifying how organizations move to Teams in the near future and it will no longer be possible to move to Skype for Business Online.</span></span>  <span data-ttu-id="87175-110">これらの変更を利用できると、ユーザーをオンプレミスからクラウドに移動すると、ユーザーには TeamsOnly モードが自動的に割り当て、スイッチが実際に指定されたかどうかに関係なく、スイッチが指定された場合と同様に、ユーザーの会議が自動的に Teams 会議に変換されます。 `-MoveToTeams`</span><span class="sxs-lookup"><span data-stu-id="87175-110">Once these changes are made available, when moving a user from on-premises to the cloud, users will automatically be assigned TeamsOnly mode and their meetings from on-premises will be automtically converted to Teams meetings, just as if the `-MoveToTeams` switch had been specified, regardless of whether the switch is actually specified.</span></span> <span data-ttu-id="87175-111">この機能は、2021 年 7 月 31 日の実際の使用が解除される前にリリースされる予定です。</span><span class="sxs-lookup"><span data-stu-id="87175-111">We expect to release this functionality before the actual retirement of July 31, 2021.</span></span>   <span data-ttu-id="87175-112">現在、このスイッチを指定しない場合、ユーザーは Skype for Business Server オンプレミスのホームから Skype for Business Online に移行し、モードは変更されず、この記事に記載されている機能です。</span><span class="sxs-lookup"><span data-stu-id="87175-112">Currently if this switch is not specified, users transition from being homed in Skype for Business Server on-premises to Skype for Business Online, and their mode remains unchanged, which is the functionality documented in this article.</span></span>

 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="87175-113">ユーザーをユーザーに移動Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="87175-113">Move users with Move-CsUser</span></span> 

<span data-ttu-id="87175-114">Move-CsUser管理シェル PowerShell ウィンドウからSkype for Business使用できます。</span><span class="sxs-lookup"><span data-stu-id="87175-114">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="87175-115">「必須の管理資格情報」の説明に従って、オンプレミス環境と組織の両方で十分Microsoft 365[必要があります](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。</span><span class="sxs-lookup"><span data-stu-id="87175-115">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="87175-116">両方の環境で特権を持つ 1 つのアカウントを使用するか、オンプレミスの資格情報を使用してオンプレミスの Skype for Business Server 管理シェル ウィンドウを起動し、パラメーターを使用して、必要な管理役割を持つ Microsoft 365 アカウントの資格情報を指定できます。 `-Credential`</span><span class="sxs-lookup"><span data-stu-id="87175-116">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="87175-117">Move-CsUser を使用してユーザーをオンラインに移動するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="87175-117">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="87175-118">Identity パラメーターを使用して移動するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="87175-118">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="87175-119">値 "sipfed.online.lync" で -Target パラメーターを指定します。 <span>com」</span><span class="sxs-lookup"><span data-stu-id="87175-119">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="87175-120">オンプレミスと Microsoft 365 の両方で十分なアクセス許可を持つアカウントが 1 つない場合は、-credential パラメーターを使用して、Microsoft 365 で十分なアクセス許可を持つアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="87175-120">If you do not have one account with sufficient permissions in both on premises and Microsoft 365, use the -credential parameter to supply an account with sufficient permissions in Microsoft 365.</span></span>
- <span data-ttu-id="87175-121">アクセス許可が設定されているアカウントMicrosoft 365.onmicrosoft で終了しない場合。 <span>com"の場合は、-HostedMigrationOverrideUrl パラメーターを指定し、「必須の管理資格情報」の説明に従って正しい値[を指定する必要があります](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。</span><span class="sxs-lookup"><span data-stu-id="87175-121">If the account with permissions in Microsoft 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="87175-122">次のコマンドレット シーケンスを使用して、ユーザーを Online に移動Skype for Businessできます。</span><span class="sxs-lookup"><span data-stu-id="87175-122">The following cmdlet sequence can be used to move a user to Skype for Business Online.</span></span> <span data-ttu-id="87175-123">この資格情報は、Microsoft 365アカウントであり、ユーザープロンプトの入力として提供Get-Credentialします。</span><span class="sxs-lookup"><span data-stu-id="87175-123">It assumes the Microsoft 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="87175-124">管理者アカウントが MFA (多要素認証) が有効になっている場合は、-Credential パラメーターを指定しません。</span><span class="sxs-lookup"><span data-stu-id="87175-124">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="87175-125">管理者に資格情報の入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87175-125">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="87175-126">コントロール パネルでユーザー Skype for Business Server移動する</span><span class="sxs-lookup"><span data-stu-id="87175-126">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="87175-127">コントロール パネル アプリSkype for Business Server開きます。</span><span class="sxs-lookup"><span data-stu-id="87175-127">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="87175-128">左側のナビゲーションで、[ユーザー] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="87175-128">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="87175-129">[**検索]** を使用して、[オンライン] に移動するユーザーをSkype for Businessします。</span><span class="sxs-lookup"><span data-stu-id="87175-129">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="87175-130">ユーザーを選択し、リストの上にある [アクション] ドロップダウンから 、[選択したユーザーをオンラインに移動Skype for Business **します**。</span><span class="sxs-lookup"><span data-stu-id="87175-130">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="87175-131">ウィザードで、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87175-131">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="87175-132">メッセージが表示されたら、.Microsoft 365で終わり、十分なアクセス許可を持つアカウントを使用して、onmicrosoft.com にサインインします。</span><span class="sxs-lookup"><span data-stu-id="87175-132">If prompted, sign in to Microsoft 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="87175-133">[ **次へ]** をクリックし、[ **次** へ] をクリックしてもう 1 回ユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="87175-133">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="87175-134">成功または失敗に関する状態メッセージは、ウィザードではなく、メインのコントロール パネル アプリの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="87175-134">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="87175-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="87175-135">See also</span></span>

[<span data-ttu-id="87175-136">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="87175-136">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)
