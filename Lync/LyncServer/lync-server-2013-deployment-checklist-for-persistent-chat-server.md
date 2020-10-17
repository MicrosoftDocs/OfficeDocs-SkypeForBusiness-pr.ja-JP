---
title: 'Lync Server 2013: 常設チャットサーバーの展開チェックリスト'
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
ms.openlocfilehash: 2399d6ce6fc17a802c8f6bc39730370948ef0253
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522744"
---
# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="04c85-102">Lync Server 2013 の常設チャットサーバーの展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="04c85-102">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04c85-103">_**トピックの最終更新日:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="04c85-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="04c85-104">Lync Server 2013 を展開する場合は、常設チャットサーバーを正しい順序で展開し、必要なすべての展開手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04c85-104">Deployment of Lync Server 2013, Persistent Chat Server requires that you deploy it in the correct sequence and that you complete all required deployment steps.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="04c85-105">展開順序</span><span class="sxs-lookup"><span data-stu-id="04c85-105">Deployment Sequence</span></span>

<span data-ttu-id="04c85-106">最初のトポロジの展開後に常設チャットサーバーを展開できます。これには、少なくとも1つの Lync Server 2013、フロントエンドプール、または1つの Lync Server 2013、Standard Edition サーバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="04c85-106">You can deploy Persistent Chat Server after you deploy your initial topology, including at least one Lync Server 2013, Front End pool or one Lync Server 2013, Standard Edition server.</span></span> <span data-ttu-id="04c85-107">このトピックでは、既存の展開に追加することによって常設チャットサーバーを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="04c85-107">This topic describes how to deploy Persistent Chat Server by adding it to an existing deployment.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="04c85-108">展開プロセス</span><span class="sxs-lookup"><span data-stu-id="04c85-108">Deployment Process</span></span>

<span data-ttu-id="04c85-109">次の表に、常設チャットサーバーを展開するための基本的な手順と、詳細情報へのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="04c85-109">The following table lists the basic steps to deploy Persistent Chat Server and provides links for more details.</span></span>

