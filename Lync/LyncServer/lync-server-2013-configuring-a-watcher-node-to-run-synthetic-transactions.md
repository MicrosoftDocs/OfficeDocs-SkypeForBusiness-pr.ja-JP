---
title: 'Lync Server 2013: 代理トランザクションを実行する監視ノードの構成'
description: 'Lync Server 2013: 代理トランザクションを実行する監視ノードの構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd5fdb3d1a1499a6ef79e962a41d9eb3ee174c33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567883"
---
# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a>Lync Server 2013 で代理トランザクションを実行する監視ノードの構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-07_

System Center エージェント ファイルがインストールされたら、次に監視ノード自体を構成する必要があります。監視ノードを構成する手順は監視ノードを境界ネットワークの内側に置くか、外側に置くかによって異なります。

監視ノードの構成時には、そのノードが使用する認証方法の種類も選択する必要があります。 Lync Server 2013 では、信頼されたサーバー認証または資格情報認証という2つの認証方法のどちらかを選択できます。 この 2 つの方法の主な違いを次の表にまとめます。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>構成</th>
<th>説明</th>
<th>サポートされる場所</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>信頼済みサーバー</p></td>
<td><p>内部サーバーを偽装する証明書を使用し、認証チャレンジをバイパスします。</p>
<p>この方法は、各監視ノードで多数のユーザー パスワードではなく、1 つの証明書を管理したいと考える管理者にとって便利です。</p></td>
<td><p>エンタープライズの内側。</p>
<p>この方法では、監視ノードが監視対象のプールと同じドメイン内に存在する必要があることに注意してください。監視ノードと監視対象のプールが別のドメインに存在する場合は、この方法ではなく、資格情報認証を使用します。</p></td>
</tr>
<tr class="even">
<td><p>資格情報認証</p></td>
<td><p>ユーザー名とパスワードを各監視ノードの Windows 資格情報マネージャーに保管します。</p>
<p>このモードは、パスワード管理の手間を必要としますが、エンタープライズの外側に位置する監視ノードの場合には唯一の選択肢となります。このような外側に位置する監視ノードを認証の際に信頼済みのエンドポイントとして扱うことはできません。</p></td>
<td><p>エンタープライズの外側。</p>
<p>エンタープライズの内側。</p></td>
</tr>
</tbody>
</table>


また、ファイアウォールに MonitoringHost.exe と PowerShell.exe の受信規則があることも確認する必要があります。 これらのプロセスがファイアウォールによってブロックされている場合、代理トランザクションは 504 (サーバータイムアウト) エラーで失敗します。

</div>

<span> </span>

</div>

</div>

</div>

