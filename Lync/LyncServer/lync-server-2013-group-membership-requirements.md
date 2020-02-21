---
title: 'Lync Server 2013: グループメンバーシップの要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group membership requirements
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48183239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8726d471b1db95aa67cca58a77452d9faa43df4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a><span data-ttu-id="10847-102">Lync Server 2013 のグループメンバーシップ要件</span><span class="sxs-lookup"><span data-stu-id="10847-102">Group membership requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10847-103">_**トピックの最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="10847-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="10847-104">次の表に、Lync Server 2013 のインストール、管理、およびトラブルシューティングを正常に行うために、個人が所属する必要があるグループをまとめています。</span><span class="sxs-lookup"><span data-stu-id="10847-104">The following table summarizes the group or groups that a person should belong to in order to successfully install, manage, and troubleshoot Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10847-105">Lync Server 2013 実行可能ファイル</span><span class="sxs-lookup"><span data-stu-id="10847-105">Lync Server 2013 Executable</span></span></th>
<th><span data-ttu-id="10847-106">必要なグループ メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="10847-106">Group Membership Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10847-107"><strong>Setup.exe</strong> – Lync Server 2013 管理ツールのインストールを開始する実行可能ファイル。</span><span class="sxs-lookup"><span data-stu-id="10847-107"><strong>Setup.exe</strong> – Executable that starts the installation of the Lync Server 2013 administrative tools.</span></span></p></td>
<td><p><span data-ttu-id="10847-108">実行可能ファイルを実行するコンピューターでの Local Administrators グループのメンバー。</span><span class="sxs-lookup"><span data-stu-id="10847-108">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="10847-109">Active Directory ドメインサービスの情報を読み取るためのドメインユーザーグループのメンバ。</span><span class="sxs-lookup"><span data-stu-id="10847-109">Member of Domain Users group to read information in Active Directory Domain Services.</span></span> <span data-ttu-id="10847-110">このレベルのアクセス許可が必要なのは、ローカル コンピューターへの必須 MSI パッケージの自動インストールでは、Program Files ディレクトリなどのローカル コンピューターの保護されたリソース、およびローカル コンピューター ハイブなどの保護されたレジストリとの間で読み書きできる特権が必要だからです。</span><span class="sxs-lookup"><span data-stu-id="10847-110">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="10847-111">セットアップ アクセス許可は、メンバーシップを付与したくない、Domain Admins グループのユーザーやグループに委任することもできます。</span><span class="sxs-lookup"><span data-stu-id="10847-111">You can also delegate setup permissions to users or groups to whom you do not want to grant membership in the Domain Admins group.</span></span> <span data-ttu-id="10847-112">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 でのセットアップのアクセス許可の付与</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10847-112">For details, see <A href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</A> in the Deployment documentation.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10847-113"><strong>deploy.exe</strong> - setup.exe によって呼び出され、サーバーの役割のソフトウェア コンポーネントを展開する処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="10847-113"><strong>Deploy.exe</strong> – Called by setup.exe, deploy.exe is responsible for the deployment of the software components for the server roles.</span></span></p></td>
<td><p><span data-ttu-id="10847-114">実行可能ファイルを実行するコンピューターでの Local Administrators グループのメンバー。</span><span class="sxs-lookup"><span data-stu-id="10847-114">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="10847-115">AD DS の情報を読み取る Domain Users グループのメンバー。</span><span class="sxs-lookup"><span data-stu-id="10847-115">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="10847-116">このレベルのアクセス許可が必要なのは、ローカル コンピューターへの必須 MSI パッケージの自動インストールでは、Program Files ディレクトリなどのローカル コンピューターの保護されたリソース、およびローカル コンピューター ハイブなどの保護されたレジストリとの間で読み書きできる特権が必要だからです。</span><span class="sxs-lookup"><span data-stu-id="10847-116">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span> <span data-ttu-id="10847-117">中央管理ストアを読み取るには、RtcUniversalReadOnlyAdmins グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="10847-117">Membership in RtcUniversalReadOnlyAdmins group is necessary to read the Central Management store.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="10847-118">Windows Vista オペレーティングシステムまたは Windows 7 オペレーティングシステムを実行している場合は、インストールを続行するためにユーザーアカウント制御 (UAC) によってメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="10847-118">If you are running the Windows Vista operating system or Windows 7 operating system, you will be prompted by User Account Control (UAC) to proceed with installation.</span></span> <span data-ttu-id="10847-119">標準のユーザー アカウントでログオンしている場合に、ソフトウェアのインストール アクセス許可を持つアカウントを要求されたときは、Local Administrators グループのメンバーであるユーザーから資格情報の提供を受ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="10847-119">If you are logged on with a standard user account, you will need someone who is a member of the Local Administrators group to provide credentials when prompted for an account with permissions to install the software.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10847-120"><strong>bootstrapper.exe</strong> - setup.exe によって呼び出され、サーバーの役割を展開および構成する処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="10847-120"><strong>Bootstrapper.exe</strong> – Called by setup.exe, bootstrapper.exe is responsible for deployment and configuration of server roles.</span></span></p></td>
<td><p><span data-ttu-id="10847-p105">実行可能ファイルを実行するコンピューターでの Local Administrators グループのメンバー。Bootstrapper.exe を実行する RTCUniversalServerAdmins グループのメンバー。AD DS の情報を読み取る Domain Users グループのメンバー。このレベルのアクセス許可が必要なのは、ローカル コンピューターへの必須 MSI パッケージの自動インストールでは、Program Files ディレクトリなどのローカル コンピューターの保護されたリソース、およびローカル コンピューター ハイブなどの保護されたレジストリとの間で読み書きできる特権が必要だからです。</span><span class="sxs-lookup"><span data-stu-id="10847-p105">Member of the Local Administrators group on the computer from which the executable is run. Member of the RTCUniversalServerAdmins group to run Bootstrapper.exe. Member of Domain Users group to read information in AD DS. This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10847-125"><strong>TopologyBuilder</strong> – Lync Server 2013 のトポロジを作成、表示、調整、および検証するためのウィザードベースのユーザーインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="10847-125"><strong>TopologyBuilder</strong> – Wizard-driven user interface to create, view, adjust, and validate Lync Server 2013 topologies.</span></span></p></td>
<td><p><span data-ttu-id="10847-126">実行可能ファイルを実行してトポロジを表示するコンピューターでの Local Administrators グループのメンバー。</span><span class="sxs-lookup"><span data-stu-id="10847-126">Member of the Local Administrators group on the computer from which the executable is run to view the topology.</span></span> <span data-ttu-id="10847-127">構成の設定を変更する RTCUniversalServerAdmins グループのメンバー。</span><span class="sxs-lookup"><span data-stu-id="10847-127">Member of the RTCUniversalServerAdmins group to change configuration settings.</span></span> <span data-ttu-id="10847-128">RTCUniversalServerAdmins グループと Domain Admins グループのメンバー、またはトポロジを発行する RTCUniversalServerAdmins グループのメンバー (このグループに委任セットアップ アクセス許可が付与されている場合のみ)。</span><span class="sxs-lookup"><span data-stu-id="10847-128">Member of the RTCUniversalServerAdmins group and Domain Admins group, or member of the RTCUniversalServerAdmins group (only if the group has been granted delegate setup permissions), to publish the topology.</span></span> <span data-ttu-id="10847-129">RTCUniversalServerAdmins グループのメンバーがドメイン管理者グループのメンバーではない状態でトポロジを公開できるようにするための、セットアップのアクセス許可の委任の詳細については、「展開」のドキュメントの「 <a href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 のセットアップのアクセス許可を付与</a>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10847-129">For details about delegating setup permissions to allow members of the RTCUniversalServerAdmins group to publish the topology without being members of the Domain Admins group, see <a href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10847-130"><strong>AdminUIHost</strong> – Lync Server 2013 を管理するための Web ベースのグラフィカルユーザーインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="10847-130"><strong>AdminUIHost</strong> – Web-based graphical user interface for managing Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="10847-131">CsAdministrator グループのメンバー、または特定の管理タスクが割り当てられる別の役割ベースのアクセス制御 (RBAC) の役割のメンバー。</span><span class="sxs-lookup"><span data-stu-id="10847-131">Member of CsAdministrator group or member of another role-based access control (RBAC) role to which the specific administrative task is assigned.</span></span> <span data-ttu-id="10847-132">Lync Server 2013 コントロールパネルは、Lync Server 2013 管理シェルコマンドレットを実行することによって、構成の変更を実装します。</span><span class="sxs-lookup"><span data-stu-id="10847-132">Lync Server 2013 Control Panel implements configuration changes by running Lync Server 2013 Management Shell cmdlets.</span></span> <span data-ttu-id="10847-133">定義済みの役割の一覧とコマンドレットのメンバーの実行を許可する方法については、「計画」のドキュメントの「 <a href="lync-server-2013-planning-for-role-based-access-control.md">planning for roles based access control In Lync Server 2013</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10847-133">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10847-134">PowerShell: lync server <strong>2013 モジュールが読み込ま</strong>れたコマンドライン管理ツールを使用して、lync server 2013 の管理に固有のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="10847-134"><strong>PowerShell.exe with the Lync Server 2013 module loaded</strong> – Command-line administrative tool with cmdlets specific to management of Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="10847-135">CsAdministrator グループのメンバー、または特定のコマンドレットが割り当てられている別の RBAC の役割のメンバー。</span><span class="sxs-lookup"><span data-stu-id="10847-135">Member of CsAdministrator group or member of another RBAC role to which the specific cmdlet has been assigned.</span></span> <span data-ttu-id="10847-136">定義済みの役割の一覧とコマンドレットのメンバーの実行を許可する方法については、「計画」のドキュメントの「 <a href="lync-server-2013-planning-for-role-based-access-control.md">planning for roles based access control In Lync Server 2013</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10847-136">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="10847-137">または、次に示すグループのうち 1 つ以上のメンバー (コマンドレットによる):</span><span class="sxs-lookup"><span data-stu-id="10847-137">Or, member of one or more of the following groups, depending on the cmdlet:</span></span></p>
<ul>
<li><p><span data-ttu-id="10847-138">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="10847-138">RTCUniversalServerAdmins</span></span></p></li>
<li><p><span data-ttu-id="10847-139">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="10847-139">RTCUniversalUserAdmins</span></span></p></li>
<li><p><span data-ttu-id="10847-140">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="10847-140">RTCUniversalReadOnlyAdmins</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

