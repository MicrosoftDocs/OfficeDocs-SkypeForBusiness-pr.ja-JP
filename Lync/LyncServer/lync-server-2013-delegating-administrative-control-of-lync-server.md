---
title: 'Lync Server 2013: Lync Server の管理制御の委任'
description: 'Lync Server 2013: Lync Server の管理制御を委任します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegating administrative control of Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48183418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8d3710af2d194a5aa4ebdd7291be2ee58176507
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567493"
---
# <a name="delegating-administrative-control-of-lync-server-2013"></a><span data-ttu-id="e4165-103">Lync Server 2013 の管理制御の委任</span><span class="sxs-lookup"><span data-stu-id="e4165-103">Delegating administrative control of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4165-104">_**トピックの最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="e4165-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="e4165-105">Lync Server 2013 では、新しい役割ベースのアクセス制御 (RBAC) 機能を使用して、管理タスクがユーザーに委任されます。</span><span class="sxs-lookup"><span data-stu-id="e4165-105">In Lync Server 2013, administrative tasks are delegated to users by using the new role-based access control (RBAC) feature.</span></span> <span data-ttu-id="e4165-106">Lync Server をインストールすると、いくつかの RBAC の役割が作成されます。</span><span class="sxs-lookup"><span data-stu-id="e4165-106">When you install Lync Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="e4165-107">これらの役割は、Active Directory ドメインサービスのユニバーサルセキュリティグループに対応します。</span><span class="sxs-lookup"><span data-stu-id="e4165-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="e4165-108">たとえば、RBAC 役割 CsHelpDesk は、Active Directory ドメインサービスの Users コンテナーにある CsHelpDesk グループに対応します。</span><span class="sxs-lookup"><span data-stu-id="e4165-108">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="e4165-109">さらに、各 RBAC の役割は、Lync Server Windows PowerShell コマンドレットのセットに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="e4165-109">In addition, each RBAC role is associated with a set of Lync Server Windows PowerShell cmdlets.</span></span> <span data-ttu-id="e4165-110">これらのコマンドレットは、特定の RBAC の役割が割り当てられているユーザーが実行できるタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="e4165-110">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="e4165-111">たとえば、CsHelpDesk 役割には Lock-CsClientPin コマンドレットと UnlockCsClientPin コマンドレットが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="e4165-111">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="e4165-112">これは、CsHelpDesk の役割が割り当てられているユーザーが、ユーザーの PIN 番号をロックおよびロック解除できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e4165-112">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="e4165-113">ただし、CsHelpDesk の役割には New-CsVoicePolicy コマンドレットが割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="e4165-113">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="e4165-114">これは、CsHelpDesk 役割が割り当てられているユーザーが新しい音声ポリシーを作成できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e4165-114">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

<div>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="e4165-115">RBAC の役割に関する情報の表示</span><span class="sxs-lookup"><span data-stu-id="e4165-115">Viewing Information about RBAC Roles</span></span>

<span data-ttu-id="e4165-116">RBAC の役割に関する基本的な情報を取得するには、Lync Server 管理シェルから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e4165-116">You can retrieve basic information about your RBAC roles by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRole

<span data-ttu-id="e4165-117">RBAC の役割 (CsVoiceAdministrator など) の Id は、Active Directory ドメインサービスのユーザーコンテナーにあるセキュリティグループに直接マッピングされていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e4165-117">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="e4165-118">役割に割り当てられているコマンドレットのリストを表示するには、次のようなコマンドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="e4165-118">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="e4165-119">ユーザーへの RBAC の役割の割り当て</span><span class="sxs-lookup"><span data-stu-id="e4165-119">Assigning an RBAC Role to a User</span></span>

<span data-ttu-id="e4165-120">RBAC の役割をユーザーに割り当てるには、そのユーザーを適切な Active Directory セキュリティグループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4165-120">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="e4165-121">たとえば、CsLocationAdministrator 役割をユーザーに割り当てるには、そのユーザーを CsLocationAdministrator グループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4165-121">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="e4165-122">ユーザーをセキュリティ グループに追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e4165-122">That can be done by carrying out the following procedure:</span></span>

<span data-ttu-id="e4165-123">**ユーザーをセキュリティ グループに割り当てるには**</span><span class="sxs-lookup"><span data-stu-id="e4165-123">**To assign a user to a security group**</span></span>

1.  <span data-ttu-id="e4165-124">Active Directory グループのメンバーシップを変更できるアクセス許可を持つアカウントを使用して、Active Directory ユーザーおよびコンピューターがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e4165-124">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>

2.  <span data-ttu-id="e4165-125">[**スタート**] をクリックし、[**すべてのプログラム**] をクリックし、[**管理ツール**] をクリックし、[**Active Directory ユーザーおよびコンピューター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4165-125">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="e4165-126">Active Directory ユーザーおよびコンピューターで、自分のドメインの名前を展開し、[**Users**] コンテナーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4165-126">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>

4.  <span data-ttu-id="e4165-127">セキュリティ グループの [**CsLocationAdministrator**] を右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4165-127">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>

5.  <span data-ttu-id="e4165-128">[**プロパティ**] ダイアログ ボックスの [**メンバー**] タブで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4165-128">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>

6.  <span data-ttu-id="e4165-129">[**ユーザー、コンピューター、連絡先、またはグループの選択**] ダイアログ ボックスの [**選択するオブジェクト名を入力してください**] ボックスにグループに追加するユーザーの名前または表示名 (たとえば、**Ken Myer**) を入力して [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4165-129">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, **Ken Myer**) in the **Enter the object names to select** box and then click **OK**.</span></span>

7.  <span data-ttu-id="e4165-130">[**プロパティ**] ダイアログ ボックスで [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4165-130">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="e4165-131">RBAC の役割が割り当てられていることを確認するには、ユーザーの SamAccountName (Active Directory ログオン名) をコマンドレットに渡して、 [Get-help Adminroleassignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4165-131">To verify that the RBAC role has been assigned, use the [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="e4165-132">たとえば、Lync Server 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e4165-132">For example, run this command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

