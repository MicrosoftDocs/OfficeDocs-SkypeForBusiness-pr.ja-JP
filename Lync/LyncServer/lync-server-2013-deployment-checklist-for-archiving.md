---
title: 'Lync Server 2013: アーカイブの展開チェックリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e55e2471a71c985861c35c4ec2e07582dbfa0f23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a><span data-ttu-id="b62ce-102">Lync Server 2013 のアーカイブの展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="b62ce-102">Deployment checklist for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b62ce-103">_**最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="b62ce-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="b62ce-104">アーカイブは、Lync Server 2013 展開の各フロントエンドサーバーに自動的にインストールされますが、使用する前に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b62ce-104">Archiving is automatically installed on each Front End Server in your Lync Server 2013 deployment, but you still need to set it up before you can use it.</span></span> <span data-ttu-id="b62ce-105">このセクションで概要を設定するために必要な手順は、アーカイブの展開を構成するものです。</span><span class="sxs-lookup"><span data-stu-id="b62ce-105">The steps required to set it up, as summarized in this section, constitute the deployment of Archiving.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="b62ce-106">展開シーケンス</span><span class="sxs-lookup"><span data-stu-id="b62ce-106">Deployment Sequence</span></span>

<span data-ttu-id="b62ce-107">アーカイブの設定方法は、選択したストレージオプションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b62ce-107">How you set up Archiving depends on which storage option you choose:</span></span>

  - <span data-ttu-id="b62ce-108">展開のすべてのユーザーに対して Microsoft Exchange 統合を使用している場合は、ユーザーの Lync Server 2013 アーカイブポリシーを構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b62ce-108">If you use Microsoft Exchange integration for all users in your deployment, you don’t need to configure Lync Server 2013 Archiving policies for your users.</span></span> <span data-ttu-id="b62ce-109">代わりに、exchange 2013 を使用しているユーザーのアーカイブをサポートするように Exchange のインプレースホールドポリシーを構成し、メールボックスがインプレース保持されるようにします。</span><span class="sxs-lookup"><span data-stu-id="b62ce-109">Instead, configure your Exchange In-Place Hold policies to support archiving for users homed on Exchange 2013, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="b62ce-110">これらのポリシーの構成の詳細については、Exchange 2013 の製品に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b62ce-110">For details about configuring these policies, see the Exchange 2013 product documentation.</span></span>

  - <span data-ttu-id="b62ce-111">展開内のすべてのユーザーに対して Microsoft Exchange 統合を使用していない場合は、お客様のトポロジに Lync Server アーカイブデータベース (SQL Server データベース) を追加し、それを公開して、ユーザーのポリシーと設定を構成する必要があります。それらのユーザーのデータをアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="b62ce-111">If you do not use Microsoft Exchange integration for all users in your deployment, you need to add Lync Server Archiving databases (SQL Server databases) to your topology and then publish it, as well as configure policies and settings for your users, before you can archive data for those users.</span></span> <span data-ttu-id="b62ce-112">最初のトポロジを展開するとき、または少なくとも1つのフロントエンドプールまたは Standard Edition サーバーを展開した後で、アーカイブデータベースを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="b62ce-112">You can deploy Archiving databases at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span> <span data-ttu-id="b62ce-113">このドキュメントでは、アーカイブデータベースを既存の展開に追加して展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b62ce-113">This document describes how to deploy Archiving databases by adding them to an existing deployment.</span></span>

<span data-ttu-id="b62ce-114">1つのフロントエンドプールまたは Standard Edition サーバーでアーカイブを有効にしている場合、展開内の他のすべてのフロントエンドプールおよび Standard Edition サーバーでアーカイブを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b62ce-114">If you enable archiving in one Front End pool or Standard Edition server, you should enable it for all other Front End pools and Standard Edition servers in your deployment.</span></span> <span data-ttu-id="b62ce-115">その理由は、通信のアーカイブが必要なユーザーは、別のプールでホストされるグループ IM 会話や会議に招待される可能性があるからです。</span><span class="sxs-lookup"><span data-stu-id="b62ce-115">This is because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool.</span></span> <span data-ttu-id="b62ce-116">会話や会議がホストされているプールでアーカイブが有効になっていない場合は、セッション全体をアーカイブすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b62ce-116">If archiving is not enabled on the pool where the conversation or meeting is hosted, the complete session may not be archived.</span></span> <span data-ttu-id="b62ce-117">このような場合、アーカイブが有効なユーザーの IM はアーカイブできますが、会議コンテンツ ファイルや会議参加または退出イベントはアーカイブできません。</span><span class="sxs-lookup"><span data-stu-id="b62ce-117">In these cases, IMs with archiving-enabled users still can be archived, but not for conferencing content files, and conference join or leave events.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b62ce-118">コンプライアンス上の理由からアーカイブが重要である場合は、アーカイブを展開し、ポリシーおよびその他のオプションを適切なレベルで構成して、適切なユーザー全員に対して有効にしてから、Lync Server 2013 のユーザーを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b62ce-118">If archiving is critical in your organization for compliance reasons, be sure to deploy Archiving, configure policies and other options at the appropriate level, and enable it for all appropriate users, before you enable those users for Lync Server 2013.</span></span>



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a><span data-ttu-id="b62ce-119">アーカイブ展開プロセス</span><span class="sxs-lookup"><span data-stu-id="b62ce-119">Archiving Deployment Process</span></span>

