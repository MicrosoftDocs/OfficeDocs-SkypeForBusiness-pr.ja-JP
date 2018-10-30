---
title: 証明書の概要 - 自動検出
TOCTitle: 証明書の概要 - 自動検出
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945616(v=OCS.15)
ms:contentKeyID: 52056543
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 証明書の概要 - 自動検出

 

_**トピックの最終更新日:** 2015-03-09_

Lync Server 2013 自動検出サービスは、ディレクターおよびフロントエンド プールのサーバーで実行されます。この自動検出サービスが DNS で公開された場合、Lync クライアントでこの自動検出サービスを使用してサーバーおよびユーザー サービスを検索できます。Lync Server 2010 からアップグレードするときにモビリティを展開していない場合、クライアントで自動検出を使用できるようにするには、自動検出サービスを実行するすべてのディレクターおよびフロント エンド サーバーで、証明書のサブジェクトの別名リストを変更する必要があります。また、リバース プロキシ上の外部 Web サービス公開ルールで使用される証明書についても、サブジェクトの別名リストの変更が必要になる場合があります。

リバース プロキシでサブジェクトの別名リストを使用するかどうかについては、自動検出サービスをポート 80 またはポート 443 のどちらで公開するかに基づいて決定します。

  - **ポート 80 で公開する**:   自動検出サービスへの最初のクエリをポート 80 で実行する場合、証明書を変更する必要はありません。これは、Lync を実行するモバイル デバイスがポート 80 のリバース プロキシに外部的にアクセスした後に、ポート 8080 のディレクターまたはフロント エンド サーバーに内部的にブリッジされるためです。詳細については、「[Lync Server 2013 でのモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md)」の「ポート 80 を使用する初期の自動検出プロセス」を参照してください。

  - **ポート 443 で公開する**:   外部 Web サービス公開ルールで使用される証明書上のサブジェクトの別名リストには、組織内の各 SIP ドメインの lyncdiscover.\<SIP ドメイン\> エントリが含まれる必要があります。
    

    > [!IMPORTANT]
    > HTTPS over HTTP の使用を強くお勧めします。HTTPS は証明書を使用してトラフィックを暗号化します。HTTP は暗号化に対応していないので、送信されるすべてのデータはプレーン テキストになります。



通常、内部の証明機関を使用した証明書の再発行は簡単なプロセスです。ただし、Web サービス公開ルールで使用されるパブリック証明書の場合、サブジェクトの複数の別名エントリを追加する処理に高い費用がかかる可能性があります。この問題を回避するために、ポート 80 での自動検出の初期接続がサポートされます。この接続は、その後、ディレクターまたはフロント エンド サーバーのポート 8080 にリダイレクトされます。

> [!NOTE]
> 内部証明機関 (CA) から発行された内部証明書を Lync Server 2013 インフラストラクチャで使用しており、ワイヤレスによるモバイル デバイスの接続をサポートする計画がある場合、内部 CA からのルート証明書チェーンをモバイル デバイスにインストールするか、Lync Server 2013 インフラストラクチャのパブリック証明書に変更する必要があります。


このトピックでは、ディレクター、フロント エンド サーバー、およびリバース プロキシで必要とされる追加されたサブジェクトの別名について説明します。説明するのは、追加されたサブジェクトの別名 (SAN) についてのみです。証明書の他のエントリに関するガイダンスについては、計画セクションを参照してください。詳細については、「[Lync Server 2013 のディレクターのシナリオ](lync-server-2013-scenarios-for-the-director.md)」、「[Lync Server 2013 の外部ユーザー アクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」、および「[Lync Server 2013 のリバース プロキシのシナリオ](lync-server-2013-scenarios-for-reverse-proxy.md)」を参照してください。

以下の表で、ディレクター プール、フロント エンド プール、およびリバース プロキシの自動検出 SAN エントリを定義します。

### ディレクター プールの証明書の要件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>説明</th>
<th>サブジェクト名の別名エントリ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部自動検出サービス URL</p></td>
<td><p>SAN=lyncdiscoverinternal.&lt;内部ドメイン名&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自動検出サービス URL</p></td>
<td><p>SAN=lyncdiscover.&lt;SIP ドメイン&gt;</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> 新しい SAN エントリのある更新された証明書を既定の証明書に割り当てます。または、SAN=*.&lt;SIP ドメイン&gt; を使用することもできます。


### フロントエンド プールの証明書の要件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>説明</th>
<th>サブジェクト名の別名エントリ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部自動検出サービス URL</p></td>
<td><p>SAN=lyncdiscoverinternal.&lt;内部ドメイン名&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自動検出サービス URL</p></td>
<td><p>SAN=lyncdiscover.&lt;SIP ドメイン&gt;</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> 新しい SAN エントリのある更新された証明書を既定の証明書に割り当てます。または、SAN=*.&lt;SIP ドメイン&gt; を使用することもできます。


### リバース プロキシ (パブリック CA) の証明書の要件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>説明</th>
<th>サブジェクト名の別名エントリ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部自動検出サービス URL</p></td>
<td><p>SAN=lyncdiscover.&lt;SIP ドメイン&gt;</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> 新しい SAN エントリのある更新された証明書を、リバース プロキシ上の SSL リスナーに割り当てます。

