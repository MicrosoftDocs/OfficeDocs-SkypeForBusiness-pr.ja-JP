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
description: '概要: は、ユーザー設定を移行し、オンライン ビジネスの Skype ユーザーを移動する方法を説明します。'
ms.openlocfilehash: 9fd51c55be35e55be6ca837ccb72413043283ac7
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "25030750"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="4f4f3-103">ユーザーをオンプレミスから Skype for Business Online に移動する</span><span class="sxs-lookup"><span data-stu-id="4f4f3-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="4f4f3-104">**の概要:** ユーザー設定を移行し、オンライン ビジネスの Skype ユーザーを移動する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-104">**Summary:** Learn how to migrate user settings and move users to Skype for Business Online.</span></span>

<span data-ttu-id="4f4f3-105">Office 365 にユーザーを実際に移動するには、前に、ユーザー アカウントは、クラウドに同期され、ライセンスを割り当てることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-105">Before actually moving a user to Office 365, you should first confirm that the user accounts are synchronized to the cloud, and assign them a license.</span></span> <span data-ttu-id="4f4f3-106">この操作には、Office 365 管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-106">To do this, you use the Office 365 Admin Center.</span></span>

### <a name="to-confirm-that-an-on-premises-user-account-has-been-synchronized-with-office-365"></a><span data-ttu-id="4f4f3-107">オンプレミス ユーザー アカウントが Office 365 と同期していることを確認するには</span><span class="sxs-lookup"><span data-stu-id="4f4f3-107">To confirm that an on-premises user account has been synchronized with Office 365</span></span>

1. <span data-ttu-id="4f4f3-108">テナント管理者のアカウントを使用して、テナントの Office 365 の管理ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-108">Using a tenant admin account, open the Office 365 admin center for your tenant.</span></span>  <span data-ttu-id="4f4f3-109">テナント管理者のアカウントは、Office 365 でこの機能を実行するのにはビジネス管理者の役割とユーザー管理の役割 (または、グローバル管理者ロール) の両方の Skype に付与してください。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-109">Tenant admin accounts should be granted both the Skype for Business Admin Role and the User Management Role (or the Global Admin role) to perform this function in Office 365.</span></span>

