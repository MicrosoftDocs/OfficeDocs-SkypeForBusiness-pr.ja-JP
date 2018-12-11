---
title: ビジネス サーバーの Skype の管理制御を委任します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 6dbd254a96e4ffe961edc1a7d601870eb38b35db
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222899"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a><span data-ttu-id="9a9b3-102">ビジネス サーバーの Skype の管理制御を委任します。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-102">Delegate administrative control of Skype for Business Server</span></span> 

<span data-ttu-id="9a9b3-103">ビジネス サーバーの Skype は、管理タスクは、役割ベースのアクセス制御 (RBAC) 機能を使用してユーザーに委任します。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-103">In Skype for Business Server, administrative tasks are delegated to users by using the role-based access control (RBAC) feature.</span></span> <span data-ttu-id="9a9b3-104">ビジネス サーバーの Skype をインストールするときの RBAC の役割の多くが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-104">When you install Skype for Business Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="9a9b3-105">これらの役割は、Active Directory ドメイン サービスのユニバーサル セキュリティ グループに対応します。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-105">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="9a9b3-106">などの CsHelpDesk の RBAC の役割は、Active Directory ドメイン サービス内の Users コンテナー内の CsHelpDesk グループに対応します。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-106">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="9a9b3-107">さらに、各 RBAC の役割は、Skype のビジネス サーバーの Windows PowerShell コマンドレットのセットに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-107">In addition, each RBAC role is associated with a set of Skype for Business Server  Windows PowerShell cmdlets.</span></span> <span data-ttu-id="9a9b3-108">これらのコマンドレットは、特定の RBAC の役割が割り当てられているユーザーによって実行できるタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-108">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="9a9b3-109">などのロック ・ CsClientPin、UnlockCsClientPin コマンドレットは、CsHelpDesk の役割を割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-109">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="9a9b3-110">つまり、CsHelpDesk の役割が割り当てられているユーザーをロックし、ユーザーの暗証番号 (pin) 番号のロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-110">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="9a9b3-111">ただし、CsHelpDesk の役割では新規 CsVoicePolicy コマンドレットを割り当てられていませんが。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-111">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="9a9b3-112">つまり、CsHelpDesk の役割が割り当てられているユーザーが新しい音声ポリシーを作成できません。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-112">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="9a9b3-113">RBAC の役割に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-113">Viewing information about RBAC roles</span></span>

<span data-ttu-id="9a9b3-114">ビジネス サーバー管理シェルには、Skype 内で次のコマンドを実行することによって、RBAC の役割に関する基本的な情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-114">You can retrieve basic information about your RBAC roles by running the following command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRole`

<span data-ttu-id="9a9b3-115">RBAC の役割 (たとえば、CsVoiceAdministrator) の Id は、Active Directory ドメイン サービス内の Users コンテナーにセキュリティ グループに直接マッピングを持っていることに留意してください。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-115">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="9a9b3-116">ロールに割り当てられているコマンドレットの一覧を表示するのには次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-116">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="9a9b3-117">RBAC の役割をユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="9a9b3-117">Assigning an RBAC role to a user</span></span>

<span data-ttu-id="9a9b3-118">RBAC の役割をユーザーに割り当てるには、適切な Active Directory セキュリティ グループにそのユーザーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-118">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="9a9b3-119">たとえば、CsLocationAdministrator ロールをユーザーに割り当てるには、CsLocationAdministrator グループにそのユーザーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-119">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="9a9b3-120">行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-120">That can be done by carrying out the following procedure:</span></span>

1. <span data-ttu-id="9a9b3-121">アクセス許可を持つアカウントを使用して、Active Directory グループのメンバーシップを変更、Active Directory ユーザーとコンピューターがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-121">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>
2. <span data-ttu-id="9a9b3-122">[**スタート**] ボタン**すべてのプログラム** **[管理ツール**] をクリックして、 **Active Directory ユーザーとコンピューター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-122">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
3. <span data-ttu-id="9a9b3-123">Active Directory ユーザーとコンピューターでは、コンピューターのドメイン名を展開を **[Users** ] コンテナーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-123">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>
4. <span data-ttu-id="9a9b3-124">**CsLocationAdministrator**、セキュリティ グループを右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-124">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>
5. <span data-ttu-id="9a9b3-125">**プロパティ**] ダイアログ ボックスの [**メンバー** ] タブで [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-125">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>
6. <span data-ttu-id="9a9b3-126">**[ユーザー、コンピューター、連絡先、またはグループ**] ダイアログ ボックスで、ユーザー名を入力またはグループ (たとえば、Ken Myer)**を選択するオブジェクト名を入力してください**] ボックスに追加するユーザーの名前を表示でし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-126">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, Ken Myer) in the **Enter the object names to select** box, and then click **OK**.</span></span>
7. <span data-ttu-id="9a9b3-127">**プロパティ**] ダイアログ ボックスで [ **OK**を] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-127">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="9a9b3-128">RBAC の役割が割り当てられていることを確認するには、Get CsAdminRoleAssignment コマンドレットは、ユーザーの SamAccountName (Active Directory のログオン名) をコマンドレットに渡すことを使用します。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-128">To verify that the RBAC role has been assigned, use the Get-CsAdminRoleAssignment cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="9a9b3-129">たとえば、ビジネス サーバー管理シェルには、Skype 内からは、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-129">For example, run this command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`