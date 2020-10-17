---
title: 'Lync Server 2013: モバイルクライアントの展開プロセス'
description: 'Lync Server 2013: モバイルクライアントの展開プロセス。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobile client deployment process
ms:assetid: 6498235b-2fa9-421d-bfa0-0ccc09508dbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690982(v=OCS.15)
ms:contentKeyID: 51541484
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fa4e9e1d272915e06009df5c06480309ce104e0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563483"
---
# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="5659e-103">Lync Server 2013 でのモバイルクライアントの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="5659e-103">Mobile client deployment process in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5659e-104">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="5659e-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="5659e-105">Microsoft Lync Server 2013 の展開が完了した後、ユーザーは、特定のデバイスに慣れているモバイルマーケットプレースから Lync 2013 アプリをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="5659e-105">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="5659e-106">Lync モバイルの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="5659e-106">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5659e-107">フェーズ</span><span class="sxs-lookup"><span data-stu-id="5659e-107">Phase</span></span></th>
<th><span data-ttu-id="5659e-108">手順</span><span class="sxs-lookup"><span data-stu-id="5659e-108">Steps</span></span></th>
<th><span data-ttu-id="5659e-109">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="5659e-109">Permissions</span></span></th>
<th><span data-ttu-id="5659e-110">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="5659e-110">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5659e-111">セットアップ前のタスクを実行する</span><span class="sxs-lookup"><span data-stu-id="5659e-111">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="5659e-112">Lync Server 2013 の展開を確認します。</span><span class="sxs-lookup"><span data-stu-id="5659e-112">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="5659e-113">証明書の要件を確認します。</span><span class="sxs-lookup"><span data-stu-id="5659e-113">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="5659e-114">管理者</span><span class="sxs-lookup"><span data-stu-id="5659e-114">Administrator</span></span></p></td>
<td><p><span data-ttu-id="5659e-115">サーバー計画のドキュメントの「 <a href="lync-server-2013-planning-for-mobility.md">Lync server 2013 でのモビリティの計画</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5659e-115"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="5659e-116">サーバー展開のドキュメントの「 <a href="lync-server-2013-deploying-mobility.md">Lync server 2013 でのモビリティの展開</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5659e-116"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="5659e-117">サーバー計画のドキュメントの「 <a href="lync-server-2013-certificate-infrastructure-requirements.md">Lync server 2013 の証明書インフラストラクチャ要件</a>」。</span><span class="sxs-lookup"><span data-stu-id="5659e-117"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5659e-118">Lync アプリケーションをテスト デバイスにインストールする</span><span class="sxs-lookup"><span data-stu-id="5659e-118">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="5659e-119">必要なソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5659e-119">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="5659e-120">モバイル デバイスに固有のマーケットプレースからインストールします。</span><span class="sxs-lookup"><span data-stu-id="5659e-120">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="5659e-121">管理者</span><span class="sxs-lookup"><span data-stu-id="5659e-121">Administrator</span></span></p></td>
<td><p><span data-ttu-id="5659e-122"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013 でのモバイルクライアントの展開</a>でのモバイルデバイスに固有のインストール手順。</span><span class="sxs-lookup"><span data-stu-id="5659e-122">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5659e-123">クライアントを構成する</span><span class="sxs-lookup"><span data-stu-id="5659e-123">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5659e-124">サインイン設定とサーバー情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="5659e-124">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5659e-125">管理者</span><span class="sxs-lookup"><span data-stu-id="5659e-125">Administrator</span></span></p></td>
<td><p><span data-ttu-id="5659e-126"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013 でのモバイルクライアントの展開</a></span><span class="sxs-lookup"><span data-stu-id="5659e-126"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5659e-127">モバイル シナリオをテストする</span><span class="sxs-lookup"><span data-stu-id="5659e-127">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="5659e-128">インスタントメッセージング (IM) とプレゼンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="5659e-128">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="5659e-129">ダイヤルアウト会議をテストします。</span><span class="sxs-lookup"><span data-stu-id="5659e-129">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="5659e-130">会社のディレクトリで連絡先を検索します。</span><span class="sxs-lookup"><span data-stu-id="5659e-130">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="5659e-131">プッシュ通知をテストします。</span><span class="sxs-lookup"><span data-stu-id="5659e-131">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="5659e-132">管理者</span><span class="sxs-lookup"><span data-stu-id="5659e-132">Administrator</span></span></p></td>
<td><p><span data-ttu-id="5659e-133"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013 でのモバイルクライアントの展開</a>でのモバイルデバイスに固有の確認手順。</span><span class="sxs-lookup"><span data-stu-id="5659e-133">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5659e-134">Lync アプリケーションを携帯電話にインストールする</span><span class="sxs-lookup"><span data-stu-id="5659e-134">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="5659e-135">必要なソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5659e-135">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="5659e-136">モバイル デバイスに固有のマーケットプレースからインストールします。</span><span class="sxs-lookup"><span data-stu-id="5659e-136">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="5659e-137">User</span><span class="sxs-lookup"><span data-stu-id="5659e-137">User</span></span></p></td>
<td><p><span data-ttu-id="5659e-138"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013 でのモバイルクライアントの展開</a>でのモバイルデバイスに固有のインストール手順。</span><span class="sxs-lookup"><span data-stu-id="5659e-138">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

