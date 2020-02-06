---
title: Skype for Business Server の管理制御を委任する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 5c295ed1233cb8a0900828cb1d1c074de1d0f16f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817273"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a><span data-ttu-id="67b27-102">Skype for Business Server の管理制御を委任する</span><span class="sxs-lookup"><span data-stu-id="67b27-102">Delegate administrative control of Skype for Business Server</span></span> 

<span data-ttu-id="67b27-103">Skype for Business Server では、管理タスクは、役割ベースのアクセス制御 (RBAC) 機能を使用してユーザーに委任されます。</span><span class="sxs-lookup"><span data-stu-id="67b27-103">In Skype for Business Server, administrative tasks are delegated to users by using the role-based access control (RBAC) feature.</span></span> <span data-ttu-id="67b27-104">Skype for Business Server をインストールすると、複数の RBAC の役割が作成されます。</span><span class="sxs-lookup"><span data-stu-id="67b27-104">When you install Skype for Business Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="67b27-105">これらの役割は、Active Directory ドメイン サービスのユニバーサル セキュリティ グループに対応します。</span><span class="sxs-lookup"><span data-stu-id="67b27-105">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="67b27-106">たとえば、RBAC の役割 CsHelpDesk は、Active Directory ドメインサービスの Users コンテナーに含まれる CsHelpDesk グループに対応しています。</span><span class="sxs-lookup"><span data-stu-id="67b27-106">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="67b27-107">さらに、各 RBAC の役割は、Skype for Business Server Windows PowerShell コマンドレットのセットと関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="67b27-107">In addition, each RBAC role is associated with a set of Skype for Business Server  Windows PowerShell cmdlets.</span></span> <span data-ttu-id="67b27-108">これらのコマンドレットは、特定の RBAC の役割が割り当てられたユーザーが実行できるタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="67b27-108">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="67b27-109">たとえば、CsHelpDesk role には、Lock と UnlockCsClientPin コマンドレットが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="67b27-109">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="67b27-110">つまり、CsHelpDesk の役割が割り当てられているユーザーは、ユーザーの PIN 番号のロックとロック解除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="67b27-110">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="67b27-111">ただし、CsHelpDesk の役割には、CsVoicePolicy コマンドレットが割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="67b27-111">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="67b27-112">つまり、CsHelpDesk role を割り当てられているユーザーは、新しいボイスポリシーを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="67b27-112">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="67b27-113">RBAC ロールに関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="67b27-113">Viewing information about RBAC roles</span></span>

<span data-ttu-id="67b27-114">次のコマンドを Skype for Business Server 管理シェルから実行して、RBAC ロールに関する基本的な情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="67b27-114">You can retrieve basic information about your RBAC roles by running the following command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRole`

<span data-ttu-id="67b27-115">RBAC の役割 (CsVoiceAdministrator など) の Id は、Active Directory ドメインサービスの Users コンテナーにあるセキュリティグループに直接マッピングされていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="67b27-115">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="67b27-116">ロールに割り当てられているコマンドレットの一覧を表示するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="67b27-116">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="67b27-117">RBAC の役割をユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="67b27-117">Assigning an RBAC role to a user</span></span>

<span data-ttu-id="67b27-118">RBAC の役割をユーザーに割り当てるには、適切な Active Directory セキュリティグループにそのユーザーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67b27-118">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="67b27-119">たとえば、CsLocationAdministrator の役割をユーザーに割り当てるには、そのユーザーを CsLocationAdministrator グループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67b27-119">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="67b27-120">そのためには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="67b27-120">That can be done by carrying out the following procedure:</span></span>

1. <span data-ttu-id="67b27-121">Active Directory グループのメンバーシップを変更する権限を持つアカウントを使用して、Active Directory ユーザーとコンピューターがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="67b27-121">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>
2. <span data-ttu-id="67b27-122">[**スタート**] をクリックし、[**すべてのプログラム**] をクリックし、[**管理ツール**] をクリックして、[ **Active Directory ユーザーとコンピューター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67b27-122">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
3. <span data-ttu-id="67b27-123">Active Directory ユーザーとコンピューターで、ドメインの名前を展開し、[**ユーザー** ] コンテナーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="67b27-123">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>
4. <span data-ttu-id="67b27-124">セキュリティグループ**Cslocationadministrator 者**を右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67b27-124">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>
5. <span data-ttu-id="67b27-125">[**プロパティ**] ダイアログボックスの [**メンバー** ] タブで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67b27-125">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>
6. <span data-ttu-id="67b27-126">**[ユーザー、コンピューター、連絡先、またはグループの選択**] ダイアログボックスで、 **[選択するオブジェクト名を入力**してください] ボックスに、グループに追加するユーザー名またはユーザー名 (Ken Myer など) を入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67b27-126">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, Ken Myer) in the **Enter the object names to select** box, and then click **OK**.</span></span>
7. <span data-ttu-id="67b27-127">[**プロパティ**] ダイアログボックスで、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67b27-127">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="67b27-128">RBAC の役割が割り当てられていることを確認するには、ユーザーの "SamAccountName (Active Directory のログオン名)" というコマンドレットを渡して、Csadminadminroleassignment コマンドレットを使います。</span><span class="sxs-lookup"><span data-stu-id="67b27-128">To verify that the RBAC role has been assigned, use the Get-CsAdminRoleAssignment cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="67b27-129">たとえば、次のコマンドを Skype for Business Server 管理シェル内から実行します。</span><span class="sxs-lookup"><span data-stu-id="67b27-129">For example, run this command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
