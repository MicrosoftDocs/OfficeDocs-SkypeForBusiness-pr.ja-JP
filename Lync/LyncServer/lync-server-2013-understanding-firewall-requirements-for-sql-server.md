---
title: 'Lync Server 2013: SQL Server のファイアウォール要件について'
TOCTitle: SQL Server のファイアウォール要件について
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48271697
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での SQL Server のファイアウォール要件について

 

_**トピックの最終更新日:** 2016-12-08_

Standard Edition の展開では、Lync Server 2013 のセットアップ時に、ファイアウォール例外が自動的に作成されます。一方、Enterprise Edition の展開では、SQL Server のバックエンド サーバーでファイアウォール例外を手動で構成する必要があります。TCP/IP プロトコルでは、特定のポートを複数の IP アドレスで共有することはできません。このため、SQL Server ベースのサーバーでは、既定のデータベース インスタンスを既定の TCP ポート 1433 に割り当てることができます。他のインスタンスに対しては、SQL Server Configuration Manager を使用して未使用の固有ポートを割り当てる必要があります。このトピックでは、以下の内容について説明します。

  - 既定のインスタンスを使用する場合のファイアウォール例外の要件

  - SQL Server ブラウザー サービスのファイアウォール例外の要件

  - 名前付きインスタンスを使用する場合の静的リッスン ポートの要件

## 既定のインスタンスを使用する場合のファイアウォール例外の要件

Lync Server 2013 を展開するとき、データベース用に SQL Server の既定のインスタンスを使用する場合、フロントエンド プールから SQL Server の既定のインスタンスへの通信を保証するために次のファイアウォール規則要件が使用されます。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>プロトコル</th>
<th>ポート</th>
<th>方向</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>1433</p></td>
<td><p>SQL Server に対する受信</p></td>
</tr>
</tbody>
</table>


## SQL Server ブラウザー サービスのファイアウォール例外の要件

SQL Server ブラウザー サービスは、データベース インスタンスを見つけて、そのインスタンス (名前付きまたは既定) が使用するように構成されているポートを通知します。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>プロトコル</th>
<th>ポート</th>
<th>方向</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>1434</p></td>
<td><p>受信</p></td>
</tr>
</tbody>
</table>


## 名前付きインスタンスを使用する場合の静的リッスン ポートの要件

Lync Server 2013 をサポートするデータベース用の SQL Server 構成で名前付きインスタンスを使用する場合は、SQL Server Configuration Manager を使用して静的ポートを構成します。名前付きインスタンスごとに静的ポートを割り当てたら、ファイアウォールで静的ポートごとに例外を作成します。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>プロトコル</th>
<th>ポート</th>
<th>方向</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>静的に定義</p></td>
<td><p>受信</p></td>
</tr>
</tbody>
</table>


## SQL Server のドキュメント

Microsoft SQL Server 2012 のドキュメントには、データベースのファイアウォール アクセスを構成する詳細な手順が記載されています。Microsoft SQL Server 2012 の詳細については、「SQL Server のアクセスを許可するための Windows ファイアウォールの構成」([http://go.microsoft.com/fwlink/?linkid=218031\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=218031%26clcid=0x411)) を参照してください。