<span data-ttu-id="b62ce-120">次の表に、既存のトポロジにアーカイブを展開するために必要な手順の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="b62ce-120">The following table provides an overview of the steps required to deploy archiving in an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b62ce-121">段階</span><span class="sxs-lookup"><span data-stu-id="b62ce-121">Phase</span></span></th>
<th><span data-ttu-id="b62ce-122">手順</span><span class="sxs-lookup"><span data-stu-id="b62ce-122">Steps</span></span></th>
<th><span data-ttu-id="b62ce-123">役割とグループ メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="b62ce-123">Roles and group memberships</span></span></th>
<th><span data-ttu-id="b62ce-124">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="b62ce-124">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b62ce-125"><strong>必要なハードウェアとソフトウェアのインストール</strong></span><span class="sxs-lookup"><span data-stu-id="b62ce-125"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b62ce-126">Microsoft Exchange 統合 (一部またはすべてのユーザーのアーカイブストレージに Exchange 2013 を使用) を使用するには、既存の Exchange 2013 の展開が必要です。</span><span class="sxs-lookup"><span data-stu-id="b62ce-126">To use Microsoft Exchange integration (using Exchange 2013 for archiving storage for some or all users), you need an existing Exchange 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="b62ce-127">一部またはすべてのユーザーのアーカイブストレージに個別のアーカイブデータベース (SQL Server データベースを使用) を使用するには、アーカイブデータを格納するサーバー上の SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b62ce-127">To use separate Archiving databases (using SQL Server databases) for archiving storage for some or all users, SQL Server on the server that will store archiving data.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="b62ce-128">アーカイブは、エンタープライズプールと Standard Edition サーバーのフロントエンドサーバー上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="b62ce-128">Archiving runs on Front End Servers of an Enterprise pool and Standard Edition servers.</span></span> <span data-ttu-id="b62ce-129">これらのサーバーのインストールに必要なもの以外には、追加のハードウェア要件やソフトウェア要件はありません。</span><span class="sxs-lookup"><span data-stu-id="b62ce-129">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span>


