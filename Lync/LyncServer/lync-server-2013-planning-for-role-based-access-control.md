---
title: 'Lync Server 2013: 役割ベースのアクセス制御の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1771eb906685294e588e0c67b1fa8fb1f67a8b6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a><span data-ttu-id="bc709-102">Lync Server 2013 での役割ベースのアクセス制御の計画</span><span class="sxs-lookup"><span data-stu-id="bc709-102">Planning for role-based access control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc709-103">_**最終更新日:** 2015-01-27_</span><span class="sxs-lookup"><span data-stu-id="bc709-103">_**Topic Last Modified:** 2015-01-27_</span></span>

<span data-ttu-id="bc709-104">セキュリティの高い標準を維持しながら、管理タスクの委任を可能にするために、Lync Server 2013 は役割ベースのアクセス制御 (RBAC) を提供しています。</span><span class="sxs-lookup"><span data-stu-id="bc709-104">To enable you to delegate administrative tasks while maintaining high standards for security, Lync Server 2013 offers role-based access control (RBAC).</span></span> <span data-ttu-id="bc709-105">RBAC では、管理者権限が付与され、管理者ロールにユーザーが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="bc709-105">With RBAC, administrative privilege is granted by assigning users to administrative roles.</span></span> <span data-ttu-id="bc709-106">Lync Server 2013 には、豊富な組み込みの管理者ロールが用意されています。また、新しいロールを作成して、新しい役割ごとにコマンドレットのカスタムリストを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="bc709-106">Lync Server 2013 includes a rich set of built-in administrative roles, and also enables you to create new roles and specify a custom list of cmdlets for each new role.</span></span> <span data-ttu-id="bc709-107">また、定義済み RBAC 役割およびカスタム RBAC 役割の許可されたタスクに、コマンドレットのスクリプトを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="bc709-107">You can also add scripts of cmdlets to the allowed tasks of both predefined and custom RBAC roles.</span></span>

<div>

## <a name="better-server-security-and-centralization"></a><span data-ttu-id="bc709-108">サーバーのセキュリティと集中化の向上</span><span class="sxs-lookup"><span data-stu-id="bc709-108">Better Server Security and Centralization</span></span>

<span data-ttu-id="bc709-109">RBAC では、アクセスと承認はユーザーの Lync Server の役割に基づいています。</span><span class="sxs-lookup"><span data-stu-id="bc709-109">With RBAC, access and authorization is based precisely on a user’s Lync Server role.</span></span> <span data-ttu-id="bc709-110">これにより、"最低限の権限" というセキュリティ慣行を使用できるようになり、管理者とユーザーには、その職務に必要な権利のみが付与されます。</span><span class="sxs-lookup"><span data-stu-id="bc709-110">This enables use of the security practice of "least privilege," granting administrators and users only the rights that are necessary for their job.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bc709-111">RBAC の制限は、Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、リモートで作業している管理者に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="bc709-111">RBAC restrictions work only on administrators working remotely, using either the Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="bc709-112">Lync Server を実行しているサーバーに座っているユーザーは、RBAC によって制限されません。</span><span class="sxs-lookup"><span data-stu-id="bc709-112">A user sitting at a server running Lync Server is not restricted by RBAC.</span></span> <span data-ttu-id="bc709-113">したがって、Lync Server の物理的なセキュリティは、RBAC の制限を維持することが重要です。</span><span class="sxs-lookup"><span data-stu-id="bc709-113">Therefore, physical security of your Lync Server is important to preserve RBAC restrictions.</span></span>



</div>

</div>

<div>

## <a name="roles-and-scope"></a><span data-ttu-id="bc709-114">役割と範囲</span><span class="sxs-lookup"><span data-stu-id="bc709-114">Roles and Scope</span></span>

<span data-ttu-id="bc709-115">RBAC では、特定の種類の管理者または技術者のために役立つように設計されたコマンドレットのリストを使用する*役割*が有効になります。</span><span class="sxs-lookup"><span data-stu-id="bc709-115">In RBAC, a *role* is enabled to use a list of cmdlets, designed to be useful for a certain type of administrator or technician.</span></span> <span data-ttu-id="bc709-116">*スコープ*とは、役割で定義されているコマンドレットで操作できる一連のオブジェクトのことです。</span><span class="sxs-lookup"><span data-stu-id="bc709-116">A *scope* is the set of objects which the cmdlets defined in a role can operate on.</span></span> <span data-ttu-id="bc709-117">範囲に影響を与えるオブジェクトは、ユーザーアカウント (組織単位でグループ化) または (サイトごとにグループ化された) いずれかにすることができます。</span><span class="sxs-lookup"><span data-stu-id="bc709-117">The objects that scope affects can be either user accounts (grouped by organizational unit) or servers (grouped by site).</span></span>

