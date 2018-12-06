---
title: 'Lync Server 2013: SQL Server の展開のアクセス許可'
TOCTitle: SQL Server の展開のアクセス許可
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48272146
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の SQL Server の展開のアクセス許可

 

_**トピックの最終更新日:** 2015-03-09_

Lync Server 2013 をインストールして展開する場合、Microsoft SQL Server 2012 には固有の要件があります。Windows と SQL Server はセキュリティを定義する方法が異なるため、Active Directory ドメインの管理者としてログインしても、SQL Server に対するアクセス許可が暗黙的に付与されるわけではありません。また、構成する SQL Server ベースのサーバーの sysadmin エンティティのメンバーであることも必要です。

## データベースおよび Lync Server のインストールに必要なアクセス許可

以下に、Lync Server 2013 ファイルおよび SQL Server データベースのインストールで使用される 3 つのアクセス許可とグループ メンバーシップの関連付けについての詳細な選択肢を示します。組織の要件に最もよく合うシナリオを選択してください。

### アクセス許可およびグループ メンバーシップの関連付け

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>SQL Server または Lync Server 2013 の役割</th>
<th>役割に典型的な SQL Server のアクセス許可およびグループ メンバーシップ</th>
<th>役割に典型的な Lync Server 2013 のアクセス許可およびグループ メンバーシップ</th>
<th>アクセス許可によって実行できること</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 管理者</p></td>
<td><p>sysadmins SQL Server セキュリティ グループのメンバーシップが付与され、SQL Server のローカル Administrators グループのメンバーである必要があります。</p></td>
<td><p>RTCUniversalServerAdmins グループのメンバーである必要があります。</p></td>
<td><p>Lync Server 2013 の管理者には、Lync Server 2013 および SQL Server データベースの両方をインストールするための適切な権限があります。</p></td>
</tr>
<tr class="even">
<td><p>SQL Server 管理者</p></td>
<td><p>SQL Server sysadmin グループ メンバー (または相当するもの) および SQL Server のローカル Administrators グループのメンバー。</p></td>
<td><p>RTCUniversalServerReadOnly グループのメンバーである必要があります。</p></td>
<td><p>SQL Server の管理者には、Lync Server 2013 および SQL Server データベースの両方をインストールするための適切な権限があります。</p></td>
</tr>
<tr class="odd">
<td><p>インストール作業を共有する両方の管理者</p></td>
<td><p>SQL Server の管理者は、sysadmins グループのメンバー (または相当するもの) および SQL Server のローカル Administrators グループのメンバーです。</p></td>
<td><p>Lync Server 2013 の管理者は、RTCUniversalServerAdmins のメンバーです。</p></td>
<td><p>Lync Server 2013 の管理者は Lync Server 2013 をインストールできますが、データベースをインストールすることはできません。SQL Server の管理者は Lync Server 2013 の管理者によって提供される Lync Server 管理シェルのコマンドレットと Windows PowerShell のコマンドレットを使用して、データベースをインストールします。SQL Server の管理者によって使用される Lync Server 2013 管理シェルは、フロント エンド サーバーにインストールされます。これにより、Lync Server 2013 管理ツールを SQL Server ベースのサーバーにインストールする必要がなくなります。</p></td>
</tr>
</tbody>
</table>