2. <span data-ttu-id="4f4f3-110">左側のナビゲーション ウィンドウで、[**ユーザー**] をクリックし、[**アクティブ ユーザ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-110">On the left navigation pane, click **Users**, and then click **Active Users**.</span></span>

3. <span data-ttu-id="4f4f3-111">[**ユーザーの検索**] をクリックして、ユーザーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-111">Click **Search for a User**, and type the name of the user.</span></span>

4. <span data-ttu-id="4f4f3-112">ユーザーを参照してください、それらの状態が**Active Directory に Synched**を確認します。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-112">Confirm that you see the user and that their status is **Synched with Active Directory**.</span></span>

    <span data-ttu-id="4f4f3-113">ユーザーがまだ同期されていない場合は、3 時間以内に次の自動同期が実行されます。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-113">If the user is not yet synchronized, the next automatic synchronization should happen within three hours.</span></span> <span data-ttu-id="4f4f3-114">早く同期を強制的にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-114">You can also force a synchronization sooner.</span></span> <span data-ttu-id="4f4f3-115">詳細については、[ディレクトリ同期の強制](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-115">For more information, see [Force Directory Synchronization](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx).</span></span>

<span data-ttu-id="4f4f3-116">Office 365 のライセンスを割り当てるには、[ビジネス向けの Office 365 のユーザーにライセンスを割り当てる](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-116">To assign the license in Office 365, see [Assign licenses to users in Office 365 for Business](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="migrate-user-settings-to-skype-for-business-online"></a><span data-ttu-id="4f4f3-117">Skype をオンライン ビジネスのユーザー設定を移行します。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-117">Migrate user settings to Skype for Business Online</span></span>

<span data-ttu-id="4f4f3-118">Skype をビジネス オンラインのユーザーを移行する前に移動するアカウントに関連付けられたユーザー データをバックアップしてください。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-118">Before you migrate users to Skype for Business Online, you should back up the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="4f4f3-119">ユーザー アカウントと共にすべてのユーザー データが移動されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-119">Not all user data is moved with the user account.</span></span> <span data-ttu-id="4f4f3-120">についてを参照してください[のバックアップと復元の要件: データ](https://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-120">For information, see [Backup and Restoration Requirements: Data](https://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx).</span></span>

<span data-ttu-id="4f4f3-p105">ユーザー設定は、ユーザー アカウントと共に移動されます。いくつかのオンプレミス設定は、ユーザー アカウントと共に移動されることはありません。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-p105">User settings are moved with the user account. Some on-premises settings are not moved with the user account.</span></span>

## <a name="move-pilot-users-to-skype-for-business-online"></a><span data-ttu-id="4f4f3-123">ビジネス オンラインの Skype をパイロット ユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="4f4f3-123">Move pilot users to Skype for Business Online</span></span>

<span data-ttu-id="4f4f3-124">Skype をビジネス オンラインのユーザーを移動する前に、環境が正しく構成されていることを確認するのには、いくつかのパイロット ユーザーを移動することがあります。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-124">Before you move users to Skype for Business Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="4f4f3-125">その他のユーザーを移動する前に、機能とサービス機能が予想どおりであることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-125">You can then verify that the features and services function as expected before attempting to move additional users.</span></span>

<span data-ttu-id="4f4f3-126">オンライン ビジネスのテナントの Skype に、オンプレミスのユーザーを移動するには、ビジネス サーバー管理シェルを管理者の資格情報を使用して、Microsoft Office 365 のテナントのため、Skype で次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-126">To move an on-premises user to your Skype for Business Online tenant, run the following cmdlets in the Skype for Business Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="4f4f3-127">"Username@contoso.com"を移動したいユーザーの情報に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-127">Replace "username@contoso.com" with the information for the user you want to move.</span></span>

```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds
```

## <a name="move-users-to-skype-for-business-online"></a><span data-ttu-id="4f4f3-128">Skype for Business Online にユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="4f4f3-128">Move users to Skype for Business Online</span></span>

<span data-ttu-id="4f4f3-129">[Get CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)コマンドレットを使用して複数のユーザーを移動することができます、RegistrarPool などのユーザー アカウントに割り当てられている特定のプロパティを使用してユーザーを選択するフィルター パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-129">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet with the -Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="4f4f3-130">コマンドレットにパイプ[移動 CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps)コマンドレットでは、返されるユーザーは、次の例に示すように。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-130">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) cmdlet, as shown in the following example:</span></span>

```
Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds
```

<span data-ttu-id="4f4f3-131">次の例に示すように、指定した OU 内のすべてのユーザーを取得するために OU パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-131">You can also use the -OU parameter to retrieve all users in the specified OU, as shown in the following example:</span></span>

```
Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds
```

## <a name="verify-online-user-settings-and-features"></a><span data-ttu-id="4f4f3-132">オンライン ユーザーの設定と機能を確認する</span><span class="sxs-lookup"><span data-stu-id="4f4f3-132">Verify online user settings and features</span></span>

<span data-ttu-id="4f4f3-133">ユーザーの移動が正常に完了したことは、次の方法で確認できます。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-133">You can verify that the user was moved successfully in the following ways:</span></span>

- <span data-ttu-id="4f4f3-p109">Skype for Business Online コントロール パネルでユーザーの状態を表示します。オンプレミス ユーザーとオンライン ユーザーでは視覚的なインジケーターが異なります。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-p109">View the status of the user in the Skype for Business Online Control Panel. The visual indicator for on-premises users and online users is different.</span></span>

- <span data-ttu-id="4f4f3-136">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="4f4f3-136">Run the following cmdlet:</span></span>

  ```
  Get-CsUser -Identity
  ```