<span data-ttu-id="bc709-118">次の表に、Lync Server で定義されている役割と、各タスクの種類の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="bc709-118">The following table lists the predefined roles in Lync Server, and gives a general overview of the types of tasks each can do.</span></span> <span data-ttu-id="bc709-119">4番目の列には、各 Lync Server の役割に類似した Microsoft Exchange Server の役割 (存在する場合) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc709-119">The fourth column shows the similar Microsoft Exchange Server role for each Lync Server role, if there is one.</span></span>

### <a name="predefined-administrative-roles"></a><span data-ttu-id="bc709-120">定義済みの管理者ロール</span><span class="sxs-lookup"><span data-stu-id="bc709-120">Predefined Administrative Roles</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc709-121">ロール</span><span class="sxs-lookup"><span data-stu-id="bc709-121">Role</span></span></th>
<th><span data-ttu-id="bc709-122">許可されたタスク</span><span class="sxs-lookup"><span data-stu-id="bc709-122">Tasks allowed</span></span></th>
<th><span data-ttu-id="bc709-123">基になる Active Directory グループ</span><span class="sxs-lookup"><span data-stu-id="bc709-123">Underlying Active Directory group</span></span></th>
<th><span data-ttu-id="bc709-124">同等の交換</span><span class="sxs-lookup"><span data-stu-id="bc709-124">Exchange equivalent</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc709-125">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc709-125">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc709-126">すべての管理タスクを実行し、ロールの作成やロールへのユーザーの割り当てなどのすべての設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="bc709-126">Can perform all administrative tasks and modify all settings, including creating roles and assigning users to roles.</span></span> <span data-ttu-id="bc709-127">新しいサイト、プール、およびサービスを追加して展開を展開できます。</span><span class="sxs-lookup"><span data-stu-id="bc709-127">Can expand a deployment by adding new sites, pools, and services.</span></span></p></td>
<td><p><span data-ttu-id="bc709-128">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc709-128">CSAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc709-129">組織管理</span><span class="sxs-lookup"><span data-stu-id="bc709-129">Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc709-130">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc709-130">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc709-131">Lync Server のユーザーを有効または無効にしたり、ユーザーを移動したり、既存のポリシーをユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="bc709-131">Can enable and disable users for Lync Server, move users and assign existing policies to users.</span></span> <span data-ttu-id="bc709-132">ポリシーを変更できません。</span><span class="sxs-lookup"><span data-stu-id="bc709-132">Cannot modify policies.</span></span></p></td>
<td><p><span data-ttu-id="bc709-133">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc709-133">CSUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc709-134">メールの宛先</span><span class="sxs-lookup"><span data-stu-id="bc709-134">Mail Recipients</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc709-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc709-135">CsVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc709-136">音声関連の設定とポリシーの作成、構成、管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bc709-136">Can create, configure, and manage voice-related settings and policies.</span></span></p></td>
<td><p><span data-ttu-id="bc709-137">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc709-137">CSVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc709-138">該当しない</span><span class="sxs-lookup"><span data-stu-id="bc709-138">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc709-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc709-139">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc709-140">サーバーとサービスの管理、監視、トラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bc709-140">Can manage, monitor, and troubleshoot servers and services.</span></span> <span data-ttu-id="bc709-141">サーバーへの新しい接続の禁止、サービスの停止と開始、ソフトウェアの更新プログラムの適用を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bc709-141">Can prevent new connections to servers, stop and start services, and apply software updates.</span></span> <span data-ttu-id="bc709-142">グローバル構成の影響を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="bc709-142">Cannot make changes with global configuration impact.</span></span></p></td>
<td><p><span data-ttu-id="bc709-143">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc709-143">CSServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc709-144">サーバー管理</span><span class="sxs-lookup"><span data-stu-id="bc709-144">Server Management</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc709-145">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc709-145">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc709-146">展開の正常性を監視するために、ユーザーやサーバーの情報などの展開を表示できます。</span><span class="sxs-lookup"><span data-stu-id="bc709-146">Can view the deployment, including user and server information, in order to monitor deployment health.</span></span></p></td>
<td><p><span data-ttu-id="bc709-147">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc709-147">CSViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc709-148">表示のみの組織管理</span><span class="sxs-lookup"><span data-stu-id="bc709-148">View-Only Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc709-149">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="bc709-149">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="bc709-150">ユーザーのプロパティやポリシーなどの展開を表示できます。</span><span class="sxs-lookup"><span data-stu-id="bc709-150">Can view the deployment, including user's properties and policies.</span></span> <span data-ttu-id="bc709-151">特定のトラブルシューティングタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="bc709-151">Can run specific troubleshooting tasks.</span></span> <span data-ttu-id="bc709-152">ユーザーのプロパティやポリシー、サーバーの構成、またはサービスを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="bc709-152">Cannot change user properties or policies, server configuration, or services.</span></span></p></td>
<td><p><span data-ttu-id="bc709-153">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="bc709-153">CSHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="bc709-154">ヘルプデスク</span><span class="sxs-lookup"><span data-stu-id="bc709-154">HelpDesk</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc709-155">CsArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc709-155">CsArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc709-156">アーカイブの構成とポリシーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="bc709-156">Can modify archiving configuration and policies.</span></span></p></td>
<td><p><span data-ttu-id="bc709-157">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc709-157">CSArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc709-158">保持管理、法的保持</span><span class="sxs-lookup"><span data-stu-id="bc709-158">Retention Management, Legal Hold</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc709-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc709-159">CsResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc709-160">サイト内の応答グループアプリケーションの構成を管理できます。</span><span class="sxs-lookup"><span data-stu-id="bc709-160">Can manage the configuration of the Response Group application within a site.</span></span></p></td>
<td><p><span data-ttu-id="bc709-161">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc709-161">CSResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc709-162">該当しない</span><span class="sxs-lookup"><span data-stu-id="bc709-162">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc709-163">CsLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc709-163">CsLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc709-164">9-1-1 (E9) の管理を強化するための最小レベルの権限 (E9 の場所とネットワーク識別子の作成、および相互の関連付けを含む)。</span><span class="sxs-lookup"><span data-stu-id="bc709-164">Lowest level of rights for Enhanced 9-1-1 (E9-1-1) management, including creating E9-1-1 locations and network identifiers, and associating these with each other.</span></span> <span data-ttu-id="bc709-165">この役割は、常にグローバルスコープに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="bc709-165">This role is always assigned with a global scope.</span></span></p></td>
<td><p><span data-ttu-id="bc709-166">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc709-166">CSLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc709-167">該当しない</span><span class="sxs-lookup"><span data-stu-id="bc709-167">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc709-168">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="bc709-168">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="bc709-169">特定の応答グループを管理できます。</span><span class="sxs-lookup"><span data-stu-id="bc709-169">Can manage specific response groups.</span></span></p></td>
<td><p><span data-ttu-id="bc709-170">CSResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="bc709-170">CSResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="bc709-171">該当しない</span><span class="sxs-lookup"><span data-stu-id="bc709-171">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc709-172">CsPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc709-172">CsPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc709-173">常設チャット機能と特定の常設チャットルームを管理できます。</span><span class="sxs-lookup"><span data-stu-id="bc709-173">Can manage the Persistent Chat feature and specific Persistent Chat rooms.</span></span></p></td>
<td><p><span data-ttu-id="bc709-174">CSPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc709-174">CSPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc709-175">該当しない</span><span class="sxs-lookup"><span data-stu-id="bc709-175">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bc709-176">Lync Server に組み込まれているすべての定義済みロールにはグローバルスコープがあります。</span><span class="sxs-lookup"><span data-stu-id="bc709-176">All predefined roles shipped in Lync Server have a global scope.</span></span> <span data-ttu-id="bc709-177">最低限の権限適用方法を実行するには、限定されたサーバーまたはユーザーのセットのみを管理する場合は、グローバル範囲の役割にユーザーを割り当てないでください。</span><span class="sxs-lookup"><span data-stu-id="bc709-177">To follow least privilege practices, you should not assign users to roles with global scope if they are going to administer only a limited set of servers or users.</span></span> <span data-ttu-id="bc709-178">これを実現するために、既存のロールに基づいているが、スコープが制限されているロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bc709-178">To accomplish this, you can create roles which are based on an existing role, but with a more limited scope.</span></span>