</div></td>
<td><p><span data-ttu-id="b62ce-130">ローカルの Administrators グループのメンバーであるドメイン ユーザー。</span><span class="sxs-lookup"><span data-stu-id="b62ce-130">Domain user who is a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="b62ce-131"><a href="lync-server-2013-supported-hardware.md">サポートされているドキュメントの Lync Server 2013 でサポートされているハードウェア</a>。</span><span class="sxs-lookup"><span data-stu-id="b62ce-131"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="b62ce-132">サポートドキュメントの<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート</a>。</span><span class="sxs-lookup"><span data-stu-id="b62ce-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="b62ce-133">計画ドキュメントの<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 でのアーカイブの技術要件</a>。</span><span class="sxs-lookup"><span data-stu-id="b62ce-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="b62ce-134">展開ドキュメントの<a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Lync Server 2013 でアーカイブ用にシステムとインフラストラクチャ</a>をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="b62ce-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Setting up systems and infrastructure for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="b62ce-135">サポートドキュメントの<a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Lync server 2013 での Exchange Server と SharePoint の統合のサポート</a>。</span><span class="sxs-lookup"><span data-stu-id="b62ce-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange Server and SharePoint integration support in Lync Server 2013</a> in the Supportability documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b62ce-136"><strong>アーカイブをサポートする適切な内部トポロジを作成します (展開のすべてのユーザーに対して Microsoft Exchange 統合を使用していない場合のみ)。</strong></span><span class="sxs-lookup"><span data-stu-id="b62ce-136"><strong>Create the appropriate internal topology to support archiving (only if not using Microsoft Exchange integration for all users in your deployment)</strong></span></span></p></td>
<td><p><span data-ttu-id="b62ce-137">トポロジビルダーを実行して、Lync Server 2013 アーカイブデータベース (SQL Server データベース) をトポロジに追加してから、トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="b62ce-137">Run Topology Builder to add Lync Server 2013 Archiving databases (SQL Server databases) to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="b62ce-138">アーカイブデータベースを取り込むためのトポロジを定義するには、ローカルユーザーグループのメンバーであるアカウント。</span><span class="sxs-lookup"><span data-stu-id="b62ce-138">To define a topology to incorporate Archiving databases, an account that is a member of the local users group.</span></span></p>
<p><span data-ttu-id="b62ce-139">トポロジを公開するには、ドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーであり、Lync Server 2013 ファイルストアに使用するフルコントロール権限 (読み取り/書き込み/変更) を持つアカウント (トポロジビルダーが必要な Dacl を構成できるようにします) を公開します。</span><span class="sxs-lookup"><span data-stu-id="b62ce-139">To publish the topology, an account that is a member of the domain admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="b62ce-140">展開ドキュメントの<a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">既存の Lync Server 2013 展開にアーカイブデータベースを追加する</a></span><span class="sxs-lookup"><span data-stu-id="b62ce-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adding Archiving databases to an existing Lync Server 2013 Deployment</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b62ce-141"><strong>サーバー間認証を構成する (Microsoft Exchange 統合を使用している場合のみ)</strong></span><span class="sxs-lookup"><span data-stu-id="b62ce-141"><strong>Configure server-to-server authentication (only if using Microsoft Exchange integration)</strong></span></span></p></td>
<td><p><span data-ttu-id="b62ce-142">Lync Server 2013 と Exchange 2013 の間の認証を有効にするようにサーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="b62ce-142">Configure servers to enable authentication between Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="b62ce-143">アーカイブを有効にする前に<strong>、CsExchangeStorageConnectivity testuser_sipUri –フォルダー収集</strong>を実行して、Exchange アーカイブストレージの接続を検証することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b62ce-143">We recommend running <strong>Test-CsExchangeStorageConnectivity testuser_sipUri –Folder Dumpster</strong> to validate Exchange Archiving storage connectivity before enabling archiving.</span></span></p></td>
<td><p><span data-ttu-id="b62ce-144">サーバーで証明書を管理するための適切なアクセス許可のあるアカウント。</span><span class="sxs-lookup"><span data-stu-id="b62ce-144">An account with the appropriate permissions for managing certificates on the servers.</span></span></p></td>
<td><p><span data-ttu-id="b62ce-145">展開ドキュメントまたは運用ドキュメントの<a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Lync server 2013 でサーバー間認証 (OAuth) とパートナーアプリケーションを管理</a>します。</span><span class="sxs-lookup"><span data-stu-id="b62ce-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</a> in the Deployment documentation or the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b62ce-146"><strong>アーカイブポリシーと構成を構成する</strong></span><span class="sxs-lookup"><span data-stu-id="b62ce-146"><strong>Configure archiving policies and configurations</strong></span></span></p></td>
<td><p><span data-ttu-id="b62ce-147">Microsoft Exchange 統合を使用するかどうか、グローバルポリシー、サイトとユーザーのポリシー (すべてのデータストレージに対して Microsoft Exchange の統合を使用していない場合)、および重要なモードやデータなどの特定のアーカイブオプションを含むアーカイブを構成します。エクスポートと削除。</span><span class="sxs-lookup"><span data-stu-id="b62ce-147">Configure archiving, including whether to use Microsoft Exchange integration, the global policy and any site and user policies (when not using Microsoft Exchange integration for all data storage), and specific archiving options, such as critical mode and data export and purging.</span></span></p>
<p><span data-ttu-id="b62ce-148">Microsoft Exchange 統合を使用している場合は、必要に応じて、Exchange のインプレースホールドポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="b62ce-148">If using Microsoft Exchange integration, configure Exchange In-Place Hold policies as appropriate.</span></span></p></td>
<td><p><span data-ttu-id="b62ce-149">RTCUniversalServerAdmins グループ (Windows PowerShell のみ)。または、CSArchivingAdministrator の役割または CSAdministrator の役割にユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b62ce-149">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the CSArchivingAdministrator or CSAdministrator role.</span></span></p></td>
<td><p><span data-ttu-id="b62ce-150">展開ドキュメントの<a href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013 でアーカイブのサポートを構成</a>します。</span><span class="sxs-lookup"><span data-stu-id="b62ce-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="b62ce-151">Exchange 製品ドキュメント (Microsoft Exchange 統合を使用している場合)。</span><span class="sxs-lookup"><span data-stu-id="b62ce-151">Exchange product documentation (if using Microsoft Exchange integration).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a><span data-ttu-id="b62ce-152">さまざまなフォレストでの Lync Server と Microsoft Exchange の展開</span><span class="sxs-lookup"><span data-stu-id="b62ce-152">Deploying Lync Server and Microsoft Exchange in Different Forests</span></span>

<span data-ttu-id="b62ce-153">Microsoft Exchange Server が Lync Server と同じフォレストに展開されていない場合は、次の Exchange Active Directory 属性が Lync Server が展開されているフォレストと同期されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b62ce-153">If Microsoft Exchange Server is not deployed in the same forest as Lync Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Lync Server is deployed:</span></span>

1.  <span data-ttu-id="b62ce-154">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="b62ce-154">msExchUserHoldPolicies</span></span>

2.  <span data-ttu-id="b62ce-155">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="b62ce-155">proxyAddresses</span></span>

<span data-ttu-id="b62ce-p107">これは複数値の属性です。この属性を同期するときは、値を置き換えるのではなく値をマージして、既存の値が失われないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b62ce-p107">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

