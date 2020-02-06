---
title: 外部ユーザー アクセスに関するサイト ポリシーまたはユーザー ポリシーの削除
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: '[外部アクセスポリシー] ページの [Skype for Business Server] コントロールパネルに表示されているサイトまたはユーザーポリシーは、削除することができます。'
ms.openlocfilehash: 2472058009622834e20a1657167c7061b9706579
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818288"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="ff1e7-103">外部ユーザー アクセスに関するサイト ポリシーまたはユーザー ポリシーの削除</span><span class="sxs-lookup"><span data-stu-id="ff1e7-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="ff1e7-104">使用しない外部ユーザーアクセスポリシーを作成または構成している場合は、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ff1e7-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="ff1e7-105">作成したサイトまたはユーザーのポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="ff1e7-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="ff1e7-106">グローバルポリシーを既定の設定にリセットします。</span><span class="sxs-lookup"><span data-stu-id="ff1e7-106">Reset the global policy to the default settings.</span></span> <span data-ttu-id="ff1e7-107">既定のグローバルポリシー設定では、外部ユーザーのアクセスを拒否します。</span><span class="sxs-lookup"><span data-stu-id="ff1e7-107">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="ff1e7-108">グローバルポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="ff1e7-108">The global policy cannot be deleted.</span></span>


<span data-ttu-id="ff1e7-109">[**外部アクセスポリシー** ] ページの [Skype For Business Server] コントロールパネルに表示されているサイトまたはユーザーポリシーは、削除することができます。</span><span class="sxs-lookup"><span data-stu-id="ff1e7-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="ff1e7-110">グローバルポリシーを削除しても、実際に削除されるわけではありませんが、外部ユーザーアクセスオプションのサポートは含まれていない既定の設定にリセットされるだけです。</span><span class="sxs-lookup"><span data-stu-id="ff1e7-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="ff1e7-111">グローバルポリシーのリセットの詳細については、「[外部ユーザーアクセスのグローバルポリシーをリセット](reset-the-global-policy-for-external-user-access.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff1e7-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="ff1e7-112">外部ユーザーアクセスのサイトまたはユーザーポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="ff1e7-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="ff1e7-113">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ff1e7-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ff1e7-114">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ff1e7-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ff1e7-115">[**外部ユーザーアクセス**] をクリックし、[**外部アクセスポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff1e7-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="ff1e7-116">[**外部アクセスポリシー** ] タブで、削除するサイトまたはユーザーのポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff1e7-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="ff1e7-117">削除を確認するメッセージが表示されたら、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff1e7-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ff1e7-118">Windows PowerShell コマンドレットを使用して PIN ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="ff1e7-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ff1e7-119">外部アクセスポリシーは、Windows PowerShell と CsExternalAccessPolicy コマンドレットを使用して削除できます。</span><span class="sxs-lookup"><span data-stu-id="ff1e7-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="ff1e7-120">このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="ff1e7-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="ff1e7-121">特定の外部アクセスポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="ff1e7-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="ff1e7-122">このコマンドは、Redmond サイトに適用されている外部アクセスポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="ff1e7-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="ff1e7-123">ユーザーごとのスコープに適用されたすべての外部アクセスポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="ff1e7-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="ff1e7-124">このコマンドは、ユーザーごとのスコープで構成されたすべての外部アクセスポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="ff1e7-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="ff1e7-125">外部ユーザーアクセスが無効になっている外部アクセスポリシーをすべて削除するには</span><span class="sxs-lookup"><span data-stu-id="ff1e7-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="ff1e7-126">このコマンドは、外部ユーザーアクセスが無効になっている外部アクセスポリシーをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="ff1e7-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="ff1e7-127">詳細については、 [CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff1e7-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>