<div>

## <a name="creating-a-scoped-role"></a><span data-ttu-id="bc709-179">スコープ指定された役割の作成</span><span class="sxs-lookup"><span data-stu-id="bc709-179">Creating a Scoped Role</span></span>

<span data-ttu-id="bc709-180">制限されたスコープ (スコープ指定された役割) を持つ役割を作成する場合は、スコープを指定し、基になる既存の役割と、役割を割り当てられる Active Directory グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="bc709-180">When you create a role with limited scope (a scoped role), you specify the scope, along with the existing role it is based on and the Active Directory group to be assigned the role.</span></span> <span data-ttu-id="bc709-181">指定した Active Directory グループは、既に作成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc709-181">The Active Directory group you specify must already be created.</span></span> <span data-ttu-id="bc709-182">次のコマンドレットは、事前に定義されている管理者ロールの1つであるという権限を持ち、スコープが制限されている役割を作成する例です。</span><span class="sxs-lookup"><span data-stu-id="bc709-182">The following cmdlet is an example of a creating a role which has the privileges of one of the pre-defined administrative roles, but with limited scope.</span></span> <span data-ttu-id="bc709-183">という`Site01 Server Administrators`新しい役割が作成されます。</span><span class="sxs-lookup"><span data-stu-id="bc709-183">It creates a new role called `Site01 Server Administrators`.</span></span> <span data-ttu-id="bc709-184">この役割には、定義済みの CsServerAdministrator ロールの権限がありますが、Site01 サイトにあるサーバーに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="bc709-184">The role has the abilities of the predefined CsServerAdministrator role, but only for the servers located in the Site01 site.</span></span> <span data-ttu-id="bc709-185">このコマンドレットが動作するためには、Site01 サイトが既に定義されており`Site01 Server Administrators` 、という名前のユニバーサルセキュリティグループが既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc709-185">For this cmdlet to work, the Site01 site must already be defined, and a universal security group named `Site01 Server Administrators` must already exist.</span></span>

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

