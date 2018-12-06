---
title: 'Lync Server 2013: インターネット インフォメーション サービス (IIS) の要件'
TOCTitle: インターネット インフォメーション サービス (IIS) の要件
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48272056
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のインターネット インフォメーション サービス (IIS) の要件

 

_**トピックの最終更新日:** 2015-03-09_

いくつかの Lync Server 2013 コンポーネントには、インターネット インフォメーション サービス (IIS) が必要です。このトピックでは、Lync Server のサポートに必要な特定の IIS 機能について説明します。このセクションのトピックでは、IIS の特定のコンポーネントの要件について説明します。

Windows Server 2008 で Web サーバー (IIS) の役割が有効になっていると、さまざまな役割サービスが既定でインストールされます。 次の表で、Windows Server 2008 で Web サーバー (IIS) の役割が有効になっている場合にインストールする必要がある、追加の役割サービスを示します。


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
<td><p>共通の HTTP 機能</p></td>
<td><p>HTTP リダイレクト</p></td>
</tr>
<tr class="even">
<td><p>アプリケーション開発</p></td>
<td><p>ASP.NET</p></td>
</tr>
<tr class="odd">
<td><p>アプリケーション開発</p></td>
<td><p>.NET 拡張機能</p></td>
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
<td><p>追跡</p></td>
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
<td><p>IIS 6 管理互換</p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="security" alt="security" />セキュリティ 注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Windows Server 2008 オペレーティング システムで IIS 7.0 の使用中に Lync Server をセットアップすると、IIS でのカーネル モード認証が無効になります。</td>
</tr>
</tbody>
</table>


## このセクション中

  - [Lync Server 2013 のフロントエンド プールおよび Standard Edition サーバーの IIS 要件](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

