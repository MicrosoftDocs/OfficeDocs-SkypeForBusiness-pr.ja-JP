---
title: ユーザーをオンプレミスから Skype for Business Online に移動する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/12/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
description: '概要: は、ユーザー設定を移行し、オンライン ビジネスの Skype ユーザーを移動する方法を説明します。'
ms.openlocfilehash: 25065f5765f46d5432e59d8053573a13e37dc8a1
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569415"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="9421e-103">ユーザーをオンプレミスから Skype for Business Online に移動する</span><span class="sxs-lookup"><span data-stu-id="9421e-103">Move users from on premises to Skype for Business Online</span></span>
 
<span data-ttu-id="9421e-104">**の概要:** ユーザー設定を移行し、オンライン ビジネスの Skype ユーザーを移動する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9421e-104">**Summary:** Learn how to migrate user settings and move users to Skype for Business Online.</span></span>
  
<span data-ttu-id="9421e-p101">ユーザーを実際に Office 365 に移動する前に、まずユーザー アカウントがクラウドと同期されていることを確認してライセンスを割り当てる必要があります。この操作には、Office 365 管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9421e-p101">Before actually moving the user to Office 365, you should first confirm that the user accounts are synchronized to the cloud, and assign them a license. To do this, you use the Office 365 Admin Center.</span></span>
  
### <a name="to-confirm-that-an-on-premises-user-account-has-been-synchronized-with-office-365"></a><span data-ttu-id="9421e-107">オンプレミス ユーザー アカウントが Office 365 と同期していることを確認するには</span><span class="sxs-lookup"><span data-stu-id="9421e-107">To confirm that an on-premises user account has been synchronized with Office 365</span></span>

