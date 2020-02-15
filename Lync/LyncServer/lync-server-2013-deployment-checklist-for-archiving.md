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
ms.openlocfilehash: 275556e6be613d2dfe23cf245e75c725286e0c02
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a><span data-ttu-id="c1b8e-102">Lync Server 2013 でのアーカイブの展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="c1b8e-102">Deployment checklist for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1b8e-103">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="c1b8e-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="c1b8e-104">アーカイブは、Lync Server 2013 展開の各フロントエンドサーバーに自動的にインストールされますが、使用する前に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-104">Archiving is automatically installed on each Front End Server in your Lync Server 2013 deployment, but you still need to set it up before you can use it.</span></span> <span data-ttu-id="c1b8e-105">ここで説明するセットアップに必要な手順では、アーカイブの展開を構成します。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-105">The steps required to set it up, as summarized in this section, constitute the deployment of Archiving.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="c1b8e-106">展開の順序</span><span class="sxs-lookup"><span data-stu-id="c1b8e-106">Deployment Sequence</span></span>

<span data-ttu-id="c1b8e-107">アーカイブのセットアップ方法は、選択するストレージ オプションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-107">How you set up Archiving depends on which storage option you choose:</span></span>

  - <span data-ttu-id="c1b8e-108">展開内のすべてのユーザーに対して Microsoft Exchange 統合を使用する場合は、Lync Server 2013 アーカイブポリシーをユーザーに対して構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-108">If you use Microsoft Exchange integration for all users in your deployment, you don’t need to configure Lync Server 2013 Archiving policies for your users.</span></span> <span data-ttu-id="c1b8e-109">代わりに、exchange 2013 に所属するユーザーのアーカイブをサポートするように Exchange のインプレース保持ポリシーを構成します。メールボックスはインプレース保持に配置されています。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-109">Instead, configure your Exchange In-Place Hold policies to support archiving for users homed on Exchange 2013, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="c1b8e-110">これらのポリシーの構成の詳細については、「Exchange 2013 製品のドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-110">For details about configuring these policies, see the Exchange 2013 product documentation.</span></span>

  - <span data-ttu-id="c1b8e-111">展開内のすべてのユーザーに対して Microsoft Exchange 統合を使用しない場合は、Lync Server アーカイブデータベース (SQL Server データベース) をトポロジに追加してから発行し、ユーザーのポリシーと設定を構成する必要があります。その前に、これらのユーザーのデータをアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-111">If you do not use Microsoft Exchange integration for all users in your deployment, you need to add Lync Server Archiving databases (SQL Server databases) to your topology and then publish it, as well as configure policies and settings for your users, before you can archive data for those users.</span></span> <span data-ttu-id="c1b8e-112">アーカイブデータベースは、初期トポロジを展開するとき、または少なくとも1つのフロントエンドプールまたは Standard Edition サーバーを展開した後に展開できます。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-112">You can deploy Archiving databases at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span> <span data-ttu-id="c1b8e-113">このドキュメントでは、アーカイブデータベースを既存の展開に追加して展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-113">This document describes how to deploy Archiving databases by adding them to an existing deployment.</span></span>

<span data-ttu-id="c1b8e-p104">1 つのフロントエンド プールまたは Standard Edition サーバーでアーカイブを有効にする場合、展開内の他のすべてのフロントエンド プールおよび Standard Edition サーバーに対してアーカイブを有効にする必要があります。これは、通信をアーカイブする必要があるユーザーは、別のプールでホストされるグループ IM 会話やミーティングに招待される可能性があるためです。会話やミーティングがホストされているプールでアーカイブが有効になっていない場合は、完全なセッションをアーカイブすることはできません。このような場合、アーカイブが有効なユーザーの IM はアーカイブできますが、会議コンテンツ ファイルおよび会議参加または退出イベントはアーカイブできません。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-p104">If you enable archiving in one Front End pool or Standard Edition server, you should enable it for all other Front End pools and Standard Edition servers in your deployment. This is because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool. If archiving is not enabled on the pool where the conversation or meeting is hosted, the complete session may not be archived. In these cases, IMs with archiving-enabled users still can be archived, but not for conferencing content files, and conference join or leave events.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c1b8e-118">コンプライアンス上の理由からアーカイブが重要な場合は、アーカイブを展開し、ポリシーおよびその他のオプションを適切なレベルで構成して、適切なユーザーすべてに対して有効にしてから、Lync Server 2013 のユーザーを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-118">If archiving is critical in your organization for compliance reasons, be sure to deploy Archiving, configure policies and other options at the appropriate level, and enable it for all appropriate users, before you enable those users for Lync Server 2013.</span></span>



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a><span data-ttu-id="c1b8e-119">アーカイブの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="c1b8e-119">Archiving Deployment Process</span></span>

