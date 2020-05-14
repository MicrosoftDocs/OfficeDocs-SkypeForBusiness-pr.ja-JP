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
description: ユーザーを Skype for Business Online に移動する方法について説明します。
ms.openlocfilehash: a9fb80046195580daca6dfc7f810b2e0c1877f1c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221117"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="211f6-103">ユーザーをオンプレミスから Skype for Business Online に移動する</span><span class="sxs-lookup"><span data-stu-id="211f6-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="211f6-104">オンプレミスから Skype for Business Online にユーザーを移動すると、ユーザーは Skype for Business Online と対話してその機能を利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="211f6-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="211f6-105">オンプレミスに存在していた連絡先は、Skype for business Online で利用できるようになります。また、今後、ユーザーが開催した既存の会議が更新されるようになっています。このリンクは、Skype for Business Online を指すようになります。</span><span class="sxs-lookup"><span data-stu-id="211f6-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="211f6-106">ユーザーが電話会議に対して有効になっている場合、会議にはダイヤルイン座標も含まれます。</span><span class="sxs-lookup"><span data-stu-id="211f6-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="211f6-107">オンプレミス環境から Skype for Business Online にユーザーを移動するには、ユーザーコマンドレットを使用するか、または Skype for Business Server コントロールパネルを使用します。どちらもオンプレミスのツールです。</span><span class="sxs-lookup"><span data-stu-id="211f6-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="211f6-108">ユーザーを移動する前に、ユーザーをクラウドに移動するための[前提条件](move-users-between-on-premises-and-cloud.md#prerequisites)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="211f6-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="211f6-109">Move-CsUser を使用してユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="211f6-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="211f6-110">Move-CsUser は、オンプレミスの Skype for Business 管理シェル PowerShell ウィンドウから入手できます。</span><span class="sxs-lookup"><span data-stu-id="211f6-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="211f6-111">[必要な管理者の資格情報](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)に説明されているように、オンプレミス環境と Microsoft 365/Office 365 組織の両方に十分な特権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="211f6-111">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365/Office 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="211f6-112">両方の環境で権限を持つ単一のアカウントを使用するか、オンプレミスの資格情報を使用してオンプレミスの Skype for Business Server 管理シェルウィンドウを開始することができます。また、パラメーターを使用して、 `-Credential` 必要な管理役割を持つ Microsoft 365 または Office 365 アカウントの資格情報を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="211f6-112">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="211f6-113">ユーザーを Move-CsUser を使用してオンラインに移行するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="211f6-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="211f6-114">Identity パラメーターを使用して移動するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="211f6-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="211f6-115">値が "sipfed <span> " の-Target パラメーターを指定します。com "。</span><span class="sxs-lookup"><span data-stu-id="211f6-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="211f6-116">オンプレミスと Office 365 の両方に十分な権限を持つアカウントがない場合は、-credential パラメーターを使用して、Office 365 に十分なアクセス許可を持つアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="211f6-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="211f6-117">Office 365 のアクセス許可を持つアカウントが "onmicrosoft <span> " で終了していない場合。com の場合は、-HostedMigrationOverrideUrl パラメーターを指定する必要があります。詳細については、「[必要な管理者の資格情報](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="211f6-117">If the account with permissions in Office 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="211f6-118">次のコマンドレットシーケンスを使用して、ユーザーを Skype for Business Online に移動できます。</span><span class="sxs-lookup"><span data-stu-id="211f6-118">The following cmdlet sequence can be used to move a user to Skype for Business Online.</span></span> <span data-ttu-id="211f6-119">この例では、Microsoft 365 または Office 365 の資格情報が別のアカウントであり、資格情報の取得を求めるプロンプトの入力として指定されています。</span><span class="sxs-lookup"><span data-stu-id="211f6-119">It assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="211f6-120">管理者アカウントが MFA (多要素認証) を有効にしている場合は、-Credential パラメーターを指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="211f6-120">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="211f6-121">管理者は資格情報の入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="211f6-121">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="211f6-122">Skype for Business Server コントロールパネルを使用してユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="211f6-122">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="211f6-123">Skype for Business Server コントロールパネルアプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="211f6-123">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="211f6-124">左側のナビゲーションで、[**ユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="211f6-124">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="211f6-125">[**検索**] を使用して、Skype For business Online に移動するユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="211f6-125">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="211f6-126">ユーザーを選択し、リストの上にある**アクション**ドロップダウンから、[**選択されたユーザーを Skype for Business Online に移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="211f6-126">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="211f6-127">ウィザードで、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="211f6-127">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="211f6-128">メッセージが表示された場合は、onmicrosoft.com で終了し、十分な権限があるアカウントを使用して、Microsoft 365 または Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="211f6-128">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="211f6-129">[**次へ**] をクリックし、[**次**へ] をもう一度クリックして、ユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="211f6-129">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="211f6-130">成功または失敗に関するステータスメッセージは、ウィザードではなく、メインコントロールパネルアプリの上部に表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="211f6-130">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="211f6-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="211f6-131">See also</span></span>

[<span data-ttu-id="211f6-132">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="211f6-132">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)
