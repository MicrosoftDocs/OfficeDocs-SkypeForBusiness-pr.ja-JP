---
title: 'Lync Server 2013: 通話受付管理の展開チェックリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bf88529734530e70c4d0536d5337395ff0742d2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="cf689-102">Lync Server 2013 の通話受付管理の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="cf689-102">Deployment checklist for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf689-103">_**最終更新日:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="cf689-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="cf689-104">通話受付制御 (CAC) を効率的に計画するには、次の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf689-104">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="cf689-105">CAC を展開するための前提条件。</span><span class="sxs-lookup"><span data-stu-id="cf689-105">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="cf689-106">CAC と構成の決定に必要な情報。展開前に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf689-106">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="cf689-107">通話受付制御の展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="cf689-107">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="cf689-108">通話受付制御を展開する前に、既に Lync Server 2013 内部サーバー (フロントエンドプールまたは Standard Edition サーバー) を展開している必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf689-108">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="cf689-109">通話受付制御の情報要件</span><span class="sxs-lookup"><span data-stu-id="cf689-109">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="cf689-110">次の表は、通話受付制御の展開に必要な情報をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="cf689-110">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="cf689-111">通話受付制御の展開に関する情報要件</span><span class="sxs-lookup"><span data-stu-id="cf689-111">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf689-112">情報</span><span class="sxs-lookup"><span data-stu-id="cf689-112">Information</span></span></th>
<th><span data-ttu-id="cf689-113">必要な情報の概要</span><span class="sxs-lookup"><span data-stu-id="cf689-113">Summary of Information Required</span></span></th>
<th><span data-ttu-id="cf689-114">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="cf689-114">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf689-115">組織で必要な Lync Server 機能</span><span class="sxs-lookup"><span data-stu-id="cf689-115">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="cf689-116">組織でサポートされる機能</span><span class="sxs-lookup"><span data-stu-id="cf689-116">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="cf689-117">個々のユーザーに対して有効になる機能</span><span class="sxs-lookup"><span data-stu-id="cf689-117">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cf689-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013 での通話受付管理サービス要件の定義</a></span><span class="sxs-lookup"><span data-stu-id="cf689-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf689-119">展開するトポロジとコンポーネント</span><span class="sxs-lookup"><span data-stu-id="cf689-119">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="cf689-120">CAC 関連のコンポーネントは、Lync Server 2013 の一部として自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="cf689-120">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cf689-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013 での通話受付管理サービス要件の定義</a></span><span class="sxs-lookup"><span data-stu-id="cf689-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf689-122">システム要件</span><span class="sxs-lookup"><span data-stu-id="cf689-122">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="cf689-123">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="cf689-123">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="cf689-124">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="cf689-124">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="cf689-125">Collocation の要件</span><span class="sxs-lookup"><span data-stu-id="cf689-125">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cf689-126"><a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013 システム要件の決定</a></span><span class="sxs-lookup"><span data-stu-id="cf689-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf689-127">インフラストラクチャの要件</span><span class="sxs-lookup"><span data-stu-id="cf689-127">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="cf689-128">CAC では、特定のインフラストラクチャ要件は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="cf689-128">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cf689-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Lync Server 2013 での通話受付管理のインフラストラクチャ要件</a></span><span class="sxs-lookup"><span data-stu-id="cf689-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf689-130">ネットワークインターフェイスの要件</span><span class="sxs-lookup"><span data-stu-id="cf689-130">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="cf689-131">内部と外部のインターフェイス情報</span><span class="sxs-lookup"><span data-stu-id="cf689-131">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="cf689-132">ルーティング情報 (NextHop ブログの情報<a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>を含む、Microsoft Lync Server チームの顧客対応チャネル)</span><span class="sxs-lookup"><span data-stu-id="cf689-132">Routing information (including information on the NextHop blog at <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cf689-133"><a href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013 での外部ユーザー アクセスの展開</a></span><span class="sxs-lookup"><span data-stu-id="cf689-133"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf689-134">展開戦略</span><span class="sxs-lookup"><span data-stu-id="cf689-134">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="cf689-135">展開シーケンス</span><span class="sxs-lookup"><span data-stu-id="cf689-135">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="cf689-136">ワークグループまたはドメイン</span><span class="sxs-lookup"><span data-stu-id="cf689-136">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="cf689-137">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="cf689-137">Security</span></span></p></li>
<li><p><span data-ttu-id="cf689-138">監視と監査</span><span class="sxs-lookup"><span data-stu-id="cf689-138">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="cf689-139">ハードウェアに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="cf689-139">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cf689-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Lync Server 2013 の通話受付管理のベスト プラクティス</a></span><span class="sxs-lookup"><span data-stu-id="cf689-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf689-141">展開プロセス</span><span class="sxs-lookup"><span data-stu-id="cf689-141">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="cf689-142">前提条件</span><span class="sxs-lookup"><span data-stu-id="cf689-142">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="cf689-143">情報の要件</span><span class="sxs-lookup"><span data-stu-id="cf689-143">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="cf689-144">プロセスと手順</span><span class="sxs-lookup"><span data-stu-id="cf689-144">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cf689-145"><a href="lync-server-2013-configure-call-admission-control.md">Lync Server 2013 での通話受付制御の構成</a></span><span class="sxs-lookup"><span data-stu-id="cf689-145"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

