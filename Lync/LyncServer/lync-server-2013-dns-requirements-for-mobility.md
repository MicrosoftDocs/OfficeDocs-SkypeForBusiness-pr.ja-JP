---
title: 'Lync Server 2013: モビリティの DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fb933e20b8da627ad48a30802ff86c7ed95faff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a>Lync Server 2013 を使ったモビリティの DNS 要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-13_

Lync Server 2013 モビリティ機能を展開するときに、Microsoft Lync Server 2013 自動検出サービスで利用できる新しい Url を使用したり、既存の Web サービスの Url を使用したりすることができます。 既存の Url を使用している場合、ユーザーは自分のモバイルデバイス設定に Url を手動で入力する必要があります。 通常、このオプションはトラブルシューティングに使用されます。 新しい Url を使用すると、モバイルクライアントは Lync Server 2013 のリソースを自動的に検出できます。 自動検出をサポートしている場合は、新しいドメインネームシステム (DNS) レコードを追加する必要があります。 このセクションでは、自動検出に必要な DNS レコードについて説明します。

自動検出をサポートするには、SIP ドメインごとに次の DNS レコードを作成する必要があります。

  - 組織のネットワーク内から接続するモバイルユーザーをサポートするための内部 DNS レコード

  - インターネットから接続するモバイルユーザーをサポートするための、外部またはパブリックの DNS レコード

内部の自動検出 URL は、ネットワークの外部からのアドレス指定を行うことはできません。 外部の自動検出 URL は、ネットワーク内からアドレス指定できません。 ただし、外部 URL に対してこの要件を満たしていない場合は、モバイルクライアントの機能が影響を受けないようにする必要があります。

DNS レコードには、CNAME レコードまたは (ホスト) レコードのいずれかを使うことができます。

**内部 DNS レコード**

次の内部 DNS レコードのいずれかを作成する必要があります。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>レコードの種類</th>
<th>ホスト名または SRV 定義</th>
<th>解決先</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscoverinternal.&lt;sipdomain&gt;</p></td>
<td><p>ディレクタープールの場合は、内部 Web サービスの完全修飾ドメイン名 (FQDN)、ディレクターを持っていない場合は、フロントエンドプールの FQDN</p></td>
</tr>
<tr class="even">
<td><p>A (ホスト)</p></td>
<td><p>lyncdiscoverinternal.&lt;sipdomain&gt;</p></td>
<td><p>ディレクターを持っていない場合は、ディレクタープールの内部 Web サービス IP アドレス (ロードバランサーを使用している場合は仮想 IP (VIP) アドレス) (ディレクターを持っていない場合は、フロントエンドプールを持っている場合)</p></td>
</tr>
</tbody>
</table>


**外部 DNS レコード**

次のいずれかの外部 DNS レコードを作成する必要があります。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>レコードの種類</th>
<th>ホスト名</th>
<th>解決先</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>ディレクタープールを所有している場合は、そのディレクタープールの外部 Web サービス FQDN (ディレクターを持っていない場合は、フロントエンドプール用)</p></td>
</tr>
<tr class="even">
<td><p>A (ホスト)</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>リバースプロキシの外部またはパブリック IP アドレス (ロードバランサーを使用している場合は VIP アドレス)</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_sipfederationtls._tcp. &lt;sipdomain&gt;</p>
<p>アクセスエッジサービスの host (A または AAAA) レコードに解決されます。</p></td>
<td><p>プッシュ通知サービスと Apple プッシュ通知サービスをサポートするには、Microsoft Lync モバイルクライアントを含む SIP ドメインごとに SRV レコードを1つ作成します。</p>
<div>

> [!IMPORTANT]  
> この要件は、Apple または Microsoft ベースのモバイルデバイス上の Microsoft Lync モバイルクライアントにのみ適用されます。 Andriod および Nokia Symbian デバイスでは、プッシュ通知は使用されません。


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lyncdiscover は、自動検出とも呼ばれます。トラフィックはリバースプロキシを通過します。 SRV レコードは、アクセスエッジサービスを通じて解決されるレコードを指します。



</div>

</div>

<span> </span>

</div>

</div>

</div>

