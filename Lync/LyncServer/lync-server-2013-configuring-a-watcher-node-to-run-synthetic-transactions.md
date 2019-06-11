---
title: 'Lync Server 2013: 代理トランザクションを実行するためのウォッチャーノードの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ec42f5b0f3839ee0efac84f08344aa1718120b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a>Lync Server 2013 で代理トランザクションを実行するためのウォッチャーノードの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-07_

System Center agent ファイルをインストールしたら、次にウォッチャーノード自体を構成する必要があります。 ウォッチャーノードを構成するための手順は、ウォッチャーノードのコンピューターが境界ネットワーク内にあるか境界ネットワークの外側にあるかによって異なります。

監視ノードの構成時には、そのノードが使用する認証方法の種類も選択する必要があります。 Lync Server 2013 では、次の2つの認証方法のいずれかを選択できます。信頼されたサーバーまたは資格情報認証。 この2つの方法の違いについては、次の表で説明します。


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
<th>サポートされている場所</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>信頼できるサーバー</p></td>
<td><p>内部サーバーを偽装する証明書を使用し、認証チャレンジをバイパスします。</p>
<p>これは、各ウォッチャーノードで多くのユーザーパスワードの代わりに1つの証明書を管理することを希望している管理者にとって便利です。</p></td>
<td><p>エンタープライズの内側。</p>
<p>この方法では、監視ノードが監視対象のプールと同じドメインに存在する必要があることに注意してください。 ウォッチャーノードと監視対象のプールが異なるドメインにある場合は、代わりに資格情報認証を使用します。</p></td>
</tr>
<tr class="even">
<td><p>資格情報認証</p></td>
<td><p>ユーザー名とパスワードを各監視ノードの Windows 資格情報マネージャーに保管します。</p>
<p>このモードでは、より多くのパスワードを管理する必要がありますが、エンタープライズの外部にあるウォッチャーノードには唯一の選択肢です。 このような外側に位置する監視ノードを認証の際に信頼済みのエンドポイントとして扱うことはできません。</p></td>
<td><p>エンタープライズの外側。</p>
<p>エンタープライズの内側。</p></td>
</tr>
</tbody>
</table>


また、ファイアウォールが MonitoringHost と PowerShell の両方の受信規則を持っていることも確認する必要があります。 これらのプロセスがファイアウォールによってブロックされた場合、代理トランザクションは 504 (サーバータイムアウト) エラーで失敗します。

</div>

<span> </span>

</div>

</div>

</div>

