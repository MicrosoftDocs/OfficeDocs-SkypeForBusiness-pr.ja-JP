---
title: 外部ユーザー アクセスに関するサイト ポリシーまたはユーザー ポリシーの削除
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: '[外部アクセス ポリシー] ページの Skype for Business Server コントロール パネルに表示されているサイトポリシーまたはユーザー ポリシーは削除できます。'
ms.openlocfilehash: 0fbde98868bfe7f8dbe9f97db2350e02dba44560
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817277"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="9743c-103">外部ユーザー アクセスに関するサイト ポリシーまたはユーザー ポリシーの削除</span><span class="sxs-lookup"><span data-stu-id="9743c-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="9743c-104">使用しなくなった外部ユーザー アクセス ポリシーを作成または構成済みの場合は、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="9743c-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="9743c-105">作成したサイトやユーザー ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="9743c-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="9743c-p101">グローバル ポリシーを既定の設定にリセットします。 既定のグローバル ポリシー設定では、外部ユーザー アクセスが許可されません。 グローバル ポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="9743c-p101">Reset the global policy to the default settings. The default global policy settings deny any external user access. The global policy cannot be deleted.</span></span>


<span data-ttu-id="9743c-109">[外部アクセス ポリシー] ページの Skype for Business Server コントロール パネルに表示されているサイトポリシーまたはユーザー ポリシー **は削除** できます。</span><span class="sxs-lookup"><span data-stu-id="9743c-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="9743c-110">グローバル ポリシーを削除すると、実際には削除されず、外部ユーザー アクセス オプションのサポートが含まれていない既定の設定にリセットされるだけです。</span><span class="sxs-lookup"><span data-stu-id="9743c-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="9743c-111">グローバル ポリシーのリセットの詳細については、「外部ユーザー アクセスの [グローバル ポリシーをリセットする」を参照してください](reset-the-global-policy-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="9743c-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="9743c-112">外部ユーザー アクセスのサイト ポリシーまたはユーザー ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="9743c-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="9743c-113">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9743c-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9743c-114">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9743c-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9743c-115">[**外部ユーザー アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9743c-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="9743c-116">[**外部アクセス ポリシー**] タブで、削除するサイト ポリシーまたはユーザー ポリシーをクリックして [**編集**] をクリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9743c-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="9743c-117">削除について確認するメッセージが表示されたら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9743c-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9743c-118">コマンドレットを使用した PIN ポリシー Windows PowerShell削除する</span><span class="sxs-lookup"><span data-stu-id="9743c-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9743c-119">外部アクセス ポリシーは、外部アクセス ポリシーと Windows PowerShell使用してRemove-CsExternalAccessPolicyできます。</span><span class="sxs-lookup"><span data-stu-id="9743c-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="9743c-120">このコマンドレットは、Skype for Business Server 管理シェルまたは Skype for Business Server のリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="9743c-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="9743c-121">特定の外部アクセス ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="9743c-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="9743c-122">次のコマンドでは、Redmond サイトに適用されている外部アクセス ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="9743c-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="9743c-123">ユーザーごとのスコープに適用されている外部アクセス ポリシーをすべて削除するには</span><span class="sxs-lookup"><span data-stu-id="9743c-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="9743c-124">次のコマンドでは、ユーザーごとのスコープで構成されているすべての外部アクセス ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="9743c-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="9743c-125">外部ユーザー アクセスが無効になっているすべての外部アクセス ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="9743c-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="9743c-126">次のコマンドでは、外部ユーザー アクセス ポリシーが無効になっているすべての外部アクセス ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="9743c-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="9743c-127">詳細については [、Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9743c-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>
