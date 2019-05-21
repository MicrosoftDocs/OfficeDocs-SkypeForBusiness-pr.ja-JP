---
title: 外部ユーザー アクセス ポリシーの割り当て
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ユーザーが Skype for business Server 用に有効になっている場合は、特定のユーザーに適切なポリシーを適用することにより、Skype for Business Server コントロールパネルで SIP フェデレーション、リモートユーザーアクセス、およびパブリックインスタントメッセージング (IM) 接続を構成できます。
ms.openlocfilehash: ae8bea38a01f9211fc3338faf3e97f737c99e1a4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280174"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a><span data-ttu-id="5a7a4-103">外部ユーザーアクセスポリシーを Skype for Business が有効なユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="5a7a4-103">Assign an external user access policy to a Skype for Business enabled user</span></span>

<span data-ttu-id="5a7a4-104">ユーザーが Skype for business Server 用に有効になっている場合は、特定のユーザーに適切なポリシーを適用することにより、Skype for Business Server コントロールパネルで SIP フェデレーション、リモートユーザーアクセス、およびパブリックインスタントメッセージング (IM) 接続を構成できます。</span><span class="sxs-lookup"><span data-stu-id="5a7a4-104">If a user has been enabled for Skype for Business Server, you can configure SIP federation, remote user access, and public instant messaging (IM) connectivity in the Skype for Business Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="5a7a4-105">たとえば、リモートユーザーアクセスをサポートするためのポリシーを作成した場合、ユーザーがリモートの場所から Skype for Business Server に接続して、リモートの場所から内部ユーザーと共同作業できるようにするには、ユーザーにそのポリシーを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a7a4-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Skype for Business Server from a remote location and collaborate with internal users from the remote location.</span></span>


> [!NOTE]  
> <span data-ttu-id="5a7a4-106">外部ユーザーのアクセスをサポートするには、サポートする外部ユーザーアクセスの種類ごとにサポートを有効にし、その使用を制御するために適切なポリシーとその他のオプションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a7a4-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="5a7a4-107">詳細については、「 [Skype For Business Server へのフェデレーションと外部アクセスの管理](../managing-federation-and-external-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a7a4-107">For details, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>


<span data-ttu-id="5a7a4-108">このトピックの手順を使用して、以前に作成した外部ユーザーアクセスポリシーを1つ以上のユーザーアカウントに適用します。</span><span class="sxs-lookup"><span data-stu-id="5a7a4-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="5a7a4-109">ユーザーアカウントに外部ユーザーポリシーを適用するには</span><span class="sxs-lookup"><span data-stu-id="5a7a4-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="5a7a4-110">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5a7a4-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5a7a4-111">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5a7a4-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5a7a4-112">左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="5a7a4-112">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="5a7a4-113">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a7a4-113">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="5a7a4-114">[**外部アクセスポリシー**] の [ **Skype For business Server ユーザーの編集**] で、適用するユーザーポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="5a7a4-114">In **Edit Skype for Business Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
     
> [!NOTE]  
> <span data-ttu-id="5a7a4-115">\*\* \<Automatic>\*\* の設定では、既定のサーバーまたはグローバルポリシーの設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="5a7a4-115">The **\<Automatic>** settings apply the default server or global policy settings.</span></span>


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5a7a4-116">Windows PowerShell コマンドレットを使用して、ユーザーごとの外部アクセスポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="5a7a4-116">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5a7a4-117">ユーザーごとの外部アクセスポリシーは、Windows PowerShell と Grant-CsExternalAccessPolicy コマンドレットを使用して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="5a7a4-117">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="5a7a4-118">このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="5a7a4-118">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="5a7a4-119">ユーザーごとの外部アクセスポリシーを1人のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="5a7a4-119">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="5a7a4-120">このコマンドを実行すると、ユーザーごとの外部アクセスポリシー RedmondExternalAccessPolicy が Ken Myer に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="5a7a4-120">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="5a7a4-121">ユーザーごとの外部アクセスポリシーを複数のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="5a7a4-121">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="5a7a4-122">このコマンドによって、Active Directory の米国 OU にアカウントを持つすべてのユーザーに、ユーザーごとの外部アクセスポリシー USAExternalAccessPolicy が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="5a7a4-122">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="5a7a4-123">このコマンドで使用される OU パラメーターの詳細については、「[ユーザーの取得](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser)」コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a7a4-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="5a7a4-124">ユーザーごとの外部アクセスポリシーを割り当て解除するには</span><span class="sxs-lookup"><span data-stu-id="5a7a4-124">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="5a7a4-125">このコマンドは、前に Ken Myer に割り当てられているユーザーごとの外部アクセスポリシーを割り当て解除します。</span><span class="sxs-lookup"><span data-stu-id="5a7a4-125">This command unassigns any per-user external access policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="5a7a4-126">ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="5a7a4-126">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="5a7a4-127">サイト ポリシーは、グローバル ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="5a7a4-127">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



<span data-ttu-id="5a7a4-128">詳細については、「 [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a7a4-128">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>


