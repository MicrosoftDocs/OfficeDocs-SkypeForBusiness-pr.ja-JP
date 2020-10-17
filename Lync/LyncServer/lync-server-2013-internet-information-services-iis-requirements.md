---
title: 'Lync Server 2013: インターネットインフォメーションサービス (IIS) の要件'
description: 'Lync Server 2013: インターネットインフォメーションサービス (IIS) の要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd8de55fa4611c3ab29eac7d7c28c522b418e77d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543993"
---
# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a><span data-ttu-id="6b2c0-103">Lync Server 2013 のインターネットインフォメーションサービス (IIS) の要件</span><span class="sxs-lookup"><span data-stu-id="6b2c0-103">Internet Information Services (IIS) requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b2c0-104">_**トピックの最終更新日:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="6b2c0-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="6b2c0-105">いくつかの Lync Server 2013 コンポーネントには、インターネットインフォメーションサービス (IIS) が必要です。</span><span class="sxs-lookup"><span data-stu-id="6b2c0-105">Several Lync Server 2013 components require Internet Information Services (IIS).</span></span> <span data-ttu-id="6b2c0-106">このトピックでは、Lync Server をサポートするために必要な特定の IIS 機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b2c0-106">This topic describes the specific IIS features required to support Lync Server.</span></span> <span data-ttu-id="6b2c0-107">このセクションのトピックでは、IIS の特定のコンポーネントの要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b2c0-107">The topics in this section describe the requirements of specific components for IIS.</span></span>

<span data-ttu-id="6b2c0-p102">Windows Server 2008 で Web サーバー (IIS) の役割が有効になっていると、さまざまな役割サービスが既定でインストールされます。 次の表で、Windows Server 2008 で Web サーバー (IIS) の役割が有効になっている場合にインストールする必要がある、追加の役割サービスを示します。</span><span class="sxs-lookup"><span data-stu-id="6b2c0-p102">When the Web Server (IIS) role is enabled on Windows Server 2008, various role services are installed by default. The following table describes the additional role services that must be installed when the Web Server (IIS) role is enabled on Windows Server 2008.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b2c0-110">役割サービス</span><span class="sxs-lookup"><span data-stu-id="6b2c0-110">Role service</span></span></th>
<th><span data-ttu-id="6b2c0-111">機能</span><span class="sxs-lookup"><span data-stu-id="6b2c0-111">Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b2c0-112">共通の HTTP 機能</span><span class="sxs-lookup"><span data-stu-id="6b2c0-112">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="6b2c0-113">HTTP リダイレクト</span><span class="sxs-lookup"><span data-stu-id="6b2c0-113">HTTP Redirection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2c0-114">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="6b2c0-114">Application Development</span></span></p></td>
<td><p><span data-ttu-id="6b2c0-115">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6b2c0-115">ASP.NET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2c0-116">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="6b2c0-116">Application Development</span></span></p></td>
<td><p><span data-ttu-id="6b2c0-117">.NET 拡張機能</span><span class="sxs-lookup"><span data-stu-id="6b2c0-117">.NET Extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2c0-118">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="6b2c0-118">Application Development</span></span></p></td>
<td><p><span data-ttu-id="6b2c0-119">ISAPI 拡張機能</span><span class="sxs-lookup"><span data-stu-id="6b2c0-119">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2c0-120">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="6b2c0-120">Application Development</span></span></p></td>
<td><p><span data-ttu-id="6b2c0-121">ISAPI フィルター</span><span class="sxs-lookup"><span data-stu-id="6b2c0-121">ISAPI Filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2c0-122">状態と診断</span><span class="sxs-lookup"><span data-stu-id="6b2c0-122">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="6b2c0-123">ログ ツール</span><span class="sxs-lookup"><span data-stu-id="6b2c0-123">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2c0-124">状態と診断</span><span class="sxs-lookup"><span data-stu-id="6b2c0-124">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="6b2c0-125">・</span><span class="sxs-lookup"><span data-stu-id="6b2c0-125">Tracing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2c0-126">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="6b2c0-126">Security</span></span></p></td>
<td><p><span data-ttu-id="6b2c0-127">基本認証</span><span class="sxs-lookup"><span data-stu-id="6b2c0-127">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2c0-128">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="6b2c0-128">Security</span></span></p></td>
<td><p><span data-ttu-id="6b2c0-129">Windows 認証</span><span class="sxs-lookup"><span data-stu-id="6b2c0-129">Windows Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2c0-130">管理ツール</span><span class="sxs-lookup"><span data-stu-id="6b2c0-130">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="6b2c0-131">IIS 管理スクリプトおよびツール</span><span class="sxs-lookup"><span data-stu-id="6b2c0-131">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2c0-132">管理ツール</span><span class="sxs-lookup"><span data-stu-id="6b2c0-132">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="6b2c0-133">IIS 6 管理互換</span><span class="sxs-lookup"><span data-stu-id="6b2c0-133">IIS 6 Management Compatibility</span></span></p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="security" alt="security" /><span data-ttu-id="6b2c0-135">セキュリティに関する注意事項:</span><span class="sxs-lookup"><span data-stu-id="6b2c0-135">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6b2c0-136">Windows Server 2008 オペレーティングシステムで IIS 7.0 を使用している場合、Lync Server セットアップでは IIS でカーネルモード認証が無効になります。</span><span class="sxs-lookup"><span data-stu-id="6b2c0-136">If you are using IIS 7.0 on a Windows Server 2008 operating system, Lync Server Setup disables kernel mode authentication in IIS.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6b2c0-137">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6b2c0-137">In This Section</span></span>

  - [<span data-ttu-id="6b2c0-138">Lync Server 2013 のフロントエンドプールおよび Standard Edition サーバーの IIS 要件</span><span class="sxs-lookup"><span data-stu-id="6b2c0-138">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