<span data-ttu-id="c1b8e-120">次の表に、既存のトポロジにアーカイブを展開するために必要な手順の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-120">The following table provides an overview of the steps required to deploy archiving in an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c1b8e-121">フェーズ</span><span class="sxs-lookup"><span data-stu-id="c1b8e-121">Phase</span></span></th>
<th><span data-ttu-id="c1b8e-122">手順</span><span class="sxs-lookup"><span data-stu-id="c1b8e-122">Steps</span></span></th>
<th><span data-ttu-id="c1b8e-123">役割とグループ メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="c1b8e-123">Roles and group memberships</span></span></th>
<th><span data-ttu-id="c1b8e-124">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="c1b8e-124">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c1b8e-125"><strong>必要なハードウェアとソフトウェアのインストール</strong></span><span class="sxs-lookup"><span data-stu-id="c1b8e-125"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c1b8e-126">Microsoft Exchange 統合 (Exchange 2013 を使用して一部またはすべてのユーザーのストレージをアーカイブする) を使用するには、既存の Exchange 2013 展開が必要です。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-126">To use Microsoft Exchange integration (using Exchange 2013 for archiving storage for some or all users), you need an existing Exchange 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="c1b8e-127">一部またはすべてのユーザーのストレージをアーカイブするために別のアーカイブ データベースを使用するには (SQL Server データベースを使用する場合)、アーカイブ データを格納するサーバーに SQL Server が必要です。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-127">To use separate Archiving databases (using SQL Server databases) for archiving storage for some or all users, SQL Server on the server that will store archiving data.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="c1b8e-p105">アーカイブは、エンタープライズ プールのフロントエンド サーバーと Standard Edition サーバー上で実行されます。これらのサーバーのインストールに必要なもの以外には、追加のハードウェア要件やソフトウェア要件はありません。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-p105">Archiving runs on Front End Servers of an Enterprise pool and Standard Edition servers. It has no additional hardware or software requirements beyond what is required to install those servers.</span></span>


