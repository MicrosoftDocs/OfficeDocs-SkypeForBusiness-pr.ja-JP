---
title: 外部ユーザー アクセス ポリシーの割り当て
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
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
description: ユーザーが Skype for Business Server に対して有効になっている場合は、特定のユーザーに適切なポリシーを適用することで、Skype for Business Server コントロール パネルで SIP フェデレーション、リモート ユーザー アクセス、およびパブリック インスタント メッセージング (IM) 接続を構成できます。
ms.openlocfilehash: 25e9a63363dc4f982e142defd2164c2423471961
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826627"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a><span data-ttu-id="13825-103">Skype for Business が有効なユーザーに外部ユーザー アクセス ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="13825-103">Assign an external user access policy to a Skype for Business enabled user</span></span>

<span data-ttu-id="13825-104">ユーザーが Skype for Business Server に対して有効になっている場合は、特定のユーザーに適切なポリシーを適用することで、Skype for Business Server コントロール パネルで SIP フェデレーション、リモート ユーザー アクセス、およびパブリック インスタント メッセージング (IM) 接続を構成できます。</span><span class="sxs-lookup"><span data-stu-id="13825-104">If a user has been enabled for Skype for Business Server, you can configure SIP federation, remote user access, and public instant messaging (IM) connectivity in the Skype for Business Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="13825-105">たとえば、リモート ユーザー アクセスをサポートするポリシーを作成した場合、ユーザーがリモートの場所から Skype for Business Server に接続し、リモートの場所から内部ユーザーと共同作業を行う前に、そのポリシーをユーザーに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13825-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Skype for Business Server from a remote location and collaborate with internal users from the remote location.</span></span>


> [!NOTE]  
> <span data-ttu-id="13825-106">外部ユーザー アクセスをサポートするには、サポートする各種類の外部ユーザー アクセスのサポートを有効にし、適切なポリシーとその他の使用制御オプションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13825-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="13825-107">詳細については [、「Skype for Business Server へのフェデレーションと外部アクセスの管理」を参照してください](../managing-federation-and-external-access.md)。</span><span class="sxs-lookup"><span data-stu-id="13825-107">For details, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>


<span data-ttu-id="13825-108">このトピックの手順を使用して、あらかじめ作成した外部ユーザー アクセス ポリシーを、1 つまたは複数のユーザー アカウントに適用します。</span><span class="sxs-lookup"><span data-stu-id="13825-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="13825-109">外部ユーザー ポリシーをユーザー アカウントに適用するには</span><span class="sxs-lookup"><span data-stu-id="13825-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="13825-110">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="13825-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="13825-111">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="13825-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="13825-112">左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="13825-112">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="13825-113">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13825-113">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="13825-114">[ **外部アクセス ポリシー] の [Skype for Business Server** ユーザーの編集] **で、適用** するユーザー ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="13825-114">In **Edit Skype for Business Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
     
> [!NOTE]  
> <span data-ttu-id="13825-115">この **\<Automatic>** 設定では、既定のサーバーまたはグローバル ポリシー設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="13825-115">The **\<Automatic>** settings apply the default server or global policy settings.</span></span>


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="13825-116">外部アクセス Per-Userコマンドレットを使用して外部アクセス ポリシー Windows PowerShell割り当てる</span><span class="sxs-lookup"><span data-stu-id="13825-116">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="13825-117">ユーザーごとの外部アクセス ポリシーは、ユーザーごとの外部アクセス ポリシーと Windows PowerShellコマンドレットをGrant-CsExternalAccessPolicyできます。</span><span class="sxs-lookup"><span data-stu-id="13825-117">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="13825-118">このコマンドレットは、Skype for Business Server 管理シェルまたは Skype for Business Server のリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="13825-118">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="13825-119">ユーザー単位の外部アクセス ポリシーを 1 人のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="13825-119">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="13825-120">次のコマンドは、ユーザーごとの外部アクセス ポリシー RedmondExternalAccessPolicy をユーザー Ken Myer に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="13825-120">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="13825-121">ユーザー単位の外部アクセス ポリシーを複数のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="13825-121">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="13825-122">次のコマンドは、ユーザーごとの外部アクセス ポリシー USAExternalAccessPolicy を、Active Directory の UnitedStates OU にアカウントを持っているすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="13825-122">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="13825-123">このコマンドで使用される OU パラメーターの詳細については [、Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="13825-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="13825-124">ユーザーごとの外部アクセス ポリシーの割り当てを解除するには</span><span class="sxs-lookup"><span data-stu-id="13825-124">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="13825-p105">次のコマンドは、以前に Ken Myer に割り当てたユーザーごとの外部アクセス ポリシーのすべての割り当てを解除します。ユーザーごとのポリシーの割り当てを解除された後の Ken Myer は、グローバル ポリシーまたは存在する場合はローカル サイト ポリシーを使用して、自動的に管理されます。サイト ポリシーの方がグローバル ポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="13825-p105">This command unassigns any per-user external access policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



<span data-ttu-id="13825-128">詳細については [、Grant-CsExternalAccessPolicy コマンドレット](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="13825-128">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>


