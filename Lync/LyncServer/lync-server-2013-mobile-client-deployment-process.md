---
title: 'Lync Server 2013: モバイルクライアントの展開プロセス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobile client deployment process
ms:assetid: 6498235b-2fa9-421d-bfa0-0ccc09508dbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690982(v=OCS.15)
ms:contentKeyID: 51541484
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0d0bf17fe4906d49fefd8bd319d25d1268191e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="41ac5-102">Lync Server 2013 でのモバイルクライアントの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="41ac5-102">Mobile client deployment process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41ac5-103">_**最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="41ac5-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="41ac5-104">Microsoft Lync Server 2013 の展開が完了したら、ユーザーは、特定のデバイスで使い慣れたモバイル市場から Lync 2013 アプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="41ac5-104">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="41ac5-105">Lync モバイル展開プロセス</span><span class="sxs-lookup"><span data-stu-id="41ac5-105">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41ac5-106">段階</span><span class="sxs-lookup"><span data-stu-id="41ac5-106">Phase</span></span></th>
<th><span data-ttu-id="41ac5-107">ステップ</span><span class="sxs-lookup"><span data-stu-id="41ac5-107">Steps</span></span></th>
<th><span data-ttu-id="41ac5-108">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="41ac5-108">Permissions</span></span></th>
<th><span data-ttu-id="41ac5-109">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="41ac5-109">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41ac5-110">セットアップ前のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="41ac5-110">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="41ac5-111">Lync Server 2013 の展開を確認します。</span><span class="sxs-lookup"><span data-stu-id="41ac5-111">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="41ac5-112">証明書の要件を確認します。</span><span class="sxs-lookup"><span data-stu-id="41ac5-112">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="41ac5-113">Administrator</span><span class="sxs-lookup"><span data-stu-id="41ac5-113">Administrator</span></span></p></td>
<td><p><span data-ttu-id="41ac5-114">サーバー計画ドキュメントの<a href="lync-server-2013-planning-for-mobility.md">Lync server 2013 でのモビリティの計画</a>。</span><span class="sxs-lookup"><span data-stu-id="41ac5-114"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="41ac5-115">サーバー展開ドキュメントの<a href="lync-server-2013-deploying-mobility.md">Lync server 2013</a>へのモビリティの展開。</span><span class="sxs-lookup"><span data-stu-id="41ac5-115"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="41ac5-116">サーバー計画ドキュメントの<a href="lync-server-2013-certificate-infrastructure-requirements.md">Lync server 2013 の証明書インフラストラクチャの要件</a>。</span><span class="sxs-lookup"><span data-stu-id="41ac5-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41ac5-117">Lync アプリケーションをテストデバイスにインストールします。</span><span class="sxs-lookup"><span data-stu-id="41ac5-117">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="41ac5-118">前提条件をインストールします。</span><span class="sxs-lookup"><span data-stu-id="41ac5-118">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="41ac5-119">モバイルデバイスに固有の marketplace からインストールします。</span><span class="sxs-lookup"><span data-stu-id="41ac5-119">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="41ac5-120">Administrator</span><span class="sxs-lookup"><span data-stu-id="41ac5-120">Administrator</span></span></p></td>
<td><p><span data-ttu-id="41ac5-121"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013 でモバイルクライアントを展開</a>するときのモバイルデバイス固有のインストール手順。</span><span class="sxs-lookup"><span data-stu-id="41ac5-121">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41ac5-122">クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="41ac5-122">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="41ac5-123">サインインの設定とサーバー情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="41ac5-123">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="41ac5-124">Administrator</span><span class="sxs-lookup"><span data-stu-id="41ac5-124">Administrator</span></span></p></td>
<td><p><span data-ttu-id="41ac5-125"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013 でモバイルクライアントを展開する</a></span><span class="sxs-lookup"><span data-stu-id="41ac5-125"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41ac5-126">モバイルシナリオをテストする。</span><span class="sxs-lookup"><span data-stu-id="41ac5-126">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="41ac5-127">インスタントメッセージング (IM) とプレゼンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="41ac5-127">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="41ac5-128">ダイヤルアウト会議をテストします。</span><span class="sxs-lookup"><span data-stu-id="41ac5-128">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="41ac5-129">会社のディレクトリで連絡先を検索します。</span><span class="sxs-lookup"><span data-stu-id="41ac5-129">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="41ac5-130">プッシュ通知をテストします。</span><span class="sxs-lookup"><span data-stu-id="41ac5-130">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="41ac5-131">Administrator</span><span class="sxs-lookup"><span data-stu-id="41ac5-131">Administrator</span></span></p></td>
<td><p><span data-ttu-id="41ac5-132"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013 でモバイルクライアントを展開</a>するときのモバイルデバイス固有の確認手順。</span><span class="sxs-lookup"><span data-stu-id="41ac5-132">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41ac5-133">Lync アプリケーションを携帯電話にインストールします。</span><span class="sxs-lookup"><span data-stu-id="41ac5-133">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="41ac5-134">前提条件をインストールします。</span><span class="sxs-lookup"><span data-stu-id="41ac5-134">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="41ac5-135">モバイルデバイスに固有の marketplace からインストールします。</span><span class="sxs-lookup"><span data-stu-id="41ac5-135">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="41ac5-136">ユーザー</span><span class="sxs-lookup"><span data-stu-id="41ac5-136">User</span></span></p></td>
<td><p><span data-ttu-id="41ac5-137"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013 でモバイルクライアントを展開</a>するときのモバイルデバイス固有のインストール手順。</span><span class="sxs-lookup"><span data-stu-id="41ac5-137">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

