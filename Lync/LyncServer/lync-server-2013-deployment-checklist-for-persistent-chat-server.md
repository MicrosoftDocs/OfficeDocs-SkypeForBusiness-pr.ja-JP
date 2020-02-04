---
title: 'Lync Server 2013: 常設チャット サーバーの展開チェックリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d80122534739d443dedaeeb203ab09da94cb0067
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="c03e9-102">Lync Server 2013 の常設チャット サーバーの展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="c03e9-102">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c03e9-103">_**最終更新日:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="c03e9-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="c03e9-104">Lync Server 2013、常設チャットサーバーを展開するには、正しい順序で展開し、必要なすべての展開手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c03e9-104">Deployment of Lync Server 2013, Persistent Chat Server requires that you deploy it in the correct sequence and that you complete all required deployment steps.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="c03e9-105">展開シーケンス</span><span class="sxs-lookup"><span data-stu-id="c03e9-105">Deployment Sequence</span></span>

<span data-ttu-id="c03e9-106">少なくとも1つの Lync Server 2013、フロントエンドプール、または1つの Lync Server 2013、Standard Edition server を含む、最初のトポロジを展開した後、常設チャットサーバーを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="c03e9-106">You can deploy Persistent Chat Server after you deploy your initial topology, including at least one Lync Server 2013, Front End pool or one Lync Server 2013, Standard Edition server.</span></span> <span data-ttu-id="c03e9-107">このトピックでは、既存の展開に追加して、常設チャットサーバーを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c03e9-107">This topic describes how to deploy Persistent Chat Server by adding it to an existing deployment.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="c03e9-108">展開プロセス</span><span class="sxs-lookup"><span data-stu-id="c03e9-108">Deployment Process</span></span>

<span data-ttu-id="c03e9-109">次の表は、常設チャットサーバーを展開するための基本的な手順と、詳細情報のリンクを示しています。</span><span class="sxs-lookup"><span data-stu-id="c03e9-109">The following table lists the basic steps to deploy Persistent Chat Server and provides links for more details.</span></span>

