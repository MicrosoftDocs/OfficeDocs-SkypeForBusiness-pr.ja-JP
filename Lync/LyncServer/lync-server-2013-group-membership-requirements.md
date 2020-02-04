---
title: 'Lync Server 2013: グループ メンバーシップの要件'
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
ms.openlocfilehash: 44ad8c7f6eab93f3bdcd7b73d4ae05bd3b2e25ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a><span data-ttu-id="f891f-102">Lync Server 2013 のグループ メンバーシップの要件</span><span class="sxs-lookup"><span data-stu-id="f891f-102">Group membership requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f891f-103">_**最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="f891f-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="f891f-104">次の表は、Lync Server 2013 を正常にインストール、管理、トラブルシューティングするために、ユーザーが所属する必要があるグループをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="f891f-104">The following table summarizes the group or groups that a person should belong to in order to successfully install, manage, and troubleshoot Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f891f-105">Lync Server 2013 実行可能ファイル</span><span class="sxs-lookup"><span data-stu-id="f891f-105">Lync Server 2013 Executable</span></span></th>
<th><span data-ttu-id="f891f-106">グループメンバーシップが必要です</span><span class="sxs-lookup"><span data-stu-id="f891f-106">Group Membership Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f891f-107"><strong>Setup.exe – Lync</strong> Server 2013 管理ツールのインストールを開始する実行可能ファイル。</span><span class="sxs-lookup"><span data-stu-id="f891f-107"><strong>Setup.exe</strong> – Executable that starts the installation of the Lync Server 2013 administrative tools.</span></span></p></td>
<td><p><span data-ttu-id="f891f-108">実行可能ファイルを実行しているコンピューターのローカル管理者グループのメンバー。</span><span class="sxs-lookup"><span data-stu-id="f891f-108">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="f891f-109">Active Directory ドメインサービスの情報を読み取るためのドメインユーザーグループのメンバー。</span><span class="sxs-lookup"><span data-stu-id="f891f-109">Member of Domain Users group to read information in Active Directory Domain Services.</span></span> <span data-ttu-id="f891f-110">ローカルコンピューターで必須の MSI パッケージを自動的にインストールするには、Program Files ディレクトリなどの保護されたローカルコンピューターリソースの読み取りと書き込みを許可する特権が必要となるため、このレベルのアクセス許可が必要です。ローカルコンピューターハイブなどのレジストリ。</span><span class="sxs-lookup"><span data-stu-id="f891f-110">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="f891f-111">また、ドメイン管理者グループのメンバーシップを付与しないユーザーまたはグループに、セットアップのアクセス許可を委任することもできます。</span><span class="sxs-lookup"><span data-stu-id="f891f-111">You can also delegate setup permissions to users or groups to whom you do not want to grant membership in the Domain Admins group.</span></span> <span data-ttu-id="f891f-112">詳細については、展開ドキュメントの「 <A href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 でのセットアップ権限の付与</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f891f-112">For details, see <A href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</A> in the Deployment documentation.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f891f-113"><strong>Update.exe</strong> – Setup.exe で呼び出される場合は、サーバーの役割のソフトウェアコンポーネントの展開について行います。</span><span class="sxs-lookup"><span data-stu-id="f891f-113"><strong>Deploy.exe</strong> – Called by setup.exe, deploy.exe is responsible for the deployment of the software components for the server roles.</span></span></p></td>
<td><p><span data-ttu-id="f891f-114">実行可能ファイルを実行しているコンピューターのローカル管理者グループのメンバー。</span><span class="sxs-lookup"><span data-stu-id="f891f-114">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="f891f-115">ドメインユーザーグループのメンバーで、AD DS の情報を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="f891f-115">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="f891f-116">ローカルコンピューターで必須の MSI パッケージを自動的にインストールするには、Program Files ディレクトリなどの保護されたローカルコンピューターリソースの読み取りと書き込みを許可する特権が必要となるため、このレベルのアクセス許可が必要です。ローカルコンピューターハイブなどのレジストリ。</span><span class="sxs-lookup"><span data-stu-id="f891f-116">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span> <span data-ttu-id="f891f-117">中央管理ストアを読むには、RtcUniversalReadOnlyAdmins group のメンバーシップが必要です。</span><span class="sxs-lookup"><span data-stu-id="f891f-117">Membership in RtcUniversalReadOnlyAdmins group is necessary to read the Central Management store.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f891f-118">Windows Vista オペレーティングシステムまたは Windows 7 オペレーティングシステムを実行している場合は、ユーザーアカウント制御 (UAC) によってインストールを続行するかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f891f-118">If you are running the Windows Vista operating system or Windows 7 operating system, you will be prompted by User Account Control (UAC) to proceed with installation.</span></span> <span data-ttu-id="f891f-119">標準ユーザーアカウントでログオンしている場合は、ソフトウェアをインストールする権限を持つアカウントの入力を求められたときに、資格情報を提供するために、ローカル管理者グループのメンバーであるユーザーが必要になります。</span><span class="sxs-lookup"><span data-stu-id="f891f-119">If you are logged on with a standard user account, you will need someone who is a member of the Local Administrators group to provide credentials when prompted for an account with permissions to install the software.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f891f-120"><strong>ブートストラップ</strong>– setup.exe によって呼び出され、サーバーの役割の展開と構成を担当します。</span><span class="sxs-lookup"><span data-stu-id="f891f-120"><strong>Bootstrapper.exe</strong> – Called by setup.exe, bootstrapper.exe is responsible for deployment and configuration of server roles.</span></span></p></td>
<td><p><span data-ttu-id="f891f-121">実行可能ファイルを実行しているコンピューターのローカル管理者グループのメンバー。</span><span class="sxs-lookup"><span data-stu-id="f891f-121">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="f891f-122">RTCUniversalServerAdmins グループのメンバーであるブートストラップを実行します。</span><span class="sxs-lookup"><span data-stu-id="f891f-122">Member of the RTCUniversalServerAdmins group to run Bootstrapper.exe.</span></span> <span data-ttu-id="f891f-123">ドメインユーザーグループのメンバーで、AD DS の情報を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="f891f-123">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="f891f-124">ローカルコンピューターで必須の MSI パッケージを自動的にインストールするには、Program Files ディレクトリなどの保護されたローカルコンピューターリソースの読み取りと書き込みを許可する特権が必要となるため、このレベルのアクセス許可が必要です。ローカルコンピューターハイブなどのレジストリ。</span><span class="sxs-lookup"><span data-stu-id="f891f-124">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f891f-125"><strong>TopologyBuilder</strong> – Lync Server 2013 トポロジの作成、表示、調整、検証を行うためのウィザードベースのユーザーインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="f891f-125"><strong>TopologyBuilder</strong> – Wizard-driven user interface to create, view, adjust, and validate Lync Server 2013 topologies.</span></span></p></td>
<td><p><span data-ttu-id="f891f-126">トポロジを表示するために、実行可能ファイルを実行しているコンピューターのローカル管理者グループのメンバー。</span><span class="sxs-lookup"><span data-stu-id="f891f-126">Member of the Local Administrators group on the computer from which the executable is run to view the topology.</span></span> <span data-ttu-id="f891f-127">構成の設定を変更する RTCUniversalServerAdmins グループのメンバー。</span><span class="sxs-lookup"><span data-stu-id="f891f-127">Member of the RTCUniversalServerAdmins group to change configuration settings.</span></span> <span data-ttu-id="f891f-128">トポロジを公開するには、RTCUniversalServerAdmins group と Domain Admins グループのメンバー、または RTCUniversalServerAdmins グループのメンバー (グループに委任の設定権限が付与されている場合のみ)。</span><span class="sxs-lookup"><span data-stu-id="f891f-128">Member of the RTCUniversalServerAdmins group and Domain Admins group, or member of the RTCUniversalServerAdmins group (only if the group has been granted delegate setup permissions), to publish the topology.</span></span> <span data-ttu-id="f891f-129">RTCUniversalServerAdmins グループのメンバーが、ドメイン管理者グループのメンバーにならずにトポロジを公開できるようにするための委任セットアップのアクセス許可の詳細については、「展開ドキュメントの「 <a href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 でのセットアップアクセス許可の付与</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f891f-129">For details about delegating setup permissions to allow members of the RTCUniversalServerAdmins group to publish the topology without being members of the Domain Admins group, see <a href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f891f-130"><strong>AdminUIHost</strong> – Lync Server 2013 を管理するための Web ベースのグラフィカルユーザーインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="f891f-130"><strong>AdminUIHost</strong> – Web-based graphical user interface for managing Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="f891f-131">特定の管理タスクが割り当てられている、他の役割ベースのアクセス制御 (RBAC) 役割のメンバー。 CsAdministrator グループまたはメンバー。</span><span class="sxs-lookup"><span data-stu-id="f891f-131">Member of CsAdministrator group or member of another role-based access control (RBAC) role to which the specific administrative task is assigned.</span></span> <span data-ttu-id="f891f-132">Lync Server 2013 コントロールパネルでは、Lync Server 2013 Management Shell コマンドレットを実行することで、構成の変更を実装します。</span><span class="sxs-lookup"><span data-stu-id="f891f-132">Lync Server 2013 Control Panel implements configuration changes by running Lync Server 2013 Management Shell cmdlets.</span></span> <span data-ttu-id="f891f-133">定義済みの役割と、コマンドレットのメンバーの実行を許可する方法については、計画ドキュメントの「 <a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 でのロールベースのアクセス制御の計画</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f891f-133">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f891f-134">Lync server <strong>2013 モジュールが読み込まれた PowerShell .exe</strong> – lync server 2013 の管理に固有のコマンドレット付きのコマンドライン管理ツール。</span><span class="sxs-lookup"><span data-stu-id="f891f-134"><strong>PowerShell.exe with the Lync Server 2013 module loaded</strong> – Command-line administrative tool with cmdlets specific to management of Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="f891f-135">特定のコマンドレットが割り当てられている CsAdministrator グループまたは別の RBAC 役割のメンバー。</span><span class="sxs-lookup"><span data-stu-id="f891f-135">Member of CsAdministrator group or member of another RBAC role to which the specific cmdlet has been assigned.</span></span> <span data-ttu-id="f891f-136">定義済みの役割と、コマンドレットのメンバーの実行を許可する方法については、計画ドキュメントの「 <a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 でのロールベースのアクセス制御の計画</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f891f-136">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="f891f-137">または、コマンドレットに応じて、次の1つまたは複数のグループのメンバーになります。</span><span class="sxs-lookup"><span data-stu-id="f891f-137">Or, member of one or more of the following groups, depending on the cmdlet:</span></span></p>
<ul>
<li><p><span data-ttu-id="f891f-138">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f891f-138">RTCUniversalServerAdmins</span></span></p></li>
<li><p><span data-ttu-id="f891f-139">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="f891f-139">RTCUniversalUserAdmins</span></span></p></li>
<li><p><span data-ttu-id="f891f-140">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="f891f-140">RTCUniversalReadOnlyAdmins</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

