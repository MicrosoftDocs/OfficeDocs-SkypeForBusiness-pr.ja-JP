---
title: 'Lync Server 2013: 役割ベースのアクセス制御の計画'
description: 'Lync Server 2013: 役割ベースのアクセス制御の計画。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 971b3353694a1cdd53d88452717e6a9a360c6870
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549243"
---
# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a><span data-ttu-id="74cea-103">Lync Server 2013 での役割ベースのアクセス制御の計画</span><span class="sxs-lookup"><span data-stu-id="74cea-103">Planning for role-based access control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74cea-104">_**トピックの最終更新日:** 2015-01-27_</span><span class="sxs-lookup"><span data-stu-id="74cea-104">_**Topic Last Modified:** 2015-01-27_</span></span>

<span data-ttu-id="74cea-105">高水準のセキュリティを維持しながら管理タスクを委任できるようにするために、Lync Server 2013 は役割ベースのアクセス制御 (RBAC) を提供しています。</span><span class="sxs-lookup"><span data-stu-id="74cea-105">To enable you to delegate administrative tasks while maintaining high standards for security, Lync Server 2013 offers role-based access control (RBAC).</span></span> <span data-ttu-id="74cea-106">RBAC では、ユーザーを管理役割に割り当てることによって管理特権を付与します。</span><span class="sxs-lookup"><span data-stu-id="74cea-106">With RBAC, administrative privilege is granted by assigning users to administrative roles.</span></span> <span data-ttu-id="74cea-107">Lync Server 2013 には、組み込みの管理役割の豊富なセットが含まれており、新しい役割を作成し、新しい役割ごとにコマンドレットのカスタムリストを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="74cea-107">Lync Server 2013 includes a rich set of built-in administrative roles, and also enables you to create new roles and specify a custom list of cmdlets for each new role.</span></span> <span data-ttu-id="74cea-108">また、定義済み RBAC 役割およびカスタム RBAC 役割の許可されたタスクに、コマンドレットのスクリプトを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="74cea-108">You can also add scripts of cmdlets to the allowed tasks of both predefined and custom RBAC roles.</span></span>

<div>

## <a name="better-server-security-and-centralization"></a><span data-ttu-id="74cea-109">優れたサーバー セキュリティと集中管理</span><span class="sxs-lookup"><span data-stu-id="74cea-109">Better Server Security and Centralization</span></span>

<span data-ttu-id="74cea-110">RBAC を使用すると、アクセスと承認は、ユーザーの Lync Server の役割に正確に基づいています。</span><span class="sxs-lookup"><span data-stu-id="74cea-110">With RBAC, access and authorization is based precisely on a user’s Lync Server role.</span></span> <span data-ttu-id="74cea-111">これにより、管理者およびユーザーに各自の業務に必要な権限のみを付与するセキュリティ プラクティス ("最小限の特権") を利用できます。</span><span class="sxs-lookup"><span data-stu-id="74cea-111">This enables use of the security practice of "least privilege," granting administrators and users only the rights that are necessary for their job.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="74cea-112">RBAC 制限は、Lync Server コントロールパネルまたは Lync Server 管理シェルのいずれかを使用して、リモートで作業している管理者に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="74cea-112">RBAC restrictions work only on administrators working remotely, using either the Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="74cea-113">Lync Server を実行しているサーバーのユーザーは、RBAC によって制限されていません。</span><span class="sxs-lookup"><span data-stu-id="74cea-113">A user sitting at a server running Lync Server is not restricted by RBAC.</span></span> <span data-ttu-id="74cea-114">そのため、RBAC 制限を保持するには、Lync Server の物理的なセキュリティが重要です。</span><span class="sxs-lookup"><span data-stu-id="74cea-114">Therefore, physical security of your Lync Server is important to preserve RBAC restrictions.</span></span>



</div>

</div>

<div>

## <a name="roles-and-scope"></a><span data-ttu-id="74cea-115">役割とスコープ</span><span class="sxs-lookup"><span data-stu-id="74cea-115">Roles and Scope</span></span>

<span data-ttu-id="74cea-p104">RBAC において、ある役割\*\* に属するユーザーは、特定のタイプの管理者または技術者用に定義された一連のコマンドレットを使用できます。スコープ\*\* は、役割で定義されているコマンドレットで操作できる一連のオブジェクトです。スコープの影響を受けるオブジェクトは、ユーザー アカウント (組織単位でグループ化) またはサーバー (サイト単位でグループ化) のどちらかです。</span><span class="sxs-lookup"><span data-stu-id="74cea-p104">In RBAC, a *role* is enabled to use a list of cmdlets, designed to be useful for a certain type of administrator or technician. A *scope* is the set of objects which the cmdlets defined in a role can operate on. The objects that scope affects can be either user accounts (grouped by organizational unit) or servers (grouped by site).</span></span>