### <a name="persistent-chat-server-deployment-process"></a><span data-ttu-id="c03e9-110">常設チャットサーバーの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="c03e9-110">Persistent Chat Server Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c03e9-111">タスク</span><span class="sxs-lookup"><span data-stu-id="c03e9-111">Task</span></span></th>
<th><span data-ttu-id="c03e9-112">ステップ</span><span class="sxs-lookup"><span data-stu-id="c03e9-112">Steps</span></span></th>
<th><span data-ttu-id="c03e9-113">必要な役割とグループ メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="c03e9-113">Required roles and group memberships</span></span></th>
<th><span data-ttu-id="c03e9-114">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c03e9-114">Related topics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c03e9-115"><strong>必要なハードウェアとソフトウェアのインストール</strong></span><span class="sxs-lookup"><span data-stu-id="c03e9-115"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="c03e9-116">システム要件を満たすハードウェアに、次をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c03e9-116">On hardware that meets system requirements, install the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c03e9-117">常設チャットサーバーのフロントエンドサーバーで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c03e9-117">On the Persistent Chat Server Front End Servers:</span></span></p></li>
</ul>
<ul>
<li><p><span data-ttu-id="c03e9-118">システム要件を満たすオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="c03e9-118">An operating system that meets system requirements</span></span></p></li>
<li><p><span data-ttu-id="c03e9-119">Lync Server 2013 を実行しているコンピューターのソフトウェアの前提条件</span><span class="sxs-lookup"><span data-stu-id="c03e9-119">Software prerequisites for computers running Lync Server 2013</span></span></p></li>
<li><p><span data-ttu-id="c03e9-120">常設チャットサーバーデータベースをホストするサーバー上の SQL Server</span><span class="sxs-lookup"><span data-stu-id="c03e9-120">SQL Server on the server that will host Persistent Chat Server database</span></span></p></li>
</ul>
<p><span data-ttu-id="c03e9-121">常設チャットサーバーのコンプライアンスが必要な場合:</span><span class="sxs-lookup"><span data-stu-id="c03e9-121">If Persistent Chat Server compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="c03e9-122">常設チャットサーバーのコンプライアンスデータベースをホストするサーバー上の SQL Server</span><span class="sxs-lookup"><span data-stu-id="c03e9-122">SQL Server on the server that will host Persistent Chat Server compliance database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c03e9-123">ローカルの Administrators グループのメンバーであるユーザー。</span><span class="sxs-lookup"><span data-stu-id="c03e9-123">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="c03e9-124"><a href="lync-server-2013-supported-hardware.md">サポートされているドキュメントの Lync Server 2013 でサポートされているハードウェア</a></span><span class="sxs-lookup"><span data-stu-id="c03e9-124"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="c03e9-125">サポートドキュメントの<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート</a></span><span class="sxs-lookup"><span data-stu-id="c03e9-125"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="c03e9-126"><a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013 システム要件の決定</a></span><span class="sxs-lookup"><span data-stu-id="c03e9-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="c03e9-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Lync Server 2013 の常設チャットサーバーの技術要件</a></span><span class="sxs-lookup"><span data-stu-id="c03e9-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technical requirements for Persistent Chat Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03e9-128"><strong>常設チャットサーバーをサポートするための適切な内部トポロジを作成します (また、必要に応じて常設チャットのコンプライアンスも可能)。</strong></span><span class="sxs-lookup"><span data-stu-id="c03e9-128"><strong>Create the appropriate internal topology to support Persistent Chat Server (and optionally, Persistent Chat compliance)</strong></span></span></p></td>
<td><p><span data-ttu-id="c03e9-129">トポロジビルダーを実行して、常設チャットサーバープールをトポロジに追加します。</span><span class="sxs-lookup"><span data-stu-id="c03e9-129">Run Topology Builder to add a Persistent Chat Server pool to your topology:</span></span></p>
<ul>
<li><p><span data-ttu-id="c03e9-130">常設チャットサーバーコンポーネントをトポロジに追加する</span><span class="sxs-lookup"><span data-stu-id="c03e9-130">Add Persistent Chat Server components to the topology</span></span></p></li>
<li><p><span data-ttu-id="c03e9-131">常設チャットサーバーストア用の SQL Server データベースを作成します (および障害回復用のバックアップ SQL Server)。</span><span class="sxs-lookup"><span data-stu-id="c03e9-131">Create a SQL Server database for the Persistent Chat Server store (and a backup SQL Server for disaster recovery)</span></span></p></li>
<li><p><span data-ttu-id="c03e9-132">新しい Lync ファイルストアを定義するか、既存の Lync ファイルストアで常設チャットサーバーファイルを使用する</span><span class="sxs-lookup"><span data-stu-id="c03e9-132">Define a new Lync File Store or use an existing Lync File Store for Persistent Chat Server files</span></span></p></li>
<li><p><span data-ttu-id="c03e9-133">要求をこの常設チャットサーバープールにルーティングできる Lync Server 2013 プールを関連付ける</span><span class="sxs-lookup"><span data-stu-id="c03e9-133">Associate the Lync Server 2013 pool that can route requests to this Persistent Chat Server pool</span></span></p></li>
</ul>
<p><span data-ttu-id="c03e9-134">常設チャット コンプライアンスが必要な場合</span><span class="sxs-lookup"><span data-stu-id="c03e9-134">If Persistent Chat compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="c03e9-135">常設チャットのコンプライアンスストアを追加する</span><span class="sxs-lookup"><span data-stu-id="c03e9-135">Add Persistent Chat Compliance Store</span></span></p></li>
<li><p><span data-ttu-id="c03e9-136">コンプライアンスを有効にするには、[常設チャットサーバープールの定義] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c03e9-136">Click the Persistent Chat Server pool definition check box for enabling compliance</span></span></p></li>
<li><p><span data-ttu-id="c03e9-137">トポロジを公開する</span><span class="sxs-lookup"><span data-stu-id="c03e9-137">Publish the topology</span></span></p></li>
</ul>
<p><span data-ttu-id="c03e9-138">標準エディションに常設チャットサーバーをインストールする場合は、常設チャットサーバープールの完全修飾ドメイン名 (FQDN) が standard Edition サーバーと一致する必要があります。 SQL Server データベースは、標準の SQL Server Express インスタンスに併置されています。エディションサーバー</span><span class="sxs-lookup"><span data-stu-id="c03e9-138">If you install Persistent Chat Server on Standard Edition, the fully qualified domain name (FQDN) of the Persistent Chat Server pool must match the Standard Edition server, and the SQL Server databases are collocated on the SQL Server Express instance on the Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="c03e9-139">トポロジを定義するには、ローカルの Users グループのメンバーであるアカウント。</span><span class="sxs-lookup"><span data-stu-id="c03e9-139">To define a topology, an account that is a member of the local Users group.</span></span></p>
<p><span data-ttu-id="c03e9-140">トポロジを公開するには、ドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーであるアカウントであり、ユーザーは、常設チャットサーバーファイル用の Lync ファイルストアに対するフルコントロールのアクセス許可 (読み取り/書き込み/変更) を持っている必要があります (これにより、トポロジビルダーは必要な Dacl を構成できるようになります)。</span><span class="sxs-lookup"><span data-stu-id="c03e9-140">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and the user should also have full control permissions (read/write/modify) on the Lync File Store for Persistent Chat Server files (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="c03e9-141">展開ドキュメントの<a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 での展開への常設チャットサーバーの追加</a></span><span class="sxs-lookup"><span data-stu-id="c03e9-141"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03e9-142"><strong>常設チャット サーバーの展開</strong></span><span class="sxs-lookup"><span data-stu-id="c03e9-142"><strong>Deploy Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="c03e9-143">常設チャットサーバーを実行しているすべてのコンピューターで Lync Server のセットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="c03e9-143">Run the Lync Server setup on all the computers running Persistent Chat Server.</span></span> <span data-ttu-id="c03e9-144">常設チャットサーバーのセットアップは Lync Server 2013 展開ウィザードに統合されているため、次の手順で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c03e9-144">The Persistent Chat Server setup is integrated into the Lync Server 2013 Deployment wizard that provides the following instructions:</span></span></p>
<ul>
<li><p><span data-ttu-id="c03e9-145">ローカル管理ストアを展開する。</span><span class="sxs-lookup"><span data-stu-id="c03e9-145">Deploy local management store</span></span></p></li>
<li><p><span data-ttu-id="c03e9-146">常設チャットサーバーサービスをインストールする</span><span class="sxs-lookup"><span data-stu-id="c03e9-146">Install Persistent Chat Server services</span></span></p></li>
<li><p><span data-ttu-id="c03e9-147">証明書を要求および割り当てる。</span><span class="sxs-lookup"><span data-stu-id="c03e9-147">Request and assign certificates</span></span></p></li>
<li><p><span data-ttu-id="c03e9-148">サービスを実行および開始する。</span><span class="sxs-lookup"><span data-stu-id="c03e9-148">Run and start the services</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c03e9-149">ローカルの Administrators グループのメンバーであるユーザー。</span><span class="sxs-lookup"><span data-stu-id="c03e9-149">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="c03e9-150">展開ドキュメントの<a href="lync-server-2013-deploying-persistent-chat-server.md">Lync server 2013 での常設チャットサーバーの展開</a></span><span class="sxs-lookup"><span data-stu-id="c03e9-150"><a href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c03e9-151"><strong>常設チャット管理者の作成</strong></span><span class="sxs-lookup"><span data-stu-id="c03e9-151"><strong>Create a Persistent Chat administrator</strong></span></span></p></td>
<td><p><span data-ttu-id="c03e9-152">ユーザーを CsPersistentChatAdministrator セキュリティ グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="c03e9-152">Add users to the CsPersistentChatAdministrator security group.</span></span></p></td>
<td><p><span data-ttu-id="c03e9-153">ドメイン管理者のメンバーであるユーザー。</span><span class="sxs-lookup"><span data-stu-id="c03e9-153">Any user who is a member of domain administrators.</span></span></p></td>
<td><p><span data-ttu-id="c03e9-154">展開ドキュメントの<a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Lync Server 2013 での常設チャット管理者の追加</a></span><span class="sxs-lookup"><span data-stu-id="c03e9-154"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Adding a Persistent Chat administrator in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c03e9-155"><strong>常設チャット サーバーの構成</strong></span><span class="sxs-lookup"><span data-stu-id="c03e9-155"><strong>Configure Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="c03e9-156">次のようにユーザーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c03e9-156">Configure users:</span></span></p>
<ul>
<li><p><span data-ttu-id="c03e9-157">ユーザは、常設チャットサーバにアクセスするためにポリシーによって有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c03e9-157">User has to be enabled by policy to access Persistent Chat Server.</span></span> <span data-ttu-id="c03e9-158">既定では、ポリシーはすべてのユーザーに対してオフになっており、グローバル/サイト/プール/ユーザー スコープで定義できます。</span><span class="sxs-lookup"><span data-stu-id="c03e9-158">By default, the policy is turned off for all users and can be defined at global/site/pool/user scopes.</span></span></p></li>
<li><p><span data-ttu-id="c03e9-159">設定の構成</span><span class="sxs-lookup"><span data-stu-id="c03e9-159">Configure settings</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c03e9-p104">ユーザーは CsPersistentChatAdministrator のメンバーであることが必要です。ポリシーを変更するには、ユーザーは最低でも CsUserAdministrator であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="c03e9-p104">User must be a member of CsPersistentChatAdministrator. To change policy, user must be in CsUserAdministrator, at a minimum.</span></span></p></td>
<td><p><span data-ttu-id="c03e9-162">展開ドキュメントの<a href="lync-server-2013-configuring-persistent-chat-server.md">Lync server 2013 での常設チャットサーバーの構成</a></span><span class="sxs-lookup"><span data-stu-id="c03e9-162"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuring Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="c03e9-163">1つ以上の常設チャットサーバープールを展開できます。</span><span class="sxs-lookup"><span data-stu-id="c03e9-163">You can deploy one or more Persistent Chat Server pools.</span></span> <span data-ttu-id="c03e9-164">複数の常設チャットサーバープールをサポートしており、特定の地域で生成されたデータをその地域内に維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c03e9-164">We support multiple Persistent Chat Server pools for regulatory reasons whereby data generated in a given region is required to stay in that region.</span></span> <span data-ttu-id="c03e9-165">たとえば、Zurich で常設チャットサーバープールを展開し、スイスのデータに関する規制に準拠するために、ユーザーは、アクセス権を持っている常設チャットサーバープールの会議室に接続できます。</span><span class="sxs-lookup"><span data-stu-id="c03e9-165">For example, if you deploy a Persistent Chat Server pool in Chicago, and another in Zurich to comply with regulations for data in Switzerland, users can connect to rooms in both the Persistent Chat Server pools, provided they have access.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

