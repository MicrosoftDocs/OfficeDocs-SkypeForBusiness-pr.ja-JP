---
title: 'Lync Server 2013: DNS の概要 - リバース プロキシ'
TOCTitle: DNS の概要 - リバース プロキシ
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48271653
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS の概要 - Lync Server 2013 でのリバース プロキシ

 

_**トピックの最終更新日:** 2015-03-09_

リバース プロキシでは、2 つのネットワーク アダプターを次のように構成します。

## リバース プロキシ ネットワーク アダプターの要件

  - **ネットワーク アダプター 1 (内部インターフェイス)** の例
    
    172.25.33.40 が割り当てられた内部インターフェイス。
    
    デフォルト ゲートウェイは定義されません。
    
    リバース プロキシの内部インターフェイスを含むネットワークから、Lync Serverフロント エンド プール サーバーを含む任意のネットワークへのルート (たとえば、172.25.33.0 から 192.168.10.0) があることを確認します。

  - **ネットワーク アダプター 2 (外部インターフェイス)** の例
    
    このネットワーク アダプターには、1 つ以上のパブリック IP アドレスが割り当てられます。
    
    ゲートウェイは、境界の外側のルーターまたは統合ファイアウォールを指すように定義されます (シナリオ例では 10.45.16.1)。

### リバース プロキシで必要な DNS レコード

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>場所/種類/ポート</th>
<th>FQDN</th>
<th>IP アドレス</th>
<th>マッピング先/コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>外部に公開されたリソースに割り当てられたリスナー</p></td>
<td><p>内部展開からの外部 Web サービス。このリバース プロキシを使用し、外部 Web サービスを定義している任意の SIP ドメインの、すべてのプールと単一のサーバーについて、追加のレコードを定義および作成できます。</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>外部に公開されたリソースに割り当てられたリスナー</p></td>
<td><p>展開内の ディレクターまたは ディレクター プールの外部 Web サービス。ディレクターは、存在する個々の ディレクターの数だけ定義でき、その中には他の SIP ドメインに関連付けられているものもあります。</p>
<div>

> [!IMPORTANT]
> ディレクターに対して DNS レコードを定義し、公開する場合、フロントエンド プールか ディレクターかを選択して行うわけではありません。ディレクターを使用する場合は、ディレクターおよび フロント エンド プールの両方の外部 Web サービスに対して DNS レコードを定義し、公開する必要があります。トポロジでディレクターが定義されている場合は、特定の種類のトラフィック (認証およびその他の用途のトラフィック) が最初に ディレクターに送信されます。


</div></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>外部に公開されたリソースに割り当てられたリスナー</p></td>
<td><p>外部に公開されるダイヤルイン会議</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>外部に公開されたリソースに割り当てられたリスナー</p></td>
<td><p>外部に公開される会議</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>Office Web Apps サーバー に割り当てられたリスナー</p></td>
<td><p>内部または境界に展開され、外部クライアント アクセス用に公開された Office Web Apps サーバー</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>外部に公開されたリソースに割り当てられたリスナー</p></td>
<td><p>モビリティ、Microsoft Lync Web App、スケジューラ Web アプリケーションを含む、外部に公開された AutoDiscover の Lync Discover External レコード</p></td>
</tr>
</tbody>
</table>