<span data-ttu-id="74cea-119">次の表に、Lync Server で定義されている役割の一覧と、各タスクの種類について一般的な概要を示します。</span><span class="sxs-lookup"><span data-stu-id="74cea-119">The following table lists the predefined roles in Lync Server, and gives a general overview of the types of tasks each can do.</span></span> <span data-ttu-id="74cea-120">4番目の列には、各 Lync Server の役割に類似した Microsoft Exchange サーバーの役割 (存在する場合) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="74cea-120">The fourth column shows the similar Microsoft Exchange Server role for each Lync Server role, if there is one.</span></span>

### <a name="predefined-administrative-roles"></a><span data-ttu-id="74cea-121">定義済みの管理役割</span><span class="sxs-lookup"><span data-stu-id="74cea-121">Predefined Administrative Roles</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74cea-122">Role</span><span class="sxs-lookup"><span data-stu-id="74cea-122">Role</span></span></th>
<th><span data-ttu-id="74cea-123">実行可能なタスク</span><span class="sxs-lookup"><span data-stu-id="74cea-123">Tasks allowed</span></span></th>
<th><span data-ttu-id="74cea-124">基礎となる Active Directory グループ</span><span class="sxs-lookup"><span data-stu-id="74cea-124">Underlying Active Directory group</span></span></th>
<th><span data-ttu-id="74cea-125">対応する Exchange Server の役割</span><span class="sxs-lookup"><span data-stu-id="74cea-125">Exchange equivalent</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74cea-126">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="74cea-126">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="74cea-p106">すべての管理タスクの実行とすべての設定の変更ができます。これには、役割の作成や役割へのユーザーの割り当ても含まれます。 新しいサイト、プール、およびサービスを追加して展開を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="74cea-p106">Can perform all administrative tasks and modify all settings, including creating roles and assigning users to roles. Can expand a deployment by adding new sites, pools, and services.</span></span></p></td>
<td><p><span data-ttu-id="74cea-129">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="74cea-129">CSAdministrator</span></span></p></td>
<td><p><span data-ttu-id="74cea-130">Organization Management</span><span class="sxs-lookup"><span data-stu-id="74cea-130">Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74cea-131">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="74cea-131">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="74cea-132">Lync Server でユーザーを有効または無効にしたり、ユーザーを移動したり、既存のポリシーをユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="74cea-132">Can enable and disable users for Lync Server, move users and assign existing policies to users.</span></span> <span data-ttu-id="74cea-133">ポリシーは変更できません。</span><span class="sxs-lookup"><span data-stu-id="74cea-133">Cannot modify policies.</span></span></p></td>
<td><p><span data-ttu-id="74cea-134">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="74cea-134">CSUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="74cea-135">Mail Recipients</span><span class="sxs-lookup"><span data-stu-id="74cea-135">Mail Recipients</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74cea-136">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="74cea-136">CsVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="74cea-137">音声関連の設定やポリシーを作成、構成、および管理できます。</span><span class="sxs-lookup"><span data-stu-id="74cea-137">Can create, configure, and manage voice-related settings and policies.</span></span></p></td>
<td><p><span data-ttu-id="74cea-138">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="74cea-138">CSVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="74cea-139">該当なし</span><span class="sxs-lookup"><span data-stu-id="74cea-139">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74cea-140">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="74cea-140">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="74cea-p108">サーバーやサービスを管理、監視、およびトラブルシューティングできます。 サーバーへの新しい接続を禁止したり、サービスを停止および開始したり、ソフトウェア更新プログラムを適用したりできます。 グローバル構成に影響する変更はできません。</span><span class="sxs-lookup"><span data-stu-id="74cea-p108">Can manage, monitor, and troubleshoot servers and services. Can prevent new connections to servers, stop and start services, and apply software updates. Cannot make changes with global configuration impact.</span></span></p></td>
<td><p><span data-ttu-id="74cea-144">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="74cea-144">CSServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="74cea-145">Server Management</span><span class="sxs-lookup"><span data-stu-id="74cea-145">Server Management</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74cea-146">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="74cea-146">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="74cea-147">展開の状態を監視するためにユーザーやサーバーの情報を含む展開を表示できます。</span><span class="sxs-lookup"><span data-stu-id="74cea-147">Can view the deployment, including user and server information, in order to monitor deployment health.</span></span></p></td>
<td><p><span data-ttu-id="74cea-148">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="74cea-148">CSViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="74cea-149">View-Only Organization Management</span><span class="sxs-lookup"><span data-stu-id="74cea-149">View-Only Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74cea-150">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="74cea-150">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="74cea-p109">ユーザーのプロパティやポリシーを含む展開を表示できます。 特定のトラブルシューティング タスクを実行できます。 ユーザーのプロパティやポリシー、サーバー構成、またはサービスは変更できません。</span><span class="sxs-lookup"><span data-stu-id="74cea-p109">Can view the deployment, including user's properties and policies. Can run specific troubleshooting tasks. Cannot change user properties or policies, server configuration, or services.</span></span></p></td>
<td><p><span data-ttu-id="74cea-154">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="74cea-154">CSHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="74cea-155">問い合わせ</span><span class="sxs-lookup"><span data-stu-id="74cea-155">HelpDesk</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74cea-156">CsArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="74cea-156">CsArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="74cea-157">アーカイブ構成およびポリシーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="74cea-157">Can modify archiving configuration and policies.</span></span></p></td>
<td><p><span data-ttu-id="74cea-158">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="74cea-158">CSArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="74cea-159">Retention Management, Legal Hold</span><span class="sxs-lookup"><span data-stu-id="74cea-159">Retention Management, Legal Hold</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74cea-160">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="74cea-160">CsResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="74cea-161">サイト内の応答グループ アプリケーションの構成を管理できます。</span><span class="sxs-lookup"><span data-stu-id="74cea-161">Can manage the configuration of the Response Group application within a site.</span></span></p></td>
<td><p><span data-ttu-id="74cea-162">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="74cea-162">CSResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="74cea-163">該当なし</span><span class="sxs-lookup"><span data-stu-id="74cea-163">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74cea-164">CsLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="74cea-164">CsLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="74cea-p110">Enhanced 9-1-1 (E9-1-1) を管理するための最低レベルの権限。E9-1-1 の場所とネットワーク識別子の作成、およびこれらの相互関連付けが含まれます。 この役割は必ずグローバル スコープに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="74cea-p110">Lowest level of rights for Enhanced 9-1-1 (E9-1-1) management, including creating E9-1-1 locations and network identifiers, and associating these with each other. This role is always assigned with a global scope.</span></span></p></td>
<td><p><span data-ttu-id="74cea-167">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="74cea-167">CSLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="74cea-168">該当なし</span><span class="sxs-lookup"><span data-stu-id="74cea-168">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74cea-169">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="74cea-169">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="74cea-170">特定の応答グループを管理できます。</span><span class="sxs-lookup"><span data-stu-id="74cea-170">Can manage specific response groups.</span></span></p></td>
<td><p><span data-ttu-id="74cea-171">CSResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="74cea-171">CSResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="74cea-172">該当なし</span><span class="sxs-lookup"><span data-stu-id="74cea-172">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74cea-173">CsPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="74cea-173">CsPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="74cea-174">常設チャット機能および特定の常設チャット ルームを管理できます。</span><span class="sxs-lookup"><span data-stu-id="74cea-174">Can manage the Persistent Chat feature and specific Persistent Chat rooms.</span></span></p></td>
<td><p><span data-ttu-id="74cea-175">CSPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="74cea-175">CSPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="74cea-176">該当なし</span><span class="sxs-lookup"><span data-stu-id="74cea-176">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="74cea-177">Lync Server に出荷されたすべての定義済みの役割には、グローバルスコープがあります。</span><span class="sxs-lookup"><span data-stu-id="74cea-177">All predefined roles shipped in Lync Server have a global scope.</span></span> <span data-ttu-id="74cea-178">最小限の特権のプラクティスを実施するには、限定的なサーバーやユーザーのセットのみを管理するユーザーに対して、グローバル スコープを持つ役割を割り当てないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="74cea-178">To follow least privilege practices, you should not assign users to roles with global scope if they are going to administer only a limited set of servers or users.</span></span> <span data-ttu-id="74cea-179">これを実現するには、既存の役割に基づいて、スコープが制限された役割を作成します。</span><span class="sxs-lookup"><span data-stu-id="74cea-179">To accomplish this, you can create roles which are based on an existing role, but with a more limited scope.</span></span>

