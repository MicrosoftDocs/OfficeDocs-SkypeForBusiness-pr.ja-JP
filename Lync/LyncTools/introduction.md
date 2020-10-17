---
title: 概要
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f217ec7d39134dcb8d6000de33b3d0c17aeb033d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527154"
---
# <a name="introduction"></a><span data-ttu-id="e61ff-102">はじめに</span><span class="sxs-lookup"><span data-stu-id="e61ff-102">Introduction</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e61ff-103">_**トピックの最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="e61ff-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="e61ff-104">Lync Server 2013 ストレスおよびパフォーマンスツール (LyncPerfTool と呼ばれます) は、次の種類のユーザーロードをシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="e61ff-104">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e61ff-105">インスタント メッセージング (IM) およびプレゼンス</span><span class="sxs-lookup"><span data-stu-id="e61ff-105">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="e61ff-106">電話会議</span><span class="sxs-lookup"><span data-stu-id="e61ff-106">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e61ff-107">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="e61ff-107">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="e61ff-108">公衆交換電話網 (PSTN) シミュレーションを含むボイスオーバー IP (VoIP)</span><span class="sxs-lookup"><span data-stu-id="e61ff-108">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e61ff-109">Web Access クライアント会議</span><span class="sxs-lookup"><span data-stu-id="e61ff-109">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="e61ff-110">Microsoft Lync 2013 アテンダント</span><span class="sxs-lookup"><span data-stu-id="e61ff-110">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e61ff-111">応答グループ</span><span class="sxs-lookup"><span data-stu-id="e61ff-111">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="e61ff-112">配布リストの展開</span><span class="sxs-lookup"><span data-stu-id="e61ff-112">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e61ff-113">アドレス帳のダウンロードとアドレス帳のクエリ</span><span class="sxs-lookup"><span data-stu-id="e61ff-113">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="e61ff-114">拡張 9-1-1 (E9-1-1) 通話と場所プロファイル (ダイヤルプラン)</span><span class="sxs-lookup"><span data-stu-id="e61ff-114">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e61ff-115">マルチビュー</span><span class="sxs-lookup"><span data-stu-id="e61ff-115">MultiView</span></span></p></td>
<td><p><span data-ttu-id="e61ff-116">会議から複数のストリームを表示する</span><span class="sxs-lookup"><span data-stu-id="e61ff-116">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e61ff-117">Lync Server 2013 ストレスおよびパフォーマンスツールは、高度な構成のみを通じて、クロスプールの負荷生成とフェデレーションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e61ff-117">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="e61ff-118">このツールでは、次のクライアントのユーザー負荷もシミュレートされません。</span><span class="sxs-lookup"><span data-stu-id="e61ff-118">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="e61ff-119">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="e61ff-119">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="e61ff-120">Lync 2013 常設チャット</span><span class="sxs-lookup"><span data-stu-id="e61ff-120">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="e61ff-121">そのため、Lync Server 2013 ストレスおよびパフォーマンスツールでは、次のコンポーネントのテストはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="e61ff-121">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="e61ff-122">Lync 2013 常設チャット</span><span class="sxs-lookup"><span data-stu-id="e61ff-122">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="e61ff-123">Exchange 統合のシナリオ</span><span class="sxs-lookup"><span data-stu-id="e61ff-123">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="e61ff-124">Lync Server 2013 ストレスおよびパフォーマンスツールに含まれているアプリケーションとファイル</span><span class="sxs-lookup"><span data-stu-id="e61ff-124">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="e61ff-125">Lync Server 2013 のストレスおよびパフォーマンスツールには、次のアプリケーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e61ff-125">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e61ff-126">ツール</span><span class="sxs-lookup"><span data-stu-id="e61ff-126">Tool</span></span></th>
<th><span data-ttu-id="e61ff-127">説明</span><span class="sxs-lookup"><span data-stu-id="e61ff-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e61ff-128">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="e61ff-128">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="e61ff-129">Lync Server 2013 ユーザープロビジョニングツール。</span><span class="sxs-lookup"><span data-stu-id="e61ff-129">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="e61ff-130">このツールは、ユーザーと連絡先を作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e61ff-130">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e61ff-131">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="e61ff-131">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="e61ff-132">Lync Server 2013 Load 構成ツール。</span><span class="sxs-lookup"><span data-stu-id="e61ff-132">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="e61ff-133">このツールは、シミュレートするユーザーロードの特性を構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e61ff-133">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e61ff-134">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="e61ff-134">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="e61ff-135">Lync Server 2013 ストレスおよびパフォーマンスツール。</span><span class="sxs-lookup"><span data-stu-id="e61ff-135">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="e61ff-136">LyncPerfTool は、ユーザー負荷をシミュレートするツールです。</span><span class="sxs-lookup"><span data-stu-id="e61ff-136">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e61ff-137">Tmx</span><span class="sxs-lookup"><span data-stu-id="e61ff-137">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="e61ff-138">Lync Server 2013 ログツールを使用するには、tmx が必要です。</span><span class="sxs-lookup"><span data-stu-id="e61ff-138">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e61ff-139">プロビジョニングスクリプトの例</span><span class="sxs-lookup"><span data-stu-id="e61ff-139">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="e61ff-140">これらの例は、特定のシナリオに基づいて、ロードテストを実行するためのトポロジを構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e61ff-140">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

