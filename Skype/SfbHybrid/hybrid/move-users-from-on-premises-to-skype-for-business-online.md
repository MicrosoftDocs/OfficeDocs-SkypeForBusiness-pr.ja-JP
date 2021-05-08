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
ms.openlocfilehash: 8c028044fe8c4b808a419503091f9ecf767cfe4d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237963"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="2272b-103">ユーザーをオンプレミスから Skype for Business Online に移動する</span><span class="sxs-lookup"><span data-stu-id="2272b-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="2272b-104">オンプレミスからオンラインにユーザーを移動した後Skype for Businessユーザーは、その機能のために Skype for Business Online を操作します。</span><span class="sxs-lookup"><span data-stu-id="2272b-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="2272b-105">オンプレミスに存在していた連絡先は Skype for Business Online で利用できます。また、ユーザーが将来開催する既存の会議は更新され、リンクは Skype for Business Online を指します。</span><span class="sxs-lookup"><span data-stu-id="2272b-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="2272b-106">ユーザーが電話会議を有効にしている場合、会議にはダイヤルイン座標も含まれます。</span><span class="sxs-lookup"><span data-stu-id="2272b-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="2272b-107">ユーザーをオンプレミス環境から Skype for Business Online に移動するには、Move-CsUser コマンドレットまたは Skype for Business Server コントロール パネルのいずれかを使用します。どちらもオンプレミス ツールです。</span><span class="sxs-lookup"><span data-stu-id="2272b-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="2272b-108">ユーザーを移動する前に、必ず前提条件を確認 [して](move-users-between-on-premises-and-cloud.md#prerequisites) 、ユーザーをクラウドに移動してください。</span><span class="sxs-lookup"><span data-stu-id="2272b-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="2272b-109">ユーザーをユーザーに移動Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="2272b-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="2272b-110">Move-CsUser管理シェル PowerShell ウィンドウからSkype for Business使用できます。</span><span class="sxs-lookup"><span data-stu-id="2272b-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="2272b-111">「必須の管理資格情報」の説明に従って、オンプレミス環境と Microsoft 365/Office 365 組織の両方で十分な特権を持っている[必要があります](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。</span><span class="sxs-lookup"><span data-stu-id="2272b-111">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365/Office 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="2272b-112">両方の環境で特権を持つ 1 つのアカウントを使用するか、オンプレミスの資格情報を使用してオンプレミスの Skype for Business Server 管理シェル ウィンドウを起動し、パラメーターを使用して、必要な管理役割を持つ Microsoft 365 アカウントまたは Office 365 アカウントの資格情報を指定できます。 `-Credential`</span><span class="sxs-lookup"><span data-stu-id="2272b-112">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="2272b-113">Move-CsUser を使用してユーザーをオンラインに移動するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2272b-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="2272b-114">Identity パラメーターを使用して移動するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="2272b-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="2272b-115">値 "sipfed.online.lync" で -Target パラメーターを指定します。 <span>com」</span><span class="sxs-lookup"><span data-stu-id="2272b-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="2272b-116">オンプレミスと Office 365 の両方で十分なアクセス許可を持つアカウントが 1 つない場合は、-credential パラメーターを使用して、Office 365 で十分なアクセス許可を持つアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="2272b-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="2272b-117">アカウントにアクセス許可を持つアカウントOffice 365.onmicrosoft で終了しない場合。 <span>com"の場合は、-HostedMigrationOverrideUrl パラメーターを指定し、「必須の管理資格情報」の説明に従って正しい値[を指定する必要があります](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。</span><span class="sxs-lookup"><span data-stu-id="2272b-117">If the account with permissions in Office 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="2272b-118">次のコマンドレット シーケンスを使用して、ユーザーを Online に移動Skype for Businessできます。</span><span class="sxs-lookup"><span data-stu-id="2272b-118">The following cmdlet sequence can be used to move a user to Skype for Business Online.</span></span> <span data-ttu-id="2272b-119">この資格情報は、Microsoft 365またはOffice 365資格情報が別のアカウントであり、ユーザープロンプトの入力としてGet-Credentialします。</span><span class="sxs-lookup"><span data-stu-id="2272b-119">It assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="2272b-120">管理者アカウントが MFA (多要素認証) が有効になっている場合は、-Credential パラメーターを指定しません。</span><span class="sxs-lookup"><span data-stu-id="2272b-120">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="2272b-121">管理者に資格情報の入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2272b-121">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="2272b-122">コントロール パネルでユーザー Skype for Business Server移動する</span><span class="sxs-lookup"><span data-stu-id="2272b-122">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="2272b-123">コントロール パネル アプリSkype for Business Server開きます。</span><span class="sxs-lookup"><span data-stu-id="2272b-123">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="2272b-124">左側のナビゲーションで、[ユーザー] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="2272b-124">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="2272b-125">[**検索]** を使用して、[オンライン] に移動するユーザーをSkype for Businessします。</span><span class="sxs-lookup"><span data-stu-id="2272b-125">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="2272b-126">ユーザーを選択し、リストの上にある [アクション] ドロップダウンから 、[選択したユーザーをオンラインに移動Skype for Business **します**。</span><span class="sxs-lookup"><span data-stu-id="2272b-126">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="2272b-127">ウィザードで、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2272b-127">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="2272b-128">メッセージが表示されたら、.Microsoft 365でOffice 365で、十分なアクセス許可を持つアカウントを使用して、Microsoft 365 または onmicrosoft.com にサインインします。</span><span class="sxs-lookup"><span data-stu-id="2272b-128">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="2272b-129">[ **次へ]** をクリックし、[ **次** へ] をクリックしてもう 1 回ユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="2272b-129">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="2272b-130">成功または失敗に関する状態メッセージは、ウィザードではなく、メインのコントロール パネル アプリの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2272b-130">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="2272b-131">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="2272b-131">See also</span></span>

[<span data-ttu-id="2272b-132">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="2272b-132">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)