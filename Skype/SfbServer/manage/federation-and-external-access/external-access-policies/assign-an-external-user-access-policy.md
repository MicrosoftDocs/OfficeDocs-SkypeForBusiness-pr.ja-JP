---
title: 外部ユーザー アクセス ポリシーの割り当て
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ユーザーが有効になって Skype のビジネス サーバー、SIP フェデレーション、リモート ユーザー アクセス、およびパブリック インスタント ビジネス サーバーのコントロール パネルの特定のユーザーに適切なポリシーを適用することにより、Skype での (IM) 接続をメッセージングを構成できます。
ms.openlocfilehash: f07a407fee6f32f4cd4207c93ca19341e409ea78
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881501"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a><span data-ttu-id="b3cf6-103">外部ユーザー アクセス ポリシーを有効になっているビジネス ユーザーに、Skype を割り当てる</span><span class="sxs-lookup"><span data-stu-id="b3cf6-103">Assign an external user access policy to a Skype for Business enabled user</span></span>

<span data-ttu-id="b3cf6-104">ユーザーが有効になって Skype のビジネス サーバー、SIP フェデレーション、リモート ユーザー アクセス、およびパブリック インスタント ビジネス サーバーのコントロール パネルの特定のユーザーに適切なポリシーを適用することにより、Skype での (IM) 接続をメッセージングを構成できます。</span><span class="sxs-lookup"><span data-stu-id="b3cf6-104">If a user has been enabled for Skype for Business Server, you can configure SIP federation, remote user access, and public instant messaging (IM) connectivity in the Skype for Business Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="b3cf6-105">などのリモート ユーザー アクセスをサポートするポリシーを作成した場合必要がありますに適用するユーザー、ユーザーはリモートの場所から、ビジネス サーバーの Skype に接続でき、リモートの場所から内部のユーザーと共同作業を行う前にします。</span><span class="sxs-lookup"><span data-stu-id="b3cf6-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Skype for Business Server from a remote location and collaborate with internal users from the remote location.</span></span>


> [!NOTE]  
> <span data-ttu-id="b3cf6-106">外部ユーザー アクセスをサポートするためには、サポートする外部ユーザー アクセスの種類ごとにサポートを有効にして、適切なポリシーとその使用を制御するその他のオプションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3cf6-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="b3cf6-107">詳細については、[管理するフェデレーションと Skype のビジネス サーバーへの外部アクセス](../managing-federation-and-external-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3cf6-107">For details, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>


<span data-ttu-id="b3cf6-108">このトピックで以前に作成した外部ユーザー アクセス ポリシーを 1 つまたは複数のユーザー アカウントに適用するのに手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="b3cf6-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="b3cf6-109">ユーザー アカウントに、外部のユーザー ポリシーを適用するには</span><span class="sxs-lookup"><span data-stu-id="b3cf6-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="b3cf6-110">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b3cf6-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b3cf6-111">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="b3cf6-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b3cf6-112">左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="b3cf6-112">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="b3cf6-113">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3cf6-113">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b3cf6-114">**外部アクセス ポリシー**] の下の**サーバー ユーザーのビジネスの Skype を編集**、適用するユーザー ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b3cf6-114">In **Edit Skype for Business Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
     
> [!NOTE]  
> <span data-ttu-id="b3cf6-115">\*\* \<Automatic>\*\* の設定は、既定のサーバーまたはグローバル ポリシーの設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="b3cf6-115">The **\<Automatic>** settings apply the default server or global policy settings.</span></span>


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b3cf6-116">Windows PowerShell コマンドレットを使用して、ユーザーごとの外部アクセス ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b3cf6-116">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b3cf6-117">Windows PowerShell と与える CsExternalAccessPolicy コマンドレットを使用して、ユーザーごとの外部アクセス ポリシーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b3cf6-117">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="b3cf6-118">ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b3cf6-118">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="b3cf6-119">1 人のユーザーにユーザーごとの外部アクセス ポリシーを設定するのには</span><span class="sxs-lookup"><span data-stu-id="b3cf6-119">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="b3cf6-120">このコマンドでは、Ken Myer のユーザーに、ユーザーごとの外部アクセス ポリシー RedmondExternalAccessPolicy が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b3cf6-120">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="b3cf6-121">複数のユーザーにユーザーごとの外部アクセス ポリシーを設定するのには</span><span class="sxs-lookup"><span data-stu-id="b3cf6-121">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="b3cf6-122">このコマンドは、アメリカ合衆国の組織単位に Active Directory のアカウントを持つすべてのユーザーに、ユーザーごとの外部アクセス ポリシー USAExternalAccessPolicy を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b3cf6-122">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="b3cf6-123">このコマンドで使用されている OU パラメーターの詳細については、 [Get CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser)コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3cf6-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="b3cf6-124">ユーザーごとの外部アクセス ポリシーの割り当てを解除するには</span><span class="sxs-lookup"><span data-stu-id="b3cf6-124">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="b3cf6-125">このコマンド Ken Myer に割り当てられていたすべてのユーザーごとの外部アクセス ポリシー割り当てが解除されます。</span><span class="sxs-lookup"><span data-stu-id="b3cf6-125">This command unassigns any per-user external access policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="b3cf6-126">ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="b3cf6-126">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="b3cf6-127">サイト ポリシーは、グローバル ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="b3cf6-127">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



<span data-ttu-id="b3cf6-128">詳細については、[補助金 CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3cf6-128">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>