<div>

## <a name="creating-a-scoped-role"></a><span data-ttu-id="74cea-180">スコープ付き役割の作成</span><span class="sxs-lookup"><span data-stu-id="74cea-180">Creating a Scoped Role</span></span>

<span data-ttu-id="74cea-181">スコープを制限した役割 (スコープ付き役割) を作成する場合、スコープ、スコープ付き役割のベースとなる既存の役割、および役割を割り当てる Active Directory グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="74cea-181">When you create a role with limited scope (a scoped role), you specify the scope, along with the existing role it is based on and the Active Directory group to be assigned the role.</span></span> <span data-ttu-id="74cea-182">指定する Active Directory グループは事前に作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="74cea-182">The Active Directory group you specify must already be created.</span></span> <span data-ttu-id="74cea-183">次に、定義済みの管理役割のうちの 1 つの特権を持ち、スコープを制限した役割を作成するコマンドレットの例を示します。</span><span class="sxs-lookup"><span data-stu-id="74cea-183">The following cmdlet is an example of a creating a role which has the privileges of one of the pre-defined administrative roles, but with limited scope.</span></span> <span data-ttu-id="74cea-184">という新しい役割が作成され `Site01 Server Administrators` ます。</span><span class="sxs-lookup"><span data-stu-id="74cea-184">It creates a new role called `Site01 Server Administrators`.</span></span> <span data-ttu-id="74cea-185">この役割には定義済みの CsServerAdministrator 役割の機能がありますが、Site01 サイトにあるサーバーのみが対象となります。</span><span class="sxs-lookup"><span data-stu-id="74cea-185">The role has the abilities of the predefined CsServerAdministrator role, but only for the servers located in the Site01 site.</span></span> <span data-ttu-id="74cea-186">このコマンドレットが動作するには、Site01 サイトが既に定義されている必要があります。また、という名前のユニバーサルセキュリティグループが既に存在している必要があり `Site01 Server Administrators` ます。</span><span class="sxs-lookup"><span data-stu-id="74cea-186">For this cmdlet to work, the Site01 site must already be defined, and a universal security group named `Site01 Server Administrators` must already exist.</span></span>

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

