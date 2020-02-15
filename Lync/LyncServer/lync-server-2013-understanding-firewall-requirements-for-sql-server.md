---
title: 'Lync Server 2013: SQL Server のファイアウォール要件について'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba04284106bcd1b0cbf17d214d8ad0b1a1ff9024
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a>Lync Server 2013 を使用した SQL Server のファイアウォール要件について

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

Standard Edition 展開の場合、ファイアウォール例外は Lync Server 2013 セットアップ時に自動的に作成されます。 ただし、Enterprise Edition の展開では、SQL Server バックエンドサーバー上でファイアウォール例外を手動で構成する必要があります。 TCP/IP プロトコルでは、特定のポートを複数の IP アドレスで共有することはできません。 このため、SQL Server ベースのサーバーでは、既定のデータベース インスタンスを既定の TCP ポート 1433 に割り当てることができます。 他のインスタンスに対しては、SQL Server Configuration Manager を使用して未使用の固有ポートを割り当てる必要があります。 このトピックでは、以下の内容について説明します。

  - 既定のインスタンスを使用する場合のファイアウォール例外の要件

  - SQL Server ブラウザー サービスのファイアウォール例外の要件

  - 名前付きインスタンスを使用する場合の静的リッスン ポートの要件

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a>既定のインスタンスを使用する場合のファイアウォール例外の要件

Lync Server 2013 を展開するときに、任意のデータベースに対して SQL Server の既定のインスタンスを使用している場合は、フロントエンドプールから SQL Server の既定のインスタンスへの通信を確実にするために、次のファイアウォール規則要件を使用します。


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
<th>Direction</th>
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


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a>SQL Server ブラウザー サービスのファイアウォール例外の要件

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
<th>Direction</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>受信</p></td>
<td><p>1434</p></td>
<td><p>受信</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a>名前付きインスタンスを使用する場合の静的リッスン ポートの要件

Lync Server 2013 をサポートするデータベース用の SQL Server 構成で名前付きインスタンスを使用する場合は、SQL Server 構成マネージャーを使用して静的ポートを構成します。 名前付きインスタンスごとに静的ポートを割り当てたら、ファイアウォールで静的ポートごとに例外を作成します。


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
<th>Direction</th>
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


</div>

<div>

## <a name="sql-server-documentation"></a>SQL Server ドキュメント

Microsoft SQL Server 2012 ドキュメントは、データベースのファイアウォールアクセスを構成する方法について詳細なガイダンスを提供します。 Microsoft SQL Server 2012 の詳細については、「」の「SQL Server へのアクセスを[http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031)許可するように Windows ファイアウォールを構成する」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

