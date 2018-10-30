---
title: モビリティの DNS 要件
TOCTitle: モビリティの DNS 要件
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48273782
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# モビリティの DNS 要件

 

_**トピックの最終更新日:** 2015-03-09_

Lync Server 2013 モビリティ機能を展開するときは、Microsoft Lync Server 2013 自動検出サービスで利用できる新しい URL を使用するか、既存の Web サービス URL を使用することができます。既存の URL を使用する場合、ユーザーはモバイル デバイス設定に手動で URL を入力する必要があります。このオプションは、通常、トラブルシューティングに使用されます。新しい URL を使用すると、モバイル クライアントは自動的に Lync Server 2013 リソースを検出できます。自動検出をサポートするときには、新しいドメイン ネーム システム (DNS) レコードを追加する必要があります。このセクションでは、自動検出に必要な DNS レコードについて説明します。

自動検出をサポートするには、SIP ドメインごとに以下の DNS レコードを作成する必要があります。

  - 組織のネットワーク内から接続するモバイル ユーザーをサポートするための内部 DNS レコード

  - インターネットから接続するモバイル ユーザーをサポートするための外部 (パブリック) DNS レコード

内部自動検出 URL は、ネットワーク外部からアドレス指定しないでください。外部自動検出 URL は、ネットワーク内部からアドレス指定しないでください。ただし、外部 URL に対してこの要件を満たすことができなければ、モバイル クライアントは機能的な影響を受けません。

DNS レコードは、CNAME レコードまたは A (ホスト) レコードとすることができます。

**内部 DNS レコード**

次の内部 DNS レコードの 1 つを作成する必要があります。


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
<td><p>lyncdiscoverinternal.<em>&lt;sipdomain&gt;</em></p></td>
<td><p>ディレクター プール用の内部 Web サービス完全修飾ドメイン名 (FQDN) (ディレクター プールがある場合)、またはフロント エンド プール用の内部 Web サービス FQDN (ディレクターがない場合)</p></td>
</tr>
<tr class="even">
<td><p>A (ホスト)</p></td>
<td><p>lyncdiscoverinternal.<em>&lt;sipdomain&gt;</em></p></td>
<td><p>ディレクター プール (ディレクター プールがある場合) またはフロント エンド プール (ディレクターがない場合) の内部 Web サービス IP アドレス (ロード バランサーを使用する場合は仮想 IP (VIP) アドレス)</p></td>
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
<td><p>lyncdiscover. <em>&lt;sipdomain&gt;</em></p></td>
<td><p>ディレクター プール (ディレクター プールがある場合) またはフロント エンド プール (ディレクターがない場合) の外部 Web サービス FQDN</p></td>
</tr>
<tr class="even">
<td><p>A (ホスト)</p></td>
<td><p>lyncdiscover. <em>&lt;sipdomain&gt;</em></p></td>
<td><p>リバース プロキシの外部またはパブリック IP アドレス (ロード バランサーを使用する場合は VIP アドレス)</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_sipfederationtls._tcp. &lt;sipdomain&gt;</p>
<p>アクセス エッジ サービスのホスト (A または AAAA) レコードに解決</p></td>
<td><p>プッシュ通知サービス と Apple プッシュ通知サービス をサポートするには、Microsoft Lync Mobile クライアントを持つ各 SIP ドメイン対して 1 つの SRV レコードを作成します。</p>
<div>

> [!IMPORTANT]
> この要件は、Apple または Microsoft ベースのモバイル デバイス上の Microsoft Lync Mobile クライアントのみに適用されます。Andriod および Nokia Symbian デバイスはプッシュ通知を使用しません。


</div></td>
</tr>
</tbody>
</table>


> [!NOTE]
> Lyncdiscover トラフィックは、リバース プロキシを経由します。Lyncdiscover は自動検出とも呼ばれます。SRV レコードは、アクセス エッジ サービスにより解決されるレコードを示します。

