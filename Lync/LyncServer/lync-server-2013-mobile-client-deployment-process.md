---
title: 'Lync Server 2013: モバイルクライアントの展開プロセス'
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
ms.openlocfilehash: 841b0349818fd94d828e3aaa93b3f7c9a99f9f00
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="cc54c-102">Lync Server 2013 でのモバイルクライアントの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="cc54c-102">Mobile client deployment process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc54c-103">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="cc54c-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="cc54c-104">Microsoft Lync Server 2013 の展開が完了した後、ユーザーは、特定のデバイスに慣れているモバイルマーケットプレースから Lync 2013 アプリをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="cc54c-104">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="cc54c-105">Lync モバイルの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="cc54c-105">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc54c-106">フェーズ</span><span class="sxs-lookup"><span data-stu-id="cc54c-106">Phase</span></span></th>
<th><span data-ttu-id="cc54c-107">手順</span><span class="sxs-lookup"><span data-stu-id="cc54c-107">Steps</span></span></th>
<th><span data-ttu-id="cc54c-108">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="cc54c-108">Permissions</span></span></th>
<th><span data-ttu-id="cc54c-109">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="cc54c-109">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc54c-110">セットアップ前のタスクを実行する</span><span class="sxs-lookup"><span data-stu-id="cc54c-110">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="cc54c-111">Lync Server 2013 の展開を確認します。</span><span class="sxs-lookup"><span data-stu-id="cc54c-111">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="cc54c-112">証明書の要件を確認します。</span><span class="sxs-lookup"><span data-stu-id="cc54c-112">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="cc54c-113">管理者</span><span class="sxs-lookup"><span data-stu-id="cc54c-113">Administrator</span></span></p></td>
<td><p><span data-ttu-id="cc54c-114">サーバー計画のドキュメントの「 <a href="lync-server-2013-planning-for-mobility.md">Lync server 2013 でのモビリティの計画</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc54c-114"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="cc54c-115">サーバー展開のドキュメントの「 <a href="lync-server-2013-deploying-mobility.md">Lync server 2013 でのモビリティの展開</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc54c-115"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="cc54c-116">サーバー計画のドキュメントの「 <a href="lync-server-2013-certificate-infrastructure-requirements.md">Lync server 2013 の証明書インフラストラクチャ要件</a>」。</span><span class="sxs-lookup"><span data-stu-id="cc54c-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc54c-117">Lync アプリケーションをテスト デバイスにインストールする</span><span class="sxs-lookup"><span data-stu-id="cc54c-117">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="cc54c-118">必要なソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="cc54c-118">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="cc54c-119">モバイル デバイスに固有のマーケットプレースからインストールします。</span><span class="sxs-lookup"><span data-stu-id="cc54c-119">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="cc54c-120">管理者</span><span class="sxs-lookup"><span data-stu-id="cc54c-120">Administrator</span></span></p></td>
<td><p><span data-ttu-id="cc54c-121"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013 でのモバイルクライアントの展開</a>でのモバイルデバイスに固有のインストール手順。</span><span class="sxs-lookup"><span data-stu-id="cc54c-121">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc54c-122">クライアントを構成する</span><span class="sxs-lookup"><span data-stu-id="cc54c-122">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="cc54c-123">サインイン設定とサーバー情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="cc54c-123">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cc54c-124">管理者</span><span class="sxs-lookup"><span data-stu-id="cc54c-124">Administrator</span></span></p></td>
<td><p><span data-ttu-id="cc54c-125"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013 でのモバイルクライアントの展開</a></span><span class="sxs-lookup"><span data-stu-id="cc54c-125"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc54c-126">モバイル シナリオをテストする</span><span class="sxs-lookup"><span data-stu-id="cc54c-126">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="cc54c-127">インスタントメッセージング (IM) とプレゼンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="cc54c-127">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="cc54c-128">ダイヤルアウト会議をテストします。</span><span class="sxs-lookup"><span data-stu-id="cc54c-128">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="cc54c-129">会社のディレクトリで連絡先を検索します。</span><span class="sxs-lookup"><span data-stu-id="cc54c-129">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="cc54c-130">プッシュ通知をテストします。</span><span class="sxs-lookup"><span data-stu-id="cc54c-130">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="cc54c-131">管理者</span><span class="sxs-lookup"><span data-stu-id="cc54c-131">Administrator</span></span></p></td>
<td><p><span data-ttu-id="cc54c-132"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013 でのモバイルクライアントの展開</a>でのモバイルデバイスに固有の確認手順。</span><span class="sxs-lookup"><span data-stu-id="cc54c-132">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc54c-133">Lync アプリケーションを携帯電話にインストールする</span><span class="sxs-lookup"><span data-stu-id="cc54c-133">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="cc54c-134">必要なソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="cc54c-134">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="cc54c-135">モバイル デバイスに固有のマーケットプレースからインストールします。</span><span class="sxs-lookup"><span data-stu-id="cc54c-135">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="cc54c-136">ユーザー</span><span class="sxs-lookup"><span data-stu-id="cc54c-136">User</span></span></p></td>
<td><p><span data-ttu-id="cc54c-137"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013 でのモバイルクライアントの展開</a>でのモバイルデバイスに固有のインストール手順。</span><span class="sxs-lookup"><span data-stu-id="cc54c-137">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