1. <span data-ttu-id="9421e-108">テナント管理者用のアカウントを使用して、テナントの[Office 365 管理センター](https://portal.office.com/)を開きます。</span><span class="sxs-lookup"><span data-stu-id="9421e-108">Using an tenant admin account, open the [Office 365 admin center](https://portal.office.com/) for your tenant.</span></span>  <span data-ttu-id="9421e-109">テナント管理者のアカウントが Office 365 でこの機能を実行するのにはビジネス管理者の役割とユーザー管理の役割 (または、グローバル管理者ロール) の両方、Skype を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9421e-109">Tenant admin accounts should be granted both the Skype for Business Admin Role and the User Management Role (or the Global Admin role) to perform this function in Office 365</span></span>
    
2. <span data-ttu-id="9421e-110">左側のナビゲーション ウィンドウで、[**ユーザー**]、[**アクティブなユーザー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="9421e-110">On the left navigation pane, click **Users** and then **Active Users**.</span></span>
    
3. <span data-ttu-id="9421e-111">[**ユーザーの検索**] をクリックして、ユーザーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="9421e-111">Click **Search for a User**, and type the name of the user.</span></span>
    
4. <span data-ttu-id="9421e-112">ユーザーが表示されており、そのステータスが [**Active Directory と同期済み**] であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9421e-112">Confirm that you see the user, and that their status is **Synched with Active Directory**.</span></span>
    
    <span data-ttu-id="9421e-113">ユーザーがまだ同期されていない場合は、3 時間以内に次の自動同期が実行されます。</span><span class="sxs-lookup"><span data-stu-id="9421e-113">If the user is not yet synchronized, the next automatic synchronization should happen within three hours.</span></span> <span data-ttu-id="9421e-114">早く同期を強制的にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9421e-114">You can also force a synchronization sooner.</span></span> <span data-ttu-id="9421e-115">詳細については、[ディレクトリ同期の強制](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9421e-115">For more information, see [Force Directory Synchronization](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx).</span></span>
    
<span data-ttu-id="9421e-116">Office 365 のライセンスを割り当てるには、[ビジネス向けの Office 365 のライセンスを割り当てる](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9421e-116">To assign the license in Office 365, see [Assign licenses for Office 365 for Business](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
## <a name="migrate-user-settings-to-skype-for-business-online"></a><span data-ttu-id="9421e-117">Skype をオンライン ビジネスのユーザー設定を移行します。</span><span class="sxs-lookup"><span data-stu-id="9421e-117">Migrate user settings to Skype for Business Online</span></span>

<span data-ttu-id="9421e-118">Skype をビジネス オンラインのユーザーを移行を開始する前に移動するアカウントに関連付けられたユーザー データをバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9421e-118">Before you start migrating users to Skype for Business Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="9421e-119">ユーザー アカウントと共にすべてのユーザー データが移動されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="9421e-119">Not all user data is moved with the user account.</span></span> <span data-ttu-id="9421e-120">についてを参照してください[のバックアップと復元の要件: データ](http://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9421e-120">For information, see [Backup and Restoration Requirements: Data](http://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx).</span></span>
  
<span data-ttu-id="9421e-p105">ユーザー設定は、ユーザー アカウントと共に移動されます。いくつかのオンプレミス設定は、ユーザー アカウントと共に移動されることはありません。</span><span class="sxs-lookup"><span data-stu-id="9421e-p105">User settings are moved with the user account. Some on-premises settings are not moved with the user account.</span></span>
  
## <a name="move-pilot-users-to-skype-for-business-online"></a><span data-ttu-id="9421e-123">ビジネス オンラインの Skype をパイロット ユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="9421e-123">Move pilot users to Skype for Business Online</span></span>

<span data-ttu-id="9421e-124">Skype をビジネス オンラインのユーザーを移動する前に、お客様の環境が正しく構成されていることを確認するのには、いくつかのパイロット ユーザーを移動することがあります。</span><span class="sxs-lookup"><span data-stu-id="9421e-124">Before you begin to move users to Skype for Business Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="9421e-125">その他のユーザーを移動する前に、機能とサービス機能が予想どおりであることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="9421e-125">You can then verify that the features and services function as expected before attempting to move additional users.</span></span>
  
<span data-ttu-id="9421e-126">オンライン ビジネスのテナントの Skype に、オンプレミスのユーザーを移動するには、ビジネス サーバー管理シェルを管理者の資格情報を使用して、Microsoft Office 365 のテナントのため、Skype で次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9421e-126">To move an on-premises user to your Skype for Business Online tenant, run the following cmdlets in the Skype for Business Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="9421e-127">"username@contoso.com" を、移動するユーザーの情報で置換します。</span><span class="sxs-lookup"><span data-stu-id="9421e-127">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds 
```

## <a name="move-users-to-skype-for-business-online"></a><span data-ttu-id="9421e-128">Skype for Business Online にユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="9421e-128">Move users to Skype for Business Online</span></span>

<span data-ttu-id="9421e-129">[Get CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)コマンドレットを使用して複数のユーザーを移動することができます、RegistrarPool などのユーザー アカウントに割り当てられている特定のプロパティを使用してユーザーを選択するフィルター パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9421e-129">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet with the -Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="9421e-130">コマンドレットにパイプ[移動 CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps)コマンドレットでは、返されるユーザーは、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="9421e-130">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) cmdlet, as shown in the following example.</span></span>
  
```
Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds 
```

<span data-ttu-id="9421e-131">次の例のようには、指定した OU 内のすべてのユーザーを取得するために OU パラメーターを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9421e-131">You can also use the -OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>
  
```
Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds 
```

## <a name="verify-online-user-settings-and-features"></a><span data-ttu-id="9421e-132">オンライン ユーザーの設定と機能を確認する</span><span class="sxs-lookup"><span data-stu-id="9421e-132">Verify online user settings and features</span></span>

<span data-ttu-id="9421e-133">ユーザーの移動が正常に完了したことは、次の方法で確認できます。</span><span class="sxs-lookup"><span data-stu-id="9421e-133">You can verify that the user was moved successfully in the following ways:</span></span>
  
- <span data-ttu-id="9421e-p109">Skype for Business Online コントロール パネルでユーザーの状態を表示します。オンプレミス ユーザーとオンライン ユーザーでは視覚的なインジケーターが異なります。</span><span class="sxs-lookup"><span data-stu-id="9421e-p109">View the status of the user in the Skype for Business Online Control Panel. The visual indicator for on-premises users and online users is different.</span></span>
    
- <span data-ttu-id="9421e-136">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9421e-136">Run the following cmdlet:</span></span>
    
  ```
  Get-CsUser -Identity
  ```