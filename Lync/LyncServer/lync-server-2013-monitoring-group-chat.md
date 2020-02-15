---
title: 'Lync Server 2013: グループチャットの監視'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb82eedd9d9578aeb4120136c1896267cde35392
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a>Lync Server 2013 でのグループチャットの監視

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-08-04_

パフォーマンスを向上させるために、最新の[累積サーバー更新プログラムインストーラー](http://support.microsoft.com/kb/968802)を Microsoft ダウンロードセンターから入手することを強くお勧めします。

最新の累積更新プログラムを実行している場合は、次のストレステストテーブルを基準として使用して、グループチャットサーバーが最適な状態で実行されているかどうか理解します。

### <a name="test-environment-and-user-model"></a>テスト環境とユーザーモデル

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>グループチャットプールに3つのグループチャットサーバー。それぞれに 8 GB のメモリと8個のプロセッサがあります。</p></td>
</tr>
<tr class="even">
<td><p>Enterprise Edition では、2つの Lync Server 2013 フロントエンドがあります。</p></td>
</tr>
<tr class="odd">
<td><p>6万3つのグループチャットサーバー間での同時ユーザー数。</p></td>
</tr>
<tr class="even">
<td><p>グループチャットプールによってホストされる25000チャネル</p></td>
</tr>
<tr class="odd">
<td><p>チャネルのサイズ:</p>
<ul>
<li><p>小さいチャネルのサイズ:30</p></li>
<li><p>中規模チャネルサイズ: 150</p></li>
<li><p>大きいチャネルのサイズ: 2500</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>チャネル数:</p>
<ul>
<li><p>小さいチャンネル数: 24000</p></li>
<li><p>Medium チャネルの数800</p></li>
<li><p>大きなチャネルの数24</p></li>
<li><p>チャネル合計24824</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>チャネルの招待:</p>
<ul>
<li><p>チャネルの半数はチャネルを招待する</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>ユーザーが参加したチャネルの数:</p>
<ul>
<li><p>小:12</p></li>
<li><p>中: 2</p></li>
<li><p>大: 1</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>参加率:</p>
<ul>
<li><p>サーバーごとに10合計/秒、3.33/秒</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>ログアウト率:</p>
<ul>
<li><p>サーバーごとに10合計/秒、3.33/秒</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>チャットレート:</p>
<ul>
<li><p>1サーバーあたり20合計/秒、6.66/秒</p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> 次のパフォーマンスカウンターの数値は、異なるハードウェア仕様またはユーザープロファイルを使用したときに異なる可能性があります。



</div>

### <a name="performance-counter-to-be-monitored"></a>監視対象のパフォーマンスカウンター

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>パフォーマンス カウンター</th>
<th>しきい値</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>プロセス (ChannelService)-&gt;プロセッサ時間 (%)</p></td>
<td><p>Min: 0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

