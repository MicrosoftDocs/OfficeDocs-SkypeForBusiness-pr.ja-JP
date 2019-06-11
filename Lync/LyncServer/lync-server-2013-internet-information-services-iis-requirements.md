---
title: 'Lync Server 2013: インターネット インフォメーション サービス (IIS) の要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcb0350178a19a75ac821a452ef90e10da297677
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a>Lync Server 2013 のインターネット インフォメーション サービス (IIS) の要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-19_

一部の Lync Server 2013 コンポーネントには、インターネットインフォメーションサービス (IIS) が必要です。 このトピックでは、Lync Server をサポートするために必要な特定の IIS 機能について説明します。 このセクションのトピックでは、IIS の特定のコンポーネントの要件について説明します。

Windows Server 2008 で Web サーバー (IIS) の役割が有効になっていると、さまざまな役割サービスが既定でインストールされます。 次の表では、Windows Server 2008 で Web サーバー (IIS) の役割が有効になったときにインストールする必要があるその他の役割サービスについて説明します。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>役割サービス</th>
<th>機能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP 共通機能</p></td>
<td><p>HTTP リダイレクション</p></td>
</tr>
<tr class="even">
<td><p>アプリケーション開発</p></td>
<td><p>ASP.NET</p></td>
</tr>
<tr class="odd">
<td><p>アプリケーション開発</p></td>
<td><p>.NET の拡張性</p></td>
</tr>
<tr class="even">
<td><p>アプリケーション開発</p></td>
<td><p>ISAPI 拡張機能</p></td>
</tr>
<tr class="odd">
<td><p>アプリケーション開発</p></td>
<td><p>ISAPI フィルター</p></td>
</tr>
<tr class="even">
<td><p>状態と診断</p></td>
<td><p>ログ ツール</p></td>
</tr>
<tr class="odd">
<td><p>状態と診断</p></td>
<td><p>トレース</p></td>
</tr>
<tr class="even">
<td><p>セキュリティ</p></td>
<td><p>基本認証</p></td>
</tr>
<tr class="odd">
<td><p>セキュリティ</p></td>
<td><p>Windows 認証</p></td>
</tr>
<tr class="even">
<td><p>管理ツール</p></td>
<td><p>IIS 管理スクリプトおよびツール</p></td>
</tr>
<tr class="odd">
<td><p>管理ツール</p></td>
<td><p>IIS 6 管理の互換性</p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="証券" alt="security" />セキュリティメモ:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Windows Server 2008 オペレーティングシステムで IIS 7.0 を使用している場合、Lync Server セットアップは IIS のカーネルモード認証を無効にします。</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 のフロントエンド プールおよび Standard Edition サーバーの IIS 要件](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

