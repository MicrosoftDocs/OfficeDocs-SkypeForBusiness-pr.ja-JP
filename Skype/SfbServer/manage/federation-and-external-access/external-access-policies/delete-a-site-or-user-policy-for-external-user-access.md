---
title: 外部ユーザー アクセスに関するサイト ポリシーまたはユーザー ポリシーの削除
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 記載されている、Skype ビジネス サーバーのコントロール パネルの [外部アクセス ポリシー] ページで、サイトまたはユーザーのポリシーを削除することができます。
ms.openlocfilehash: 24d26e8668d04f1c11a3039b4b524d25e209e619
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197745"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="fa3c0-103">外部ユーザー アクセスに関するサイト ポリシーまたはユーザー ポリシーの削除</span><span class="sxs-lookup"><span data-stu-id="fa3c0-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="fa3c0-104">作成または、外部ユーザー アクセス ポリシーを使用する必要がなくなったように構成した場合は、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fa3c0-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="fa3c0-105">作成したサイトまたはユーザーのポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa3c0-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="fa3c0-106">グローバル ポリシーを既定の設定にリセットします。</span><span class="sxs-lookup"><span data-stu-id="fa3c0-106">Reset the global policy to the default settings.</span></span> <span data-ttu-id="fa3c0-107">既定のグローバル ポリシー設定は、すべての外部ユーザー アクセスを拒否します。</span><span class="sxs-lookup"><span data-stu-id="fa3c0-107">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="fa3c0-108">グローバル ポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="fa3c0-108">The global policy cannot be deleted.</span></span>


<span data-ttu-id="fa3c0-109">記載されている、Skype ビジネス サーバーのコントロール パネルの [**外部アクセス ポリシー** ] ページで、サイトまたはユーザーのポリシーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="fa3c0-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="fa3c0-110">グローバル ポリシーを削除すると、実際には削除されず、ですが、のみが、外部ユーザー アクセス オプションのサポートが含まれていない既定の設定にリセットします。</span><span class="sxs-lookup"><span data-stu-id="fa3c0-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="fa3c0-111">グローバル ポリシーのリセットの詳細については、[外部ユーザー アクセス用のグローバル ポリシーのリセット](reset-the-global-policy-for-external-user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa3c0-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="fa3c0-112">外部ユーザー アクセスのサイトまたはユーザーのポリシーを削除するのには</span><span class="sxs-lookup"><span data-stu-id="fa3c0-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="fa3c0-113">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="fa3c0-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fa3c0-114">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="fa3c0-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="fa3c0-115">**外部ユーザー アクセス**] をクリックして、[**外部アクセス ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa3c0-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="fa3c0-116">[**外部アクセス ポリシー** ] タブで、削除、**編集**] をクリックし、[**削除**] をクリックするサイトまたはユーザーのポリシーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa3c0-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="fa3c0-117">削除の確認メッセージが表示されたら、[ **OK**を] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa3c0-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fa3c0-118">Windows PowerShell コマンドレットを使用して、暗証番号 (pin) ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa3c0-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fa3c0-119">外部アクセス ポリシーは、Windows PowerShell と削除 CsExternalAccessPolicy コマンドレットを使用して削除できます。</span><span class="sxs-lookup"><span data-stu-id="fa3c0-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="fa3c0-120">ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="fa3c0-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="fa3c0-121">特定の外部アクセス ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="fa3c0-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="fa3c0-122">このコマンドは、Redmond サイトに適用される外部アクセス ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa3c0-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="fa3c0-123">外部アクセス ユーザーごとのスコープに適用されるポリシーをすべて削除するには</span><span class="sxs-lookup"><span data-stu-id="fa3c0-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="fa3c0-124">このコマンドは、ユーザーごとのスコープで構成されているすべての外部アクセス ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa3c0-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="fa3c0-125">外部ユーザー アクセスが無効になっているすべての外部アクセス ポリシーを削除するのには</span><span class="sxs-lookup"><span data-stu-id="fa3c0-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="fa3c0-126">このコマンドは、外部ユーザー アクセスが無効になってすべての外部アクセス ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa3c0-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="fa3c0-127">詳細については、[削除 CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa3c0-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>
