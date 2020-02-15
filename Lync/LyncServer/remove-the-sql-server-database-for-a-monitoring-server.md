---
title: 監視サーバーの SQL Server データベースを削除する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Monitoring server
ms:assetid: aed5e394-d63e-4ad4-af40-f12d3a044344
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721848(v=OCS.15)
ms:contentKeyID: 49733781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5485f957bf0f172b52db602fba84819f493bc817
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>監視サーバーの SQL Server データベースを削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-04_

Microsoft Lync Server 2010 監視サーバーを削除した後、サーバーデータをホストしていた SQL Server データベースを削除することができます。 次の手順を使用して、トポロジビルダーから定義を削除し、データベースサーバーからデータベースとログファイルを削除します。

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>トポロジビルダーを使用して SQL Server データベースを削除するには

1.  Lync Server 2013 フロントエンドサーバーで、トポロジビルダーを開きます。

2.  トポロジビルダーで、[**共有コンポーネント**] に移動し、[ **sql server ストア**] をクリックし、削除または再構成された監視サーバーに関連付けられている sql server インスタンスを右クリックして、[**削除**] をクリックします。

3.  トポロジを公開し、レプリケーションの状態を確認します。

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a>SQL Server からデータベース ファイルを削除するには

1.  SQL Server ベースのサーバーにあるデータベースを削除するためには、削除しようとしているデータベース ファイルがある SQL Server ベースのサーバーの SQL Server sysadmins グループのメンバーでなければなりません。

2.  Lync Server 管理シェルを開きます。

3.  コマンドラインで、次のように入力します。
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    ここ\<で\> 、fqdn はデータベースサーバーの完全修飾ドメイン名 (fqdn)、 \<インスタンス\>はオプションの名前付きデータベースインスタンスです。

4.  **Uninstall-CsDataBase** コマンドレットから操作を確認するメッセージが表示される場合は、情報を読み、**Y** (または Enter) キーを押して操作を続行するか、**N** キーを押し、次に Enter キーを押してコマンドレットを停止します (問題がある場合)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