<span data-ttu-id="bc709-186">このコマンドレットを実行すると、 `Site01 Server Administrators`グループのメンバーになっているすべてのユーザーに、Site01 のサーバーのサーバー管理者権限が与えられます。</span><span class="sxs-lookup"><span data-stu-id="bc709-186">After this cmdlet runs, all users who are members of the `Site01 Server Administrators` group will have server administrator privileges for the servers in Site01.</span></span> <span data-ttu-id="bc709-187">さらに、このユニバーサルセキュリティグループに後で追加されたすべてのユーザーも、この役割の権限を取得します。</span><span class="sxs-lookup"><span data-stu-id="bc709-187">Additionally, any users who are later added to this universal security group also gain the privileges of this role.</span></span> <span data-ttu-id="bc709-188">役割自体と、それに割り当てられているユニバーサルセキュリティグループの両方が呼び出さ`Site01 Server Administrators`れます。</span><span class="sxs-lookup"><span data-stu-id="bc709-188">Note that both the role itself, and the universal security group it is assigned to are called `Site01 Server Administrators`.</span></span>

<span data-ttu-id="bc709-189">次の例では、サーバースコープの代わりにユーザーのスコープを制限しています。</span><span class="sxs-lookup"><span data-stu-id="bc709-189">The following example limits user scope instead of server scope.</span></span> <span data-ttu-id="bc709-190">営業組織単位`Sales Users Administrator`のユーザーアカウントを管理するための役割を作成します。</span><span class="sxs-lookup"><span data-stu-id="bc709-190">It creates a `Sales Users Administrator` role to administer the user accounts in the Sales organizational unit.</span></span> <span data-ttu-id="bc709-191">このコマンドレットが機能するためには、Salesて管理者のユニバーサルセキュリティグループが既に作成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc709-191">The SalesUsersAdministrator universal security group must already be created for this cmdlet to work.</span></span>

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a><span data-ttu-id="bc709-192">新しい役割の作成</span><span class="sxs-lookup"><span data-stu-id="bc709-192">Creating a New Role</span></span>

