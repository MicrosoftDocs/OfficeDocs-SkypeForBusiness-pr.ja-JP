---
title: 'Lync Server 2013: モビリティの DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0201a9e8870a1b7d8cc579eb270ca67c929cae5d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a>Lync Server 2013 を使用したモビリティの DNS 要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-13_

Lync Server 2013 モビリティ機能を展開する場合は、Microsoft Lync Server 2013 自動検出サービスで使用可能な新しい Url を使用するか、既存の Web サービスの Url を使用することができます。 既存の Url を使用する場合、ユーザーはモバイルデバイスの設定で Url を手動で入力する必要があります。 このオプションは、通常、トラブルシューティングに使用されます。 新しい Url を使用すると、モバイルクライアントは Lync Server 2013 のリソースを自動的に検出できるようになります。 自動検出をサポートする場合は、新しいドメインネームシステム (DNS) レコードを追加する必要があります。 このセクションでは、自動検出に必要な DNS レコードについて説明します。

自動検出をサポートするには、SIP ドメインごとに次の DNS レコードを作成する必要があります。

  - 組織のネットワーク内から接続するモバイル ユーザーをサポートするための内部 DNS レコード

  - インターネットから接続するモバイル ユーザーをサポートするための外部 (パブリック) DNS レコード

内部の自動検出 URL は、ネットワークの外部からアドレス指定できません。 外部自動検出 URL は、ネットワーク内からアドレス指定できません。 ただし、外部 URL に対してこの要件を満たしていない場合、モバイルクライアントの機能は影響を受けません。

DNS レコードは、CNAME レコードまたは A (ホスト) レコードとすることができます。

**内部 DNS レコード**

次の内部 DNS レコードの1つを作成する必要があります。


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
<td><p>lyncdiscoverinternal.&lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
<td><p>ディレクタープールの内部 Web サービスの完全修飾ドメイン名 (FQDN) (ディレクターがない場合) またはフロントエンドプールの場合は、ディレクターが存在しない場合</p></td>
</tr>
<tr class="even">
<td><p>A (ホスト)</p></td>
<td><p>lyncdiscoverinternal.&lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
<td><p>ディレクタープールを使用する場合の内部 Web サービス IP アドレス (ロードバランサーを使用する場合は仮想 IP (VIP) アドレス、ディレクターを持っていない場合はフロントエンドプールのいずれか)</p></td>
</tr>
</tbody>
</table>


**外部 DNS レコード**

次の外部 DNS レコードの 1 つを作成する必要があります。


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
<td><p>lyncdiscover. &lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
<td><p>ディレクターが存在しない場合は、ディレクタープールの外部 Web サービスの FQDN、またはディレクターを持っていない場合はフロントエンドプール。</p></td>
</tr>
<tr class="even">
<td><p>A (ホスト)</p></td>
<td><p>lyncdiscover. &lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
<td><p>リバースプロキシの外部またはパブリック IP アドレス (ロードバランサーを使用する場合は VIP アドレス)</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_sipfederationtls _tcp。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</p>
<p>アクセスエッジサービスのホスト (A または AAAA) レコードに解決されます。</p></td>
<td><p>プッシュ通知サービスと Apple プッシュ通知サービスをサポートするには、Microsoft Lync Mobile クライアントが存在する各 SIP ドメインに対して1つの SRV レコードを作成します。</p>
<div>

> [!IMPORTANT]  
> この要件は、Apple または Microsoft ベースのモバイルデバイス上の Microsoft Lync モバイルクライアントにのみ適用されます。 Andriod および Nokia Symbian デバイスは、プッシュ通知を使用しません。


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lyncdiscover (自動検出とも呼ばれます) は、トラフィックはリバースプロキシを通過します。 SRV レコードは、アクセスエッジサービスを介して解決されるレコードを指します。



</div>

</div>

<span> </span>

</div>

</div>

</div>