<span data-ttu-id="74cea-187">このコマンドレットを実行すると、グループのメンバーであるすべてのユーザー `Site01 Server Administrators` は、Site01 のサーバーに対するサーバー管理者権限を持つことになります。</span><span class="sxs-lookup"><span data-stu-id="74cea-187">After this cmdlet runs, all users who are members of the `Site01 Server Administrators` group will have server administrator privileges for the servers in Site01.</span></span> <span data-ttu-id="74cea-188">さらに、このユニバーサルセキュリティグループに後で追加されたユーザーも、この役割の権限を取得します。</span><span class="sxs-lookup"><span data-stu-id="74cea-188">Additionally, any users who are later added to this universal security group also gain the privileges of this role.</span></span> <span data-ttu-id="74cea-189">役割自体と、それが割り当てられているユニバーサルセキュリティグループの両方が呼び出されることに注意 `Site01 Server Administrators` してください。</span><span class="sxs-lookup"><span data-stu-id="74cea-189">Note that both the role itself, and the universal security group it is assigned to are called `Site01 Server Administrators`.</span></span>

<span data-ttu-id="74cea-190">次の例では、サーバー スコープではなくユーザー スコープを制限しています。</span><span class="sxs-lookup"><span data-stu-id="74cea-190">The following example limits user scope instead of server scope.</span></span> <span data-ttu-id="74cea-191">`Sales Users Administrator`Sales 組織単位のユーザーアカウントを管理するための役割を作成します。</span><span class="sxs-lookup"><span data-stu-id="74cea-191">It creates a `Sales Users Administrator` role to administer the user accounts in the Sales organizational unit.</span></span> <span data-ttu-id="74cea-192">このコマンドレットが動作するように、Salesユーザー管理者ユニバーサルセキュリティグループが既に作成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="74cea-192">The SalesUsersAdministrator universal security group must already be created for this cmdlet to work.</span></span>

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a><span data-ttu-id="74cea-193">新規役割の作成</span><span class="sxs-lookup"><span data-stu-id="74cea-193">Creating a New Role</span></span>