<span data-ttu-id="bc709-193">定義済みのロールのいずれにも含まれていない一連のコマンドレット、または一連のスクリプトまたはモジュールにアクセスできる役割を作成するには、あらかじめ定義されたいずれかのロールをテンプレートとして使用します。</span><span class="sxs-lookup"><span data-stu-id="bc709-193">To create a role that has access to a set of cmdlets not in one of the predefined roles, or to a set of scripts or modules, you again start by using one of the predefined roles as a template.</span></span> <span data-ttu-id="bc709-194">ロールを実行できるスクリプトとモジュールは、次の場所に格納されている必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bc709-194">Note that scripts and modules that roles are to be able to run must be stored in the following locations:</span></span>

  - <span data-ttu-id="bc709-195">Lync モジュールのパス (既定では\\C: Program files\\の共通ファイル\\Microsoft lync Server 2013\\モジュール\\Lync)</span><span class="sxs-lookup"><span data-stu-id="bc709-195">The Lync module path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\Lync</span></span>

  - <span data-ttu-id="bc709-196">ユーザースクリプト\\パス (既定では C: Program Files\\Common files\\Microsoft Lync Server 2013\\adminscripts)</span><span class="sxs-lookup"><span data-stu-id="bc709-196">The user script path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\AdminScripts</span></span>

<span data-ttu-id="bc709-197">新しい役割を作成するには、**新しい-CsAdminRole**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bc709-197">To make a new role, you use the **New-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="bc709-198">**新しい CsAdminRole**を実行する前に、この役割に関連付けられる、基になるユニバーサルセキュリティグループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc709-198">Before running **New-CsAdminRole**, you must first create the underlying universal security group that will be associated with this role.</span></span>

<span data-ttu-id="bc709-199">次のコマンドレットは、新しい役割の作成例として機能します。</span><span class="sxs-lookup"><span data-stu-id="bc709-199">The following cmdlets serve as an example of a creating a new role.</span></span> <span data-ttu-id="bc709-200">これにより、という`MyHelpDeskScriptRole`新しい役割の種類が作成されます。</span><span class="sxs-lookup"><span data-stu-id="bc709-200">They create a new role type called `MyHelpDeskScriptRole`.</span></span> <span data-ttu-id="bc709-201">新しい役割には、定義済みの CsHelpDesk ロールの機能があり、"testscript" という名前のスクリプトでさらに関数を実行できます。</span><span class="sxs-lookup"><span data-stu-id="bc709-201">The new role has the abilities of the predefined CsHelpDesk role, and can additionally run the functions in a script named “testscript”.</span></span>

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

<span data-ttu-id="bc709-202">このコマンドレットが動作するためには、まずユニバーサルセキュリティグループ Myhelpデスク Scriptrole を作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc709-202">For this cmdlet to work, you must have first created the universal security group MyHelpDeskScriptRole.</span></span>

<span data-ttu-id="bc709-203">このコマンドレットを実行した後、このロールにユーザーを直接割り当てる (その場合はグローバルスコープを持つ) か、このドキュメントの「スコープロールの作成」で説明したように、このロールに基づいてスコープ指定された役割を作成できます。</span><span class="sxs-lookup"><span data-stu-id="bc709-203">After this cmdlet runs, you can assign users directly to this role (in which case they have global scope), or create a scoped role based on this role, as explained in Creating a Scoped Role, previously in this document.</span></span>

</div>

<div>

## <a name="assigning-roles-to-users"></a><span data-ttu-id="bc709-204">ロールをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="bc709-204">Assigning Roles to Users</span></span>

<span data-ttu-id="bc709-205">各 Lync Server の役割は、基になる Active Directory ユニバーサルセキュリティグループに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="bc709-205">Each Lync Server role is associated with an underlying Active Directory universal security group.</span></span> <span data-ttu-id="bc709-206">基になるグループに追加したユーザーは、その役割の能力を獲得できます。</span><span class="sxs-lookup"><span data-stu-id="bc709-206">Any users who you add to the underlying group gain the abilities of that role.</span></span>

<span data-ttu-id="bc709-207">前のセクションの例では、新しい役割を作成し、既存のユニバーサルセキュリティグループを新しい役割に割り当てています。</span><span class="sxs-lookup"><span data-stu-id="bc709-207">The examples in the preceding sections both created a new role and assigned an existing universal security group to the new role.</span></span> <span data-ttu-id="bc709-208">既存の役割を1人または複数のユーザーに割り当てるには、その役割に関連付けられたグループにそれらのユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="bc709-208">To assign an existing role to one or more users, add those users to the group associated with the role.</span></span> <span data-ttu-id="bc709-209">これらのグループには、個々のユーザーとユニバーサルセキュリティグループの両方を追加できます。</span><span class="sxs-lookup"><span data-stu-id="bc709-209">You can add both individual users and universal security groups to these groups.</span></span>

