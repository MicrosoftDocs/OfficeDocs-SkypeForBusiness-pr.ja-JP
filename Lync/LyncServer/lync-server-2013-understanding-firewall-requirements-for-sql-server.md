---
title: 'Lync Server 2013: SQL Server のファイアウォール要件について'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 586985c3059e12d358249a71dc2435c3be9254f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a>Lync Server 2013 での SQL Server のファイアウォール要件について

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

Standard Edition の展開の場合、ファイアウォールの例外は Lync Server 2013 のセットアップ中に自動的に作成されます。 ただし、Enterprise Edition の展開の場合は、SQL Server バックエンドサーバーでファイアウォールの例外を手動で構成する必要があります。 TCP/IP プロトコルでは、特定の IP アドレスに対して1つのポートを使うことができます。 つまり、SQL Server ベースのサーバーの場合、既定のデータベースインスタンスに既定の TCP ポート1433を割り当てることができます。 その他の場合は、SQL Server 構成マネージャーを使って、一意の未使用のポートを割り当てる必要があります。 ここでは、次の内容を説明します。

  - 既定のインスタンスを使用する場合のファイアウォール例外の要件

  - SQL Server Browser サービスのファイアウォール例外の要件

  - 名前付きインスタンスを使用するときの静的リッスンポートの要件

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a>既定のインスタンスを使用する場合のファイアウォール例外の要件

Lync Server 2013 を展開するときに、任意のデータベースに対して SQL Server の既定のインスタンスを使用している場合、フロントエンドプールから SQL Server の既定のインスタンスへの通信を確実にするために、次のファイアウォール規則要件が使用されます。


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
<td><p>SQL Server への受信</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a>SQL Server Browser サービスのファイアウォール例外の要件

SQL Server Browser サービスは、データベースインスタンスを探し、インスタンス (名前付きまたは既定) が使用するように構成されているポートを伝えます。


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
<td><p>トラフィック</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a>名前付きインスタンスを使用するときの静的リッスンポートの要件

Lync Server 2013 をサポートするデータベースの SQL Server 構成で名前付きインスタンスを使用している場合は、SQL Server 構成マネージャーを使って静的ポートを構成します。 名前付きインスタンスごとに静的ポートを割り当てると、ファイアウォールの各静的ポートに対して例外が作成されます。


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
<td><p>静的に定義された</p></td>
<td><p>トラフィック</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a>SQL Server ドキュメント

Microsoft SQL Server 2012 ドキュメントは、データベースのファイアウォールアクセスを構成する方法についての詳細なガイダンスを提供します。 Microsoft SQL Server 2012 の詳細については、「」の「SQL Server へのアクセスを[http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031)許可するように Windows ファイアウォールを構成する」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

