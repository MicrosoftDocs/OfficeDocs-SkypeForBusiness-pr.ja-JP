---
title: ユーザーをオンプレミスから Skype for Business Online に移動する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: Skype をビジネス オンラインのユーザーを移動する方法について説明します。
ms.openlocfilehash: 083f2f52fd07439d85d017db9c4b035b8ea326b6
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2018
ms.locfileid: "27243998"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="14c74-103">ユーザーをオンプレミスから Skype for Business Online に移動する</span><span class="sxs-lookup"><span data-stu-id="14c74-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="14c74-104">移動した後、ユーザー設置から Skype オンライン ビジネスのユーザーと対話する Skype オンライン ビジネスの機能をします。</span><span class="sxs-lookup"><span data-stu-id="14c74-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="14c74-105">設置型に存在していた取引先担当者は、ビジネス オンラインの Skype で利用可能ななりビジネス オンラインの Skype のリンクをポイントするように将来のユーザーが構成されて、既存の会議の更新されます。</span><span class="sxs-lookup"><span data-stu-id="14c74-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="14c74-106">オーディオ会議で、ユーザーが有効な場合、会議はダイヤルインの座標も含まれます。</span><span class="sxs-lookup"><span data-stu-id="14c74-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="14c74-107">ビジネス オンラインの Skype をオンプレミス環境からユーザーを移動するには、設置型のツールは、両方とも、ビジネス サーバー コントロール パネルの移動 CsUser コマンドレット、または、Skype のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="14c74-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="14c74-108">すべてのユーザーを移動する前に必ずユーザーをクラウドに移行する[前提条件](move-users-between-on-premises-and-cloud.md#prerequisites)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="14c74-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="14c74-109">Csuser からの移動でユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="14c74-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="14c74-110">Csuser からの移動を指定する場合は、オンプレミス Skype のビジネス管理シェルの PowerShell ウィンドウで実行できます。</span><span class="sxs-lookup"><span data-stu-id="14c74-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="14c74-111">[管理者の資格情報が必要](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)で説明したように両方設置環境にも、Office 365 テナントのように十分な特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="14c74-111">You must have sufficient privileges in both the on-premises environment as well as in the Office 365 tenant as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="14c74-112">両方の環境で権限のある単一のアカウントを使用することができますか、または設置型の資格情報を持つビジネス サーバー管理シェル ウィンドウに、オンプレミス Skype を起動し、使用できます、 `-Credential` 、Office 365 の資格情報を指定するパラメーター必要な Office 365 管理者の役割を持つアカウント。</span><span class="sxs-lookup"><span data-stu-id="14c74-112">You can either use a single account that has privileges in both environments, or you can start an on-premise Skype for Business Server Management Shell window with on-premise credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="14c74-113">オンラインにユーザーを移動する移動 CsUser を使用します。</span><span class="sxs-lookup"><span data-stu-id="14c74-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="14c74-114">Id パラメーターを使用して移動するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="14c74-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="14c74-115">指定ターゲット パラメーターを指定する値"sipfed.online.lync。<span>com"します。</span><span class="sxs-lookup"><span data-stu-id="14c74-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="14c74-116">設置型および Office 365 の両方のための十分なアクセス許可を持つ 1 つのアカウントがないを使用して、Office 365 のための十分な権限を持つアカウントを指定するには、資格情報パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="14c74-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="14c74-117">」On.microsoft で Office 365 にアクセス許可を持つアカウントが終わっていない場合。<span>com」、[ために必要な管理者資格情報](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)で説明するよう、正しい値を持つ、- HostedMigrationOverrideUrl パラメーターを指定する必要があり、。</span><span class="sxs-lookup"><span data-stu-id="14c74-117">If the account with permissions in Office 365 does not end in “on.microsoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="14c74-118">次のコマンドレットのシーケンスは、Skype をビジネス オンラインでのユーザーを移動する使用することができ、Office 365 の資格情報は別のアカウントであり、取得の資格情報のプロンプトへの入力として提供されたと仮定しています。</span><span class="sxs-lookup"><span data-stu-id="14c74-118">The following cmdlet sequence can be used to move a user to Skype for Business Online, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```
## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="14c74-119">ビジネス サーバーのコントロール パネルの Skype でユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="14c74-119">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="14c74-120">ビジネス サーバー管理のため、Skype を開くパネルのアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="14c74-120">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="14c74-121">左側のナビゲーションでは、**ユーザー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="14c74-121">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="14c74-122">**検索**を使用すると、Skype のビジネスをオンラインに移動したいユーザーを検索できます。</span><span class="sxs-lookup"><span data-stu-id="14c74-122">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="14c74-123">、ユーザーを選択して、**アクション**ドロップダウン リストの上からクリックして**Skype オンライン ビジネス用に選択したユーザーを移動**します。</span><span class="sxs-lookup"><span data-stu-id="14c74-123">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="14c74-124">ウィザードで、[**次へ**] クリックします。</span><span class="sxs-lookup"><span data-stu-id="14c74-124">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="14c74-125">メッセージが表示されたらにサインイン、Office 365 で終了するアカウントを使用しています。 onmicrosoft.com 十分なアクセス許可とします。</span><span class="sxs-lookup"><span data-stu-id="14c74-125">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="14c74-126">ユーザーを移動するのには**次へ**、し、[**次へ**1 つのより多くの時間をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14c74-126">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="14c74-127">ウィザードではなく、メインのコントロール パネルの [アプリケーションの上部に成功または失敗に関連するステータス メッセージが提供されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="14c74-127">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="14c74-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="14c74-128">See also</span></span>

[<span data-ttu-id="14c74-129">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="14c74-129">Move-CsUser</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)