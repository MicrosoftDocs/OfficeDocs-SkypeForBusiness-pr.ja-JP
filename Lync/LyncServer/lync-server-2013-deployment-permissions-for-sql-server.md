---
title: 'Lync Server 2013: SQL Server の展開のアクセス許可'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea0334c7070ae3aadb3191da4bf036a978878688
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a>Lync Server 2013 の SQL Server の展開のアクセス許可

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-01_

Microsoft SQL Server 2012 には、Lync Server 2013 をインストールして展開するときに特定の要件があります。 Windows と SQL Server はセキュリティの定義が異なるため、Active Directory ドメインで管理者としてログインしても、SQL Server へのアクセス許可が暗黙的に付与されることはありません。 また、構成している SQL Server ベースのサーバーの sysadmin エンティティのメンバーである必要があります。

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a>データベースおよび Lync Server のインストールに必要なアクセス許可

次のオプションでは、Lync Server 2013 ファイルと SQL Server データベースをインストールするための3つのアクセス許可とグループメンバーシップの関連付けについて説明します。 組織の要件に最も適合するシナリオを選択します。

### <a name="permissions-and-group-membership-associations"></a>権限とグループメンバーシップの関連付け

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
<th>役割-一般的な SQL Server 権限とグループメンバーシップ</th>
<th>役割-一般的な Lync Server 2013 のアクセス許可とグループメンバーシップ</th>
<th>権限の結果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 管理者</p></td>
<td><p>システム管理者の SQL Server セキュリティグループと、SQL Server のローカル管理者グループのメンバーに付与されている必要があります。</p></td>
<td><p>RTCUniversalServerAdmins グループのメンバーである必要があります</p></td>
<td><p>Lync server 2013 管理者は、Lync Server 2013 と SQL Server データベースの両方をインストールするための適切な権限を持っています。</p></td>
</tr>
<tr class="even">
<td><p>SQL Server 管理者</p></td>
<td><p>SQL Server sysadmin グループのメンバー (または同等の機能) と SQL Server のローカル管理者グループのメンバー</p></td>
<td><p>RTCUniversalServerReadOnly グループのメンバーである必要があります</p></td>
<td><p>SQL Server 管理者は、Lync Server 2013 データベースと SQL Server データベースの両方をインストールするための適切な権限を持っています。</p></td>
</tr>
<tr class="odd">
<td><p>両方の管理者がインストール義務を共有する</p></td>
<td><p>SQL Server 管理者は、システム管理者グループ (または同等のメンバー) と SQL Server のローカル管理者グループのメンバーである</p></td>
<td><p>Lync Server 2013 管理者が RTCUniversalServerAdmins のメンバーである</p></td>
<td><p>Lync Server 2013 管理者は Lync Server 2013 をインストールできますが、データベースをインストールすることはできません。 SQL Server 管理者は、lync server 2013 管理者が提供する Lync Server 管理シェルと Windows PowerShell コマンドレットを使用して、データベースをインストールします。 SQL Server 管理者が使用する Lync Server 2013 管理シェルは、フロントエンドサーバーにインストールされています。 これにより、Lync Server 2013 管理ツールを SQL Server ベースのサーバーにインストールする必要がなくなります。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

