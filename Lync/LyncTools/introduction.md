---
title: 概要
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d496d0aeaabd8ef7502cae8db89f2668d0574499
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction"></a><span data-ttu-id="21192-102">概要</span><span class="sxs-lookup"><span data-stu-id="21192-102">Introduction</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21192-103">_**最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="21192-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="21192-104">Lync Server 2013 のストレスとパフォーマンスツール (LyncPerfTool とも呼ばれます) では、次の種類のユーザーロードをシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="21192-104">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21192-105">インスタントメッセージング (IM) とプレゼンス</span><span class="sxs-lookup"><span data-stu-id="21192-105">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="21192-106">電話会議</span><span class="sxs-lookup"><span data-stu-id="21192-106">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21192-107">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="21192-107">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="21192-108">VoIP (公衆交換電話網 (PSTN) シミュレーションを含む) ボイスオーバー IP (VoIP)</span><span class="sxs-lookup"><span data-stu-id="21192-108">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21192-109">Web Access クライアント会議</span><span class="sxs-lookup"><span data-stu-id="21192-109">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="21192-110">Microsoft Lync 2013 アテンダント</span><span class="sxs-lookup"><span data-stu-id="21192-110">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21192-111">応答グループ</span><span class="sxs-lookup"><span data-stu-id="21192-111">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="21192-112">配布リストの展開</span><span class="sxs-lookup"><span data-stu-id="21192-112">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21192-113">アドレス帳のダウンロードとアドレス帳のクエリ</span><span class="sxs-lookup"><span data-stu-id="21192-113">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="21192-114">拡張 9-1-1 (E9) 通話と位置情報プロファイル (ダイヤルプラン)</span><span class="sxs-lookup"><span data-stu-id="21192-114">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21192-115">MultiView</span><span class="sxs-lookup"><span data-stu-id="21192-115">MultiView</span></span></p></td>
<td><p><span data-ttu-id="21192-116">会議から複数のストリームを表示する</span><span class="sxs-lookup"><span data-stu-id="21192-116">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="21192-117">Lync Server 2013 のストレスとパフォーマンスツールは、高度な構成のみを通じて、クロスプールの負荷生成とフェデレーションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="21192-117">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="21192-118">このツールでは、次のクライアントのユーザーロードもシミュレートされません。</span><span class="sxs-lookup"><span data-stu-id="21192-118">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="21192-119">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="21192-119">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="21192-120">Lync 2013 常設チャット</span><span class="sxs-lookup"><span data-stu-id="21192-120">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="21192-121">このため、Lync Server 2013 のストレスとパフォーマンスツールは、次のコンポーネントのテストをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="21192-121">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="21192-122">Lync 2013 常設チャット</span><span class="sxs-lookup"><span data-stu-id="21192-122">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="21192-123">Exchange の統合シナリオ</span><span class="sxs-lookup"><span data-stu-id="21192-123">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="21192-124">Lync Server 2013 のストレスとパフォーマンスツールに含まれているアプリケーションとファイル</span><span class="sxs-lookup"><span data-stu-id="21192-124">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="21192-125">Lync Server 2013 のストレスとパフォーマンスツールには、次のアプリケーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="21192-125">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21192-126">ツール</span><span class="sxs-lookup"><span data-stu-id="21192-126">Tool</span></span></th>
<th><span data-ttu-id="21192-127">説明</span><span class="sxs-lookup"><span data-stu-id="21192-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21192-128">Userプロビジョニングツール .exe</span><span class="sxs-lookup"><span data-stu-id="21192-128">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="21192-129">Lync Server 2013 ユーザープロビジョニングツール。</span><span class="sxs-lookup"><span data-stu-id="21192-129">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="21192-130">このツールは、ユーザーと連絡先を作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="21192-130">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21192-131">UserProfileGenerator</span><span class="sxs-lookup"><span data-stu-id="21192-131">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="21192-132">Lync Server 2013 のロード構成ツール。</span><span class="sxs-lookup"><span data-stu-id="21192-132">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="21192-133">このツールは、シミュレートするためのユーザーロードの特性を構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="21192-133">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21192-134">LyncPerfTool</span><span class="sxs-lookup"><span data-stu-id="21192-134">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="21192-135">Lync Server 2013 ストレスおよびパフォーマンスツール。</span><span class="sxs-lookup"><span data-stu-id="21192-135">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="21192-136">LyncPerfTool は、ユーザーロードをシミュレートするツールです。</span><span class="sxs-lookup"><span data-stu-id="21192-136">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21192-137">Tmx</span><span class="sxs-lookup"><span data-stu-id="21192-137">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="21192-138">Lync Server 2013 ログツールを使用するには、tmx が必要です。</span><span class="sxs-lookup"><span data-stu-id="21192-138">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21192-139">プロビジョニングスクリプトの例</span><span class="sxs-lookup"><span data-stu-id="21192-139">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="21192-140">次の例は、特定のシナリオに基づいて、ロードテストを実行するためのトポロジを構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="21192-140">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

