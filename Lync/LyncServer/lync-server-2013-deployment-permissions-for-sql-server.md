---
title: 'Lync Server 2013: SQL Server の展開のアクセス許可'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea0334c7070ae3aadb3191da4bf036a978878688
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="0ad75-102">Lync Server 2013 の SQL Server の展開のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0ad75-102">Deployment permissions for SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ad75-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="0ad75-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="0ad75-104">Microsoft SQL Server 2012 には、Lync Server 2013 をインストールして展開するときに特定の要件があります。</span><span class="sxs-lookup"><span data-stu-id="0ad75-104">Microsoft SQL Server 2012 has specific requirements when installing and deploying Lync Server 2013.</span></span> <span data-ttu-id="0ad75-105">Windows と SQL Server はセキュリティの定義が異なるため、Active Directory ドメインで管理者としてログインしても、SQL Server へのアクセス許可が暗黙的に付与されることはありません。</span><span class="sxs-lookup"><span data-stu-id="0ad75-105">Because Windows and SQL Server define their security differently, logging in as an administrator in the Active Directory domain does not implicitly grant permissions for SQL Server.</span></span> <span data-ttu-id="0ad75-106">また、構成している SQL Server ベースのサーバーの sysadmin エンティティのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ad75-106">You must also be a member of the sysadmin entity on the SQL Server-based server you are configuring.</span></span>

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a><span data-ttu-id="0ad75-107">データベースおよび Lync Server のインストールに必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0ad75-107">Permissions Required for Database and Lync Server Installation</span></span>

<span data-ttu-id="0ad75-108">次のオプションでは、Lync Server 2013 ファイルと SQL Server データベースをインストールするための3つのアクセス許可とグループメンバーシップの関連付けについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0ad75-108">The following options detail three permissions and group membership associations for installation of Lync Server 2013 files and SQL Server databases.</span></span> <span data-ttu-id="0ad75-109">組織の要件に最も適合するシナリオを選択します。</span><span class="sxs-lookup"><span data-stu-id="0ad75-109">Choose the scenario that best meets the requirements of your organization.</span></span>

### <a name="permissions-and-group-membership-associations"></a><span data-ttu-id="0ad75-110">権限とグループメンバーシップの関連付け</span><span class="sxs-lookup"><span data-stu-id="0ad75-110">Permissions and Group Membership Associations</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ad75-111">SQL Server または Lync Server 2013 の役割</span><span class="sxs-lookup"><span data-stu-id="0ad75-111">SQL Server or Lync Server 2013 role</span></span></th>
<th><span data-ttu-id="0ad75-112">役割-一般的な SQL Server 権限とグループメンバーシップ</span><span class="sxs-lookup"><span data-stu-id="0ad75-112">Role-Typical SQL Server permissions and group membership</span></span></th>
<th><span data-ttu-id="0ad75-113">役割-一般的な Lync Server 2013 のアクセス許可とグループメンバーシップ</span><span class="sxs-lookup"><span data-stu-id="0ad75-113">Role-typical Lync Server 2013 permissions and group membership</span></span></th>
<th><span data-ttu-id="0ad75-114">権限の結果</span><span class="sxs-lookup"><span data-stu-id="0ad75-114">Permissions outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ad75-115">Lync Server 2013 管理者</span><span class="sxs-lookup"><span data-stu-id="0ad75-115">Lync Server 2013 administrator</span></span></p></td>
<td><p><span data-ttu-id="0ad75-116">システム管理者の SQL Server セキュリティグループと、SQL Server のローカル管理者グループのメンバーに付与されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ad75-116">Must be granted membership of sysadmins SQL Server security group and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="0ad75-117">RTCUniversalServerAdmins グループのメンバーである必要があります</span><span class="sxs-lookup"><span data-stu-id="0ad75-117">Must be a member of the RTCUniversalServerAdmins group</span></span></p></td>
<td><p><span data-ttu-id="0ad75-118">Lync server 2013 管理者は、Lync Server 2013 と SQL Server データベースの両方をインストールするための適切な権限を持っています。</span><span class="sxs-lookup"><span data-stu-id="0ad75-118">Lync Server 2013 administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ad75-119">SQL Server 管理者</span><span class="sxs-lookup"><span data-stu-id="0ad75-119">SQL Server administrator</span></span></p></td>
<td><p><span data-ttu-id="0ad75-120">SQL Server sysadmin グループのメンバー (または同等の機能) と SQL Server のローカル管理者グループのメンバー</span><span class="sxs-lookup"><span data-stu-id="0ad75-120">SQL Server sysadmin group member (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="0ad75-121">RTCUniversalServerReadOnly グループのメンバーである必要があります</span><span class="sxs-lookup"><span data-stu-id="0ad75-121">Must be a member of the RTCUniversalServerReadOnly group</span></span></p></td>
<td><p><span data-ttu-id="0ad75-122">SQL Server 管理者は、Lync Server 2013 データベースと SQL Server データベースの両方をインストールするための適切な権限を持っています。</span><span class="sxs-lookup"><span data-stu-id="0ad75-122">SQL Server administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ad75-123">両方の管理者がインストール義務を共有する</span><span class="sxs-lookup"><span data-stu-id="0ad75-123">Both administrators sharing installation duties</span></span></p></td>
<td><p><span data-ttu-id="0ad75-124">SQL Server 管理者は、システム管理者グループ (または同等のメンバー) と SQL Server のローカル管理者グループのメンバーである</span><span class="sxs-lookup"><span data-stu-id="0ad75-124">SQL Server administrator is member of sysadmins group (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="0ad75-125">Lync Server 2013 管理者が RTCUniversalServerAdmins のメンバーである</span><span class="sxs-lookup"><span data-stu-id="0ad75-125">Lync Server 2013 administrator is member of RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="0ad75-126">Lync Server 2013 管理者は Lync Server 2013 をインストールできますが、データベースをインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0ad75-126">The Lync Server 2013 administrator can install Lync Server 2013, but cannot install the databases.</span></span> <span data-ttu-id="0ad75-127">SQL Server 管理者は、lync server 2013 管理者が提供する Lync Server 管理シェルと Windows PowerShell コマンドレットを使用して、データベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0ad75-127">The SQL Server administrator uses the Lync Server Management Shell and Windows PowerShell cmdlets provided by the Lync Server 2013 administrator to install the databases.</span></span> <span data-ttu-id="0ad75-128">SQL Server 管理者が使用する Lync Server 2013 管理シェルは、フロントエンドサーバーにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="0ad75-128">The Lync Server 2013 Management Shell used by the SQL Server administrator is installed on the Front End Server.</span></span> <span data-ttu-id="0ad75-129">これにより、Lync Server 2013 管理ツールを SQL Server ベースのサーバーにインストールする必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="0ad75-129">This eliminates the need to install the Lync Server 2013 administrative tools on the SQL Server-based server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

