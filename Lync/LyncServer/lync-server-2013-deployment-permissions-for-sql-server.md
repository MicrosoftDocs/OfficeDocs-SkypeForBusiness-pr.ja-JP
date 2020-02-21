---
title: 'Lync Server 2013: SQL Server の展開権限'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d24a60c089efef55718dd71d889caade8f24949a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a>Lync Server 2013 での SQL Server の展開権限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

Microsoft SQL Server 2012 には、Lync Server 2013 をインストールして展開するときの特定の要件があります。 Windows と SQL Server はセキュリティを異なる方法で定義するため、Active Directory ドメインの管理者としてログインしても、SQL Server に対する権限は暗黙的に付与されません。 また、構成する SQL Server ベースのサーバーの sysadmin エンティティのメンバーであることも必要です。

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a>データベースおよび Lync Server のインストールに必要なアクセス許可

次のオプションは、Lync Server 2013 ファイルおよび SQL Server データベースをインストールするための3つのアクセス許可およびグループメンバーシップの関連付けの詳細です。 組織の要件に最もよく合うシナリオを選択してください。

### <a name="permissions-and-group-membership-associations"></a>アクセス許可およびグループ メンバーシップの関連付け

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
<th>役割-一般的な Lync Server 2013 アクセス許可およびグループメンバーシップ</th>
<th>アクセス許可によって実行できること</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 管理者</p></td>
<td><p>sysadmins SQL Server セキュリティ グループのメンバーシップが付与され、SQL Server のローカル Administrators グループのメンバーである必要があります。</p></td>
<td><p>RTCUniversalServerAdmins グループのメンバーである必要があります。</p></td>
<td><p>Lync server 2013 管理者には、Lync Server 2013 と SQL Server データベースの両方をインストールするための適切な権限があります。</p></td>
</tr>
<tr class="even">
<td><p>SQL Server 管理者</p></td>
<td><p>SQL Server sysadmin グループ メンバー (または相当するもの) および SQL Server のローカル Administrators グループのメンバー。</p></td>
<td><p>RTCUniversalServerReadOnly グループのメンバーである必要があります。</p></td>
<td><p>SQL Server 管理者には、Lync Server 2013 データベースと SQL Server データベースの両方をインストールするための適切な権限があります。</p></td>
</tr>
<tr class="odd">
<td><p>インストール作業を共有する両方の管理者</p></td>
<td><p>SQL Server の管理者は、sysadmins グループのメンバー (または相当するもの) および SQL Server のローカル Administrators グループのメンバーです。</p></td>
<td><p>Lync Server 2013 管理者が RTCUniversalServerAdmins のメンバーである</p></td>
<td><p>Lync Server 2013 管理者は Lync Server 2013 をインストールできますが、データベースをインストールすることはできません。 SQL Server 管理者は、lync server 2013 管理者が提供する Lync Server 管理シェルおよび Windows PowerShell コマンドレットを使用して、データベースをインストールします。 SQL Server 管理者が使用する Lync Server 2013 管理シェルは、フロントエンドサーバーにインストールされます。 これにより、Lync Server 2013 管理ツールを SQL Server ベースのサーバーにインストールする必要がなくなります。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