<span data-ttu-id="bc709-210">たとえば、 **Csadministrator**の役割は、Active Directory の**CS 管理者**のユニバーサルセキュリティグループに自動的に付与されます。</span><span class="sxs-lookup"><span data-stu-id="bc709-210">For example, the **CsAdministrator** role is automatically granted to the **CS Administrators** universal security group in Active Directory.</span></span> <span data-ttu-id="bc709-211">このユニバーサルセキュリティグループは、Lync Server を展開するときに Active Directory で作成されます。</span><span class="sxs-lookup"><span data-stu-id="bc709-211">This universal security group is created in Active Directory when you deploy Lync Server.</span></span> <span data-ttu-id="bc709-212">ユーザーまたはグループにこの権限を付与するには、 **CS 管理者**グループに追加するだけです。</span><span class="sxs-lookup"><span data-stu-id="bc709-212">To grant a user or group this privilege, you can simply add them to the **CS Administrators** group.</span></span>

<span data-ttu-id="bc709-213">ユーザーには、各役割に対応する、基になる Active Directory グループに追加することで、複数の RBAC ロールを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="bc709-213">A user can be given multiple RBAC roles by being added to the underlying Active Directory groups that correspond to each role.</span></span>

<span data-ttu-id="bc709-214">ロールを作成すると、基になる Active Directory グループに後で追加されたユーザーにその役割の機能が与えられることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bc709-214">Note that when you create a role, users who are later added to the underlying Active Directory group gain the abilities of that role.</span></span>

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a><span data-ttu-id="bc709-215">役割の権限を変更する</span><span class="sxs-lookup"><span data-stu-id="bc709-215">Modifying the Abilities of a Role</span></span>

<span data-ttu-id="bc709-216">役割が実行できるコマンドレットとスクリプトの一覧は変更できます。</span><span class="sxs-lookup"><span data-stu-id="bc709-216">You can modify the list of cmdlets and scripts that a role can run.</span></span> <span data-ttu-id="bc709-217">カスタムロールで実行できるコマンドレットとスクリプトの両方を変更することはできますが、定義済みのロールのスクリプトのみを変更できます。</span><span class="sxs-lookup"><span data-stu-id="bc709-217">You can modify both the cmdlets and scripts that custom roles can run, but you can modify only the scripts for predefined roles.</span></span> <span data-ttu-id="bc709-218">入力する各コマンドレットでは、コマンドレットまたはスクリプトの追加、削除、置換を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bc709-218">Each cmdlet you type can add, remove, or replace cmdlets or scripts.</span></span>

<span data-ttu-id="bc709-219">役割を変更するには、 **Set-CsAdminRole**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bc709-219">To modify a role, use the **Set-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="bc709-220">次のコマンドレットは、役割から1つのスクリプトを削除します。</span><span class="sxs-lookup"><span data-stu-id="bc709-220">The following cmdlet removes one script from the role.</span></span>

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a><span data-ttu-id="bc709-221">RBAC の計画</span><span class="sxs-lookup"><span data-stu-id="bc709-221">Planning for RBAC</span></span>

<span data-ttu-id="bc709-222">Lync Server の展開にどのような管理権限を付与するかについては、どのようなタスクを実行する必要があるかを正確に考慮し、その職務に必要な最低限の権限と範囲の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc709-222">For each person who is to be given any kind of administrative rights for your Lync Server deployment, consider exactly which tasks they need to perform, then assign them to roles with the least privilege and scope necessary for their job.</span></span> <span data-ttu-id="bc709-223">必要に応じて、[ **Set-CsAdminRole** ] コマンドレットを使用して、このユーザーのタスクに必要なコマンドレットのみを含む新しい役割を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="bc709-223">If necessary, you can use the **Set-CsAdminRole** cmdlet to create a new role with only the cmdlets necessary for this person’s tasks.</span></span>

<span data-ttu-id="bc709-224">CsAdministrator ロールを持っているユーザーは、CsAdministrator に基づくロールを含むすべての種類の役割を作成し、ユーザーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="bc709-224">Users who have the CsAdministrator role can create all types of roles, including roles based on CsAdministrator, and assign users to them.</span></span> <span data-ttu-id="bc709-225">ベストプラクティスとして、CsAdministrator の役割を、非常に少数の信頼できるユーザーに割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bc709-225">The best practice is to assign the CsAdministrator role to a very small set of trusted users.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