<span data-ttu-id="74cea-p115">定義済みの役割に定義されていないコマンドレットのセットにアクセスする役割や、スクリプトまたはモジュールのセットにアクセスする役割を作成する場合も、定義済みの役割のいずれかをテンプレートとして使用します。役割で実行できるスクリプトおよびモジュールは、次の場所に保存しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="74cea-p115">To create a role that has access to a set of cmdlets not in one of the predefined roles, or to a set of scripts or modules, you again start by using one of the predefined roles as a template. Note that scripts and modules that roles are to be able to run must be stored in the following locations:</span></span>

  - <span data-ttu-id="74cea-196">Lync モジュールパス (既定で C: \\ Program Files \\ Common Files \\ Microsoft lync Server 2013 \\ モジュール \\ Lync</span><span class="sxs-lookup"><span data-stu-id="74cea-196">The Lync module path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\Lync</span></span>

  - <span data-ttu-id="74cea-197">ユーザースクリプトパス。既定では C: \\ Program Files \\ Common Files \\ Microsoft Lync Server 2013 \\ adminscripts</span><span class="sxs-lookup"><span data-stu-id="74cea-197">The user script path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\AdminScripts</span></span>

<span data-ttu-id="74cea-198">新規役割を作成するには、**New-CsAdminRole** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="74cea-198">To make a new role, you use the **New-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="74cea-199">**新しい-CsAdminRole**を実行する前に、まず、この役割に関連付けられる基礎となるユニバーサルセキュリティグループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74cea-199">Before running **New-CsAdminRole**, you must first create the underlying universal security group that will be associated with this role.</span></span>

<span data-ttu-id="74cea-200">新規役割を作成するコマンドレットの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="74cea-200">The following cmdlets serve as an example of a creating a new role.</span></span> <span data-ttu-id="74cea-201">という名前の新しい役割の種類を作成 `MyHelpDeskScriptRole` します。</span><span class="sxs-lookup"><span data-stu-id="74cea-201">They create a new role type called `MyHelpDeskScriptRole`.</span></span> <span data-ttu-id="74cea-202">新しい役割は、定義済みの CsHelpDesk 役割の機能を持っていますが、それに加えて "testscript" という名前のスクリプトで関数を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="74cea-202">The new role has the abilities of the predefined CsHelpDesk role, and can additionally run the functions in a script named “testscript”.</span></span>

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

<span data-ttu-id="74cea-203">このコマンドレットが動作するためには、最初にユニバーサルセキュリティグループ Myhelpの Scriptrole を作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="74cea-203">For this cmdlet to work, you must have first created the universal security group MyHelpDeskScriptRole.</span></span>

<span data-ttu-id="74cea-204">このコマンドレットの実行後、ユーザーをこの役割に直接割り当てたり (この場合ユーザーのスコープはグローバルになります)、このドキュメントの「スコープ付き役割の作成」で説明したように、この役割に基づいてスコープ付き役割を作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="74cea-204">After this cmdlet runs, you can assign users directly to this role (in which case they have global scope), or create a scoped role based on this role, as explained in Creating a Scoped Role, previously in this document.</span></span>

</div>

<div>

## <a name="assigning-roles-to-users"></a><span data-ttu-id="74cea-205">ユーザーへの役割の割り当て</span><span class="sxs-lookup"><span data-stu-id="74cea-205">Assigning Roles to Users</span></span>

<span data-ttu-id="74cea-206">各 Lync Server の役割は、基礎となる Active Directory ユニバーサルセキュリティグループに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="74cea-206">Each Lync Server role is associated with an underlying Active Directory universal security group.</span></span> <span data-ttu-id="74cea-207">基礎となるグループに追加したユーザーには、その役割の機能が付与されます。</span><span class="sxs-lookup"><span data-stu-id="74cea-207">Any users who you add to the underlying group gain the abilities of that role.</span></span>

<span data-ttu-id="74cea-208">前のセクションの例では、新しい役割を作成し、既存のユニバーサルセキュリティグループを新しい役割に割り当てています。</span><span class="sxs-lookup"><span data-stu-id="74cea-208">The examples in the preceding sections both created a new role and assigned an existing universal security group to the new role.</span></span> <span data-ttu-id="74cea-209">既存の役割を 1 人以上のユーザーに割り当てるには、役割に関連付けられているグループにそれらのユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="74cea-209">To assign an existing role to one or more users, add those users to the group associated with the role.</span></span> <span data-ttu-id="74cea-210">これらのグループには、個々のユーザーとユニバーサルセキュリティグループの両方を追加できます。</span><span class="sxs-lookup"><span data-stu-id="74cea-210">You can add both individual users and universal security groups to these groups.</span></span>

<span data-ttu-id="74cea-211">たとえば、 **Csadministrator** の役割は、Active Directory の **CS Administrators** ユニバーサルセキュリティグループに自動的に付与されます。</span><span class="sxs-lookup"><span data-stu-id="74cea-211">For example, the **CsAdministrator** role is automatically granted to the **CS Administrators** universal security group in Active Directory.</span></span> <span data-ttu-id="74cea-212">このユニバーサルセキュリティグループは、Lync Server の展開時に Active Directory 内に作成されます。</span><span class="sxs-lookup"><span data-stu-id="74cea-212">This universal security group is created in Active Directory when you deploy Lync Server.</span></span> <span data-ttu-id="74cea-213">ユーザーまたはグループを **CS Administrators** グループに追加するだけでこの特権をユーザーまたはグループに付与できます。</span><span class="sxs-lookup"><span data-stu-id="74cea-213">To grant a user or group this privilege, you can simply add them to the **CS Administrators** group.</span></span>

<span data-ttu-id="74cea-214">各役割に対応する基礎となる Active Directory グループにユーザーを追加することで、複数の RBAC の役割をユーザーに付与できます。</span><span class="sxs-lookup"><span data-stu-id="74cea-214">A user can be given multiple RBAC roles by being added to the underlying Active Directory groups that correspond to each role.</span></span>

<span data-ttu-id="74cea-215">役割を作成する場合、基礎となる Active Directory グループに後から追加されたユーザーにもその役割の機能が付与されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="74cea-215">Note that when you create a role, users who are later added to the underlying Active Directory group gain the abilities of that role.</span></span>

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a><span data-ttu-id="74cea-216">役割の機能の変更</span><span class="sxs-lookup"><span data-stu-id="74cea-216">Modifying the Abilities of a Role</span></span>

<span data-ttu-id="74cea-p121">役割で実行できるコマンドレットおよびスクリプトのリストを変更できます。カスタムの役割では、実行できるコマンドレットとスクリプトの両方を変更できますが、定義済みの役割ではスクリプトのみを変更できます。入力する各コマンドレットで、コマンドレットまたはスクリプトを追加、削除したり、置き換えたりできます。</span><span class="sxs-lookup"><span data-stu-id="74cea-p121">You can modify the list of cmdlets and scripts that a role can run. You can modify both the cmdlets and scripts that custom roles can run, but you can modify only the scripts for predefined roles. Each cmdlet you type can add, remove, or replace cmdlets or scripts.</span></span>

<span data-ttu-id="74cea-220">役割を変更するには、**Set-CsAdminRole** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="74cea-220">To modify a role, use the **Set-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="74cea-221">次のコマンドレットは、役割から1つのスクリプトを削除します。</span><span class="sxs-lookup"><span data-stu-id="74cea-221">The following cmdlet removes one script from the role.</span></span>

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a><span data-ttu-id="74cea-222">RBAC の計画</span><span class="sxs-lookup"><span data-stu-id="74cea-222">Planning for RBAC</span></span>

<span data-ttu-id="74cea-223">Lync Server 展開に対して何らかの管理者権限を与えられるユーザーごとに、実行する必要があるタスクを正確に検討し、その仕事に必要な最低限の特権と範囲を持つ役割に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="74cea-223">For each person who is to be given any kind of administrative rights for your Lync Server deployment, consider exactly which tasks they need to perform, then assign them to roles with the least privilege and scope necessary for their job.</span></span> <span data-ttu-id="74cea-224">必要に応じて **Set-CsAdminRole** コマンドレットを使用して、このユーザーのタスクに必要なコマンドレットのみを実行できる新しい役割を作成できます。</span><span class="sxs-lookup"><span data-stu-id="74cea-224">If necessary, you can use the **Set-CsAdminRole** cmdlet to create a new role with only the cmdlets necessary for this person’s tasks.</span></span>

<span data-ttu-id="74cea-p124">CsAdministrator の役割があるユーザーは、すべてのタイプの役割 (CsAdministrator に基づいた役割など) を作成し、その役割にユーザーを割り当てることができます。 CsAdministrator の役割は、信頼できる少数のユーザーに割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="74cea-p124">Users who have the CsAdministrator role can create all types of roles, including roles based on CsAdministrator, and assign users to them. The best practice is to assign the CsAdministrator role to a very small set of trusted users.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