### <a name="persistent-chat-server-deployment-process"></a><span data-ttu-id="04c85-110">常設チャットサーバーの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="04c85-110">Persistent Chat Server Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04c85-111">タスク</span><span class="sxs-lookup"><span data-stu-id="04c85-111">Task</span></span></th>
<th><span data-ttu-id="04c85-112">手順</span><span class="sxs-lookup"><span data-stu-id="04c85-112">Steps</span></span></th>
<th><span data-ttu-id="04c85-113">必要な役割およびグループ メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="04c85-113">Required roles and group memberships</span></span></th>
<th><span data-ttu-id="04c85-114">関連トピック</span><span class="sxs-lookup"><span data-stu-id="04c85-114">Related topics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04c85-115"><strong>必要なハードウェアとソフトウェアのインストール</strong></span><span class="sxs-lookup"><span data-stu-id="04c85-115"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="04c85-116">システム要件を満たすハードウェアに、次のものをインストールします。</span><span class="sxs-lookup"><span data-stu-id="04c85-116">On hardware that meets system requirements, install the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="04c85-117">常設チャットサーバーのフロントエンドサーバーで、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="04c85-117">On the Persistent Chat Server Front End Servers:</span></span></p></li>
</ul>
<ul>
<li><p><span data-ttu-id="04c85-118">システム要件を満たすオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="04c85-118">An operating system that meets system requirements</span></span></p></li>
<li><p><span data-ttu-id="04c85-119">Lync Server 2013 を実行しているコンピューターのソフトウェア前提条件</span><span class="sxs-lookup"><span data-stu-id="04c85-119">Software prerequisites for computers running Lync Server 2013</span></span></p></li>
<li><p><span data-ttu-id="04c85-120">常設チャットサーバーデータベースをホストするサーバー上の SQL Server</span><span class="sxs-lookup"><span data-stu-id="04c85-120">SQL Server on the server that will host Persistent Chat Server database</span></span></p></li>
</ul>
<p><span data-ttu-id="04c85-121">常設チャットサーバーのコンプライアンスが必要な場合:</span><span class="sxs-lookup"><span data-stu-id="04c85-121">If Persistent Chat Server compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="04c85-122">常設チャットサーバーコンプライアンスデータベースをホストするサーバー上の SQL Server</span><span class="sxs-lookup"><span data-stu-id="04c85-122">SQL Server on the server that will host Persistent Chat Server compliance database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="04c85-123">ローカルの Administrators グループのメンバーであるユーザー。</span><span class="sxs-lookup"><span data-stu-id="04c85-123">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="04c85-124">「サポート」のドキュメントの「 <a href="lync-server-2013-supported-hardware.md">Lync Server 2013 でサポートされるハードウェア</a>」</span><span class="sxs-lookup"><span data-stu-id="04c85-124"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="04c85-125">「サポート」のドキュメントの「 <a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート」</a></span><span class="sxs-lookup"><span data-stu-id="04c85-125"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="04c85-126"><a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013 のシステム要件を決定する</a></span><span class="sxs-lookup"><span data-stu-id="04c85-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="04c85-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Lync Server 2013 の常設チャットサーバーの技術要件</a></span><span class="sxs-lookup"><span data-stu-id="04c85-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technical requirements for Persistent Chat Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04c85-128"><strong>常設チャットサーバーをサポートするための適切な内部トポロジの作成 (およびオプションで常設チャットコンプライアンス)</strong></span><span class="sxs-lookup"><span data-stu-id="04c85-128"><strong>Create the appropriate internal topology to support Persistent Chat Server (and optionally, Persistent Chat compliance)</strong></span></span></p></td>
<td><p><span data-ttu-id="04c85-129">トポロジビルダーを実行して、常設チャットサーバープールをトポロジに追加します。</span><span class="sxs-lookup"><span data-stu-id="04c85-129">Run Topology Builder to add a Persistent Chat Server pool to your topology:</span></span></p>
<ul>
<li><p><span data-ttu-id="04c85-130">常設チャットサーバーコンポーネントをトポロジに追加する</span><span class="sxs-lookup"><span data-stu-id="04c85-130">Add Persistent Chat Server components to the topology</span></span></p></li>
<li><p><span data-ttu-id="04c85-131">常設チャットサーバーストア (および障害復旧用のバックアップ SQL Server) 用の SQL Server データベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="04c85-131">Create a SQL Server database for the Persistent Chat Server store (and a backup SQL Server for disaster recovery)</span></span></p></li>
<li><p><span data-ttu-id="04c85-132">新しい Lync ファイルストアを定義するか、既存の Lync ファイルストアを使用して常設チャットサーバーファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="04c85-132">Define a new Lync File Store or use an existing Lync File Store for Persistent Chat Server files</span></span></p></li>
<li><p><span data-ttu-id="04c85-133">この常設チャットサーバープールに要求をルーティングできる Lync Server 2013 プールを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="04c85-133">Associate the Lync Server 2013 pool that can route requests to this Persistent Chat Server pool</span></span></p></li>
</ul>
<p><span data-ttu-id="04c85-134">常設チャットのコンプライアンスが必要な場合:</span><span class="sxs-lookup"><span data-stu-id="04c85-134">If Persistent Chat compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="04c85-135">常設チャットコンプライアンスストアの追加</span><span class="sxs-lookup"><span data-stu-id="04c85-135">Add Persistent Chat Compliance Store</span></span></p></li>
<li><p><span data-ttu-id="04c85-136">[常設チャットサーバープールの定義] チェックボックスをオンにして、コンプライアンスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="04c85-136">Click the Persistent Chat Server pool definition check box for enabling compliance</span></span></p></li>
<li><p><span data-ttu-id="04c85-137">トポロジを公開する。</span><span class="sxs-lookup"><span data-stu-id="04c85-137">Publish the topology</span></span></p></li>
</ul>
<p><span data-ttu-id="04c85-138">Standard Edition に常設チャットサーバーをインストールする場合は、常設チャットサーバープールの完全修飾ドメイン名 (FQDN) が Standard Edition サーバーと一致している必要があります。また、SQL Server データベースは、Standard Edition サーバー上の SQL Server Express インスタンスに併置されます。</span><span class="sxs-lookup"><span data-stu-id="04c85-138">If you install Persistent Chat Server on Standard Edition, the fully qualified domain name (FQDN) of the Persistent Chat Server pool must match the Standard Edition server, and the SQL Server databases are collocated on the SQL Server Express instance on the Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="04c85-139">トポロジを定義するには、ローカルの Users グループのメンバーであるアカウント。</span><span class="sxs-lookup"><span data-stu-id="04c85-139">To define a topology, an account that is a member of the local Users group.</span></span></p>
<p><span data-ttu-id="04c85-140">トポロジを公開するには、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーであり、ユーザーは、常設チャットサーバーファイル用の Lync ファイルストアに対するフルコントロールのアクセス許可 (読み取り/書き込み/変更) を所有している必要があります (これにより、トポロジビルダーは必要な Dacl を構成できます)。</span><span class="sxs-lookup"><span data-stu-id="04c85-140">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and the user should also have full control permissions (read/write/modify) on the Lync File Store for Persistent Chat Server files (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="04c85-141">展開のドキュメントの「 <a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 での展開への常設チャットサーバーの追加」</a></span><span class="sxs-lookup"><span data-stu-id="04c85-141"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04c85-142"><strong>常設チャット サーバーの展開</strong></span><span class="sxs-lookup"><span data-stu-id="04c85-142"><strong>Deploy Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="04c85-143">常設チャットサーバーを実行しているすべてのコンピューターで Lync Server セットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="04c85-143">Run the Lync Server setup on all the computers running Persistent Chat Server.</span></span> <span data-ttu-id="04c85-144">常設チャットサーバーのセットアップは、Lync Server 2013 展開ウィザードに統合され、次の手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="04c85-144">The Persistent Chat Server setup is integrated into the Lync Server 2013 Deployment wizard that provides the following instructions:</span></span></p>
<ul>
<li><p><span data-ttu-id="04c85-145">ローカル管理ストアを展開する。</span><span class="sxs-lookup"><span data-stu-id="04c85-145">Deploy local management store</span></span></p></li>
<li><p><span data-ttu-id="04c85-146">常設チャットサーバーサービスのインストール</span><span class="sxs-lookup"><span data-stu-id="04c85-146">Install Persistent Chat Server services</span></span></p></li>
<li><p><span data-ttu-id="04c85-147">証明書を要求および割り当てる。</span><span class="sxs-lookup"><span data-stu-id="04c85-147">Request and assign certificates</span></span></p></li>
<li><p><span data-ttu-id="04c85-148">サービスを実行および開始する。</span><span class="sxs-lookup"><span data-stu-id="04c85-148">Run and start the services</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="04c85-149">ローカルの Administrators グループのメンバーであるユーザー。</span><span class="sxs-lookup"><span data-stu-id="04c85-149">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="04c85-150">展開のドキュメントの「 <a href="lync-server-2013-deploying-persistent-chat-server.md">Lync server 2013 での常設チャットサーバーの展開</a>」</span><span class="sxs-lookup"><span data-stu-id="04c85-150"><a href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04c85-151"><strong>常設チャット管理者の作成</strong></span><span class="sxs-lookup"><span data-stu-id="04c85-151"><strong>Create a Persistent Chat administrator</strong></span></span></p></td>
<td><p><span data-ttu-id="04c85-152">ユーザーを CsPersistentChatAdministrator セキュリティ グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="04c85-152">Add users to the CsPersistentChatAdministrator security group.</span></span></p></td>
<td><p><span data-ttu-id="04c85-153">ドメイン管理者のメンバーであるユーザー。</span><span class="sxs-lookup"><span data-stu-id="04c85-153">Any user who is a member of domain administrators.</span></span></p></td>
<td><p><span data-ttu-id="04c85-154">「展開」のドキュメントの「 <a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Lync Server 2013 での常設チャット管理者の追加」</a></span><span class="sxs-lookup"><span data-stu-id="04c85-154"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Adding a Persistent Chat administrator in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04c85-155"><strong>常設チャット サーバーの構成</strong></span><span class="sxs-lookup"><span data-stu-id="04c85-155"><strong>Configure Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="04c85-156">次のようにユーザーを構成します。</span><span class="sxs-lookup"><span data-stu-id="04c85-156">Configure users:</span></span></p>
<ul>
<li><p><span data-ttu-id="04c85-157">常設チャットサーバーにアクセスするには、ポリシーによってユーザーを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04c85-157">User has to be enabled by policy to access Persistent Chat Server.</span></span> <span data-ttu-id="04c85-158">既定では、ポリシーはすべてのユーザーに対してオフになっており、グローバル/サイト/プール/ユーザー スコープで定義できます。</span><span class="sxs-lookup"><span data-stu-id="04c85-158">By default, the policy is turned off for all users and can be defined at global/site/pool/user scopes.</span></span></p></li>
<li><p><span data-ttu-id="04c85-159">設定の構成</span><span class="sxs-lookup"><span data-stu-id="04c85-159">Configure settings</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="04c85-p104">ユーザーは CsPersistentChatAdministrator のメンバーである必要がある。ポリシーを変更するには、ユーザーは最低でも CsUserAdministrator である必要がある。</span><span class="sxs-lookup"><span data-stu-id="04c85-p104">User must be a member of CsPersistentChatAdministrator. To change policy, user must be in CsUserAdministrator, at a minimum.</span></span></p></td>
<td><p><span data-ttu-id="04c85-162">「展開」のドキュメントの「 <a href="lync-server-2013-configuring-persistent-chat-server.md">Lync server 2013 での常設チャットサーバーの構成</a>」</span><span class="sxs-lookup"><span data-stu-id="04c85-162"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuring Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="04c85-163">1つまたは複数の常設チャットサーバープールを展開できます。</span><span class="sxs-lookup"><span data-stu-id="04c85-163">You can deploy one or more Persistent Chat Server pools.</span></span> <span data-ttu-id="04c85-164">複数の常設チャットサーバープールをサポートしています。規制上の理由から、特定の地域で生成されたデータはその地域にとどまる必要があります。</span><span class="sxs-lookup"><span data-stu-id="04c85-164">We support multiple Persistent Chat Server pools for regulatory reasons whereby data generated in a given region is required to stay in that region.</span></span> <span data-ttu-id="04c85-165">たとえば、永続的なチャットサーバープールをシカゴに展開し、Zurich フルタの別のユーザーがスイスのデータに対する規則に準拠している場合、ユーザーは、アクセス権を持っている限り、両方の常設チャットサーバープールのルームに接続できます。</span><span class="sxs-lookup"><span data-stu-id="04c85-165">For example, if you deploy a Persistent Chat Server pool in Chicago, and another in Zurich to comply with regulations for data in Switzerland, users can connect to rooms in both the Persistent Chat Server pools, provided they have access.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

