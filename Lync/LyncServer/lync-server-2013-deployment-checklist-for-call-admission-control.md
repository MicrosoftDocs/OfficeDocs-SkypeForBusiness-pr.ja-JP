---
title: 'Lync Server 2013: 通話受付管理の展開チェックリスト'
description: 'Lync Server 2013: 通話受付管理の展開チェックリスト。'
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
ms.openlocfilehash: ea5b16d41228faf01637e7e0d78f5ce56f950a19
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557693"
---
# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="ff7d7-103">Lync Server 2013 での通話受付管理の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="ff7d7-103">Deployment checklist for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff7d7-104">_**トピックの最終更新日:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="ff7d7-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="ff7d7-105">通話受付管理 (CAC) を効率的に計画するには、以下のことを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff7d7-105">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="ff7d7-106">CAC を展開するための前提条件</span><span class="sxs-lookup"><span data-stu-id="ff7d7-106">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="ff7d7-107">CAC および展開前に行う必要がある構成上の意思決定に必要な情報</span><span class="sxs-lookup"><span data-stu-id="ff7d7-107">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="ff7d7-108">通話受付管理の展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="ff7d7-108">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="ff7d7-109">通話受付管理を展開する前に、既に、フロントエンドプールまたは Standard Edition サーバーのいずれかを含む Lync Server 2013 内部サーバーを展開しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff7d7-109">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="ff7d7-110">通話受付管理の情報要件</span><span class="sxs-lookup"><span data-stu-id="ff7d7-110">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="ff7d7-111">次の表は、通話受付管理を展開するために必要な情報の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="ff7d7-111">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="ff7d7-112">通話受付管理の展開の情報要件</span><span class="sxs-lookup"><span data-stu-id="ff7d7-112">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff7d7-113">情報</span><span class="sxs-lookup"><span data-stu-id="ff7d7-113">Information</span></span></th>
<th><span data-ttu-id="ff7d7-114">必要な情報の概要</span><span class="sxs-lookup"><span data-stu-id="ff7d7-114">Summary of Information Required</span></span></th>
<th><span data-ttu-id="ff7d7-115">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="ff7d7-115">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff7d7-116">組織が必要とする Lync Server の機能</span><span class="sxs-lookup"><span data-stu-id="ff7d7-116">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ff7d7-117">組織でサポートされる機能</span><span class="sxs-lookup"><span data-stu-id="ff7d7-117">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="ff7d7-118">個々のユーザーに対して有効にする機能</span><span class="sxs-lookup"><span data-stu-id="ff7d7-118">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ff7d7-119"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013 での通話受付管理の要件の定義</a></span><span class="sxs-lookup"><span data-stu-id="ff7d7-119"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff7d7-120">展開するトポロジとコンポーネント</span><span class="sxs-lookup"><span data-stu-id="ff7d7-120">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ff7d7-121">CAC 関連のコンポーネントは、Lync Server 2013 の一部として自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ff7d7-121">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ff7d7-122"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013 での通話受付管理の要件の定義</a></span><span class="sxs-lookup"><span data-stu-id="ff7d7-122"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff7d7-123">システム要件</span><span class="sxs-lookup"><span data-stu-id="ff7d7-123">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ff7d7-124">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="ff7d7-124">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="ff7d7-125">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="ff7d7-125">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="ff7d7-126">併置要件</span><span class="sxs-lookup"><span data-stu-id="ff7d7-126">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ff7d7-127"><a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013 のシステム要件を決定する</a></span><span class="sxs-lookup"><span data-stu-id="ff7d7-127"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff7d7-128">インフラストラクチャ要件</span><span class="sxs-lookup"><span data-stu-id="ff7d7-128">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ff7d7-129">CAC に必要なインフラストラクチャ要件は特にありません</span><span class="sxs-lookup"><span data-stu-id="ff7d7-129">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ff7d7-130"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Lync Server 2013 での通話受付管理のインフラストラクチャ要件</a></span><span class="sxs-lookup"><span data-stu-id="ff7d7-130"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff7d7-131">ネットワーク インターフェイス要件</span><span class="sxs-lookup"><span data-stu-id="ff7d7-131">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ff7d7-132">内部インターフェイスと外部インターフェイスの情報</span><span class="sxs-lookup"><span data-stu-id="ff7d7-132">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="ff7d7-133">ルーティング情報 (NextHop ブログの情報 <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a> を含む、Microsoft Lync Server チームの顧客対応チャネル)</span><span class="sxs-lookup"><span data-stu-id="ff7d7-133">Routing information (including information on the NextHop blog at <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ff7d7-134"><a href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013 での外部ユーザーアクセスの展開</a></span><span class="sxs-lookup"><span data-stu-id="ff7d7-134"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff7d7-135">展開戦略</span><span class="sxs-lookup"><span data-stu-id="ff7d7-135">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ff7d7-136">展開順序</span><span class="sxs-lookup"><span data-stu-id="ff7d7-136">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="ff7d7-137">ワークグループかドメインか</span><span class="sxs-lookup"><span data-stu-id="ff7d7-137">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="ff7d7-138">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="ff7d7-138">Security</span></span></p></li>
<li><p><span data-ttu-id="ff7d7-139">監視と監査</span><span class="sxs-lookup"><span data-stu-id="ff7d7-139">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="ff7d7-140">ハードウェアに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="ff7d7-140">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ff7d7-141"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Lync Server 2013 での通話受付管理のベストプラクティス</a></span><span class="sxs-lookup"><span data-stu-id="ff7d7-141"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff7d7-142">展開プロセス</span><span class="sxs-lookup"><span data-stu-id="ff7d7-142">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ff7d7-143">必要条件</span><span class="sxs-lookup"><span data-stu-id="ff7d7-143">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="ff7d7-144">情報要件</span><span class="sxs-lookup"><span data-stu-id="ff7d7-144">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="ff7d7-145">プロセスと手順</span><span class="sxs-lookup"><span data-stu-id="ff7d7-145">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ff7d7-146"><a href="lync-server-2013-configure-call-admission-control.md">Lync Server 2013 で通話受付管理を構成する</a></span><span class="sxs-lookup"><span data-stu-id="ff7d7-146"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