</div></td>
<td><p><span data-ttu-id="c1b8e-130">ローカルの Administrators グループのメンバーであるドメイン ユーザー。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-130">Domain user who is a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="c1b8e-131">「サポート」のドキュメントの「 <a href="lync-server-2013-supported-hardware.md">Lync Server 2013 でサポートされているハードウェア</a>」。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-131"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="c1b8e-132">「サポート」のドキュメントの「 <a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート」</a> 。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="c1b8e-133">「計画」のドキュメントの「 <a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 でのアーカイブの技術要件</a>」。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="c1b8e-134">「展開」のドキュメントの「 <a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Lync Server 2013 でのアーカイブのためのシステムとインフラストラクチャの</a>セットアップ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Setting up systems and infrastructure for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="c1b8e-135">「サポート」のドキュメントの「 <a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Lync server 2013 での Exchange Server および SharePoint の統合のサポート</a>」。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange Server and SharePoint integration support in Lync Server 2013</a> in the Supportability documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1b8e-136"><strong>アーカイブをサポートするために適切な内部トポロジを作成します (展開内のすべてのユーザーに対して Microsoft Exchange 統合を使用していない場合のみ)。</strong></span><span class="sxs-lookup"><span data-stu-id="c1b8e-136"><strong>Create the appropriate internal topology to support archiving (only if not using Microsoft Exchange integration for all users in your deployment)</strong></span></span></p></td>
<td><p><span data-ttu-id="c1b8e-137">トポロジビルダーを実行して、Lync Server 2013 アーカイブデータベース (SQL Server データベース) をトポロジに追加してから、トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-137">Run Topology Builder to add Lync Server 2013 Archiving databases (SQL Server databases) to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="c1b8e-138">アーカイブ データベースを組み込むためのトポロジを定義する場合は、ローカル ユーザー グループのメンバーであるアカウント。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-138">To define a topology to incorporate Archiving databases, an account that is a member of the local users group.</span></span></p>
<p><span data-ttu-id="c1b8e-139">トポロジを公開するには、domain admins グループおよび RTCUniversalServerAdmins グループのメンバーであり、Lync Server 2013 ファイルストアに対して使用されるファイル共有のフルコントロールアクセス許可 (読み取り/書き込み/変更) を持つアカウント (トポロジビルダーが必要な Dacl を構成できるようにするため)。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-139">To publish the topology, an account that is a member of the domain admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="c1b8e-140">「展開」のドキュメントの「<a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">既存の Lync Server 2013 展開へのアーカイブデータベースの追加」を</a>参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adding Archiving databases to an existing Lync Server 2013 Deployment</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1b8e-141"><strong>サーバー間認証を構成する (Microsoft Exchange 統合を使用する場合のみ)</strong></span><span class="sxs-lookup"><span data-stu-id="c1b8e-141"><strong>Configure server-to-server authentication (only if using Microsoft Exchange integration)</strong></span></span></p></td>
<td><p><span data-ttu-id="c1b8e-142">Lync Server 2013 と Exchange 2013 の間の認証を有効にするようにサーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-142">Configure servers to enable authentication between Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="c1b8e-143">アーカイブを有効にする前に、Exchange アーカイブストレージの接続を検証するには、 <strong>CsExchangeStorageConnectivity testuser_sipUri-フォルダー収集</strong>を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-143">We recommend running <strong>Test-CsExchangeStorageConnectivity testuser_sipUri –Folder Dumpster</strong> to validate Exchange Archiving storage connectivity before enabling archiving.</span></span></p></td>
<td><p><span data-ttu-id="c1b8e-144">サーバーで証明書を管理するための適切なアクセス許可のあるアカウント。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-144">An account with the appropriate permissions for managing certificates on the servers.</span></span></p></td>
<td><p><span data-ttu-id="c1b8e-145">「展開」のドキュメントまたは「操作」のドキュメントの<a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">「Lync server 2013 でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理」</a>を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</a> in the Deployment documentation or the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1b8e-146"><strong>アーカイブ ポリシーと設定の構成</strong></span><span class="sxs-lookup"><span data-stu-id="c1b8e-146"><strong>Configure archiving policies and configurations</strong></span></span></p></td>
<td><p><span data-ttu-id="c1b8e-147">アーカイブを構成する (Microsoft Exchange 統合を使用するかどうか、グローバルポリシーとサイトポリシーおよびユーザーポリシーを (すべてのデータ記憶域に対して Microsoft Exchange 統合を使用しない場合)、および特定のアーカイブオプション (重要なモードやデータなど) を含む)。エクスポートと削除。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-147">Configure archiving, including whether to use Microsoft Exchange integration, the global policy and any site and user policies (when not using Microsoft Exchange integration for all data storage), and specific archiving options, such as critical mode and data export and purging.</span></span></p>
<p><span data-ttu-id="c1b8e-148">Microsoft Exchange 統合を使用する場合は、必要に応じて Exchange のインプレース保持ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-148">If using Microsoft Exchange integration, configure Exchange In-Place Hold policies as appropriate.</span></span></p></td>
<td><p><span data-ttu-id="c1b8e-149">RTCUniversalServerAdmins グループ (Windows PowerShell のみ)。あるいは、CSArchivingAdministrator の役割または CSAdministrator の役割にユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-149">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the CSArchivingAdministrator or CSAdministrator role.</span></span></p></td>
<td><p><span data-ttu-id="c1b8e-150">「展開」のドキュメントの「 <a href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013 でのアーカイブのサポートの構成</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="c1b8e-151">Exchange 製品ドキュメント (Microsoft Exchange 統合を使用している場合)。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-151">Exchange product documentation (if using Microsoft Exchange integration).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a><span data-ttu-id="c1b8e-152">異なるフォレストへの Lync Server と Microsoft Exchange の展開</span><span class="sxs-lookup"><span data-stu-id="c1b8e-152">Deploying Lync Server and Microsoft Exchange in Different Forests</span></span>

<span data-ttu-id="c1b8e-153">Microsoft Exchange Server が Lync Server と同じフォレストに展開されていない場合は、次の Exchange Active Directory 属性が Lync Server が展開されているフォレストに同期されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-153">If Microsoft Exchange Server is not deployed in the same forest as Lync Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Lync Server is deployed:</span></span>

1.  <span data-ttu-id="c1b8e-154">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="c1b8e-154">msExchUserHoldPolicies</span></span>

2.  <span data-ttu-id="c1b8e-155">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="c1b8e-155">proxyAddresses</span></span>

<span data-ttu-id="c1b8e-p107">これは複数値の属性です。この属性を同期するときは、値を置き換えるのではなく値をマージして、既存の値が失われないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1b8e-p107">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

