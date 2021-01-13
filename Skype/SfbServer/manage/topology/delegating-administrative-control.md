---
title: Skype for Business Server の管理制御を委任する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: eb78fc7e0f831bae1c5dd6e207791e27aa4c68d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832797"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a><span data-ttu-id="eb40c-102">Skype for Business Server の管理制御を委任する</span><span class="sxs-lookup"><span data-stu-id="eb40c-102">Delegate administrative control of Skype for Business Server</span></span> 

<span data-ttu-id="eb40c-103">Skype for Business Server では、管理タスクは役割ベースのアクセス制御 (RBAC) 機能を使用してユーザーに委任されます。</span><span class="sxs-lookup"><span data-stu-id="eb40c-103">In Skype for Business Server, administrative tasks are delegated to users by using the role-based access control (RBAC) feature.</span></span> <span data-ttu-id="eb40c-104">Skype for Business Server をインストールすると、多くの RBAC の役割が作成されます。</span><span class="sxs-lookup"><span data-stu-id="eb40c-104">When you install Skype for Business Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="eb40c-105">これらの役割は、Active Directory ドメイン サービスのユニバーサル セキュリティ グループに対応しています。</span><span class="sxs-lookup"><span data-stu-id="eb40c-105">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="eb40c-106">たとえば、RBAC の役割 CsHelpDesk は、Active Directory ドメイン サービスの Users コンテナーにある CsHelpDesk グループに対応します。</span><span class="sxs-lookup"><span data-stu-id="eb40c-106">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="eb40c-107">さらに、各 RBAC の役割は、一連の Skype for Business Server Windows PowerShellされます。</span><span class="sxs-lookup"><span data-stu-id="eb40c-107">In addition, each RBAC role is associated with a set of Skype for Business Server  Windows PowerShell cmdlets.</span></span> <span data-ttu-id="eb40c-108">これらのコマンドレットは、特定の RBAC の役割が割り当てられているユーザーが実行できるタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="eb40c-108">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="eb40c-109">たとえば、CsHelpDesk の役割には、Lock-CsClientPin UnlockCsClientPin コマンドレットが割り当てされています。</span><span class="sxs-lookup"><span data-stu-id="eb40c-109">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="eb40c-110">つまり、CsHelpDesk の役割が割り当てられているユーザーは、ユーザーの PIN 番号をロックおよびロック解除できます。</span><span class="sxs-lookup"><span data-stu-id="eb40c-110">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="eb40c-111">ただし、CsHelpDesk の役割にこのコマンドレットが割りNew-CsVoicePolicyされていない。</span><span class="sxs-lookup"><span data-stu-id="eb40c-111">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="eb40c-112">つまり、CsHelpDesk の役割が割り当てられているユーザーは、新しい音声ポリシーを作成できません。</span><span class="sxs-lookup"><span data-stu-id="eb40c-112">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="eb40c-113">RBAC の役割に関する情報の表示</span><span class="sxs-lookup"><span data-stu-id="eb40c-113">Viewing information about RBAC roles</span></span>

<span data-ttu-id="eb40c-114">Rbac の役割に関する基本情報を取得するには、Skype for Business Server 管理シェルから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="eb40c-114">You can retrieve basic information about your RBAC roles by running the following command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRole`

<span data-ttu-id="eb40c-115">RBAC の役割の IDENTITY (CsVoiceAdministrator など) は、Active Directory ドメイン サービスの Users コンテナーにあるセキュリティ グループに直接マッピングされます。</span><span class="sxs-lookup"><span data-stu-id="eb40c-115">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="eb40c-116">役割に割り当てられているコマンドレットのリストを表示するには、次のようなコマンドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="eb40c-116">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="eb40c-117">RBAC の役割をユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="eb40c-117">Assigning an RBAC role to a user</span></span>

<span data-ttu-id="eb40c-118">RBAC の役割をユーザーに割り当てるには、そのユーザーを適切な Active Directory セキュリティ グループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb40c-118">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="eb40c-119">たとえば、CsLocationAdministrator 役割をユーザーに割り当てるには、そのユーザーを CsLocationAdministrator グループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb40c-119">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="eb40c-120">ユーザーをセキュリティ グループに追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="eb40c-120">That can be done by carrying out the following procedure:</span></span>

1. <span data-ttu-id="eb40c-121">Active Directory グループのメンバーシップを変更できるアクセス許可を持つアカウントを使用して、Active Directory ユーザーおよびコンピューターがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="eb40c-121">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>
2. <span data-ttu-id="eb40c-122">[**スタート**] をクリックし、[**すべてのプログラム**] をクリックし、[**管理ツール**] をクリックし、[**Active Directory ユーザーおよびコンピューター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb40c-122">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
3. <span data-ttu-id="eb40c-123">Active Directory ユーザーおよびコンピューターで、自分のドメインの名前を展開し、[**Users**] コンテナーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb40c-123">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>
4. <span data-ttu-id="eb40c-124">セキュリティ グループの [**CsLocationAdministrator**] を右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb40c-124">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>
5. <span data-ttu-id="eb40c-125">[**プロパティ**] ダイアログ ボックスの [**メンバー**] タブで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb40c-125">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>
6. <span data-ttu-id="eb40c-126">[ユーザー  、コンピューター、連絡先、またはグループの選択] ダイアログ ボックスで、グループに追加するユーザーのユーザー名または表示名 (Ken Myer など) を[選択するオブジェクト名を入力してください] ボックスに入力し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb40c-126">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, Ken Myer) in the **Enter the object names to select** box, and then click **OK**.</span></span>
7. <span data-ttu-id="eb40c-127">[**プロパティ**] ダイアログ ボックスで [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb40c-127">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="eb40c-128">RBAC の役割が割り当てられていることを確認するには、Get-CsAdminRoleAssignment コマンドレットを使用して、ユーザーの SamAccountName (Active Directory ログオン名) コマンドレットを渡します。</span><span class="sxs-lookup"><span data-stu-id="eb40c-128">To verify that the RBAC role has been assigned, use the Get-CsAdminRoleAssignment cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="eb40c-129">たとえば、Skype for Business Server 管理シェル内から次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="eb40c-129">For example, run this command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
